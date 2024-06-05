## Serverless Backend (Cloudflare)

NOTE : We cannot use "express" in cloudflare, that's why we not follow above way for writing the logic of our backend in cloudflare, instead we go for "HONO" for writing express application in cloudflare

### how to Initialize a worker

    1. Initialize a worker
       npm create cloudflare -- my-app
    NOTE : Select no for Do you want to deploy your application
    2. Explore package.json dependencies
       "wrangler": "^3.0.0"
    NOTE : Notice express is not a dependency there

    3. Start the worker locally
       npm run dev
    
    4. How to return json?
       export default {
	    async fetch(request: Request, env: Env, ctx: ExecutionContext): Promise<Response> {
		    return Response.json({
			    message: "hi"
		    });
	      },
        };


### Deploying a worker

    1. Login to cloudflare via the wrangler cli
       npx wrangler login
    
    2. Deploy your worker
       npm run deploy
    NOTE : If all goes well, you should see the app up and running


# Local Webhook.site

## Introduction

Love [Webhook.site](https://webhook.site), but is always frustrated by the 100 request limitation? Fret not! Now, you can easily setup the service on your local machine, with no limitation on the requests - with the help of ngrok.

## Prerequisite
1. First, you'll need a ngrok account. Claim your free ngrok account in the official website [here](https://ngrok.com/).
2. After creating your account, claim your free ngrok domain from Cloud Edge > Domains. If you need a guide, you may follow this official [blog](https://ngrok.com/blog-post/free-static-domains-ngrok-users).

## Install
1. Clone this project to your local directory.
2. Duplicate the `.env.docker` file in this repository, and rename it as `.env`
3. Fill in the secrets in the `.env` file (NGROK_AUTHTOKEN & NGROK_DOMAIN)
4. Run `docker-compose up -d`
5. Go to your static ngrok url (for example, `xxx-xxx-xxx.ngrok-free.app`). 
6. You should now see the webhook.site service running on your local machine. Enjoy!

## QnA
1. You might need to start Cloudflare WARP service on your local machine if you encounter the following error message in ngrok service:
`failed to fetch CRL. errors encountered: Get "http://crl.ngrok.com/ngrok.crl"`
- It could be dns provider blocking, refer to [this Stackoverflow answer](https://stackoverflow.com/a/76405870)
- Regarless, by starting Cloudflare WARP, you should be able to start ngrok service afterwards.

## Acknowledgements

* The app was built on top of the completely open-source, MIT-licensed version of webhook.site. You should check it out [here](https://github.com/webhooksite/webhook.site)!
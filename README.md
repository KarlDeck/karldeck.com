# karldeck.com

Personal website hosted as a static site with AWS Amplify Hosting.

## Project layout

- `website-deployed/` is the production website and the source of truth for edits.
- `html5up-read-only/` is the original HTML5 UP template kept for reference.
- `amplify.yml` tells Amplify to publish `website-deployed/` as the site root.

The site is plain HTML, CSS, and JavaScript, so it has no dependency installation or
compilation step.

## Deploy with AWS Amplify

1. In the Amplify console, choose **Create new app** and connect the GitHub repository.
2. Select the branch to deploy (normally `main`).
3. Keep the build settings detected from the repository. Amplify will use
   `amplify.yml` from the repository root.
4. Save and deploy.

Every push to the connected branch will trigger a new deployment. The build fails
early if the production entry point or its main asset directories are missing.

## Preview locally

From the repository root, run:

```sh
python3 -m http.server 8000 --directory website-deployed
```

Then open <http://localhost:8000>.

# get_ip

Yes, you can set up and deploy your project to Vercel directly from GitHub without cloning it to your local machine. Here's how:

1. **Create a GitHub Repository**:
   - Go to GitHub and create a new repository for your project.

2. **Use GitHub's Web Interface**:
   - Navigate to your new repository on GitHub.
   - Use the "Add file" button to create a new file directly in the repository.

3. **Set Up Your Project**:
   - Create a directory named `api` by creating a new file with the path `api/get-ip.js`.

4. **Write the Serverless Function**:
   - In `get-ip.js`, add the following code:
     ```javascript
     export default function handler(req, res) {
       const ip = req.headers['x-forwarded-for'] || req.connection.remoteAddress;
       console.log('Visitor IP:', ip);
       res.status(200).send('IP logged');
     }
     ```
   - Commit the changes directly on GitHub.

5. **Deploy to Vercel**:
   - Go to Vercel and sign in.
   - Click on "New Project" and import your GitHub repository.
   - Follow the prompts to deploy your project.

6. **Access the API Route**:
   - Visit `https://your-vercel-project.vercel.app/api/get-ip` to trigger the serverless function.

7. **Check Vercel Logs**:
   - In the Vercel dashboard, navigate to your project and check the logs to see the IP addresses being logged.

This method allows you to manage and deploy your project entirely through GitHub's web interface and Vercel, without needing to clone the repository locally.

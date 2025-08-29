# Onboarding Checklist for New Lab Members

Welcome to the IXI Lab! This checklist will guide you through your first day and get you ready to contribute to our research projects.

## Step 1: Accept Your Invitation

1. **Check your email** for an invitation to join the IXI-Lab GitHub organization
2. **Click the invitation link** in the email
3. **Sign in** to your GitHub account (or create one if you don't have one)
4. **Accept the invitation** to join the organization

> **Note:** If you don't see the invitation email, check your spam folder or contact an Organization Owner.

## Step 2: Enable Two-Factor Authentication (2FA)

**This step is MANDATORY and must be completed before you can access any projects.**

1. **Go to GitHub Settings:**
   - Click your profile picture in the top right
   - Select "Settings"

2. **Navigate to Security:**
   - Click "Password and authentication" in the left sidebar

3. **Enable 2FA:**
   - Click "Enable two-factor authentication"
   - Choose your preferred method (app or SMS)
   - Follow the setup instructions
   - Save your recovery codes in a secure location

4. **Verify Setup:**
   - Your profile in the organization will show a "2FA" shield icon
   - This confirms you're ready to be added to project teams

> **Security Note:** 2FA is required for all lab members to protect our research data and code.

## Step 3: Introduce Yourself

1. **Join our communication channels:**
   - Slack workspace (invitation will be sent separately)
   - Lab email list
   - Any other communication platforms your team uses

2. **Introduce yourself:**
   - Share your name, role, and research interests
   - Mention which projects you'll be working on
   - Ask any questions you have about the lab

## Step 4: Get Assigned to a Team

1. **Contact your Team Leader or an Organization Owner:**
   - Let them know you've completed Steps 1-3
   - Request to be added to your project team(s)

2. **Wait for team assignment:**
   - You'll receive an email notification when added to a team
   - This will grant you access to the project repositories

3. **Verify access:**
   - Try accessing your project repository
   - You should be able to see the code and issues

## Step 5: Learn the Workflow

1. **Read the Member Handbook:**
   - Go to [MEMBER_HANDBOOK.md](MEMBER_HANDBOOK.md)
   - This contains everything you need to know about daily work

2. **Key concepts to understand:**
   - Issues and Pull Requests workflow
   - Data management policies
   - Code quality standards
   - Collaboration best practices

## Step 6: Set Up Your Development Environment

1. **Install required software:**
   - Git (if not already installed)
   - Python (version specified by your project)
   - Any project-specific tools

2. **Clone your first repository:**
   ```bash
   git clone https://github.com/IXI-Lab/your-project-name.git
   cd your-project-name
   ```

3. **Set up the project environment:**
   ```bash
   # Using conda (recommended)
   conda env create -f environment.yml
   conda activate project-name
   
   # Or using pip
   pip install -r requirements.txt
   ```

4. **Install the project package:**
   ```bash
   pip install -e .
   ```

## Step 7: Start Contributing

1. **Find your first task:**
   - Go to your project repository's "Issues" tab
   - Look for issues labeled "good first issue" or "help wanted"
   - Ask your Team Leader for guidance if needed

2. **Follow the standard workflow:**
   - Create a branch for your work
   - Make your changes
   - Submit a pull request
   - Participate in code review

## Getting Help

If you encounter any issues during onboarding:

- **Technical problems:** Create an issue in this repository
- **Access issues:** Contact your Team Leader or an Organization Owner
- **General questions:** Ask in the lab's communication channels

## Next Steps

Once you've completed this checklist:

1. **Read the Member Handbook** thoroughly
2. **Start working on your first issue**
3. **Attend lab meetings** to meet your colleagues
4. **Ask questions** - we're here to help!

---

**Welcome to the team! We're excited to have you join our research community.** 🎉

*Need help? Don't hesitate to ask - every question helps us improve our documentation and processes.*

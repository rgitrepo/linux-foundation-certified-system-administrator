# 18-Git Basic Operations: Understanding the Need for Version Control

Welcome to the world of Git, one of the most widely used modern version control systems in the world. Git is a powerhouse for tracking changes in source code during software development, but its use goes beyond coding. Let's explore the basics of Git and set up a global configuration for your user.

## Why Git?

Git is essential for several reasons:

- **Version Control**: Git allows you to track changes, revert to previous stages, and work on different versions of your projects simultaneously.
- **Collaboration**: Multiple people can work on the same project efficiently. Git manages the complexities of merging changes from different contributors.
- **Backup and Restore**: Files are saved as they are edited, providing a historical backup. You can jump back to any saved state at any time.
- **Branching and Merging**: You can create branches to experiment with new features or ideas in a contained area of your repository and merge them back to the main branch when they're ready.
- **Track Changes**: Not only can you see what changes were made, but you also get metadata like who made the changes and when, which is valuable for traceability.

## Git Global Configuration

Before you start using Git, it's important to configure your user information. Git uses this information to associate commits with an identity. This setup is especially crucial in a collaborative environment, ensuring that you get credit for your work and that your commits are not mixed up with someone else's.

### Setting Up User Information

To set your username and email globally in Git (which applies to all repositories you work with on your machine):

```bash
$ git config --global user.name "raja"
$ git config --global user.email "raja@devopsmasters.com"
```

Replace `"raja"` with your actual name and `"raja@devopsmasters.com"` with your email. This information will be attached to your commits.

### Checking Your Configuration

You can check your configuration anytime with:

```bash
$ git config --global --list
```

Expected output:

```
user.name=raja
user.email=raja@devopsmasters.com
```

This output confirms that your global Git configuration is set correctly.

## Conclusion

Git is a powerful tool that not only helps manage and track changes in your projects but also facilitates teamwork and collaboration. By setting up your global Git configuration, you're ensuring that all your contributions are marked with your identity, making it easier for others to collaborate with you. This setup is the first step into the vast capabilities that Git offers.

In the next tutorial, we'll dive into staging and committing changes, which are the core operations to save snapshots of your projects in the course of their development. Stay tuned!
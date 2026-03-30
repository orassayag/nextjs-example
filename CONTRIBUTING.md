# Contributing

Contributions to this project are [released](https://help.github.com/articles/github-terms-of-service/#6-contributions-under-repository-license) to the public under the [project's open source license](LICENSE).

Everyone is welcome to contribute to this project. Contributing doesn't just mean submitting pull requests—there are many different ways for you to get involved, including answering questions, reporting issues, improving documentation, or suggesting new features.

## How to Contribute

### Reporting Issues

If you find a bug or have a feature request:
1. Check if the issue already exists in the [GitHub Issues](https://github.com/orassayag/nextjs-example/issues)
2. If not, create a new issue with:
   - Clear title and description
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior
   - Your environment details (OS, Node version, browser)

### Submitting Pull Requests

1. Fork the repository
2. Create a new branch for your feature/fix:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Make your changes following the code style guidelines below
4. Test your changes thoroughly
5. Commit with clear, descriptive messages
6. Push to your fork and submit a pull request

### Code Style Guidelines

This project uses:
- **React 16.8+** with functional components and hooks
- **Next.js** for server-side rendering and API routes
- **SWR** for data fetching

Before submitting:
```bash
# Test the development server
npm run dev

# Build the production version
npm run build

# Test the production build
npm run start
```

### Coding Standards

1. **Functional components**: Use functional components with hooks
2. **API routes**: Keep API handlers simple and focused
3. **Data fetching**: Use SWR for client-side data fetching
4. **Error handling**: Handle loading and error states properly
5. **Naming**: Use clear, descriptive names for variables and functions
6. **File organization**: Keep components in `components/`, pages in `pages/`, and API routes in `pages/api/`

### Adding New Features

When adding new features:
1. Create components in the `components/` directory
2. Add page routes in the `pages/` directory
3. Add API endpoints in `pages/api/`
4. Update data models in `data.js` if needed
5. Test all routes and API endpoints
6. Update documentation if necessary

### Testing

Before submitting a pull request:
1. Test the development server (`npm run dev`)
2. Test all pages and routes manually
3. Verify API endpoints return correct data
4. Test error handling (404s, invalid IDs, etc.)
5. Build and test production version (`npm run build && npm run start`)

## Questions or Need Help?

Please feel free to contact me with any question, comment, pull-request, issue, or any other thing you have in mind.

* Or Assayag <orassayag@gmail.com>
* GitHub: https://github.com/orassayag
* StackOverflow: https://stackoverflow.com/users/4442606/or-assayag?tab=profile
* LinkedIn: https://linkedin.com/in/orassayag

Thank you for contributing! 🙏

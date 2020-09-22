# gatsby-source-smartrecruiters

> Loads job openings from smartrecruiters.com into Gatsby.js. Based on [gatsby-source-greenhouse](https://github.com/tumblbug/gatsby-source-greenhouse).

## Installation

```bash
npm install gatsby-source-smartrecruiters
```

or

```bash
yarn add gatsby-source-smartrecruiters
```

## Usage

Edit `gatsby-config.js` to use the plugin:

```
{
  ...
  plugins: [
    ...
    {
      resolve: `gatsby-source-smartrecruiters`,
      options: {
        companyIdentifier: `{COMPANY_IDENTIFIER}`,
        fetchDetailed: true,
      },
    },
  ]
}
```

When the option `fetchDetailed` is set to `true`, the plugin will resolve and fetch the detailed job postings individually, which include the application link and contents of the job ad.

## Querying

You can query the all `JobPost` created by the plugin as follows:

```graphql
{
    allSmartRecruitersJobPost {
        edges {
            node {
                ...
            }
        }
    }
}
```

You can also query all `JobPost` broken out for each department:

```graphql
{
  allSmartRecruitersDepartment {
    edges {
      node {
        name
        childrenSmartRecruitersJobPost {
          title
        }
      }
    }
  }
}
```

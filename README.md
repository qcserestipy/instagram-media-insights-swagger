# Instagram Media Insights Swagger

OpenAPI/Swagger specification for the Instagram Media Insights API, enabling developers to generate type-safe API clients in any programming language.

## Overview

This project provides comprehensive Swagger/OpenAPI 2.0 specifications for Instagram's APIs. The specifications describe endpoints, request parameters, response schemas, and authentication mechanisms for retrieving insights data on Instagram media objects and accounts, as well as managing access tokens.

**Three separate specifications are provided:**
- `media/swagger.yaml` - Media Insights API (insights on posts, reels, stories, comments)
- `account/swagger.yaml` - Account Insights API (insights on Instagram business/creator accounts, stories, media management)
- `page/swagger.yaml` - Facebook Page API (retrieve page access tokens from Facebook Graph API)

## Features

- **Complete API Specification**: Full definition of the Instagram Media Insights API endpoints
- **Type-Safe Client Generation**: Generate clients in any language supported by Swagger/OpenAPI tools
- **Detailed Documentation**: Inline descriptions of metrics, parameters, and response structures
- **Authentication Support**: Includes Instagram Graph API access token security definitions

## API Coverage

The specification covers:

### Media Insights Endpoint
Get insights data on Instagram Media objects (Feed posts, Reels, Stories):
- **Available Metrics**: Comments, likes, shares, reach, impressions, views, engagement metrics, and more
- **Time Periods**: Support for day, week, 28-day, month, lifetime, and total_over_range periods
- **Breakdowns**: Action type and navigation action type breakdowns

### Account Insights Endpoint
Get insights data on Instagram business or creator accounts:
- **Interaction Metrics**: accounts_engaged, comments, likes, reach, shares, views, total_interactions, profile_links_taps, and more
- **Demographic Metrics**: engaged_audience_demographics, follower_demographics with age, city, country, and gender breakdowns
- **Time Periods**: Support for day and lifetime periods
- **Breakdowns**: media_product_type, follow_type, contact_button_type breakdowns
- **Time Ranges**: Support for since/until parameters and timeframe specifications

### Facebook Page API
Retrieve page access tokens from Facebook Graph API:
- **Page Access Tokens**: Get page access tokens to interact with Instagram Business Accounts
- **Field Selection**: Request specific fields including access_token

### General Features
- **Error Handling**: Comprehensive error response schemas
- **Authentication**: Instagram Graph API access token support

## Usage

### Generating API Clients

You can generate API clients for any programming language using tools like:

- **Swagger Codegen**: `swagger-codegen generate -i v24.0/media/swagger.yaml -l <language>`
- **OpenAPI Generator**: `openapi-generator generate -i v24.0/account/swagger.yaml -g <language>`
- **Online Editor**: Import the spec at [editor.swagger.io](https://editor.swagger.io)

### Example: Go Client Implementation

A complete Go client implementation based on this specification is available at:
**[https://github.com/qcserestipy/instagram-api-go-client](https://github.com/qcserestipy/instagram-api-go-client)**

This serves as a reference implementation demonstrating how to generate and use a type-safe client. In principle, anyone can generate clients for their preferred language (Python, Java, JavaScript, Ruby, PHP, etc.) using the same Swagger specification.

## API Versioning

- **Current Version**: v24.0
- The specification follows Facebook Graph API versioning

## Getting Started

1. **Review the Specifications**: 
   - Check `v24.0/media/swagger.yaml` for media insights and comments
   - Check `v24.0/account/swagger.yaml` for account insights, stories, and media management
   - Check `v24.0/page/swagger.yaml` for Facebook page access tokens
2. **Generate a Client**: Use Swagger Codegen or OpenAPI Generator for your language
3. **Obtain Access Token**: Get a Facebook User access token from Facebook Developer Portal
4. **Get Page Access Token**: Use the page API to retrieve your page access token
5. **Start Making Requests**: Use your generated client to fetch Instagram insights

## Authentication

The API requires an Instagram Graph API Page access token. See [Facebook's documentation on access tokens](https://developers.facebook.com/docs/facebook-login/guides/access-tokens/#pagetokens) for more information.

## Limitations

- Insights data may not exist or be temporarily unavailable (returns empty data set)
- Metrics data can be delayed up to 48 hours
- Historical data is stored for up to 2 years
- Only organic interactions are counted (ad interactions excluded)
- Story metrics are only available for 24 hours
- Story metrics with values less than 5 return error code 10

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests to improve the specification.

## License

See [LICENSE](LICENSE) file for details.

## Resources

- [Instagram Graph API Documentation](https://developers.facebook.com/docs/instagram-api)
- [Swagger/OpenAPI Specification](https://swagger.io/specification/v2/)
- [Go Client Implementation](https://github.com/qcserestipy/instagram-media-insights-go-client)

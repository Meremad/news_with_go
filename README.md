# News Search App

## Overview
News Search App is a web application built with Go that allows users to search for news articles using the [NewsAPI](https://newsapi.org/). The application fetches articles based on user queries and displays them in a simple and responsive UI.

This project is based on the [news-demo-starter-files](https://github.com/Freshman-tech/news-demo-starter-files) repository, but instead of regular CSS, Tailwind CSS was used for styling.

## Features
- Search for news articles by topic
- Display results with title, description, source, date, and image
- Pagination support
- Responsive UI using Tailwind CSS
- Built-in templating with Go's `html/template`

## Installation & Setup
### Prerequisites
- Go installed on your machine (version 1.16 or later)
- A valid API key from [NewsAPI](https://newsapi.org/)

### Steps
1. Clone the repository:
   ```sh
   git clone https://github.com/Meremad/news_with_go.git
   cd news_with_go
   ```
2. Install dependencies:
   ```sh
   go mod tidy
   ```
3. Run the application with your API key:
   ```sh
   go run main.go -apikey=YOUR_NEWSAPI_KEY
   ```
   The API key is passed using the `flag` package in Go, allowing it to be provided as a command-line argument.
4. Open your browser and visit:
   ```sh
   http://localhost:3000
   ```

## Project Structure
```
news_with_go/
├── index.html         # HTML template for rendering results
├── main.go            # Main Go application
├── go.mod             # Go module file
└── go.sum             # Dependencies
```

## API Usage
The application makes HTTP requests to the NewsAPI endpoint:
```
https://newsapi.org/v2/everything?q={search_term}&pageSize=20&page={page}&apiKey={api_key}
```

## Environment Variables
Instead of passing the API key via command line, you can also set it as an environment variable:
```sh
export NEWSAPI_KEY=your_api_key
```
Then run the application as:
```sh
API_KEY=$NEWSAPI_KEY go run main.go
```


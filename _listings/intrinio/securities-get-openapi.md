---
swagger: "2.0"
x-collection-name: Intrinio
x-complete: 0
info:
  title: Intrinio API Securities
  description: Returns security list and information for all securities covered by
    Intrinio.
  version: 1.0.0
host: api.intrinio.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /historical_data:
    get:
      summary: Historical Data
      description: Returns the historical data for for a selected identifier (ticker
        symbol or index symbol) for a selected tag.  The complete list of tags available
        through this function are available here.  Income statement, cash flow statement,
        and ratios are returned as trailing twelve months values by default, but can
        be changed with the type parameter.  All other historical data points are
        returned as their value on a certain day based on filings reported as of that
        date.
      operationId: historical-data
      x-api-path-slug: historical-data-get
      parameters:
      - in: query
        name: end_date
        description: 'the latest date for which to return data: YYYY'
        type: string
      - in: query
        name: frequency
        description: 'the frequency of the historical prices &amp; valuation data:
          daily | weekly | monthly | quarterly | yearly'
        type: string
      - in: query
        name: identifier
        description: the stock market ticker symbol associated with the company&rsquo;s
          common stock or index
        type: string
      - in: query
        name: item
        description: the specified standardized tag requested
        type: string
      - in: query
        name: page_number
        description: an integer greater than or equal to 1 for specifying the page
          number for the return values
        type: string
      - in: query
        name: page_size
        description: an integer greater than 1 for specifying the number of results
          on each page
        type: string
      - in: query
        name: sequence
        description: in function)
        type: string
      - in: query
        name: show_date
        description: 'in, false by default) if true, the function will return the
          date value, and if false the function will return the data point value for
          a given query: true | false'
        type: string
      - in: query
        name: sort_order
        description: 'the order of the historical stock price dates: asc | desc'
        type: string
      - in: query
        name: start_date
        description: 'the earliest date for which to return data: YYYY'
        type: string
      - in: query
        name: type
        description: the type of periods requested
        type: string
      responses:
        200:
          description: OK
      tags:
      - Market Data
      - Historical Data
  /companies:
    get:
      summary: Company Master
      description: Returns the master list of all companies covered by the Intrinio
        Data Marketplace.  You can view the Company/Security Master here.
      operationId: company-master
      x-api-path-slug: companies-get
      parameters:
      - in: query
        name: latest_filing_date
        description: 'a date value that returns the list of companies whose latest
          SEC filing was filed on or after this date: YYYY'
        type: string
      - in: query
        name: page_number
        description: an integer greater than or equal to 1 for specifying the page
          number for the return values
        type: string
      - in: query
        name: page_size
        description: an integer greater than 1 for specifying the number of results
          on each page
        type: string
      - in: query
        name: query
        description: a string query search of company name or ticker symbol with the
          returned results being the relevant companies in compacted list format
        type: string
      responses:
        200:
          description: OK
      tags:
      - Market Data
      - Companies
  /securities:
    get:
      summary: Securities
      description: Returns security list and information for all securities covered
        by Intrinio.
      operationId: securities
      x-api-path-slug: securities-get
      parameters:
      - in: query
        name: exch_symbol
        description: 'the Intrinio Stock Market Symbol, to specify the exchange for
          the list of securities:'
        type: string
      - in: query
        name: identifier
        description: 'the identifier for the legal entity or a security associated
          with the company:'
        type: string
      - in: query
        name: last_crsp_adj_date
        description: 'a date value that returns the list of securities that have had
          adjusted stock prices due to a corporate event after this date: YYYY'
        type: string
      - in: query
        name: page_number
        description: an integer greater than or equal to 1 for specifying the page
          number for the return values
        type: string
      - in: query
        name: page_size
        description: an integer greater than 1 for specifying the number of results
          on each page
        type: string
      - in: query
        name: query
        description: a string query search of security name or ticker symbol with
          the returned results being the relevant securities in compacted list format
        type: string
      responses:
        200:
          description: OK
      tags:
      - Market Data
      - Securities
x-streamrank:
  polling_total_time_average: "0.94"
  polling_size_download_average: "29095.58"
  streaming_total_time_average: "0.5"
  streaming_size_download_average: "14559.58"
  change_yes: "19"
  change_no: "3726"
  time_percentage: "47"
  size_percentage: "50"
  change_percentage: "1"
  last_run: "2018-02-19"
  days_run: "3"
  minute_run: "0"
---
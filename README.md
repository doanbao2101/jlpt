# JLPT App

Welcome to the Japanese Exam Preparation App project! This app is designed to help users practice for the JLPT (Japanese Language Proficiency Test) with a focus on three key sections: Vocabulary & Grammar, Reading, and Listening.

## Project Overview

This project aims to provide a comprehensive platform for learners preparing for various levels of the JLPT (N5-N1). The app is designed with the following features:

- **Interactive Quizzes**: Users can practice questions for Vocabulary, Grammar, Reading, and Listening.
- **Progress Tracking**: Monitor performance and track improvement over time.
- **Real-Time Feedback**: Get instant feedback on answers with explanations for incorrect responses.
- **Mobile-First Design**: Optimized for both desktop and mobile users.

## Key Technologies

This project is built using the following technologies:

### Front-End
- **FlutterFlow**: For building a responsive and interactive user interface.

### Back-End
- **Supabase**: For database management, authentication, and REST API generation.
- **Python**: Used for auxiliary tasks like data preprocessing and handling ETL pipelines.

### Database
- **PostgreSQL** (via Supabase): Stores user data, exam questions, and progress.

### Additional Tools
- **Web Scraping**: Python libraries like `BeautifulSoup` are used to collect data for questions from reliable sources.
- **Apache Spark**: For ETL processes if handling large datasets.
- **Docker**: To containerize the application for easy deployment.

## Installation & Setup

To get started, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/doanbao2101/jlpt.git

2. File Structure
   ```bash
   .
   ├── client/                  # Front-End code
   ├── server/                  # Back-End code
   ├── data/                    # Raw and processed data
   ├── scripts/                 # Data scraping and ETL scripts
   ├── README.md                # Project documentation
   └── .env                     # Environment variables (not included in the repo)
3. Data Sources:
   
   Link 1: 'https://dethitiengnhat.com/jlpt/N1/201412/1'

   Link 2: 'https://m.lophoctiengnhat.com/de-thi-nang-luc-tieng-nhat-jlpt_n1.html'

   Link 3: 'https://kosei.vn/hot-33-tong-hop-de-thi-jlpt-n1-cac-nam-tai-mien-phi-ban-day-du-n3016.htm'

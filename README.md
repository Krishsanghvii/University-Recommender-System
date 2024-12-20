## **Overview**
This University Recommendation System is a web-based application built using **Flask**, **Python**, and **Scikit-learn**. It recommends universities to users based on their SAT scores and tuition fee preferences for **undergraduate** and **graduate** programs. The application uses **K-Nearest Neighbors (KNN)** for making predictions and recommendations.

## **Features**
- **Undergraduate Recommendations**: Suggests universities based on SAT scores and maximum tuition fee.
- **Graduate Recommendations**: Suggests universities based on GRE scores and GPA.
- **Data Handling**: The system processes university ranking data, extracts and normalizes relevant fields like SAT scores, tuition fees, and acceptance rates.
- **Recommendation Engine**: Based on user preferences (SAT score, tuition fee, etc.), the system provides the top 5 universities.

## **Technologies Used**
- **Python**: Primary programming language.
- **Flask**: Web framework to create the web application.
- **Scikit-learn**: Machine learning library for KNN algorithm implementation.
- **Pandas**: For handling datasets.
- **NumPy**: For numerical operations.
- **Matplotlib**: For plotting (if needed).
- **HTML/CSS/Bootstrap**: For frontend development and displaying results.

## **Project Structure**
```
/University-Recommender-System
│
├── /static
│   └── (Static files like CSS, images)
│
├── /templates
│   └── index.html
│   └── graduate.html
│   └── undergraduate.html
│   └── (HTML files for rendering)
│
├── app.py                    # Main application (Flask web server)
├── UnderGraduateServer.py     # Server-side logic for undergraduate recommendations
├── cleanData.tsv              # Processed data for recommendations
├── requirements.txt           # Required Python packages
└── /WebScraped_data/csv       # Folder for the web scraped data (CSV)
```

## **Installation**

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/University-Recommender-System.git
   cd University-Recommender-System
   ```

2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the application:
   ```bash
   python app.py
   ```

4. Visit the application at `http://127.0.0.1:5000/` in your web browser.

## **Usage**
1. **Home Page**: Navigate to the home page for general information and links to undergraduate and graduate recommendation sections.
   
2. **Undergraduate Recommendations**: Input your SAT score and maximum tuition fee to get the top 5 recommended universities based on these factors.
   
3. **Graduate Recommendations**: Input your GRE scores (Verbal, Quantitative, Analytical) and CGPA to receive graduate school recommendations.
   
4. **KNN Algorithm**: The application uses K-Nearest Neighbors (KNN) to find similar universities based on input features and outputs the top recommended universities.

## **Data Flow**
1. **Data Scraping**: The system scrapes university data from [4icu](http://www.4icu.org/us/), which includes SAT scores, tuition fees, acceptance rates, and other relevant attributes.
   
2. **Preprocessing**: The scraped data is processed and normalized using custom Python functions (in `UnderGraduateServer.py`), converting raw values into a usable format.

3. **Recommendation System**: Based on the user profile (SAT/tuition for undergraduates, GRE/cgpa for graduates), the **KNN algorithm** selects the top universities by comparing the user input to pre-processed data.

4. **Web Interface**: Flask serves the web interface, where users can input their data and receive real-time recommendations.

## **Key Files**
- **app.py**: Flask app that runs the web server and handles routes for the user interface.
- **UnderGraduateServer.py**: Contains logic to process university data, calculate recommendations, and return the best-fit universities.
- **cleanData.tsv**: This file stores the cleaned university dataset, ready for recommendations.
- **requirements.txt**: Lists the Python dependencies needed to run the application, such as Flask, pandas, scikit-learn, etc.

## **Running the Code**
To run the project:

1. Clone or download the project.
2. Set up a virtual environment (optional but recommended).
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows: env\Scripts\activate
   ```
3. Install dependencies using `pip`:
   ```bash
   pip install -r requirements.txt
   ```
4. Start the Flask server:
   ```bash
   python app.py
   ```
5. Visit `http://127.0.0.1:5000/` in your browser.

## **Recommendation Algorithm**

### **K-Nearest Neighbors (KNN)**
- **Distance Metric**: Euclidean distance is used to measure similarity between the user input and university data.
- **Parameters**:
  - **k (neighbors)**: Number of closest universities to consider when making recommendations. Default is 7.
  - **Input Features**: For undergraduate, SAT score and maximum tuition fee are used. For graduate, GRE scores (verbal, quantitative, analytical) and CGPA are used.
  
### **Output**:
- The top 5 recommended universities are displayed with relevant details such as rank, city, tuition, SAT score, and acceptance rate.

## **Future Improvements**
- **Data Augmentation**: Incorporate more features like location preference, program availability, etc., into the recommendation algorithm.
- **Deployment**: Host the application on a cloud server (e.g., AWS, Heroku) for live access.
- **User Authentication**: Implement a login system to save user preferences for future sessions.

---

## **License**
This project is open-source and available under the MIT License. See the LICENSE file for more details.

---

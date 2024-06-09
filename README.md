# python-project

To avoid potential issues with running pip as the root user, it's recommended to use a virtual environment.

1. Create a Virtual Environment

       python3 -m venv venv

2. Activate the Virtual Environment:

       source venv/bin/activate

3. Install Dependencies in the Virtual Environment:

       pip install -r requirements.txt

4. Run the Tests with Coverage:

       coverage run --omit='test.py' -m pytest test.py

5. Generate the Coverage Report:

       coverage report

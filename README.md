# Sneap
class ResumeCreator:
    def __init__(self):
        self.resume_data = {}

    def get_personal_info(self):
        print("Enter Personal Information:")
        self.resume_data['name'] = input("Name: ")
        self.resume_data['email'] = input("Email: ")
        self.resume_data['phone'] = input("Phone: ")

    def get_education_info(self):
        print("Enter Education Information:")
        degree = input("Degree: ")
        institution = input("Institution: ")
        year = input("Year: ")
        self.resume_data.setdefault('education', []).append({
            'degree': degree,
            'institution': institution,
            'year': year
        })

    def get_experience_info(self):
        print("Enter Experience Information:")
        company = input("Company: ")
        position = input("Position: ")
        duration = input("Duration: ")
        self.resume_data.setdefault('experience', []).append({
            'company': company,
            'position': position,
            'duration': duration
        })

    def generate_resume(self):
        print("\n--- Resume ---")
        print("Name:", self.resume_data['name'])
        print("Email:", self.resume_data['email'])
        print("Phone:", self.resume_data['phone'])

        print("\nEducation:")
        for education in self.resume_data.get('education', []):
            print("Degree:", education['degree'])
            print("Institution:", education['institution'])
            print("Year:", education['year'])

        print("\nExperience:")
        for experience in self.resume_data.get('experience', []):
            print("Company:", experience['company'])
            print("Position:", experience['position'])
            print("Duration:", experience['duration'])

    def start(self):
        print("Resume Creator")
        self.get_personal_info()
        self.get_education_info()
        self.get_experience_info()
        self.generate_resume()


resume_app = ResumeCreator()
resume_app.start()

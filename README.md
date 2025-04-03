# scaling-memory
import streamlit as st

st.title("Employee Event Registration Survey")

# Ask how many employees are attending
num_employees = st.number_input("How many employees are attending?", min_value=1, step=1)

employee_data = []

# Loop to collect info
for i in range(num_employees):
    st.subheader(f"Employee #{i + 1}")
    name = st.text_input(f"Name", key=f"name_{i}")
    email = st.text_input(f"Email", key=f"email_{i}")
    phone = st.text_input(f"Phone Number", key=f"phone_{i}")

    employee_data.append({
        "Name": name,
        "Email": email,
        "Phone": phone
    })

# Show data on submit
if st.button("Submit"):
    st.success("Survey submitted successfully!")
    st.write("Collected Employee Data:")
    st.write(employee_data)

# FHIR-Api-Interview

Mô tả tình huống
Bạn cần xây dựng một microservice đơn giản để kiểm tra tính hợp lệ của các thông điệp FHIR Patient.
 Hệ thống này sẽ nhận các thông điệp JSON thông qua REST API và trả về kết quả validation chi tiết.
Yêu cầu cụ thể

Tạo một Spring Boot application từ đầu với cấu trúc rõ ràng

Triển khai RESTful API với endpoint validation

Xây dựng hệ thống validation sử dụng HAPI FHIR, xử lý đa luồng

Tích hợp cơ chế cache thông minh sử dụng reflection

Viết unit test đầy đủ cho validator

Payload đầu vào API và Unit test
 
Message correct:

{

  "resourceType": "Patient",

  "id": "example",

  "name": [{"use": "official", "family": "Doe", "given": ["John"]}],

  "gender": "male",

  "birthDate": "1980-01-01"

}

Message incorrect:

{

  "resourceType": "Patient",

  "id": "example-invalid",

  "name": [{"use": "official", "family": 123, "given": "Jane"}],

  "gender": "alien",

  "birthDate": "not-a-date"

}

// ❌ invalid: not a valid date format

// ❌ invalid: not one of allowed enum values (male, female, other, unknown)

// ❌ invalid: should be a string

// ❌ invalid: should be an array of strings
 

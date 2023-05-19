# Doctor App


## Built With
* `Java 17`
* `Maven 4.0.0`
* `MySql Ver 8.0.32`
* `Spring Boot 3.0.5`
* `IntelliJ IDEA 2023.1 (Community Edition)`
## Data Flow

### 1. Models:
* It consists of **Doctor** ,**Patient**, **Appontment** and **AuthenticationToken** entity classes along with their data members and member functions
* Used **_@Table_** and **_@Entity_** annotations inside the entity class.
* Used Lombok to reduce boilerplate code for pojo class.By using Lombok annotations like _**@Data,**_ **@_NoArgsConstructor_**, **_@AllArgsConstructor_** getters and setters for those object generate automatically.
* Used **_@OneToOne_**, **_@OneToMany_**, **_@ManyToOne_**. mapping.

### 2. Controllers:
* It consists of  **DoctorController** ,**PatientController**, **AppintmentController** classes in which used the annotations like **@RestController** to annotate the class as Controller.
* Used annotation **_@GetMapping_** , **_@PostMapping_** , **_@PutMapping_** , **_@DeleteMapping_** to map the HTTP web requests to the specific handler methods.

<br>

### API Reference:
<br>

>Doctor's API References
<br>

* Add Doctors:
```*.sh-session
  http://localhost:8080/doctor
```

* Get All Appointment of Doctor By DocId:
```*.sh-session
 http://localhost:8080/doctor/{docId}/appointments
```
<br>

>Patient's API References:
<br>

* Patient signup
```*.sh-session
  http://localhost:8080/patient/signup
```

* Patient signin:
```*.sh-session
http://localhost:8080/patient/signin
```


* Get All Doctors:
```*.sh-session
http://localhost:8080/patient/doctors?userEmail={userEmail}&token={token}
```

* Cancel Appointment:
```*.sh-session
 http://localhost:8080/patient/appointment?userEmail={userEmail}&token={token}
```

>Appointment's API References:
<br>

* Book Appointment:
```*.sh-session
  http://localhost:8080/laptop
```

### 3. Services:
* It consists of **DoctorService** ,**PatientService**, **AppointmentService**, **AuthenticationService** and **IAuthService**classes in which provide some business functionalities of every handler methods.
* Used _**@Service**_ annotation to indicate that a class belongs to the service layer.
* Used **_@Transactional_** annotation to separate transaction management code from the code for business logic on the update and delete methods.

### 4. Repositories:
* It consists of **IDoctorRepo** ,**IPatientRepo**, **ITokenRepo**, and **IAppointmentRepo** interfaces that extends JpaRepository which is interface for generic inbuilt CRUD operations on a repository for a specific type. Usually represent the database access layer in an application.
* Used **Iterable** to manage the data of entity classes by performing CRUD operations.
* Used _**@Repository**_ annotation is used to indicate that the class provides the mechanism for storage, retrieval, search, update and delete operation on objects.
* Used _**@Modifying**_ annotation wrote named parameters query using @Query annotation to insert, update, or delete an entity.


## Project Summary:
* The aim of this project to create A Doctor App.So A patient can book an appointment and cancel an appintment with doctor. Patient need to signup and signin before book an appointment.
* In this project I performed CRUD operation like add,get,delete and update.
* perform **_one to one_**, **_one-to-many_**, **_many-to-one_** relationships mapping between entity classes.
* Used interface JpaRepository for generic CRUD inbuilt operations like save,saveAll,updateById, etc.
* Used our own custom finder methods and wrote operations using custom queries.
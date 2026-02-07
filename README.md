# University Management System Ontology

A comprehensive OWL (Web Ontology Language) ontology for modeling a University Management System, developed as a semester project for Knowledge Representation.

## Project Information

- **Author**: Rafay Saif (VR546150)
- **Course**: Knowledge Representation
- **File**: `University-Management-Project(VR546150).owl`

## Overview

This ontology provides a formal representation of a university management system, capturing the relationships between universities, faculties, departments, programs, courses, students, professors, and administrative staff. It uses OWL (Web Ontology Language) to define classes, properties, and logical axioms that model the structure and operations of a typical university.

## Ontology Structure

### Classes (20 Classes)

The ontology defines 20 classes organized in a hierarchical structure:

| Category | Classes |
|----------|---------|
| **Organizational** | University, Faculty, Department |
| **Academic Programs** | Program, UndergraduateProgram, GraduateProgram |
| **Courses** | Course, CourseSection |
| **People** | Person, Student, UndergraduateStudent, GraduateStudent, Professor, TeachingAssistant, AdministrativeStaff |
| **Administrative** | Enrollment, Examination, Classroom, Schedule, Degree |

#### Class Hierarchy

```
Person
├── Student
│   ├── UndergraduateStudent
│   └── GraduateStudent
├── Professor
├── TeachingAssistant
└── AdministrativeStaff

Program
├── UndergraduateProgram
└── GraduateProgram
```

### Object Properties (40 Properties)

The ontology includes 40 object properties organized into categories:

#### Structural Properties
- `hasFaculty`, `hasDepartment`, `offersProgram`, `offersCourse`, `hasSection`
- `belongsToUniversity`, `belongsToFaculty`, `belongsToDepartment`

#### Programs & Degrees
- `requiresCourse`, `leadsToDegree`, `enrolledInProgram`, `completedDegree`
- `hasMajor`, `hasMinor`

#### Teaching & Learning
- `teachesCourse`, `teachesSection`, `assistsTeaching`
- `takesCourse`, `attendsSection`, `supervisesStudent`

#### Enrollment & Exams
- `hasEnrollment`, `enrollmentForCourse`, `enrollmentForStudent`
- `hasExamination`, `attemptsExam`, `evaluatesExam`

#### Scheduling & Infrastructure
- `scheduledIn`, `hasSchedule`, `heldInClassroom`, `examSchedule`

#### Administration
- `managesDepartment`, `managesProgram`, `managesCourse`
- `assignedToFaculty`, `reportsTo`

#### Advanced / Reasoning
- `advisorOf`, `coTeachesWith`, `prerequisiteOf`, `successorCourse`, `equivalentCourse`

### Logical Axioms

The ontology includes several logical axioms for reasoning:

1. **Disjoint Classes**: Student, Professor, and AdministrativeStaff are mutually exclusive
2. **Student Constraints**: 
   - Must be enrolled in at least one Program
   - Must take at least one Course
3. **Professor Constraints**: Must teach at least one Course
4. **UndergraduateStudent**: Must be enrolled in an UndergraduateProgram

## Usage

### Opening the Ontology

The ontology can be opened and edited using:

- **Protégé** (recommended): [https://protege.stanford.edu/](https://protege.stanford.edu/)
- **WebProtégé**: Online collaborative editing
- Any OWL-compatible ontology editor

### Querying the Ontology

Use SPARQL queries to extract information:

```sparql
PREFIX uni: <http://www.example.org/university#>

# Find all students enrolled in a program
SELECT ?student ?program
WHERE {
    ?student a uni:Student .
    ?student uni:enrolledInProgram ?program .
}
```

### Reasoning

The ontology supports OWL reasoning to:
- Infer class membership
- Check consistency
- Validate constraints
- Discover relationships

## Technical Specifications

- **Ontology Language**: OWL (Web Ontology Language)
- **Serialization Format**: RDF/XML
- **Namespace**: `http://www.example.org/university#`
- **Base URI**: `http://www.example.org/university`

## File Structure

```
Knowledge-Representation-Project/
├── README.md                                    # This file
├── REPORT.md                                    # Detailed project report
└── University-Management-Project(VR546150).owl # OWL ontology file
```

## License

This project is created for educational purposes as part of a Knowledge Representation course.

## Author

**Rafay Saif** (VR546150)

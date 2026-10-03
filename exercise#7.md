classDiagram
    class User {
        -int id
        -string FullName
    }

    class Identity {
        <<abstract>>
        -User propietario
        -int DailyLimit
    }

    class Personal {
        -int NationalID
    }

    class Business {
    }

    class Processors {
        <<abstract>>
        -int id
        -float Fee
    }

    class NationalBank {
        +postTransaction()
        +Deposit()
        +withdrawal()
        +DomesticTransfer()
    }

    class PacificBank {
        +DomesticTransfer()
        +payroll()
    }

    class SWIFTGateway {
        +InternationalTransfer()
    }

    Identity <|-- Personal
    Identity <|-- Business
    Processors <|-- NationalBank
    Processors <|-- PacificBank
    Processors <|-- SWIFTGateway
    Identity --> User : propietario

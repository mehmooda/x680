# Work In Progress
-

Goal

Final Syntax TBD

    x680!(r#"
    FooProtocol DEFINITIONS ::= BEGIN
    FooQuestion ::= SEQUENCE {
        trackingNumber INTEGER,
        question       IA5String
    }
    FooAnswer ::= SEQUENCE {
        questionNumber INTEGER,
        answer         BOOLEAN
    }
	END
	"#)
    
    der_decode!(fq, FooProtocol::FooQuestion)
    der_encode!(fa, FooProtocol::FooAnswer)

    fn answer_question(buffer: &[u8]) -> Vec<u8> {
	    let buffer: &[u8] = ...
	    let question: FooQuestion = fq(buffer).unwrap();
            let answer = FooProtocol::FooAnswer {
            questionNumber: 1,
            answer: true
	    }
        return fa(answer).unwrap()
    }

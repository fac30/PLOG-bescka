## Guidance
Answer the following questions considering the learning outcomes for
- [Week 03](https://learn.foundersandcoders.com/course/syllabus/developer/week03-project03-server/learning-outcomes/)

Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of some of the learning outcomes you have achieved this week.
Developed an Express server with TS. Deployed RESTful API infrastructure. Designed endpoints and logic for getting/ sending and manipulating data. 

routing example: 
```ts
import { Router } from 'express';
import { getQuiz, submitAnswer } from '../controllers/quizController';

const router = Router();

router.get('/', getQuiz);

router.post('/:quizId/answer', submitAnswer);

export default router;
```
with context from App.ts: 

```ts
import { Request, Response, NextFunction } from 'express';
dotenv.config();

const PORT = process.env.PORT || 5000;

const app = express();

function logger(request: Request, response: Response, next: NextFunction) {
  console.log(`${request.method} ${request.url}`);
  next();
}
app.use(logger);

app.use('/api/quiz', quizRoutes);

```

unit test example: 
```ts
  it('should return options in a random order', () => {
    const correctAnswer = 'Paris';
    const countries = [
      { capital: 'London' },
      { capital: 'Berlin' },
      { capital: 'Madrid' },
      { capital: 'Rome' },
      { capital: 'Paris' },
    ];
    
    const options1 = generateOptions(correctAnswer, countries);
    const options2 = generateOptions(correctAnswer, countries);
    expect(options1).not.toEqual(options2); // Randomness test
  });
```

Deployed automated scripts for db config, quiz generation logic (service), implemented integration testing with mocking and draft functional testing with config. 

 ### 2. Show an example of some of the learning outcomes you have struggled with and/or would like to re-visit.
> TDD --> ongoing learning point
> Todo: Set up swagger documentation

## Feedback (For CF's)
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]

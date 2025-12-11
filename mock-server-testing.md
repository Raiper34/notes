```ts
import {HttpClient} from '@angular/common/http';
import {HttpClientTestingModule, HttpTestingController} from '@angular/common/http/testing';
import {fakeAsync, flush, TestBed} from '@angular/core/testing';

describe('', () => {

  let httpMock: HttpTestingController;
  let http: HttpClient;
  // testing service should be here

  beforeEach(() => {
    TestBed.configureTestingModule({
      providers: [
       ...
      imports: [HttpClientTestingModule]
    });
    httpMock = TestBed.inject(HttpTestingController);
    http = TestBed.inject(HttpClient);
  });

  it('should next value to $loading in loading service', fakeAsync(() => {
    http.get('/random').pipe().subscribe();
    // calling service with subscribe
    httpMock.expectOne('/random');
    flush();
  }));


});

```

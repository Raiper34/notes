How to upload/download in Angular
```ts
const blob = new Blob(['File content'], {type: 'text/plain'});
const formData = new FormData();
formData.append('file', blob, 'file.txt');
this.http.post('/upload', formData, {responseType: 'blob'}).pipe(tap(data => saveAs(data, 'test.txt'))).subscribe();
```

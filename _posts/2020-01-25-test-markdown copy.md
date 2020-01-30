---
layout: post
title: Yeni Post
subtitle: Each post also has a subtitle
gh-repo: musahinist/musahinist.github.io
gh-badge: [star, fork, follow]
tags: [test]
comments: true
---

You can write regular [markdown](http://markdowntutorial.com/) here and Jekyll will automatically convert it to a nice webpage.  I strongly encourage you to [take 5 minutes to learn how to write in markdown](http://markdowntutorial.com/) - it'll teach you how to transform regular text into bold/italics/headings/tables/etc.

**Here is some bold text**

## Here is a secondary heading

````typescript
import { Model } from 'mongoose';
import { Injectable } from '@nestjs/common';

import { InjectModel } from '@nestjs/mongoose';

import { ITeacher } from './interface/teacher.interface';
import { CreateTeacherDto } from './dto/create-teacher.dto';

@Injectable()
export class TeachersService {

    constructor(@InjectModel('Teacher') private readonly teacherModel: Model<ITeacher>) { }

    async findAll(): Promise<ITeacher[]> {
        return await this.teacherModel.find().exec();
    }

    async findOne(options: object): Promise<ITeacher> {
        return await this.teacherModel.findOne(options).exec();
    }

    async findById(id: string): Promise<ITeacher> {
        return await this.teacherModel.findById(id).exec();
    }
    async create(createTeacher: CreateTeacherDto): Promise<ITeacher> {
        const newTeacher = new this.teacherModel(createTeacher);
        return await newTeacher.save();
    }
    async update(id: string, updateTeacher: CreateTeacherDto): Promise<ITeacher> {
        return await this.teacherModel.findByIdAndUpdate(id, updateTeacher, { new: true });
    }
    async delete(id: string): Promise<ITeacher> {
        return await this.teacherModel.findByIdAndRemove(id);
    }
}
````

Here's a useless table:

| Number | Next number | Previous number |
| :----- | :---------- | :-------------- |
| Five   | Six         | Four            |
| Ten    | Eleven      | Nine            |
| Seven  | Eight       | Six             |
| Two    | Three       | One             |


How about a yummy crepe?

![Crepe](https://s3-media3.fl.yelpcdn.com/bphoto/cQ1Yoa75m2yUFFbY2xwuqw/348s.jpg)

It can also be centered!

![Crepe](https://s3-media3.fl.yelpcdn.com/bphoto/cQ1Yoa75m2yUFFbY2xwuqw/348s.jpg){: .center-block :}

Here's a code chunk:
`asdasdsdd`
~~~
var foo = function(x) {
  return(x + 5);
}
foo(3)
~~~

And here is the same code with syntax highlighting:

```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
```

And here is the same code yet again but with line numbers:

{% highlight typescript linenos=table %}
import { Model } from 'mongoose';
import { Injectable } from '@nestjs/common';

import { InjectModel } from '@nestjs/mongoose';

import { ITeacher } from './interface/teacher.interface';
import { CreateTeacherDto } from './dto/create-teacher.dto';

@Injectable()
export class TeachersService {

    constructor(@InjectModel('Teacher') private readonly teacherModel: Model<ITeacher>) { }

    async findAll(): Promise<ITeacher[]> {
        return await this.teacherModel.find().exec();
    }

    async findOne(options: object): Promise<ITeacher> {
        return await this.teacherModel.findOne(options).exec();
    }

    async findById(id: string): Promise<ITeacher> {
        return await this.teacherModel.findById(id).exec();
    }
    async create(createTeacher: CreateTeacherDto): Promise<ITeacher> {
        const newTeacher = new this.teacherModel(createTeacher);
        return await newTeacher.save();
    }
    async update(id: string, updateTeacher: CreateTeacherDto): Promise<ITeacher> {
        return await this.teacherModel.findByIdAndUpdate(id, updateTeacher, { new: true });
    }
    async delete(id: string): Promise<ITeacher> {
        return await this.teacherModel.findByIdAndRemove(id);
    }
}
{% endhighlight %}

## Boxes
You can add notification, warning and error boxes like this:

### Notification

{: .box-note}
**Note:** This is a notification box.

### Warning

{: .box-warning}
**Warning:** This is a warning box.

### Error

{: .box-error}
**Error:** This is an error box.


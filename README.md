<div align="center">

## CString to Char Conversion


</div>

### Description

This little bit of code is simply a method of converting "CString"'s into "char"'s. I am posting this because I was having some trouble finding any code that did this type of conversion, or at least I didn't find a method that suited my needs. Regardless, I thought I'd post this for those who may need a quick and (somewhat) easy way to convert CStrings into Chars. This code is admittedly simplistic, so don't expect anything advanced here! I have added comments for each step, despite its simplicity.
 
### More Info
 
This header file takes in a CString that you can easily provide.

This code was intended for use with MFC, and I have not really tried it outside of MFC, so if you have any experiences with this code as such, please make a comment on this code about them.

When complete, this function will return a pointer to a character array on the heap with the same contents as the CString that was passed into it.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Phillip Hopkins](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/phillip-hopkins.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+
**Category**       |[Strings](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/strings__3-26.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/phillip-hopkins-cstring-to-char-conversion__3-5470/archive/master.zip)

### API Declarations

afx.h


### Source Code

```
//Takes in a CString, creates a char on the heap, and individually
//assigns each character to its respective array char, then returns
//a pointer to that array.
char * GetCharForm(CString myCString)
{
	//declare a pointer to an array of chars on the heap,
	//one for each character in the CString, plus and extra
	//one for the null terminator.
	char *tmpstring = new char[myCString.GetLength() + 1];
	//declare "i", which will be used for iterations,
	//and "m", which we set equal to the length of the
	//CString.
	int i, m=myCString.GetLength();
	//start the character-by-character loop
	for (i=0; i < m; i++)
	{
		//set this char in the array to its
		//respective character in the CString.
		tmpstring[i]=myCString.GetAt(i);
	}
	//Add in the null terminator at the end
	tmpstring[m+1]='\n';
	//return with our newly converted string!
	return tmpstring;
}
```


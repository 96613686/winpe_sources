# UnBCL::Path::GetLongName(UnBCL::String const *)

- ea: `0x1800498a0`
- end: `0x180049a47`
- name: `?GetLongName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z`
- size: `423`
- prototype: `struct UnBCL::String *__fastcall(const struct UnBCL::String *)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18002bf00`
- `0x18002c310`
- `0x18002cd20`
- `0x18002d0e0`

## callees

- `0x18000225c`
- `0x1800098f0`
- `0x180009e7c`
- `0x1800477d0`
- `0x180048d38`
- `0x1800498a0`
- `0x18004aa18`
- `0x18004aea4`
- `0x18005b790`
- `0x1800641a0`
- `0x180064340`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180049908`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180049942`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180049a1b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180049908`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180049942`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180049a1b`
- `KERNEL32!GetLastError` at `0x1800499fe`
- `KERNEL32!GetLastError` at `0x1800499fe`

## string_xrefs

- `0x18004997c`: `class UnBCL::String *__cdecl UnBCL::Path::GetLongName(const class UnBCL::String *)`
- `0x1800499c3`: `class UnBCL::String *__cdecl UnBCL::Path::GetLongName(const class UnBCL::String *)`
- `0x180049a21`: `class UnBCL::String *__cdecl UnBCL::Path::GetLongName(const class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct UnBCL::String *__fastcall UnBCL::Path::GetLongName(const unsigned __int16 **a1)
{
  unsigned __int16 *v2; // rax
  unsigned __int16 *v3; // rdi
  unsigned __int16 *Path; // rbx
  unsigned __int16 *v5; // rax
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rdi
  UnBCL::ArgumentException *v9; // rax
  UnBCL::ArgumentException *v10; // rbx
  const struct UnBCL::String *v11; // rax
  UnBCL::Win32Exception *v12; // rax
  UnBCL::Win32Exception *v13; // rbx
  DWORD LastError; // eax
  __int64 v15; // rbx
  __int64 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v17; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v18[5]; // [rsp+30h] [rbp-28h] BYREF
  UnBCL::Win32Exception *v19; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *v20; // [rsp+68h] [rbp+10h]

  v18[1] = -2;
  if ( !a1 )
  {
    v9 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v10 = v9;
    v19 = v9;
    if ( v9 )
    {
      v11 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_16_();
      v9 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(v10, v11);
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v9,
                         "class UnBCL::String *__cdecl UnBCL::Path::GetLongName(const class UnBCL::String *)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  v2 = pSanitizePath(a1[2]);
  v3 = v2;
  v20 = v2;
  if ( !v2 )
  {
    v12 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v19 = v12;
    if ( v12 )
      v12 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v12, 3u, (const struct UnBCL::String *)a1);
    v17 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v12,
            "class UnBCL::String *__cdecl UnBCL::Path::GetLongName(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&v17;
  }
  LODWORD(v19) = 0;
  try
  {
    Path = pGetPath(v2, 1, (int *)&v19);
    v18[2] = Path;
  }
  catch ( ... )
  {
    operator delete[](v20);
    throw;
  }
  if ( !Path )
  {
    v13 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v19 = v13;
    if ( v13 )
    {
      LastError = GetLastError();
      v15 = UnBCL::Win32Exception::Win32Exception(v13, LastError, v3);
    }
    else
    {
      v15 = 0;
    }
    operator delete[](v3);
    v18[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
               v15,
               "class UnBCL::String *__cdecl UnBCL::Path::GetLongName(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)v18;
  }
  operator delete[](v3);
  v5 = (unsigned __int16 *)UnBCL::Object::operator new(0x18u);
  v20 = v5;
  if ( v5 )
  {
    v6 = Path + 4;
    if ( !(_DWORD)v19 )
      v6 = Path;
    v7 = UnBCL::String::String((UnBCL::String *)v5, v6);
  }
  else
  {
    v7 = 0;
  }
  operator delete[](Path);
  return (struct UnBCL::String *)v7;
}

```

## disassembly

```asm
0x1800498a0  push    rdi
0x1800498a2  sub     rsp, 50h
0x1800498a6  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x1800498af  mov     [rsp+58h+arg_10], rbx
0x1800498b4  mov     rbx, rcx
0x1800498b7  test    rcx, rcx
0x1800498ba  jz      loc_180049956
0x1800498c0  mov     rcx, [rcx+10h]; unsigned __int16 *
0x1800498c4  call    ?pSanitizePath@@YAPEAGPEBG@Z; pSanitizePath(ushort const *)
0x1800498c9  mov     rdi, rax
0x1800498cc  mov     [rsp+58h+arg_8], rax
0x1800498d1  test    rax, rax
0x1800498d4  jz      loc_1800499A2
0x1800498da  mov     dword ptr [rsp+58h+arg_0], 0
0x1800498e2  lea     r8, [rsp+58h+arg_0]; int *
0x1800498e7  mov     edx, 1; int
0x1800498ec  mov     rcx, rdi; unsigned __int16 *
0x1800498ef  call    ?pGetPath@@YAPEAGPEBGHPEAH@Z; pGetPath(ushort const *,int,int *)
0x1800498f4  mov     rbx, rax
0x1800498f7  mov     [rsp+58h+var_18], rax
0x1800498fc  test    rbx, rbx
0x1800498ff  jz      loc_1800499E9
0x180049905  mov     rcx, rdi
0x180049908  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18004990e  mov     ecx, 18h; unsigned __int64
0x180049913  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180049918  mov     [rsp+58h+arg_8], rax
0x18004991d  test    rax, rax
0x180049920  jz      short loc_18004993D
0x180049922  cmp     dword ptr [rsp+58h+arg_0], 0
0x180049927  lea     rdx, [rbx+8]
0x18004992b  jnz     short loc_180049930
0x18004992d  mov     rdx, rbx; unsigned __int16 *
0x180049930  mov     rcx, rax; this
0x180049933  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180049938  mov     rdi, rax
0x18004993b  jmp     short loc_18004993F
0x18004993d  xor     edi, edi
0x18004993f  mov     rcx, rbx
0x180049942  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180049948  mov     rax, rdi
0x18004994b  mov     rbx, [rsp+58h+arg_10]
0x180049950  add     rsp, 50h
0x180049954  pop     rdi
0x180049955  retn
0x180049956  lea     ecx, [rbx+38h]; unsigned __int64
0x180049959  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004995e  mov     rbx, rax
0x180049961  mov     [rsp+58h+arg_0], rax
0x180049966  test    rax, rax
0x180049969  jz      short loc_18004997C
0x18004996b  call    UnBCL_____StringLiteral_16_
0x180049970  mov     rdx, rax; struct UnBCL::String *
0x180049973  mov     rcx, rbx; this
0x180049976  call    ??0ArgumentException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::ArgumentException::ArgumentException(UnBCL::String const *)
0x18004997b  nop
0x18004997c  lea     rdx, aClassUnbclStri_34; "class UnBCL::String *__cdecl UnBCL::Pat"...
0x180049983  mov     rcx, rax
0x180049986  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004998b  mov     [rsp+58h+pExceptionObject], rax
0x180049990  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180049997  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18004999c  call    _CxxThrowException_0
0x1800499a2  lea     ecx, [rax+40h]; unsigned __int64
0x1800499a5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800499aa  mov     [rsp+58h+arg_0], rax
0x1800499af  test    rax, rax
0x1800499b2  jz      short loc_1800499C3
0x1800499b4  mov     r8, rbx; struct UnBCL::String *
0x1800499b7  lea     edx, [rdi+3]; dwMessageId
0x1800499ba  mov     rcx, rax; this
0x1800499bd  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x1800499c2  nop
0x1800499c3  lea     rdx, aClassUnbclStri_34; "class UnBCL::String *__cdecl UnBCL::Pat"...
0x1800499ca  mov     rcx, rax
0x1800499cd  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800499d2  mov     [rsp+58h+var_30], rax
0x1800499d7  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x1800499de  lea     rcx, [rsp+58h+var_30]; pExceptionObject
0x1800499e3  call    _CxxThrowException_0
0x1800499e9  lea     ecx, [rbx+40h]; unsigned __int64
0x1800499ec  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800499f1  mov     rbx, rax
0x1800499f4  mov     [rsp+58h+arg_0], rax
0x1800499f9  test    rax, rax
0x1800499fc  jz      short loc_180049A16
0x1800499fe  call    cs:__imp_GetLastError
0x180049a04  mov     r8, rdi; unsigned __int16 *
0x180049a07  mov     edx, eax; dwMessageId
0x180049a09  mov     rcx, rbx; this
0x180049a0c  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x180049a11  mov     rbx, rax
0x180049a14  jmp     short loc_180049A18
0x180049a16  xor     ebx, ebx
0x180049a18  mov     rcx, rdi
0x180049a1b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180049a21  lea     rdx, aClassUnbclStri_34; "class UnBCL::String *__cdecl UnBCL::Pat"...
0x180049a28  mov     rcx, rbx
0x180049a2b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180049a30  mov     [rsp+58h+var_28], rax
0x180049a35  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x180049a3c  lea     rcx, [rsp+58h+var_28]; pExceptionObject
0x180049a41  call    _CxxThrowException_0
```

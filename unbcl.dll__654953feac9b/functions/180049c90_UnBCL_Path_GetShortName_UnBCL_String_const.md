# UnBCL::Path::GetShortName(UnBCL::String const *)

- ea: `0x180049c90`
- end: `0x180049e3a`
- name: `?GetShortName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z`
- size: `426`
- prototype: `struct UnBCL::String *__fastcall(const struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x18000225c`
- `0x1800098f0`
- `0x180009e7c`
- `0x18001a700`
- `0x1800477d0`
- `0x180048ee8`
- `0x180049c90`
- `0x18004aa18`
- `0x18004aea4`
- `0x18005b790`
- `0x1800641a0`
- `0x180064340`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180049cf1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180049d34`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180049cf1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180049d34`
- `KERNEL32!GetLastError` at `0x180049e00`
- `KERNEL32!GetLastError` at `0x180049e00`

## string_xrefs

- `0x180049d73`: `class UnBCL::String *__cdecl UnBCL::Path::GetShortName(const class UnBCL::String *)`
- `0x180049dba`: `class UnBCL::String *__cdecl UnBCL::Path::GetShortName(const class UnBCL::String *)`
- `0x180049e14`: `class UnBCL::String *__cdecl UnBCL::Path::GetShortName(const class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct UnBCL::String *__fastcall UnBCL::Path::GetShortName(const unsigned __int16 **a1)
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
  UnBCL::Win32Exception *v13; // rax
  UnBCL::Win32Exception *v14; // rdi
  const unsigned __int16 *InnerList; // rbx
  DWORD LastError; // eax
  __int64 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v18; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v19[5]; // [rsp+30h] [rbp-28h] BYREF
  UnBCL::Win32Exception *v20; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *v21; // [rsp+68h] [rbp+10h]

  v19[1] = -2;
  if ( !a1 )
  {
    v9 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v10 = v9;
    v20 = v9;
    if ( v9 )
    {
      v11 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_15_();
      v9 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(v10, v11);
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v9,
                         "class UnBCL::String *__cdecl UnBCL::Path::GetShortName(const class UnBCL::String *)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  v2 = pSanitizePath(a1[2]);
  v3 = v2;
  v21 = v2;
  if ( !v2 )
  {
    v12 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v20 = v12;
    if ( v12 )
      v12 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v12, 3u, (const struct UnBCL::String *)a1);
    v18 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v12,
            "class UnBCL::String *__cdecl UnBCL::Path::GetShortName(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&v18;
  }
  LODWORD(v20) = 0;
  try
  {
    Path = pGetPath(v2, 0, (int *)&v20);
    v19[2] = Path;
  }
  catch ( ... )
  {
    operator delete[](v21);
    throw;
  }
  operator delete[](v3);
  if ( !Path )
  {
    v13 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v14 = v13;
    v20 = v13;
    if ( v13 )
    {
      InnerList = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(a1);
      LastError = GetLastError();
      v13 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v14, LastError, InnerList);
    }
    v19[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
               v13,
               "class UnBCL::String *__cdecl UnBCL::Path::GetShortName(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)v19;
  }
  v5 = (unsigned __int16 *)UnBCL::Object::operator new(0x18u);
  v21 = v5;
  if ( v5 )
  {
    v6 = Path + 4;
    if ( !(_DWORD)v20 )
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
0x180049c90  push    rdi
0x180049c92  sub     rsp, 50h
0x180049c96  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x180049c9f  mov     [rsp+58h+arg_10], rbx
0x180049ca4  mov     [rsp+58h+arg_18], rsi
0x180049ca9  mov     rsi, rcx
0x180049cac  test    rcx, rcx
0x180049caf  jz      loc_180049D4D
0x180049cb5  mov     rcx, [rcx+10h]; unsigned __int16 *
0x180049cb9  call    ?pSanitizePath@@YAPEAGPEBG@Z; pSanitizePath(ushort const *)
0x180049cbe  mov     rdi, rax
0x180049cc1  mov     [rsp+58h+arg_8], rax
0x180049cc6  test    rax, rax
0x180049cc9  jz      loc_180049D99
0x180049ccf  mov     dword ptr [rsp+58h+arg_0], 0
0x180049cd7  lea     r8, [rsp+58h+arg_0]; int *
0x180049cdc  xor     edx, edx; int
0x180049cde  mov     rcx, rdi; unsigned __int16 *
0x180049ce1  call    ?pGetPath@@YAPEAGPEBGHPEAH@Z; pGetPath(ushort const *,int,int *)
0x180049ce6  mov     rbx, rax
0x180049ce9  mov     [rsp+58h+var_18], rax
0x180049cee  mov     rcx, rdi
0x180049cf1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180049cf7  test    rbx, rbx
0x180049cfa  jz      loc_180049DE0
0x180049d00  mov     ecx, 18h; unsigned __int64
0x180049d05  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180049d0a  mov     [rsp+58h+arg_8], rax
0x180049d0f  test    rax, rax
0x180049d12  jz      short loc_180049D2F
0x180049d14  cmp     dword ptr [rsp+58h+arg_0], 0
0x180049d19  lea     rdx, [rbx+8]
0x180049d1d  jnz     short loc_180049D22
0x180049d1f  mov     rdx, rbx; unsigned __int16 *
0x180049d22  mov     rcx, rax; this
0x180049d25  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180049d2a  mov     rdi, rax
0x180049d2d  jmp     short loc_180049D31
0x180049d2f  xor     edi, edi
0x180049d31  mov     rcx, rbx
0x180049d34  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180049d3a  mov     rax, rdi
0x180049d3d  mov     rbx, [rsp+58h+arg_10]
0x180049d42  mov     rsi, [rsp+58h+arg_18]
0x180049d47  add     rsp, 50h
0x180049d4b  pop     rdi
0x180049d4c  retn
0x180049d4d  lea     ecx, [rsi+38h]; unsigned __int64
0x180049d50  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180049d55  mov     rbx, rax
0x180049d58  mov     [rsp+58h+arg_0], rax
0x180049d5d  test    rax, rax
0x180049d60  jz      short loc_180049D73
0x180049d62  call    UnBCL_____StringLiteral_15_
0x180049d67  mov     rdx, rax; struct UnBCL::String *
0x180049d6a  mov     rcx, rbx; this
0x180049d6d  call    ??0ArgumentException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::ArgumentException::ArgumentException(UnBCL::String const *)
0x180049d72  nop
0x180049d73  lea     rdx, aClassUnbclStri_19; "class UnBCL::String *__cdecl UnBCL::Pat"...
0x180049d7a  mov     rcx, rax
0x180049d7d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180049d82  mov     [rsp+58h+pExceptionObject], rax
0x180049d87  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180049d8e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180049d93  call    _CxxThrowException_0
0x180049d99  lea     ecx, [rax+40h]; unsigned __int64
0x180049d9c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180049da1  mov     [rsp+58h+arg_0], rax
0x180049da6  test    rax, rax
0x180049da9  jz      short loc_180049DBA
0x180049dab  mov     r8, rsi; struct UnBCL::String *
0x180049dae  lea     edx, [rdi+3]; dwMessageId
0x180049db1  mov     rcx, rax; this
0x180049db4  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x180049db9  nop
0x180049dba  lea     rdx, aClassUnbclStri_19; "class UnBCL::String *__cdecl UnBCL::Pat"...
0x180049dc1  mov     rcx, rax
0x180049dc4  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180049dc9  mov     [rsp+58h+var_30], rax
0x180049dce  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x180049dd5  lea     rcx, [rsp+58h+var_30]; pExceptionObject
0x180049dda  call    _CxxThrowException_0
0x180049de0  lea     ecx, [rbx+40h]; unsigned __int64
0x180049de3  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180049de8  mov     rdi, rax
0x180049deb  mov     [rsp+58h+arg_0], rax
0x180049df0  test    rax, rax
0x180049df3  jz      short loc_180049E14
0x180049df5  mov     rcx, rsi
0x180049df8  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x180049dfd  mov     rbx, rax
0x180049e00  call    cs:__imp_GetLastError
0x180049e06  mov     r8, rbx; unsigned __int16 *
0x180049e09  mov     edx, eax; dwMessageId
0x180049e0b  mov     rcx, rdi; this
0x180049e0e  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x180049e13  nop
0x180049e14  lea     rdx, aClassUnbclStri_19; "class UnBCL::String *__cdecl UnBCL::Pat"...
0x180049e1b  mov     rcx, rax
0x180049e1e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180049e23  mov     [rsp+58h+var_28], rax
0x180049e28  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x180049e2f  lea     rcx, [rsp+58h+var_28]; pExceptionObject
0x180049e34  call    _CxxThrowException_0
```

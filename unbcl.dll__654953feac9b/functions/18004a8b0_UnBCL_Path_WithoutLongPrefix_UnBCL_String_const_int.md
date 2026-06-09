# UnBCL::Path::WithoutLongPrefix(UnBCL::String const *,int &)

- ea: `0x18004a8b0`
- end: `0x18004aa12`
- name: `?WithoutLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@AEAH@Z`
- size: `354`
- prototype: `struct UnBCL::String *__fastcall(const struct UnBCL::String *, int *)`
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180029280`
- `0x18003b740`
- `0x180049500`
- `0x180049ae0`
- `0x18004a880`

## callees

- `0x18000225c`
- `0x180002f90`
- `0x1800099f0`
- `0x180009e7c`
- `0x180011570`
- `0x1800477d0`
- `0x180048ca8`
- `0x18004a8b0`
- `0x18005b650`
- `0x18005be50`
- `0x18005dc40`
- `0x18005de90`

## import_xrefs

- `msvcrt!iswalpha` at `0x18004a962`
- `msvcrt!iswalpha` at `0x18004a962`

## string_xrefs

- `0x18004a9ec`: `class UnBCL::String *__cdecl UnBCL::Path::WithoutLongPrefix(const class UnBCL::String *,int &)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct UnBCL::String *__fastcall UnBCL::Path::WithoutLongPrefix(const struct UnBCL::String *a1, int *a2)
{
  struct UnBCL::String *v4; // rax
  struct UnBCL::String *v5; // rbx
  struct UnBCL::String *result; // rax
  UnBCL::ArgumentNullException *v7; // rax
  __int64 v8; // rcx
  UnBCL::ArgumentNullException *v9; // rbx
  const struct UnBCL::String *v10; // rax
  _QWORD v11[4]; // [rsp+28h] [rbp-20h] BYREF
  struct UnBCL::String *pExceptionObject; // [rsp+50h] [rbp+8h] BYREF
  UnBCL::ArgumentNullException *v13; // [rsp+60h] [rbp+18h]

  if ( !a1 )
  {
    v7 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v9 = v7;
    v13 = v7;
    if ( v7 )
    {
      v10 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_9__0(v8);
      v7 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(v9, v10);
    }
    pExceptionObject = (struct UnBCL::String *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                 v7,
                                                 "class UnBCL::String *__cdecl UnBCL::Path::WithoutLongPrefix(const class"
                                                 " UnBCL::String *,int &)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( (unsigned int)UnBCL::String::StartsWith(a1, L"\\\\?\\UNC\\", 1) )
  {
    *a2 = 8;
    v4 = UnBCL::String::Substring(a1, 8, *(_DWORD *)(*((_QWORD *)a1 + 2) - 16LL) - 8);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v11, v4);
    v5 = UnBCL::String::Concat(L"\\\\", *(const unsigned __int16 **)(v11[1] + 16LL));
    v11[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v11);
    return v5;
  }
  else if ( (unsigned int)UnBCL::String::StartsWith(a1, L"\\\\?\\", 1)
         && iswalpha(*(_WORD *)(*((_QWORD *)a1 + 2) + 8LL))
         && *(_WORD *)(*((_QWORD *)a1 + 2) + 10LL) == 58 )
  {
    *a2 = 4;
    return UnBCL::String::Substring(a1, 4, *(_DWORD *)(*((_QWORD *)a1 + 2) - 16LL) - 4);
  }
  else
  {
    *a2 = 0;
    result = (struct UnBCL::String *)UnBCL::Object::operator new(0x18u);
    pExceptionObject = result;
    if ( result )
      return (struct UnBCL::String *)UnBCL::String::String(result, a1);
  }
  return result;
}

```

## disassembly

```asm
0x18004a8b0  push    rdi
0x18004a8b2  sub     rsp, 40h
0x18004a8b6  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18004a8bf  mov     [rsp+48h+arg_8], rbx
0x18004a8c4  mov     rdi, rdx
0x18004a8c7  mov     rbx, rcx
0x18004a8ca  test    rcx, rcx
0x18004a8cd  jz      loc_18004A9C4
0x18004a8d3  mov     r8d, 1; int
0x18004a8d9  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x18004a8e0  call    ?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x18004a8e5  mov     rcx, rbx; this
0x18004a8e8  test    eax, eax
0x18004a8ea  jz      short loc_18004A944
0x18004a8ec  mov     edx, 8; int
0x18004a8f1  mov     [rdi], edx
0x18004a8f3  mov     rax, [rbx+10h]
0x18004a8f7  mov     r8d, [rax-10h]
0x18004a8fb  sub     r8d, edx; int
0x18004a8fe  call    ?Substring@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Substring(int,int)
0x18004a903  mov     rdx, rax
0x18004a906  lea     rcx, [rsp+48h+var_20]
0x18004a90b  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18004a910  nop
0x18004a911  mov     rdx, [rsp+48h+var_18]
0x18004a916  mov     rdx, [rdx+10h]; unsigned __int16 *
0x18004a91a  lea     rcx, asc_18008970C; "\\\\"
0x18004a921  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x18004a926  mov     rbx, rax
0x18004a929  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18004a930  mov     [rsp+48h+var_20], rax
0x18004a935  lea     rcx, [rsp+48h+var_20]
0x18004a93a  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004a93f  mov     rax, rbx
0x18004a942  jmp     short loc_18004A9B9
0x18004a944  mov     r8d, 1; int
0x18004a94a  lea     rdx, asc_1800895A0; "\\\\?\\"
0x18004a951  call    ?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x18004a956  test    eax, eax
0x18004a958  jz      short loc_18004A993
0x18004a95a  mov     rcx, [rbx+10h]
0x18004a95e  movzx   ecx, word ptr [rcx+8]; C
0x18004a962  call    cs:__imp_iswalpha
0x18004a968  test    eax, eax
0x18004a96a  jz      short loc_18004A993
0x18004a96c  mov     rax, [rbx+10h]
0x18004a970  cmp     word ptr [rax+0Ah], 3Ah ; ':'
0x18004a975  jnz     short loc_18004A993
0x18004a977  mov     edx, 4; int
0x18004a97c  mov     [rdi], edx
0x18004a97e  mov     rax, [rbx+10h]
0x18004a982  mov     r8d, [rax-10h]
0x18004a986  sub     r8d, edx; int
0x18004a989  mov     rcx, rbx; this
0x18004a98c  call    ?Substring@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Substring(int,int)
0x18004a991  jmp     short loc_18004A9B9
0x18004a993  mov     dword ptr [rdi], 0
0x18004a999  mov     ecx, 18h; unsigned __int64
0x18004a99e  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004a9a3  mov     [rsp+48h+pExceptionObject], rax
0x18004a9a8  test    rax, rax
0x18004a9ab  jz      short loc_18004A9B9
0x18004a9ad  mov     rdx, rbx; struct UnBCL::String *
0x18004a9b0  mov     rcx, rax; this
0x18004a9b3  call    ??0String@UnBCL@@QEAA@PEBV01@@Z; UnBCL::String::String(UnBCL::String const *)
0x18004a9b8  nop
0x18004a9b9  mov     rbx, [rsp+48h+arg_8]
0x18004a9be  add     rsp, 40h
0x18004a9c2  pop     rdi
0x18004a9c3  retn
0x18004a9c4  mov     ecx, 38h ; '8'; unsigned __int64
0x18004a9c9  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004a9ce  mov     rbx, rax
0x18004a9d1  mov     [rsp+48h+arg_10], rax
0x18004a9d6  test    rax, rax
0x18004a9d9  jz      short loc_18004A9EC
0x18004a9db  call    UnBCL_____StringLiteral_9__0
0x18004a9e0  mov     rdx, rax; struct UnBCL::String *
0x18004a9e3  mov     rcx, rbx; this
0x18004a9e6  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::ArgumentNullException::ArgumentNullException(UnBCL::String const *)
0x18004a9eb  nop
0x18004a9ec  lea     rdx, aClassUnbclStri_7; "class UnBCL::String *__cdecl UnBCL::Pat"...
0x18004a9f3  mov     rcx, rax
0x18004a9f6  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004a9fb  mov     [rsp+48h+pExceptionObject], rax
0x18004aa00  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18004aa07  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18004aa0c  call    _CxxThrowException_0
```

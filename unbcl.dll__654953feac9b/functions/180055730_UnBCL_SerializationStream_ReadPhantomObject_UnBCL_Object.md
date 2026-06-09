# UnBCL::SerializationStream::ReadPhantomObject(UnBCL::Object * &)

- ea: `0x180055730`
- end: `0x1800558b8`
- name: `?ReadPhantomObject@SerializationStream@UnBCL@@QEAAXAEAPEAVObject@2@@Z`
- size: `392`
- prototype: `void __fastcall(UnBCL::SerializationStream *__hidden this, struct UnBCL::Object **)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x18003f560`
- `0x1800477d0`
- `0x18004ffe0`
- `0x180050058`
- `0x180050538`
- `0x180050580`
- `0x1800505c8`
- `0x180051d10`
- `0x180055150`
- `0x180055730`

## string_xrefs

- `0x1800557f8`: `void __cdecl UnBCL::SerializationStream::ReadPhantomObject(class UnBCL::Object *&)`
- `0x180055847`: `void __cdecl UnBCL::SerializationStream::ReadPhantomObject(class UnBCL::Object *&)`
- `0x180055894`: `void __cdecl UnBCL::SerializationStream::ReadPhantomObject(class UnBCL::Object *&)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UnBCL::SerializationStream::ReadPhantomObject(
        UnBCL::SerializationStream *this,
        struct UnBCL::Object **a2)
{
  struct UnBCL::Object *v4; // rbx
  struct UnBCL::ISerializable *Object; // rax
  __int64 v6; // rcx
  UnBCL::SerializationException *v7; // rdi
  const struct UnBCL::String *v8; // rax
  __int64 v9; // rcx
  UnBCL::InvalidOperationException *v10; // rdi
  __int64 v11; // rbx
  const struct UnBCL::String *v12; // rax
  __int64 v13; // rcx
  UnBCL::SerializationException *v14; // rdi
  const struct UnBCL::String *v15; // rax
  char v16; // [rsp+50h] [rbp+20h] BYREF
  struct UnBCL::Object *pExceptionObject; // [rsp+60h] [rbp+30h] BYREF
  UnBCL::InvalidOperationException *v18; // [rsp+68h] [rbp+38h]

  if ( *((_DWORD *)this + 8) != 1 )
  {
    v10 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v18 = v10;
    v11 = 0;
    if ( v10 )
    {
      v12 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_19_(v9);
      v11 = UnBCL::InvalidOperationException::InvalidOperationException(v10, v12);
    }
    pExceptionObject = (struct UnBCL::Object *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                 v11,
                                                 "void __cdecl UnBCL::SerializationStream::ReadPhantomObject(class UnBCL::Object *&)");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  v4 = 0;
  v16 = 0;
  UnBCL::SerializationStream::ReadPrimitive<unsigned char>(this, &v16);
  if ( v16 != 80 )
  {
    v14 = (UnBCL::SerializationException *)UnBCL::Object::operator new(0x38u);
    v18 = v14;
    if ( v14 )
    {
      v15 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_20_(v13);
      v4 = (struct UnBCL::Object *)UnBCL::SerializationException::SerializationException(v14, v15);
    }
    pExceptionObject = (struct UnBCL::Object *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                 v4,
                                                 "void __cdecl UnBCL::SerializationStream::ReadPhantomObject(class UnBCL::Object *&)");
    throw (UnBCL::SerializationException **)&pExceptionObject;
  }
  UnBCL::SerializationStream::ReadPrimitive<unsigned char>(this, &v16);
  if ( v16 == 83 )
  {
    pExceptionObject = 0;
    UnBCL::SerializationStream::operator>>(this);
    *a2 = pExceptionObject;
  }
  else
  {
    if ( v16 != 88 )
    {
      v7 = (UnBCL::SerializationException *)UnBCL::Object::operator new(0x38u);
      v18 = v7;
      if ( v7 )
      {
        v8 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_21_(v6);
        v4 = (struct UnBCL::Object *)UnBCL::SerializationException::SerializationException(v7, v8);
      }
      pExceptionObject = (struct UnBCL::Object *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                   v4,
                                                   "void __cdecl UnBCL::SerializationStream::ReadPhantomObject(class UnBCL::Object *&)");
      throw (UnBCL::SerializationException **)&pExceptionObject;
    }
    Object = UnBCL::SerializationStream::ReadObject(this);
    if ( Object )
      v4 = (struct UnBCL::ISerializable *)((char *)Object + *(int *)(*((_QWORD *)Object + 1) + 4LL) + 8);
    *a2 = v4;
  }
}

```

## disassembly

```asm
0x180055730  push    rbp
0x180055732  push    rsi
0x180055733  push    rdi
0x180055734  mov     rbp, rsp
0x180055737  sub     rsp, 30h
0x18005573b  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180055743  mov     [rsp+30h+arg_8], rbx
0x180055748  mov     rsi, rdx
0x18005574b  mov     rdi, rcx
0x18005574e  cmp     dword ptr [rcx+20h], 1
0x180055752  jnz     loc_18005581C
0x180055758  xor     ebx, ebx
0x18005575a  mov     [rbp+arg_0], bl
0x18005575d  lea     rdx, [rbp+arg_0]
0x180055761  call    ??$ReadPrimitive@E@SerializationStream@UnBCL@@IEAAAEAV01@AEAE@Z; UnBCL::SerializationStream::ReadPrimitive<uchar>(uchar &)
0x180055766  cmp     [rbp+arg_0], 50h ; 'P'
0x18005576a  jnz     loc_18005586B
0x180055770  lea     rdx, [rbp+arg_0]
0x180055774  mov     rcx, rdi
0x180055777  call    ??$ReadPrimitive@E@SerializationStream@UnBCL@@IEAAAEAV01@AEAE@Z; UnBCL::SerializationStream::ReadPrimitive<uchar>(uchar &)
0x18005577c  mov     al, [rbp+arg_0]
0x18005577f  cmp     al, 53h ; 'S'
0x180055781  jz      short loc_1800557AB
0x180055783  cmp     al, 58h ; 'X'
0x180055785  jnz     short loc_1800557CF
0x180055787  mov     rcx, rdi; this
0x18005578a  call    ?ReadObject@SerializationStream@UnBCL@@IEAAPEAUISerializable@2@XZ; UnBCL::SerializationStream::ReadObject(void)
0x18005578f  mov     rdx, rax
0x180055792  test    rax, rax
0x180055795  jz      short loc_1800557A6
0x180055797  mov     rax, [rax+8]
0x18005579b  movsxd  rbx, dword ptr [rax+4]
0x18005579f  add     rbx, 8
0x1800557a3  add     rbx, rdx
0x1800557a6  mov     [rsi], rbx
0x1800557a9  jmp     short loc_1800557C2
0x1800557ab  mov     [rbp+pExceptionObject], rbx
0x1800557af  lea     rdx, [rbp+pExceptionObject]
0x1800557b3  mov     rcx, rdi
0x1800557b6  call    ??5SerializationStream@UnBCL@@QEAAAEAV01@AEAPEAVString@1@@Z; UnBCL::SerializationStream::operator>>(UnBCL::String * &)
0x1800557bb  mov     rax, [rbp+pExceptionObject]
0x1800557bf  mov     [rsi], rax
0x1800557c2  mov     rbx, [rsp+30h+arg_8]
0x1800557c7  add     rsp, 30h
0x1800557cb  pop     rdi
0x1800557cc  pop     rsi
0x1800557cd  pop     rbp
0x1800557ce  retn
0x1800557cf  mov     ecx, 38h ; '8'; unsigned __int64
0x1800557d4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800557d9  mov     rdi, rax
0x1800557dc  mov     [rbp+arg_18], rax
0x1800557e0  test    rax, rax
0x1800557e3  jz      short loc_1800557F8
0x1800557e5  call    UnBCL_____StringLiteral_21_
0x1800557ea  mov     rdx, rax; struct UnBCL::String *
0x1800557ed  mov     rcx, rdi; this
0x1800557f0  call    ??0SerializationException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::SerializationException::SerializationException(UnBCL::String const *)
0x1800557f5  mov     rbx, rax
0x1800557f8  lea     rdx, aVoidCdeclUnbcl_131; "void __cdecl UnBCL::SerializationStream"...
0x1800557ff  mov     rcx, rbx
0x180055802  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180055807  mov     [rbp+pExceptionObject], rax
0x18005580b  lea     rdx, _TI5PEAVSerializationException@UnBCL@@; pThrowInfo
0x180055812  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180055816  call    _CxxThrowException_0
0x18005581c  mov     ecx, 38h ; '8'; unsigned __int64
0x180055821  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180055826  mov     rdi, rax
0x180055829  mov     [rbp+arg_18], rax
0x18005582d  xor     ebx, ebx
0x18005582f  test    rax, rax
0x180055832  jz      short loc_180055847
0x180055834  call    UnBCL_____StringLiteral_19_
0x180055839  mov     rdx, rax; struct UnBCL::String *
0x18005583c  mov     rcx, rdi; this
0x18005583f  call    ??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *)
0x180055844  mov     rbx, rax
0x180055847  lea     rdx, aVoidCdeclUnbcl_131; "void __cdecl UnBCL::SerializationStream"...
0x18005584e  mov     rcx, rbx
0x180055851  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180055856  mov     [rbp+pExceptionObject], rax
0x18005585a  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180055861  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180055865  call    _CxxThrowException_0
0x18005586b  mov     ecx, 38h ; '8'; unsigned __int64
0x180055870  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180055875  mov     rdi, rax
0x180055878  mov     [rbp+arg_18], rax
0x18005587c  test    rax, rax
0x18005587f  jz      short loc_180055894
0x180055881  call    UnBCL_____StringLiteral_20_
0x180055886  mov     rdx, rax; struct UnBCL::String *
0x180055889  mov     rcx, rdi; this
0x18005588c  call    ??0SerializationException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::SerializationException::SerializationException(UnBCL::String const *)
0x180055891  mov     rbx, rax
0x180055894  lea     rdx, aVoidCdeclUnbcl_131; "void __cdecl UnBCL::SerializationStream"...
0x18005589b  mov     rcx, rbx
0x18005589e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800558a3  mov     [rbp+pExceptionObject], rax
0x1800558a7  lea     rdx, _TI5PEAVSerializationException@UnBCL@@; pThrowInfo
0x1800558ae  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800558b2  call    _CxxThrowException_0
```

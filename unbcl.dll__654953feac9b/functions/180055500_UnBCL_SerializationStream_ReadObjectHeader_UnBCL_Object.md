# UnBCL::SerializationStream::ReadObjectHeader(UnBCL::Object * &)

- ea: `0x180055500`
- end: `0x18005571e`
- name: `?ReadObjectHeader@SerializationStream@UnBCL@@AEAAHAEAPEAVObject@2@@Z`
- size: `542`
- prototype: `__int64 __fastcall(UnBCL::SerializationStream *__hidden this, struct UnBCL::Object **)`
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x180051d10`
- `0x180055150`

## callees

- `0x18000225c`
- `0x180002ca0`
- `0x180009e7c`
- `0x180011570`
- `0x18001a700`
- `0x1800477d0`
- `0x18004ffa0`
- `0x18004ffe0`
- `0x180050058`
- `0x1800500d8`
- `0x180050610`
- `0x180050658`
- `0x1800506a0`
- `0x180055500`
- `0x18005c180`
- `0x18006f010`

## string_xrefs

- `0x1800555f2`: `int __cdecl UnBCL::SerializationStream::ReadObjectHeader(class UnBCL::Object *&)`
- `0x180055664`: `int __cdecl UnBCL::SerializationStream::ReadObjectHeader(class UnBCL::Object *&)`
- `0x1800556af`: `int __cdecl UnBCL::SerializationStream::ReadObjectHeader(class UnBCL::Object *&)`
- `0x1800556fa`: `int __cdecl UnBCL::SerializationStream::ReadObjectHeader(class UnBCL::Object *&)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UnBCL::SerializationStream::ReadObjectHeader(
        UnBCL::SerializationStream *this,
        struct UnBCL::Object **a2)
{
  __int64 (__fastcall ***v4)(_QWORD); // rcx
  int v5; // eax
  __int64 v6; // rcx
  struct UnBCL::Object *v7; // rcx
  UnBCL::SerializationException *v9; // rax
  UnBCL::SerializationException *v10; // rbx
  const struct UnBCL::String *v11; // rax
  struct UnBCL::String *v12; // rax
  UnBCL::SerializationException *v13; // rax
  UnBCL::SerializationException *v14; // rbx
  __int64 v15; // rax
  const unsigned __int16 *InnerList; // rax
  UnBCL::SerializationException *v17; // rax
  UnBCL::SerializationException *v18; // rbx
  const struct UnBCL::String *v19; // rax
  UnBCL::SerializationException *v20; // rax
  UnBCL::SerializationException *v21; // rbx
  const struct UnBCL::String *v22; // rax
  _QWORD v23[3]; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int8 v24; // [rsp+68h] [rbp+28h] BYREF
  __int64 pExceptionObject; // [rsp+70h] [rbp+30h] BYREF
  __int64 v26; // [rsp+78h] [rbp+38h] BYREF

  *a2 = 0;
  v24 = 0;
  UnBCL::SerializationStream::ReadPrimitive<unsigned char>(this, &v24);
  switch ( v24 )
  {
    case '0':
      v7 = 0;
      break;
    case 'N':
      return 1;
    case 'P':
      v9 = (UnBCL::SerializationException *)UnBCL::Object::operator new(0x38u);
      v10 = v9;
      v26 = (__int64)v9;
      if ( v9 )
      {
        v11 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_24_();
        v9 = (UnBCL::SerializationException *)UnBCL::SerializationException::SerializationException(v10, v11);
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v9,
                           "int __cdecl UnBCL::SerializationStream::ReadObjectHeader(class UnBCL::Object *&)");
      throw (UnBCL::SerializationException **)&pExceptionObject;
    case 'R':
      LODWORD(pExceptionObject) = 0;
      UnBCL::SerializationStream::ReadPrimitive<int>(this, &pExceptionObject);
      v4 = (__int64 (__fastcall ***)(_QWORD))(*((_QWORD *)this + 9)
                                            + 8LL
                                            + *(int *)(*(_QWORD *)(*((_QWORD *)this + 9) + 8LL) + 12LL));
      v5 = (**v4)(v4);
      if ( (int)pExceptionObject >= v5 )
      {
        v17 = (UnBCL::SerializationException *)UnBCL::Object::operator new(0x38u);
        v18 = v17;
        v23[0] = v17;
        if ( v17 )
        {
          v19 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_22_();
          v17 = (UnBCL::SerializationException *)UnBCL::SerializationException::SerializationException(v18, v19);
        }
        v26 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v17,
                "int __cdecl UnBCL::SerializationStream::ReadObjectHeader(class UnBCL::Object *&)");
        throw (UnBCL::SerializationException **)&v26;
      }
      if ( (int)pExceptionObject < 0 )
      {
        v20 = (UnBCL::SerializationException *)UnBCL::Object::operator new(0x38u);
        v21 = v20;
        v23[0] = v20;
        if ( v20 )
        {
          v22 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_23_();
          v20 = (UnBCL::SerializationException *)UnBCL::SerializationException::SerializationException(v21, v22);
        }
        v26 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v20,
                "int __cdecl UnBCL::SerializationStream::ReadObjectHeader(class UnBCL::Object *&)");
        throw (UnBCL::SerializationException **)&v26;
      }
      v6 = *((_QWORD *)this + 9) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 9) + 8LL) + 16LL);
      v7 = *(struct UnBCL::Object **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
      break;
    default:
      v12 = UnBCL::String::Format(L"saw unrecognized object header '0x%x'", v24);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v23, v12);
      v13 = (UnBCL::SerializationException *)UnBCL::Object::operator new(0x38u);
      v14 = v13;
      v26 = (__int64)v13;
      if ( v13 )
      {
        v15 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(v23);
        InnerList = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v15);
        v13 = (UnBCL::SerializationException *)UnBCL::SerializationException::SerializationException(v14, InnerList);
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v13,
                           "int __cdecl UnBCL::SerializationStream::ReadObjectHeader(class UnBCL::Object *&)");
      throw (UnBCL::SerializationException **)&pExceptionObject;
  }
  *a2 = v7;
  return 0;
}

```

## disassembly

```asm
0x180055500  push    rbp
0x180055502  push    rbx
0x180055503  push    rdi
0x180055504  mov     rbp, rsp
0x180055507  sub     rsp, 40h
0x18005550b  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x180055513  mov     rbx, rdx
0x180055516  mov     rdi, rcx
0x180055519  mov     qword ptr [rdx], 0
0x180055520  mov     [rbp+arg_8], 0
0x180055524  lea     rdx, [rbp+arg_8]
0x180055528  call    ??$ReadPrimitive@E@SerializationStream@UnBCL@@IEAAAEAV01@AEAE@Z; UnBCL::SerializationStream::ReadPrimitive<uchar>(uchar &)
0x18005552d  movzx   eax, [rbp+arg_8]
0x180055531  cmp     al, 30h ; '0'
0x180055533  jz      loc_1800555BC
0x180055539  cmp     al, 4Eh ; 'N'
0x18005553b  jz      short loc_1800555B5
0x18005553d  cmp     al, 50h ; 'P'
0x18005553f  jz      loc_1800555CB
0x180055545  cmp     al, 52h ; 'R'
0x180055547  jnz     loc_180055616
0x18005554d  mov     dword ptr [rbp+pExceptionObject], 0
0x180055554  lea     rdx, [rbp+pExceptionObject]
0x180055558  mov     rcx, rdi
0x18005555b  call    ??$ReadPrimitive@H@SerializationStream@UnBCL@@IEAAAEAV01@AEAH@Z; UnBCL::SerializationStream::ReadPrimitive<int>(int &)
0x180055560  mov     rdx, [rdi+48h]
0x180055564  mov     rax, [rdx+8]
0x180055568  movsxd  rcx, dword ptr [rax+0Ch]
0x18005556c  add     rdx, 8
0x180055570  add     rcx, rdx
0x180055573  mov     rax, [rcx]
0x180055576  mov     rax, [rax]
0x180055579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005557e  mov     edx, dword ptr [rbp+pExceptionObject]
0x180055581  cmp     edx, eax
0x180055583  jge     loc_180055688
0x180055589  test    edx, edx
0x18005558b  js      loc_1800556D3
0x180055591  mov     r8, [rdi+48h]
0x180055595  mov     rax, [r8+8]
0x180055599  movsxd  rcx, dword ptr [rax+10h]
0x18005559d  add     r8, 8
0x1800555a1  add     rcx, r8
0x1800555a4  mov     rax, [rcx]
0x1800555a7  mov     rax, [rax+18h]
0x1800555ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555b0  mov     rcx, [rax]
0x1800555b3  jmp     short loc_1800555BE
0x1800555b5  mov     eax, 1
0x1800555ba  jmp     short loc_1800555C3
0x1800555bc  xor     ecx, ecx
0x1800555be  mov     [rbx], rcx
0x1800555c1  xor     eax, eax
0x1800555c3  add     rsp, 40h
0x1800555c7  pop     rdi
0x1800555c8  pop     rbx
0x1800555c9  pop     rbp
0x1800555ca  retn
0x1800555cb  mov     ecx, 38h ; '8'; unsigned __int64
0x1800555d0  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800555d5  mov     rbx, rax
0x1800555d8  mov     [rbp+arg_18], rax
0x1800555dc  test    rax, rax
0x1800555df  jz      short loc_1800555F2
0x1800555e1  call    UnBCL_____StringLiteral_24_
0x1800555e6  mov     rdx, rax; struct UnBCL::String *
0x1800555e9  mov     rcx, rbx; this
0x1800555ec  call    ??0SerializationException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::SerializationException::SerializationException(UnBCL::String const *)
0x1800555f1  nop
0x1800555f2  lea     rdx, aIntCdeclUnbclS_10; "int __cdecl UnBCL::SerializationStream:"...
0x1800555f9  mov     rcx, rax
0x1800555fc  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180055601  mov     [rbp+pExceptionObject], rax
0x180055605  lea     rdx, _TI5PEAVSerializationException@UnBCL@@; pThrowInfo
0x18005560c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180055610  call    _CxxThrowException_0
0x180055616  mov     edx, eax
0x180055618  lea     rcx, aSawUnrecognize; "saw unrecognized object header '0x%x'"
0x18005561f  call    ?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x180055624  mov     rdx, rax
0x180055627  lea     rcx, [rbp+var_18]
0x18005562b  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180055630  nop
0x180055631  mov     ecx, 38h ; '8'; unsigned __int64
0x180055636  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18005563b  mov     rbx, rax
0x18005563e  mov     [rbp+arg_18], rax
0x180055642  test    rax, rax
0x180055645  jz      short loc_180055664
0x180055647  lea     rcx, [rbp+var_18]
0x18005564b  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x180055650  mov     rcx, rax
0x180055653  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x180055658  mov     rdx, rax; unsigned __int16 *
0x18005565b  mov     rcx, rbx; this
0x18005565e  call    ??0SerializationException@UnBCL@@QEAA@PEBG@Z; UnBCL::SerializationException::SerializationException(ushort const *)
0x180055663  nop
0x180055664  lea     rdx, aIntCdeclUnbclS_10; "int __cdecl UnBCL::SerializationStream:"...
0x18005566b  mov     rcx, rax
0x18005566e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180055673  mov     [rbp+pExceptionObject], rax
0x180055677  lea     rdx, _TI5PEAVSerializationException@UnBCL@@; pThrowInfo
0x18005567e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180055682  call    _CxxThrowException_0
0x180055688  mov     ecx, 38h ; '8'; unsigned __int64
0x18005568d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180055692  mov     rbx, rax
0x180055695  mov     [rbp+var_18], rax
0x180055699  test    rax, rax
0x18005569c  jz      short loc_1800556AF
0x18005569e  call    UnBCL_____StringLiteral_22_
0x1800556a3  mov     rdx, rax; struct UnBCL::String *
0x1800556a6  mov     rcx, rbx; this
0x1800556a9  call    ??0SerializationException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::SerializationException::SerializationException(UnBCL::String const *)
0x1800556ae  nop
0x1800556af  lea     rdx, aIntCdeclUnbclS_10; "int __cdecl UnBCL::SerializationStream:"...
0x1800556b6  mov     rcx, rax
0x1800556b9  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800556be  mov     [rbp+arg_18], rax
0x1800556c2  lea     rdx, _TI5PEAVSerializationException@UnBCL@@; pThrowInfo
0x1800556c9  lea     rcx, [rbp+arg_18]; pExceptionObject
0x1800556cd  call    _CxxThrowException_0
0x1800556d3  mov     ecx, 38h ; '8'; unsigned __int64
0x1800556d8  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800556dd  mov     rbx, rax
0x1800556e0  mov     [rbp+var_18], rax
0x1800556e4  test    rax, rax
0x1800556e7  jz      short loc_1800556FA
0x1800556e9  call    UnBCL_____StringLiteral_23_
0x1800556ee  mov     rdx, rax; struct UnBCL::String *
0x1800556f1  mov     rcx, rbx; this
0x1800556f4  call    ??0SerializationException@UnBCL@@QEAA@PEBVString@1@@Z; UnBCL::SerializationException::SerializationException(UnBCL::String const *)
0x1800556f9  nop
0x1800556fa  lea     rdx, aIntCdeclUnbclS_10; "int __cdecl UnBCL::SerializationStream:"...
0x180055701  mov     rcx, rax
0x180055704  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180055709  mov     [rbp+arg_18], rax
0x18005570d  lea     rdx, _TI5PEAVSerializationException@UnBCL@@; pThrowInfo
0x180055714  lea     rcx, [rbp+arg_18]; pExceptionObject
0x180055718  call    _CxxThrowException_0
```

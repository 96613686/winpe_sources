# UnBCL::ArrayList<UnBCL::Object *>::CopyTo(UnBCL::Array<UnBCL::Object *> *,int)

- ea: `0x180016e24`
- end: `0x180017027`
- name: `?CopyTo@?$ArrayList@PEAVObject@UnBCL@@@UnBCL@@UEBAXPEAV?$Array@PEAVObject@UnBCL@@@2@H@Z`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180016e10`

## callees

- `0x18000225c`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180016e24`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180016fa7`: `null array argument to ArrayList#CopyTo`
- `0x180016f5d`: `index out of range to ArrayList#CopyTo`
- `0x180016f6d`: `void __cdecl UnBCL::ArrayList<class UnBCL::Object *>::CopyTo(class UnBCL::Array<class UnBCL::Object *> *,int) const`
- `0x180016fb7`: `void __cdecl UnBCL::ArrayList<class UnBCL::Object *>::CopyTo(class UnBCL::Array<class UnBCL::Object *> *,int) const`
- `0x180017001`: `void __cdecl UnBCL::ArrayList<class UnBCL::Object *>::CopyTo(class UnBCL::Array<class UnBCL::Object *> *,int) const`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::ArrayList<UnBCL::Object *>::CopyTo(__int64 a1, __int64 a2, int a3)
{
  int (__fastcall ***v6)(_QWORD); // rcx
  signed int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD); // rcx
  __int64 (__fastcall ***v9)(_QWORD); // rcx
  __int64 result; // rax
  __int64 v11; // r15
  __int64 v12; // r14
  int i; // ebx
  __int64 (__fastcall ***v14)(_QWORD); // rcx
  UnBCL::ArgumentOutOfRangeException *v15; // rax
  UnBCL::ArgumentNullException *v16; // rax
  UnBCL::ArgumentException *v17; // rax
  __int64 pExceptionObject; // [rsp+58h] [rbp+10h] BYREF
  UnBCL::ArgumentNullException *v19; // [rsp+68h] [rbp+20h]

  if ( !a2 )
  {
    v16 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v19 = v16;
    if ( v16 )
      v16 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v16,
                                              L"null array argument to ArrayList#CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v16,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::Object *>::CopyTo(class UnBCL::Array<class UnBCL::Ob"
                         "ject *> *,int) const");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0
    || (v6 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL),
        0x7FFFFFFF - a3 < (**v6)(v6)) )
  {
    v15 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v19 = v15;
    if ( v15 )
      v15 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v15,
                                                    L"index out of range to ArrayList#CopyTo");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v15,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::Object *>::CopyTo(class UnBCL::Array<class UnBCL::Ob"
                         "ject *> *,int) const");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v7 = (**(__int64 (__fastcall ***)(__int64))a2)(a2);
  v8 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL);
  if ( (int)(a3 + (**v8)(v8)) > v7 )
  {
    v17 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v19 = v17;
    if ( v17 )
      v17 = (UnBCL::ArgumentException *)UnBCL::ArgumentException::ArgumentException(
                                          v17,
                                          L"insufficient space available in target array");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v17,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::Object *>::CopyTo(class UnBCL::Array<class UnBCL::Ob"
                         "ject *> *,int) const");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  v9 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL);
  result = (**v9)(v9);
  if ( (_DWORD)result )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 - 88) + 104LL))(a1 - 88, 0);
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 56LL))(a2, 0);
    for ( i = 0; ; ++i )
    {
      v14 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL);
      result = (**v14)(v14);
      if ( i >= (int)result )
        break;
      *(_QWORD *)(v12 + 8LL * (i + a3)) = *(_QWORD *)(v11 + 8LL * i);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016e24  push    rdi
0x180016e26  push    r14
0x180016e28  push    r15
0x180016e2a  sub     rsp, 30h
0x180016e2e  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180016e37  mov     [rsp+48h+arg_0], rbx
0x180016e3c  mov     [rsp+48h+arg_10], rsi
0x180016e41  mov     esi, r8d
0x180016e44  mov     r14, rdx
0x180016e47  mov     rdi, rcx
0x180016e4a  test    rdx, rdx
0x180016e4d  jz      loc_180016F93
0x180016e53  test    r8d, r8d
0x180016e56  js      loc_180016F49
0x180016e5c  mov     rax, [rcx-50h]
0x180016e60  movsxd  rcx, dword ptr [rax+0Ch]
0x180016e64  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016e68  add     rcx, rdi
0x180016e6b  mov     rax, [rcx]
0x180016e6e  mov     rax, [rax]
0x180016e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e76  mov     ecx, 7FFFFFFFh
0x180016e7b  sub     ecx, esi
0x180016e7d  cmp     ecx, eax
0x180016e7f  jl      loc_180016F49
0x180016e85  mov     rax, [r14]
0x180016e88  mov     rcx, r14
0x180016e8b  mov     rax, [rax]
0x180016e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e93  mov     ebx, eax
0x180016e95  mov     rcx, [rdi-50h]
0x180016e99  movsxd  rcx, dword ptr [rcx+0Ch]
0x180016e9d  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016ea1  add     rcx, rdi
0x180016ea4  mov     rdx, [rcx]
0x180016ea7  mov     rax, [rdx]
0x180016eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016eaf  add     eax, esi
0x180016eb1  cmp     eax, ebx
0x180016eb3  jg      loc_180016FDD
0x180016eb9  mov     rax, [rdi-50h]
0x180016ebd  movsxd  rcx, dword ptr [rax+0Ch]
0x180016ec1  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016ec5  add     rcx, rdi
0x180016ec8  mov     rax, [rcx]
0x180016ecb  mov     rax, [rax]
0x180016ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ed3  test    eax, eax
0x180016ed5  jz      short loc_180016F35
0x180016ed7  lea     rcx, [rdi-58h]
0x180016edb  mov     rax, [rcx]
0x180016ede  xor     edx, edx
0x180016ee0  mov     rax, [rax+68h]
0x180016ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ee9  mov     r15, rax
0x180016eec  mov     rcx, [r14]
0x180016eef  mov     rax, [rcx+38h]
0x180016ef3  xor     edx, edx
0x180016ef5  mov     rcx, r14
0x180016ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016efd  mov     r14, rax
0x180016f00  xor     ebx, ebx
0x180016f02  mov     rcx, [rdi-50h]
0x180016f06  movsxd  rcx, dword ptr [rcx+0Ch]
0x180016f0a  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016f0e  add     rcx, rdi
0x180016f11  mov     rdx, [rcx]
0x180016f14  mov     rax, [rdx]
0x180016f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f1c  cmp     ebx, eax
0x180016f1e  jge     short loc_180016F35
0x180016f20  movsxd  rdx, ebx
0x180016f23  lea     eax, [rbx+rsi]
0x180016f26  movsxd  rcx, eax
0x180016f29  mov     rax, [r15+rdx*8]
0x180016f2d  mov     [r14+rcx*8], rax
0x180016f31  inc     ebx
0x180016f33  jmp     short loc_180016F02
0x180016f35  mov     rbx, [rsp+48h+arg_0]
0x180016f3a  mov     rsi, [rsp+48h+arg_10]
0x180016f3f  add     rsp, 30h
0x180016f43  pop     r15
0x180016f45  pop     r14
0x180016f47  pop     rdi
0x180016f48  retn
0x180016f49  mov     ecx, 38h ; '8'; unsigned __int64
0x180016f4e  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016f53  mov     [rsp+48h+arg_18], rax
0x180016f58  test    rax, rax
0x180016f5b  jz      short loc_180016F6D
0x180016f5d  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x180016f64  mov     rcx, rax; this
0x180016f67  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180016f6c  nop
0x180016f6d  lea     rdx, aVoidCdeclUnbcl_114; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180016f74  mov     rcx, rax
0x180016f77  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016f7c  mov     [rsp+48h+pExceptionObject], rax
0x180016f81  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180016f88  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180016f8d  call    _CxxThrowException_0
0x180016f93  mov     ecx, 38h ; '8'; unsigned __int64
0x180016f98  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016f9d  mov     [rsp+48h+arg_18], rax
0x180016fa2  test    rax, rax
0x180016fa5  jz      short loc_180016FB7
0x180016fa7  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x180016fae  mov     rcx, rax; this
0x180016fb1  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180016fb6  nop
0x180016fb7  lea     rdx, aVoidCdeclUnbcl_114; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180016fbe  mov     rcx, rax
0x180016fc1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016fc6  mov     [rsp+48h+pExceptionObject], rax
0x180016fcb  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180016fd2  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180016fd7  call    _CxxThrowException_0
0x180016fdd  mov     ecx, 38h ; '8'; unsigned __int64
0x180016fe2  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016fe7  mov     [rsp+48h+arg_18], rax
0x180016fec  test    rax, rax
0x180016fef  jz      short loc_180017001
0x180016ff1  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x180016ff8  mov     rcx, rax; this
0x180016ffb  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180017000  nop
0x180017001  lea     rdx, aVoidCdeclUnbcl_114; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180017008  mov     rcx, rax
0x18001700b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180017010  mov     [rsp+48h+pExceptionObject], rax
0x180017015  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18001701c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180017021  call    _CxxThrowException_0
```

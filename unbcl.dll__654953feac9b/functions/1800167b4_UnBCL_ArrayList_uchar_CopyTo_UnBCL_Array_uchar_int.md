# UnBCL::ArrayList<uchar>::CopyTo(UnBCL::Array<uchar> *,int)

- ea: `0x1800167b4`
- end: `0x1800169b4`
- name: `?CopyTo@?$ArrayList@E@UnBCL@@UEBAXPEAV?$Array@E@2@H@Z`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800167a0`

## callees

- `0x18000225c`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x1800167b4`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180016934`: `null array argument to ArrayList#CopyTo`
- `0x1800168ea`: `index out of range to ArrayList#CopyTo`
- `0x1800168fa`: `void __cdecl UnBCL::ArrayList<unsigned char>::CopyTo(class UnBCL::Array<unsigned char> *,int) const`
- `0x180016944`: `void __cdecl UnBCL::ArrayList<unsigned char>::CopyTo(class UnBCL::Array<unsigned char> *,int) const`
- `0x18001698e`: `void __cdecl UnBCL::ArrayList<unsigned char>::CopyTo(class UnBCL::Array<unsigned char> *,int) const`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::ArrayList<unsigned char>::CopyTo(__int64 a1, __int64 a2, int a3)
{
  int (__fastcall ***v6)(_QWORD); // rcx
  signed int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD); // rcx
  __int64 (__fastcall ***v9)(_QWORD); // rcx
  __int64 result; // rax
  __int64 v11; // rbp
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
                         "void __cdecl UnBCL::ArrayList<unsigned char>::CopyTo(class UnBCL::Array<unsigned char> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<unsigned char>::CopyTo(class UnBCL::Array<unsigned char> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<unsigned char>::CopyTo(class UnBCL::Array<unsigned char> *,int) const");
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
      *(_BYTE *)(i + a3 + v12) = *(_BYTE *)(i + v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800167b4  push    rsi
0x1800167b6  push    rdi
0x1800167b7  push    r14
0x1800167b9  sub     rsp, 30h
0x1800167bd  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800167c6  mov     [rsp+48h+arg_0], rbx
0x1800167cb  mov     [rsp+48h+arg_10], rbp
0x1800167d0  mov     esi, r8d
0x1800167d3  mov     r14, rdx
0x1800167d6  mov     rdi, rcx
0x1800167d9  test    rdx, rdx
0x1800167dc  jz      loc_180016920
0x1800167e2  test    r8d, r8d
0x1800167e5  js      loc_1800168D6
0x1800167eb  mov     rax, [rcx-50h]
0x1800167ef  movsxd  rcx, dword ptr [rax+0Ch]
0x1800167f3  add     rcx, 0FFFFFFFFFFFFFFB0h
0x1800167f7  add     rcx, rdi
0x1800167fa  mov     rax, [rcx]
0x1800167fd  mov     rax, [rax]
0x180016800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016805  mov     ecx, 7FFFFFFFh
0x18001680a  sub     ecx, esi
0x18001680c  cmp     ecx, eax
0x18001680e  jl      loc_1800168D6
0x180016814  mov     rax, [r14]
0x180016817  mov     rcx, r14
0x18001681a  mov     rax, [rax]
0x18001681d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016822  mov     ebx, eax
0x180016824  mov     rcx, [rdi-50h]
0x180016828  movsxd  rcx, dword ptr [rcx+0Ch]
0x18001682c  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016830  add     rcx, rdi
0x180016833  mov     rdx, [rcx]
0x180016836  mov     rax, [rdx]
0x180016839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001683e  add     eax, esi
0x180016840  cmp     eax, ebx
0x180016842  jg      loc_18001696A
0x180016848  mov     rax, [rdi-50h]
0x18001684c  movsxd  rcx, dword ptr [rax+0Ch]
0x180016850  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016854  add     rcx, rdi
0x180016857  mov     rax, [rcx]
0x18001685a  mov     rax, [rax]
0x18001685d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016862  test    eax, eax
0x180016864  jz      short loc_1800168C3
0x180016866  lea     rcx, [rdi-58h]
0x18001686a  mov     rax, [rcx]
0x18001686d  xor     edx, edx
0x18001686f  mov     rax, [rax+68h]
0x180016873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016878  mov     rbp, rax
0x18001687b  mov     rcx, [r14]
0x18001687e  mov     rax, [rcx+38h]
0x180016882  xor     edx, edx
0x180016884  mov     rcx, r14
0x180016887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001688c  mov     r14, rax
0x18001688f  xor     ebx, ebx
0x180016891  mov     rcx, [rdi-50h]
0x180016895  movsxd  rcx, dword ptr [rcx+0Ch]
0x180016899  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18001689d  add     rcx, rdi
0x1800168a0  mov     rdx, [rcx]
0x1800168a3  mov     rax, [rdx]
0x1800168a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168ab  cmp     ebx, eax
0x1800168ad  jge     short loc_1800168C3
0x1800168af  movsxd  rdx, ebx
0x1800168b2  lea     eax, [rbx+rsi]
0x1800168b5  movsxd  rcx, eax
0x1800168b8  mov     al, [rdx+rbp]
0x1800168bb  mov     [rcx+r14], al
0x1800168bf  inc     ebx
0x1800168c1  jmp     short loc_180016891
0x1800168c3  mov     rbx, [rsp+48h+arg_0]
0x1800168c8  mov     rbp, [rsp+48h+arg_10]
0x1800168cd  add     rsp, 30h
0x1800168d1  pop     r14
0x1800168d3  pop     rdi
0x1800168d4  pop     rsi
0x1800168d5  retn
0x1800168d6  mov     ecx, 38h ; '8'; unsigned __int64
0x1800168db  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800168e0  mov     [rsp+48h+arg_18], rax
0x1800168e5  test    rax, rax
0x1800168e8  jz      short loc_1800168FA
0x1800168ea  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x1800168f1  mov     rcx, rax; this
0x1800168f4  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x1800168f9  nop
0x1800168fa  lea     rdx, aVoidCdeclUnbcl_26; "void __cdecl UnBCL::ArrayList<unsigned "...
0x180016901  mov     rcx, rax
0x180016904  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016909  mov     [rsp+48h+pExceptionObject], rax
0x18001690e  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180016915  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001691a  call    _CxxThrowException_0
0x180016920  mov     ecx, 38h ; '8'; unsigned __int64
0x180016925  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001692a  mov     [rsp+48h+arg_18], rax
0x18001692f  test    rax, rax
0x180016932  jz      short loc_180016944
0x180016934  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x18001693b  mov     rcx, rax; this
0x18001693e  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180016943  nop
0x180016944  lea     rdx, aVoidCdeclUnbcl_26; "void __cdecl UnBCL::ArrayList<unsigned "...
0x18001694b  mov     rcx, rax
0x18001694e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016953  mov     [rsp+48h+pExceptionObject], rax
0x180016958  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18001695f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180016964  call    _CxxThrowException_0
0x18001696a  mov     ecx, 38h ; '8'; unsigned __int64
0x18001696f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016974  mov     [rsp+48h+arg_18], rax
0x180016979  test    rax, rax
0x18001697c  jz      short loc_18001698E
0x18001697e  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x180016985  mov     rcx, rax; this
0x180016988  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18001698d  nop
0x18001698e  lea     rdx, aVoidCdeclUnbcl_26; "void __cdecl UnBCL::ArrayList<unsigned "...
0x180016995  mov     rcx, rax
0x180016998  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001699d  mov     [rsp+48h+pExceptionObject], rax
0x1800169a2  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x1800169a9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800169ae  call    _CxxThrowException_0
```

# UnBCL::ArrayList<int>::CopyTo(UnBCL::Array<int> *,int)

- ea: `0x180016c04`
- end: `0x180016e07`
- name: `?CopyTo@?$ArrayList@H@UnBCL@@UEBAXPEAV?$Array@H@2@H@Z`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180016bf0`

## callees

- `0x18000225c`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180016c04`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180016d87`: `null array argument to ArrayList#CopyTo`
- `0x180016d3d`: `index out of range to ArrayList#CopyTo`
- `0x180016d4d`: `void __cdecl UnBCL::ArrayList<int>::CopyTo(class UnBCL::Array<int> *,int) const`
- `0x180016d97`: `void __cdecl UnBCL::ArrayList<int>::CopyTo(class UnBCL::Array<int> *,int) const`
- `0x180016de1`: `void __cdecl UnBCL::ArrayList<int>::CopyTo(class UnBCL::Array<int> *,int) const`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::ArrayList<int>::CopyTo(__int64 a1, __int64 a2, int a3)
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
                         "void __cdecl UnBCL::ArrayList<int>::CopyTo(class UnBCL::Array<int> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<int>::CopyTo(class UnBCL::Array<int> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<int>::CopyTo(class UnBCL::Array<int> *,int) const");
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
      *(_DWORD *)(v12 + 4LL * (i + a3)) = *(_DWORD *)(v11 + 4LL * i);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016c04  push    rdi
0x180016c06  push    r14
0x180016c08  push    r15
0x180016c0a  sub     rsp, 30h
0x180016c0e  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180016c17  mov     [rsp+48h+arg_0], rbx
0x180016c1c  mov     [rsp+48h+arg_10], rsi
0x180016c21  mov     esi, r8d
0x180016c24  mov     r14, rdx
0x180016c27  mov     rdi, rcx
0x180016c2a  test    rdx, rdx
0x180016c2d  jz      loc_180016D73
0x180016c33  test    r8d, r8d
0x180016c36  js      loc_180016D29
0x180016c3c  mov     rax, [rcx-50h]
0x180016c40  movsxd  rcx, dword ptr [rax+0Ch]
0x180016c44  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016c48  add     rcx, rdi
0x180016c4b  mov     rax, [rcx]
0x180016c4e  mov     rax, [rax]
0x180016c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c56  mov     ecx, 7FFFFFFFh
0x180016c5b  sub     ecx, esi
0x180016c5d  cmp     ecx, eax
0x180016c5f  jl      loc_180016D29
0x180016c65  mov     rax, [r14]
0x180016c68  mov     rcx, r14
0x180016c6b  mov     rax, [rax]
0x180016c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c73  mov     ebx, eax
0x180016c75  mov     rcx, [rdi-50h]
0x180016c79  movsxd  rcx, dword ptr [rcx+0Ch]
0x180016c7d  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016c81  add     rcx, rdi
0x180016c84  mov     rdx, [rcx]
0x180016c87  mov     rax, [rdx]
0x180016c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c8f  add     eax, esi
0x180016c91  cmp     eax, ebx
0x180016c93  jg      loc_180016DBD
0x180016c99  mov     rax, [rdi-50h]
0x180016c9d  movsxd  rcx, dword ptr [rax+0Ch]
0x180016ca1  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016ca5  add     rcx, rdi
0x180016ca8  mov     rax, [rcx]
0x180016cab  mov     rax, [rax]
0x180016cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cb3  test    eax, eax
0x180016cb5  jz      short loc_180016D15
0x180016cb7  lea     rcx, [rdi-58h]
0x180016cbb  mov     rax, [rcx]
0x180016cbe  xor     edx, edx
0x180016cc0  mov     rax, [rax+68h]
0x180016cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cc9  mov     r15, rax
0x180016ccc  mov     rcx, [r14]
0x180016ccf  mov     rax, [rcx+38h]
0x180016cd3  xor     edx, edx
0x180016cd5  mov     rcx, r14
0x180016cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cdd  mov     r14, rax
0x180016ce0  xor     ebx, ebx
0x180016ce2  mov     rcx, [rdi-50h]
0x180016ce6  movsxd  rcx, dword ptr [rcx+0Ch]
0x180016cea  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016cee  add     rcx, rdi
0x180016cf1  mov     rdx, [rcx]
0x180016cf4  mov     rax, [rdx]
0x180016cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cfc  cmp     ebx, eax
0x180016cfe  jge     short loc_180016D15
0x180016d00  movsxd  rdx, ebx
0x180016d03  lea     eax, [rbx+rsi]
0x180016d06  movsxd  rcx, eax
0x180016d09  mov     eax, [r15+rdx*4]
0x180016d0d  mov     [r14+rcx*4], eax
0x180016d11  inc     ebx
0x180016d13  jmp     short loc_180016CE2
0x180016d15  mov     rbx, [rsp+48h+arg_0]
0x180016d1a  mov     rsi, [rsp+48h+arg_10]
0x180016d1f  add     rsp, 30h
0x180016d23  pop     r15
0x180016d25  pop     r14
0x180016d27  pop     rdi
0x180016d28  retn
0x180016d29  mov     ecx, 38h ; '8'; unsigned __int64
0x180016d2e  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016d33  mov     [rsp+48h+arg_18], rax
0x180016d38  test    rax, rax
0x180016d3b  jz      short loc_180016D4D
0x180016d3d  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x180016d44  mov     rcx, rax; this
0x180016d47  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180016d4c  nop
0x180016d4d  lea     rdx, aVoidCdeclUnbcl_174; "void __cdecl UnBCL::ArrayList<int>::Cop"...
0x180016d54  mov     rcx, rax
0x180016d57  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016d5c  mov     [rsp+48h+pExceptionObject], rax
0x180016d61  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180016d68  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180016d6d  call    _CxxThrowException_0
0x180016d73  mov     ecx, 38h ; '8'; unsigned __int64
0x180016d78  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016d7d  mov     [rsp+48h+arg_18], rax
0x180016d82  test    rax, rax
0x180016d85  jz      short loc_180016D97
0x180016d87  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x180016d8e  mov     rcx, rax; this
0x180016d91  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180016d96  nop
0x180016d97  lea     rdx, aVoidCdeclUnbcl_174; "void __cdecl UnBCL::ArrayList<int>::Cop"...
0x180016d9e  mov     rcx, rax
0x180016da1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016da6  mov     [rsp+48h+pExceptionObject], rax
0x180016dab  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180016db2  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180016db7  call    _CxxThrowException_0
0x180016dbd  mov     ecx, 38h ; '8'; unsigned __int64
0x180016dc2  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016dc7  mov     [rsp+48h+arg_18], rax
0x180016dcc  test    rax, rax
0x180016dcf  jz      short loc_180016DE1
0x180016dd1  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x180016dd8  mov     rcx, rax; this
0x180016ddb  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180016de0  nop
0x180016de1  lea     rdx, aVoidCdeclUnbcl_174; "void __cdecl UnBCL::ArrayList<int>::Cop"...
0x180016de8  mov     rcx, rax
0x180016deb  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016df0  mov     [rsp+48h+pExceptionObject], rax
0x180016df5  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180016dfc  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180016e01  call    _CxxThrowException_0
```

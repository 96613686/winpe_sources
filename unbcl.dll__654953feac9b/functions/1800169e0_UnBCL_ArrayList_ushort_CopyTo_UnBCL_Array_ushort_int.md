# UnBCL::ArrayList<ushort>::CopyTo(UnBCL::Array<ushort> *,int)

- ea: `0x1800169e0`
- end: `0x180016be5`
- name: `?CopyTo@?$ArrayList@G@UnBCL@@UEBAXPEAV?$Array@G@2@H@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800169c0`

## callees

- `0x18000225c`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x1800169e0`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180016b65`: `null array argument to ArrayList#CopyTo`
- `0x180016b1b`: `index out of range to ArrayList#CopyTo`
- `0x180016b2b`: `void __cdecl UnBCL::ArrayList<unsigned short>::CopyTo(class UnBCL::Array<unsigned short> *,int) const`
- `0x180016b75`: `void __cdecl UnBCL::ArrayList<unsigned short>::CopyTo(class UnBCL::Array<unsigned short> *,int) const`
- `0x180016bbf`: `void __cdecl UnBCL::ArrayList<unsigned short>::CopyTo(class UnBCL::Array<unsigned short> *,int) const`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::ArrayList<unsigned short>::CopyTo(__int64 a1, __int64 a2, int a3)
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
                         "void __cdecl UnBCL::ArrayList<unsigned short>::CopyTo(class UnBCL::Array<unsigned short> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<unsigned short>::CopyTo(class UnBCL::Array<unsigned short> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<unsigned short>::CopyTo(class UnBCL::Array<unsigned short> *,int) const");
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
      *(_WORD *)(v12 + 2LL * (i + a3)) = *(_WORD *)(v11 + 2LL * i);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800169e0  push    rdi
0x1800169e2  push    r14
0x1800169e4  push    r15
0x1800169e6  sub     rsp, 30h
0x1800169ea  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800169f3  mov     [rsp+48h+arg_0], rbx
0x1800169f8  mov     [rsp+48h+arg_10], rsi
0x1800169fd  mov     esi, r8d
0x180016a00  mov     r14, rdx
0x180016a03  mov     rdi, rcx
0x180016a06  test    rdx, rdx
0x180016a09  jz      loc_180016B51
0x180016a0f  test    r8d, r8d
0x180016a12  js      loc_180016B07
0x180016a18  mov     rax, [rcx-50h]
0x180016a1c  movsxd  rcx, dword ptr [rax+0Ch]
0x180016a20  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016a24  add     rcx, rdi
0x180016a27  mov     rax, [rcx]
0x180016a2a  mov     rax, [rax]
0x180016a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a32  mov     ecx, 7FFFFFFFh
0x180016a37  sub     ecx, esi
0x180016a39  cmp     ecx, eax
0x180016a3b  jl      loc_180016B07
0x180016a41  mov     rax, [r14]
0x180016a44  mov     rcx, r14
0x180016a47  mov     rax, [rax]
0x180016a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a4f  mov     ebx, eax
0x180016a51  mov     rcx, [rdi-50h]
0x180016a55  movsxd  rcx, dword ptr [rcx+0Ch]
0x180016a59  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016a5d  add     rcx, rdi
0x180016a60  mov     rdx, [rcx]
0x180016a63  mov     rax, [rdx]
0x180016a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a6b  add     eax, esi
0x180016a6d  cmp     eax, ebx
0x180016a6f  jg      loc_180016B9B
0x180016a75  mov     rax, [rdi-50h]
0x180016a79  movsxd  rcx, dword ptr [rax+0Ch]
0x180016a7d  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016a81  add     rcx, rdi
0x180016a84  mov     rax, [rcx]
0x180016a87  mov     rax, [rax]
0x180016a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a8f  test    eax, eax
0x180016a91  jz      short loc_180016AF3
0x180016a93  lea     rcx, [rdi-58h]
0x180016a97  mov     rax, [rcx]
0x180016a9a  xor     edx, edx
0x180016a9c  mov     rax, [rax+68h]
0x180016aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aa5  mov     r15, rax
0x180016aa8  mov     rcx, [r14]
0x180016aab  mov     rax, [rcx+38h]
0x180016aaf  xor     edx, edx
0x180016ab1  mov     rcx, r14
0x180016ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ab9  mov     r14, rax
0x180016abc  xor     ebx, ebx
0x180016abe  mov     rcx, [rdi-50h]
0x180016ac2  movsxd  rcx, dword ptr [rcx+0Ch]
0x180016ac6  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180016aca  add     rcx, rdi
0x180016acd  mov     rdx, [rcx]
0x180016ad0  mov     rax, [rdx]
0x180016ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ad8  cmp     ebx, eax
0x180016ada  jge     short loc_180016AF3
0x180016adc  movsxd  rdx, ebx
0x180016adf  lea     eax, [rbx+rsi]
0x180016ae2  movsxd  rcx, eax
0x180016ae5  movzx   eax, word ptr [r15+rdx*2]
0x180016aea  mov     [r14+rcx*2], ax
0x180016aef  inc     ebx
0x180016af1  jmp     short loc_180016ABE
0x180016af3  mov     rbx, [rsp+48h+arg_0]
0x180016af8  mov     rsi, [rsp+48h+arg_10]
0x180016afd  add     rsp, 30h
0x180016b01  pop     r15
0x180016b03  pop     r14
0x180016b05  pop     rdi
0x180016b06  retn
0x180016b07  mov     ecx, 38h ; '8'; unsigned __int64
0x180016b0c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016b11  mov     [rsp+48h+arg_18], rax
0x180016b16  test    rax, rax
0x180016b19  jz      short loc_180016B2B
0x180016b1b  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x180016b22  mov     rcx, rax; this
0x180016b25  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180016b2a  nop
0x180016b2b  lea     rdx, aVoidCdeclUnbcl_58; "void __cdecl UnBCL::ArrayList<unsigned "...
0x180016b32  mov     rcx, rax
0x180016b35  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016b3a  mov     [rsp+48h+pExceptionObject], rax
0x180016b3f  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180016b46  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180016b4b  call    _CxxThrowException_0
0x180016b51  mov     ecx, 38h ; '8'; unsigned __int64
0x180016b56  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016b5b  mov     [rsp+48h+arg_18], rax
0x180016b60  test    rax, rax
0x180016b63  jz      short loc_180016B75
0x180016b65  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x180016b6c  mov     rcx, rax; this
0x180016b6f  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180016b74  nop
0x180016b75  lea     rdx, aVoidCdeclUnbcl_58; "void __cdecl UnBCL::ArrayList<unsigned "...
0x180016b7c  mov     rcx, rax
0x180016b7f  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016b84  mov     [rsp+48h+pExceptionObject], rax
0x180016b89  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180016b90  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180016b95  call    _CxxThrowException_0
0x180016b9b  mov     ecx, 38h ; '8'; unsigned __int64
0x180016ba0  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180016ba5  mov     [rsp+48h+arg_18], rax
0x180016baa  test    rax, rax
0x180016bad  jz      short loc_180016BBF
0x180016baf  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x180016bb6  mov     rcx, rax; this
0x180016bb9  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180016bbe  nop
0x180016bbf  lea     rdx, aVoidCdeclUnbcl_58; "void __cdecl UnBCL::ArrayList<unsigned "...
0x180016bc6  mov     rcx, rax
0x180016bc9  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016bce  mov     [rsp+48h+pExceptionObject], rax
0x180016bd3  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180016bda  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180016bdf  call    _CxxThrowException_0
```

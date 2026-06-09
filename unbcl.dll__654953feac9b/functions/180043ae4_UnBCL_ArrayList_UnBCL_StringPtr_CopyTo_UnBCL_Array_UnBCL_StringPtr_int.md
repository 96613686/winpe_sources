# UnBCL::ArrayList<UnBCL::StringPtr>::CopyTo(UnBCL::Array<UnBCL::StringPtr> *,int)

- ea: `0x180043ae4`
- end: `0x180043d10`
- name: `?CopyTo@?$ArrayList@VStringPtr@UnBCL@@@UnBCL@@UEBAXPEAV?$Array@VStringPtr@UnBCL@@@2@H@Z`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180043ad0`

## callees

- `0x18000225c`
- `0x180002f50`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180043ae4`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180043c90`: `null array argument to ArrayList#CopyTo`
- `0x180043c46`: `index out of range to ArrayList#CopyTo`
- `0x180043c56`: `void __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::CopyTo(class UnBCL::Array<class UnBCL::StringPtr> *,int) const`
- `0x180043ca0`: `void __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::CopyTo(class UnBCL::Array<class UnBCL::StringPtr> *,int) const`
- `0x180043cea`: `void __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::CopyTo(class UnBCL::Array<class UnBCL::StringPtr> *,int) const`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::ArrayList<UnBCL::StringPtr>::CopyTo(__int64 a1, __int64 a2, int a3)
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::CopyTo(class UnBCL::Array<class UnBCL::S"
                         "tringPtr> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::CopyTo(class UnBCL::Array<class UnBCL::S"
                         "tringPtr> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::StringPtr>::CopyTo(class UnBCL::Array<class UnBCL::S"
                         "tringPtr> *,int) const");
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
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(
        v12 + 32LL * (i + a3) + 8 + *(int *)(*(_QWORD *)(v12 + 32LL * (i + a3) + 8) + 4LL),
        *(_QWORD *)(*(int *)(*(_QWORD *)(v11 + 32LL * i + 8) + 4LL) + v11 + 32LL * i + 16));
    }
  }
  return result;
}

```

## disassembly

```asm
0x180043ae4  push    rsi
0x180043ae6  push    rdi
0x180043ae7  push    r14
0x180043ae9  sub     rsp, 30h
0x180043aed  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180043af6  mov     [rsp+48h+arg_0], rbx
0x180043afb  mov     [rsp+48h+arg_10], rbp
0x180043b00  mov     esi, r8d
0x180043b03  mov     r14, rdx
0x180043b06  mov     rdi, rcx
0x180043b09  test    rdx, rdx
0x180043b0c  jz      loc_180043C7C
0x180043b12  test    r8d, r8d
0x180043b15  js      loc_180043C32
0x180043b1b  mov     rax, [rcx-50h]
0x180043b1f  movsxd  rcx, dword ptr [rax+0Ch]
0x180043b23  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180043b27  add     rcx, rdi
0x180043b2a  mov     rax, [rcx]
0x180043b2d  mov     rax, [rax]
0x180043b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b35  mov     ecx, 7FFFFFFFh
0x180043b3a  sub     ecx, esi
0x180043b3c  cmp     ecx, eax
0x180043b3e  jl      loc_180043C32
0x180043b44  mov     rax, [r14]
0x180043b47  mov     rcx, r14
0x180043b4a  mov     rax, [rax]
0x180043b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b52  mov     ebx, eax
0x180043b54  mov     rcx, [rdi-50h]
0x180043b58  movsxd  rcx, dword ptr [rcx+0Ch]
0x180043b5c  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180043b60  add     rcx, rdi
0x180043b63  mov     rdx, [rcx]
0x180043b66  mov     rax, [rdx]
0x180043b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b6e  add     eax, esi
0x180043b70  cmp     eax, ebx
0x180043b72  jg      loc_180043CC6
0x180043b78  mov     rax, [rdi-50h]
0x180043b7c  movsxd  rcx, dword ptr [rax+0Ch]
0x180043b80  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180043b84  add     rcx, rdi
0x180043b87  mov     rax, [rcx]
0x180043b8a  mov     rax, [rax]
0x180043b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b92  test    eax, eax
0x180043b94  jz      loc_180043C1F
0x180043b9a  lea     rcx, [rdi-58h]
0x180043b9e  mov     rax, [rcx]
0x180043ba1  xor     edx, edx
0x180043ba3  mov     rax, [rax+68h]
0x180043ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bac  mov     rbp, rax
0x180043baf  mov     rcx, [r14]
0x180043bb2  mov     rax, [rcx+38h]
0x180043bb6  xor     edx, edx
0x180043bb8  mov     rcx, r14
0x180043bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bc0  mov     r14, rax
0x180043bc3  xor     ebx, ebx
0x180043bc5  mov     rcx, [rdi-50h]
0x180043bc9  movsxd  rcx, dword ptr [rcx+0Ch]
0x180043bcd  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180043bd1  add     rcx, rdi
0x180043bd4  mov     rdx, [rcx]
0x180043bd7  mov     rax, [rdx]
0x180043bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bdf  cmp     ebx, eax
0x180043be1  jge     short loc_180043C1F
0x180043be3  movsxd  r9, ebx
0x180043be6  shl     r9, 5
0x180043bea  add     r9, rbp
0x180043bed  lea     eax, [rbx+rsi]
0x180043bf0  movsxd  r8, eax
0x180043bf3  shl     r8, 5
0x180043bf7  add     r8, r14
0x180043bfa  mov     rax, [r9+8]
0x180043bfe  movsxd  rdx, dword ptr [rax+4]
0x180043c02  mov     rax, [r8+8]
0x180043c06  movsxd  rcx, dword ptr [rax+4]
0x180043c0a  add     r8, 8
0x180043c0e  add     rcx, r8
0x180043c11  mov     rdx, [rdx+r9+10h]
0x180043c16  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x180043c1b  inc     ebx
0x180043c1d  jmp     short loc_180043BC5
0x180043c1f  mov     rbx, [rsp+48h+arg_0]
0x180043c24  mov     rbp, [rsp+48h+arg_10]
0x180043c29  add     rsp, 30h
0x180043c2d  pop     r14
0x180043c2f  pop     rdi
0x180043c30  pop     rsi
0x180043c31  retn
0x180043c32  mov     ecx, 38h ; '8'; unsigned __int64
0x180043c37  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180043c3c  mov     [rsp+48h+arg_18], rax
0x180043c41  test    rax, rax
0x180043c44  jz      short loc_180043C56
0x180043c46  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x180043c4d  mov     rcx, rax; this
0x180043c50  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180043c55  nop
0x180043c56  lea     rdx, aVoidCdeclUnbcl_141; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180043c5d  mov     rcx, rax
0x180043c60  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180043c65  mov     [rsp+48h+pExceptionObject], rax
0x180043c6a  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180043c71  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180043c76  call    _CxxThrowException_0
0x180043c7c  mov     ecx, 38h ; '8'; unsigned __int64
0x180043c81  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180043c86  mov     [rsp+48h+arg_18], rax
0x180043c8b  test    rax, rax
0x180043c8e  jz      short loc_180043CA0
0x180043c90  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x180043c97  mov     rcx, rax; this
0x180043c9a  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180043c9f  nop
0x180043ca0  lea     rdx, aVoidCdeclUnbcl_141; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180043ca7  mov     rcx, rax
0x180043caa  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180043caf  mov     [rsp+48h+pExceptionObject], rax
0x180043cb4  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180043cbb  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180043cc0  call    _CxxThrowException_0
0x180043cc6  mov     ecx, 38h ; '8'; unsigned __int64
0x180043ccb  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180043cd0  mov     [rsp+48h+arg_18], rax
0x180043cd5  test    rax, rax
0x180043cd8  jz      short loc_180043CEA
0x180043cda  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x180043ce1  mov     rcx, rax; this
0x180043ce4  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180043ce9  nop
0x180043cea  lea     rdx, aVoidCdeclUnbcl_141; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180043cf1  mov     rcx, rax
0x180043cf4  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180043cf9  mov     [rsp+48h+pExceptionObject], rax
0x180043cfe  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180043d05  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180043d0a  call    _CxxThrowException_0
```

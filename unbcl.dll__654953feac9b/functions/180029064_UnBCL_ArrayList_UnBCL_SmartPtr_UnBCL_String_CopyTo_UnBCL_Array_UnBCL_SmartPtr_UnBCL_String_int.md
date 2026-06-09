# UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::CopyTo(UnBCL::Array<UnBCL::SmartPtr<UnBCL::String>> *,int)

- ea: `0x180029064`
- end: `0x180029271`
- name: `?CopyTo@?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@UEBAXPEAV?$Array@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@2@H@Z`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180029050`

## callees

- `0x18000225c`
- `0x180002f50`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180029064`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x1800291f1`: `null array argument to ArrayList#CopyTo`
- `0x1800291a7`: `index out of range to ArrayList#CopyTo`
- `0x1800291b7`: `void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL::Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const`
- `0x180029201`: `void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL::Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const`
- `0x18002924b`: `void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL::Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::CopyTo(__int64 a1, __int64 a2, int a3)
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL:"
                         ":Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL:"
                         ":Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::CopyTo(class UnBCL:"
                         ":Array<class UnBCL::SmartPtr<class UnBCL::String> > *,int) const");
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
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(v12 + 16LL * (i + a3), *(_QWORD *)(v11 + 16LL * i + 8));
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029064  push    rsi
0x180029066  push    rdi
0x180029067  push    r14
0x180029069  sub     rsp, 30h
0x18002906d  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180029076  mov     [rsp+48h+arg_0], rbx
0x18002907b  mov     [rsp+48h+arg_10], rbp
0x180029080  mov     esi, r8d
0x180029083  mov     r14, rdx
0x180029086  mov     rdi, rcx
0x180029089  test    rdx, rdx
0x18002908c  jz      loc_1800291DD
0x180029092  test    r8d, r8d
0x180029095  js      loc_180029193
0x18002909b  mov     rax, [rcx-50h]
0x18002909f  movsxd  rcx, dword ptr [rax+0Ch]
0x1800290a3  add     rcx, 0FFFFFFFFFFFFFFB0h
0x1800290a7  add     rcx, rdi
0x1800290aa  mov     rax, [rcx]
0x1800290ad  mov     rax, [rax]
0x1800290b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290b5  mov     ecx, 7FFFFFFFh
0x1800290ba  sub     ecx, esi
0x1800290bc  cmp     ecx, eax
0x1800290be  jl      loc_180029193
0x1800290c4  mov     rax, [r14]
0x1800290c7  mov     rcx, r14
0x1800290ca  mov     rax, [rax]
0x1800290cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290d2  mov     ebx, eax
0x1800290d4  mov     rcx, [rdi-50h]
0x1800290d8  movsxd  rcx, dword ptr [rcx+0Ch]
0x1800290dc  add     rcx, 0FFFFFFFFFFFFFFB0h
0x1800290e0  add     rcx, rdi
0x1800290e3  mov     rdx, [rcx]
0x1800290e6  mov     rax, [rdx]
0x1800290e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290ee  add     eax, esi
0x1800290f0  cmp     eax, ebx
0x1800290f2  jg      loc_180029227
0x1800290f8  mov     rax, [rdi-50h]
0x1800290fc  movsxd  rcx, dword ptr [rax+0Ch]
0x180029100  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180029104  add     rcx, rdi
0x180029107  mov     rax, [rcx]
0x18002910a  mov     rax, [rax]
0x18002910d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029112  test    eax, eax
0x180029114  jz      short loc_180029180
0x180029116  lea     rcx, [rdi-58h]
0x18002911a  mov     rax, [rcx]
0x18002911d  xor     edx, edx
0x18002911f  mov     rax, [rax+68h]
0x180029123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029128  mov     rbp, rax
0x18002912b  mov     rcx, [r14]
0x18002912e  mov     rax, [rcx+38h]
0x180029132  xor     edx, edx
0x180029134  mov     rcx, r14
0x180029137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002913c  mov     r14, rax
0x18002913f  xor     ebx, ebx
0x180029141  mov     rcx, [rdi-50h]
0x180029145  movsxd  rcx, dword ptr [rcx+0Ch]
0x180029149  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18002914d  add     rcx, rdi
0x180029150  mov     rdx, [rcx]
0x180029153  mov     rax, [rdx]
0x180029156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002915b  cmp     ebx, eax
0x18002915d  jge     short loc_180029180
0x18002915f  movsxd  rdx, ebx
0x180029162  add     rdx, rdx
0x180029165  lea     eax, [rbx+rsi]
0x180029168  movsxd  rcx, eax
0x18002916b  shl     rcx, 4
0x18002916f  add     rcx, r14
0x180029172  mov     rdx, [rbp+rdx*8+8]
0x180029177  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002917c  inc     ebx
0x18002917e  jmp     short loc_180029141
0x180029180  mov     rbx, [rsp+48h+arg_0]
0x180029185  mov     rbp, [rsp+48h+arg_10]
0x18002918a  add     rsp, 30h
0x18002918e  pop     r14
0x180029190  pop     rdi
0x180029191  pop     rsi
0x180029192  retn
0x180029193  mov     ecx, 38h ; '8'; unsigned __int64
0x180029198  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002919d  mov     [rsp+48h+arg_18], rax
0x1800291a2  test    rax, rax
0x1800291a5  jz      short loc_1800291B7
0x1800291a7  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x1800291ae  mov     rcx, rax; this
0x1800291b1  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x1800291b6  nop
0x1800291b7  lea     rdx, aVoidCdeclUnbcl_120; "void __cdecl UnBCL::ArrayList<class UnB"...
0x1800291be  mov     rcx, rax
0x1800291c1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800291c6  mov     [rsp+48h+pExceptionObject], rax
0x1800291cb  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x1800291d2  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800291d7  call    _CxxThrowException_0
0x1800291dd  mov     ecx, 38h ; '8'; unsigned __int64
0x1800291e2  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800291e7  mov     [rsp+48h+arg_18], rax
0x1800291ec  test    rax, rax
0x1800291ef  jz      short loc_180029201
0x1800291f1  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x1800291f8  mov     rcx, rax; this
0x1800291fb  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180029200  nop
0x180029201  lea     rdx, aVoidCdeclUnbcl_120; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180029208  mov     rcx, rax
0x18002920b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180029210  mov     [rsp+48h+pExceptionObject], rax
0x180029215  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18002921c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180029221  call    _CxxThrowException_0
0x180029227  mov     ecx, 38h ; '8'; unsigned __int64
0x18002922c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180029231  mov     [rsp+48h+arg_18], rax
0x180029236  test    rax, rax
0x180029239  jz      short loc_18002924B
0x18002923b  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x180029242  mov     rcx, rax; this
0x180029245  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18002924a  nop
0x18002924b  lea     rdx, aVoidCdeclUnbcl_120; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180029252  mov     rcx, rax
0x180029255  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002925a  mov     [rsp+48h+pExceptionObject], rax
0x18002925f  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180029266  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18002926b  call    _CxxThrowException_0
```

# UnBCL::ArrayList<UnBCL::String *>::CopyTo(UnBCL::Array<UnBCL::String *> *,int)

- ea: `0x180017050`
- end: `0x180017253`
- name: `?CopyTo@?$ArrayList@PEAVString@UnBCL@@@UnBCL@@UEBAXPEAV?$Array@PEAVString@UnBCL@@@2@H@Z`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180017030`

## callees

- `0x18000225c`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180017050`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180017199`: `void __cdecl UnBCL::ArrayList<class UnBCL::String *>::CopyTo(class UnBCL::Array<class UnBCL::String *> *,int) const`
- `0x1800171e3`: `void __cdecl UnBCL::ArrayList<class UnBCL::String *>::CopyTo(class UnBCL::Array<class UnBCL::String *> *,int) const`
- `0x18001722d`: `void __cdecl UnBCL::ArrayList<class UnBCL::String *>::CopyTo(class UnBCL::Array<class UnBCL::String *> *,int) const`
- `0x1800171d3`: `null array argument to ArrayList#CopyTo`
- `0x180017189`: `index out of range to ArrayList#CopyTo`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnBCL::ArrayList<UnBCL::String *>::CopyTo(__int64 a1, __int64 a2, int a3)
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::String *>::CopyTo(class UnBCL::Array<class UnBCL::St"
                         "ring *> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::String *>::CopyTo(class UnBCL::Array<class UnBCL::St"
                         "ring *> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::String *>::CopyTo(class UnBCL::Array<class UnBCL::St"
                         "ring *> *,int) const");
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
0x180017050  push    rdi
0x180017052  push    r14
0x180017054  push    r15
0x180017056  sub     rsp, 30h
0x18001705a  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180017063  mov     [rsp+48h+arg_0], rbx
0x180017068  mov     [rsp+48h+arg_10], rsi
0x18001706d  mov     esi, r8d
0x180017070  mov     r14, rdx
0x180017073  mov     rdi, rcx
0x180017076  test    rdx, rdx
0x180017079  jz      loc_1800171BF
0x18001707f  test    r8d, r8d
0x180017082  js      loc_180017175
0x180017088  mov     rax, [rcx-50h]
0x18001708c  movsxd  rcx, dword ptr [rax+0Ch]
0x180017090  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180017094  add     rcx, rdi
0x180017097  mov     rax, [rcx]
0x18001709a  mov     rax, [rax]
0x18001709d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170a2  mov     ecx, 7FFFFFFFh
0x1800170a7  sub     ecx, esi
0x1800170a9  cmp     ecx, eax
0x1800170ab  jl      loc_180017175
0x1800170b1  mov     rax, [r14]
0x1800170b4  mov     rcx, r14
0x1800170b7  mov     rax, [rax]
0x1800170ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170bf  mov     ebx, eax
0x1800170c1  mov     rcx, [rdi-50h]
0x1800170c5  movsxd  rcx, dword ptr [rcx+0Ch]
0x1800170c9  add     rcx, 0FFFFFFFFFFFFFFB0h
0x1800170cd  add     rcx, rdi
0x1800170d0  mov     rdx, [rcx]
0x1800170d3  mov     rax, [rdx]
0x1800170d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170db  add     eax, esi
0x1800170dd  cmp     eax, ebx
0x1800170df  jg      loc_180017209
0x1800170e5  mov     rax, [rdi-50h]
0x1800170e9  movsxd  rcx, dword ptr [rax+0Ch]
0x1800170ed  add     rcx, 0FFFFFFFFFFFFFFB0h
0x1800170f1  add     rcx, rdi
0x1800170f4  mov     rax, [rcx]
0x1800170f7  mov     rax, [rax]
0x1800170fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170ff  test    eax, eax
0x180017101  jz      short loc_180017161
0x180017103  lea     rcx, [rdi-58h]
0x180017107  mov     rax, [rcx]
0x18001710a  xor     edx, edx
0x18001710c  mov     rax, [rax+68h]
0x180017110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017115  mov     r15, rax
0x180017118  mov     rcx, [r14]
0x18001711b  mov     rax, [rcx+38h]
0x18001711f  xor     edx, edx
0x180017121  mov     rcx, r14
0x180017124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017129  mov     r14, rax
0x18001712c  xor     ebx, ebx
0x18001712e  mov     rcx, [rdi-50h]
0x180017132  movsxd  rcx, dword ptr [rcx+0Ch]
0x180017136  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18001713a  add     rcx, rdi
0x18001713d  mov     rdx, [rcx]
0x180017140  mov     rax, [rdx]
0x180017143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017148  cmp     ebx, eax
0x18001714a  jge     short loc_180017161
0x18001714c  movsxd  rdx, ebx
0x18001714f  lea     eax, [rbx+rsi]
0x180017152  movsxd  rcx, eax
0x180017155  mov     rax, [r15+rdx*8]
0x180017159  mov     [r14+rcx*8], rax
0x18001715d  inc     ebx
0x18001715f  jmp     short loc_18001712E
0x180017161  mov     rbx, [rsp+48h+arg_0]
0x180017166  mov     rsi, [rsp+48h+arg_10]
0x18001716b  add     rsp, 30h
0x18001716f  pop     r15
0x180017171  pop     r14
0x180017173  pop     rdi
0x180017174  retn
0x180017175  mov     ecx, 38h ; '8'; unsigned __int64
0x18001717a  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001717f  mov     [rsp+48h+arg_18], rax
0x180017184  test    rax, rax
0x180017187  jz      short loc_180017199
0x180017189  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x180017190  mov     rcx, rax; this
0x180017193  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180017198  nop
0x180017199  lea     rdx, aVoidCdeclUnbcl_172; "void __cdecl UnBCL::ArrayList<class UnB"...
0x1800171a0  mov     rcx, rax
0x1800171a3  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800171a8  mov     [rsp+48h+pExceptionObject], rax
0x1800171ad  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x1800171b4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800171b9  call    _CxxThrowException_0
0x1800171bf  mov     ecx, 38h ; '8'; unsigned __int64
0x1800171c4  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800171c9  mov     [rsp+48h+arg_18], rax
0x1800171ce  test    rax, rax
0x1800171d1  jz      short loc_1800171E3
0x1800171d3  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x1800171da  mov     rcx, rax; this
0x1800171dd  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x1800171e2  nop
0x1800171e3  lea     rdx, aVoidCdeclUnbcl_172; "void __cdecl UnBCL::ArrayList<class UnB"...
0x1800171ea  mov     rcx, rax
0x1800171ed  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800171f2  mov     [rsp+48h+pExceptionObject], rax
0x1800171f7  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x1800171fe  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180017203  call    _CxxThrowException_0
0x180017209  mov     ecx, 38h ; '8'; unsigned __int64
0x18001720e  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180017213  mov     [rsp+48h+arg_18], rax
0x180017218  test    rax, rax
0x18001721b  jz      short loc_18001722D
0x18001721d  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x180017224  mov     rcx, rax; this
0x180017227  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18001722c  nop
0x18001722d  lea     rdx, aVoidCdeclUnbcl_172; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180017234  mov     rcx, rax
0x180017237  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001723c  mov     [rsp+48h+pExceptionObject], rax
0x180017241  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180017248  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001724d  call    _CxxThrowException_0
```

# UnBCL::ArrayList<UnBCL::String *>::Copy(UnBCL::ArrayList<UnBCL::String *> const *,int,UnBCL::ArrayList<UnBCL::String *> *,int,int)

- ea: `0x180016570`
- end: `0x180016710`
- name: `?Copy@?$ArrayList@PEAVString@UnBCL@@@UnBCL@@SAXPEBV12@HPEAV12@HH@Z`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180016720`

## callees

- `0x18000225c`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180016570`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x180016694`: `void __cdecl UnBCL::ArrayList<class UnBCL::String *>::Copy(const class UnBCL::ArrayList<class UnBCL::String *> *,int,class UnBCL::ArrayList<class UnBCL::String *> *,int,int)`
- `0x1800166e4`: `void __cdecl UnBCL::ArrayList<class UnBCL::String *>::Copy(const class UnBCL::ArrayList<class UnBCL::String *> *,int,class UnBCL::ArrayList<class UnBCL::String *> *,int,int)`
- `0x1800166d4`: `null src or dest list to ArrayList<T>::Copy`
- `0x180016684`: `position params out of range to ArrayList::Copy`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnBCL::ArrayList<UnBCL::String *>::Copy(__int64 a1, int a2, __int64 a3, int a4, int a5)
{
  __int64 (__fastcall ***v9)(_QWORD); // rcx
  int v10; // eax
  int v11; // r14d
  __int64 (__fastcall ***v12)(_QWORD); // rcx
  __int64 result; // rax
  int i; // r13d
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, _QWORD); // rbx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  UnBCL::ArgumentOutOfRangeException *v19; // rax
  UnBCL::ArgumentNullException *v20; // rax
  __int64 pExceptionObject; // [rsp+80h] [rbp+8h] BYREF

  if ( !a1 || !a3 )
  {
    v20 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    if ( v20 )
      v20 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v20,
                                              L"null src or dest list to ArrayList<T>::Copy");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v20,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::String *>::Copy(const class UnBCL::ArrayList<class U"
                         "nBCL::String *> *,int,class UnBCL::ArrayList<class UnBCL::String *> *,int,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a2 < 0
    || a4 < 0
    || (v9 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL),
        v10 = (**v9)(v9),
        v11 = a5,
        a2 + a5 > v10)
    || (v12 = (__int64 (__fastcall ***)(_QWORD))(a3 + *(int *)(*(_QWORD *)(a3 + 8) + 12LL) + 8LL),
        result = (**v12)(v12),
        a4 + v11 > (int)result) )
  {
    v19 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    if ( v19 )
      v19 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v19,
                                                    L"position params out of range to ArrayList::Copy");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v19,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::String *>::Copy(const class UnBCL::ArrayList<class U"
                         "nBCL::String *> *,int,class UnBCL::ArrayList<class UnBCL::String *> *,int,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  for ( i = 0; i < v11; ++i )
  {
    v15 = *(int *)(*(_QWORD *)(a3 + 8) + 16LL);
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)(v15 + a3 + 8) + 32LL);
    v17 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
    v18 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 16LL))(v17, (unsigned int)(a2 + i));
    result = v16(v15 + a3 + 8, (unsigned int)(a4 + i), *v18);
  }
  return result;
}

```

## disassembly

```asm
0x180016570  push    rbx
0x180016572  push    rbp
0x180016573  push    rsi
0x180016574  push    rdi
0x180016575  push    r12
0x180016577  push    r13
0x180016579  push    r14
0x18001657b  push    r15
0x18001657d  sub     rsp, 38h
0x180016581  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x18001658a  mov     r15d, r9d
0x18001658d  mov     rsi, r8
0x180016590  mov     r12d, edx
0x180016593  mov     rbp, rcx
0x180016596  test    rcx, rcx
0x180016599  jz      loc_1800166C0
0x18001659f  test    r8, r8
0x1800165a2  jz      loc_1800166C0
0x1800165a8  test    edx, edx
0x1800165aa  js      loc_180016670
0x1800165b0  test    r9d, r9d
0x1800165b3  js      loc_180016670
0x1800165b9  mov     rax, [rcx+8]
0x1800165bd  movsxd  rcx, dword ptr [rax+0Ch]
0x1800165c1  add     rcx, 8
0x1800165c5  add     rcx, rbp
0x1800165c8  mov     rax, [rcx]
0x1800165cb  mov     rax, [rax]
0x1800165ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165d3  mov     r14d, [rsp+78h+arg_20]
0x1800165db  lea     ecx, [r12+r14]
0x1800165df  cmp     ecx, eax
0x1800165e1  jg      loc_180016670
0x1800165e7  mov     rax, [rsi+8]
0x1800165eb  movsxd  rcx, dword ptr [rax+0Ch]
0x1800165ef  add     rcx, 8
0x1800165f3  add     rcx, rsi
0x1800165f6  mov     rax, [rcx]
0x1800165f9  mov     rax, [rax]
0x1800165fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016601  lea     ecx, [r15+r14]
0x180016605  cmp     ecx, eax
0x180016607  jg      short loc_180016670
0x180016609  xor     r13d, r13d
0x18001660c  test    r14d, r14d
0x18001660f  jle     short loc_18001665F
0x180016611  mov     rax, [rsi+8]
0x180016615  movsxd  rdi, dword ptr [rax+10h]
0x180016619  mov     rax, [rdi+rsi+8]
0x18001661e  mov     rbx, [rax+20h]
0x180016622  mov     rax, [rbp+8]
0x180016626  movsxd  rcx, dword ptr [rax+10h]
0x18001662a  add     rcx, 8
0x18001662e  add     rcx, rbp
0x180016631  mov     r8, [rcx]
0x180016634  lea     edx, [r12+r13]
0x180016638  mov     rax, [r8+10h]
0x18001663c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016641  lea     edx, [r15+r13]
0x180016645  mov     r8, [rax]
0x180016648  lea     rcx, [rsi+8]
0x18001664c  add     rcx, rdi
0x18001664f  mov     rax, rbx
0x180016652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016657  inc     r13d
0x18001665a  cmp     r13d, r14d
0x18001665d  jl      short loc_180016611
0x18001665f  add     rsp, 38h
0x180016663  pop     r15
0x180016665  pop     r14
0x180016667  pop     r13
0x180016669  pop     r12
0x18001666b  pop     rdi
0x18001666c  pop     rsi
0x18001666d  pop     rbp
0x18001666e  pop     rbx
0x18001666f  retn
0x180016670  mov     ecx, 38h ; '8'; unsigned __int64
0x180016675  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001667a  mov     [rsp+78h+var_50], rax
0x18001667f  test    rax, rax
0x180016682  jz      short loc_180016694
0x180016684  lea     rdx, aPositionParams; "position params out of range to ArrayLi"...
0x18001668b  mov     rcx, rax; this
0x18001668e  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180016693  nop
0x180016694  lea     rdx, aVoidCdeclUnbcl_115; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18001669b  mov     rcx, rax
0x18001669e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800166a3  mov     [rsp+78h+pExceptionObject], rax
0x1800166ab  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x1800166b2  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800166ba  call    _CxxThrowException_0
0x1800166c0  mov     ecx, 38h ; '8'; unsigned __int64
0x1800166c5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800166ca  mov     [rsp+78h+var_50], rax
0x1800166cf  test    rax, rax
0x1800166d2  jz      short loc_1800166E4
0x1800166d4  lea     rdx, aNullSrcOrDestL; "null src or dest list to ArrayList<T>::"...
0x1800166db  mov     rcx, rax; this
0x1800166de  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x1800166e3  nop
0x1800166e4  lea     rdx, aVoidCdeclUnbcl_115; "void __cdecl UnBCL::ArrayList<class UnB"...
0x1800166eb  mov     rcx, rax
0x1800166ee  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800166f3  mov     [rsp+78h+pExceptionObject], rax
0x1800166fb  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180016702  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001670a  call    _CxxThrowException_0
```

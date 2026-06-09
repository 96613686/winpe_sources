# UnBCL::ArrayList<ushort>::Copy(UnBCL::ArrayList<ushort> const *,int,UnBCL::ArrayList<ushort> *,int,int)

- ea: `0x1800163c0`
- end: `0x18001652e`
- name: `?Copy@?$ArrayList@G@UnBCL@@SAXPEBV12@HPEAV12@HH@Z`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180016540`

## callees

- `0x18000225c`
- `0x180002276`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x1800163c0`
- `0x1800477d0`
- `0x18006f010`

## string_xrefs

- `0x1800164f8`: `null src or dest list to ArrayList<T>::Copy`
- `0x1800164ae`: `position params out of range to ArrayList::Copy`
- `0x1800164be`: `void __cdecl UnBCL::ArrayList<unsigned short>::Copy(const class UnBCL::ArrayList<unsigned short> *,int,class UnBCL::ArrayList<unsigned short> *,int,int)`
- `0x180016508`: `void __cdecl UnBCL::ArrayList<unsigned short>::Copy(const class UnBCL::ArrayList<unsigned short> *,int,class UnBCL::ArrayList<unsigned short> *,int,int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall UnBCL::ArrayList<unsigned short>::Copy(_QWORD *a1, int a2, _QWORD *a3, int a4, int a5)
{
  __int64 (__fastcall ***v9)(_QWORD); // rcx
  int v10; // eax
  __int64 v11; // rsi
  int (__fastcall ***v12)(_QWORD); // rcx
  __int64 (__fastcall *v13)(_QWORD *, _QWORD); // rdi
  const void *v14; // rbx
  void *v15; // rax
  UnBCL::ArgumentOutOfRangeException *v17; // rax
  UnBCL::ArgumentNullException *v18; // rax
  __int64 pExceptionObject; // [rsp+70h] [rbp+8h] BYREF

  if ( !a1 || !a3 )
  {
    v18 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    if ( v18 )
      v18 = (UnBCL::ArgumentNullException *)UnBCL::ArgumentNullException::ArgumentNullException(
                                              v18,
                                              L"null src or dest list to ArrayList<T>::Copy");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v18,
                         "void __cdecl UnBCL::ArrayList<unsigned short>::Copy(const class UnBCL::ArrayList<unsigned short"
                         "> *,int,class UnBCL::ArrayList<unsigned short> *,int,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a2 < 0
    || a4 < 0
    || (v9 = (__int64 (__fastcall ***)(_QWORD))((char *)a1 + *(int *)(a1[1] + 12LL) + 8),
        v10 = (**v9)(v9),
        v11 = a5,
        a2 + a5 > v10)
    || (v12 = (int (__fastcall ***)(_QWORD))((char *)a3 + *(int *)(a3[1] + 12LL) + 8), a4 + (int)v11 > (**v12)(v12)) )
  {
    v17 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    if ( v17 )
      v17 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v17,
                                                    L"position params out of range to ArrayList::Copy");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v17,
                         "void __cdecl UnBCL::ArrayList<unsigned short>::Copy(const class UnBCL::ArrayList<unsigned short"
                         "> *,int,class UnBCL::ArrayList<unsigned short> *,int,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v13 = *(__int64 (__fastcall **)(_QWORD *, _QWORD))(*a3 + 112LL);
  v14 = (const void *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 104LL))(a1, (unsigned int)a2);
  v15 = (void *)v13(a3, (unsigned int)a4);
  return memcpy_0(v15, v14, 2 * v11);
}

```

## disassembly

```asm
0x1800163c0  push    rbx
0x1800163c2  push    rsi
0x1800163c3  push    rdi
0x1800163c4  push    r12
0x1800163c6  push    r14
0x1800163c8  push    r15
0x1800163ca  sub     rsp, 38h
0x1800163ce  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800163d7  mov     r15d, r9d
0x1800163da  mov     r14, r8
0x1800163dd  mov     r12d, edx
0x1800163e0  mov     rbx, rcx
0x1800163e3  test    rcx, rcx
0x1800163e6  jz      loc_1800164E4
0x1800163ec  test    r8, r8
0x1800163ef  jz      loc_1800164E4
0x1800163f5  test    edx, edx
0x1800163f7  js      loc_18001649A
0x1800163fd  test    r9d, r9d
0x180016400  js      loc_18001649A
0x180016406  mov     rax, [rcx+8]
0x18001640a  movsxd  rcx, dword ptr [rax+0Ch]
0x18001640e  add     rcx, 8
0x180016412  add     rcx, rbx
0x180016415  mov     rax, [rcx]
0x180016418  mov     rax, [rax]
0x18001641b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016420  movsxd  rsi, [rsp+68h+arg_20]
0x180016428  lea     ecx, [r12+rsi]
0x18001642c  cmp     ecx, eax
0x18001642e  jg      short loc_18001649A
0x180016430  mov     rax, [r14+8]
0x180016434  movsxd  rcx, dword ptr [rax+0Ch]
0x180016438  add     rcx, 8
0x18001643c  add     rcx, r14
0x18001643f  mov     rax, [rcx]
0x180016442  mov     rax, [rax]
0x180016445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001644a  lea     ecx, [r15+rsi]
0x18001644e  cmp     ecx, eax
0x180016450  jg      short loc_18001649A
0x180016452  mov     rax, [rbx]
0x180016455  mov     rcx, [r14]
0x180016458  mov     rdi, [rcx+70h]
0x18001645c  add     rsi, rsi
0x18001645f  mov     edx, r12d
0x180016462  mov     rcx, rbx
0x180016465  mov     rax, [rax+68h]
0x180016469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001646e  mov     rbx, rax
0x180016471  mov     edx, r15d
0x180016474  mov     rcx, r14
0x180016477  mov     rax, rdi
0x18001647a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001647f  mov     rcx, rax; void *
0x180016482  mov     r8, rsi; Size
0x180016485  mov     rdx, rbx; Src
0x180016488  add     rsp, 38h
0x18001648c  pop     r15
0x18001648e  pop     r14
0x180016490  pop     r12
0x180016492  pop     rdi
0x180016493  pop     rsi
0x180016494  pop     rbx
0x180016495  jmp     memcpy_0
0x18001649a  mov     ecx, 38h ; '8'; unsigned __int64
0x18001649f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800164a4  mov     [rsp+68h+var_40], rax
0x1800164a9  test    rax, rax
0x1800164ac  jz      short loc_1800164BE
0x1800164ae  lea     rdx, aPositionParams; "position params out of range to ArrayLi"...
0x1800164b5  mov     rcx, rax; this
0x1800164b8  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x1800164bd  nop
0x1800164be  lea     rdx, aVoidCdeclUnbcl_28; "void __cdecl UnBCL::ArrayList<unsigned "...
0x1800164c5  mov     rcx, rax
0x1800164c8  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800164cd  mov     [rsp+68h+pExceptionObject], rax
0x1800164d2  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x1800164d9  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800164de  call    _CxxThrowException_0
0x1800164e4  mov     ecx, 38h ; '8'; unsigned __int64
0x1800164e9  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800164ee  mov     [rsp+68h+var_40], rax
0x1800164f3  test    rax, rax
0x1800164f6  jz      short loc_180016508
0x1800164f8  lea     rdx, aNullSrcOrDestL; "null src or dest list to ArrayList<T>::"...
0x1800164ff  mov     rcx, rax; this
0x180016502  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180016507  nop
0x180016508  lea     rdx, aVoidCdeclUnbcl_28; "void __cdecl UnBCL::ArrayList<unsigned "...
0x18001650f  mov     rcx, rax
0x180016512  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180016517  mov     [rsp+68h+pExceptionObject], rax
0x18001651c  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180016523  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180016528  call    _CxxThrowException_0
```

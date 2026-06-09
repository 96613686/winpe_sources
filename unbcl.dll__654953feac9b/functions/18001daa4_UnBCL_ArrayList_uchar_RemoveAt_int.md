# UnBCL::ArrayList<uchar>::RemoveAt(int)

- ea: `0x18001daa4`
- end: `0x18001dbe1`
- name: `?RemoveAt@?$ArrayList@E@UnBCL@@UEAAXH@Z`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001da90`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x180009b40`
- `0x180009e7c`
- `0x18001daa4`
- `0x1800477d0`
- `0x18006f010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001db40`
- `msvcrt!memmove_s` at `0x18001db40`

## string_xrefs

- `0x18001db95`: `index out of range to ArrayList#RemoveAt`
- `0x18001dba5`: `void __cdecl UnBCL::ArrayList<unsigned char>::RemoveAt(int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::ArrayList<unsigned char>::RemoveAt(__int64 a1, int a2)
{
  unsigned __int64 v2; // rdi
  int (__fastcall ***v4)(_QWORD); // rcx
  __int64 v5; // rax
  __int64 *v6; // rbx
  unsigned __int64 v7; // rcx
  _QWORD *v8; // rbx
  unsigned __int64 v9; // rdx
  rsize_t v10; // rdx
  UnBCL::ArgumentOutOfRangeException *v11; // rax
  __int64 pExceptionObject; // [rsp+50h] [rbp+18h] BYREF
  UnBCL::ArgumentOutOfRangeException *v14; // [rsp+58h] [rbp+20h]

  v2 = a2;
  if ( a2 < 0
    || (v4 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 104) + 12LL) - 104LL), a2 >= (**v4)(v4)) )
  {
    v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v14 = v11;
    if ( v11 )
      v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v11,
                                                    L"index out of range to ArrayList#RemoveAt");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::ArrayList<unsigned char>::RemoveAt(int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  ++*(_DWORD *)(a1 - 88);
  LODWORD(v5) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 - 112) + 32LL))(a1 - 112);
  v6 = (__int64 *)(a1 - 96);
  if ( (_DWORD)v5 )
  {
    v5 = *v6;
    if ( v2 >= *(_QWORD *)(*v6 + 8) )
      goto LABEL_15;
  }
  v7 = v2 + 1;
  if ( v2 + 1 < v2 )
    goto LABEL_15;
  if ( v2 == -1 )
    goto LABEL_15;
  v8 = (_QWORD *)*v6;
  v9 = v8[1];
  if ( v7 > v9 )
    goto LABEL_15;
  v10 = v9 - v7;
  if ( !v10 )
    goto LABEL_14;
  LODWORD(v5) = memmove_s((void *const)(*v8 + v2), v10, (const void *const)(*v8 + v7), v10);
  switch ( (_DWORD)v5 )
  {
    case 0:
      goto LABEL_14;
    case 0xC:
      ATL::AtlThrowImpl(-2147024882);
    case 0x16:
    case 0x22:
LABEL_15:
      ATL::AtlThrowImpl(-2147024809);
  }
  if ( (_DWORD)v5 != 80 )
    ATL::AtlThrowImpl(-2147467259);
LABEL_14:
  --v8[1];
  return v5;
}

```

## disassembly

```asm
0x18001daa4  push    rdi
0x18001daa6  sub     rsp, 30h
0x18001daaa  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001dab3  mov     [rsp+38h+arg_0], rbx
0x18001dab8  mov     [rsp+38h+arg_8], rsi
0x18001dabd  movsxd  rdi, edx
0x18001dac0  mov     rbx, rcx
0x18001dac3  test    edx, edx
0x18001dac5  js      loc_18001DB81
0x18001dacb  mov     rax, [rcx-68h]
0x18001dacf  movsxd  rcx, dword ptr [rax+0Ch]
0x18001dad3  add     rcx, 0FFFFFFFFFFFFFF98h
0x18001dad7  add     rcx, rbx
0x18001dada  mov     rax, [rcx]
0x18001dadd  mov     rax, [rax]
0x18001dae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dae5  cmp     edi, eax
0x18001dae7  jge     loc_18001DB81
0x18001daed  inc     dword ptr [rbx-58h]
0x18001daf0  mov     rax, [rbx-70h]
0x18001daf4  lea     rcx, [rbx-70h]
0x18001daf8  mov     rax, [rax+20h]
0x18001dafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db01  add     rbx, 0FFFFFFFFFFFFFFA0h
0x18001db05  test    eax, eax
0x18001db07  jz      short loc_18001DB12
0x18001db09  mov     rax, [rbx]
0x18001db0c  cmp     rdi, [rax+8]
0x18001db10  jnb     short loc_18001DB76
0x18001db12  lea     rcx, [rdi+1]
0x18001db16  cmp     rcx, rdi
0x18001db19  jb      short loc_18001DB76
0x18001db1b  cmp     rcx, 1
0x18001db1f  jb      short loc_18001DB76
0x18001db21  mov     rbx, [rbx]
0x18001db24  mov     rdx, [rbx+8]
0x18001db28  cmp     rcx, rdx
0x18001db2b  ja      short loc_18001DB76
0x18001db2d  sub     rdx, rcx; DestinationSize
0x18001db30  jz      short loc_18001DB62
0x18001db32  mov     rax, [rbx]
0x18001db35  lea     r8, [rax+rcx]; Source
0x18001db39  lea     rcx, [rax+rdi]; Destination
0x18001db3d  mov     r9, rdx; SourceSize
0x18001db40  call    cs:__imp_memmove_s
0x18001db46  test    eax, eax
0x18001db48  jz      short loc_18001DB62
0x18001db4a  cmp     eax, 0Ch
0x18001db4d  jz      loc_18001DBD6
0x18001db53  cmp     eax, 16h
0x18001db56  jz      short loc_18001DB76
0x18001db58  cmp     eax, 22h ; '"'
0x18001db5b  jz      short loc_18001DB76
0x18001db5d  cmp     eax, 50h ; 'P'
0x18001db60  jnz     short loc_18001DBCB
0x18001db62  dec     qword ptr [rbx+8]
0x18001db66  mov     rbx, [rsp+38h+arg_0]
0x18001db6b  mov     rsi, [rsp+38h+arg_8]
0x18001db70  add     rsp, 30h
0x18001db74  pop     rdi
0x18001db75  retn
0x18001db76  mov     ecx, 80070057h; int
0x18001db7b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001db81  mov     ecx, 38h ; '8'; unsigned __int64
0x18001db86  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001db8b  mov     [rsp+38h+arg_18], rax
0x18001db90  test    rax, rax
0x18001db93  jz      short loc_18001DBA5
0x18001db95  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x18001db9c  mov     rcx, rax; this
0x18001db9f  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18001dba4  nop
0x18001dba5  lea     rdx, aVoidCdeclUnbcl_132; "void __cdecl UnBCL::ArrayList<unsigned "...
0x18001dbac  mov     rcx, rax
0x18001dbaf  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001dbb4  mov     [rsp+38h+pExceptionObject], rax
0x18001dbb9  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18001dbc0  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18001dbc5  call    _CxxThrowException_0
0x18001dbcb  mov     ecx, 80004005h; int
0x18001dbd0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001dbd6  mov     ecx, 8007000Eh; int
0x18001dbdb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

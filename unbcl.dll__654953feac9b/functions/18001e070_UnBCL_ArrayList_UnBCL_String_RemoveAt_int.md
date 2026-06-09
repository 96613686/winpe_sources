# UnBCL::ArrayList<UnBCL::String *>::RemoveAt(int)

- ea: `0x18001e070`
- end: `0x18001e1dc`
- name: `?RemoveAt@?$ArrayList@PEAVString@UnBCL@@@UnBCL@@UEAAXH@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001e050`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x180009b40`
- `0x180009e7c`
- `0x18001e070`
- `0x1800477d0`
- `0x18006f010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001e13b`
- `msvcrt!memmove_s` at `0x18001e13b`

## string_xrefs

- `0x18001e1a0`: `void __cdecl UnBCL::ArrayList<class UnBCL::String *>::RemoveAt(int)`
- `0x18001e190`: `index out of range to ArrayList#RemoveAt`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::ArrayList<UnBCL::String *>::RemoveAt(__int64 a1, int a2)
{
  unsigned __int64 v2; // rdi
  int (__fastcall ***v4)(_QWORD); // rcx
  __int64 v5; // rax
  __int64 *v6; // rcx
  __int64 (__fastcall ***v7)(_QWORD, __int64); // rcx
  unsigned __int64 v8; // rcx
  _QWORD *v9; // rbx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  UnBCL::ArgumentOutOfRangeException *v12; // rax
  __int64 pExceptionObject; // [rsp+50h] [rbp+18h] BYREF
  UnBCL::ArgumentOutOfRangeException *v15; // [rsp+58h] [rbp+20h]

  v2 = a2;
  if ( a2 < 0
    || (v4 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 104) + 12LL) - 104LL), a2 >= (**v4)(v4)) )
  {
    v12 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v15 = v12;
    if ( v12 )
      v12 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v12,
                                                    L"index out of range to ArrayList#RemoveAt");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::String *>::RemoveAt(int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  ++*(_DWORD *)(a1 - 88);
  LODWORD(v5) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 - 112) + 32LL))(a1 - 112);
  if ( (_DWORD)v5 )
  {
    v6 = *(__int64 **)(a1 - 96);
    if ( v2 >= v6[1] )
      goto LABEL_18;
    v5 = *v6;
    if ( *(_QWORD *)(*v6 + 8 * v2) )
    {
      _mm_lfence();
      v5 = *v6;
      v7 = *(__int64 (__fastcall ****)(_QWORD, __int64))(*v6 + 8 * v2);
      if ( v7 )
        LODWORD(v5) = (**v7)(v7, 1);
    }
  }
  v8 = v2 + 1;
  if ( v2 + 1 < v2 )
    goto LABEL_18;
  if ( v2 == -1 )
    goto LABEL_18;
  v9 = *(_QWORD **)(a1 - 96);
  v10 = v9[1];
  if ( v8 > v10 )
    goto LABEL_18;
  v11 = v10 - v8;
  if ( !v11 )
    goto LABEL_17;
  LODWORD(v5) = memmove_s((void *const)(*v9 + 8 * v2), 8 * v11, (const void *const)(*v9 + 8 * v8), 8 * v11);
  switch ( (_DWORD)v5 )
  {
    case 0:
      goto LABEL_17;
    case 0xC:
      ATL::AtlThrowImpl(-2147024882);
    case 0x16:
    case 0x22:
LABEL_18:
      ATL::AtlThrowImpl(-2147024809);
  }
  if ( (_DWORD)v5 != 80 )
    ATL::AtlThrowImpl(-2147467259);
LABEL_17:
  --v9[1];
  return v5;
}

```

## disassembly

```asm
0x18001e070  push    rdi
0x18001e072  sub     rsp, 30h
0x18001e076  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001e07f  mov     [rsp+38h+arg_0], rbx
0x18001e084  mov     [rsp+38h+arg_8], rsi
0x18001e089  movsxd  rdi, edx
0x18001e08c  mov     rbx, rcx
0x18001e08f  test    edx, edx
0x18001e091  js      loc_18001E17C
0x18001e097  mov     rax, [rcx-68h]
0x18001e09b  movsxd  rcx, dword ptr [rax+0Ch]
0x18001e09f  add     rcx, 0FFFFFFFFFFFFFF98h
0x18001e0a3  add     rcx, rbx
0x18001e0a6  mov     rax, [rcx]
0x18001e0a9  mov     rax, [rax]
0x18001e0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0b1  cmp     edi, eax
0x18001e0b3  jge     loc_18001E17C
0x18001e0b9  inc     dword ptr [rbx-58h]
0x18001e0bc  mov     rax, [rbx-70h]
0x18001e0c0  lea     rcx, [rbx-70h]
0x18001e0c4  mov     rax, [rax+20h]
0x18001e0c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0cd  test    eax, eax
0x18001e0cf  jz      short loc_18001E108
0x18001e0d1  mov     rcx, [rbx-60h]
0x18001e0d5  cmp     rdi, [rcx+8]
0x18001e0d9  jnb     loc_18001E171
0x18001e0df  mov     rax, [rcx]
0x18001e0e2  cmp     qword ptr [rax+rdi*8], 0
0x18001e0e7  jz      short loc_18001E108
0x18001e0e9  lfence
0x18001e0ec  mov     rax, [rcx]
0x18001e0ef  mov     rcx, [rax+rdi*8]
0x18001e0f3  test    rcx, rcx
0x18001e0f6  jz      short loc_18001E108
0x18001e0f8  mov     rax, [rcx]
0x18001e0fb  mov     edx, 1
0x18001e100  mov     rax, [rax]
0x18001e103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e108  lea     rcx, [rdi+1]
0x18001e10c  cmp     rcx, rdi
0x18001e10f  jb      short loc_18001E171
0x18001e111  cmp     rcx, 1
0x18001e115  jb      short loc_18001E171
0x18001e117  mov     rbx, [rbx-60h]
0x18001e11b  mov     rdx, [rbx+8]
0x18001e11f  cmp     rcx, rdx
0x18001e122  ja      short loc_18001E171
0x18001e124  sub     rdx, rcx
0x18001e127  jz      short loc_18001E15D
0x18001e129  mov     rax, [rbx]
0x18001e12c  shl     rdx, 3; DestinationSize
0x18001e130  lea     r8, [rax+rcx*8]; Source
0x18001e134  lea     rcx, [rax+rdi*8]; Destination
0x18001e138  mov     r9, rdx; SourceSize
0x18001e13b  call    cs:__imp_memmove_s
0x18001e141  test    eax, eax
0x18001e143  jz      short loc_18001E15D
0x18001e145  cmp     eax, 0Ch
0x18001e148  jz      loc_18001E1D1
0x18001e14e  cmp     eax, 16h
0x18001e151  jz      short loc_18001E171
0x18001e153  cmp     eax, 22h ; '"'
0x18001e156  jz      short loc_18001E171
0x18001e158  cmp     eax, 50h ; 'P'
0x18001e15b  jnz     short loc_18001E1C6
0x18001e15d  dec     qword ptr [rbx+8]
0x18001e161  mov     rbx, [rsp+38h+arg_0]
0x18001e166  mov     rsi, [rsp+38h+arg_8]
0x18001e16b  add     rsp, 30h
0x18001e16f  pop     rdi
0x18001e170  retn
0x18001e171  mov     ecx, 80070057h; int
0x18001e176  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e17c  mov     ecx, 38h ; '8'; unsigned __int64
0x18001e181  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001e186  mov     [rsp+38h+arg_18], rax
0x18001e18b  test    rax, rax
0x18001e18e  jz      short loc_18001E1A0
0x18001e190  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x18001e197  mov     rcx, rax; this
0x18001e19a  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18001e19f  nop
0x18001e1a0  lea     rdx, aVoidCdeclUnbcl_18; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18001e1a7  mov     rcx, rax
0x18001e1aa  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001e1af  mov     [rsp+38h+pExceptionObject], rax
0x18001e1b4  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18001e1bb  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18001e1c0  call    _CxxThrowException_0
0x18001e1c6  mov     ecx, 80004005h; int
0x18001e1cb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e1d1  mov     ecx, 8007000Eh; int
0x18001e1d6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

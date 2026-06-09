# UnBCL::ArrayList<UnBCL::Object *>::RemoveAt(int)

- ea: `0x18001ded4`
- end: `0x18001e040`
- name: `?RemoveAt@?$ArrayList@PEAVObject@UnBCL@@@UnBCL@@UEAAXH@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001dec0`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x180009b40`
- `0x180009e7c`
- `0x18001ded4`
- `0x1800477d0`
- `0x18006f010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001df9f`
- `msvcrt!memmove_s` at `0x18001df9f`

## string_xrefs

- `0x18001dff4`: `index out of range to ArrayList#RemoveAt`
- `0x18001e004`: `void __cdecl UnBCL::ArrayList<class UnBCL::Object *>::RemoveAt(int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::ArrayList<UnBCL::Object *>::RemoveAt(__int64 a1, int a2)
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
                         "void __cdecl UnBCL::ArrayList<class UnBCL::Object *>::RemoveAt(int)");
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
0x18001ded4  push    rdi
0x18001ded6  sub     rsp, 30h
0x18001deda  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001dee3  mov     [rsp+38h+arg_0], rbx
0x18001dee8  mov     [rsp+38h+arg_8], rsi
0x18001deed  movsxd  rdi, edx
0x18001def0  mov     rbx, rcx
0x18001def3  test    edx, edx
0x18001def5  js      loc_18001DFE0
0x18001defb  mov     rax, [rcx-68h]
0x18001deff  movsxd  rcx, dword ptr [rax+0Ch]
0x18001df03  add     rcx, 0FFFFFFFFFFFFFF98h
0x18001df07  add     rcx, rbx
0x18001df0a  mov     rax, [rcx]
0x18001df0d  mov     rax, [rax]
0x18001df10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df15  cmp     edi, eax
0x18001df17  jge     loc_18001DFE0
0x18001df1d  inc     dword ptr [rbx-58h]
0x18001df20  mov     rax, [rbx-70h]
0x18001df24  lea     rcx, [rbx-70h]
0x18001df28  mov     rax, [rax+20h]
0x18001df2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df31  test    eax, eax
0x18001df33  jz      short loc_18001DF6C
0x18001df35  mov     rcx, [rbx-60h]
0x18001df39  cmp     rdi, [rcx+8]
0x18001df3d  jnb     loc_18001DFD5
0x18001df43  mov     rax, [rcx]
0x18001df46  cmp     qword ptr [rax+rdi*8], 0
0x18001df4b  jz      short loc_18001DF6C
0x18001df4d  lfence
0x18001df50  mov     rax, [rcx]
0x18001df53  mov     rcx, [rax+rdi*8]
0x18001df57  test    rcx, rcx
0x18001df5a  jz      short loc_18001DF6C
0x18001df5c  mov     rax, [rcx]
0x18001df5f  mov     edx, 1
0x18001df64  mov     rax, [rax]
0x18001df67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df6c  lea     rcx, [rdi+1]
0x18001df70  cmp     rcx, rdi
0x18001df73  jb      short loc_18001DFD5
0x18001df75  cmp     rcx, 1
0x18001df79  jb      short loc_18001DFD5
0x18001df7b  mov     rbx, [rbx-60h]
0x18001df7f  mov     rdx, [rbx+8]
0x18001df83  cmp     rcx, rdx
0x18001df86  ja      short loc_18001DFD5
0x18001df88  sub     rdx, rcx
0x18001df8b  jz      short loc_18001DFC1
0x18001df8d  mov     rax, [rbx]
0x18001df90  shl     rdx, 3; DestinationSize
0x18001df94  lea     r8, [rax+rcx*8]; Source
0x18001df98  lea     rcx, [rax+rdi*8]; Destination
0x18001df9c  mov     r9, rdx; SourceSize
0x18001df9f  call    cs:__imp_memmove_s
0x18001dfa5  test    eax, eax
0x18001dfa7  jz      short loc_18001DFC1
0x18001dfa9  cmp     eax, 0Ch
0x18001dfac  jz      loc_18001E035
0x18001dfb2  cmp     eax, 16h
0x18001dfb5  jz      short loc_18001DFD5
0x18001dfb7  cmp     eax, 22h ; '"'
0x18001dfba  jz      short loc_18001DFD5
0x18001dfbc  cmp     eax, 50h ; 'P'
0x18001dfbf  jnz     short loc_18001E02A
0x18001dfc1  dec     qword ptr [rbx+8]
0x18001dfc5  mov     rbx, [rsp+38h+arg_0]
0x18001dfca  mov     rsi, [rsp+38h+arg_8]
0x18001dfcf  add     rsp, 30h
0x18001dfd3  pop     rdi
0x18001dfd4  retn
0x18001dfd5  mov     ecx, 80070057h; int
0x18001dfda  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001dfe0  mov     ecx, 38h ; '8'; unsigned __int64
0x18001dfe5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001dfea  mov     [rsp+38h+arg_18], rax
0x18001dfef  test    rax, rax
0x18001dff2  jz      short loc_18001E004
0x18001dff4  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x18001dffb  mov     rcx, rax; this
0x18001dffe  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18001e003  nop
0x18001e004  lea     rdx, aVoidCdeclUnbcl_12; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18001e00b  mov     rcx, rax
0x18001e00e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001e013  mov     [rsp+38h+pExceptionObject], rax
0x18001e018  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18001e01f  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18001e024  call    _CxxThrowException_0
0x18001e02a  mov     ecx, 80004005h; int
0x18001e02f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e035  mov     ecx, 8007000Eh; int
0x18001e03a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

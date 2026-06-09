# COleScript::EnumStackFramesEx64(unsigned __int64,IEnumDebugStackFrames64 * *)

- ea: `0x180054530`
- end: `0x1800545eb`
- name: `?EnumStackFramesEx64@COleScript@@UEAAJ_KPEAPEAUIEnumDebugStackFrames64@@@Z`
- size: `187`
- prototype: `int(COleScript *__hidden this, unsigned __int64, struct IEnumDebugStackFrames64 **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001b588`
- `0x180044540`
- `0x180046884`
- `0x180051bf0`
- `0x180052f60`
- `0x180054530`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180054572`
- `KERNEL32!GetCurrentThreadId` at `0x180054572`

## pseudocode

```c
__int64 __fastcall COleScript::EnumStackFramesEx64(
        COleScript *this,
        unsigned __int64 a2,
        struct IEnumDebugStackFrames64 **a3)
{
  int v7; // ebx
  CEnumDebugStackFrames *v8; // rax
  CEnumDebugStackFrames *v9; // rax
  CEnumDebugStackFrames *v10; // rdi
  unsigned int Interface; // ebx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !(unsigned int)COleScript::FDebuggerEnabled((COleScript *)((char *)this - 40)) )
    return 2147549183LL;
  v7 = *((_DWORD *)this + 51);
  if ( GetCurrentThreadId() != v7 || !*((_QWORD *)this + 75) )
    return 2147500037LL;
  v8 = (CEnumDebugStackFrames *)operator new(0x30u);
  if ( !v8 )
    return 2147942414LL;
  v9 = CEnumDebugStackFrames::CEnumDebugStackFrames(v8, a2, *((struct CSession **)this + 75));
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  Interface = CEnumDebugStackFrames::QueryInterface(v9, &IID_IEnumDebugStackFrames64, (void **)a3);
  CEnumDebugStackFrames::Release(v10);
  return Interface;
}

```

## disassembly

```asm
0x180054530  push    rbx
0x180054532  push    rbp
0x180054533  push    rsi
0x180054534  push    rdi
0x180054535  sub     rsp, 28h
0x180054539  mov     rsi, r8
0x18005453c  mov     rbp, rdx
0x18005453f  mov     rdi, rcx
0x180054542  test    r8, r8
0x180054545  jnz     short loc_180054551
0x180054547  mov     eax, 80004003h
0x18005454c  jmp     loc_1800545E1
0x180054551  add     rcx, 0FFFFFFFFFFFFFFD8h; this
0x180054555  mov     qword ptr [r8], 0
0x18005455c  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x180054561  test    eax, eax
0x180054563  jnz     short loc_18005456C
0x180054565  mov     eax, 8000FFFFh
0x18005456a  jmp     short loc_1800545E1
0x18005456c  mov     ebx, [rdi+0CCh]
0x180054572  call    cs:__imp_GetCurrentThreadId
0x180054579  nop     dword ptr [rax+rax+00h]
0x18005457e  cmp     eax, ebx
0x180054580  jnz     short loc_1800545DC
0x180054582  cmp     qword ptr [rdi+258h], 0
0x18005458a  jz      short loc_1800545DC
0x18005458c  mov     ecx, 30h ; '0'; Size
0x180054591  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054596  test    rax, rax
0x180054599  jz      short loc_1800545D5
0x18005459b  mov     r8, [rdi+258h]; struct CSession *
0x1800545a2  mov     rdx, rbp; unsigned __int64
0x1800545a5  mov     rcx, rax; this
0x1800545a8  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x1800545ad  mov     rdi, rax
0x1800545b0  test    rax, rax
0x1800545b3  jz      short loc_1800545D5
0x1800545b5  mov     r8, rsi; void **
0x1800545b8  lea     rdx, IID_IEnumDebugStackFrames64; struct _GUID *
0x1800545bf  mov     rcx, rax; this
0x1800545c2  call    ?QueryInterface@CEnumDebugStackFrames@@UEAAJAEBU_GUID@@PEAPEAX@Z; CEnumDebugStackFrames::QueryInterface(_GUID const &,void * *)
0x1800545c7  mov     rcx, rdi; this
0x1800545ca  mov     ebx, eax
0x1800545cc  call    ?Release@CEnumDebugStackFrames@@UEAAKXZ; CEnumDebugStackFrames::Release(void)
0x1800545d1  mov     eax, ebx
0x1800545d3  jmp     short loc_1800545E1
0x1800545d5  mov     eax, 8007000Eh
0x1800545da  jmp     short loc_1800545E1
0x1800545dc  mov     eax, 80004005h
0x1800545e1  add     rsp, 28h
0x1800545e5  pop     rdi
0x1800545e6  pop     rsi
0x1800545e7  pop     rbp
0x1800545e8  pop     rbx
0x1800545e9  retn
```

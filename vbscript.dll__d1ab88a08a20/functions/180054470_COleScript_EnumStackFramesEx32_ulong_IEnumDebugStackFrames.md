# COleScript::EnumStackFramesEx32(ulong,IEnumDebugStackFrames * *)

- ea: `0x180054470`
- end: `0x180054526`
- name: `?EnumStackFramesEx32@COleScript@@UEAAJKPEAPEAUIEnumDebugStackFrames@@@Z`
- size: `182`
- prototype: `int(COleScript *__hidden this, unsigned int, struct IEnumDebugStackFrames **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180054450`

## callees

- `0x18001b588`
- `0x180044540`
- `0x180046884`
- `0x180051bf0`
- `0x180052f60`
- `0x180054470`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800544ad`
- `KERNEL32!GetCurrentThreadId` at `0x1800544ad`

## pseudocode

```c
__int64 __fastcall COleScript::EnumStackFramesEx32(
        struct CSession **this,
        unsigned int a2,
        struct IEnumDebugStackFrames **a3)
{
  unsigned __int64 v3; // rbp
  int v7; // ebx
  CEnumDebugStackFrames *v8; // rax
  CEnumDebugStackFrames *v9; // rax
  CEnumDebugStackFrames *v10; // rdi
  unsigned int Interface; // ebx

  v3 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !(unsigned int)COleScript::FDebuggerEnabled((COleScript *)this) )
    return 2147549183LL;
  v7 = *((_DWORD *)this + 61);
  if ( GetCurrentThreadId() != v7 || !this[80] )
    return 2147500037LL;
  v8 = (CEnumDebugStackFrames *)operator new(0x30u);
  if ( !v8 )
    return 2147942414LL;
  v9 = CEnumDebugStackFrames::CEnumDebugStackFrames(v8, v3, this[80]);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  Interface = CEnumDebugStackFrames::QueryInterface(v9, &IID_IEnumDebugStackFrames, (void **)a3);
  CEnumDebugStackFrames::Release(v10);
  return Interface;
}

```

## disassembly

```asm
0x180054470  push    rbx
0x180054472  push    rbp
0x180054473  push    rsi
0x180054474  push    rdi
0x180054475  sub     rsp, 28h
0x180054479  mov     ebp, edx
0x18005447b  mov     rsi, r8
0x18005447e  mov     rdi, rcx
0x180054481  test    r8, r8
0x180054484  jnz     short loc_180054490
0x180054486  mov     eax, 80004003h
0x18005448b  jmp     loc_18005451C
0x180054490  mov     qword ptr [r8], 0
0x180054497  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x18005449c  test    eax, eax
0x18005449e  jnz     short loc_1800544A7
0x1800544a0  mov     eax, 8000FFFFh
0x1800544a5  jmp     short loc_18005451C
0x1800544a7  mov     ebx, [rdi+0F4h]
0x1800544ad  call    cs:__imp_GetCurrentThreadId
0x1800544b4  nop     dword ptr [rax+rax+00h]
0x1800544b9  cmp     eax, ebx
0x1800544bb  jnz     short loc_180054517
0x1800544bd  cmp     qword ptr [rdi+280h], 0
0x1800544c5  jz      short loc_180054517
0x1800544c7  mov     ecx, 30h ; '0'; Size
0x1800544cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800544d1  test    rax, rax
0x1800544d4  jz      short loc_180054510
0x1800544d6  mov     r8, [rdi+280h]; struct CSession *
0x1800544dd  mov     rdx, rbp; unsigned __int64
0x1800544e0  mov     rcx, rax; this
0x1800544e3  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x1800544e8  mov     rdi, rax
0x1800544eb  test    rax, rax
0x1800544ee  jz      short loc_180054510
0x1800544f0  mov     r8, rsi; void **
0x1800544f3  lea     rdx, IID_IEnumDebugStackFrames; struct _GUID *
0x1800544fa  mov     rcx, rax; this
0x1800544fd  call    ?QueryInterface@CEnumDebugStackFrames@@UEAAJAEBU_GUID@@PEAPEAX@Z; CEnumDebugStackFrames::QueryInterface(_GUID const &,void * *)
0x180054502  mov     rcx, rdi; this
0x180054505  mov     ebx, eax
0x180054507  call    ?Release@CEnumDebugStackFrames@@UEAAKXZ; CEnumDebugStackFrames::Release(void)
0x18005450c  mov     eax, ebx
0x18005450e  jmp     short loc_18005451C
0x180054510  mov     eax, 8007000Eh
0x180054515  jmp     short loc_18005451C
0x180054517  mov     eax, 80004005h
0x18005451c  add     rsp, 28h
0x180054520  pop     rdi
0x180054521  pop     rsi
0x180054522  pop     rbp
0x180054523  pop     rbx
0x180054524  retn
```

# SqospAllocateStreamHandleContext

- ea: `0x140003460`
- end: `0x14000363e`
- name: `SqospAllocateStreamHandleContext`
- size: `478`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000603c`
- `0x140014690`

## callees

- `0x140003460`
- `0x14000666c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140003587`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003587`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000355a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000355a`
- `FLTMGR!FltAllocateContext` at `0x1400034c6`
- `FLTMGR!FltAllocateContext` at `0x1400034c6`
- `FLTMGR!FltInitializePushLock` at `0x1400034eb`
- `FLTMGR!FltInitializePushLock` at `0x1400034eb`
- `FLTMGR!FltReferenceContext` at `0x1400034fc`
- `FLTMGR!FltReferenceContext` at `0x1400034fc`
- `FLTMGR!FltReleaseContext` at `0x1400035cc`
- `FLTMGR!FltReleaseContext` at `0x14000362d`
- `FLTMGR!FltReleaseContext` at `0x1400035cc`
- `FLTMGR!FltReleaseContext` at `0x14000362d`
- `FLTMGR!FltGetInstanceContext` at `0x140003491`
- `FLTMGR!FltGetInstanceContext` at `0x140003491`

## pseudocode

```c
__int64 __fastcall SqospAllocateStreamHandleContext(__int64 a1, PFLT_CONTEXT *a2)
{
  struct _FLT_INSTANCE *v4; // rcx
  NTSTATUS InstanceContext; // ebx
  __int64 v6; // r14
  __int64 v7; // rbp
  KIRQL v8; // al
  _QWORD *v9; // rcx
  _QWORD *v10; // rdi
  PFLT_CONTEXT ReturnedContext; // [rsp+60h] [rbp+8h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp+18h] BYREF

  v4 = *(struct _FLT_INSTANCE **)(a1 + 24);
  Context = 0;
  ReturnedContext = 0;
  InstanceContext = FltGetInstanceContext(v4, &Context);
  if ( InstanceContext < 0
    || (InstanceContext = FltAllocateContext(*(PFLT_FILTER *)(a1 + 8), 0x10u, 0x28u, (POOL_TYPE)512, &ReturnedContext),
        InstanceContext < 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xBu,
        (__int64)WPP_af53c64ad8bd3a498290aca5a9ae070a_Traceguids,
        InstanceContext);
    }
    if ( ReturnedContext )
      FltReleaseContext(ReturnedContext);
  }
  else
  {
    FltInitializePushLock((PULONG_PTR)ReturnedContext);
    FltReferenceContext(Context);
    *((_QWORD *)ReturnedContext + 1) = Context;
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)Context + 22) + 12LL));
    *((_QWORD *)ReturnedContext + 2) = *((_QWORD *)Context + 22);
    *((_BYTE *)ReturnedContext + 32) = byte_14000D2AB;
    v6 = *((_QWORD *)ReturnedContext + 2);
    v7 = *((_QWORD *)ReturnedContext + 1);
    v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v6);
    v9 = *(_QWORD **)(v6 + 104);
    *(_BYTE *)(v6 + 8) = v8;
    while ( v9 != (_QWORD *)(v6 + 104) )
    {
      v10 = v9 - 5;
      if ( *(v9 - 5) == v7 )
        goto LABEL_6;
      v9 = (_QWORD *)*v9;
    }
    v10 = 0;
LABEL_6:
    KeReleaseSpinLock((PKSPIN_LOCK)v6, v8);
    *((_QWORD *)ReturnedContext + 3) = v10;
    *a2 = ReturnedContext;
    ReturnedContext = 0;
  }
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)InstanceContext;
}

```

## disassembly

```asm
0x140003460  push    rbx
0x140003462  sub     rsp, 50h
0x140003466  mov     [rsp+58h+var_10], rsi
0x14000346b  mov     rsi, rdx
0x14000346e  mov     [rsp+58h+var_18], rdi
0x140003473  lea     rdx, [rsp+58h+Context]; Context
0x140003478  mov     rdi, rcx
0x14000347b  mov     [rsp+58h+var_28], r15
0x140003480  mov     rcx, [rcx+18h]; Instance
0x140003484  xor     r15d, r15d
0x140003487  mov     [rsp+58h+Context], r15
0x14000348c  mov     [rsp+58h+arg_0], r15
0x140003491  call    cs:__imp_FltGetInstanceContext
0x140003498  nop     dword ptr [rax+rax+00h]
0x14000349d  mov     ebx, eax
0x14000349f  test    eax, eax
0x1400034a1  js      loc_1400035EB
0x1400034a7  mov     rcx, [rdi+8]; Filter
0x1400034ab  lea     rax, [rsp+58h+arg_0]
0x1400034b0  mov     edx, 10h; ContextType
0x1400034b5  mov     [rsp+58h+ReturnedContext], rax; ReturnedContext
0x1400034ba  mov     r9d, 200h; PoolType
0x1400034c0  mov     r8d, 28h ; '('; ContextSize
0x1400034c6  call    cs:__imp_FltAllocateContext
0x1400034cd  nop     dword ptr [rax+rax+00h]
0x1400034d2  mov     ebx, eax
0x1400034d4  test    eax, eax
0x1400034d6  js      loc_1400035EB
0x1400034dc  mov     rcx, [rsp+58h+arg_0]; PushLock
0x1400034e1  mov     [rsp+58h+arg_8], rbp
0x1400034e6  mov     [rsp+58h+var_20], r14
0x1400034eb  call    cs:__imp_FltInitializePushLock
0x1400034f2  nop     dword ptr [rax+rax+00h]
0x1400034f7  mov     rcx, [rsp+58h+Context]; Context
0x1400034fc  call    cs:__imp_FltReferenceContext
0x140003503  nop     dword ptr [rax+rax+00h]
0x140003508  mov     rax, [rsp+58h+arg_0]
0x14000350d  mov     rcx, [rsp+58h+Context]
0x140003512  mov     [rax+8], rcx
0x140003516  mov     rax, [rsp+58h+Context]
0x14000351b  mov     rcx, [rax+0B0h]
0x140003522  lock inc dword ptr [rcx+0Ch]
0x140003526  mov     rax, [rsp+58h+Context]
0x14000352b  mov     rcx, [rax+0B0h]
0x140003532  mov     rax, [rsp+58h+arg_0]
0x140003537  mov     [rax+10h], rcx
0x14000353b  mov     rcx, [rsp+58h+arg_0]
0x140003540  movzx   eax, cs:byte_14000D2AB
0x140003547  mov     [rcx+20h], al
0x14000354a  mov     rax, [rsp+58h+arg_0]
0x14000354f  mov     r14, [rax+10h]
0x140003553  mov     rbp, [rax+8]
0x140003557  mov     rcx, r14; SpinLock
0x14000355a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003561  nop     dword ptr [rax+rax+00h]
0x140003566  mov     rcx, [r14+68h]
0x14000356a  lea     rdx, [r14+68h]
0x14000356e  mov     [r14+8], al
0x140003572  cmp     rcx, rdx
0x140003575  jz      short loc_1400035E6
0x140003577  cmp     [rcx-28h], rbp
0x14000357b  lea     rdi, [rcx-28h]
0x14000357f  jnz     short loc_1400035E1
0x140003581  movzx   edx, al; NewIrql
0x140003584  mov     rcx, r14; SpinLock
0x140003587  call    cs:__imp_KeReleaseSpinLock
0x14000358e  nop     dword ptr [rax+rax+00h]
0x140003593  mov     rax, [rsp+58h+arg_0]
0x140003598  mov     r14, [rsp+58h+var_20]
0x14000359d  mov     rbp, [rsp+58h+arg_8]
0x1400035a2  mov     [rax+18h], rdi
0x1400035a6  mov     rax, [rsp+58h+arg_0]
0x1400035ab  mov     [rsi], rax
0x1400035ae  mov     [rsp+58h+arg_0], r15
0x1400035b3  mov     rcx, [rsp+58h+Context]; Context
0x1400035b8  mov     r15, [rsp+58h+var_28]
0x1400035bd  mov     rdi, [rsp+58h+var_18]
0x1400035c2  mov     rsi, [rsp+58h+var_10]
0x1400035c7  test    rcx, rcx
0x1400035ca  jz      short loc_1400035D8
0x1400035cc  call    cs:__imp_FltReleaseContext
0x1400035d3  nop     dword ptr [rax+rax+00h]
0x1400035d8  mov     eax, ebx
0x1400035da  add     rsp, 50h
0x1400035de  pop     rbx
0x1400035df  retn
0x1400035e1  mov     rcx, [rcx]
0x1400035e4  jmp     short loc_140003572
0x1400035e6  mov     rdi, r15
0x1400035e9  jmp     short loc_140003581
0x1400035eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400035f2  lea     rax, WPP_GLOBAL_Control
0x1400035f9  cmp     rcx, rax
0x1400035fc  jz      short loc_140003623
0x1400035fe  mov     eax, [rcx+2Ch]
0x140003601  test    al, 10h
0x140003603  jz      short loc_140003623
0x140003605  cmp     byte ptr [rcx+29h], 2
0x140003609  jb      short loc_140003623
0x14000360b  mov     rcx, [rcx+18h]
0x14000360f  lea     r8, WPP_af53c64ad8bd3a498290aca5a9ae070a_Traceguids
0x140003616  mov     edx, 0Bh
0x14000361b  mov     r9d, ebx
0x14000361e  call    WPP_SF_d
0x140003623  mov     rcx, [rsp+58h+arg_0]; Context
0x140003628  test    rcx, rcx
0x14000362b  jz      short loc_1400035B3
0x14000362d  call    cs:__imp_FltReleaseContext
0x140003634  nop     dword ptr [rax+rax+00h]
0x140003639  jmp     loc_1400035B3
```

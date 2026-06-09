# TmpScheduleRollback

- ea: `0x14001176c`
- end: `0x140011895`
- name: `TmpScheduleRollback`
- size: `297`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400109a4`
- `0x14001189c`

## callees

- `0x14001176c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400117f4`
- `ntoskrnl!ObfDereferenceObject` at `0x14001186e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400117f4`
- `ntoskrnl!ObfDereferenceObject` at `0x14001186e`
- `ntoskrnl!ObfReferenceObject` at `0x140011803`
- `ntoskrnl!ObfReferenceObject` at `0x140011803`
- `ntoskrnl!KeInitializeTimer` at `0x1400117a7`
- `ntoskrnl!KeInitializeTimer` at `0x1400117a7`
- `ntoskrnl!KeInitializeDpc` at `0x1400117c0`
- `ntoskrnl!KeInitializeDpc` at `0x1400117c0`
- `ntoskrnl!KeSetTimer` at `0x140011824`
- `ntoskrnl!KeSetTimer` at `0x140011824`
- `ntoskrnl!KeCancelTimer` at `0x1400117e1`
- `ntoskrnl!KeCancelTimer` at `0x140011844`
- `ntoskrnl!KeCancelTimer` at `0x1400117e1`
- `ntoskrnl!KeCancelTimer` at `0x140011844`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14001185b`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14001185b`

## pseudocode

```c
__int64 __fastcall TmpScheduleRollback(char *Object)
{
  int v2; // eax
  struct _KTIMER *v3; // rdi
  struct _KDPC *v4; // rsi

  v2 = *((_DWORD *)Object + 49);
  if ( *((_QWORD *)Object + 37) )
  {
    v3 = (struct _KTIMER *)(Object + 424);
    v4 = (struct _KDPC *)(Object + 360);
    if ( (v2 & 0x10) == 0 )
    {
      KeInitializeTimer(v3);
      KeInitializeDpc(v4, TmpRollbackDpc, Object);
      _InterlockedOr((volatile signed __int32 *)Object + 49, 0x10u);
    }
    if ( (*((_DWORD *)Object + 49) & 0x20) != 0 )
    {
      if ( !KeCancelTimer(v3) )
        return 3222863932LL;
      ObfDereferenceObject(Object);
    }
    ObfReferenceObject(Object);
    _InterlockedOr((volatile signed __int32 *)Object + 49, 0x20u);
    KeSetTimer(v3, *(LARGE_INTEGER *)(Object + 296), v4);
  }
  else if ( (v2 & 0x20) != 0
         && (KeCancelTimer((PKTIMER)(Object + 424)) == 1 || KeRemoveQueueDpc((PRKDPC)(Object + 360)) == 1) )
  {
    ObfDereferenceObject(Object);
    _InterlockedAnd((volatile signed __int32 *)Object + 49, 0xFFFFFFDF);
  }
  return 0;
}

```

## disassembly

```asm
0x14001176c  mov     [rsp+arg_0], rbx
0x140011771  mov     [rsp+arg_8], rsi
0x140011776  push    rdi
0x140011777  sub     rsp, 20h
0x14001177b  cmp     qword ptr [rcx+128h], 0
0x140011783  mov     rbx, rcx
0x140011786  mov     eax, [rcx+0C4h]
0x14001178c  jz      loc_140011839
0x140011792  lea     rdi, [rcx+1A8h]
0x140011799  lea     rsi, [rcx+168h]
0x1400117a0  test    al, 10h
0x1400117a2  jnz     short loc_1400117D4
0x1400117a4  mov     rcx, rdi; Timer
0x1400117a7  call    cs:__imp_KeInitializeTimer
0x1400117ae  nop     dword ptr [rax+rax+00h]
0x1400117b3  mov     r8, rbx; DeferredContext
0x1400117b6  lea     rdx, TmpRollbackDpc; DeferredRoutine
0x1400117bd  mov     rcx, rsi; Dpc
0x1400117c0  call    cs:__imp_KeInitializeDpc
0x1400117c7  nop     dword ptr [rax+rax+00h]
0x1400117cc  lock or dword ptr [rbx+0C4h], 10h
0x1400117d4  mov     eax, [rbx+0C4h]
0x1400117da  test    al, 20h
0x1400117dc  jz      short loc_140011800
0x1400117de  mov     rcx, rdi; PKTIMER
0x1400117e1  call    cs:__imp_KeCancelTimer
0x1400117e8  nop     dword ptr [rax+rax+00h]
0x1400117ed  test    al, al
0x1400117ef  jz      short loc_140011832
0x1400117f1  mov     rcx, rbx; Object
0x1400117f4  call    cs:__imp_ObfDereferenceObject
0x1400117fb  nop     dword ptr [rax+rax+00h]
0x140011800  mov     rcx, rbx; Object
0x140011803  call    cs:__imp_ObfReferenceObject
0x14001180a  nop     dword ptr [rax+rax+00h]
0x14001180f  lock or dword ptr [rbx+0C4h], 20h
0x140011817  mov     rdx, [rbx+128h]; DueTime
0x14001181e  mov     r8, rsi; Dpc
0x140011821  mov     rcx, rdi; Timer
0x140011824  call    cs:__imp_KeSetTimer
0x14001182b  nop     dword ptr [rax+rax+00h]
0x140011830  jmp     short loc_140011882
0x140011832  mov     eax, 0C019003Ch
0x140011837  jmp     short loc_140011884
0x140011839  test    al, 20h
0x14001183b  jz      short loc_140011882
0x14001183d  add     rcx, 1A8h; PKTIMER
0x140011844  call    cs:__imp_KeCancelTimer
0x14001184b  nop     dword ptr [rax+rax+00h]
0x140011850  cmp     al, 1
0x140011852  jz      short loc_14001186B
0x140011854  lea     rcx, [rbx+168h]; Dpc
0x14001185b  call    cs:__imp_KeRemoveQueueDpc
0x140011862  nop     dword ptr [rax+rax+00h]
0x140011867  cmp     al, 1
0x140011869  jnz     short loc_140011882
0x14001186b  mov     rcx, rbx; Object
0x14001186e  call    cs:__imp_ObfDereferenceObject
0x140011875  nop     dword ptr [rax+rax+00h]
0x14001187a  lock and dword ptr [rbx+0C4h], 0FFFFFFDFh
0x140011882  xor     eax, eax
0x140011884  mov     rbx, [rsp+28h+arg_0]
0x140011889  mov     rsi, [rsp+28h+arg_8]
0x14001188e  add     rsp, 20h
0x140011892  pop     rdi
0x140011893  retn
```

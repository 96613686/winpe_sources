# OncRpcWiMgrpWorkerThreadTerminate

- ea: `0x1400204c0`
- end: `0x1400205ad`
- name: `OncRpcWiMgrpWorkerThreadTerminate`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140005830`
- `0x14000f1d0`
- `0x1400204c0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002052e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002052e`
- `ntoskrnl!ObfDereferenceObject` at `0x140020541`
- `ntoskrnl!ObfDereferenceObject` at `0x140020541`
- `ntoskrnl!ObfReferenceObject` at `0x14002055d`
- `ntoskrnl!ObfReferenceObject` at `0x14002055d`
- `ntoskrnl!PsTerminateSystemThread` at `0x140020595`
- `ntoskrnl!PsTerminateSystemThread` at `0x140020595`
- `ntoskrnl!KeSetEvent` at `0x140020579`
- `ntoskrnl!KeSetEvent` at `0x140020579`

## pseudocode

```c
NTSTATUS __fastcall OncRpcWiMgrpWorkerThreadTerminate(__int64 a1)
{
  signed __int32 v2; // edi
  void *v3; // rcx
  struct _KTHREAD *CurrentThread; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 104));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids,
      *(unsigned int *)(a1 + 112),
      *(_DWORD *)(a1 + 104));
  v3 = *(void **)(a1 + 208);
  if ( v3 )
  {
    KeWaitForSingleObject(v3, Executive, 0, 0, 0);
    ObfDereferenceObject(*(PVOID *)(a1 + 208));
  }
  CurrentThread = KeGetCurrentThread();
  *(_QWORD *)(a1 + 208) = CurrentThread;
  ObfReferenceObject(CurrentThread);
  if ( v2 )
    OncRpcWiMgrWorkQueueItemPost((PLIST_ENTRY)(a1 + 136));
  else
    KeSetEvent((PRKEVENT)(a1 + 184), 0, 0);
  return PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x1400204c0  mov     [rsp+arg_0], rbx
0x1400204c5  push    rdi
0x1400204c6  sub     rsp, 30h
0x1400204ca  mov     rbx, rcx
0x1400204cd  or      edi, 0FFFFFFFFh
0x1400204d0  lock xadd [rcx+68h], edi
0x1400204d5  dec     edi
0x1400204d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400204de  lea     rax, WPP_GLOBAL_Control
0x1400204e5  cmp     rcx, rax
0x1400204e8  jz      short loc_140020511
0x1400204ea  mov     eax, [rcx+2Ch]
0x1400204ed  test    al, al
0x1400204ef  jns     short loc_140020511
0x1400204f1  mov     eax, [rbx+68h]
0x1400204f4  lea     r8, WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids
0x1400204fb  mov     r9d, [rbx+70h]
0x1400204ff  mov     edx, 0Dh
0x140020504  mov     rcx, [rcx+18h]
0x140020508  mov     dword ptr [rsp+38h+Timeout], eax
0x14002050c  call    WPP_SF_Dd
0x140020511  mov     rcx, [rbx+0D0h]; Object
0x140020518  test    rcx, rcx
0x14002051b  jz      short loc_14002054D
0x14002051d  xor     r9d, r9d; Alertable
0x140020520  mov     [rsp+38h+Timeout], 0; Timeout
0x140020529  xor     r8d, r8d; WaitMode
0x14002052c  xor     edx, edx; WaitReason
0x14002052e  call    cs:__imp_KeWaitForSingleObject
0x140020535  nop     dword ptr [rax+rax+00h]
0x14002053a  mov     rcx, [rbx+0D0h]; Object
0x140020541  call    cs:__imp_ObfDereferenceObject
0x140020548  nop     dword ptr [rax+rax+00h]
0x14002054d  mov     rcx, gs:188h; Object
0x140020556  mov     [rbx+0D0h], rcx
0x14002055d  call    cs:__imp_ObfReferenceObject
0x140020564  nop     dword ptr [rax+rax+00h]
0x140020569  test    edi, edi
0x14002056b  jnz     short loc_140020587
0x14002056d  lea     rcx, [rbx+0B8h]; Event
0x140020574  xor     r8d, r8d; Wait
0x140020577  xor     edx, edx; Increment
0x140020579  call    cs:__imp_KeSetEvent
0x140020580  nop     dword ptr [rax+rax+00h]
0x140020585  jmp     short loc_140020593
0x140020587  lea     rcx, [rbx+88h]; Entry
0x14002058e  call    OncRpcWiMgrWorkQueueItemPost
0x140020593  xor     ecx, ecx; ExitStatus
0x140020595  call    cs:__imp_PsTerminateSystemThread
0x14002059c  nop     dword ptr [rax+rax+00h]
0x1400205a1  mov     rbx, [rsp+38h+arg_0]
0x1400205a6  add     rsp, 30h
0x1400205aa  pop     rdi
0x1400205ab  retn
```

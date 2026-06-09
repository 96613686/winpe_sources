# FlUnbindAdapter

- ea: `0x1401a4560`
- end: `0x1401a48a7`
- name: `FlUnbindAdapter`
- size: `839`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140077580`
- `0x1400c4190`
- `0x1400c4ba0`
- `0x1400c4cec`
- `0x1400c5290`
- `0x1400c5648`
- `0x1400c6448`
- `0x1400c7b84`
- `0x1400c8a8c`
- `0x1400c8e74`
- `0x140114950`
- `0x14011aab8`
- `0x140149484`
- `0x140149a68`
- `0x1401a4560`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401a464b`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401a464b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a46bf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a47b7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a46bf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a47b7`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x1401a4833`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x1401a4833`
- `NDIS!NdisCloseAdapterEx` at `0x1401a4788`
- `NDIS!NdisCloseAdapterEx` at `0x1401a4788`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401a45d1`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401a45d1`
- `NDIS!NdisReleaseRWLock` at `0x1401a45f5`
- `NDIS!NdisReleaseRWLock` at `0x1401a45f5`

## pseudocode

```c
__int64 __fastcall FlUnbindAdapter(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  int v4; // esi
  NDIS_STATUS v5; // ecx
  __int64 v6; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF
  int v9; // [rsp+60h] [rbp+18h] BYREF

  v2 = *(_QWORD *)(a2 + 32);
  v4 = *(_DWORD *)(a2 + 1176);
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( (BYTE2(WPP_MAIN_CB.Reserved) & 4) != 0 )
    McTemplateK0qqqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)TCPIP_FRAMING_BIND_PROGRESS,
      (unsigned int)MICROSOFT_TCPIP_PROVIDER,
      v4,
      *(_WORD *)(v2 + 92),
      2,
      0);
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a2 + 40), &LockState, 0);
  *(_DWORD *)(a2 + 196) |= 8u;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a2 + 40), &LockState);
  FlpSerializedNdisRequest((PVOID)a2, 0, 0);
  if ( (*(_DWORD *)(a2 + 976) & 1) != 0 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(a2 + 32) + 632LL))(a2, 8);
  ExWaitForRundownProtectionReleaseCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a2 + 72));
  if ( *(_BYTE *)(v2 + 656) )
    FlpDisableVirtualInterfaceConfiguration(a2);
  FlpDeleteInterface(*(PRTL_DYNAMIC_HASH_TABLE_ENTRY *)(a2 + 288));
  FlpDereferenceClientInterface(*(_QWORD *)(a2 + 288));
  FlpFlushQueuedPmRemoveOids(a2);
  if ( *(_DWORD *)(a2 + 860) != 1 && _InterlockedDecrement((volatile signed __int32 *)(a2 + 860)) != 1 )
    KeWaitForSingleObject((PVOID)(a2 + 864), UserRequest, 0, 0, 0);
  FlpCleanupWolPatternEntries(a2);
  if ( *(_DWORD *)(a2 + 912) )
  {
    v9 = *(_DWORD *)(a2 + 912);
    FlpNdisRequest(a2, 0, 1, -50265845, (__int64)&v9, 4, 0);
    *(_DWORD *)(a2 + 912) = 0;
  }
  if ( *(_DWORD *)(a2 + 916) )
  {
    v9 = *(_DWORD *)(a2 + 916);
    FlpNdisRequest(a2, 0, 1, -50265845, (__int64)&v9, 4, 0);
    *(_DWORD *)(a2 + 916) = 0;
  }
  FlpCleanupPortCoalescedWakePatterns(a2);
  FlpCleanupL2UnicastWakePatterns(a2);
  FlpTraceWakeStatistics(a2);
  FlpUninitializeProviderInterfaces(a2);
  v5 = NdisCloseAdapterEx(*(NDIS_HANDLE *)(a2 + 1280));
  if ( v5 == 259 )
  {
    KeWaitForSingleObject((PVOID)(a2 + 168), UserRequest, 0, 0, 0);
    v5 = *(_DWORD *)(a2 + 192);
  }
  if ( v5 < 0 )
  {
    if ( (BYTE2(WPP_MAIN_CB.Reserved) & 4) != 0 )
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_FRAMING_BIND_PROGRESS,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v4,
        *(_WORD *)(v2 + 92),
        10,
        v5);
  }
  else if ( *(_DWORD *)(a2 + 312) == 15 )
  {
    v6 = *(_QWORD *)(a2 + 32);
    if ( *(_WORD *)(v6 + 92) == 23 )
      (*(void (__fastcall **)(__int64))(v6 + 400))(a2);
  }
  NetioDeregisterTriageDumpDataCallback(a2 + 1088);
  FlpRemoveInterface(v2 + 440, a2);
  FlpDereferenceInterface(a2);
  if ( (BYTE2(WPP_MAIN_CB.Reserved) & 4) != 0 )
    McTemplateK0qqqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)TCPIP_FRAMING_BIND_PROGRESS,
      (unsigned int)MICROSOFT_TCPIP_PROVIDER,
      v4,
      *(_WORD *)(v2 + 92),
      3,
      0);
  return 0;
}

```

## disassembly

```asm
0x1401a4560  mov     [rsp+arg_0], rbx
0x1401a4565  mov     [rsp+arg_18], rsi
0x1401a456a  push    rdi
0x1401a456b  sub     rsp, 40h
0x1401a456f  mov     rdi, [rdx+20h]
0x1401a4573  xor     eax, eax
0x1401a4575  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x1401a457c  mov     rbx, rdx
0x1401a457f  mov     esi, [rdx+498h]
0x1401a4585  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x1401a458a  mov     [rsp+48h+LockState.Flags], al
0x1401a458e  jz      short loc_1401A45C5
0x1401a4590  movzx   eax, word ptr [rdi+5Ch]
0x1401a4594  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401a459b  mov     dword ptr [rsp+48h+var_18], 0
0x1401a45a3  lea     rdx, TCPIP_FRAMING_BIND_PROGRESS
0x1401a45aa  mov     dword ptr [rsp+48h+var_20], 2
0x1401a45b2  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401a45b9  mov     r9d, esi
0x1401a45bc  mov     dword ptr [rsp+48h+Timeout], eax
0x1401a45c0  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401a45c5  mov     rcx, [rbx+28h]; Lock
0x1401a45c9  lea     rdx, [rsp+48h+LockState]; LockState
0x1401a45ce  xor     r8d, r8d; Flags
0x1401a45d1  call    cs:__imp_NdisAcquireRWLockWrite
0x1401a45d8  nop     dword ptr [rax+rax+00h]
0x1401a45dd  mov     eax, [rbx+0C4h]
0x1401a45e3  lea     rdx, [rsp+48h+LockState]; LockState
0x1401a45e8  or      eax, 8
0x1401a45eb  mov     [rbx+0C4h], eax
0x1401a45f1  mov     rcx, [rbx+28h]; Lock
0x1401a45f5  call    cs:__imp_NdisReleaseRWLock
0x1401a45fc  nop     dword ptr [rax+rax+00h]
0x1401a4601  xor     r9d, r9d
0x1401a4604  mov     [rsp+48h+var_20], 0; __int64
0x1401a460d  lea     rdx, FlpSerializedNdisResetFiltersWorker
0x1401a4614  mov     [rsp+48h+Timeout], 0; __int64
0x1401a461d  mov     rcx, rbx; Context
0x1401a4620  call    FlpSerializedNdisRequest
0x1401a4625  mov     eax, [rbx+3D0h]
0x1401a462b  test    al, 1
0x1401a462d  jz      short loc_1401A4647
0x1401a462f  mov     rax, [rbx+20h]
0x1401a4633  mov     edx, 8
0x1401a4638  mov     rcx, rbx
0x1401a463b  mov     rax, [rax+278h]
0x1401a4642  call    _guard_dispatch_icall
0x1401a4647  mov     rcx, [rbx+48h]; RunRef
0x1401a464b  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1401a4652  nop     dword ptr [rax+rax+00h]
0x1401a4657  cmp     byte ptr [rdi+290h], 0
0x1401a465e  jz      short loc_1401A4668
0x1401a4660  mov     rcx, rbx
0x1401a4663  call    FlpDisableVirtualInterfaceConfiguration
0x1401a4668  mov     rcx, [rbx+120h]; Entry
0x1401a466f  call    FlpDeleteInterface
0x1401a4674  mov     rcx, [rbx+120h]
0x1401a467b  call    FlpDereferenceClientInterface
0x1401a4680  mov     rcx, rbx
0x1401a4683  call    FlpFlushQueuedPmRemoveOids
0x1401a4688  mov     eax, [rbx+35Ch]
0x1401a468e  cmp     eax, 1
0x1401a4691  jz      short loc_1401A46CB
0x1401a4693  or      eax, 0FFFFFFFFh
0x1401a4696  lock xadd [rbx+35Ch], eax
0x1401a469e  dec     eax
0x1401a46a0  cmp     eax, 1
0x1401a46a3  jz      short loc_1401A46CB
0x1401a46a5  xor     r9d, r9d; Alertable
0x1401a46a8  mov     [rsp+48h+Timeout], 0; Timeout
0x1401a46b1  lea     rcx, [rbx+360h]; Object
0x1401a46b8  xor     r8d, r8d; WaitMode
0x1401a46bb  lea     edx, [r9+6]; WaitReason
0x1401a46bf  call    cs:__imp_KeWaitForSingleObject
0x1401a46c6  nop     dword ptr [rax+rax+00h]
0x1401a46cb  mov     rcx, rbx
0x1401a46ce  call    FlpCleanupWolPatternEntries
0x1401a46d3  mov     eax, [rbx+390h]
0x1401a46d9  test    eax, eax
0x1401a46db  jz      short loc_1401A471A
0x1401a46dd  xor     edx, edx
0x1401a46df  mov     [rsp+48h+arg_10], eax
0x1401a46e3  mov     [rsp+48h+var_18], 0
0x1401a46ec  lea     rax, [rsp+48h+arg_10]
0x1401a46f1  mov     dword ptr [rsp+48h+var_20], 4
0x1401a46f9  mov     r9d, 0FD01010Bh
0x1401a46ff  mov     rcx, rbx
0x1401a4702  mov     [rsp+48h+Timeout], rax
0x1401a4707  lea     r8d, [rdx+1]
0x1401a470b  call    FlpNdisRequest
0x1401a4710  mov     dword ptr [rbx+390h], 0
0x1401a471a  mov     eax, [rbx+394h]
0x1401a4720  test    eax, eax
0x1401a4722  jz      short loc_1401A4761
0x1401a4724  xor     edx, edx
0x1401a4726  mov     [rsp+48h+arg_10], eax
0x1401a472a  mov     [rsp+48h+var_18], 0
0x1401a4733  lea     rax, [rsp+48h+arg_10]
0x1401a4738  mov     dword ptr [rsp+48h+var_20], 4
0x1401a4740  mov     r9d, 0FD01010Bh
0x1401a4746  mov     rcx, rbx
0x1401a4749  mov     [rsp+48h+Timeout], rax
0x1401a474e  lea     r8d, [rdx+1]
0x1401a4752  call    FlpNdisRequest
0x1401a4757  mov     dword ptr [rbx+394h], 0
0x1401a4761  mov     rcx, rbx
0x1401a4764  call    FlpCleanupPortCoalescedWakePatterns
0x1401a4769  mov     rcx, rbx
0x1401a476c  call    FlpCleanupL2UnicastWakePatterns
0x1401a4771  mov     rcx, rbx
0x1401a4774  call    FlpTraceWakeStatistics
0x1401a4779  mov     rcx, rbx
0x1401a477c  call    FlpUninitializeProviderInterfaces
0x1401a4781  mov     rcx, [rbx+500h]; NdisBindingHandle
0x1401a4788  call    cs:__imp_NdisCloseAdapterEx
0x1401a478f  nop     dword ptr [rax+rax+00h]
0x1401a4794  mov     ecx, eax
0x1401a4796  cmp     eax, 103h
0x1401a479b  jnz     short loc_1401A47C9
0x1401a479d  xor     r9d, r9d; Alertable
0x1401a47a0  mov     [rsp+48h+Timeout], 0; Timeout
0x1401a47a9  lea     rcx, [rbx+0A8h]; Object
0x1401a47b0  xor     r8d, r8d; WaitMode
0x1401a47b3  lea     edx, [r9+6]; WaitReason
0x1401a47b7  call    cs:__imp_KeWaitForSingleObject
0x1401a47be  nop     dword ptr [rax+rax+00h]
0x1401a47c3  mov     ecx, [rbx+0C0h]
0x1401a47c9  test    ecx, ecx
0x1401a47cb  js      short loc_1401A47F2
0x1401a47cd  cmp     dword ptr [rbx+138h], 0Fh
0x1401a47d4  jnz     short loc_1401A482C
0x1401a47d6  mov     rax, [rbx+20h]
0x1401a47da  cmp     word ptr [rax+5Ch], 17h
0x1401a47df  jnz     short loc_1401A482C
0x1401a47e1  mov     rax, [rax+190h]
0x1401a47e8  mov     rcx, rbx
0x1401a47eb  call    _guard_dispatch_icall
0x1401a47f0  jmp     short loc_1401A482C
0x1401a47f2  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x1401a47f9  jz      short loc_1401A482C
0x1401a47fb  movzx   eax, word ptr [rdi+5Ch]
0x1401a47ff  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401a4806  mov     dword ptr [rsp+48h+var_18], ecx
0x1401a480a  lea     rdx, TCPIP_FRAMING_BIND_PROGRESS
0x1401a4811  mov     dword ptr [rsp+48h+var_20], 0Ah
0x1401a4819  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401a4820  mov     r9d, esi
0x1401a4823  mov     dword ptr [rsp+48h+Timeout], eax
0x1401a4827  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401a482c  lea     rcx, [rbx+440h]
0x1401a4833  call    cs:__imp_NetioDeregisterTriageDumpDataCallback
0x1401a483a  nop     dword ptr [rax+rax+00h]
0x1401a483f  lea     rcx, [rdi+1B8h]
0x1401a4846  mov     rdx, rbx
0x1401a4849  call    FlpRemoveInterface
0x1401a484e  mov     rcx, rbx
0x1401a4851  call    FlpDereferenceInterface
0x1401a4856  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x1401a485d  jz      short loc_1401A4894
0x1401a485f  movzx   eax, word ptr [rdi+5Ch]
0x1401a4863  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401a486a  mov     dword ptr [rsp+48h+var_18], 0
0x1401a4872  lea     rdx, TCPIP_FRAMING_BIND_PROGRESS
0x1401a4879  mov     dword ptr [rsp+48h+var_20], 3
0x1401a4881  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401a4888  mov     r9d, esi
0x1401a488b  mov     dword ptr [rsp+48h+Timeout], eax
0x1401a488f  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401a4894  mov     rbx, [rsp+48h+arg_0]
0x1401a4899  xor     eax, eax
0x1401a489b  mov     rsi, [rsp+48h+arg_18]
0x1401a48a0  add     rsp, 40h
0x1401a48a4  pop     rdi
0x1401a48a5  retn
```

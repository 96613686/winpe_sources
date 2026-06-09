# FlUnbindAdapter

- ea: `0x1401a4420`
- end: `0x1401a4767`
- name: `FlUnbindAdapter`
- size: `839`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400772e0`
- `0x1400c43b0`
- `0x1400c4dc0`
- `0x1400c4f0c`
- `0x1400c54b0`
- `0x1400c5868`
- `0x1400c6668`
- `0x1400c7da4`
- `0x1400c8cac`
- `0x1400c9094`
- `0x140114810`
- `0x14011a978`
- `0x1401492f4`
- `0x1401498d8`
- `0x1401a4420`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401a450b`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401a450b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a457f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a4677`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a457f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a4677`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x1401a46f3`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x1401a46f3`
- `NDIS!NdisCloseAdapterEx` at `0x1401a4648`
- `NDIS!NdisCloseAdapterEx` at `0x1401a4648`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401a4491`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401a4491`
- `NDIS!NdisReleaseRWLock` at `0x1401a44b5`
- `NDIS!NdisReleaseRWLock` at `0x1401a44b5`

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
0x1401a4420  mov     [rsp+arg_0], rbx
0x1401a4425  mov     [rsp+arg_18], rsi
0x1401a442a  push    rdi
0x1401a442b  sub     rsp, 40h
0x1401a442f  mov     rdi, [rdx+20h]
0x1401a4433  xor     eax, eax
0x1401a4435  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x1401a443c  mov     rbx, rdx
0x1401a443f  mov     esi, [rdx+498h]
0x1401a4445  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x1401a444a  mov     [rsp+48h+LockState.Flags], al
0x1401a444e  jz      short loc_1401A4485
0x1401a4450  movzx   eax, word ptr [rdi+5Ch]
0x1401a4454  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401a445b  mov     dword ptr [rsp+48h+var_18], 0
0x1401a4463  lea     rdx, TCPIP_FRAMING_BIND_PROGRESS
0x1401a446a  mov     dword ptr [rsp+48h+var_20], 2
0x1401a4472  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401a4479  mov     r9d, esi
0x1401a447c  mov     dword ptr [rsp+48h+Timeout], eax
0x1401a4480  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401a4485  mov     rcx, [rbx+28h]; Lock
0x1401a4489  lea     rdx, [rsp+48h+LockState]; LockState
0x1401a448e  xor     r8d, r8d; Flags
0x1401a4491  call    cs:__imp_NdisAcquireRWLockWrite
0x1401a4498  nop     dword ptr [rax+rax+00h]
0x1401a449d  mov     eax, [rbx+0C4h]
0x1401a44a3  lea     rdx, [rsp+48h+LockState]; LockState
0x1401a44a8  or      eax, 8
0x1401a44ab  mov     [rbx+0C4h], eax
0x1401a44b1  mov     rcx, [rbx+28h]; Lock
0x1401a44b5  call    cs:__imp_NdisReleaseRWLock
0x1401a44bc  nop     dword ptr [rax+rax+00h]
0x1401a44c1  xor     r9d, r9d
0x1401a44c4  mov     [rsp+48h+var_20], 0; __int64
0x1401a44cd  lea     rdx, FlpSerializedNdisResetFiltersWorker
0x1401a44d4  mov     [rsp+48h+Timeout], 0; __int64
0x1401a44dd  mov     rcx, rbx; Context
0x1401a44e0  call    FlpSerializedNdisRequest
0x1401a44e5  mov     eax, [rbx+3D0h]
0x1401a44eb  test    al, 1
0x1401a44ed  jz      short loc_1401A4507
0x1401a44ef  mov     rax, [rbx+20h]
0x1401a44f3  mov     edx, 8
0x1401a44f8  mov     rcx, rbx
0x1401a44fb  mov     rax, [rax+278h]
0x1401a4502  call    _guard_dispatch_icall
0x1401a4507  mov     rcx, [rbx+48h]; RunRef
0x1401a450b  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1401a4512  nop     dword ptr [rax+rax+00h]
0x1401a4517  cmp     byte ptr [rdi+290h], 0
0x1401a451e  jz      short loc_1401A4528
0x1401a4520  mov     rcx, rbx
0x1401a4523  call    FlpDisableVirtualInterfaceConfiguration
0x1401a4528  mov     rcx, [rbx+120h]; Entry
0x1401a452f  call    FlpDeleteInterface
0x1401a4534  mov     rcx, [rbx+120h]
0x1401a453b  call    FlpDereferenceClientInterface
0x1401a4540  mov     rcx, rbx
0x1401a4543  call    FlpFlushQueuedPmRemoveOids
0x1401a4548  mov     eax, [rbx+35Ch]
0x1401a454e  cmp     eax, 1
0x1401a4551  jz      short loc_1401A458B
0x1401a4553  or      eax, 0FFFFFFFFh
0x1401a4556  lock xadd [rbx+35Ch], eax
0x1401a455e  dec     eax
0x1401a4560  cmp     eax, 1
0x1401a4563  jz      short loc_1401A458B
0x1401a4565  xor     r9d, r9d; Alertable
0x1401a4568  mov     [rsp+48h+Timeout], 0; Timeout
0x1401a4571  lea     rcx, [rbx+360h]; Object
0x1401a4578  xor     r8d, r8d; WaitMode
0x1401a457b  lea     edx, [r9+6]; WaitReason
0x1401a457f  call    cs:__imp_KeWaitForSingleObject
0x1401a4586  nop     dword ptr [rax+rax+00h]
0x1401a458b  mov     rcx, rbx
0x1401a458e  call    FlpCleanupWolPatternEntries
0x1401a4593  mov     eax, [rbx+390h]
0x1401a4599  test    eax, eax
0x1401a459b  jz      short loc_1401A45DA
0x1401a459d  xor     edx, edx
0x1401a459f  mov     [rsp+48h+arg_10], eax
0x1401a45a3  mov     [rsp+48h+var_18], 0
0x1401a45ac  lea     rax, [rsp+48h+arg_10]
0x1401a45b1  mov     dword ptr [rsp+48h+var_20], 4
0x1401a45b9  mov     r9d, 0FD01010Bh
0x1401a45bf  mov     rcx, rbx
0x1401a45c2  mov     [rsp+48h+Timeout], rax
0x1401a45c7  lea     r8d, [rdx+1]
0x1401a45cb  call    FlpNdisRequest
0x1401a45d0  mov     dword ptr [rbx+390h], 0
0x1401a45da  mov     eax, [rbx+394h]
0x1401a45e0  test    eax, eax
0x1401a45e2  jz      short loc_1401A4621
0x1401a45e4  xor     edx, edx
0x1401a45e6  mov     [rsp+48h+arg_10], eax
0x1401a45ea  mov     [rsp+48h+var_18], 0
0x1401a45f3  lea     rax, [rsp+48h+arg_10]
0x1401a45f8  mov     dword ptr [rsp+48h+var_20], 4
0x1401a4600  mov     r9d, 0FD01010Bh
0x1401a4606  mov     rcx, rbx
0x1401a4609  mov     [rsp+48h+Timeout], rax
0x1401a460e  lea     r8d, [rdx+1]
0x1401a4612  call    FlpNdisRequest
0x1401a4617  mov     dword ptr [rbx+394h], 0
0x1401a4621  mov     rcx, rbx
0x1401a4624  call    FlpCleanupPortCoalescedWakePatterns
0x1401a4629  mov     rcx, rbx
0x1401a462c  call    FlpCleanupL2UnicastWakePatterns
0x1401a4631  mov     rcx, rbx
0x1401a4634  call    FlpTraceWakeStatistics
0x1401a4639  mov     rcx, rbx
0x1401a463c  call    FlpUninitializeProviderInterfaces
0x1401a4641  mov     rcx, [rbx+500h]; NdisBindingHandle
0x1401a4648  call    cs:__imp_NdisCloseAdapterEx
0x1401a464f  nop     dword ptr [rax+rax+00h]
0x1401a4654  mov     ecx, eax
0x1401a4656  cmp     eax, 103h
0x1401a465b  jnz     short loc_1401A4689
0x1401a465d  xor     r9d, r9d; Alertable
0x1401a4660  mov     [rsp+48h+Timeout], 0; Timeout
0x1401a4669  lea     rcx, [rbx+0A8h]; Object
0x1401a4670  xor     r8d, r8d; WaitMode
0x1401a4673  lea     edx, [r9+6]; WaitReason
0x1401a4677  call    cs:__imp_KeWaitForSingleObject
0x1401a467e  nop     dword ptr [rax+rax+00h]
0x1401a4683  mov     ecx, [rbx+0C0h]
0x1401a4689  test    ecx, ecx
0x1401a468b  js      short loc_1401A46B2
0x1401a468d  cmp     dword ptr [rbx+138h], 0Fh
0x1401a4694  jnz     short loc_1401A46EC
0x1401a4696  mov     rax, [rbx+20h]
0x1401a469a  cmp     word ptr [rax+5Ch], 17h
0x1401a469f  jnz     short loc_1401A46EC
0x1401a46a1  mov     rax, [rax+190h]
0x1401a46a8  mov     rcx, rbx
0x1401a46ab  call    _guard_dispatch_icall
0x1401a46b0  jmp     short loc_1401A46EC
0x1401a46b2  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x1401a46b9  jz      short loc_1401A46EC
0x1401a46bb  movzx   eax, word ptr [rdi+5Ch]
0x1401a46bf  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401a46c6  mov     dword ptr [rsp+48h+var_18], ecx
0x1401a46ca  lea     rdx, TCPIP_FRAMING_BIND_PROGRESS
0x1401a46d1  mov     dword ptr [rsp+48h+var_20], 0Ah
0x1401a46d9  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401a46e0  mov     r9d, esi
0x1401a46e3  mov     dword ptr [rsp+48h+Timeout], eax
0x1401a46e7  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401a46ec  lea     rcx, [rbx+440h]
0x1401a46f3  call    cs:__imp_NetioDeregisterTriageDumpDataCallback
0x1401a46fa  nop     dword ptr [rax+rax+00h]
0x1401a46ff  lea     rcx, [rdi+1B8h]
0x1401a4706  mov     rdx, rbx
0x1401a4709  call    FlpRemoveInterface
0x1401a470e  mov     rcx, rbx
0x1401a4711  call    FlpDereferenceInterface
0x1401a4716  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x1401a471d  jz      short loc_1401A4754
0x1401a471f  movzx   eax, word ptr [rdi+5Ch]
0x1401a4723  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401a472a  mov     dword ptr [rsp+48h+var_18], 0
0x1401a4732  lea     rdx, TCPIP_FRAMING_BIND_PROGRESS
0x1401a4739  mov     dword ptr [rsp+48h+var_20], 3
0x1401a4741  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401a4748  mov     r9d, esi
0x1401a474b  mov     dword ptr [rsp+48h+Timeout], eax
0x1401a474f  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401a4754  mov     rbx, [rsp+48h+arg_0]
0x1401a4759  xor     eax, eax
0x1401a475b  mov     rsi, [rsp+48h+arg_18]
0x1401a4760  add     rsp, 40h
0x1401a4764  pop     rdi
0x1401a4765  retn
```

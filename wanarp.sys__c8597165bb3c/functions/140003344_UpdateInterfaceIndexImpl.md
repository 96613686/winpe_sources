# UpdateInterfaceIndexImpl

- ea: `0x140003344`
- end: `0x1400033b2`
- name: `UpdateInterfaceIndexImpl`
- size: `110`
- prototype: `__int64 __fastcall(PVOID Entry, NET_IFINDEX ifIndex)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400033c0`
- `0x14000fdc4`

## callees

- `0x140003344`
- `0x14000f728`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000336f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000336f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000338a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000338a`
- `NDIS!NdisIfGetNetLuidFromInterfaceIndex` at `0x14000335f`
- `NDIS!NdisIfGetNetLuidFromInterfaceIndex` at `0x14000335f`

## pseudocode

```c
void __fastcall UpdateInterfaceIndexImpl(PVOID Entry, NET_IFINDEX ifIndex)
{
  KIRQL v3; // al
  KSPIN_LOCK *v4; // rcx
  NET_LUID pNetLuid; // [rsp+30h] [rbp+8h] BYREF

  pNetLuid.Value = 0;
  NdisIfGetNetLuidFromInterfaceIndex(ifIndex, &pNetLuid);
  v3 = KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)Entry + 10));
  v4 = (KSPIN_LOCK *)*((_QWORD *)Entry + 10);
  *((NET_LUID *)Entry + 9) = pNetLuid;
  KeReleaseSpinLock(v4, v3);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
    WanpDeleteConnEntry((char *)Entry);
}

```

## disassembly

```asm
0x140003344  push    rbx
0x140003346  sub     rsp, 20h
0x14000334a  mov     eax, edx
0x14000334c  mov     qword ptr [rsp+28h+pNetLuid], 0
0x140003355  mov     rbx, rcx
0x140003358  lea     rdx, [rsp+28h+pNetLuid]; pNetLuid
0x14000335d  mov     ecx, eax; ifIndex
0x14000335f  call    cs:__imp_NdisIfGetNetLuidFromInterfaceIndex
0x140003366  nop     dword ptr [rax+rax+00h]
0x14000336b  mov     rcx, [rbx+50h]; SpinLock
0x14000336f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003376  nop     dword ptr [rax+rax+00h]
0x14000337b  mov     rdx, qword ptr [rsp+28h+pNetLuid]
0x140003380  mov     rcx, [rbx+50h]; SpinLock
0x140003384  mov     [rbx+48h], rdx
0x140003388  mov     dl, al; NewIrql
0x14000338a  call    cs:__imp_KeReleaseSpinLock
0x140003391  nop     dword ptr [rax+rax+00h]
0x140003396  or      eax, 0FFFFFFFFh
0x140003399  lock xadd [rbx+60h], eax
0x14000339e  cmp     eax, 1
0x1400033a1  jnz     short loc_1400033AB
0x1400033a3  mov     rcx, rbx; Entry
0x1400033a6  call    WanpDeleteConnEntry
0x1400033ab  add     rsp, 20h
0x1400033af  pop     rbx
0x1400033b0  retn
```

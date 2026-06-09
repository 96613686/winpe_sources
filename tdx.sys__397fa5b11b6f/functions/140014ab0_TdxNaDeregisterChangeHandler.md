# TdxNaDeregisterChangeHandler

- ea: `0x140014ab0`
- end: `0x140014beb`
- name: `TdxNaDeregisterChangeHandler`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140015038`

## callees

- `0x140014958`
- `0x140014ab0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014abd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014abd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014ade`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014afc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014ade`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014afc`
- `NETIO!NsiDeregisterChangeNotification` at `0x140014b2b`
- `NETIO!NsiDeregisterChangeNotification` at `0x140014b4f`
- `NETIO!NsiDeregisterChangeNotification` at `0x140014b88`
- `NETIO!NsiDeregisterChangeNotification` at `0x140014bac`
- `NETIO!NsiDeregisterChangeNotification` at `0x140014bd0`
- `NETIO!NsiDeregisterChangeNotification` at `0x140014b2b`
- `NETIO!NsiDeregisterChangeNotification` at `0x140014b4f`
- `NETIO!NsiDeregisterChangeNotification` at `0x140014b88`
- `NETIO!NsiDeregisterChangeNotification` at `0x140014bac`
- `NETIO!NsiDeregisterChangeNotification` at `0x140014bd0`

## pseudocode

```c
void TdxNaDeregisterChangeHandler()
{
  KIRQL v0; // al
  __int64 v1; // rbx
  __int64 v2; // rcx

  v0 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  if ( !*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject, v0);
    return;
  }
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 16LL));
  v1 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject, v0);
  if ( WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink )
  {
    NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 10);
  }
  else if ( !*(_QWORD *)&WPP_MAIN_CB.SectorSize )
  {
    goto LABEL_9;
  }
  if ( *(_QWORD *)&WPP_MAIN_CB.SectorSize )
    NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 7);
LABEL_9:
  if ( WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink )
  {
    NsiDeregisterChangeNotification(&NPI_MS_IPV6_MODULEID, 10);
    if ( !WPP_MAIN_CB.DeviceObjectExtension )
    {
LABEL_14:
      if ( WPP_MAIN_CB.Reserved )
        NsiDeregisterChangeNotification(&NPI_MS_NDIS_MODULEID, 1);
      v2 = v1;
      goto LABEL_17;
    }
LABEL_13:
    NsiDeregisterChangeNotification(&NPI_MS_IPV6_MODULEID, 7);
    goto LABEL_14;
  }
  if ( WPP_MAIN_CB.DeviceObjectExtension )
    goto LABEL_13;
  v2 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
LABEL_17:
  TdxDereferenceNaProviderContext(v2);
}

```

## disassembly

```asm
0x140014ab0  push    rbx
0x140014ab2  sub     rsp, 20h
0x140014ab6  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x140014abd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014ac4  nop     dword ptr [rax+rax+00h]
0x140014ac9  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140014ad0  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x140014ad7  test    rdx, rdx
0x140014ada  jnz     short loc_140014AEF
0x140014adc  mov     dl, al; NewIrql
0x140014ade  call    cs:__imp_KeReleaseSpinLock
0x140014ae5  nop     dword ptr [rax+rax+00h]
0x140014aea  jmp     loc_140014BE4
0x140014aef  lock inc dword ptr [rdx+10h]
0x140014af3  mov     rbx, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140014afa  mov     dl, al; NewIrql
0x140014afc  call    cs:__imp_KeReleaseSpinLock
0x140014b03  nop     dword ptr [rax+rax+00h]
0x140014b08  mov     r8, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140014b0f  test    r8, r8
0x140014b12  jnz     short loc_140014B1F
0x140014b14  cmp     qword ptr cs:WPP_MAIN_CB.SectorSize, r8
0x140014b1b  jz      short loc_140014B5B
0x140014b1d  jmp     short loc_140014B37
0x140014b1f  mov     edx, 0Ah
0x140014b24  lea     rcx, NPI_MS_IPV4_MODULEID
0x140014b2b  call    cs:__imp_NsiDeregisterChangeNotification
0x140014b32  nop     dword ptr [rax+rax+00h]
0x140014b37  mov     r8, qword ptr cs:WPP_MAIN_CB.SectorSize
0x140014b3e  test    r8, r8
0x140014b41  jz      short loc_140014B5B
0x140014b43  mov     edx, 7
0x140014b48  lea     rcx, NPI_MS_IPV4_MODULEID
0x140014b4f  call    cs:__imp_NsiDeregisterChangeNotification
0x140014b56  nop     dword ptr [rax+rax+00h]
0x140014b5b  mov     r8, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink
0x140014b62  test    r8, r8
0x140014b65  jnz     short loc_140014B7C
0x140014b67  mov     r8, cs:WPP_MAIN_CB.DeviceObjectExtension
0x140014b6e  test    r8, r8
0x140014b71  jnz     short loc_140014BA0
0x140014b73  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140014b7a  jmp     short loc_140014BDF
0x140014b7c  mov     edx, 0Ah
0x140014b81  lea     rcx, NPI_MS_IPV6_MODULEID
0x140014b88  call    cs:__imp_NsiDeregisterChangeNotification
0x140014b8f  nop     dword ptr [rax+rax+00h]
0x140014b94  mov     r8, cs:WPP_MAIN_CB.DeviceObjectExtension
0x140014b9b  test    r8, r8
0x140014b9e  jz      short loc_140014BB8
0x140014ba0  mov     edx, 7
0x140014ba5  lea     rcx, NPI_MS_IPV6_MODULEID
0x140014bac  call    cs:__imp_NsiDeregisterChangeNotification
0x140014bb3  nop     dword ptr [rax+rax+00h]
0x140014bb8  mov     r8, cs:WPP_MAIN_CB.Reserved
0x140014bbf  test    r8, r8
0x140014bc2  jz      short loc_140014BDC
0x140014bc4  mov     edx, 1
0x140014bc9  lea     rcx, NPI_MS_NDIS_MODULEID
0x140014bd0  call    cs:__imp_NsiDeregisterChangeNotification
0x140014bd7  nop     dword ptr [rax+rax+00h]
0x140014bdc  mov     rcx, rbx
0x140014bdf  call    TdxDereferenceNaProviderContext
0x140014be4  add     rsp, 20h
0x140014be8  pop     rbx
0x140014be9  retn
```

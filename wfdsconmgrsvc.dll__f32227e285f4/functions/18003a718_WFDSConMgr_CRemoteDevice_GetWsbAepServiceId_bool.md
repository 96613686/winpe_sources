# WFDSConMgr::CRemoteDevice::GetWsbAepServiceId(bool &)

- ea: `0x18003a718`
- end: `0x18003a7a1`
- name: `?GetWsbAepServiceId@CRemoteDevice@WFDSConMgr@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z`
- size: `137`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005a3f0`

## callees

- `0x180004c7c`
- `0x18003a718`
- `0x18005c888`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003a789`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003a789`

## string_xrefs

- `0x18003a745`: `Attempted to get WSB AEP Service ID before doing the query, should not happen as caller must always ensure query was complete`
- `0x18003a75e`: `WFDSConMgr::CRemoteDevice::GetWsbAepServiceId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RTL_SRWLOCK *__fastcall WFDSConMgr::CRemoteDevice::GetWsbAepServiceId(RTL_SRWLOCK *a1, _BYTE *a2)
{
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-18h] BYREF
  char v6; // [rsp+38h] [rbp-10h]

  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(
    (__int64)&SRWLock,
    a1 + 6);
  if ( !LOBYTE(a1[27].Ptr) )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CRemoteDevice::GetWsbAepServiceId",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\remotedevice.cpp",
      132,
      L"Attempted to get WSB AEP Service ID before doing the query, should not happen as caller must always ensure query was complete",
      a1);
  *a2 = a1[61].Ptr;
  if ( v6 && SRWLock )
    ReleaseSRWLockShared(SRWLock);
  return a1 + 57;
}

```

## disassembly

```asm
0x18003a718  mov     [rsp+arg_0], rbx
0x18003a71d  push    rdi
0x18003a71e  sub     rsp, 40h
0x18003a722  mov     rdi, rdx
0x18003a725  mov     rbx, rcx
0x18003a728  lea     rdx, [rcx+30h]
0x18003a72c  lea     rcx, [rsp+48h+SRWLock]
0x18003a731  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(WFDSConMgr::ReadersWriterLock &)
0x18003a736  nop
0x18003a737  cmp     byte ptr [rbx+0D8h], 0
0x18003a73e  jnz     short loc_18003A770
0x18003a740  mov     [rsp+48h+var_20], rbx; void *
0x18003a745  lea     rax, aAttemptedToGet_2; "Attempted to get WSB AEP Service ID bef"...
0x18003a74c  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18003a751  mov     r9d, 284h; char
0x18003a757  lea     r8, aOnecoreuapNetW_17; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18003a75e  lea     rdx, aWfdsconmgrCrem_2; "WFDSConMgr::CRemoteDevice::GetWsbAepSer"...
0x18003a765  mov     ecx, 8007139Fh; char
0x18003a76a  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003a770  mov     al, [rbx+1E8h]
0x18003a776  mov     [rdi], al
0x18003a778  cmp     [rsp+48h+var_10], 0
0x18003a77d  jz      short loc_18003A78F
0x18003a77f  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18003a784  test    rcx, rcx
0x18003a787  jz      short loc_18003A78F
0x18003a789  call    cs:__imp_ReleaseSRWLockShared
0x18003a78f  lea     rax, [rbx+1C8h]
0x18003a796  mov     rbx, [rsp+48h+arg_0]
0x18003a79b  add     rsp, 40h
0x18003a79f  pop     rdi
0x18003a7a0  retn
```

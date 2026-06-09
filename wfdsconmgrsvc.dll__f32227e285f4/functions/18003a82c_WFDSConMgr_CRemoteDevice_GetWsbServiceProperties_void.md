# WFDSConMgr::CRemoteDevice::GetWsbServiceProperties(void)

- ea: `0x18003a82c`
- end: `0x18003a8a1`
- name: `?GetWsbServiceProperties@CRemoteDevice@WFDSConMgr@@QEBAAEBVCServiceProperties@2@XZ`
- size: `117`
- prototype: `const struct WFDSConMgr::CServiceProperties *__fastcall(WFDSConMgr::CRemoteDevice *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18005a6e0`

## callees

- `0x180004c7c`
- `0x18003a82c`
- `0x18005c888`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003a88e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003a88e`

## string_xrefs

- `0x18003a852`: `Attempted to get WSB service parameters before doing the query`
- `0x18003a86b`: `WFDSConMgr::CRemoteDevice::GetWsbServiceProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RTL_SRWLOCK *__fastcall WFDSConMgr::CRemoteDevice::GetWsbServiceProperties(RTL_SRWLOCK *this)
{
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-18h] BYREF
  char v4; // [rsp+38h] [rbp-10h]

  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(
    (__int64)&SRWLock,
    this + 6);
  if ( !BYTE1(this[61].Ptr) )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CRemoteDevice::GetWsbServiceProperties",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\remotedevice.cpp",
      1,
      L"Attempted to get WSB service parameters before doing the query",
      this);
  if ( v4 && SRWLock )
    ReleaseSRWLockShared(SRWLock);
  return this + 62;
}

```

## disassembly

```asm
0x18003a82c  push    rbx
0x18003a82e  sub     rsp, 40h
0x18003a832  mov     rbx, rcx
0x18003a835  lea     rdx, [rcx+30h]
0x18003a839  lea     rcx, [rsp+48h+SRWLock]
0x18003a83e  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(WFDSConMgr::ReadersWriterLock &)
0x18003a843  nop
0x18003a844  cmp     byte ptr [rbx+1E9h], 0
0x18003a84b  jnz     short loc_18003A87D
0x18003a84d  mov     [rsp+48h+var_20], rbx; void *
0x18003a852  lea     rax, aAttemptedToGet_1; "Attempted to get WSB service parameters"...
0x18003a859  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18003a85e  mov     r9d, 301h; char
0x18003a864  lea     r8, aOnecoreuapNetW_17; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18003a86b  lea     rdx, aWfdsconmgrCrem_0; "WFDSConMgr::CRemoteDevice::GetWsbServic"...
0x18003a872  mov     ecx, 8007139Fh; char
0x18003a877  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003a87d  cmp     [rsp+48h+var_10], 0
0x18003a882  jz      short loc_18003A894
0x18003a884  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18003a889  test    rcx, rcx
0x18003a88c  jz      short loc_18003A894
0x18003a88e  call    cs:__imp_ReleaseSRWLockShared
0x18003a894  lea     rax, [rbx+1F0h]
0x18003a89b  add     rsp, 40h
0x18003a89f  pop     rbx
0x18003a8a0  retn
```

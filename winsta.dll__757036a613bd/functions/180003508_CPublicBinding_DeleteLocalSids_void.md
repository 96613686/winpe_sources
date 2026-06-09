# CPublicBinding::DeleteLocalSids(void)

- ea: `0x180003508`
- end: `0x180003558`
- name: `?DeleteLocalSids@CPublicBinding@@SAXXZ`
- size: `80`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180003494`

## callees

- `0x180003508`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18000352e`
- `ntdll!RtlFreeSid` at `0x18000352e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003540`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003540`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000354d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000354d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000351c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000351c`

## pseudocode

```c
void CPublicBinding::DeleteLocalSids(void)
{
  if ( CPublicBinding::bCritSecInitialized )
  {
    EnterCriticalSection(&CPublicBinding::m_CritSec);
    if ( CPublicBinding::pSystemSid )
      RtlFreeSid(CPublicBinding::pSystemSid);
    if ( CPublicBinding::pNetsrvSid )
      LocalFree(CPublicBinding::pNetsrvSid);
    LeaveCriticalSection(&CPublicBinding::m_CritSec);
  }
}

```

## disassembly

```asm
0x180003508  sub     rsp, 28h
0x18000350c  cmp     cs:?bCritSecInitialized@CPublicBinding@@1HA, 0; int CPublicBinding::bCritSecInitialized
0x180003513  jz      short loc_180003553
0x180003515  lea     rcx, ?m_CritSec@CPublicBinding@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000351c  call    cs:__imp_EnterCriticalSection
0x180003522  mov     rcx, cs:?pSystemSid@CPublicBinding@@1PEAXEA; Sid
0x180003529  test    rcx, rcx
0x18000352c  jz      short loc_180003534
0x18000352e  call    cs:__imp_RtlFreeSid
0x180003534  mov     rcx, cs:?pNetsrvSid@CPublicBinding@@1PEAXEA; hMem
0x18000353b  test    rcx, rcx
0x18000353e  jz      short loc_180003546
0x180003540  call    cs:__imp_LocalFree
0x180003546  lea     rcx, ?m_CritSec@CPublicBinding@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000354d  call    cs:__imp_LeaveCriticalSection
0x180003553  add     rsp, 28h
0x180003557  retn
```

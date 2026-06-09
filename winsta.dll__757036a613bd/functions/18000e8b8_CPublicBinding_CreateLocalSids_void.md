# CPublicBinding::CreateLocalSids(void)

- ea: `0x18000e8b8`
- end: `0x18000e941`
- name: `?CreateLocalSids@CPublicBinding@@SAJXZ`
- size: `137`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180008150`
- `0x180008e30`
- `0x180008f10`
- `0x18001f5f8`

## callees

- `0x180007890`
- `0x18000e8b8`
- `0x18000e948`
- `0x18000e9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e906`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e906`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8db`

## string_xrefs

- `0x18000e924`: `CUtils::CreateNetworkServiceSid failed: 0x%x in %s`
- `0x18000e92b`: `CPublicBinding::CreateLocalSids`
- `0x18000e91b`: `CUtils::CreateSystemSid failed: 0x%x in %s`

## pseudocode

```c
__int64 CPublicBinding::CreateLocalSids(void)
{
  unsigned int v1; // ebx
  void **v2; // rcx
  int NetworkServiceSid; // eax
  int SystemSid; // eax

  if ( !CPublicBinding::bCritSecInitialized )
    return 2147500037LL;
  v1 = 0;
  EnterCriticalSection(&CPublicBinding::m_CritSec);
  if ( CPublicBinding::pSystemSid || (SystemSid = CUtils::CreateSystemSid(v2), v1 = SystemSid, SystemSid >= 0) )
  {
    if ( !CPublicBinding::pNetsrvSid )
    {
      NetworkServiceSid = CUtils::CreateNetworkServiceSid(v2);
      v1 = NetworkServiceSid;
      if ( NetworkServiceSid < 0 )
        _DbgPrintMessage(
          8,
          "CUtils::CreateNetworkServiceSid failed: 0x%x in %s",
          (unsigned int)NetworkServiceSid,
          "CPublicBinding::CreateLocalSids");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "CUtils::CreateSystemSid failed: 0x%x in %s",
      (unsigned int)SystemSid,
      "CPublicBinding::CreateLocalSids");
  }
  LeaveCriticalSection(&CPublicBinding::m_CritSec);
  return v1;
}

```

## disassembly

```asm
0x18000e8b8  push    rbx
0x18000e8ba  sub     rsp, 20h
0x18000e8be  cmp     cs:?bCritSecInitialized@CPublicBinding@@1HA, 0; int CPublicBinding::bCritSecInitialized
0x18000e8c5  jnz     short loc_18000E8D2
0x18000e8c7  mov     eax, 80004005h
0x18000e8cc  add     rsp, 20h
0x18000e8d0  pop     rbx
0x18000e8d1  retn
0x18000e8d2  lea     rcx, ?m_CritSec@CPublicBinding@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e8d9  xor     ebx, ebx
0x18000e8db  call    cs:__imp_EnterCriticalSection
0x18000e8e1  cmp     cs:?pSystemSid@CPublicBinding@@1PEAXEA, rbx; void * CPublicBinding::pSystemSid
0x18000e8e8  jz      short loc_18000E910
0x18000e8ea  cmp     cs:?pNetsrvSid@CPublicBinding@@1PEAXEA, 0; void * CPublicBinding::pNetsrvSid
0x18000e8f2  jnz     short loc_18000E8FF
0x18000e8f4  call    ?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateNetworkServiceSid(void * *)
0x18000e8f9  mov     ebx, eax
0x18000e8fb  test    eax, eax
0x18000e8fd  js      short loc_18000E924
0x18000e8ff  lea     rcx, ?m_CritSec@CPublicBinding@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e906  call    cs:__imp_LeaveCriticalSection
0x18000e90c  mov     eax, ebx
0x18000e90e  jmp     short loc_18000E8CC
0x18000e910  call    ?CreateSystemSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateSystemSid(void * *)
0x18000e915  mov     ebx, eax
0x18000e917  test    eax, eax
0x18000e919  jns     short loc_18000E8EA
0x18000e91b  lea     rdx, aCutilsCreatesy; "CUtils::CreateSystemSid failed: 0x%x in"...
0x18000e922  jmp     short loc_18000E92B
0x18000e924  lea     rdx, aCutilsCreatene; "CUtils::CreateNetworkServiceSid failed:"...
0x18000e92b  lea     r9, aCpublicbinding; "CPublicBinding::CreateLocalSids"
0x18000e932  mov     r8d, eax
0x18000e935  mov     ecx, 8; int
0x18000e93a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e93f  jmp     short loc_18000E8FF
```

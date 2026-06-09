# WinStationConsumeCacheSession

- ea: `0x18002b680`
- end: `0x18002b789`
- name: `WinStationConsumeCacheSession`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18002b680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6b3`
- `RPCRT4!NdrClientCall3` at `0x18002b6fb`
- `RPCRT4!NdrClientCall3` at `0x18002b6fb`

## string_xrefs

- `0x18002b6a4`: `Failed to open binding`
- `0x18002b71a`: `RpcConsumeCacheSession threw an exception: 0x%x`
- `0x18002b740`: `WinStationConsumeCacheSession`
- `0x18002b74a`: `RpcConsumeCacheSession failed: 0x%x in %s`

## pseudocode

```c
__int64 WinStationConsumeCacheSession()
{
  signed int LastError; // eax
  signed int Pointer; // ebx
  __int64 v2; // rax
  unsigned int v3; // ebx
  unsigned __int16 v5[16]; // [rsp+28h] [rbp-20h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v5, 0, 0);
  if ( CSmartPublicBinding::operator void *(v5) )
  {
    v2 = CSmartPublicBinding::operator void *(v5);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351D0, 4u, 0, v2).Pointer;
    if ( Pointer >= 0 )
      goto LABEL_8;
    _DbgPrintMessage(8, "RpcConsumeCacheSession failed: 0x%x in %s", Pointer, "WinStationConsumeCacheSession");
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
  }
  if ( Pointer < 0 )
  {
    v3 = ConvertHRESULT2WIN32(Pointer);
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v5);
    return v3;
  }
LABEL_8:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v5);
  return 0;
}

```

## disassembly

```asm
0x18002b680  push    rbx
0x18002b682  sub     rsp, 40h
0x18002b686  xor     r8d, r8d; int
0x18002b689  xor     edx, edx; void *
0x18002b68b  lea     rcx, [rsp+48h+var_20]; this
0x18002b690  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002b695  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18002b69a  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002b69f  test    rax, rax
0x18002b6a2  jnz     short loc_18002B6D7
0x18002b6a4  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002b6ab  lea     ecx, [rax+8]; int
0x18002b6ae  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b6b3  call    cs:__imp_GetLastError
0x18002b6ba  nop     dword ptr [rax+rax+00h]
0x18002b6bf  mov     ebx, eax
0x18002b6c1  test    eax, eax
0x18002b6c3  jle     loc_18002B75B
0x18002b6c9  movzx   ebx, ax
0x18002b6cc  or      ebx, 80070000h
0x18002b6d2  jmp     loc_18002B75B
0x18002b6d7  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18002b6dc  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002b6e1  mov     [rsp+48h+arg_0], 0
0x18002b6ea  mov     r9, rax
0x18002b6ed  xor     r8d, r8d; pReturnValue
0x18002b6f0  lea     edx, [r8+4]; nProcNum
0x18002b6f4  lea     rcx, stru_1800351D0; pProxyInfo
0x18002b6fb  call    cs:__imp_NdrClientCall3
0x18002b702  nop     dword ptr [rax+rax+00h]
0x18002b707  mov     rbx, rax
0x18002b70a  mov     [rsp+48h+arg_0], rax
0x18002b70f  mov     [rsp+48h+var_28], eax
0x18002b713  jmp     short loc_18002B73C
0x18002b715  mov     ebx, eax
0x18002b717  mov     r8d, eax
0x18002b71a  lea     rdx, aRpcconsumecach; "RpcConsumeCacheSession threw an excepti"...
0x18002b721  mov     ecx, 8; int
0x18002b726  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b72b  test    ebx, ebx
0x18002b72d  jle     short loc_18002B738
0x18002b72f  movzx   ebx, bx
0x18002b732  or      ebx, 80070000h
0x18002b738  mov     [rsp+48h+var_28], ebx
0x18002b73c  test    ebx, ebx
0x18002b73e  jns     short loc_18002B776
0x18002b740  lea     r9, aWinstationcons_0; "WinStationConsumeCacheSession"
0x18002b747  mov     r8d, ebx
0x18002b74a  lea     rdx, aRpcconsumecach_0; "RpcConsumeCacheSession failed: 0x%x in "...
0x18002b751  mov     ecx, 8; int
0x18002b756  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b75b  test    ebx, ebx
0x18002b75d  jns     short loc_18002B776
0x18002b75f  mov     ecx, ebx; int
0x18002b761  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002b766  mov     ebx, eax
0x18002b768  lea     rcx, [rsp+48h+var_20]; this
0x18002b76d  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002b772  mov     eax, ebx
0x18002b774  jmp     short loc_18002B782
0x18002b776  lea     rcx, [rsp+48h+var_20]; this
0x18002b77b  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002b780  xor     eax, eax
0x18002b782  add     rsp, 40h
0x18002b786  pop     rbx
0x18002b787  retn
0x18003372f  push    rbp
0x180033731  sub     rsp, 20h
0x180033735  mov     rbp, rdx
0x180033738  mov     rcx, [rcx]
0x18003373b  mov     ecx, [rcx]; ExceptionCode
0x18003373d  call    cs:__imp_I_RpcExceptionFilter
0x180033744  nop     dword ptr [rax+rax+00h]
0x180033749  nop
0x18003374a  add     rsp, 20h
0x18003374e  pop     rbp
0x18003374f  retn
```

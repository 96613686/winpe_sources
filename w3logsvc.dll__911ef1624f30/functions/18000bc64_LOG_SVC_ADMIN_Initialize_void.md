# LOG_SVC_ADMIN::Initialize(void)

- ea: `0x18000bc64`
- end: `0x18000be18`
- name: `?Initialize@LOG_SVC_ADMIN@@QEAAJXZ`
- size: `436`
- prototype: `signed int __fastcall(LOG_SVC_ADMIN *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001bd0`

## callees

- `0x180001008`
- `0x18000bc64`
- `0x18000c1b4`
- `0x18000c944`
- `0x18000d718`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bc92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bcdd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bc92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bcdd`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x18000bd03`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x18000bd03`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18000bd82`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18000bdd3`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18000bd82`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18000bdd3`

## string_xrefs

- `0x18000bcfc`: `System\CurrentControlSet\Services\W3LogSvc\Parameters`

## pseudocode

```c
signed int __fastcall LOG_SVC_ADMIN::Initialize(LOG_SVC_ADMIN *this)
{
  _QWORD *v1; // rbx
  HANDLE EventW; // rax
  signed int result; // eax
  HANDLE v4; // rax
  LOG_SVC_ADMIN *v5; // rcx
  LOG_SVC_ADMIN *v6; // rcx
  ALLOC_CACHE_HANDLER *v7; // rax
  ALLOC_CACHE_HANDLER *v8; // rax
  int v9; // [rsp+28h] [rbp-20h] BYREF
  int v10; // [rsp+2Ch] [rbp-1Ch]
  int v11; // [rsp+30h] [rbp-18h]

  v1 = g_pLogSvcAdmin;
  EventW = CreateEventW(0, 1, 0, 0);
  v1[262] = EventW;
  if ( !EventW || (v4 = CreateEventW(0, 1, 0, 0), (v1[236] = v4) == 0) )
  {
    if ( GetLastError() )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    return -2147467259;
  }
  *((_DWORD *)v1 + 3) = ReadDwordParameterValueFromAnyService(
                          L"System\\CurrentControlSet\\Services\\W3LogSvc\\Parameters",
                          L"LogBufferSize",
                          0x10000u);
  if ( (unsigned int)McGenEventRegister_EventRegister() )
    return -2147467259;
  result = LOG_SVC_ADMIN::QueryComputerName(v5, (struct STRU *)(v1 + 212), ComputerNameDnsDomain);
  if ( result >= 0 )
  {
    result = LOG_SVC_ADMIN::QueryComputerName(v6, (struct STRU *)(v1 + 223), ComputerNameDnsHostname);
    if ( result >= 0 )
    {
      v9 = 0;
      v11 = 48;
      v10 = 250;
      v7 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
      if ( v7 )
        v7 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
               v7,
               "MULTI_WORK_ITEM",
               (const struct ALLOC_CACHE_CONFIGURATION *)&v9,
               1);
      MULTI_WORK_ITEM::sm_pAllocCacheHandler = v7;
      if ( !v7 )
        return -2147024882;
      v9 = 0;
      v11 = 1200;
      v10 = 1000;
      v8 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
      if ( v8 )
        v8 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
               v8,
               "HTTP_LOG_CONTEXT",
               (const struct ALLOC_CACHE_CONFIGURATION *)&v9,
               1);
      HTTP_LOG_CONTEXT::sm_pAllocCacheHandler = v8;
      if ( v8 )
      {
        HTTP_LOG_CONTEXT::sm_pTraceLog = 0;
        return LOG_SVC_ADMIN::InitializePipeClientHashTable(v1);
      }
      else
      {
        return -2147024882;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bc64  mov     [rsp+arg_0], rbx
0x18000bc69  push    rsi
0x18000bc6a  sub     rsp, 40h
0x18000bc6e  mov     rax, cs:__security_cookie
0x18000bc75  xor     rax, rsp
0x18000bc78  mov     [rsp+48h+var_10], rax
0x18000bc7d  mov     rbx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000bc84  xor     r9d, r9d; lpName
0x18000bc87  xor     r8d, r8d; bInitialState
0x18000bc8a  lea     esi, [r9+1]
0x18000bc8e  mov     edx, esi; bManualReset
0x18000bc90  xor     ecx, ecx; lpEventAttributes
0x18000bc92  call    cs:__imp_CreateEventW
0x18000bc98  mov     [rbx+830h], rax
0x18000bc9f  test    rax, rax
0x18000bca2  jnz     short loc_18000BCD3
0x18000bca4  call    cs:__imp_GetLastError
0x18000bcaa  test    eax, eax
0x18000bcac  jz      short loc_18000BCC9
0x18000bcae  call    cs:__imp_GetLastError
0x18000bcb4  test    eax, eax
0x18000bcb6  jle     loc_18000BE00
0x18000bcbc  movzx   eax, ax
0x18000bcbf  or      eax, 80070000h
0x18000bcc4  jmp     loc_18000BE00
0x18000bcc9  mov     eax, 80004005h
0x18000bcce  jmp     loc_18000BE00
0x18000bcd3  xor     r9d, r9d; lpName
0x18000bcd6  xor     r8d, r8d; bInitialState
0x18000bcd9  mov     edx, esi; bManualReset
0x18000bcdb  xor     ecx, ecx; lpEventAttributes
0x18000bcdd  call    cs:__imp_CreateEventW
0x18000bce3  mov     [rbx+760h], rax
0x18000bcea  test    rax, rax
0x18000bced  jz      short loc_18000BCA4
0x18000bcef  mov     r8d, 10000h
0x18000bcf5  lea     rdx, aLogbuffersize; "LogBufferSize"
0x18000bcfc  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\W3"...
0x18000bd03  call    cs:__imp_?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z; ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)
0x18000bd09  mov     [rbx+0Ch], eax
0x18000bd0c  call    McGenEventRegister_EventRegister
0x18000bd11  test    eax, eax
0x18000bd13  jnz     short loc_18000BCC9
0x18000bd15  lea     rdx, [rbx+6A0h]; struct STRU *
0x18000bd1c  lea     r8d, [rax+2]; enum _COMPUTER_NAME_FORMAT
0x18000bd20  call    ?QueryComputerName@LOG_SVC_ADMIN@@AEAAJPEAVSTRU@@W4_COMPUTER_NAME_FORMAT@@@Z; LOG_SVC_ADMIN::QueryComputerName(STRU *,_COMPUTER_NAME_FORMAT)
0x18000bd25  test    eax, eax
0x18000bd27  js      loc_18000BE00
0x18000bd2d  lea     rdx, [rbx+6F8h]; struct STRU *
0x18000bd34  mov     r8d, esi; enum _COMPUTER_NAME_FORMAT
0x18000bd37  call    ?QueryComputerName@LOG_SVC_ADMIN@@AEAAJPEAVSTRU@@W4_COMPUTER_NAME_FORMAT@@@Z; LOG_SVC_ADMIN::QueryComputerName(STRU *,_COMPUTER_NAME_FORMAT)
0x18000bd3c  test    eax, eax
0x18000bd3e  js      loc_18000BE00
0x18000bd44  mov     [rsp+48h+var_20], 0
0x18000bd4c  mov     [rsp+48h+var_18], 30h ; '0'
0x18000bd54  mov     [rsp+48h+var_1C], 0FAh
0x18000bd5c  mov     ecx, 100h; Size
0x18000bd61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bd66  mov     [rsp+48h+var_28], rax
0x18000bd6b  test    rax, rax
0x18000bd6e  jz      short loc_18000BD89
0x18000bd70  mov     r9d, esi
0x18000bd73  lea     r8, [rsp+48h+var_20]
0x18000bd78  lea     rdx, aMultiWorkItem; "MULTI_WORK_ITEM"
0x18000bd7f  mov     rcx, rax
0x18000bd82  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18000bd88  nop
0x18000bd89  mov     cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x18000bd90  test    rax, rax
0x18000bd93  jz      short loc_18000BDFB
0x18000bd95  mov     [rsp+48h+var_20], 0
0x18000bd9d  mov     [rsp+48h+var_18], 4B0h
0x18000bda5  mov     [rsp+48h+var_1C], 3E8h
0x18000bdad  mov     ecx, 100h; Size
0x18000bdb2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bdb7  mov     [rsp+48h+var_28], rax
0x18000bdbc  test    rax, rax
0x18000bdbf  jz      short loc_18000BDDA
0x18000bdc1  mov     r9d, esi
0x18000bdc4  lea     r8, [rsp+48h+var_20]
0x18000bdc9  lea     rdx, aHttpLogContext_1; "HTTP_LOG_CONTEXT"
0x18000bdd0  mov     rcx, rax
0x18000bdd3  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18000bdd9  nop
0x18000bdda  mov     cs:?sm_pAllocCacheHandler@HTTP_LOG_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * HTTP_LOG_CONTEXT::sm_pAllocCacheHandler
0x18000bde1  test    rax, rax
0x18000bde4  jz      short loc_18000BDFB
0x18000bde6  mov     cs:?sm_pTraceLog@HTTP_LOG_CONTEXT@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * HTTP_LOG_CONTEXT::sm_pTraceLog
0x18000bdf1  mov     rcx, rbx; pv
0x18000bdf4  call    ?InitializePipeClientHashTable@LOG_SVC_ADMIN@@AEAAJXZ; LOG_SVC_ADMIN::InitializePipeClientHashTable(void)
0x18000bdf9  jmp     short loc_18000BE00
0x18000bdfb  mov     eax, 8007000Eh
0x18000be00  mov     rcx, [rsp+48h+var_10]
0x18000be05  xor     rcx, rsp; StackCookie
0x18000be08  call    __security_check_cookie
0x18000be0d  mov     rbx, [rsp+48h+arg_0]
0x18000be12  add     rsp, 40h
0x18000be16  pop     rsi
0x18000be17  retn
```

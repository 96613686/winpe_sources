# WinStationConsumeCacheSession

- ea: `0x180029a30`
- end: `0x180029b29`
- name: `WinStationConsumeCacheSession`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180029a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a63`
- `RPCRT4!NdrClientCall3` at `0x180029aa2`
- `RPCRT4!NdrClientCall3` at `0x180029aa2`

## string_xrefs

- `0x180029a54`: `Failed to open binding`
- `0x180029abb`: `RpcConsumeCacheSession threw an exception: 0x%x`
- `0x180029ae1`: `WinStationConsumeCacheSession`
- `0x180029aeb`: `RpcConsumeCacheSession failed: 0x%x in %s`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800321A0, 4u, 0, v2).Pointer;
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
0x180029a30  push    rbx
0x180029a32  sub     rsp, 40h
0x180029a36  xor     r8d, r8d; int
0x180029a39  xor     edx, edx; void *
0x180029a3b  lea     rcx, [rsp+48h+var_20]; this
0x180029a40  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180029a45  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180029a4a  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029a4f  test    rax, rax
0x180029a52  jnz     short loc_180029A7E
0x180029a54  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180029a5b  lea     ecx, [rax+8]; int
0x180029a5e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029a63  call    cs:__imp_GetLastError
0x180029a69  mov     ebx, eax
0x180029a6b  test    eax, eax
0x180029a6d  jle     loc_180029AFC
0x180029a73  movzx   ebx, ax
0x180029a76  or      ebx, 80070000h
0x180029a7c  jmp     short loc_180029AFC
0x180029a7e  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180029a83  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029a88  mov     [rsp+48h+arg_0], 0
0x180029a91  mov     r9, rax
0x180029a94  xor     r8d, r8d; pReturnValue
0x180029a97  lea     edx, [r8+4]; nProcNum
0x180029a9b  lea     rcx, stru_1800321A0; pProxyInfo
0x180029aa2  call    cs:__imp_NdrClientCall3
0x180029aa8  mov     rbx, rax
0x180029aab  mov     [rsp+48h+arg_0], rax
0x180029ab0  mov     [rsp+48h+var_28], eax
0x180029ab4  jmp     short loc_180029ADD
0x180029ab6  mov     ebx, eax
0x180029ab8  mov     r8d, eax
0x180029abb  lea     rdx, aRpcconsumecach; "RpcConsumeCacheSession threw an excepti"...
0x180029ac2  mov     ecx, 8; int
0x180029ac7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029acc  test    ebx, ebx
0x180029ace  jle     short loc_180029AD9
0x180029ad0  movzx   ebx, bx
0x180029ad3  or      ebx, 80070000h
0x180029ad9  mov     [rsp+48h+var_28], ebx
0x180029add  test    ebx, ebx
0x180029adf  jns     short loc_180029B17
0x180029ae1  lea     r9, aWinstationcons_0; "WinStationConsumeCacheSession"
0x180029ae8  mov     r8d, ebx
0x180029aeb  lea     rdx, aRpcconsumecach_0; "RpcConsumeCacheSession failed: 0x%x in "...
0x180029af2  mov     ecx, 8; int
0x180029af7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029afc  test    ebx, ebx
0x180029afe  jns     short loc_180029B17
0x180029b00  mov     ecx, ebx; int
0x180029b02  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180029b07  mov     ebx, eax
0x180029b09  lea     rcx, [rsp+48h+var_20]; this
0x180029b0e  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180029b13  mov     eax, ebx
0x180029b15  jmp     short loc_180029B23
0x180029b17  lea     rcx, [rsp+48h+var_20]; this
0x180029b1c  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180029b21  xor     eax, eax
0x180029b23  add     rsp, 40h
0x180029b27  pop     rbx
0x180029b28  retn
0x18003082f  push    rbp
0x180030831  sub     rsp, 20h
0x180030835  mov     rbp, rdx
0x180030838  mov     rcx, [rcx]
0x18003083b  mov     ecx, [rcx]; ExceptionCode
0x18003083d  call    cs:__imp_I_RpcExceptionFilter
0x180030843  nop
0x180030844  add     rsp, 20h
0x180030848  pop     rbp
0x180030849  retn
```

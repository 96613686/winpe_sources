# WinStationRedirectLogonBeginPainting

- ea: `0x180029e60`
- end: `0x180029f2c`
- name: `WinStationRedirectLogonBeginPainting`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180029e60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e9a`
- `RPCRT4!NdrClientCall3` at `0x180029ef4`
- `RPCRT4!NdrClientCall3` at `0x180029ef4`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180029e6d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180029e6d`

## string_xrefs

- `0x180029ebd`: `Failed to open binding failed: 0x%x in %s`

## pseudocode

```c
__int64 WinStationRedirectLogonBeginPainting()
{
  signed int Pointer; // ebx
  signed int LastError; // eax
  void *v2; // rax
  unsigned __int16 v4[16]; // [rsp+28h] [rbp-20h] BYREF

  Pointer = 0;
  if ( GetSystemMetrics(4096) )
  {
    CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v4, 0, 1);
    if ( CSmartPublicBinding::operator void *(v4) )
      goto LABEL_7;
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
    if ( Pointer >= 0 )
    {
LABEL_7:
      v2 = CSmartPublicBinding::operator void *(v4);
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032170, 4u, 0, v2).Pointer;
    }
    else
    {
      _DbgPrintMessage(8, "Failed to open binding failed: 0x%x in %s", Pointer, "WinStationRedirectLogonBeginPainting");
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v4);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180029e60  push    rbx
0x180029e62  sub     rsp, 40h
0x180029e66  xor     ebx, ebx
0x180029e68  mov     ecx, 1000h; nIndex
0x180029e6d  call    cs:__imp_GetSystemMetrics
0x180029e73  test    eax, eax
0x180029e75  jz      loc_180029F24
0x180029e7b  xor     edx, edx; void *
0x180029e7d  lea     r8d, [rbx+1]; int
0x180029e81  lea     rcx, [rsp+48h+var_20]; this
0x180029e86  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180029e8b  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180029e90  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029e95  test    rax, rax
0x180029e98  jnz     short loc_180029ED0
0x180029e9a  call    cs:__imp_GetLastError
0x180029ea0  mov     ebx, eax
0x180029ea2  test    eax, eax
0x180029ea4  jle     short loc_180029EAF
0x180029ea6  movzx   ebx, ax
0x180029ea9  or      ebx, 80070000h
0x180029eaf  test    ebx, ebx
0x180029eb1  jns     short loc_180029ED0
0x180029eb3  lea     r9, aWinstationredi_6; "WinStationRedirectLogonBeginPainting"
0x180029eba  mov     r8d, ebx
0x180029ebd  lea     rdx, aFailedToOpenBi; "Failed to open binding failed: 0x%x in "...
0x180029ec4  mov     ecx, 8; int
0x180029ec9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029ece  jmp     short loc_180029F1A
0x180029ed0  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180029ed5  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029eda  mov     [rsp+48h+arg_0], 0
0x180029ee3  mov     r9, rax
0x180029ee6  xor     r8d, r8d; pReturnValue
0x180029ee9  lea     edx, [r8+4]; nProcNum
0x180029eed  lea     rcx, stru_180032170; pProxyInfo
0x180029ef4  call    cs:__imp_NdrClientCall3
0x180029efa  mov     rbx, rax
0x180029efd  mov     [rsp+48h+arg_0], rax
0x180029f02  mov     [rsp+48h+var_28], eax
0x180029f06  jmp     short loc_180029F1A
0x180029f08  test    eax, eax
0x180029f0a  jle     short loc_180029F14
0x180029f0c  movzx   eax, ax
0x180029f0f  or      eax, 80070000h
0x180029f14  mov     ebx, eax
0x180029f16  mov     [rsp+48h+var_28], eax
0x180029f1a  lea     rcx, [rsp+48h+var_20]; this
0x180029f1f  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180029f24  mov     eax, ebx
0x180029f26  add     rsp, 40h
0x180029f2a  pop     rbx
0x180029f2b  retn
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

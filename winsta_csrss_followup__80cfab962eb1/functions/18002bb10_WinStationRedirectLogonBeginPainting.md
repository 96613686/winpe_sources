# WinStationRedirectLogonBeginPainting

- ea: `0x18002bb10`
- end: `0x18002bbef`
- name: `WinStationRedirectLogonBeginPainting`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18002bb10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb50`
- `RPCRT4!NdrClientCall3` at `0x18002bbb0`
- `RPCRT4!NdrClientCall3` at `0x18002bbb0`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002bb1d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002bb1d`

## string_xrefs

- `0x18002bb79`: `Failed to open binding failed: 0x%x in %s`

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
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351A0, 4u, 0, v2).Pointer;
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
0x18002bb10  push    rbx
0x18002bb12  sub     rsp, 40h
0x18002bb16  xor     ebx, ebx
0x18002bb18  mov     ecx, 1000h; nIndex
0x18002bb1d  call    cs:__imp_GetSystemMetrics
0x18002bb24  nop     dword ptr [rax+rax+00h]
0x18002bb29  test    eax, eax
0x18002bb2b  jz      loc_18002BBE6
0x18002bb31  xor     edx, edx; void *
0x18002bb33  lea     r8d, [rbx+1]; int
0x18002bb37  lea     rcx, [rsp+48h+var_20]; this
0x18002bb3c  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002bb41  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18002bb46  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002bb4b  test    rax, rax
0x18002bb4e  jnz     short loc_18002BB8C
0x18002bb50  call    cs:__imp_GetLastError
0x18002bb57  nop     dword ptr [rax+rax+00h]
0x18002bb5c  mov     ebx, eax
0x18002bb5e  test    eax, eax
0x18002bb60  jle     short loc_18002BB6B
0x18002bb62  movzx   ebx, ax
0x18002bb65  or      ebx, 80070000h
0x18002bb6b  test    ebx, ebx
0x18002bb6d  jns     short loc_18002BB8C
0x18002bb6f  lea     r9, aWinstationredi_6; "WinStationRedirectLogonBeginPainting"
0x18002bb76  mov     r8d, ebx
0x18002bb79  lea     rdx, aFailedToOpenBi; "Failed to open binding failed: 0x%x in "...
0x18002bb80  mov     ecx, 8; int
0x18002bb85  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002bb8a  jmp     short loc_18002BBDC
0x18002bb8c  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18002bb91  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002bb96  mov     [rsp+48h+arg_0], 0
0x18002bb9f  mov     r9, rax
0x18002bba2  xor     r8d, r8d; pReturnValue
0x18002bba5  lea     edx, [r8+4]; nProcNum
0x18002bba9  lea     rcx, stru_1800351A0; pProxyInfo
0x18002bbb0  call    cs:__imp_NdrClientCall3
0x18002bbb7  nop     dword ptr [rax+rax+00h]
0x18002bbbc  mov     rbx, rax
0x18002bbbf  mov     [rsp+48h+arg_0], rax
0x18002bbc4  mov     [rsp+48h+var_28], eax
0x18002bbc8  jmp     short loc_18002BBDC
0x18002bbca  test    eax, eax
0x18002bbcc  jle     short loc_18002BBD6
0x18002bbce  movzx   eax, ax
0x18002bbd1  or      eax, 80070000h
0x18002bbd6  mov     ebx, eax
0x18002bbd8  mov     [rsp+48h+var_28], eax
0x18002bbdc  lea     rcx, [rsp+48h+var_20]; this
0x18002bbe1  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002bbe6  mov     eax, ebx
0x18002bbe8  add     rsp, 40h
0x18002bbec  pop     rbx
0x18002bbed  retn
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

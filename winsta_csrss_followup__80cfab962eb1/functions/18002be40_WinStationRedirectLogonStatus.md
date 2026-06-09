# WinStationRedirectLogonStatus

- ea: `0x18002be40`
- end: `0x18002bf42`
- name: `WinStationRedirectLogonStatus`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18002be40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be8f`
- `RPCRT4!NdrClientCall3` at `0x18002bef9`
- `RPCRT4!NdrClientCall3` at `0x18002bef9`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002be5c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002be5c`

## string_xrefs

- `0x18002beb8`: `Failed to open binding failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall WinStationRedirectLogonStatus(__int64 a1, __int64 a2)
{
  signed int Pointer; // ebx
  signed int LastError; // eax
  void *v6; // rax
  unsigned __int16 v8[16]; // [rsp+38h] [rbp-20h] BYREF

  Pointer = 0;
  if ( GetSystemMetrics(4096) )
  {
    CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v8, 0, 1);
    if ( CSmartPublicBinding::operator void *(v8) )
      goto LABEL_7;
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
    if ( Pointer >= 0 )
    {
LABEL_7:
      v6 = CSmartPublicBinding::operator void *(v8);
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351A0, 5u, 0, v6, a1, a2).Pointer;
    }
    else
    {
      _DbgPrintMessage(8, "Failed to open binding failed: 0x%x in %s", Pointer, "WinStationRedirectLogonStatus");
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v8);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18002be40  mov     [rsp+arg_0], rbx
0x18002be45  mov     [rsp+arg_8], rsi
0x18002be4a  push    rdi
0x18002be4b  sub     rsp, 50h
0x18002be4f  mov     rdi, rdx
0x18002be52  mov     rsi, rcx
0x18002be55  xor     ebx, ebx
0x18002be57  mov     ecx, 1000h; nIndex
0x18002be5c  call    cs:__imp_GetSystemMetrics
0x18002be63  nop     dword ptr [rax+rax+00h]
0x18002be68  test    eax, eax
0x18002be6a  jz      loc_18002BF2F
0x18002be70  xor     edx, edx; void *
0x18002be72  lea     r8d, [rbx+1]; int
0x18002be76  lea     rcx, [rsp+58h+var_20]; this
0x18002be7b  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002be80  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002be85  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002be8a  test    rax, rax
0x18002be8d  jnz     short loc_18002BECB
0x18002be8f  call    cs:__imp_GetLastError
0x18002be96  nop     dword ptr [rax+rax+00h]
0x18002be9b  mov     ebx, eax
0x18002be9d  test    eax, eax
0x18002be9f  jle     short loc_18002BEAA
0x18002bea1  movzx   ebx, ax
0x18002bea4  or      ebx, 80070000h
0x18002beaa  test    ebx, ebx
0x18002beac  jns     short loc_18002BECB
0x18002beae  lea     r9, aWinstationredi_4; "WinStationRedirectLogonStatus"
0x18002beb5  mov     r8d, ebx
0x18002beb8  lea     rdx, aFailedToOpenBi; "Failed to open binding failed: 0x%x in "...
0x18002bebf  mov     ecx, 8; int
0x18002bec4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002bec9  jmp     short loc_18002BF25
0x18002becb  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002bed0  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002bed5  mov     [rsp+58h+arg_10], 0
0x18002bede  mov     [rsp+58h+var_30], rdi
0x18002bee3  mov     [rsp+58h+var_38], rsi
0x18002bee8  mov     r9, rax
0x18002beeb  xor     r8d, r8d; pReturnValue
0x18002beee  lea     edx, [r8+5]; nProcNum
0x18002bef2  lea     rcx, stru_1800351A0; pProxyInfo
0x18002bef9  call    cs:__imp_NdrClientCall3
0x18002bf00  nop     dword ptr [rax+rax+00h]
0x18002bf05  mov     rbx, rax
0x18002bf08  mov     [rsp+58h+arg_10], rax
0x18002bf0d  mov     [rsp+58h+var_28], eax
0x18002bf11  jmp     short loc_18002BF25
0x18002bf13  test    eax, eax
0x18002bf15  jle     short loc_18002BF1F
0x18002bf17  movzx   eax, ax
0x18002bf1a  or      eax, 80070000h
0x18002bf1f  mov     ebx, eax
0x18002bf21  mov     [rsp+58h+var_28], eax
0x18002bf25  lea     rcx, [rsp+58h+var_20]; this
0x18002bf2a  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002bf2f  mov     eax, ebx
0x18002bf31  mov     rbx, [rsp+58h+arg_0]
0x18002bf36  mov     rsi, [rsp+58h+arg_8]
0x18002bf3b  add     rsp, 50h
0x18002bf3f  pop     rdi
0x18002bf40  retn
0x180033757  push    rbp
0x180033759  sub     rsp, 30h
0x18003375d  mov     rbp, rdx
0x180033760  mov     rcx, [rcx]
0x180033763  mov     ecx, [rcx]; ExceptionCode
0x180033765  call    cs:__imp_I_RpcExceptionFilter
0x18003376c  nop     dword ptr [rax+rax+00h]
0x180033771  nop
0x180033772  add     rsp, 30h
0x180033776  pop     rbp
0x180033777  retn
```

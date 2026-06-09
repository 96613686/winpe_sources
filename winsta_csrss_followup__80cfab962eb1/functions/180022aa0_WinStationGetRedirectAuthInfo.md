# WinStationGetRedirectAuthInfo

- ea: `0x180022aa0`
- end: `0x180022bb2`
- name: `WinStationGetRedirectAuthInfo`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180022aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ae4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ae4`
- `RPCRT4!NdrClientCall3` at `0x180022b5a`
- `RPCRT4!NdrClientCall3` at `0x180022b5a`

## string_xrefs

- `0x180022ad5`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall WinStationGetRedirectAuthInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  signed int LastError; // eax
  unsigned int Pointer; // ebx
  void *v12; // rax
  unsigned __int16 v14[28]; // [rsp+60h] [rbp-38h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v14, 0, 1);
  if ( CSmartPublicBinding::operator void *(v14) )
  {
    v12 = CSmartPublicBinding::operator void *(v14);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&stru_1800351A0,
                              8u,
                              0,
                              v12,
                              a1,
                              a2,
                              a3,
                              a4,
                              a5,
                              a6).Pointer;
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v14);
  return Pointer;
}

```

## disassembly

```asm
0x180022aa0  push    rbx
0x180022aa2  push    rsi
0x180022aa3  push    rdi
0x180022aa4  push    r14
0x180022aa6  sub     rsp, 78h
0x180022aaa  mov     rbx, r9
0x180022aad  mov     rdi, r8
0x180022ab0  mov     rsi, rdx
0x180022ab3  mov     r14, rcx
0x180022ab6  xor     edx, edx; void *
0x180022ab8  lea     r8d, [rdx+1]; int
0x180022abc  lea     rcx, [rsp+98h+var_38]; this
0x180022ac1  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180022ac6  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180022acb  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022ad0  test    rax, rax
0x180022ad3  jnz     short loc_180022B08
0x180022ad5  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180022adc  lea     ecx, [rax+8]; int
0x180022adf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022ae4  call    cs:__imp_GetLastError
0x180022aeb  nop     dword ptr [rax+rax+00h]
0x180022af0  mov     ebx, eax
0x180022af2  test    eax, eax
0x180022af4  jle     loc_180022B9B
0x180022afa  movzx   ebx, ax
0x180022afd  or      ebx, 80070000h
0x180022b03  jmp     loc_180022B9B
0x180022b08  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180022b0d  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022b12  mov     [rsp+98h+var_40], 0
0x180022b1b  mov     rcx, [rsp+98h+arg_28]
0x180022b23  mov     [rsp+98h+var_50], rcx
0x180022b28  mov     rcx, [rsp+98h+arg_20]
0x180022b30  mov     [rsp+98h+var_58], rcx
0x180022b35  mov     [rsp+98h+var_60], rbx
0x180022b3a  mov     [rsp+98h+var_68], rdi
0x180022b3f  mov     [rsp+98h+var_70], rsi
0x180022b44  mov     [rsp+98h+var_78], r14
0x180022b49  mov     r9, rax
0x180022b4c  xor     r8d, r8d; pReturnValue
0x180022b4f  lea     edx, [r8+8]; nProcNum
0x180022b53  lea     rcx, stru_1800351A0; pProxyInfo
0x180022b5a  call    cs:__imp_NdrClientCall3
0x180022b61  nop     dword ptr [rax+rax+00h]
0x180022b66  mov     rbx, rax
0x180022b69  mov     [rsp+98h+var_40], rax
0x180022b6e  mov     [rsp+98h+var_48], eax
0x180022b72  jmp     short loc_180022B9B
0x180022b74  test    eax, eax
0x180022b76  jle     short loc_180022B80
0x180022b78  movzx   eax, ax
0x180022b7b  or      eax, 80070000h
0x180022b80  mov     ebx, eax
0x180022b82  mov     [rsp+98h+var_48], eax
0x180022b86  mov     r8d, eax
0x180022b89  lea     rdx, aRpcgetredirect; "RpcGetRedirectAuthInfo threw an excepti"...
0x180022b90  mov     ecx, 8; int
0x180022b95  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022b9a  nop
0x180022b9b  lea     rcx, [rsp+98h+var_38]; this
0x180022ba0  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180022ba5  mov     eax, ebx
0x180022ba7  add     rsp, 78h
0x180022bab  pop     r14
0x180022bad  pop     rdi
0x180022bae  pop     rsi
0x180022baf  pop     rbx
0x180022bb0  retn
0x1800337cf  push    rbp
0x1800337d1  sub     rsp, 50h
0x1800337d5  mov     rbp, rdx
0x1800337d8  mov     rcx, [rcx]
0x1800337db  mov     ecx, [rcx]; ExceptionCode
0x1800337dd  call    cs:__imp_I_RpcExceptionFilter
0x1800337e4  nop     dword ptr [rax+rax+00h]
0x1800337e9  nop
0x1800337ea  add     rsp, 50h
0x1800337ee  pop     rbp
0x1800337ef  retn
```

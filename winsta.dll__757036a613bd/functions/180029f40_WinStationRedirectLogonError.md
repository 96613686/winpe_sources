# WinStationRedirectLogonError

- ea: `0x180029f40`
- end: `0x18002a050`
- name: `WinStationRedirectLogonError`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180029f40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f8c`
- `RPCRT4!NdrClientCall3` at `0x18002a012`
- `RPCRT4!NdrClientCall3` at `0x18002a012`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180029f5f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180029f5f`

## string_xrefs

- `0x180029faf`: `Failed to open binding failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall WinStationRedirectLogonError(int a1, int a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  signed int Pointer; // ebx
  signed int LastError; // eax
  void *v12; // rax
  int v14; // [rsp+20h] [rbp-78h]
  int v15; // [rsp+28h] [rbp-70h]
  unsigned __int16 v17[28]; // [rsp+60h] [rbp-38h] BYREF

  Pointer = 0;
  if ( GetSystemMetrics(4096) )
  {
    CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v17, 0, 1);
    if ( CSmartPublicBinding::operator void *(v17) )
      goto LABEL_7;
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
    if ( Pointer >= 0 )
    {
LABEL_7:
      v12 = CSmartPublicBinding::operator void *(v17);
      v15 = a2;
      v14 = a1;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&stru_180032170,
                                7u,
                                0,
                                v12,
                                v14,
                                v15,
                                a3,
                                a4,
                                a5,
                                a6).Pointer;
    }
    else
    {
      _DbgPrintMessage(8, "Failed to open binding failed: 0x%x in %s", Pointer, "WinStationRedirectLogonError");
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v17);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180029f40  push    rbx
0x180029f42  push    rsi
0x180029f43  push    rdi
0x180029f44  push    r14
0x180029f46  push    r15
0x180029f48  sub     rsp, 70h
0x180029f4c  mov     rdi, r9
0x180029f4f  mov     rsi, r8
0x180029f52  mov     r14d, edx
0x180029f55  mov     r15d, ecx
0x180029f58  xor     ebx, ebx
0x180029f5a  mov     ecx, 1000h; nIndex
0x180029f5f  call    cs:__imp_GetSystemMetrics
0x180029f65  test    eax, eax
0x180029f67  jz      loc_18002A042
0x180029f6d  xor     edx, edx; void *
0x180029f6f  lea     r8d, [rbx+1]; int
0x180029f73  lea     rcx, [rsp+98h+var_38]; this
0x180029f78  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180029f7d  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180029f82  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029f87  test    rax, rax
0x180029f8a  jnz     short loc_180029FC2
0x180029f8c  call    cs:__imp_GetLastError
0x180029f92  mov     ebx, eax
0x180029f94  test    eax, eax
0x180029f96  jle     short loc_180029FA1
0x180029f98  movzx   ebx, ax
0x180029f9b  or      ebx, 80070000h
0x180029fa1  test    ebx, ebx
0x180029fa3  jns     short loc_180029FC2
0x180029fa5  lea     r9, aWinstationredi_7; "WinStationRedirectLogonError"
0x180029fac  mov     r8d, ebx
0x180029faf  lea     rdx, aFailedToOpenBi; "Failed to open binding failed: 0x%x in "...
0x180029fb6  mov     ecx, 8; int
0x180029fbb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029fc0  jmp     short loc_18002A038
0x180029fc2  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180029fc7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029fcc  mov     [rsp+98h+var_40], 0
0x180029fd5  mov     rcx, [rsp+98h+arg_28]
0x180029fdd  mov     [rsp+98h+var_50], rcx
0x180029fe2  mov     ecx, [rsp+98h+arg_20]
0x180029fe9  mov     [rsp+98h+var_58], ecx
0x180029fed  mov     [rsp+98h+var_60], rdi
0x180029ff2  mov     [rsp+98h+var_68], rsi
0x180029ff7  mov     [rsp+98h+var_70], r14d
0x180029ffc  mov     [rsp+98h+var_78], r15d
0x18002a001  mov     r9, rax
0x18002a004  xor     r8d, r8d; pReturnValue
0x18002a007  lea     edx, [r8+7]; nProcNum
0x18002a00b  lea     rcx, stru_180032170; pProxyInfo
0x18002a012  call    cs:__imp_NdrClientCall3
0x18002a018  mov     rbx, rax
0x18002a01b  mov     [rsp+98h+var_40], rax
0x18002a020  mov     [rsp+98h+var_48], eax
0x18002a024  jmp     short loc_18002A038
0x18002a026  test    eax, eax
0x18002a028  jle     short loc_18002A032
0x18002a02a  movzx   eax, ax
0x18002a02d  or      eax, 80070000h
0x18002a032  mov     ebx, eax
0x18002a034  mov     [rsp+98h+var_48], eax
0x18002a038  lea     rcx, [rsp+98h+var_38]; this
0x18002a03d  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002a042  mov     eax, ebx
0x18002a044  add     rsp, 70h
0x18002a048  pop     r15
0x18002a04a  pop     r14
0x18002a04c  pop     rdi
0x18002a04d  pop     rsi
0x18002a04e  pop     rbx
0x18002a04f  retn
0x1800308b7  push    rbp
0x1800308b9  sub     rsp, 50h
0x1800308bd  mov     rbp, rdx
0x1800308c0  mov     rcx, [rcx]
0x1800308c3  mov     ecx, [rcx]; ExceptionCode
0x1800308c5  call    cs:__imp_I_RpcExceptionFilter
0x1800308cb  nop
0x1800308cc  add     rsp, 50h
0x1800308d0  pop     rbp
0x1800308d1  retn
```

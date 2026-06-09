# WinStationRedirectLogonError

- ea: `0x18002bc00`
- end: `0x18002bd23`
- name: `WinStationRedirectLogonError`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18002bc00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc52`
- `RPCRT4!NdrClientCall3` at `0x18002bcde`
- `RPCRT4!NdrClientCall3` at `0x18002bcde`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002bc1f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002bc1f`

## string_xrefs

- `0x18002bc7b`: `Failed to open binding failed: 0x%x in %s`

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
                                (MIDL_STUBLESS_PROXY_INFO *)&stru_1800351A0,
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
0x18002bc00  push    rbx
0x18002bc02  push    rsi
0x18002bc03  push    rdi
0x18002bc04  push    r14
0x18002bc06  push    r15
0x18002bc08  sub     rsp, 70h
0x18002bc0c  mov     rdi, r9
0x18002bc0f  mov     rsi, r8
0x18002bc12  mov     r14d, edx
0x18002bc15  mov     r15d, ecx
0x18002bc18  xor     ebx, ebx
0x18002bc1a  mov     ecx, 1000h; nIndex
0x18002bc1f  call    cs:__imp_GetSystemMetrics
0x18002bc26  nop     dword ptr [rax+rax+00h]
0x18002bc2b  test    eax, eax
0x18002bc2d  jz      loc_18002BD14
0x18002bc33  xor     edx, edx; void *
0x18002bc35  lea     r8d, [rbx+1]; int
0x18002bc39  lea     rcx, [rsp+98h+var_38]; this
0x18002bc3e  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002bc43  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x18002bc48  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002bc4d  test    rax, rax
0x18002bc50  jnz     short loc_18002BC8E
0x18002bc52  call    cs:__imp_GetLastError
0x18002bc59  nop     dword ptr [rax+rax+00h]
0x18002bc5e  mov     ebx, eax
0x18002bc60  test    eax, eax
0x18002bc62  jle     short loc_18002BC6D
0x18002bc64  movzx   ebx, ax
0x18002bc67  or      ebx, 80070000h
0x18002bc6d  test    ebx, ebx
0x18002bc6f  jns     short loc_18002BC8E
0x18002bc71  lea     r9, aWinstationredi_7; "WinStationRedirectLogonError"
0x18002bc78  mov     r8d, ebx
0x18002bc7b  lea     rdx, aFailedToOpenBi; "Failed to open binding failed: 0x%x in "...
0x18002bc82  mov     ecx, 8; int
0x18002bc87  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002bc8c  jmp     short loc_18002BD0A
0x18002bc8e  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x18002bc93  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002bc98  mov     [rsp+98h+var_40], 0
0x18002bca1  mov     rcx, [rsp+98h+arg_28]
0x18002bca9  mov     [rsp+98h+var_50], rcx
0x18002bcae  mov     ecx, [rsp+98h+arg_20]
0x18002bcb5  mov     [rsp+98h+var_58], ecx
0x18002bcb9  mov     [rsp+98h+var_60], rdi
0x18002bcbe  mov     [rsp+98h+var_68], rsi
0x18002bcc3  mov     [rsp+98h+var_70], r14d
0x18002bcc8  mov     [rsp+98h+var_78], r15d
0x18002bccd  mov     r9, rax
0x18002bcd0  xor     r8d, r8d; pReturnValue
0x18002bcd3  lea     edx, [r8+7]; nProcNum
0x18002bcd7  lea     rcx, stru_1800351A0; pProxyInfo
0x18002bcde  call    cs:__imp_NdrClientCall3
0x18002bce5  nop     dword ptr [rax+rax+00h]
0x18002bcea  mov     rbx, rax
0x18002bced  mov     [rsp+98h+var_40], rax
0x18002bcf2  mov     [rsp+98h+var_48], eax
0x18002bcf6  jmp     short loc_18002BD0A
0x18002bcf8  test    eax, eax
0x18002bcfa  jle     short loc_18002BD04
0x18002bcfc  movzx   eax, ax
0x18002bcff  or      eax, 80070000h
0x18002bd04  mov     ebx, eax
0x18002bd06  mov     [rsp+98h+var_48], eax
0x18002bd0a  lea     rcx, [rsp+98h+var_38]; this
0x18002bd0f  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002bd14  mov     eax, ebx
0x18002bd16  add     rsp, 70h
0x18002bd1a  pop     r15
0x18002bd1c  pop     r14
0x18002bd1e  pop     rdi
0x18002bd1f  pop     rsi
0x18002bd20  pop     rbx
0x18002bd21  retn
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

# WinStationRedirectLogonStatus

- ea: `0x18002a160`
- end: `0x18002a24f`
- name: `WinStationRedirectLogonStatus`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18002a160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1a9`
- `RPCRT4!NdrClientCall3` at `0x18002a20d`
- `RPCRT4!NdrClientCall3` at `0x18002a20d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002a17c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002a17c`

## string_xrefs

- `0x18002a1cc`: `Failed to open binding failed: 0x%x in %s`

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
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032170, 5u, 0, v6, a1, a2).Pointer;
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
0x18002a160  mov     [rsp+arg_0], rbx
0x18002a165  mov     [rsp+arg_8], rsi
0x18002a16a  push    rdi
0x18002a16b  sub     rsp, 50h
0x18002a16f  mov     rdi, rdx
0x18002a172  mov     rsi, rcx
0x18002a175  xor     ebx, ebx
0x18002a177  mov     ecx, 1000h; nIndex
0x18002a17c  call    cs:__imp_GetSystemMetrics
0x18002a182  test    eax, eax
0x18002a184  jz      loc_18002A23D
0x18002a18a  xor     edx, edx; void *
0x18002a18c  lea     r8d, [rbx+1]; int
0x18002a190  lea     rcx, [rsp+58h+var_20]; this
0x18002a195  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002a19a  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002a19f  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002a1a4  test    rax, rax
0x18002a1a7  jnz     short loc_18002A1DF
0x18002a1a9  call    cs:__imp_GetLastError
0x18002a1af  mov     ebx, eax
0x18002a1b1  test    eax, eax
0x18002a1b3  jle     short loc_18002A1BE
0x18002a1b5  movzx   ebx, ax
0x18002a1b8  or      ebx, 80070000h
0x18002a1be  test    ebx, ebx
0x18002a1c0  jns     short loc_18002A1DF
0x18002a1c2  lea     r9, aWinstationredi_4; "WinStationRedirectLogonStatus"
0x18002a1c9  mov     r8d, ebx
0x18002a1cc  lea     rdx, aFailedToOpenBi; "Failed to open binding failed: 0x%x in "...
0x18002a1d3  mov     ecx, 8; int
0x18002a1d8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a1dd  jmp     short loc_18002A233
0x18002a1df  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002a1e4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002a1e9  mov     [rsp+58h+arg_10], 0
0x18002a1f2  mov     [rsp+58h+var_30], rdi
0x18002a1f7  mov     [rsp+58h+var_38], rsi
0x18002a1fc  mov     r9, rax
0x18002a1ff  xor     r8d, r8d; pReturnValue
0x18002a202  lea     edx, [r8+5]; nProcNum
0x18002a206  lea     rcx, stru_180032170; pProxyInfo
0x18002a20d  call    cs:__imp_NdrClientCall3
0x18002a213  mov     rbx, rax
0x18002a216  mov     [rsp+58h+arg_10], rax
0x18002a21b  mov     [rsp+58h+var_28], eax
0x18002a21f  jmp     short loc_18002A233
0x18002a221  test    eax, eax
0x18002a223  jle     short loc_18002A22D
0x18002a225  movzx   eax, ax
0x18002a228  or      eax, 80070000h
0x18002a22d  mov     ebx, eax
0x18002a22f  mov     [rsp+58h+var_28], eax
0x18002a233  lea     rcx, [rsp+58h+var_20]; this
0x18002a238  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002a23d  mov     eax, ebx
0x18002a23f  mov     rbx, [rsp+58h+arg_0]
0x18002a244  mov     rsi, [rsp+58h+arg_8]
0x18002a249  add     rsp, 50h
0x18002a24d  pop     rdi
0x18002a24e  retn
0x180030851  push    rbp
0x180030853  sub     rsp, 30h
0x180030857  mov     rbp, rdx
0x18003085a  mov     rcx, [rcx]
0x18003085d  mov     ecx, [rcx]; ExceptionCode
0x18003085f  call    cs:__imp_I_RpcExceptionFilter
0x180030865  nop
0x180030866  add     rsp, 30h
0x18003086a  pop     rbp
0x18003086b  retn
```

# WinStationGetRestrictedLogonInfo

- ea: `0x180029b30`
- end: `0x180029c46`
- name: `WinStationGetRestrictedLogonInfo`
- size: `278`
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
- `0x180029b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b6e`
- `RPCRT4!NdrClientCall3` at `0x180029bba`
- `RPCRT4!NdrClientCall3` at `0x180029bba`

## string_xrefs

- `0x180029b5f`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall WinStationGetRestrictedLogonInfo(__int64 a1, __int64 a2)
{
  signed int LastError; // eax
  signed int Pointer; // ebx
  void *v6; // rax
  unsigned int v7; // ebx
  unsigned __int16 v9[16]; // [rsp+38h] [rbp-20h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v9, 0, 1);
  if ( CSmartPublicBinding::operator void *(v9) )
  {
    v6 = CSmartPublicBinding::operator void *(v9);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032170, 9u, 0, v6, a1, a2).Pointer;
    if ( Pointer >= 0 )
      goto LABEL_8;
    _DbgPrintMessage(8, "RpcGetRestrictedLogonInfo failed: 0x%x in %s", Pointer, "WinStationGetRestrictedLogonInfo");
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
    v7 = ConvertHRESULT2WIN32(Pointer);
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v9);
    return v7;
  }
LABEL_8:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v9);
  return 0;
}

```

## disassembly

```asm
0x180029b30  mov     [rsp+arg_0], rbx
0x180029b35  push    rdi
0x180029b36  sub     rsp, 50h
0x180029b3a  mov     rbx, rdx
0x180029b3d  mov     rdi, rcx
0x180029b40  xor     edx, edx; void *
0x180029b42  lea     r8d, [rdx+1]; int
0x180029b46  lea     rcx, [rsp+58h+var_20]; this
0x180029b4b  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180029b50  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180029b55  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029b5a  test    rax, rax
0x180029b5d  jnz     short loc_180029B8C
0x180029b5f  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180029b66  lea     ecx, [rax+8]; int
0x180029b69  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029b6e  call    cs:__imp_GetLastError
0x180029b74  mov     ebx, eax
0x180029b76  test    eax, eax
0x180029b78  jle     loc_180029C14
0x180029b7e  movzx   ebx, ax
0x180029b81  or      ebx, 80070000h
0x180029b87  jmp     loc_180029C14
0x180029b8c  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180029b91  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029b96  mov     [rsp+58h+arg_10], 0
0x180029b9f  mov     [rsp+58h+var_30], rbx
0x180029ba4  mov     [rsp+58h+var_38], rdi
0x180029ba9  mov     r9, rax
0x180029bac  xor     r8d, r8d; pReturnValue
0x180029baf  lea     edx, [r8+9]; nProcNum
0x180029bb3  lea     rcx, stru_180032170; pProxyInfo
0x180029bba  call    cs:__imp_NdrClientCall3
0x180029bc0  mov     rbx, rax
0x180029bc3  mov     [rsp+58h+arg_10], rax
0x180029bc8  mov     [rsp+58h+var_28], eax
0x180029bcc  jmp     short loc_180029BF5
0x180029bce  mov     ebx, eax
0x180029bd0  mov     r8d, eax
0x180029bd3  lea     rdx, aRpcgetrestrict; "RpcGetRestrictedLogonInfo threw an exce"...
0x180029bda  mov     ecx, 8; int
0x180029bdf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029be4  test    ebx, ebx
0x180029be6  jle     short loc_180029BF1
0x180029be8  movzx   ebx, bx
0x180029beb  or      ebx, 80070000h
0x180029bf1  mov     [rsp+58h+var_28], ebx
0x180029bf5  test    ebx, ebx
0x180029bf7  jns     short loc_180029C2F
0x180029bf9  lea     r9, aWinstationgetr_1; "WinStationGetRestrictedLogonInfo"
0x180029c00  mov     r8d, ebx
0x180029c03  lea     rdx, aRpcgetrestrict_0; "RpcGetRestrictedLogonInfo failed: 0x%x "...
0x180029c0a  mov     ecx, 8; int
0x180029c0f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029c14  test    ebx, ebx
0x180029c16  jns     short loc_180029C2F
0x180029c18  mov     ecx, ebx; int
0x180029c1a  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180029c1f  mov     ebx, eax
0x180029c21  lea     rcx, [rsp+58h+var_20]; this
0x180029c26  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180029c2b  mov     eax, ebx
0x180029c2d  jmp     short loc_180029C3B
0x180029c2f  lea     rcx, [rsp+58h+var_20]; this
0x180029c34  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180029c39  xor     eax, eax
0x180029c3b  mov     rbx, [rsp+58h+arg_0]
0x180029c40  add     rsp, 50h
0x180029c44  pop     rdi
0x180029c45  retn
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

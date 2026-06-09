# WinStationGetRestrictedLogonInfo

- ea: `0x18002b790`
- end: `0x18002b8b3`
- name: `WinStationGetRestrictedLogonInfo`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18002b790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7ce`
- `RPCRT4!NdrClientCall3` at `0x18002b820`
- `RPCRT4!NdrClientCall3` at `0x18002b820`

## string_xrefs

- `0x18002b7bf`: `Failed to open binding`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351A0, 9u, 0, v6, a1, a2).Pointer;
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
0x18002b790  mov     [rsp+arg_0], rbx
0x18002b795  push    rdi
0x18002b796  sub     rsp, 50h
0x18002b79a  mov     rbx, rdx
0x18002b79d  mov     rdi, rcx
0x18002b7a0  xor     edx, edx; void *
0x18002b7a2  lea     r8d, [rdx+1]; int
0x18002b7a6  lea     rcx, [rsp+58h+var_20]; this
0x18002b7ab  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002b7b0  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002b7b5  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002b7ba  test    rax, rax
0x18002b7bd  jnz     short loc_18002B7F2
0x18002b7bf  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002b7c6  lea     ecx, [rax+8]; int
0x18002b7c9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b7ce  call    cs:__imp_GetLastError
0x18002b7d5  nop     dword ptr [rax+rax+00h]
0x18002b7da  mov     ebx, eax
0x18002b7dc  test    eax, eax
0x18002b7de  jle     loc_18002B880
0x18002b7e4  movzx   ebx, ax
0x18002b7e7  or      ebx, 80070000h
0x18002b7ed  jmp     loc_18002B880
0x18002b7f2  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002b7f7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002b7fc  mov     [rsp+58h+arg_10], 0
0x18002b805  mov     [rsp+58h+var_30], rbx
0x18002b80a  mov     [rsp+58h+var_38], rdi
0x18002b80f  mov     r9, rax
0x18002b812  xor     r8d, r8d; pReturnValue
0x18002b815  lea     edx, [r8+9]; nProcNum
0x18002b819  lea     rcx, stru_1800351A0; pProxyInfo
0x18002b820  call    cs:__imp_NdrClientCall3
0x18002b827  nop     dword ptr [rax+rax+00h]
0x18002b82c  mov     rbx, rax
0x18002b82f  mov     [rsp+58h+arg_10], rax
0x18002b834  mov     [rsp+58h+var_28], eax
0x18002b838  jmp     short loc_18002B861
0x18002b83a  mov     ebx, eax
0x18002b83c  mov     r8d, eax
0x18002b83f  lea     rdx, aRpcgetrestrict; "RpcGetRestrictedLogonInfo threw an exce"...
0x18002b846  mov     ecx, 8; int
0x18002b84b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b850  test    ebx, ebx
0x18002b852  jle     short loc_18002B85D
0x18002b854  movzx   ebx, bx
0x18002b857  or      ebx, 80070000h
0x18002b85d  mov     [rsp+58h+var_28], ebx
0x18002b861  test    ebx, ebx
0x18002b863  jns     short loc_18002B89B
0x18002b865  lea     r9, aWinstationgetr_1; "WinStationGetRestrictedLogonInfo"
0x18002b86c  mov     r8d, ebx
0x18002b86f  lea     rdx, aRpcgetrestrict_0; "RpcGetRestrictedLogonInfo failed: 0x%x "...
0x18002b876  mov     ecx, 8; int
0x18002b87b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b880  test    ebx, ebx
0x18002b882  jns     short loc_18002B89B
0x18002b884  mov     ecx, ebx; int
0x18002b886  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002b88b  mov     ebx, eax
0x18002b88d  lea     rcx, [rsp+58h+var_20]; this
0x18002b892  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002b897  mov     eax, ebx
0x18002b899  jmp     short loc_18002B8A7
0x18002b89b  lea     rcx, [rsp+58h+var_20]; this
0x18002b8a0  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002b8a5  xor     eax, eax
0x18002b8a7  mov     rbx, [rsp+58h+arg_0]
0x18002b8ac  add     rsp, 50h
0x18002b8b0  pop     rdi
0x18002b8b1  retn
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

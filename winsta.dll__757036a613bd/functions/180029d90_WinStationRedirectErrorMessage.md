# WinStationRedirectErrorMessage

- ea: `0x180029d90`
- end: `0x180029e58`
- name: `WinStationRedirectErrorMessage`
- size: `200`
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
- `0x180029d90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029de6`
- `RPCRT4!NdrClientCall3` at `0x180029e1c`
- `RPCRT4!NdrClientCall3` at `0x180029e1c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180029daa`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180029daa`

## string_xrefs

- `0x180029dd7`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall WinStationRedirectErrorMessage(int a1, int a2)
{
  DWORD LastError; // ebx
  void *v5; // rax
  int v7; // [rsp+20h] [rbp-38h]
  int v8; // [rsp+28h] [rbp-30h]
  unsigned __int16 v9[16]; // [rsp+38h] [rbp-20h] BYREF
  int Pointer; // [rsp+70h] [rbp+18h]

  LastError = 0;
  if ( GetSystemMetrics(4096) )
  {
    CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v9, 0, 1);
    if ( CSmartPublicBinding::operator void *(v9) )
    {
      v5 = CSmartPublicBinding::operator void *(v9);
      v8 = a2;
      v7 = a1;
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032170, 3u, 0, v5, v7, v8).Pointer;
      LastError = ConvertHRESULT2WIN32(Pointer);
    }
    else
    {
      _DbgPrintMessage(8, "Failed to open binding");
      LastError = GetLastError();
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v9);
  }
  return LastError;
}

```

## disassembly

```asm
0x180029d90  mov     [rsp+arg_0], rbx
0x180029d95  mov     [rsp+arg_8], rsi
0x180029d9a  push    rdi
0x180029d9b  sub     rsp, 50h
0x180029d9f  mov     edi, edx
0x180029da1  mov     esi, ecx
0x180029da3  xor     ebx, ebx
0x180029da5  mov     ecx, 1000h; nIndex
0x180029daa  call    cs:__imp_GetSystemMetrics
0x180029db0  test    eax, eax
0x180029db2  jz      loc_180029E46
0x180029db8  xor     edx, edx; void *
0x180029dba  lea     r8d, [rbx+1]; int
0x180029dbe  lea     rcx, [rsp+58h+var_20]; this
0x180029dc3  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180029dc8  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180029dcd  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029dd2  test    rax, rax
0x180029dd5  jnz     short loc_180029DF0
0x180029dd7  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180029dde  lea     ecx, [rbx+8]; int
0x180029de1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029de6  call    cs:__imp_GetLastError
0x180029dec  mov     ebx, eax
0x180029dee  jmp     short loc_180029E3C
0x180029df0  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180029df5  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029dfa  mov     [rsp+58h+arg_10], 0
0x180029e03  mov     [rsp+58h+var_30], edi
0x180029e07  mov     [rsp+58h+var_38], esi
0x180029e0b  mov     r9, rax
0x180029e0e  xor     r8d, r8d; pReturnValue
0x180029e11  lea     edx, [r8+3]; nProcNum
0x180029e15  lea     rcx, stru_180032170; pProxyInfo
0x180029e1c  call    cs:__imp_NdrClientCall3
0x180029e22  mov     [rsp+58h+arg_10], rax
0x180029e27  mov     ecx, eax; int
0x180029e29  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180029e2e  mov     ebx, eax
0x180029e30  mov     [rsp+58h+var_28], eax
0x180029e34  jmp     short loc_180029E3C
0x180029e36  mov     ebx, eax
0x180029e38  mov     [rsp+58h+var_28], eax
0x180029e3c  lea     rcx, [rsp+58h+var_20]; this
0x180029e41  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180029e46  mov     eax, ebx
0x180029e48  mov     rbx, [rsp+58h+arg_0]
0x180029e4d  mov     rsi, [rsp+58h+arg_8]
0x180029e52  add     rsp, 50h
0x180029e56  pop     rdi
0x180029e57  retn
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

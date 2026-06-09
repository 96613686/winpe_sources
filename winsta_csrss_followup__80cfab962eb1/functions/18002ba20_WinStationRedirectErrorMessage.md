# WinStationRedirectErrorMessage

- ea: `0x18002ba20`
- end: `0x18002bafb`
- name: `WinStationRedirectErrorMessage`
- size: `219`
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
- `0x18002ba20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba7c`
- `RPCRT4!NdrClientCall3` at `0x18002bab8`
- `RPCRT4!NdrClientCall3` at `0x18002bab8`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002ba3a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002ba3a`

## string_xrefs

- `0x18002ba6d`: `Failed to open binding`

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
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351A0, 3u, 0, v5, v7, v8).Pointer;
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
0x18002ba20  mov     [rsp+arg_0], rbx
0x18002ba25  mov     [rsp+arg_8], rsi
0x18002ba2a  push    rdi
0x18002ba2b  sub     rsp, 50h
0x18002ba2f  mov     edi, edx
0x18002ba31  mov     esi, ecx
0x18002ba33  xor     ebx, ebx
0x18002ba35  mov     ecx, 1000h; nIndex
0x18002ba3a  call    cs:__imp_GetSystemMetrics
0x18002ba41  nop     dword ptr [rax+rax+00h]
0x18002ba46  test    eax, eax
0x18002ba48  jz      loc_18002BAE8
0x18002ba4e  xor     edx, edx; void *
0x18002ba50  lea     r8d, [rbx+1]; int
0x18002ba54  lea     rcx, [rsp+58h+var_20]; this
0x18002ba59  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002ba5e  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002ba63  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002ba68  test    rax, rax
0x18002ba6b  jnz     short loc_18002BA8C
0x18002ba6d  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002ba74  lea     ecx, [rbx+8]; int
0x18002ba77  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ba7c  call    cs:__imp_GetLastError
0x18002ba83  nop     dword ptr [rax+rax+00h]
0x18002ba88  mov     ebx, eax
0x18002ba8a  jmp     short loc_18002BADE
0x18002ba8c  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002ba91  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002ba96  mov     [rsp+58h+arg_10], 0
0x18002ba9f  mov     [rsp+58h+var_30], edi
0x18002baa3  mov     [rsp+58h+var_38], esi
0x18002baa7  mov     r9, rax
0x18002baaa  xor     r8d, r8d; pReturnValue
0x18002baad  lea     edx, [r8+3]; nProcNum
0x18002bab1  lea     rcx, stru_1800351A0; pProxyInfo
0x18002bab8  call    cs:__imp_NdrClientCall3
0x18002babf  nop     dword ptr [rax+rax+00h]
0x18002bac4  mov     [rsp+58h+arg_10], rax
0x18002bac9  mov     ecx, eax; int
0x18002bacb  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002bad0  mov     ebx, eax
0x18002bad2  mov     [rsp+58h+var_28], eax
0x18002bad6  jmp     short loc_18002BADE
0x18002bad8  mov     ebx, eax
0x18002bada  mov     [rsp+58h+var_28], eax
0x18002bade  lea     rcx, [rsp+58h+var_20]; this
0x18002bae3  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002bae8  mov     eax, ebx
0x18002baea  mov     rbx, [rsp+58h+arg_0]
0x18002baef  mov     rsi, [rsp+58h+arg_8]
0x18002baf4  add     rsp, 50h
0x18002baf8  pop     rdi
0x18002baf9  retn
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

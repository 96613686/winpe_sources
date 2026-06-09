# WinStationEnumerateContainerSessions

- ea: `0x1800213c0`
- end: `0x1800214b2`
- name: `WinStationEnumerateContainerSessions`
- size: `242`
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
- `0x1800213c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021480`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021480`
- `RPCRT4!NdrClientCall3` at `0x180021432`
- `RPCRT4!NdrClientCall3` at `0x180021432`

## string_xrefs

- `0x1800213f3`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationEnumerateContainerSessions(__int64 a1, __int64 a2)
{
  int Pointer; // ebx
  void *v5; // rax
  DWORD v6; // eax
  unsigned __int16 v8[16]; // [rsp+38h] [rbp-20h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v8, 0, 0);
  if ( CSmartPublicBinding::operator void *(v8) )
  {
    v5 = CSmartPublicBinding::operator void *(v8);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035290, 6u, 0, v5, a1, a2).Pointer;
  }
  else
  {
    Pointer = -2147467263;
    _DbgPrintMessage(8, "Failed to open binding");
  }
  if ( Pointer >= 0 )
  {
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v8);
    return 1;
  }
  else
  {
    v6 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v6);
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v8);
    return 0;
  }
}

```

## disassembly

```asm
0x1800213c0  mov     [rsp+arg_0], rbx
0x1800213c5  push    rdi
0x1800213c6  sub     rsp, 50h
0x1800213ca  mov     rbx, rdx
0x1800213cd  mov     rdi, rcx
0x1800213d0  xor     r8d, r8d; int
0x1800213d3  xor     edx, edx; void *
0x1800213d5  lea     rcx, [rsp+58h+var_20]; this
0x1800213da  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800213df  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x1800213e4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800213e9  test    rax, rax
0x1800213ec  jnz     short loc_180021404
0x1800213ee  mov     ebx, 80004001h
0x1800213f3  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800213fa  lea     ecx, [rax+8]; int
0x1800213fd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021402  jmp     short loc_180021473
0x180021404  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180021409  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002140e  mov     [rsp+58h+arg_10], 0
0x180021417  mov     [rsp+58h+var_30], rbx
0x18002141c  mov     [rsp+58h+var_38], rdi
0x180021421  mov     r9, rax
0x180021424  xor     r8d, r8d; pReturnValue
0x180021427  lea     edx, [r8+6]; nProcNum
0x18002142b  lea     rcx, stru_180035290; pProxyInfo
0x180021432  call    cs:__imp_NdrClientCall3
0x180021439  nop     dword ptr [rax+rax+00h]
0x18002143e  mov     rbx, rax
0x180021441  mov     [rsp+58h+arg_10], rax
0x180021446  mov     [rsp+58h+var_28], eax
0x18002144a  jmp     short loc_180021473
0x18002144c  test    eax, eax
0x18002144e  jle     short loc_180021458
0x180021450  movzx   eax, ax
0x180021453  or      eax, 80070000h
0x180021458  mov     ebx, eax
0x18002145a  mov     [rsp+58h+var_28], eax
0x18002145e  mov     r8d, eax
0x180021461  lea     rdx, aRpcenumcontain; "RpcEnumContainerSessions threw an excep"...
0x180021468  mov     ecx, 8; int
0x18002146d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021472  nop
0x180021473  test    ebx, ebx
0x180021475  jns     short loc_18002149A
0x180021477  mov     ecx, ebx; int
0x180021479  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002147e  mov     ecx, eax; dwErrCode
0x180021480  call    cs:__imp_SetLastError
0x180021487  nop     dword ptr [rax+rax+00h]
0x18002148c  lea     rcx, [rsp+58h+var_20]; this
0x180021491  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180021496  xor     al, al
0x180021498  jmp     short loc_1800214A6
0x18002149a  lea     rcx, [rsp+58h+var_20]; this
0x18002149f  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800214a4  mov     al, 1
0x1800214a6  mov     rbx, [rsp+58h+arg_0]
0x1800214ab  add     rsp, 50h
0x1800214af  pop     rdi
0x1800214b0  retn
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

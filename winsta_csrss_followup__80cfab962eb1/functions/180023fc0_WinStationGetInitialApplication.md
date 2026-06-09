# WinStationGetInitialApplication

- ea: `0x180023fc0`
- end: `0x1800240f5`
- name: `WinStationGetInitialApplication`
- size: `309`
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
- `0x180023fc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800240ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800240ca`
- `RPCRT4!NdrClientCall3` at `0x180024060`
- `RPCRT4!NdrClientCall3` at `0x180024060`

## string_xrefs

- `0x180023ff8`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationGetInitialApplication(ULONG SessionId, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  char v9; // di
  void *v10; // rax
  int Pointer; // ebx
  DWORD v12; // eax
  ULONG v14; // [rsp+20h] [rbp-78h]
  unsigned __int16 v15[28]; // [rsp+60h] [rbp-38h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v15, 0, 1);
  v9 = 0;
  if ( CSmartPublicBinding::operator void *(v15) )
  {
    if ( SessionId == -1 )
      SessionId = NtCurrentPeb()->SessionId;
    v10 = CSmartPublicBinding::operator void *(v15);
    v14 = SessionId;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035140, 3u, 0, v10, v14, a2, a3, a4, a5).Pointer;
    if ( Pointer >= 0 )
    {
      v9 = 1;
    }
    else
    {
      _DbgPrintMessage(8, "RpcGetInitialApplication failed: 0x%x in %s", Pointer, "WinStationGetInitialApplication");
      v12 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v12);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v15);
  return v9;
}

```

## disassembly

```asm
0x180023fc0  push    rbx
0x180023fc2  push    rsi
0x180023fc3  push    rdi
0x180023fc4  push    r14
0x180023fc6  push    r15
0x180023fc8  sub     rsp, 70h
0x180023fcc  mov     rsi, r9
0x180023fcf  mov     r14, r8
0x180023fd2  mov     r15, rdx
0x180023fd5  mov     ebx, ecx
0x180023fd7  xor     edx, edx; void *
0x180023fd9  lea     r8d, [rdx+1]; int
0x180023fdd  lea     rcx, [rsp+98h+var_38]; this
0x180023fe2  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180023fe7  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180023fec  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180023ff1  xor     edi, edi
0x180023ff3  test    rax, rax
0x180023ff6  jnz     short loc_18002400C
0x180023ff8  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180023fff  lea     ecx, [rdi+8]; int
0x180024002  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180024007  jmp     loc_1800240DB
0x18002400c  cmp     ebx, 0FFFFFFFFh
0x18002400f  jnz     short loc_180024020
0x180024011  mov     rax, gs:60h
0x18002401a  mov     ebx, [rax+2C0h]
0x180024020  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180024025  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002402a  mov     [rsp+98h+var_40], rdi
0x18002402f  mov     rcx, [rsp+98h+arg_20]
0x180024037  mov     [rsp+98h+var_58], rcx
0x18002403c  mov     [rsp+98h+var_60], rsi
0x180024041  mov     [rsp+98h+var_68], r14
0x180024046  mov     [rsp+98h+var_70], r15
0x18002404b  mov     [rsp+98h+var_78], ebx
0x18002404f  mov     r9, rax
0x180024052  xor     r8d, r8d; pReturnValue
0x180024055  lea     edx, [r8+3]; nProcNum
0x180024059  lea     rcx, stru_180035140; pProxyInfo
0x180024060  call    cs:__imp_NdrClientCall3
0x180024067  nop     dword ptr [rax+rax+00h]
0x18002406c  mov     rbx, rax
0x18002406f  mov     [rsp+98h+var_40], rax
0x180024074  mov     [rsp+98h+var_48], eax
0x180024078  jmp     short loc_1800240A2
0x18002407a  test    eax, eax
0x18002407c  jle     short loc_180024086
0x18002407e  movzx   eax, ax
0x180024081  or      eax, 80070000h
0x180024086  mov     ebx, eax
0x180024088  mov     [rsp+98h+var_48], eax
0x18002408c  mov     r8d, eax
0x18002408f  lea     rdx, aRpcgetinitiala_0; "RpcGetInitialApplication threw an excep"...
0x180024096  mov     ecx, 8; int
0x18002409b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800240a0  xor     edi, edi
0x1800240a2  test    ebx, ebx
0x1800240a4  jns     short loc_1800240D8
0x1800240a6  lea     r9, aWinstationgeti_0; "WinStationGetInitialApplication"
0x1800240ad  mov     r8d, ebx
0x1800240b0  lea     rdx, aRpcgetinitiala; "RpcGetInitialApplication failed: 0x%x i"...
0x1800240b7  mov     ecx, 8; int
0x1800240bc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800240c1  mov     ecx, ebx; int
0x1800240c3  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800240c8  mov     ecx, eax; dwErrCode
0x1800240ca  call    cs:__imp_SetLastError
0x1800240d1  nop     dword ptr [rax+rax+00h]
0x1800240d6  jmp     short loc_1800240DB
0x1800240d8  mov     dil, 1
0x1800240db  lea     rcx, [rsp+98h+var_38]; this
0x1800240e0  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800240e5  mov     al, dil
0x1800240e8  add     rsp, 70h
0x1800240ec  pop     r15
0x1800240ee  pop     r14
0x1800240f0  pop     rdi
0x1800240f1  pop     rsi
0x1800240f2  pop     rbx
0x1800240f3  retn
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

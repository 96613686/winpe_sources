# WinStationSwitchToServicesSession

- ea: `0x180023000`
- end: `0x1800230d7`
- name: `WinStationSwitchToServicesSession`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180023000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800230b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800230b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023024`
- `RPCRT4!NdrClientCall3` at `0x180023065`
- `RPCRT4!NdrClientCall3` at `0x180023065`

## string_xrefs

- `0x180023094`: `RpcSwitchToServicesSession threw an exception: 0x%x`

## pseudocode

```c
bool WinStationSwitchToServicesSession()
{
  signed int LastError; // eax
  signed int Pointer; // ebx
  void *v2; // rax
  bool v3; // sf
  DWORD v4; // eax
  bool v5; // bl
  unsigned __int16 v7[16]; // [rsp+28h] [rbp-20h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v7, 0, 0);
  if ( CSmartPublicBinding::operator void *(v7) )
  {
    v2 = CSmartPublicBinding::operator void *(v7);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xDu, 0, v2).Pointer;
  }
  else
  {
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
  }
  v3 = Pointer < 0;
  if ( Pointer < 0 )
  {
    v4 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v4);
    v3 = Pointer < 0;
  }
  v5 = !v3;
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v7);
  return v5;
}

```

## disassembly

```asm
0x180023000  push    rbx
0x180023002  sub     rsp, 40h
0x180023006  xor     r8d, r8d; int
0x180023009  xor     edx, edx; void *
0x18002300b  lea     rcx, [rsp+48h+var_20]; this
0x180023010  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180023015  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18002301a  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002301f  test    rax, rax
0x180023022  jnz     short loc_180023041
0x180023024  call    cs:__imp_GetLastError
0x18002302b  nop     dword ptr [rax+rax+00h]
0x180023030  mov     ebx, eax
0x180023032  test    eax, eax
0x180023034  jle     short loc_1800230A6
0x180023036  movzx   ebx, ax
0x180023039  or      ebx, 80070000h
0x18002303f  jmp     short loc_1800230A6
0x180023041  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180023046  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002304b  mov     [rsp+48h+arg_0], 0
0x180023054  mov     r9, rax
0x180023057  xor     r8d, r8d; pReturnValue
0x18002305a  lea     edx, [r8+0Dh]; nProcNum
0x18002305e  lea     rcx, pProxyInfo; pProxyInfo
0x180023065  call    cs:__imp_NdrClientCall3
0x18002306c  nop     dword ptr [rax+rax+00h]
0x180023071  mov     rbx, rax
0x180023074  mov     [rsp+48h+arg_0], rax
0x180023079  mov     [rsp+48h+var_28], eax
0x18002307d  jmp     short loc_1800230A6
0x18002307f  test    eax, eax
0x180023081  jle     short loc_18002308B
0x180023083  movzx   eax, ax
0x180023086  or      eax, 80070000h
0x18002308b  mov     ebx, eax
0x18002308d  mov     [rsp+48h+var_28], eax
0x180023091  mov     r8d, eax
0x180023094  lea     rdx, aRpcswitchtoser; "RpcSwitchToServicesSession threw an exc"...
0x18002309b  mov     ecx, 8; int
0x1800230a0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800230a5  nop
0x1800230a6  test    ebx, ebx
0x1800230a8  jns     short loc_1800230C1
0x1800230aa  mov     ecx, ebx; int
0x1800230ac  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800230b1  mov     ecx, eax; dwErrCode
0x1800230b3  call    cs:__imp_SetLastError
0x1800230ba  nop     dword ptr [rax+rax+00h]
0x1800230bf  test    ebx, ebx
0x1800230c1  setns   bl
0x1800230c4  lea     rcx, [rsp+48h+var_20]; this
0x1800230c9  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800230ce  mov     al, bl
0x1800230d0  add     rsp, 40h
0x1800230d4  pop     rbx
0x1800230d5  retn
0x18003372f  push    rbp
0x180033731  sub     rsp, 20h
0x180033735  mov     rbp, rdx
0x180033738  mov     rcx, [rcx]
0x18003373b  mov     ecx, [rcx]; ExceptionCode
0x18003373d  call    cs:__imp_I_RpcExceptionFilter
0x180033744  nop     dword ptr [rax+rax+00h]
0x180033749  nop
0x18003374a  add     rsp, 20h
0x18003374e  pop     rbp
0x18003374f  retn
```

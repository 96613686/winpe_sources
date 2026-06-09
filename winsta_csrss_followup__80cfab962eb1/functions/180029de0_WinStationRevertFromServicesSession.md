# WinStationRevertFromServicesSession

- ea: `0x180029de0`
- end: `0x180029eb7`
- name: `WinStationRevertFromServicesSession`
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
- `0x180029de0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029e93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e04`
- `RPCRT4!NdrClientCall3` at `0x180029e45`
- `RPCRT4!NdrClientCall3` at `0x180029e45`

## string_xrefs

- `0x180029e74`: `RpcRevertFromServicesSession threw an exception: 0x%x`

## pseudocode

```c
bool WinStationRevertFromServicesSession()
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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xEu, 0, v2).Pointer;
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
0x180029de0  push    rbx
0x180029de2  sub     rsp, 40h
0x180029de6  xor     r8d, r8d; int
0x180029de9  xor     edx, edx; void *
0x180029deb  lea     rcx, [rsp+48h+var_20]; this
0x180029df0  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180029df5  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180029dfa  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029dff  test    rax, rax
0x180029e02  jnz     short loc_180029E21
0x180029e04  call    cs:__imp_GetLastError
0x180029e0b  nop     dword ptr [rax+rax+00h]
0x180029e10  mov     ebx, eax
0x180029e12  test    eax, eax
0x180029e14  jle     short loc_180029E86
0x180029e16  movzx   ebx, ax
0x180029e19  or      ebx, 80070000h
0x180029e1f  jmp     short loc_180029E86
0x180029e21  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180029e26  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029e2b  mov     [rsp+48h+arg_0], 0
0x180029e34  mov     r9, rax
0x180029e37  xor     r8d, r8d; pReturnValue
0x180029e3a  lea     edx, [r8+0Eh]; nProcNum
0x180029e3e  lea     rcx, pProxyInfo; pProxyInfo
0x180029e45  call    cs:__imp_NdrClientCall3
0x180029e4c  nop     dword ptr [rax+rax+00h]
0x180029e51  mov     rbx, rax
0x180029e54  mov     [rsp+48h+arg_0], rax
0x180029e59  mov     [rsp+48h+var_28], eax
0x180029e5d  jmp     short loc_180029E86
0x180029e5f  test    eax, eax
0x180029e61  jle     short loc_180029E6B
0x180029e63  movzx   eax, ax
0x180029e66  or      eax, 80070000h
0x180029e6b  mov     ebx, eax
0x180029e6d  mov     [rsp+48h+var_28], eax
0x180029e71  mov     r8d, eax
0x180029e74  lea     rdx, aRpcrevertfroms; "RpcRevertFromServicesSession threw an e"...
0x180029e7b  mov     ecx, 8; int
0x180029e80  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029e85  nop
0x180029e86  test    ebx, ebx
0x180029e88  jns     short loc_180029EA1
0x180029e8a  mov     ecx, ebx; int
0x180029e8c  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180029e91  mov     ecx, eax; dwErrCode
0x180029e93  call    cs:__imp_SetLastError
0x180029e9a  nop     dword ptr [rax+rax+00h]
0x180029e9f  test    ebx, ebx
0x180029ea1  setns   bl
0x180029ea4  lea     rcx, [rsp+48h+var_20]; this
0x180029ea9  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180029eae  mov     al, bl
0x180029eb0  add     rsp, 40h
0x180029eb4  pop     rbx
0x180029eb5  retn
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

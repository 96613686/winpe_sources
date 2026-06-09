# WinStationSwitchToServicesSession

- ea: `0x1800217a0`
- end: `0x180021864`
- name: `WinStationSwitchToServicesSession`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800217a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021847`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217c4`
- `RPCRT4!NdrClientCall3` at `0x1800217ff`
- `RPCRT4!NdrClientCall3` at `0x1800217ff`

## string_xrefs

- `0x180021828`: `RpcSwitchToServicesSession threw an exception: 0x%x`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032200, 0xDu, 0, v2).Pointer;
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
0x1800217a0  push    rbx
0x1800217a2  sub     rsp, 40h
0x1800217a6  xor     r8d, r8d; int
0x1800217a9  xor     edx, edx; void *
0x1800217ab  lea     rcx, [rsp+48h+var_20]; this
0x1800217b0  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800217b5  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x1800217ba  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800217bf  test    rax, rax
0x1800217c2  jnz     short loc_1800217DB
0x1800217c4  call    cs:__imp_GetLastError
0x1800217ca  mov     ebx, eax
0x1800217cc  test    eax, eax
0x1800217ce  jle     short loc_18002183A
0x1800217d0  movzx   ebx, ax
0x1800217d3  or      ebx, 80070000h
0x1800217d9  jmp     short loc_18002183A
0x1800217db  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x1800217e0  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800217e5  mov     [rsp+48h+arg_0], 0
0x1800217ee  mov     r9, rax
0x1800217f1  xor     r8d, r8d; pReturnValue
0x1800217f4  lea     edx, [r8+0Dh]; nProcNum
0x1800217f8  lea     rcx, stru_180032200; pProxyInfo
0x1800217ff  call    cs:__imp_NdrClientCall3
0x180021805  mov     rbx, rax
0x180021808  mov     [rsp+48h+arg_0], rax
0x18002180d  mov     [rsp+48h+var_28], eax
0x180021811  jmp     short loc_18002183A
0x180021813  test    eax, eax
0x180021815  jle     short loc_18002181F
0x180021817  movzx   eax, ax
0x18002181a  or      eax, 80070000h
0x18002181f  mov     ebx, eax
0x180021821  mov     [rsp+48h+var_28], eax
0x180021825  mov     r8d, eax
0x180021828  lea     rdx, aRpcswitchtoser; "RpcSwitchToServicesSession threw an exc"...
0x18002182f  mov     ecx, 8; int
0x180021834  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021839  nop
0x18002183a  test    ebx, ebx
0x18002183c  jns     short loc_18002184F
0x18002183e  mov     ecx, ebx; int
0x180021840  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180021845  mov     ecx, eax; dwErrCode
0x180021847  call    cs:__imp_SetLastError
0x18002184d  test    ebx, ebx
0x18002184f  setns   bl
0x180021852  lea     rcx, [rsp+48h+var_20]; this
0x180021857  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002185c  mov     al, bl
0x18002185e  add     rsp, 40h
0x180021862  pop     rbx
0x180021863  retn
0x18003082f  push    rbp
0x180030831  sub     rsp, 20h
0x180030835  mov     rbp, rdx
0x180030838  mov     rcx, [rcx]
0x18003083b  mov     ecx, [rcx]; ExceptionCode
0x18003083d  call    cs:__imp_I_RpcExceptionFilter
0x180030843  nop
0x180030844  add     rsp, 20h
0x180030848  pop     rbp
0x180030849  retn
```

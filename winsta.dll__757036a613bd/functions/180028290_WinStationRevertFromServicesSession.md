# WinStationRevertFromServicesSession

- ea: `0x180028290`
- end: `0x180028354`
- name: `WinStationRevertFromServicesSession`
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
- `0x180028290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028337`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282b4`
- `RPCRT4!NdrClientCall3` at `0x1800282ef`
- `RPCRT4!NdrClientCall3` at `0x1800282ef`

## string_xrefs

- `0x180028318`: `RpcRevertFromServicesSession threw an exception: 0x%x`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032200, 0xEu, 0, v2).Pointer;
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
0x180028290  push    rbx
0x180028292  sub     rsp, 40h
0x180028296  xor     r8d, r8d; int
0x180028299  xor     edx, edx; void *
0x18002829b  lea     rcx, [rsp+48h+var_20]; this
0x1800282a0  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800282a5  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x1800282aa  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800282af  test    rax, rax
0x1800282b2  jnz     short loc_1800282CB
0x1800282b4  call    cs:__imp_GetLastError
0x1800282ba  mov     ebx, eax
0x1800282bc  test    eax, eax
0x1800282be  jle     short loc_18002832A
0x1800282c0  movzx   ebx, ax
0x1800282c3  or      ebx, 80070000h
0x1800282c9  jmp     short loc_18002832A
0x1800282cb  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x1800282d0  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800282d5  mov     [rsp+48h+arg_0], 0
0x1800282de  mov     r9, rax
0x1800282e1  xor     r8d, r8d; pReturnValue
0x1800282e4  lea     edx, [r8+0Eh]; nProcNum
0x1800282e8  lea     rcx, stru_180032200; pProxyInfo
0x1800282ef  call    cs:__imp_NdrClientCall3
0x1800282f5  mov     rbx, rax
0x1800282f8  mov     [rsp+48h+arg_0], rax
0x1800282fd  mov     [rsp+48h+var_28], eax
0x180028301  jmp     short loc_18002832A
0x180028303  test    eax, eax
0x180028305  jle     short loc_18002830F
0x180028307  movzx   eax, ax
0x18002830a  or      eax, 80070000h
0x18002830f  mov     ebx, eax
0x180028311  mov     [rsp+48h+var_28], eax
0x180028315  mov     r8d, eax
0x180028318  lea     rdx, aRpcrevertfroms; "RpcRevertFromServicesSession threw an e"...
0x18002831f  mov     ecx, 8; int
0x180028324  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028329  nop
0x18002832a  test    ebx, ebx
0x18002832c  jns     short loc_18002833F
0x18002832e  mov     ecx, ebx; int
0x180028330  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180028335  mov     ecx, eax; dwErrCode
0x180028337  call    cs:__imp_SetLastError
0x18002833d  test    ebx, ebx
0x18002833f  setns   bl
0x180028342  lea     rcx, [rsp+48h+var_20]; this
0x180028347  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002834c  mov     al, bl
0x18002834e  add     rsp, 40h
0x180028352  pop     rbx
0x180028353  retn
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

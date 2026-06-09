# CTSLicense::CMonitor::OpenSenderProcess(ulong,void * *)

- ea: `0x18002f700`
- end: `0x18002f7bf`
- name: `?OpenSenderProcess@CMonitor@CTSLicense@@QEAAJKPEAPEAX@Z`
- size: `191`
- prototype: `int(CTSLicense::CMonitor *__hidden this, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18009f7e0`

## callees

- `0x180009940`
- `0x18002f700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f751`
- `RPCRT4!RpcRevertToSelf` at `0x18002f780`
- `RPCRT4!RpcRevertToSelf` at `0x18002f780`
- `RPCRT4!RpcImpersonateClient` at `0x18002f716`
- `RPCRT4!RpcImpersonateClient` at `0x18002f716`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002f73d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002f73d`

## string_xrefs

- `0x18002f76f`: `CTSLicense::CMonitor::OpenSenderProcess FAILED - Error in OpenProcess: 0x%x`
- `0x18002f728`: `CTSLicense::CMonitor::OpenSenderProcess FAILED - Error in RpcImpersonateClient: 0x%x`
- `0x18002f790`: `CTSLicense::CMonitor::OpenSenderProcess FAILED - Error in RpcRevertToSelf: 0x%x`

## pseudocode

```c
__int64 __fastcall CTSLicense::CMonitor::OpenSenderProcess(CTSLicense::CMonitor *this, DWORD a2, void **a3)
{
  unsigned int v5; // eax
  HANDLE v6; // rdi
  const char *v7; // rdx
  unsigned int v8; // ebx
  signed int LastError; // eax

  v5 = RpcImpersonateClient(0);
  if ( v5 )
  {
    v6 = 0;
    v7 = "CTSLicense::CMonitor::OpenSenderProcess FAILED - Error in RpcImpersonateClient: 0x%x";
LABEL_9:
    v8 = 1368;
    _DbgPrintMessage(8, v7, v5);
    goto LABEL_10;
  }
  v8 = 0;
  v6 = OpenProcess(0x410u, 0, a2);
  if ( !v6 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "CTSLicense::CMonitor::OpenSenderProcess FAILED - Error in OpenProcess: 0x%x", v8);
  }
  v5 = RpcRevertToSelf();
  if ( v5 )
  {
    v7 = "CTSLicense::CMonitor::OpenSenderProcess FAILED - Error in RpcRevertToSelf: 0x%x";
    goto LABEL_9;
  }
LABEL_10:
  *a3 = v6;
  return v8;
}

```

## disassembly

```asm
0x18002f700  mov     [rsp+arg_0], rbx
0x18002f705  mov     [rsp+arg_8], rsi
0x18002f70a  push    rdi
0x18002f70b  sub     rsp, 20h
0x18002f70f  xor     ecx, ecx; BindingHandle
0x18002f711  mov     rsi, r8
0x18002f714  mov     edi, edx
0x18002f716  call    cs:__imp_RpcImpersonateClient
0x18002f71d  nop     dword ptr [rax+rax+00h]
0x18002f722  test    eax, eax
0x18002f724  jz      short loc_18002F731
0x18002f726  xor     edi, edi
0x18002f728  lea     rdx, aCtslicenseCmon_1; "CTSLicense::CMonitor::OpenSenderProcess"...
0x18002f72f  jmp     short loc_18002F797
0x18002f731  mov     r8d, edi; dwProcessId
0x18002f734  xor     edx, edx; bInheritHandle
0x18002f736  mov     ecx, 410h; dwDesiredAccess
0x18002f73b  xor     ebx, ebx
0x18002f73d  call    cs:__imp_OpenProcess
0x18002f744  nop     dword ptr [rax+rax+00h]
0x18002f749  mov     rdi, rax
0x18002f74c  test    rax, rax
0x18002f74f  jnz     short loc_18002F780
0x18002f751  call    cs:__imp_GetLastError
0x18002f758  nop     dword ptr [rax+rax+00h]
0x18002f75d  mov     ebx, eax
0x18002f75f  test    eax, eax
0x18002f761  jle     short loc_18002F76C
0x18002f763  movzx   ebx, ax
0x18002f766  or      ebx, 80070000h
0x18002f76c  mov     r8d, ebx
0x18002f76f  lea     rdx, aCtslicenseCmon_0; "CTSLicense::CMonitor::OpenSenderProcess"...
0x18002f776  mov     ecx, 8; int
0x18002f77b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f780  call    cs:__imp_RpcRevertToSelf
0x18002f787  nop     dword ptr [rax+rax+00h]
0x18002f78c  test    eax, eax
0x18002f78e  jz      short loc_18002F7A9
0x18002f790  lea     rdx, aCtslicenseCmon_2; "CTSLicense::CMonitor::OpenSenderProcess"...
0x18002f797  mov     r8d, eax
0x18002f79a  mov     ecx, 8; int
0x18002f79f  mov     ebx, 558h
0x18002f7a4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f7a9  mov     [rsi], rdi
0x18002f7ac  mov     eax, ebx
0x18002f7ae  mov     rbx, [rsp+28h+arg_0]
0x18002f7b3  mov     rsi, [rsp+28h+arg_8]
0x18002f7b8  add     rsp, 20h
0x18002f7bc  pop     rdi
0x18002f7bd  retn
```

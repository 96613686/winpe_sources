# CTSLicense::CMonitor::OpenSenderProcess(ulong,void * *)

- ea: `0x18002dcb8`
- end: `0x18002dd5e`
- name: `?OpenSenderProcess@CMonitor@CTSLicense@@QEAAJKPEAPEAX@Z`
- size: `166`
- prototype: `int(CTSLicense::CMonitor *__hidden this, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18009b5d0`

## callees

- `0x18000a210`
- `0x18002dcb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcfd`
- `RPCRT4!RpcRevertToSelf` at `0x18002dd26`
- `RPCRT4!RpcRevertToSelf` at `0x18002dd26`
- `RPCRT4!RpcImpersonateClient` at `0x18002dcce`
- `RPCRT4!RpcImpersonateClient` at `0x18002dcce`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002dcef`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002dcef`

## string_xrefs

- `0x18002dd15`: `CTSLicense::CMonitor::OpenSenderProcess FAILED - Error in OpenProcess: 0x%x`
- `0x18002dcda`: `CTSLicense::CMonitor::OpenSenderProcess FAILED - Error in RpcImpersonateClient: 0x%x`
- `0x18002dd30`: `CTSLicense::CMonitor::OpenSenderProcess FAILED - Error in RpcRevertToSelf: 0x%x`

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
0x18002dcb8  mov     [rsp+arg_0], rbx
0x18002dcbd  mov     [rsp+arg_8], rsi
0x18002dcc2  push    rdi
0x18002dcc3  sub     rsp, 20h
0x18002dcc7  xor     ecx, ecx; BindingHandle
0x18002dcc9  mov     rsi, r8
0x18002dccc  mov     edi, edx
0x18002dcce  call    cs:__imp_RpcImpersonateClient
0x18002dcd4  test    eax, eax
0x18002dcd6  jz      short loc_18002DCE3
0x18002dcd8  xor     edi, edi
0x18002dcda  lea     rdx, aCtslicenseCmon_1; "CTSLicense::CMonitor::OpenSenderProcess"...
0x18002dce1  jmp     short loc_18002DD37
0x18002dce3  mov     r8d, edi; dwProcessId
0x18002dce6  xor     edx, edx; bInheritHandle
0x18002dce8  mov     ecx, 410h; dwDesiredAccess
0x18002dced  xor     ebx, ebx
0x18002dcef  call    cs:__imp_OpenProcess
0x18002dcf5  mov     rdi, rax
0x18002dcf8  test    rax, rax
0x18002dcfb  jnz     short loc_18002DD26
0x18002dcfd  call    cs:__imp_GetLastError
0x18002dd03  mov     ebx, eax
0x18002dd05  test    eax, eax
0x18002dd07  jle     short loc_18002DD12
0x18002dd09  movzx   ebx, ax
0x18002dd0c  or      ebx, 80070000h
0x18002dd12  mov     r8d, ebx
0x18002dd15  lea     rdx, aCtslicenseCmon_0; "CTSLicense::CMonitor::OpenSenderProcess"...
0x18002dd1c  mov     ecx, 8; int
0x18002dd21  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002dd26  call    cs:__imp_RpcRevertToSelf
0x18002dd2c  test    eax, eax
0x18002dd2e  jz      short loc_18002DD49
0x18002dd30  lea     rdx, aCtslicenseCmon_2; "CTSLicense::CMonitor::OpenSenderProcess"...
0x18002dd37  mov     r8d, eax
0x18002dd3a  mov     ecx, 8; int
0x18002dd3f  mov     ebx, 558h
0x18002dd44  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002dd49  mov     [rsi], rdi
0x18002dd4c  mov     eax, ebx
0x18002dd4e  mov     rbx, [rsp+28h+arg_0]
0x18002dd53  mov     rsi, [rsp+28h+arg_8]
0x18002dd58  add     rsp, 20h
0x18002dd5c  pop     rdi
0x18002dd5d  retn
```

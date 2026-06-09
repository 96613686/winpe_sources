# COMXProc::CAdviseClient::_Init(ulong,unsigned __int64,unsigned __int64)

- ea: `0x18002a150`
- end: `0x18002a253`
- name: `?_Init@CAdviseClient@COMXProc@@QEAAJK_K0@Z`
- size: `259`
- prototype: `__int64 __fastcall(HANDLE *this, DWORD, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800291e0`

## callees

- `0x180023220`
- `0x180023304`
- `0x180029fec`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002a220`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002a220`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a1b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a1b6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002a1e2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002a1e2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002a1a7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002a1a7`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002a20c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002a20c`

## pseudocode

```c
__int64 __fastcall COMXProc::CAdviseClient::_Init(HANDLE *this, DWORD a2, void *a3, void *a4)
{
  int v8; // ebx
  HANDLE v9; // rax
  HANDLE CurrentProcess; // rax
  void **v12; // [rsp+40h] [rbp-10h] BYREF
  int v13; // [rsp+48h] [rbp-8h]
  unsigned int Pid; // [rsp+80h] [rbp+30h] BYREF
  DWORD pSessionId; // [rsp+98h] [rbp+48h] BYREF

  COMXProc::CAdviseClient::_Cleanup((COMXProc::CAdviseClient *)this);
  this[3] = a4;
  v12 = &CImpersonateCOMCaller::`vftable';
  v13 = 0;
  v8 = CImpersonateCOMCaller::Impersonate((CImpersonateCOMCaller *)&v12);
  if ( v8 >= 0 )
  {
    v8 = -2147467259;
    v9 = OpenProcess(0x100068u, 0, a2);
    this[4] = v9;
    if ( v9 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(this[4], a3, CurrentProcess, this + 5, 0x1FFFFFu, 0, 0) )
        v8 = 0;
    }
    CImpersonateCOMCaller::_RevertToSelf((CImpersonateCOMCaller *)&v12);
  }
  *((_DWORD *)this + 12) = 0;
  Pid = 0;
  if ( !I_RpcBindingInqLocalClientPID(0, &Pid) )
  {
    pSessionId = 0;
    if ( ProcessIdToSessionId(Pid, &pSessionId) )
      *((_DWORD *)this + 12) = pSessionId;
  }
  v12 = &CImpersonateCOMCaller::`vftable';
  CImpersonateCOMCaller::_RevertToSelf((CImpersonateCOMCaller *)&v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002a150  mov     [rsp-28h+arg_8], rbx
0x18002a155  push    rbp
0x18002a156  push    rsi
0x18002a157  push    rdi
0x18002a158  push    r12
0x18002a15a  push    r14
0x18002a15c  mov     rbp, rsp
0x18002a15f  sub     rsp, 50h
0x18002a163  mov     rbx, r9
0x18002a166  mov     r14, r8
0x18002a169  mov     esi, edx
0x18002a16b  mov     rdi, rcx
0x18002a16e  call    ?_Cleanup@CAdviseClient@COMXProc@@QEAAJXZ; COMXProc::CAdviseClient::_Cleanup(void)
0x18002a173  lea     r12, ??_7CImpersonateCOMCaller@@6B@; const CImpersonateCOMCaller::`vftable'
0x18002a17a  mov     [rdi+18h], rbx
0x18002a17e  lea     rcx, [rbp+var_10]; this
0x18002a182  mov     [rbp+var_10], r12
0x18002a186  mov     [rbp+var_8], 0
0x18002a18d  call    ?Impersonate@CImpersonateCOMCaller@@UEAAJXZ; CImpersonateCOMCaller::Impersonate(void)
0x18002a192  mov     ebx, eax
0x18002a194  test    eax, eax
0x18002a196  js      short loc_18002A1F8
0x18002a198  mov     r8d, esi; dwProcessId
0x18002a19b  xor     edx, edx; bInheritHandle
0x18002a19d  mov     ecx, 100068h; dwDesiredAccess
0x18002a1a2  mov     ebx, 80004005h
0x18002a1a7  call    cs:__imp_OpenProcess
0x18002a1ad  mov     [rdi+20h], rax
0x18002a1b1  test    rax, rax
0x18002a1b4  jz      short loc_18002A1EF
0x18002a1b6  call    cs:__imp_GetCurrentProcess
0x18002a1bc  mov     rcx, [rdi+20h]; hSourceProcessHandle
0x18002a1c0  lea     r9, [rdi+28h]; lpTargetHandle
0x18002a1c4  mov     [rsp+50h+dwOptions], 0; dwOptions
0x18002a1cc  mov     r8, rax; hTargetProcessHandle
0x18002a1cf  mov     [rsp+50h+bInheritHandle], 0; bInheritHandle
0x18002a1d7  mov     rdx, r14; hSourceHandle
0x18002a1da  mov     [rsp+50h+dwDesiredAccess], 1FFFFFh; dwDesiredAccess
0x18002a1e2  call    cs:__imp_DuplicateHandle
0x18002a1e8  xor     ecx, ecx
0x18002a1ea  test    eax, eax
0x18002a1ec  cmovnz  ebx, ecx
0x18002a1ef  lea     rcx, [rbp+var_10]; this
0x18002a1f3  call    ?_RevertToSelf@CImpersonateCOMCaller@@AEAAJXZ; CImpersonateCOMCaller::_RevertToSelf(void)
0x18002a1f8  lea     rdx, [rbp+Pid]; Pid
0x18002a1fc  mov     dword ptr [rdi+30h], 0
0x18002a203  xor     ecx, ecx; Binding
0x18002a205  mov     [rbp+Pid], 0
0x18002a20c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18002a212  test    eax, eax
0x18002a214  jnz     short loc_18002A230
0x18002a216  mov     ecx, [rbp+Pid]; dwProcessId
0x18002a219  lea     rdx, [rbp+pSessionId]; pSessionId
0x18002a21d  mov     [rbp+pSessionId], eax
0x18002a220  call    cs:__imp_ProcessIdToSessionId
0x18002a226  test    eax, eax
0x18002a228  jz      short loc_18002A230
0x18002a22a  mov     eax, [rbp+pSessionId]
0x18002a22d  mov     [rdi+30h], eax
0x18002a230  lea     rcx, [rbp+var_10]; this
0x18002a234  mov     [rbp+var_10], r12
0x18002a238  call    ?_RevertToSelf@CImpersonateCOMCaller@@AEAAJXZ; CImpersonateCOMCaller::_RevertToSelf(void)
0x18002a23d  mov     eax, ebx
0x18002a23f  mov     rbx, [rsp+50h+arg_8]
0x18002a247  add     rsp, 50h
0x18002a24b  pop     r14
0x18002a24d  pop     r12
0x18002a24f  pop     rdi
0x18002a250  pop     rsi
0x18002a251  pop     rbp
0x18002a252  retn
```

# RPCSplWOW64GetProcessHndl

- ea: `0x14000dce0`
- end: `0x14000ddb1`
- name: `RPCSplWOW64GetProcessHndl`
- size: `209`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140007d00`
- `0x14000dce0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000dd77`
- `KERNEL32!GetLastError` at `0x14000dd8a`
- `KERNEL32!GetLastError` at `0x14000dd77`
- `KERNEL32!GetLastError` at `0x14000dd8a`
- `KERNEL32!CloseHandle` at `0x14000dd82`
- `KERNEL32!CloseHandle` at `0x14000dd82`
- `KERNEL32!OpenProcess` at `0x14000dd2a`
- `KERNEL32!OpenProcess` at `0x14000dd2a`
- `KERNEL32!DuplicateHandle` at `0x14000dd6d`
- `KERNEL32!DuplicateHandle` at `0x14000dd6d`
- `KERNEL32!GetCurrentProcess` at `0x14000dd38`
- `KERNEL32!GetCurrentProcess` at `0x14000dd41`
- `KERNEL32!GetCurrentProcess` at `0x14000dd38`
- `KERNEL32!GetCurrentProcess` at `0x14000dd41`
- `RPCRT4!RpcRevertToSelf` at `0x14000dd92`
- `RPCRT4!RpcRevertToSelf` at `0x14000dd92`
- `RPCRT4!RpcImpersonateClient` at `0x14000dd05`
- `RPCRT4!RpcImpersonateClient` at `0x14000dd05`

## pseudocode

```c
HANDLE __fastcall RPCSplWOW64GetProcessHndl(DWORD dwProcessId, _DWORD *a2)
{
  RPC_STATUS v4; // eax
  HANDLE v5; // rsi
  HANDLE CurrentProcess; // rbx
  HANDLE v7; // rax
  HANDLE TargetHandle; // [rsp+58h] [rbp+10h] BYREF

  TargetHandle = 0;
  *a2 = 0;
  v4 = RpcImpersonateClient(0);
  if ( v4 )
  {
    *a2 = v4;
  }
  else
  {
    TLoad64BitDllsMgr::RefreshLifeSpan(pGLdrObj);
    v5 = OpenProcess(0x40u, 1, dwProcessId);
    if ( v5 )
    {
      CurrentProcess = GetCurrentProcess();
      v7 = GetCurrentProcess();
      if ( !DuplicateHandle(v7, CurrentProcess, v5, &TargetHandle, 0x100400u, 0, 0) )
        *a2 = GetLastError();
      CloseHandle(v5);
    }
    else
    {
      *a2 = GetLastError();
    }
    RpcRevertToSelf();
  }
  return TargetHandle;
}

```

## disassembly

```asm
0x14000dce0  mov     [rsp+arg_0], rbx
0x14000dce5  mov     [rsp+arg_10], rsi
0x14000dcea  push    rdi
0x14000dceb  sub     rsp, 40h
0x14000dcef  mov     ebx, ecx
0x14000dcf1  mov     [rsp+48h+TargetHandle], 0
0x14000dcfa  xor     ecx, ecx; BindingHandle
0x14000dcfc  mov     dword ptr [rdx], 0
0x14000dd02  mov     rdi, rdx
0x14000dd05  call    cs:__imp_RpcImpersonateClient
0x14000dd0b  test    eax, eax
0x14000dd0d  jnz     loc_14000DD9A
0x14000dd13  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000dd1a  call    ?RefreshLifeSpan@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::RefreshLifeSpan(void)
0x14000dd1f  mov     edx, 1; bInheritHandle
0x14000dd24  mov     r8d, ebx; dwProcessId
0x14000dd27  lea     ecx, [rdx+3Fh]; dwDesiredAccess
0x14000dd2a  call    cs:__imp_OpenProcess
0x14000dd30  mov     rsi, rax
0x14000dd33  test    rax, rax
0x14000dd36  jz      short loc_14000DD8A
0x14000dd38  call    cs:__imp_GetCurrentProcess
0x14000dd3e  mov     rbx, rax
0x14000dd41  call    cs:__imp_GetCurrentProcess
0x14000dd47  mov     [rsp+48h+dwOptions], 0; dwOptions
0x14000dd4f  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x14000dd54  mov     rcx, rax; hSourceProcessHandle
0x14000dd57  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x14000dd5f  mov     r8, rsi; hTargetProcessHandle
0x14000dd62  mov     [rsp+48h+dwDesiredAccess], 100400h; dwDesiredAccess
0x14000dd6a  mov     rdx, rbx; hSourceHandle
0x14000dd6d  call    cs:__imp_DuplicateHandle
0x14000dd73  test    eax, eax
0x14000dd75  jnz     short loc_14000DD7F
0x14000dd77  call    cs:__imp_GetLastError
0x14000dd7d  mov     [rdi], eax
0x14000dd7f  mov     rcx, rsi; hObject
0x14000dd82  call    cs:__imp_CloseHandle
0x14000dd88  jmp     short loc_14000DD92
0x14000dd8a  call    cs:__imp_GetLastError
0x14000dd90  mov     [rdi], eax
0x14000dd92  call    cs:__imp_RpcRevertToSelf
0x14000dd98  jmp     short loc_14000DD9C
0x14000dd9a  mov     [rdi], eax
0x14000dd9c  mov     rax, [rsp+48h+TargetHandle]
0x14000dda1  mov     rbx, [rsp+48h+arg_0]
0x14000dda6  mov     rsi, [rsp+48h+arg_10]
0x14000ddab  add     rsp, 40h
0x14000ddaf  pop     rdi
0x14000ddb0  retn
```

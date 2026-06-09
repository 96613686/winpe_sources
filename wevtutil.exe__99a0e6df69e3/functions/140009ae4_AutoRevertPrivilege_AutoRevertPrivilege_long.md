# AutoRevertPrivilege::AutoRevertPrivilege(long)

- ea: `0x140009ae4`
- end: `0x140009b52`
- name: `??0AutoRevertPrivilege@@QEAA@J@Z`
- size: `110`
- prototype: `AutoRevertPrivilege *__fastcall(AutoRevertPrivilege *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400238ac`

## callees

- `0x140009a38`
- `0x140009ae4`
- `0x14001b5e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140009b2d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140009b2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140009b1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140009b1c`

## pseudocode

```c
AutoRevertPrivilege *__fastcall AutoRevertPrivilege::AutoRevertPrivilege(AutoRevertPrivilege *this, int a2)
{
  void **v3; // rbx
  HANDLE CurrentProcess; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = a2;
  *((_BYTE *)this + 16) = 0;
  v3 = (void **)tlx::replace<tlx::file_handle_traits>();
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20u, v3) )
    *((_BYTE *)this + 16) = AutoRevertPrivilege::EnableOrDisablePrivilege(this, 1);
  return this;
}

```

## disassembly

```asm
0x140009ae4  mov     [rsp+arg_8], rbx
0x140009ae9  push    rdi
0x140009aea  sub     rsp, 20h
0x140009aee  movsxd  rax, edx
0x140009af1  mov     rdi, rcx
0x140009af4  mov     dword ptr [rsp+28h+arg_0], eax
0x140009af8  shr     rax, 20h
0x140009afc  mov     qword ptr [rcx], 0
0x140009b03  mov     dword ptr [rsp+28h+arg_0+4], eax
0x140009b07  mov     rax, [rsp+28h+arg_0]
0x140009b0c  mov     [rcx+8], rax
0x140009b10  mov     byte ptr [rcx+10h], 0
0x140009b14  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x140009b19  mov     rbx, rax
0x140009b1c  call    cs:__imp_GetCurrentProcess
0x140009b22  mov     r8, rbx; TokenHandle
0x140009b25  mov     edx, 20h ; ' '; DesiredAccess
0x140009b2a  mov     rcx, rax; ProcessHandle
0x140009b2d  call    cs:__imp_OpenProcessToken
0x140009b33  test    eax, eax
0x140009b35  jz      short loc_140009B44
0x140009b37  mov     dl, 1; bool
0x140009b39  mov     rcx, rdi; this
0x140009b3c  call    ?EnableOrDisablePrivilege@AutoRevertPrivilege@@AEAA_N_N@Z; AutoRevertPrivilege::EnableOrDisablePrivilege(bool)
0x140009b41  mov     [rdi+10h], al
0x140009b44  mov     rbx, [rsp+28h+arg_8]
0x140009b49  mov     rax, rdi
0x140009b4c  add     rsp, 20h
0x140009b50  pop     rdi
0x140009b51  retn
```

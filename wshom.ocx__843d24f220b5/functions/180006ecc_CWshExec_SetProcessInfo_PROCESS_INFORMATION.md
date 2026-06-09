# CWshExec::SetProcessInfo(_PROCESS_INFORMATION *)

- ea: `0x180006ecc`
- end: `0x180006ef6`
- name: `?SetProcessInfo@CWshExec@@QEAAJPEAU_PROCESS_INFORMATION@@@Z`
- size: `42`
- prototype: `__int64 __fastcall(CWshExec *__hidden this, struct _PROCESS_INFORMATION *)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x18000ce3c`
- `0x18000cf70`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180006ee9`
- `KERNEL32!CloseHandle` at `0x180006ee9`

## pseudocode

```c
__int64 __fastcall CWshExec::SetProcessInfo(CWshExec *this, struct _PROCESS_INFORMATION *a2)
{
  *((_DWORD *)this + 24) = a2->dwProcessId;
  *((_QWORD *)this + 13) = a2->hProcess;
  _InterlockedExchange((volatile __int32 *)this + 29, 1);
  CloseHandle(a2->hThread);
  return 0;
}

```

## disassembly

```asm
0x180006ecc  sub     rsp, 28h
0x180006ed0  mov     eax, [rdx+10h]
0x180006ed3  mov     [rcx+60h], eax
0x180006ed6  mov     rax, [rdx]
0x180006ed9  mov     [rcx+68h], rax
0x180006edd  mov     eax, 1
0x180006ee2  xchg    eax, [rcx+74h]
0x180006ee5  mov     rcx, [rdx+8]; hObject
0x180006ee9  call    cs:__imp_CloseHandle
0x180006eef  xor     eax, eax
0x180006ef1  add     rsp, 28h
0x180006ef5  retn
```

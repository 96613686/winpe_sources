# CATUtils::IsProcessInATJob(void *)

- ea: `0x14001cd1c`
- end: `0x14001cda9`
- name: `?IsProcessInATJob@CATUtils@@SAHPEAX@Z`
- size: `141`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140012f54`
- `0x1400172b0`

## callees

- `0x14001cd1c`

## import_xrefs

- `KERNEL32!IsProcessInJob` at `0x14001cd6c`
- `KERNEL32!IsProcessInJob` at `0x14001cd6c`
- `KERNEL32!OpenJobObjectW` at `0x14001cd41`
- `KERNEL32!OpenJobObjectW` at `0x14001cd41`
- `KERNEL32!GetCurrentProcess` at `0x14001cd55`
- `KERNEL32!GetCurrentProcess` at `0x14001cd55`
- `KERNEL32!CloseHandle` at `0x14001cd7d`
- `KERNEL32!CloseHandle` at `0x14001cd7d`

## string_xrefs

- `0x14001cd35`: `WinlogonAccess`

## pseudocode

```c
_BOOL8 __fastcall CATUtils::IsProcessInATJob(void *a1)
{
  BOOL v1; // ebx
  HANDLE v2; // rdi
  HANDLE CurrentProcess; // rax
  WINBOOL Result; // [rsp+30h] [rbp+8h] BYREF
  int v6; // [rsp+34h] [rbp+Ch]

  v6 = HIDWORD(a1);
  v1 = 0;
  Result = 0;
  v2 = OpenJobObjectW(4u, 0, L"WinlogonAccess");
  if ( v2 )
  {
    CurrentProcess = GetCurrentProcess();
    v1 = IsProcessInJob(CurrentProcess, v2, &Result);
    CloseHandle(v2);
  }
  return Result && v1;
}

```

## disassembly

```asm
0x14001cd1c  mov     [rsp+arg_8], rbx
0x14001cd21  mov     qword ptr [rsp+Result], rcx
0x14001cd26  push    rdi
0x14001cd27  sub     rsp, 20h
0x14001cd2b  xor     ebx, ebx
0x14001cd2d  mov     [rsp+28h+Result], 0
0x14001cd35  lea     r8, aWinlogonaccess; "WinlogonAccess"
0x14001cd3c  xor     edx, edx; bInheritHandle
0x14001cd3e  lea     ecx, [rbx+4]; dwDesiredAccess
0x14001cd41  call    cs:__imp_OpenJobObjectW
0x14001cd48  nop     dword ptr [rax+rax+00h]
0x14001cd4d  mov     rdi, rax
0x14001cd50  test    rax, rax
0x14001cd53  jz      short loc_14001CD89
0x14001cd55  call    cs:__imp_GetCurrentProcess
0x14001cd5c  nop     dword ptr [rax+rax+00h]
0x14001cd61  lea     r8, [rsp+28h+Result]; Result
0x14001cd66  mov     rdx, rdi; JobHandle
0x14001cd69  mov     rcx, rax; ProcessHandle
0x14001cd6c  call    cs:__imp_IsProcessInJob
0x14001cd73  nop     dword ptr [rax+rax+00h]
0x14001cd78  mov     rcx, rdi; hObject
0x14001cd7b  mov     ebx, eax
0x14001cd7d  call    cs:__imp_CloseHandle
0x14001cd84  nop     dword ptr [rax+rax+00h]
0x14001cd89  cmp     [rsp+28h+Result], 0
0x14001cd8e  jz      short loc_14001CD9B
0x14001cd90  test    ebx, ebx
0x14001cd92  jz      short loc_14001CD9B
0x14001cd94  mov     eax, 1
0x14001cd99  jmp     short loc_14001CD9D
0x14001cd9b  xor     eax, eax
0x14001cd9d  mov     rbx, [rsp+28h+arg_8]
0x14001cda2  add     rsp, 20h
0x14001cda6  pop     rdi
0x14001cda7  retn
```

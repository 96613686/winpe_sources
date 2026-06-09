# SuspendImpersonate(void * *)

- ea: `0x1800108e4`
- end: `0x180010986`
- name: `?SuspendImpersonate@@YAKPEAPEAX@Z`
- size: `162`
- prototype: `unsigned int __fastcall(HANDLE hObject)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000e7d0`

## callees

- `0x1800108e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010932`
- `KERNEL32!GetLastError` at `0x18001095f`
- `KERNEL32!GetLastError` at `0x180010932`
- `KERNEL32!GetLastError` at `0x18001095f`
- `KERNEL32!CloseHandle` at `0x180010943`
- `KERNEL32!CloseHandle` at `0x180010943`
- `KERNEL32!GetCurrentThread` at `0x1800108f1`
- `KERNEL32!GetCurrentThread` at `0x1800108f1`
- `ADVAPI32!SetThreadToken` at `0x180010922`
- `ADVAPI32!SetThreadToken` at `0x180010922`
- `ADVAPI32!OpenThreadToken` at `0x18001090c`
- `ADVAPI32!OpenThreadToken` at `0x18001090c`

## pseudocode

```c
__int64 __fastcall SuspendImpersonate(_QWORD *hObject)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)hObject) )
  {
    LastError = 0;
    if ( !SetThreadToken(0, 0) )
    {
      LastError = GetLastError();
      CloseHandle(hObject);
      *hObject = 0;
    }
  }
  else
  {
    *hObject = 0;
    LastError = GetLastError();
    if ( LastError == 1008 )
      return 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800108e4  mov     [rsp+arg_0], rbx
0x1800108e9  push    rdi
0x1800108ea  sub     rsp, 20h
0x1800108ee  mov     rdi, rcx
0x1800108f1  call    cs:__imp_GetCurrentThread
0x1800108f8  nop     dword ptr [rax+rax+00h]
0x1800108fd  mov     edx, 0Ch; DesiredAccess
0x180010902  mov     r9, rdi; TokenHandle
0x180010905  mov     rcx, rax; ThreadHandle
0x180010908  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18001090c  call    cs:__imp_OpenThreadToken
0x180010913  nop     dword ptr [rax+rax+00h]
0x180010918  test    eax, eax
0x18001091a  jz      short loc_180010958
0x18001091c  xor     edx, edx; Token
0x18001091e  xor     ecx, ecx; Thread
0x180010920  xor     ebx, ebx
0x180010922  call    cs:__imp_SetThreadToken
0x180010929  nop     dword ptr [rax+rax+00h]
0x18001092e  test    eax, eax
0x180010930  jnz     short loc_180010978
0x180010932  call    cs:__imp_GetLastError
0x180010939  nop     dword ptr [rax+rax+00h]
0x18001093e  mov     rcx, rdi; hObject
0x180010941  mov     ebx, eax
0x180010943  call    cs:__imp_CloseHandle
0x18001094a  nop     dword ptr [rax+rax+00h]
0x18001094f  mov     qword ptr [rdi], 0
0x180010956  jmp     short loc_180010978
0x180010958  mov     qword ptr [rdi], 0
0x18001095f  call    cs:__imp_GetLastError
0x180010966  nop     dword ptr [rax+rax+00h]
0x18001096b  mov     ebx, eax
0x18001096d  xor     eax, eax
0x18001096f  cmp     ebx, 3F0h
0x180010975  cmovz   ebx, eax
0x180010978  mov     eax, ebx
0x18001097a  mov     rbx, [rsp+28h+arg_0]
0x18001097f  add     rsp, 20h
0x180010983  pop     rdi
0x180010984  retn
```

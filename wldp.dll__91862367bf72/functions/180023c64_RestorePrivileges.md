# RestorePrivileges

- ea: `0x180023c64`
- end: `0x180023cc9`
- name: `RestorePrivileges`
- size: `101`
- prototype: `__int64 __fastcall(HANDLE hObject, PTOKEN_PRIVILEGES NewState)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023cd0`
- `0x180024430`

## callees

- `0x180023c64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023cb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023cb6`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180023c8b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180023c8b`

## pseudocode

```c
__int64 __fastcall RestorePrivileges(HANDLE hObject, PTOKEN_PRIVILEGES NewState)
{
  signed int LastError; // eax
  unsigned int v4; // ebx

  if ( AdjustTokenPrivileges(hObject, 0, NewState, 0, 0, 0) )
  {
    v4 = 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hObject )
    CloseHandle(hObject);
  return v4;
}

```

## disassembly

```asm
0x180023c64  mov     [rsp+arg_0], rbx
0x180023c69  push    rdi
0x180023c6a  sub     rsp, 30h
0x180023c6e  mov     r8, rdx; NewState
0x180023c71  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180023c7a  xor     edx, edx; DisableAllPrivileges
0x180023c7c  mov     [rsp+38h+PreviousState], 0; PreviousState
0x180023c85  xor     r9d, r9d; BufferLength
0x180023c88  mov     rdi, rcx
0x180023c8b  call    cs:__imp_AdjustTokenPrivileges
0x180023c91  test    eax, eax
0x180023c93  jnz     short loc_180023CAC
0x180023c95  call    cs:__imp_GetLastError
0x180023c9b  mov     ebx, eax
0x180023c9d  test    eax, eax
0x180023c9f  jle     short loc_180023CAE
0x180023ca1  movzx   ebx, ax
0x180023ca4  or      ebx, 80070000h
0x180023caa  jmp     short loc_180023CAE
0x180023cac  xor     ebx, ebx
0x180023cae  test    rdi, rdi
0x180023cb1  jz      short loc_180023CBC
0x180023cb3  mov     rcx, rdi; hObject
0x180023cb6  call    cs:__imp_CloseHandle
0x180023cbc  mov     eax, ebx
0x180023cbe  mov     rbx, [rsp+38h+arg_0]
0x180023cc3  add     rsp, 30h
0x180023cc7  pop     rdi
0x180023cc8  retn
```

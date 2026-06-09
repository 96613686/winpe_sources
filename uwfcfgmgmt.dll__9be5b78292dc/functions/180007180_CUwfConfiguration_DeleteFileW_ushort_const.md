# CUwfConfiguration::DeleteFileW(ushort const *)

- ea: `0x180007180`
- end: `0x1800071c7`
- name: `?DeleteFileW@CUwfConfiguration@@QEAAJPEBG@Z`
- size: `71`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x180007250`

## callees

- `0x180007180`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071aa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800071a0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800071a0`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x180007198`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x180007198`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::DeleteFileW(CUwfConfiguration *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  void *v4; // rdx
  BOOL v5; // eax
  signed int LastError; // eax

  v3 = 0;
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 == (void *)-1LL )
    v5 = DeleteFileW(a2);
  else
    v5 = DeleteFileTransactedW(a2, v4);
  if ( !v5 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180007180  push    rbx
0x180007182  sub     rsp, 20h
0x180007186  mov     rax, rdx
0x180007189  xor     ebx, ebx
0x18000718b  mov     rdx, [rcx+8]; hTransaction
0x18000718f  mov     rcx, rax; lpFileName
0x180007192  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180007196  jz      short loc_1800071A0
0x180007198  call    cs:__imp_DeleteFileTransactedW
0x18000719e  jmp     short loc_1800071A6
0x1800071a0  call    cs:__imp_DeleteFileW
0x1800071a6  test    eax, eax
0x1800071a8  jnz     short loc_1800071BF
0x1800071aa  call    cs:__imp_GetLastError
0x1800071b0  mov     ebx, eax
0x1800071b2  test    eax, eax
0x1800071b4  jle     short loc_1800071BF
0x1800071b6  movzx   ebx, ax
0x1800071b9  or      ebx, 80070000h
0x1800071bf  mov     eax, ebx
0x1800071c1  add     rsp, 20h
0x1800071c5  pop     rbx
0x1800071c6  retn
```

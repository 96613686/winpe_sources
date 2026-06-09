# FileInUse(ushort const *,ushort const *)

- ea: `0x180001d9c`
- end: `0x180001def`
- name: `?FileInUse@@YAHPEBG0@Z`
- size: `83`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002b00`

## callees

- `0x180001d9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dd0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001dc4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001dc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001de1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001de1`

## pseudocode

```c
__int64 __fastcall FileInUse(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  HANDLE FileW; // rax

  v2 = 0;
  FileW = CreateFileW(a1, 0xC0000000, 0, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    LOBYTE(v2) = GetLastError() == 32;
  else
    CloseHandle(FileW);
  return v2;
}

```

## disassembly

```asm
0x180001d9c  push    rbx
0x180001d9e  sub     rsp, 40h
0x180001da2  xor     ebx, ebx
0x180001da4  xor     r9d, r9d; lpSecurityAttributes
0x180001da7  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180001dac  xor     r8d, r8d; dwShareMode
0x180001daf  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180001db7  mov     edx, 0C0000000h; dwDesiredAccess
0x180001dbc  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180001dc4  call    cs:__imp_CreateFileW
0x180001dca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001dce  jnz     short loc_180001DDE
0x180001dd0  call    cs:__imp_GetLastError
0x180001dd6  cmp     eax, 20h ; ' '
0x180001dd9  setz    bl
0x180001ddc  jmp     short loc_180001DE7
0x180001dde  mov     rcx, rax; hObject
0x180001de1  call    cs:__imp_CloseHandle
0x180001de7  mov     eax, ebx
0x180001de9  add     rsp, 40h
0x180001ded  pop     rbx
0x180001dee  retn
```

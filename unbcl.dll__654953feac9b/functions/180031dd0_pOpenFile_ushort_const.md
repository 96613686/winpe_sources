# pOpenFile(ushort const *)

- ea: `0x180031dd0`
- end: `0x180031e38`
- name: `?pOpenFile@@YAPEAXPEBG@Z`
- size: `104`
- prototype: `HANDLE __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180029b30`
- `0x18002a870`
- `0x1800306a0`

## callees

- `0x180031dd0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180031dfb`
- `KERNEL32!CreateFileW` at `0x180031e2c`
- `KERNEL32!CreateFileW` at `0x180031dfb`
- `KERNEL32!CreateFileW` at `0x180031e2c`

## pseudocode

```c
HANDLE __fastcall pOpenFile(LPCWSTR lpFileName)
{
  HANDLE result; // rax

  result = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x200000u, 0);
  if ( result == (HANDLE)-1LL )
    return CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x2200000u, 0);
  return result;
}

```

## disassembly

```asm
0x180031dd0  push    rbx
0x180031dd2  sub     rsp, 40h
0x180031dd6  xor     r9d, r9d; lpSecurityAttributes
0x180031dd9  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180031de2  mov     [rsp+48h+dwFlagsAndAttributes], 200000h; dwFlagsAndAttributes
0x180031dea  xor     edx, edx; dwDesiredAccess
0x180031dec  mov     rbx, rcx
0x180031def  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180031df7  lea     r8d, [r9+7]; dwShareMode
0x180031dfb  call    cs:__imp_CreateFileW
0x180031e01  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031e05  jnz     short loc_180031E32
0x180031e07  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180031e10  lea     r8d, [rax+8]; dwShareMode
0x180031e14  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180031e1c  xor     r9d, r9d; lpSecurityAttributes
0x180031e1f  xor     edx, edx; dwDesiredAccess
0x180031e21  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180031e29  mov     rcx, rbx; lpFileName
0x180031e2c  call    cs:__imp_CreateFileW
0x180031e32  add     rsp, 40h
0x180031e36  pop     rbx
0x180031e37  retn
```

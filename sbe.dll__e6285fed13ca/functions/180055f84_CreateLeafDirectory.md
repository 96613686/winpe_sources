# CreateLeafDirectory

- ea: `0x180055f84`
- end: `0x180055fca`
- name: `CreateLeafDirectory`
- size: `70`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180056b10`

## callees

- `0x180055f84`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180055fb0`
- `KERNEL32!GetFileAttributesW` at `0x180055fa0`
- `KERNEL32!GetFileAttributesW` at `0x180055fa0`
- `KERNEL32!CreateDirectoryW` at `0x180055f8f`
- `KERNEL32!CreateDirectoryW` at `0x180055f8f`

## pseudocode

```c
DWORD __fastcall CreateLeafDirectory(LPCWSTR lpFileName)
{
  DWORD FileAttributesW; // eax

  if ( CreateDirectoryW(lpFileName, 0) )
    return 0;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
    return GetLastError();
  else
    return (FileAttributesW & 0x10) == 0 ? 0x10B : 0;
}

```

## disassembly

```asm
0x180055f84  push    rbx
0x180055f86  sub     rsp, 20h
0x180055f8a  xor     edx, edx; lpSecurityAttributes
0x180055f8c  mov     rbx, rcx
0x180055f8f  call    cs:__imp_CreateDirectoryW
0x180055f95  test    eax, eax
0x180055f97  jz      short loc_180055F9D
0x180055f99  xor     eax, eax
0x180055f9b  jmp     short loc_180055FC4
0x180055f9d  mov     rcx, rbx; lpFileName
0x180055fa0  call    cs:__imp_GetFileAttributesW
0x180055fa6  cmp     eax, 0FFFFFFFFh
0x180055fa9  jnz     short loc_180055FB7
0x180055fab  add     rsp, 20h
0x180055faf  pop     rbx
0x180055fb0  jmp     cs:__imp_GetLastError
0x180055fb7  and     al, 10h
0x180055fb9  neg     al
0x180055fbb  sbb     eax, eax
0x180055fbd  not     eax
0x180055fbf  and     eax, 10Bh
0x180055fc4  add     rsp, 20h
0x180055fc8  pop     rbx
0x180055fc9  retn
```

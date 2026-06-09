# FileStream::Read(void *,ulong,ulong *)

- ea: `0x180011680`
- end: `0x1800116b6`
- name: `?Read@FileStream@@UEAAJPEAXKPEAK@Z`
- size: `54`
- prototype: `__int64 __fastcall(FileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180011680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001169f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001169f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180011691`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180011691`

## pseudocode

```c
signed int __fastcall FileStream::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax

  if ( ReadFile(this[1], a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180011680  sub     rsp, 38h
0x180011684  mov     rcx, [rcx+8]; hFile
0x180011688  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180011691  call    cs:__imp_ReadFile
0x180011697  test    eax, eax
0x180011699  jz      short loc_18001169F
0x18001169b  xor     eax, eax
0x18001169d  jmp     short loc_1800116B1
0x18001169f  call    cs:__imp_GetLastError
0x1800116a5  test    eax, eax
0x1800116a7  jle     short loc_1800116B1
0x1800116a9  movzx   eax, ax
0x1800116ac  or      eax, 80070000h
0x1800116b1  add     rsp, 38h
0x1800116b5  retn
```

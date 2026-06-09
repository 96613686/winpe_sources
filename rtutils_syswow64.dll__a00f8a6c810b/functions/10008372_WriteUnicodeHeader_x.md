# WriteUnicodeHeader(x)

- ea: `0x10008372`
- end: `0x100083ac`
- name: `_WriteUnicodeHeader@4`
- size: `58`
- prototype: `int __thiscall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x10007954`

## callees

- `0x10008372`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x10008395`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x10008395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000839f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000839f`

## pseudocode

```c
DWORD __thiscall WriteUnicodeHeader(HANDLE hFile)
{
  int v1; // esi
  DWORD NumberOfBytesWritten; // [esp+4h] [ebp-8h] BYREF
  __int16 Buffer; // [esp+8h] [ebp-4h] BYREF

  v1 = 0;
  NumberOfBytesWritten = 0;
  Buffer = -257;
  if ( !WriteFile(hFile, &Buffer, 2u, &NumberOfBytesWritten, 0) )
    return GetLastError();
  return v1;
}

```

## disassembly

```asm
0x10008372  mov     edi, edi
0x10008374  push    ebp
0x10008375  mov     ebp, esp
0x10008377  push    ecx
0x10008378  push    ecx
0x10008379  push    esi
0x1000837a  xor     esi, esi
0x1000837c  mov     [ebp+NumberOfBytesWritten], 0
0x10008383  push    esi; lpOverlapped
0x10008384  lea     eax, [ebp+NumberOfBytesWritten]
0x10008387  mov     [ebp+Buffer], 0FEFFh
0x1000838d  push    eax; lpNumberOfBytesWritten
0x1000838e  push    2; nNumberOfBytesToWrite
0x10008390  lea     eax, [ebp+Buffer]
0x10008393  push    eax; lpBuffer
0x10008394  push    ecx; hFile
0x10008395  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x1000839b  test    eax, eax
0x1000839d  jnz     short loc_100083A7
0x1000839f  call    ds:__imp__GetLastError@0; GetLastError()
0x100083a5  mov     esi, eax
0x100083a7  mov     eax, esi
0x100083a9  pop     esi
0x100083aa  leave
0x100083ab  retn
```

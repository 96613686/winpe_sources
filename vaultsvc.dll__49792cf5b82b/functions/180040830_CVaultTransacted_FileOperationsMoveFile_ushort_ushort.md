# CVaultTransacted::FileOperationsMoveFile(ushort *,ushort *)

- ea: `0x180040830`
- end: `0x180040873`
- name: `?FileOperationsMoveFile@CVaultTransacted@@UEAAKPEAG0@Z`
- size: `67`
- prototype: `unsigned int(CVaultTransacted *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180040830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040865`
- `api-ms-win-core-kernel32-legacy-l1-1-3!MoveFileTransactedW` at `0x180040857`
- `api-ms-win-core-kernel32-legacy-l1-1-3!MoveFileTransactedW` at `0x180040857`

## pseudocode

```c
DWORD __fastcall CVaultTransacted::FileOperationsMoveFile(HANDLE *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  if ( MoveFileTransactedW(a2, a3, 0, 0, 0, this[1]) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180040830  sub     rsp, 38h
0x180040834  mov     rax, [rcx+8]
0x180040838  mov     r10, r8
0x18004083b  mov     r11, rdx
0x18004083e  mov     [rsp+38h+hTransaction], rax; hTransaction
0x180040843  mov     rdx, r10; lpNewFileName
0x180040846  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18004084e  mov     rcx, r11; lpExistingFileName
0x180040851  xor     r9d, r9d; lpData
0x180040854  xor     r8d, r8d; lpProgressRoutine
0x180040857  call    cs:__imp_MoveFileTransactedW
0x18004085d  test    eax, eax
0x18004085f  jnz     short loc_18004086C
0x180040861  add     rsp, 38h
0x180040865  jmp     cs:__imp_GetLastError
0x18004086c  xor     eax, eax
0x18004086e  add     rsp, 38h
0x180040872  retn
```

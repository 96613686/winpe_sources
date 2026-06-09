# TextLogUpdateEof

- ea: `0x18000f7f0`
- end: `0x18000f825`
- name: `TextLogUpdateEof`
- size: `53`
- prototype: `DWORD __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x180016cac`

## callees

- `0x18000f7f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f816`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000f80b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000f80b`

## pseudocode

```c
DWORD __fastcall TextLogUpdateEof(__int64 a1, int a2)
{
  *(_QWORD *)(a1 + 24) += a2;
  if ( SetFilePointer(*(HANDLE *)a1, *(_QWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16), 0, 0) == -1 )
    return GetLastError();
  else
    return 0;
}

```

## disassembly

```asm
0x18000f7f0  sub     rsp, 28h
0x18000f7f4  movsxd  rax, edx
0x18000f7f7  xor     r9d, r9d; dwMoveMethod
0x18000f7fa  add     [rcx+18h], rax
0x18000f7fe  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000f801  mov     rdx, [rcx+18h]
0x18000f805  sub     edx, [rcx+10h]; lDistanceToMove
0x18000f808  mov     rcx, [rcx]; hFile
0x18000f80b  call    cs:__imp_SetFilePointer
0x18000f811  cmp     eax, 0FFFFFFFFh
0x18000f814  jnz     short loc_18000F81E
0x18000f816  call    cs:__imp_GetLastError
0x18000f81c  jmp     short loc_18000F820
0x18000f81e  xor     eax, eax
0x18000f820  add     rsp, 28h
0x18000f824  retn
```

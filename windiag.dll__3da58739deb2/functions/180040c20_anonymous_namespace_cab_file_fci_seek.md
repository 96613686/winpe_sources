# _anonymous_namespace_::cab_file::fci_seek

- ea: `0x180040c20`
- end: `0x180040c79`
- name: `_anonymous_namespace_::cab_file::fci_seek`
- size: `89`
- prototype: `int __cdecl(INT_PTR hf, int dist, int seektype, int *err, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180040c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040c3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c68`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180040c5d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180040c5d`

## pseudocode

```c
DWORD __fastcall anonymous_namespace_::cab_file::fci_seek(INT_PTR hf, LONG dist, int seektype, DWORD *err)
{
  int v5; // r8d
  DWORD v6; // r9d
  DWORD result; // eax

  if ( !seektype )
  {
    v6 = 0;
LABEL_8:
    result = SetFilePointer((HANDLE)hf, dist, 0, v6);
    if ( result != -1 )
      return result;
    goto LABEL_9;
  }
  v5 = seektype - 1;
  if ( !v5 )
  {
    v6 = 1;
    goto LABEL_8;
  }
  if ( v5 == 1 )
  {
    v6 = 2;
    goto LABEL_8;
  }
  SetLastError(0x57u);
LABEL_9:
  *err = GetLastError();
  return -1;
}

```

## disassembly

```asm
0x180040c20  push    rbx
0x180040c22  sub     rsp, 20h
0x180040c26  mov     rbx, r9
0x180040c29  test    r8d, r8d
0x180040c2c  jz      short loc_180040C57
0x180040c2e  sub     r8d, 1
0x180040c32  jz      short loc_180040C4F
0x180040c34  cmp     r8d, 1
0x180040c38  jz      short loc_180040C47
0x180040c3a  mov     ecx, 57h ; 'W'; dwErrCode
0x180040c3f  call    cs:__imp_SetLastError
0x180040c45  jmp     short loc_180040C68
0x180040c47  mov     r9d, 2
0x180040c4d  jmp     short loc_180040C5A
0x180040c4f  mov     r9d, 1
0x180040c55  jmp     short loc_180040C5A
0x180040c57  xor     r9d, r9d; dwMoveMethod
0x180040c5a  xor     r8d, r8d; lpDistanceToMoveHigh
0x180040c5d  call    cs:__imp_SetFilePointer
0x180040c63  cmp     eax, 0FFFFFFFFh
0x180040c66  jnz     short loc_180040C73
0x180040c68  call    cs:__imp_GetLastError
0x180040c6e  mov     [rbx], eax
0x180040c70  or      eax, 0FFFFFFFFh
0x180040c73  add     rsp, 20h
0x180040c77  pop     rbx
0x180040c78  retn
```

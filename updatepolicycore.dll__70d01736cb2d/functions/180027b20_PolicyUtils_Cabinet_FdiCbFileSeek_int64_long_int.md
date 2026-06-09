# PolicyUtils::Cabinet::FdiCbFileSeek(__int64,long,int)

- ea: `0x180027b20`
- end: `0x180027b55`
- name: `?FdiCbFileSeek@Cabinet@PolicyUtils@@YAJ_JJH@Z`
- size: `53`
- prototype: `DWORD __fastcall(INT_PTR hf, LONG dist, int seektype)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180027b41`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180027b41`

## pseudocode

```c
DWORD __fastcall PolicyUtils::Cabinet::FdiCbFileSeek(INT_PTR hf, LONG dist, int seektype)
{
  DWORD v3; // r9d
  DWORD result; // eax

  v3 = 0;
  if ( seektype == 2 )
    v3 = 2;
  if ( seektype == 1 )
    v3 = 1;
  result = SetFilePointer((HANDLE)hf, dist, 0, v3);
  if ( result == -1 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x180027b20  sub     rsp, 28h
0x180027b24  xor     r9d, r9d
0x180027b27  lea     eax, [r9+2]
0x180027b2b  cmp     r8d, eax
0x180027b2e  cmovz   r9d, eax
0x180027b32  mov     eax, 1
0x180027b37  cmp     r8d, eax
0x180027b3a  cmovz   r9d, eax; dwMoveMethod
0x180027b3e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180027b41  call    cs:__imp_SetFilePointer
0x180027b47  or      ecx, 0FFFFFFFFh
0x180027b4a  cmp     eax, 0FFFFFFFFh
0x180027b4d  cmovz   eax, ecx
0x180027b50  add     rsp, 28h
0x180027b54  retn
```

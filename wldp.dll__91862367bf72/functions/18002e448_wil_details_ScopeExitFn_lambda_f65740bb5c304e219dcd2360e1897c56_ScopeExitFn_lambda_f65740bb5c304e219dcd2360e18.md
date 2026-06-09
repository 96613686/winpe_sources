# wil::details::ScopeExitFn__lambda_f65740bb5c304e219dcd2360e1897c56___::_ScopeExitFn__lambda_f65740bb5c304e219dcd2360e1897c56___

- ea: `0x18002e448`
- end: `0x18002e475`
- name: `wil::details::ScopeExitFn__lambda_f65740bb5c304e219dcd2360e1897c56___::_ScopeExitFn__lambda_f65740bb5c304e219dcd2360e1897c56___`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180040696`
- `0x1800407d4`

## callees

- `0x18002e448`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002e469`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002e469`

## pseudocode

```c
BOOL __fastcall wil::details::ScopeExitFn__lambda_f65740bb5c304e219dcd2360e1897c56___::_ScopeExitFn__lambda_f65740bb5c304e219dcd2360e1897c56___(
        __int64 a1)
{
  BOOL result; // eax

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    return SetFilePointerEx(**(HANDLE **)a1, **(LARGE_INTEGER **)(a1 + 8), 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18002e448  sub     rsp, 28h
0x18002e44c  cmp     byte ptr [rcx+10h], 0
0x18002e450  jz      short loc_18002E470
0x18002e452  mov     byte ptr [rcx+10h], 0
0x18002e456  mov     rdx, [rcx+8]
0x18002e45a  mov     rcx, [rcx]
0x18002e45d  xor     r9d, r9d; dwMoveMethod
0x18002e460  xor     r8d, r8d; lpNewFilePointer
0x18002e463  mov     rdx, [rdx]; liDistanceToMove
0x18002e466  mov     rcx, [rcx]; hFile
0x18002e469  call    cs:__imp_SetFilePointerEx
0x18002e46f  nop
0x18002e470  add     rsp, 28h
0x18002e474  retn
```

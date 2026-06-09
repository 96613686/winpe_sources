# wil::details::ScopeExitFn__lambda_90e66dca0f80c570f86a999a69da7912___::_ScopeExitFn__lambda_90e66dca0f80c570f86a999a69da7912___

- ea: `0x18002e33c`
- end: `0x18002e389`
- name: `wil::details::ScopeExitFn__lambda_90e66dca0f80c570f86a999a69da7912___::_ScopeExitFn__lambda_90e66dca0f80c570f86a999a69da7912___`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180040612`
- `0x180040837`

## callees

- `0x18002e33c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002e362`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002e37c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002e362`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002e37c`

## pseudocode

```c
BOOL __fastcall wil::details::ScopeExitFn__lambda_90e66dca0f80c570f86a999a69da7912___::_ScopeExitFn__lambda_90e66dca0f80c570f86a999a69da7912___(
        __int64 a1)
{
  BOOL result; // eax

  if ( *(_BYTE *)(a1 + 32) )
  {
    *(_BYTE *)(a1 + 32) = 0;
    SetFilePointerEx(**(HANDLE **)a1, **(LARGE_INTEGER **)(a1 + 8), 0, 0);
    return SetFilePointerEx(**(HANDLE **)(a1 + 16), **(LARGE_INTEGER **)(a1 + 24), 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18002e33c  push    rbx
0x18002e33e  sub     rsp, 20h
0x18002e342  mov     rbx, rcx
0x18002e345  cmp     byte ptr [rcx+20h], 0
0x18002e349  jz      short loc_18002E383
0x18002e34b  mov     byte ptr [rcx+20h], 0
0x18002e34f  mov     rdx, [rcx+8]
0x18002e353  mov     rcx, [rcx]
0x18002e356  xor     r9d, r9d; dwMoveMethod
0x18002e359  xor     r8d, r8d; lpNewFilePointer
0x18002e35c  mov     rdx, [rdx]; liDistanceToMove
0x18002e35f  mov     rcx, [rcx]; hFile
0x18002e362  call    cs:__imp_SetFilePointerEx
0x18002e368  mov     rdx, [rbx+18h]
0x18002e36c  mov     rcx, [rbx+10h]
0x18002e370  xor     r9d, r9d; dwMoveMethod
0x18002e373  xor     r8d, r8d; lpNewFilePointer
0x18002e376  mov     rdx, [rdx]; liDistanceToMove
0x18002e379  mov     rcx, [rcx]; hFile
0x18002e37c  call    cs:__imp_SetFilePointerEx
0x18002e382  nop
0x18002e383  add     rsp, 20h
0x18002e387  pop     rbx
0x18002e388  retn
```

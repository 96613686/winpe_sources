# _SortedCatalogInfoCompareFileAttributes

- ea: `0x180001c78`
- end: `0x180001cd0`
- name: `_SortedCatalogInfoCompareFileAttributes`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001fb4`

## callees

- `0x180001c78`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001ca0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001cb2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001ca0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001cb2`

## pseudocode

```c
_BOOL8 __fastcall SortedCatalogInfoCompareFileAttributes(__int64 a1, __int64 a2)
{
  return *(_DWORD *)(a1 + 32) == *(_DWORD *)(a2 + 36)
      && *(_DWORD *)(a1 + 28) == *(_DWORD *)(a2 + 32)
      && !CompareFileTime((const FILETIME *)(a1 + 20), (const FILETIME *)(a2 + 20))
      && CompareFileTime((const FILETIME *)(a1 + 4), (const FILETIME *)(a2 + 4)) == 0;
}

```

## disassembly

```asm
0x180001c78  mov     [rsp+arg_0], rbx
0x180001c7d  push    rdi
0x180001c7e  sub     rsp, 20h
0x180001c82  mov     eax, [rdx+24h]
0x180001c85  mov     rbx, rdx
0x180001c88  mov     rdi, rcx
0x180001c8b  cmp     [rcx+20h], eax
0x180001c8e  jnz     short loc_180001CCC
0x180001c90  mov     eax, [rdx+20h]
0x180001c93  cmp     [rcx+1Ch], eax
0x180001c96  jnz     short loc_180001CCC
0x180001c98  add     rdx, 14h; lpFileTime2
0x180001c9c  add     rcx, 14h; lpFileTime1
0x180001ca0  call    cs:__imp_CompareFileTime
0x180001ca6  test    eax, eax
0x180001ca8  jnz     short loc_180001CCC
0x180001caa  lea     rdx, [rbx+4]; lpFileTime2
0x180001cae  lea     rcx, [rdi+4]; lpFileTime1
0x180001cb2  call    cs:__imp_CompareFileTime
0x180001cb8  xor     ecx, ecx
0x180001cba  test    eax, eax
0x180001cbc  setz    cl
0x180001cbf  mov     eax, ecx
0x180001cc1  mov     rbx, [rsp+28h+arg_0]
0x180001cc6  add     rsp, 20h
0x180001cca  pop     rdi
0x180001ccb  retn
0x180001ccc  xor     eax, eax
0x180001cce  jmp     short loc_180001CC1
```

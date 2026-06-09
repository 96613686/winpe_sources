# CipRemoveCatalogFromTable

- ea: `0x180044444`
- end: `0x18004448e`
- name: `CipRemoveCatalogFromTable`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180044008`
- `0x180044058`

## callees

- `0x180044444`

## import_xrefs

- `securekernel!RtlAvlRemoveNode` at `0x180044475`
- `securekernel!RtlAvlRemoveNode` at `0x180044475`

## pseudocode

```c
__int64 __fastcall CipRemoveCatalogFromTable(__int64 a1, __int64 a2)
{
  __int64 v2; // r9
  _QWORD *v3; // r8

  v2 = *(_QWORD *)(a1 + 184);
  if ( *(_QWORD *)(v2 + 8) != a1 + 184 || (v3 = *(_QWORD **)(a1 + 192), *v3 != a1 + 184) )
    __fastfail(3u);
  *v3 = v2;
  *(_QWORD *)(v2 + 8) = v3;
  return RtlAvlRemoveNode(a2, a1 + 208);
}

```

## disassembly

```asm
0x180044444  sub     rsp, 28h
0x180044448  lea     rax, [rcx+0B8h]
0x18004444f  mov     r10, rdx
0x180044452  mov     r9, [rax]
0x180044455  cmp     [r9+8], rax
0x180044459  jnz     short loc_180044487
0x18004445b  mov     r8, [rax+8]
0x18004445f  cmp     [r8], rax
0x180044462  jnz     short loc_180044487
0x180044464  lea     rdx, [rcx+0D0h]
0x18004446b  mov     [r8], r9
0x18004446e  mov     rcx, r10
0x180044471  mov     [r9+8], r8
0x180044475  call    cs:__imp_RtlAvlRemoveNode
0x18004447c  nop     dword ptr [rax+rax+00h]
0x180044481  add     rsp, 28h
0x180044485  retn
0x180044487  mov     ecx, 3
0x18004448c  int     29h; Win8: RtlFailFast(ecx)
```

# SkciDeleteCatalog

- ea: `0x180011540`
- end: `0x180011564`
- name: `SkciDeleteCatalog`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011540`
- `0x180044058`

## pseudocode

```c
__int64 __fastcall SkciDeleteCatalog(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = CiDeleteCatalogEntry(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180011540  push    rbx
0x180011542  sub     rsp, 20h
0x180011546  mov     rbx, rcx
0x180011549  mov     rcx, [rcx]
0x18001154c  test    rcx, rcx
0x18001154f  jz      short loc_18001155D
0x180011551  call    CiDeleteCatalogEntry
0x180011556  mov     qword ptr [rbx], 0
0x18001155d  add     rsp, 20h
0x180011561  pop     rbx
0x180011562  retn
```

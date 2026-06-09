# DecompressEnd

- ea: `0x1800022c8`
- end: `0x180002307`
- name: `DecompressEnd`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001cc0`
- `0x180002028`

## callees

- `0x1800022c8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800022ea`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800022ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800022e1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800022e1`

## pseudocode

```c
__int64 __fastcall DecompressEnd(__int64 a1)
{
  const void *v2; // rcx
  __int64 result; // rax
  HGLOBAL v4; // rax

  v2 = *(const void **)(a1 + 8);
  if ( !v2 )
    return 4294967196LL;
  v4 = GlobalHandle(v2);
  GlobalFree(v4);
  result = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x1800022c8  push    rbx
0x1800022ca  sub     rsp, 20h
0x1800022ce  mov     rbx, rcx
0x1800022d1  mov     rcx, [rcx+8]; pMem
0x1800022d5  test    rcx, rcx
0x1800022d8  jnz     short loc_1800022E1
0x1800022da  mov     eax, 0FFFFFF9Ch
0x1800022df  jmp     short loc_180002301
0x1800022e1  call    cs:__imp_GlobalHandle
0x1800022e7  mov     rcx, rax; hMem
0x1800022ea  call    cs:__imp_GlobalFree
0x1800022f0  xor     eax, eax
0x1800022f2  mov     qword ptr [rbx+8], 0
0x1800022fa  mov     dword ptr [rbx+4], 0
0x180002301  add     rsp, 20h
0x180002305  pop     rbx
0x180002306  retn
```

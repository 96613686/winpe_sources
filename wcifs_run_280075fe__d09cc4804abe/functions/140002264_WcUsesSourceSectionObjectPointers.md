# WcUsesSourceSectionObjectPointers

- ea: `0x140002264`
- end: `0x14000228d`
- name: `WcUsesSourceSectionObjectPointers`
- size: `41`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140006340`
- `0x1400198a0`
- `0x140024040`
- `0x140024bf0`
- `0x140024e60`
- `0x140024f60`
- `0x140028e00`
- `0x14002f9f8`
- `0x140034bb0`

## callees

- `0x140002264`

## pseudocode

```c
bool __fastcall WcUsesSourceSectionObjectPointers(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  bool result; // al

  result = a2
        && (v2 = a2 + 56, v3 = *(_QWORD *)(a2 + 56), v3 != v2)
        && *(_QWORD *)(a1 + 40) == *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 24) + 16LL) + 40LL);
  return result;
}

```

## disassembly

```asm
0x140002264  test    rdx, rdx
0x140002267  jz      short loc_14000228A
0x140002269  lea     rax, [rdx+38h]
0x14000226d  mov     rdx, [rax]
0x140002270  cmp     rdx, rax
0x140002273  jz      short loc_14000228A
0x140002275  mov     rax, [rdx+18h]
0x140002279  mov     rdx, [rax+10h]
0x14000227d  mov     rax, [rdx+28h]
0x140002281  cmp     [rcx+28h], rax
0x140002285  setz    al
0x140002288  retn
0x14000228a  xor     al, al
0x14000228c  retn
```

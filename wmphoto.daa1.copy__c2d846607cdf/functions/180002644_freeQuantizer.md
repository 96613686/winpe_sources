# freeQuantizer

- ea: `0x180002644`
- end: `0x180002668`
- name: `freeQuantizer`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024bc`
- `0x180031110`
- `0x180032914`
- `0x180042088`
- `0x180042294`

## callees

- `0x180002644`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002655`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002655`

## pseudocode

```c
void __fastcall freeQuantizer(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    free(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180002644  push    rbx
0x180002646  sub     rsp, 20h
0x18000264a  mov     rbx, rcx
0x18000264d  mov     rcx, [rcx]; Block
0x180002650  test    rcx, rcx
0x180002653  jz      short loc_180002662
0x180002655  call    cs:__imp_free
0x18000265b  mov     qword ptr [rbx], 0
0x180002662  add     rsp, 20h
0x180002666  pop     rbx
0x180002667  retn
```

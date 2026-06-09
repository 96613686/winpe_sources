# freeQuantizer

- ea: `0x1800026ac`
- end: `0x1800026d7`
- name: `freeQuantizer`
- size: `43`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002510`
- `0x18003146c`
- `0x180032eb4`
- `0x180042878`
- `0x180042a84`

## callees

- `0x1800026ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800026bd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800026bd`

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
0x1800026ac  push    rbx
0x1800026ae  sub     rsp, 20h
0x1800026b2  mov     rbx, rcx
0x1800026b5  mov     rcx, [rcx]; Block
0x1800026b8  test    rcx, rcx
0x1800026bb  jz      short loc_1800026D0
0x1800026bd  call    cs:__imp_free
0x1800026c4  nop     dword ptr [rax+rax+00h]
0x1800026c9  mov     qword ptr [rbx], 0
0x1800026d0  add     rsp, 20h
0x1800026d4  pop     rbx
0x1800026d5  retn
```

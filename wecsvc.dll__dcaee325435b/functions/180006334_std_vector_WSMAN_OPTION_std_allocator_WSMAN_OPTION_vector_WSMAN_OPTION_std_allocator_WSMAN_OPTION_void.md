# std::vector<_WSMAN_OPTION,std::allocator<_WSMAN_OPTION>>::~vector<_WSMAN_OPTION,std::allocator<_WSMAN_OPTION>>(void)

- ea: `0x180006334`
- end: `0x180006367`
- name: `??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(__int64)`
- caller_count: `27`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003b44`
- `0x180003cc8`
- `0x1800060b0`
- `0x180008828`
- `0x180009170`
- `0x18000b724`
- `0x18000bbec`
- `0x18000c724`
- `0x18000e01c`
- `0x18000e134`
- `0x18000f110`
- `0x180011d6c`
- `0x18001259c`
- `0x1800128c0`
- `0x18001483c`
- `0x180015c30`
- `0x1800165c0`
- `0x18001c750`
- `0x18001d2c4`
- `0x18001f4f8`
- `0x180020b71`
- `0x18002137d`
- `0x1800215bc`
- `0x18002214e`
- `0x18002223c`
- `0x180022272`
- `0x1800227a5`

## callees

- `0x1800034f0`
- `0x180006334`

## pseudocode

```c
void __fastcall std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180006334  push    rbx
0x180006336  sub     rsp, 20h
0x18000633a  mov     rbx, rcx
0x18000633d  mov     rcx, [rcx]; void *
0x180006340  test    rcx, rcx
0x180006343  jz      short loc_180006361
0x180006345  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000634a  mov     qword ptr [rbx], 0
0x180006351  mov     qword ptr [rbx+8], 0
0x180006359  mov     qword ptr [rbx+10h], 0
0x180006361  add     rsp, 20h
0x180006365  pop     rbx
0x180006366  retn
```

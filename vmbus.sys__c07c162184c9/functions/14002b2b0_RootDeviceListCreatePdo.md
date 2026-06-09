# RootDeviceListCreatePdo

- ea: `0x14002b2b0`
- end: `0x14002b2e7`
- name: `RootDeviceListCreatePdo`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14002846c`
- `0x140029f68`
- `0x14002b2b0`

## pseudocode

```c
__int64 __fastcall RootDeviceListCreatePdo(__int64 a1, __int64 a2, __int64 a3)
{
  if ( *(_BYTE *)(a2 + 192) )
    return PowerDeviceInstanceCreatePdo(a3, *(_QWORD *)(a2 + 200));
  else
    return InstanceCreatePdo(a3, *(_QWORD *)(a2 + 184), (unsigned int *)(a2 + 8));
}

```

## disassembly

```asm
0x14002b2b0  sub     rsp, 28h
0x14002b2b4  cmp     byte ptr [rdx+0C0h], 0
0x14002b2bb  mov     rax, r8
0x14002b2be  mov     rcx, rax
0x14002b2c1  jz      short loc_14002B2D1
0x14002b2c3  mov     rdx, [rdx+0C8h]
0x14002b2ca  call    PowerDeviceInstanceCreatePdo
0x14002b2cf  jmp     short loc_14002B2E1
0x14002b2d1  lea     r8, [rdx+8]
0x14002b2d5  mov     rdx, [rdx+0B8h]
0x14002b2dc  call    InstanceCreatePdo
0x14002b2e1  add     rsp, 28h
0x14002b2e5  retn
```

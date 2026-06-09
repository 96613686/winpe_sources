# RootDeviceListCreatePdo

- ea: `0x14002b260`
- end: `0x14002b297`
- name: `RootDeviceListCreatePdo`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14002841c`
- `0x140029f18`
- `0x14002b260`

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
0x14002b260  sub     rsp, 28h
0x14002b264  cmp     byte ptr [rdx+0C0h], 0
0x14002b26b  mov     rax, r8
0x14002b26e  mov     rcx, rax
0x14002b271  jz      short loc_14002B281
0x14002b273  mov     rdx, [rdx+0C8h]
0x14002b27a  call    PowerDeviceInstanceCreatePdo
0x14002b27f  jmp     short loc_14002B291
0x14002b281  lea     r8, [rdx+8]
0x14002b285  mov     rdx, [rdx+0B8h]
0x14002b28c  call    InstanceCreatePdo
0x14002b291  add     rsp, 28h
0x14002b295  retn
```

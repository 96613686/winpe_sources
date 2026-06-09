# MTX_LZCOMP_Destroy

- ea: `0x18000e5e4`
- end: `0x18000e63a`
- name: `MTX_LZCOMP_Destroy`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000de70`
- `0x18000e12c`

## callees

- `0x180009c80`
- `0x18000e734`

## pseudocode

```c
__int64 __fastcall MTX_LZCOMP_Destroy(_QWORD *a1)
{
  DiscardPointer(a1[18], *a1, 1);
  FreeAllHashNodes(a1);
  DiscardPointer(a1[18], a1[14], 1);
  return DiscardPointer(a1[18], a1, 1);
}

```

## disassembly

```asm
0x18000e5e4  push    rbx
0x18000e5e6  sub     rsp, 20h
0x18000e5ea  mov     rdx, [rcx]
0x18000e5ed  mov     rbx, rcx
0x18000e5f0  mov     rcx, [rcx+90h]
0x18000e5f7  mov     r8d, 1
0x18000e5fd  call    DiscardPointer
0x18000e602  mov     rcx, rbx
0x18000e605  call    FreeAllHashNodes
0x18000e60a  mov     rdx, [rbx+70h]
0x18000e60e  mov     r8d, 1
0x18000e614  mov     rcx, [rbx+90h]
0x18000e61b  call    DiscardPointer
0x18000e620  mov     rcx, [rbx+90h]
0x18000e627  mov     r8d, 1
0x18000e62d  mov     rdx, rbx
0x18000e630  add     rsp, 20h
0x18000e634  pop     rbx
0x18000e635  jmp     DiscardPointer
```

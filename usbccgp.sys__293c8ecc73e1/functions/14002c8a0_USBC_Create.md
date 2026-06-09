# USBC_Create

- ea: `0x14002c8a0`
- end: `0x14002c8dc`
- name: `USBC_Create`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002200`

## callees

- `0x1400029d0`
- `0x140003388`
- `0x14002c8a0`

## pseudocode

```c
__int64 __fastcall USBC_Create(__int64 a1, IRP *a2)
{
  unsigned int v2; // ebx

  if ( *(_BYTE *)(a1 + 4) )
  {
    return (unsigned int)UsbcForwardIrp(a1 + 8, *(struct _DEVICE_OBJECT **)(a1 + 48), a2);
  }
  else
  {
    v2 = -1073741637;
    UsbcCompleteIrp(*(_QWORD *)(a1 + 240), -1073741637, a2);
  }
  return v2;
}

```

## disassembly

```asm
0x14002c8a0  push    rbx
0x14002c8a2  sub     rsp, 20h
0x14002c8a6  cmp     byte ptr [rcx+4], 0
0x14002c8aa  mov     r8, rdx
0x14002c8ad  jz      short loc_14002C8C7
0x14002c8af  mov     rdx, [rcx+30h]
0x14002c8b3  add     rcx, 8
0x14002c8b7  call    UsbcForwardIrp
0x14002c8bc  mov     ebx, eax
0x14002c8be  mov     eax, ebx
0x14002c8c0  add     rsp, 20h
0x14002c8c4  pop     rbx
0x14002c8c5  retn
0x14002c8c7  mov     rcx, [rcx+0F0h]
0x14002c8ce  mov     ebx, 0C00000BBh
0x14002c8d3  mov     edx, ebx
0x14002c8d5  call    UsbcCompleteIrp
0x14002c8da  jmp     short loc_14002C8BE
```

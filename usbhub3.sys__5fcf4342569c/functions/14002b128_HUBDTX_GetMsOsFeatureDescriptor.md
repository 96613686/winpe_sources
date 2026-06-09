# HUBDTX_GetMsOsFeatureDescriptor

- ea: `0x14002b128`
- end: `0x14002b1b2`
- name: `HUBDTX_GetMsOsFeatureDescriptor`
- size: `138`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140021e00`
- `0x140022320`
- `0x1400223c0`
- `0x140022500`
- `0x140022600`
- `0x1400226c0`
- `0x140022760`

## callees

- `0x14002e270`

## pseudocode

```c
__int64 __fastcall HUBDTX_GetMsOsFeatureDescriptor(__int64 a1, char a2, __int64 a3, __int16 a4, __int64 a5, __int64 a6)
{
  *(_BYTE *)(a1 + 408) = a2 & 3 | 0xC0;
  *(_BYTE *)(a1 + 409) = *(_BYTE *)(a1 + 2060);
  *(_WORD *)(a1 + 410) = 0;
  *(_WORD *)(a1 + 412) = a4;
  *(_WORD *)(a1 + 414) = a6;
  return HUBMISC_ControlTransfer(
           *(_QWORD *)a1,
           *(_QWORD *)(a1 + 24),
           a1,
           (_QWORD *)(a1 + 256),
           (__int64)HUBDTX_ControlTransferComplete,
           a5,
           a6,
           1,
           *(_BYTE *)(a1 + 1520));
}

```

## disassembly

```asm
0x14002b128  sub     rsp, 58h
0x14002b12c  mov     r10, rcx
0x14002b12f  and     dl, 3
0x14002b132  or      dl, 0C0h
0x14002b135  mov     [rcx+198h], dl
0x14002b13b  mov     al, [rcx+80Ch]
0x14002b141  mov     [rcx+199h], al
0x14002b147  mov     word ptr [rcx+19Ah], 0
0x14002b150  mov     [rcx+19Ch], r9w
0x14002b158  mov     rcx, [rsp+58h+arg_28]
0x14002b160  mov     [r10+19Eh], cx
0x14002b168  mov     al, [r10+5F0h]
0x14002b16f  lea     r9, [r10+100h]
0x14002b176  mov     rdx, [r10+18h]
0x14002b17a  mov     r8, r10
0x14002b17d  mov     [rsp+58h+var_18], al
0x14002b181  mov     rax, [rsp+58h+arg_20]
0x14002b189  mov     [rsp+58h+var_20], 1
0x14002b18e  mov     [rsp+58h+var_28], rcx
0x14002b193  mov     rcx, [r10]
0x14002b196  mov     [rsp+58h+var_30], rax
0x14002b19b  lea     rax, HUBDTX_ControlTransferComplete
0x14002b1a2  mov     [rsp+58h+var_38], rax
0x14002b1a7  call    HUBMISC_ControlTransfer
0x14002b1ac  add     rsp, 58h
0x14002b1b0  retn
```

# HUBDTX_GetDescriptor

- ea: `0x14002ad20`
- end: `0x14002ada7`
- name: `HUBDTX_GetDescriptor`
- size: `135`
- prototype: `__int64 __fastcall(__int64, __int64, int, char, char, __int16)`
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140022030`
- `0x1400220f0`
- `0x1400221c0`
- `0x140022260`
- `0x140022460`
- `0x140023a60`
- `0x14002a978`
- `0x14002aa78`
- `0x14002ab6c`
- `0x14002ac2c`
- `0x14002b018`
- `0x14002b0a0`
- `0x14002b1b8`
- `0x14002b298`

## callees

- `0x14002e270`

## pseudocode

```c
__int64 __fastcall HUBDTX_GetDescriptor(__int64 a1, __int64 a2, int a3, char a4, char a5, __int16 a6)
{
  char v6; // al

  v6 = *(_BYTE *)(a1 + 408) & 0x1C;
  *(_BYTE *)(a1 + 409) = 6;
  *(_BYTE *)(a1 + 411) = a4;
  *(_BYTE *)(a1 + 408) = v6 | 0x80;
  *(_BYTE *)(a1 + 410) = a5;
  *(_WORD *)(a1 + 412) = a6;
  *(_WORD *)(a1 + 414) = a3;
  return HUBMISC_ControlTransfer(
           *(_QWORD *)a1,
           *(_QWORD *)(a1 + 24),
           a1,
           (_QWORD *)(a1 + 256),
           (__int64)HUBDTX_ControlTransferComplete,
           a2,
           a3,
           1,
           *(_BYTE *)(a1 + 1520));
}

```

## disassembly

```asm
0x14002ad20  sub     rsp, 58h
0x14002ad24  mov     al, [rcx+198h]
0x14002ad2a  and     al, 1Ch
0x14002ad2c  mov     byte ptr [rcx+199h], 6
0x14002ad33  or      al, 80h
0x14002ad35  mov     [rcx+19Bh], r9b
0x14002ad3c  mov     [rcx+198h], al
0x14002ad42  mov     al, [rsp+58h+arg_20]
0x14002ad49  mov     [rcx+19Ah], al
0x14002ad4f  movzx   eax, [rsp+58h+arg_28]
0x14002ad57  mov     [rcx+19Ch], ax
0x14002ad5e  mov     [rcx+19Eh], r8w
0x14002ad66  mov     al, [rcx+5F0h]
0x14002ad6c  lea     r9, [rcx+100h]
0x14002ad73  mov     [rsp+58h+var_18], al
0x14002ad77  lea     rax, HUBDTX_ControlTransferComplete
0x14002ad7e  mov     [rsp+58h+var_20], 1
0x14002ad83  mov     [rsp+58h+var_28], r8
0x14002ad88  mov     r8, rcx
0x14002ad8b  mov     [rsp+58h+var_30], rdx
0x14002ad90  mov     rdx, [rcx+18h]
0x14002ad94  mov     rcx, [rcx]
0x14002ad97  mov     [rsp+58h+var_38], rax
0x14002ad9c  call    HUBMISC_ControlTransfer
0x14002ada1  add     rsp, 58h
0x14002ada5  retn
```

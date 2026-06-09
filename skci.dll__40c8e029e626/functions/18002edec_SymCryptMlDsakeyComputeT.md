# SymCryptMlDsakeyComputeT

- ea: `0x18002edec`
- end: `0x18002ee6e`
- name: `SymCryptMlDsakeyComputeT`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002697c`
- `0x18002e158`

## callees

- `0x18002d3d0`
- `0x18002dac0`
- `0x18002e874`
- `0x18002ea38`
- `0x18002ec88`
- `0x18002edec`

## pseudocode

```c
__int64 __fastcall SymCryptMlDsakeyComputeT(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int8 *a6,
        __int64 a7)
{
  unsigned __int8 v9; // r10
  _BYTE *v10; // r11
  char v11; // r10

  SymCryptMlDsaMatrixVectorMontMul(a1, a2, a6, a7);
  v9 = 0;
  if ( *a6 )
  {
    v10 = a6 + 8;
    do
    {
      SymCryptMlDsaPolyElementMulR(&v10[1024 * (unsigned __int64)v9]);
      v9 = v11 + 1;
    }
    while ( v9 < *a6 );
  }
  SymCryptMlDsaVectorAdd(a6, a3, a6);
  SymCryptMlDsaVectorINTT(a6);
  return SymCryptMlDsaVectorPower2Round(a6, a5, a4);
}

```

## disassembly

```asm
0x18002edec  mov     [rsp+arg_0], rbx
0x18002edf1  mov     [rsp+arg_8], rsi
0x18002edf6  push    rdi
0x18002edf7  sub     rsp, 20h
0x18002edfb  mov     rbx, [rsp+28h+arg_28]
0x18002ee00  mov     rdi, r9
0x18002ee03  mov     r9, [rsp+28h+arg_30]
0x18002ee08  mov     rsi, r8
0x18002ee0b  mov     r8, rbx
0x18002ee0e  call    SymCryptMlDsaMatrixVectorMontMul
0x18002ee13  xor     r10b, r10b
0x18002ee16  cmp     [rbx], r10b
0x18002ee19  jbe     short loc_18002EE37
0x18002ee1b  lea     r11, [rbx+8]
0x18002ee1f  movzx   ecx, r10b
0x18002ee23  shl     rcx, 0Ah
0x18002ee27  add     rcx, r11
0x18002ee2a  call    SymCryptMlDsaPolyElementMulR
0x18002ee2f  inc     r10b
0x18002ee32  cmp     r10b, [rbx]
0x18002ee35  jb      short loc_18002EE1F
0x18002ee37  mov     r8, rbx
0x18002ee3a  mov     rdx, rsi
0x18002ee3d  mov     rcx, rbx
0x18002ee40  call    SymCryptMlDsaVectorAdd
0x18002ee45  mov     rcx, rbx
0x18002ee48  call    SymCryptMlDsaVectorINTT
0x18002ee4d  mov     rdx, [rsp+28h+arg_20]
0x18002ee52  mov     r8, rdi
0x18002ee55  mov     rcx, rbx
0x18002ee58  call    SymCryptMlDsaVectorPower2Round
0x18002ee5d  mov     rbx, [rsp+28h+arg_0]
0x18002ee62  mov     rsi, [rsp+28h+arg_8]
0x18002ee67  add     rsp, 20h
0x18002ee6b  pop     rdi
0x18002ee6c  retn
```

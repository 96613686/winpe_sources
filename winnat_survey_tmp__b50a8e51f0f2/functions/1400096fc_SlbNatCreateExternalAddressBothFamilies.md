# SlbNatCreateExternalAddressBothFamilies

- ea: `0x1400096fc`
- end: `0x140009754`
- name: `SlbNatCreateExternalAddressBothFamilies`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140033cc8`

## callees

- `0x1400096fc`
- `0x14000975c`

## pseudocode

```c
__int64 __fastcall SlbNatCreateExternalAddressBothFamilies(__int64 a1, __int16 a2, __int64 a3)
{
  __int64 result; // rax

  result = SlbNatCreateExternalAddressForFamily(a1, a2, a3, 1, 0);
  if ( (int)result >= 0 )
    return SlbNatCreateExternalAddressForFamily(a1, a2, a3, 0, 0);
  return result;
}

```

## disassembly

```asm
0x1400096fc  mov     [rsp+arg_0], rbx
0x140009701  mov     [rsp+arg_8], rsi
0x140009706  push    rdi
0x140009707  sub     rsp, 30h
0x14000970b  mov     r9b, 1
0x14000970e  mov     [rsp+38h+var_18], 0
0x140009717  mov     rbx, r8
0x14000971a  movzx   edi, dx
0x14000971d  mov     rsi, rcx
0x140009720  call    SlbNatCreateExternalAddressForFamily
0x140009725  test    eax, eax
0x140009727  js      short loc_140009743
0x140009729  xor     r9d, r9d
0x14000972c  mov     [rsp+38h+var_18], 0
0x140009735  mov     r8, rbx
0x140009738  movzx   edx, di
0x14000973b  mov     rcx, rsi
0x14000973e  call    SlbNatCreateExternalAddressForFamily
0x140009743  mov     rbx, [rsp+38h+arg_0]
0x140009748  mov     rsi, [rsp+38h+arg_8]
0x14000974d  add     rsp, 30h
0x140009751  pop     rdi
0x140009752  retn
```

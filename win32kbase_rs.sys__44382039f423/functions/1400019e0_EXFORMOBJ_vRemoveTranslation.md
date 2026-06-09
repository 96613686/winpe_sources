# EXFORMOBJ_vRemoveTranslation

- ea: `0x1400019e0`
- end: `0x140001a09`
- name: `EXFORMOBJ_vRemoveTranslation`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400019e0`
- `0x140018450`

## pseudocode

```c
__int64 __fastcall EXFORMOBJ_vRemoveTranslation(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( !*a1 )
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001B000);
  *(_OWORD *)(result + 16) = 0;
  *(_BYTE *)(result + 32) |= 0x40u;
  return result;
}

```

## disassembly

```asm
0x1400019e0  sub     rsp, 28h
0x1400019e4  mov     rax, [rcx]
0x1400019e7  test    rax, rax
0x1400019ea  jz      short loc_1400019FC
0x1400019ec  xorps   xmm0, xmm0
0x1400019ef  movups  xmmword ptr [rax+10h], xmm0
0x1400019f3  or      byte ptr [rax+20h], 40h
0x1400019f7  add     rsp, 28h
0x1400019fb  retn
0x1400019fc  lea     rcx, off_14001B000; "gdi_rust\\src\\xform\\mod.rs"
0x140001a03  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
```

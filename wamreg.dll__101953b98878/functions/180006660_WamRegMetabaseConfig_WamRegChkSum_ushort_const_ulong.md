# WamRegMetabaseConfig::WamRegChkSum(ushort const *,ulong)

- ea: `0x180006660`
- end: `0x18000669c`
- name: `?WamRegChkSum@WamRegMetabaseConfig@@AEAAKPEBGK@Z`
- size: `60`
- prototype: `unsigned int __fastcall(WamRegMetabaseConfig *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005584`

## callees

- `0x180006660`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::WamRegChkSum(WamRegMetabaseConfig *this, unsigned __int16 *a2)
{
  unsigned int i; // ecx
  int v3; // r8d
  unsigned int v4; // eax
  int v5; // ecx
  unsigned __int16 v6; // ax

  for ( i = 0; ; i = ~v4 & v5 )
  {
    v6 = *a2;
    if ( !*a2 )
      break;
    ++a2;
    v3 = 16 * i + v6;
    v4 = v3 & 0xF0000000;
    if ( (v3 & 0xF0000000) != 0 )
      v5 = v3 ^ HIBYTE(v4);
    else
      v5 = v3;
  }
  return i;
}

```

## disassembly

```asm
0x180006660  xor     r9d, r9d
0x180006663  mov     ecx, r9d
0x180006666  jmp     short loc_180006691
0x180006668  movzx   r8d, ax
0x18000666c  lea     rdx, [rdx+2]
0x180006670  shl     ecx, 4
0x180006673  add     r8d, ecx
0x180006676  mov     eax, r8d
0x180006679  and     eax, 0F0000000h
0x18000667e  jz      short loc_18000668A
0x180006680  mov     ecx, eax
0x180006682  shr     ecx, 18h
0x180006685  xor     ecx, r8d
0x180006688  jmp     short loc_18000668D
0x18000668a  mov     ecx, r8d
0x18000668d  not     eax
0x18000668f  and     ecx, eax
0x180006691  movzx   eax, word ptr [rdx]
0x180006694  test    ax, ax
0x180006697  jnz     short loc_180006668
0x180006699  mov     eax, ecx
0x18000669b  retn
```

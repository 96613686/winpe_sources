# CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)

- ea: `0x18000c170`
- end: `0x18000c19b`
- name: `?_CalcKeyHash@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CAK_K@Z`
- size: `43`
- prototype: `__int64 __fastcall(__int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c170`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,unsigned short const *,CLKRHashTable>::_CalcKeyHash(
        __int16 *a1)
{
  __int16 v1; // ax
  unsigned int v2; // edx
  __int16 *v3; // r8

  v1 = *a1;
  v2 = 0;
  v3 = a1;
  while ( v1 )
  {
    ++v3;
    v2 = (v1 & 0xFFDF) + 101 * v2;
    v1 = *v3;
  }
  return v2;
}

```

## disassembly

```asm
0x18000c170  movzx   eax, word ptr [rcx]
0x18000c173  xor     r9d, r9d
0x18000c176  mov     edx, r9d
0x18000c179  mov     r8, rcx
0x18000c17c  jmp     short loc_18000C193
0x18000c17e  movzx   eax, ax
0x18000c181  lea     r8, [r8+2]
0x18000c185  and     eax, 0FFDFh
0x18000c18a  imul    edx, 65h ; 'e'
0x18000c18d  add     edx, eax
0x18000c18f  movzx   eax, word ptr [r8]
0x18000c193  test    ax, ax
0x18000c196  jnz     short loc_18000C17E
0x18000c198  mov     eax, edx
0x18000c19a  retn
```

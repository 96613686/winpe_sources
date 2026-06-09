# CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)

- ea: `0x18000d060`
- end: `0x18000d08b`
- name: `?_CalcKeyHash@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CAK_K@Z`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d060`

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
0x18000d060  movzx   eax, word ptr [rcx]
0x18000d063  xor     r9d, r9d
0x18000d066  mov     edx, r9d
0x18000d069  mov     r8, rcx
0x18000d06c  jmp     short loc_18000D083
0x18000d06e  movzx   eax, ax
0x18000d071  lea     r8, [r8+2]
0x18000d075  and     eax, 0FFDFh
0x18000d07a  imul    edx, 65h ; 'e'
0x18000d07d  add     edx, eax
0x18000d07f  movzx   eax, word ptr [r8]
0x18000d083  test    ax, ax
0x18000d086  jnz     short loc_18000D06E
0x18000d088  mov     eax, edx
0x18000d08a  retn
```

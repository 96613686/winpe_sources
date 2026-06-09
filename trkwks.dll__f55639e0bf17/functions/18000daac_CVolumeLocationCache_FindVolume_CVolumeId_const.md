# CVolumeLocationCache::_FindVolume(CVolumeId const &)

- ea: `0x18000daac`
- end: `0x18000dae1`
- name: `?_FindVolume@CVolumeLocationCache@@AEAAHAEBUCVolumeId@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(CVolumeLocationCache *__hidden this, const struct CVolumeId *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800035e4`
- `0x18000c55c`

## callees

- `0x18000daac`

## pseudocode

```c
__int64 __fastcall CVolumeLocationCache::_FindVolume(CVolumeLocationCache *this, const struct CVolumeId *a2)
{
  unsigned int i; // r8d
  __int64 v3; // rax

  for ( i = 0; (signed int)i < *((_DWORD *)this + 12); ++i )
  {
    v3 = *((_QWORD *)this + 5 * (int)i + 7) - *(_QWORD *)a2;
    if ( !v3 )
      v3 = *((_QWORD *)this + 5 * (int)i + 8) - *((_QWORD *)a2 + 1);
    if ( !v3 )
      return i;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000daac  xor     r8d, r8d
0x18000daaf  cmp     r8d, [rcx+30h]
0x18000dab3  jge     short loc_18000DADD
0x18000dab5  movsxd  rax, r8d
0x18000dab8  lea     r9, [rax+rax*4]
0x18000dabc  mov     rax, [rcx+r9*8+38h]
0x18000dac1  sub     rax, [rdx]
0x18000dac4  jnz     short loc_18000DACF
0x18000dac6  mov     rax, [rcx+r9*8+40h]
0x18000dacb  sub     rax, [rdx+8]
0x18000dacf  test    rax, rax
0x18000dad2  jz      short loc_18000DAD9
0x18000dad4  inc     r8d
0x18000dad7  jmp     short loc_18000DAAF
0x18000dad9  mov     eax, r8d
0x18000dadc  retn
0x18000dadd  or      eax, 0FFFFFFFFh
0x18000dae0  retn
```

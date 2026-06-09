# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x14001751c`
- end: `0x140017568`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400176c0`

## callees

- `0x14001751c`

## pseudocode

```c
void __fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(unsigned __int8 a1, int a2, __int64 a3)
{
  int v4; // edx
  unsigned int v5; // r9d
  volatile signed __int32 *v6; // r8
  signed __int32 v7; // eax
  signed __int32 v8; // ett

  v4 = a2 - 3;
  if ( v4 )
  {
    if ( v4 != 1 )
      return;
    v5 = 32;
  }
  else
  {
    v5 = 16;
  }
  v6 = *(volatile signed __int32 **)a3;
  if ( *(_BYTE *)(a3 + 30) || *(_BYTE *)(a3 + 29) )
  {
    _InterlockedOr(v6, v5);
  }
  else
  {
    v7 = *v6;
    do
    {
      if ( (v7 & 2) == 0 )
        break;
      if ( ((a1 ^ (unsigned __int8)v7) & 1) != 0 )
        break;
      v8 = v7;
      v7 = _InterlockedCompareExchange(v6, v7 | v5, v7);
    }
    while ( v8 != v7 );
  }
}

```

## disassembly

```asm
0x14001751c  mov     r10, r8
0x14001751f  sub     edx, 3
0x140017522  jz      short loc_14001752F
0x140017524  cmp     edx, 1
0x140017527  jnz     short locret_140017567
0x140017529  lea     r9d, [rdx+1Fh]
0x14001752d  jmp     short loc_140017535
0x14001752f  mov     r9d, 10h
0x140017535  cmp     byte ptr [r10+1Eh], 0
0x14001753a  mov     r8, [r8]
0x14001753d  jnz     short loc_140017563
0x14001753f  cmp     byte ptr [r10+1Dh], 0
0x140017544  jnz     short loc_140017563
0x140017546  mov     eax, [r8]
0x140017549  test    al, 2
0x14001754b  jz      short locret_140017567
0x14001754d  mov     edx, eax
0x14001754f  xor     edx, ecx
0x140017551  test    dl, 1
0x140017554  jnz     short locret_140017567
0x140017556  mov     edx, r9d
0x140017559  or      edx, eax
0x14001755b  lock cmpxchg [r8], edx
0x140017560  jnz     short loc_140017549
0x140017562  retn
0x140017563  lock or [r8], r9d
0x140017567  retn
```

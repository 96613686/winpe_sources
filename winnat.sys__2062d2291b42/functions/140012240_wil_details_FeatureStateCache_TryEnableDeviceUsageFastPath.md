# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140012240`
- end: `0x14001228f`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400123b0`

## callees

- `0x140012240`

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
0x140012240  mov     r10, r8
0x140012243  sub     edx, 3
0x140012246  jz      short loc_140012253
0x140012248  cmp     edx, 1
0x14001224b  jnz     short locret_14001228E
0x14001224d  lea     r9d, [rdx+1Fh]
0x140012251  jmp     short loc_140012259
0x140012253  mov     r9d, 10h
0x140012259  cmp     byte ptr [r10+1Eh], 0
0x14001225e  mov     r8, [r8]
0x140012261  jnz     short loc_14001228A
0x140012263  cmp     byte ptr [r10+1Dh], 0
0x140012268  jnz     short loc_14001228A
0x14001226a  mov     eax, [r8]
0x14001226d  jmp     short loc_140012284
0x14001226f  mov     edx, eax
0x140012271  xor     edx, ecx
0x140012273  test    dl, 1
0x140012276  jnz     short locret_14001228E
0x140012278  mov     edx, r9d
0x14001227b  or      edx, eax
0x14001227d  lock cmpxchg [r8], edx
0x140012282  jz      short locret_14001228E
0x140012284  test    al, 2
0x140012286  jnz     short loc_14001226F
0x140012288  retn
0x14001228a  lock or [r8], r9d
0x14001228e  retn
```

# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180009258`
- end: `0x180009292`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800093f0`

## callees

- `0x180009258`

## pseudocode

```c
void __fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(unsigned __int8 a1, int a2)
{
  int v2; // edx
  int v3; // r8d
  signed __int32 v4; // eax
  signed __int32 v5; // ett

  v2 = a2 - 3;
  if ( v2 )
  {
    if ( v2 != 1 )
      return;
    v3 = 32;
  }
  else
  {
    v3 = 16;
  }
  v4 = *Feature_RailV2ServerBuildSupported__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_RailV2ServerBuildSupported__private_descriptor[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x180009258  sub     edx, 3
0x18000925b  jz      short loc_180009268
0x18000925d  cmp     edx, 1
0x180009260  jnz     short locret_180009291
0x180009262  lea     r8d, [rdx+1Fh]
0x180009266  jmp     short loc_18000926E
0x180009268  mov     r8d, 10h
0x18000926e  mov     r9, cs:Feature_RailV2ServerBuildSupported__private_descriptor
0x180009275  mov     eax, [r9]
0x180009278  test    al, 2
0x18000927a  jz      short locret_180009291
0x18000927c  mov     edx, eax
0x18000927e  xor     edx, ecx
0x180009280  test    dl, 1
0x180009283  jnz     short locret_180009291
0x180009285  mov     edx, r8d
0x180009288  or      edx, eax
0x18000928a  lock cmpxchg [r9], edx
0x18000928f  jnz     short loc_180009278
0x180009291  retn
```

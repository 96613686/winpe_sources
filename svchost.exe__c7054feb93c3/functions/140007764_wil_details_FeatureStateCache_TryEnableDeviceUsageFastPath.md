# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140007764`
- end: `0x1400077a0`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007900`

## callees

- `0x140007764`

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
  v4 = *Feature_ResourceManagerLimits__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_ResourceManagerLimits__private_descriptor[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x140007764  sub     edx, 3
0x140007767  jz      short loc_140007774
0x140007769  cmp     edx, 1
0x14000776c  jnz     short locret_14000779F
0x14000776e  lea     r8d, [rdx+1Fh]
0x140007772  jmp     short loc_14000777A
0x140007774  mov     r8d, 10h
0x14000777a  mov     r9, cs:Feature_ResourceManagerLimits__private_descriptor
0x140007781  mov     eax, [r9]
0x140007784  jmp     short loc_14000779B
0x140007786  mov     edx, eax
0x140007788  xor     edx, ecx
0x14000778a  test    dl, 1
0x14000778d  jnz     short locret_14000779F
0x14000778f  mov     edx, r8d
0x140007792  or      edx, eax
0x140007794  lock cmpxchg [r9], edx
0x140007799  jz      short locret_14000779F
0x14000779b  test    al, 2
0x14000779d  jnz     short loc_140007786
0x14000779f  retn
```

# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140007b6c`
- end: `0x140007ba8`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007d4c`

## callees

- `0x140007b6c`

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
  v4 = *Feature_ResourceManagerLimits__private_descriptor;
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_ResourceManagerLimits__private_descriptor, v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x140007b6c  sub     edx, 3
0x140007b6f  jz      short loc_140007B7C
0x140007b71  cmp     edx, 1
0x140007b74  jnz     short locret_140007BA7
0x140007b76  lea     r8d, [rdx+1Fh]
0x140007b7a  jmp     short loc_140007B82
0x140007b7c  mov     r8d, 10h
0x140007b82  mov     r9, cs:Feature_ResourceManagerLimits__private_descriptor
0x140007b89  mov     eax, [r9]
0x140007b8c  jmp     short loc_140007BA3
0x140007b8e  mov     edx, eax
0x140007b90  xor     edx, ecx
0x140007b92  test    dl, 1
0x140007b95  jnz     short locret_140007BA7
0x140007b97  mov     edx, r8d
0x140007b9a  or      edx, eax
0x140007b9c  lock cmpxchg [r9], edx
0x140007ba1  jz      short locret_140007BA7
0x140007ba3  test    al, 2
0x140007ba5  jnz     short loc_140007B8E
0x140007ba7  retn
```

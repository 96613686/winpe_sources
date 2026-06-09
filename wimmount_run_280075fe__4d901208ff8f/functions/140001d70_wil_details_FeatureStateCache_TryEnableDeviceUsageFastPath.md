# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140001d70`
- end: `0x140001d8f`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400090e0`

## callees

- `0x140001d70`

## pseudocode

```c
int *__fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(__int64 a1, int a2)
{
  int v2; // edx
  unsigned int v3; // ecx
  int *result; // rax

  v2 = a2 - 3;
  if ( v2 )
  {
    if ( v2 != 1 )
      return result;
    v3 = 32;
  }
  else
  {
    v3 = 16;
  }
  result = wil_details_featureDescriptors_a[0];
  _InterlockedOr(wil_details_featureDescriptors_a[0], v3);
  return result;
}

```

## disassembly

```asm
0x140001d70  sub     edx, 3
0x140001d73  jz      short loc_140001D7F
0x140001d75  cmp     edx, 1
0x140001d78  jnz     short locret_140001D8E
0x140001d7a  lea     ecx, [rdx+1Fh]
0x140001d7d  jmp     short loc_140001D84
0x140001d7f  mov     ecx, 10h
0x140001d84  mov     rax, cs:wil_details_featureDescriptors_a
0x140001d8b  lock or [rax], ecx
0x140001d8e  retn
```

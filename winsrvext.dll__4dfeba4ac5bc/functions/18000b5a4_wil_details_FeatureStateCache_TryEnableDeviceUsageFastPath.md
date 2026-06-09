# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x18000b5a4`
- end: `0x18000b5f3`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b830`

## callees

- `0x18000b5a4`

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
0x18000b5a4  mov     r10, r8
0x18000b5a7  sub     edx, 3
0x18000b5aa  jz      short loc_18000B5B7
0x18000b5ac  cmp     edx, 1
0x18000b5af  jnz     short locret_18000B5F2
0x18000b5b1  lea     r9d, [rdx+1Fh]
0x18000b5b5  jmp     short loc_18000B5BD
0x18000b5b7  mov     r9d, 10h
0x18000b5bd  cmp     byte ptr [r10+1Eh], 0
0x18000b5c2  mov     r8, [r8]
0x18000b5c5  jnz     short loc_18000B5EE
0x18000b5c7  cmp     byte ptr [r10+1Dh], 0
0x18000b5cc  jnz     short loc_18000B5EE
0x18000b5ce  mov     eax, [r8]
0x18000b5d1  jmp     short loc_18000B5E8
0x18000b5d3  mov     edx, eax
0x18000b5d5  xor     edx, ecx
0x18000b5d7  test    dl, 1
0x18000b5da  jnz     short locret_18000B5F2
0x18000b5dc  mov     edx, r9d
0x18000b5df  or      edx, eax
0x18000b5e1  lock cmpxchg [r8], edx
0x18000b5e6  jz      short locret_18000B5F2
0x18000b5e8  test    al, 2
0x18000b5ea  jnz     short loc_18000B5D3
0x18000b5ec  retn
0x18000b5ee  lock or [r8], r9d
0x18000b5f2  retn
```

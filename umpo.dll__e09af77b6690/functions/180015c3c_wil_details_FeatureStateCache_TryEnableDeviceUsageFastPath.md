# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180015c3c`
- end: `0x180015c88`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `76`
- prototype: `void __fastcall(unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015de8`

## callees

- `0x180015c3c`

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
0x180015c3c  mov     r10, r8
0x180015c3f  sub     edx, 3
0x180015c42  jz      short loc_180015C4F
0x180015c44  cmp     edx, 1
0x180015c47  jnz     short locret_180015C87
0x180015c49  lea     r9d, [rdx+1Fh]
0x180015c4d  jmp     short loc_180015C55
0x180015c4f  mov     r9d, 10h
0x180015c55  cmp     byte ptr [r10+1Eh], 0
0x180015c5a  mov     r8, [r8]
0x180015c5d  jnz     short loc_180015C83
0x180015c5f  cmp     byte ptr [r10+1Dh], 0
0x180015c64  jnz     short loc_180015C83
0x180015c66  mov     eax, [r8]
0x180015c69  test    al, 2
0x180015c6b  jz      short locret_180015C87
0x180015c6d  mov     edx, eax
0x180015c6f  xor     edx, ecx
0x180015c71  test    dl, 1
0x180015c74  jnz     short locret_180015C87
0x180015c76  mov     edx, r9d
0x180015c79  or      edx, eax
0x180015c7b  lock cmpxchg [r8], edx
0x180015c80  jnz     short loc_180015C69
0x180015c82  retn
0x180015c83  lock or [r8], r9d
0x180015c87  retn
```

# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140011c70`
- end: `0x140011cbd`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140010c94`

## callees

- `0x140011c70`

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
0x140011c70  mov     r10, r8
0x140011c73  sub     edx, 3
0x140011c76  jz      short loc_140011C83
0x140011c78  cmp     edx, 1
0x140011c7b  jnz     short locret_140011CBC
0x140011c7d  lea     r9d, [rdx+1Fh]
0x140011c81  jmp     short loc_140011C89
0x140011c83  mov     r9d, 10h
0x140011c89  cmp     byte ptr [r10+1Eh], 0
0x140011c8e  mov     r8, [r8]
0x140011c91  jnz     short loc_140011CB8
0x140011c93  cmp     byte ptr [r10+1Dh], 0
0x140011c98  jnz     short loc_140011CB8
0x140011c9a  mov     eax, [r8]
0x140011c9d  test    al, 2
0x140011c9f  jz      short locret_140011CBC
0x140011ca1  mov     edx, eax
0x140011ca3  xor     edx, ecx
0x140011ca5  test    dl, 1
0x140011ca8  jnz     short locret_140011CBC
0x140011caa  mov     edx, r9d
0x140011cad  or      edx, eax
0x140011caf  lock cmpxchg [r8], edx
0x140011cb4  jnz     short loc_140011C9D
0x140011cb6  retn
0x140011cb8  lock or [r8], r9d
0x140011cbc  retn
```

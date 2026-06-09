# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140017e14`
- end: `0x140017e63`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017fbc`

## callees

- `0x140017e14`

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
0x140017e14  mov     r10, r8
0x140017e17  sub     edx, 3
0x140017e1a  jz      short loc_140017E27
0x140017e1c  cmp     edx, 1
0x140017e1f  jnz     short locret_140017E62
0x140017e21  lea     r9d, [rdx+1Fh]
0x140017e25  jmp     short loc_140017E2D
0x140017e27  mov     r9d, 10h
0x140017e2d  cmp     byte ptr [r10+1Eh], 0
0x140017e32  mov     r8, [r8]
0x140017e35  jnz     short loc_140017E5E
0x140017e37  cmp     byte ptr [r10+1Dh], 0
0x140017e3c  jnz     short loc_140017E5E
0x140017e3e  mov     eax, [r8]
0x140017e41  jmp     short loc_140017E58
0x140017e43  mov     edx, eax
0x140017e45  xor     edx, ecx
0x140017e47  test    dl, 1
0x140017e4a  jnz     short locret_140017E62
0x140017e4c  mov     edx, r9d
0x140017e4f  or      edx, eax
0x140017e51  lock cmpxchg [r8], edx
0x140017e56  jz      short locret_140017E62
0x140017e58  test    al, 2
0x140017e5a  jnz     short loc_140017E43
0x140017e5c  retn
0x140017e5e  lock or [r8], r9d
0x140017e62  retn
```

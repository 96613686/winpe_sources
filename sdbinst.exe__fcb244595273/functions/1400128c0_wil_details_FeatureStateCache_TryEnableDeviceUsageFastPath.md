# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x1400128c0`
- end: `0x14001290e`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140012b60`

## callees

- `0x1400128c0`

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
0x1400128c0  mov     r10, r8
0x1400128c3  sub     edx, 3
0x1400128c6  jz      short loc_1400128D3
0x1400128c8  cmp     edx, 1
0x1400128cb  jnz     short locret_14001290D
0x1400128cd  lea     r9d, [rdx+1Fh]
0x1400128d1  jmp     short loc_1400128D9
0x1400128d3  mov     r9d, 10h
0x1400128d9  cmp     byte ptr [r10+1Eh], 0
0x1400128de  mov     r8, [r8]
0x1400128e1  jnz     short loc_140012909
0x1400128e3  cmp     byte ptr [r10+1Dh], 0
0x1400128e8  jnz     short loc_140012909
0x1400128ea  mov     eax, [r8]
0x1400128ed  jmp     short loc_140012904
0x1400128ef  mov     edx, eax
0x1400128f1  xor     edx, ecx
0x1400128f3  test    dl, 1
0x1400128f6  jnz     short locret_14001290D
0x1400128f8  mov     edx, r9d
0x1400128fb  or      edx, eax
0x1400128fd  lock cmpxchg [r8], edx
0x140012902  jz      short locret_14001290D
0x140012904  test    al, 2
0x140012906  jnz     short loc_1400128EF
0x140012908  retn
0x140012909  lock or [r8], r9d
0x14001290d  retn
```

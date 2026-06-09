# wil_details_EvaluateFeatureDependencies

- ea: `0x14000a41c`
- end: `0x14000a503`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a670`
- `0x14000c2d0`

## callees

- `0x14000a41c`
- `0x14000a50c`

## pseudocode

```c
void wil_details_EvaluateFeatureDependencies()
{
  volatile signed __int32 **i; // r9
  volatile signed __int32 **v1; // rcx
  unsigned int v2; // r10d
  volatile unsigned __int32 v3; // edx
  int v4; // eax
  volatile signed __int32 *v5; // r11
  __int64 v6; // r9

  i = (volatile signed __int32 **)wil_details_featureDescriptors_a;
  v1 = (volatile signed __int32 **)wil_details_featureDescriptors_a;
  if ( wil_details_featureDescriptors_a < (int **)wil_details_featureDescriptors_z )
  {
    while ( !*v1 )
    {
      if ( ++v1 >= (volatile signed __int32 **)wil_details_featureDescriptors_z )
        goto LABEL_21;
    }
    if ( !v1 )
      goto LABEL_21;
    v2 = 0;
    do
    {
      v3 = **v1;
      if ( (v3 & 0x200) != 0 )
      {
        v4 = 0;
        if ( (v3 & 0x180) != 0 )
          LOBYTE(v4) = (**v1 & 0x180) == 256;
        else
          LOBYTE(v4) = *((_BYTE *)v1 + 31) != 0;
        v2 = v2 & 0xFFFFFFBF | ((v4 ^ (v3 >> 6) & 1) << 6);
        _InterlockedXor(*v1, v2);
      }
      for ( v1 += 7; ; ++v1 )
      {
        if ( v1 >= (volatile signed __int32 **)wil_details_featureDescriptors_z )
          goto LABEL_21;
        if ( *v1 )
          break;
      }
    }
    while ( v1 );
LABEL_21:
    while ( i < (volatile signed __int32 **)wil_details_featureDescriptors_z )
    {
      if ( *i )
      {
LABEL_28:
        if ( i )
        {
          wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*i, (__int64)i);
          for ( i = (volatile signed __int32 **)(v6 + 56);
                i < (volatile signed __int32 **)wil_details_featureDescriptors_z;
                ++i )
          {
            if ( *i != v5 )
              goto LABEL_28;
          }
        }
        return;
      }
      ++i;
    }
  }
}

```

## disassembly

```asm
0x14000a41c  push    rbx
0x14000a41e  sub     rsp, 20h
0x14000a422  xor     r11d, r11d
0x14000a425  lea     r9, wil_details_featureDescriptors_a
0x14000a42c  lea     rbx, wil_details_featureDescriptors_z
0x14000a433  mov     [rsp+28h+arg_0], r11
0x14000a438  mov     rcx, r9
0x14000a43b  cmp     r9, rbx
0x14000a43e  jnb     loc_14000A4FC
0x14000a444  cmp     [rcx], r11
0x14000a447  jnz     short loc_14000A454
0x14000a449  add     rcx, 8
0x14000a44d  cmp     rcx, rbx
0x14000a450  jb      short loc_14000A444
0x14000a452  jmp     short loc_14000A4CF
0x14000a454  test    rcx, rcx
0x14000a457  jz      short loc_14000A4CF
0x14000a459  mov     r10d, dword ptr [rsp+28h+arg_0]
0x14000a45e  mov     rax, [rcx]
0x14000a461  mov     edx, [rax]
0x14000a463  bt      edx, 9
0x14000a467  jnb     short loc_14000A4A9
0x14000a469  mov     r8d, edx
0x14000a46c  mov     eax, r11d
0x14000a46f  and     r8d, 180h
0x14000a476  jnz     short loc_14000A481
0x14000a478  cmp     [rcx+1Fh], r11b
0x14000a47c  setnz   al
0x14000a47f  jmp     short loc_14000A48B
0x14000a481  cmp     r8d, 100h
0x14000a488  setz    al
0x14000a48b  shr     edx, 6
0x14000a48e  and     edx, 1
0x14000a491  xor     edx, eax
0x14000a493  mov     eax, r10d
0x14000a496  shl     edx, 6
0x14000a499  and     eax, 0FFFFFFBFh
0x14000a49c  mov     r10d, edx
0x14000a49f  or      r10d, eax
0x14000a4a2  mov     rax, [rcx]
0x14000a4a5  lock xor [rax], r10d
0x14000a4a9  add     rcx, 38h ; '8'
0x14000a4ad  jmp     short loc_14000A4B8
0x14000a4af  cmp     [rcx], r11
0x14000a4b2  jnz     short loc_14000A4BF
0x14000a4b4  add     rcx, 8
0x14000a4b8  cmp     rcx, rbx
0x14000a4bb  jb      short loc_14000A4AF
0x14000a4bd  jmp     short loc_14000A4CF
0x14000a4bf  test    rcx, rcx
0x14000a4c2  jnz     short loc_14000A45E
0x14000a4c4  jmp     short loc_14000A4CF
0x14000a4c6  cmp     [r9], r11
0x14000a4c9  jnz     short loc_14000A4F7
0x14000a4cb  add     r9, 8
0x14000a4cf  cmp     r9, rbx
0x14000a4d2  jb      short loc_14000A4C6
0x14000a4d4  jmp     short loc_14000A4FC
0x14000a4d6  mov     rcx, [r9]
0x14000a4d9  mov     rdx, r9
0x14000a4dc  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000a4e1  add     r9, 38h ; '8'
0x14000a4e5  jmp     short loc_14000A4F0
0x14000a4e7  cmp     [r9], r11
0x14000a4ea  jnz     short loc_14000A4F7
0x14000a4ec  add     r9, 8
0x14000a4f0  cmp     r9, rbx
0x14000a4f3  jb      short loc_14000A4E7
0x14000a4f5  jmp     short loc_14000A4FC
0x14000a4f7  test    r9, r9
0x14000a4fa  jnz     short loc_14000A4D6
0x14000a4fc  add     rsp, 20h
0x14000a500  pop     rbx
0x14000a501  retn
```

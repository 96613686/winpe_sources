# wil_details_EvaluateFeatureDependencies

- ea: `0x14000a41c`
- end: `0x14000a52b`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a710`
- `0x14000c2d0`

## callees

- `0x14000a41c`
- `0x14000a570`

## pseudocode

```c
void wil_details_EvaluateFeatureDependencies()
{
  volatile signed __int32 **v0; // rbx
  volatile signed __int32 **v1; // rcx
  unsigned int v2; // r9d
  volatile unsigned __int32 v3; // edx
  BOOL v4; // eax
  unsigned __int32 v5; // [rsp+30h] [rbp+8h]

  v0 = (volatile signed __int32 **)wil_details_featureDescriptors_a;
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
        if ( (v3 & 0x180) != 0 )
          v4 = (**v1 & 0x180) == 256;
        else
          v4 = *((_BYTE *)v1 + 31) != 0;
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
    while ( v0 < (volatile signed __int32 **)wil_details_featureDescriptors_z )
    {
      if ( *v0 )
      {
LABEL_30:
        if ( v0 )
        {
          v5 = **v0;
          if ( (v5 & 0x200) != 0 )
            wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(*v0, v5, (__int64)v0);
          for ( v0 += 7; v0 < (volatile signed __int32 **)wil_details_featureDescriptors_z; ++v0 )
          {
            if ( *v0 )
              goto LABEL_30;
          }
        }
        return;
      }
      ++v0;
    }
  }
}

```

## disassembly

```asm
0x14000a41c  mov     [rsp+arg_8], rbx
0x14000a421  push    rsi
0x14000a422  sub     rsp, 20h
0x14000a426  lea     rbx, wil_details_featureDescriptors_a
0x14000a42d  mov     [rsp+28h+arg_0], 0
0x14000a436  lea     rsi, wil_details_featureDescriptors_z
0x14000a43d  mov     rcx, rbx
0x14000a440  cmp     rbx, rsi
0x14000a443  jnb     loc_14000A51F
0x14000a449  cmp     qword ptr [rcx], 0
0x14000a44d  jnz     short loc_14000A45A
0x14000a44f  add     rcx, 8
0x14000a453  cmp     rcx, rsi
0x14000a456  jb      short loc_14000A449
0x14000a458  jmp     short loc_14000A4D7
0x14000a45a  test    rcx, rcx
0x14000a45d  jz      short loc_14000A4D7
0x14000a45f  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14000a464  mov     rax, [rcx]
0x14000a467  mov     edx, [rax]
0x14000a469  bt      edx, 9
0x14000a46d  jnb     short loc_14000A4AF
0x14000a46f  mov     r8d, edx
0x14000a472  and     r8d, 180h
0x14000a479  jnz     short loc_14000A485
0x14000a47b  xor     eax, eax
0x14000a47d  cmp     [rcx+1Fh], al
0x14000a480  setnz   al
0x14000a483  jmp     short loc_14000A491
0x14000a485  xor     eax, eax
0x14000a487  cmp     r8d, 100h
0x14000a48e  setz    al
0x14000a491  shr     edx, 6
0x14000a494  and     edx, 1
0x14000a497  xor     edx, eax
0x14000a499  mov     eax, r9d
0x14000a49c  shl     edx, 6
0x14000a49f  and     eax, 0FFFFFFBFh
0x14000a4a2  mov     r9d, edx
0x14000a4a5  or      r9d, eax
0x14000a4a8  mov     rax, [rcx]
0x14000a4ab  lock xor [rax], r9d
0x14000a4af  add     rcx, 38h ; '8'
0x14000a4b3  jmp     short loc_14000A4BF
0x14000a4b5  cmp     qword ptr [rcx], 0
0x14000a4b9  jnz     short loc_14000A4C6
0x14000a4bb  add     rcx, 8
0x14000a4bf  cmp     rcx, rsi
0x14000a4c2  jb      short loc_14000A4B5
0x14000a4c4  jmp     short loc_14000A4D7
0x14000a4c6  test    rcx, rcx
0x14000a4c9  jnz     short loc_14000A464
0x14000a4cb  jmp     short loc_14000A4D7
0x14000a4cd  cmp     qword ptr [rbx], 0
0x14000a4d1  jnz     short loc_14000A51A
0x14000a4d3  add     rbx, 8
0x14000a4d7  cmp     rbx, rsi
0x14000a4da  jb      short loc_14000A4CD
0x14000a4dc  jmp     short loc_14000A51F
0x14000a4de  mov     rcx, [rbx]
0x14000a4e1  mov     [rsp+28h+arg_0], 0
0x14000a4ea  mov     eax, [rcx]
0x14000a4ec  mov     dword ptr [rsp+28h+arg_0], eax
0x14000a4f0  bt      eax, 9
0x14000a4f4  jnb     short loc_14000A503
0x14000a4f6  mov     rdx, [rsp+28h+arg_0]
0x14000a4fb  mov     r8, rbx
0x14000a4fe  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14000a503  add     rbx, 38h ; '8'
0x14000a507  jmp     short loc_14000A513
0x14000a509  cmp     qword ptr [rbx], 0
0x14000a50d  jnz     short loc_14000A51A
0x14000a50f  add     rbx, 8
0x14000a513  cmp     rbx, rsi
0x14000a516  jb      short loc_14000A509
0x14000a518  jmp     short loc_14000A51F
0x14000a51a  test    rbx, rbx
0x14000a51d  jnz     short loc_14000A4DE
0x14000a51f  mov     rbx, [rsp+28h+arg_8]
0x14000a524  add     rsp, 20h
0x14000a528  pop     rsi
0x14000a529  retn
```

# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140013aa4`
- end: `0x140013b30`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001396c`

## callees

- `0x1400084a4`
- `0x140013aa4`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 *result; // rax
  __int64 *v1; // rdx
  int v2; // r9d
  unsigned int v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding(wil_details_featureDescriptors_a);
  v1 = result;
  if ( result )
  {
    v2 = 0;
    do
    {
      v3 = *(_DWORD *)*v1;
      if ( (v3 & 0x200) != 0 )
      {
        if ( (v3 & 0x180) != 0 )
          v4 = (*(_DWORD *)*v1 & 0x180) == 256;
        else
          v4 = *((_BYTE *)v1 + 31) != 0;
        _InterlockedXor((volatile signed __int32 *)*v1, v2 & 0xFFFFFFBF | ((v4 ^ (v3 >> 6) & 1) << 6));
      }
      result = wil_details_FeatureDescriptors_SkipPadding(v1 + 7);
      v1 = result;
    }
    while ( result );
  }
  return result;
}

```

## disassembly

```asm
0x140013aa4  sub     rsp, 28h
0x140013aa8  lea     rcx, wil_details_featureDescriptors_a
0x140013aaf  mov     [rsp+28h+arg_0], 0
0x140013ab8  call    wil_details_FeatureDescriptors_SkipPadding
0x140013abd  mov     rdx, rax
0x140013ac0  test    rax, rax
0x140013ac3  jz      short loc_140013B2A
0x140013ac5  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140013aca  mov     rcx, [rdx]
0x140013acd  mov     r8d, [rcx]
0x140013ad0  bt      r8d, 9
0x140013ad5  jnb     short loc_140013B19
0x140013ad7  mov     ecx, r8d
0x140013ada  and     ecx, 180h
0x140013ae0  jnz     short loc_140013AEC
0x140013ae2  xor     eax, eax
0x140013ae4  cmp     [rdx+1Fh], al
0x140013ae7  setnz   al
0x140013aea  jmp     short loc_140013AF7
0x140013aec  xor     eax, eax
0x140013aee  cmp     ecx, 100h
0x140013af4  setz    al
0x140013af7  shr     r8d, 6
0x140013afb  and     r8d, 1
0x140013aff  xor     r8d, eax
0x140013b02  mov     eax, r9d
0x140013b05  shl     r8d, 6
0x140013b09  and     eax, 0FFFFFFBFh
0x140013b0c  mov     r9d, r8d
0x140013b0f  or      r9d, eax
0x140013b12  mov     rax, [rdx]
0x140013b15  lock xor [rax], r9d
0x140013b19  lea     rcx, [rdx+38h]
0x140013b1d  call    wil_details_FeatureDescriptors_SkipPadding
0x140013b22  mov     rdx, rax
0x140013b25  test    rax, rax
0x140013b28  jnz     short loc_140013ACA
0x140013b2a  add     rsp, 28h
0x140013b2e  retn
```

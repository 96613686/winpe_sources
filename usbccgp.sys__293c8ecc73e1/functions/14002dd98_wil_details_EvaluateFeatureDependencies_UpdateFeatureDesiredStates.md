# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14002dd98`
- end: `0x14002de24`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002dd58`

## callees

- `0x14000ef2c`
- `0x14002dd98`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 *result; // rax
  __int64 *v1; // rdx
  int v2; // r9d
  unsigned int v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding((__int64 *)&wil_details_featureDescriptors_a);
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
0x14002dd98  sub     rsp, 28h
0x14002dd9c  lea     rcx, wil_details_featureDescriptors_a
0x14002dda3  mov     [rsp+28h+arg_0], 0
0x14002ddac  call    wil_details_FeatureDescriptors_SkipPadding
0x14002ddb1  mov     rdx, rax
0x14002ddb4  test    rax, rax
0x14002ddb7  jz      short loc_14002DE1E
0x14002ddb9  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14002ddbe  mov     rcx, [rdx]
0x14002ddc1  mov     r8d, [rcx]
0x14002ddc4  bt      r8d, 9
0x14002ddc9  jnb     short loc_14002DE0D
0x14002ddcb  mov     ecx, r8d
0x14002ddce  and     ecx, 180h
0x14002ddd4  jnz     short loc_14002DDE0
0x14002ddd6  xor     eax, eax
0x14002ddd8  cmp     [rdx+1Fh], al
0x14002dddb  setnz   al
0x14002ddde  jmp     short loc_14002DDEB
0x14002dde0  xor     eax, eax
0x14002dde2  cmp     ecx, 100h
0x14002dde8  setz    al
0x14002ddeb  shr     r8d, 6
0x14002ddef  and     r8d, 1
0x14002ddf3  xor     r8d, eax
0x14002ddf6  mov     eax, r9d
0x14002ddf9  shl     r8d, 6
0x14002ddfd  and     eax, 0FFFFFFBFh
0x14002de00  mov     r9d, r8d
0x14002de03  or      r9d, eax
0x14002de06  mov     rax, [rdx]
0x14002de09  lock xor [rax], r9d
0x14002de0d  lea     rcx, [rdx+38h]
0x14002de11  call    wil_details_FeatureDescriptors_SkipPadding
0x14002de16  mov     rdx, rax
0x14002de19  test    rax, rax
0x14002de1c  jnz     short loc_14002DDBE
0x14002de1e  add     rsp, 28h
0x14002de22  retn
```

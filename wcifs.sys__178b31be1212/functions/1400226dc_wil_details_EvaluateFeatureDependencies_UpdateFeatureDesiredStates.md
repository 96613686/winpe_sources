# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x1400226dc`
- end: `0x140022768`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002254c`

## callees

- `0x140003248`
- `0x1400226dc`

## pseudocode

```c
__int64 wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 result; // rax
  volatile signed __int32 **v1; // rdx
  int v2; // r9d
  volatile unsigned __int32 v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding(&wil_details_featureDescriptors_a);
  v1 = (volatile signed __int32 **)result;
  if ( result )
  {
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
        _InterlockedXor(*v1, v2 & 0xFFFFFFBF | ((v4 ^ (v3 >> 6) & 1) << 6));
      }
      result = wil_details_FeatureDescriptors_SkipPadding(v1 + 7);
      v1 = (volatile signed __int32 **)result;
    }
    while ( result );
  }
  return result;
}

```

## disassembly

```asm
0x1400226dc  sub     rsp, 28h
0x1400226e0  lea     rcx, wil_details_featureDescriptors_a
0x1400226e7  mov     [rsp+28h+arg_0], 0
0x1400226f0  call    wil_details_FeatureDescriptors_SkipPadding
0x1400226f5  mov     rdx, rax
0x1400226f8  test    rax, rax
0x1400226fb  jz      short loc_140022762
0x1400226fd  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140022702  mov     rcx, [rdx]
0x140022705  mov     r8d, [rcx]
0x140022708  bt      r8d, 9
0x14002270d  jnb     short loc_140022751
0x14002270f  mov     ecx, r8d
0x140022712  and     ecx, 180h
0x140022718  jnz     short loc_140022724
0x14002271a  xor     eax, eax
0x14002271c  cmp     [rdx+1Fh], al
0x14002271f  setnz   al
0x140022722  jmp     short loc_14002272F
0x140022724  xor     eax, eax
0x140022726  cmp     ecx, 100h
0x14002272c  setz    al
0x14002272f  shr     r8d, 6
0x140022733  and     r8d, 1
0x140022737  xor     r8d, eax
0x14002273a  mov     eax, r9d
0x14002273d  shl     r8d, 6
0x140022741  and     eax, 0FFFFFFBFh
0x140022744  mov     r9d, r8d
0x140022747  or      r9d, eax
0x14002274a  mov     rax, [rdx]
0x14002274d  lock xor [rax], r9d
0x140022751  lea     rcx, [rdx+38h]
0x140022755  call    wil_details_FeatureDescriptors_SkipPadding
0x14002275a  mov     rdx, rax
0x14002275d  test    rax, rax
0x140022760  jnz     short loc_140022702
0x140022762  add     rsp, 28h
0x140022766  retn
```

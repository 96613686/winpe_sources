# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140022684`
- end: `0x140022710`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002254c`

## callees

- `0x140003248`
- `0x140022684`

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
0x140022684  sub     rsp, 28h
0x140022688  lea     rcx, wil_details_featureDescriptors_a
0x14002268f  mov     [rsp+28h+arg_0], 0
0x140022698  call    wil_details_FeatureDescriptors_SkipPadding
0x14002269d  mov     rdx, rax
0x1400226a0  test    rax, rax
0x1400226a3  jz      short loc_14002270A
0x1400226a5  mov     r9d, dword ptr [rsp+28h+arg_0]
0x1400226aa  mov     rcx, [rdx]
0x1400226ad  mov     r8d, [rcx]
0x1400226b0  bt      r8d, 9
0x1400226b5  jnb     short loc_1400226F9
0x1400226b7  mov     ecx, r8d
0x1400226ba  and     ecx, 180h
0x1400226c0  jnz     short loc_1400226CC
0x1400226c2  xor     eax, eax
0x1400226c4  cmp     [rdx+1Fh], al
0x1400226c7  setnz   al
0x1400226ca  jmp     short loc_1400226D7
0x1400226cc  xor     eax, eax
0x1400226ce  cmp     ecx, 100h
0x1400226d4  setz    al
0x1400226d7  shr     r8d, 6
0x1400226db  and     r8d, 1
0x1400226df  xor     r8d, eax
0x1400226e2  mov     eax, r9d
0x1400226e5  shl     r8d, 6
0x1400226e9  and     eax, 0FFFFFFBFh
0x1400226ec  mov     r9d, r8d
0x1400226ef  or      r9d, eax
0x1400226f2  mov     rax, [rdx]
0x1400226f5  lock xor [rax], r9d
0x1400226f9  lea     rcx, [rdx+38h]
0x1400226fd  call    wil_details_FeatureDescriptors_SkipPadding
0x140022702  mov     rdx, rax
0x140022705  test    rax, rax
0x140022708  jnz     short loc_1400226AA
0x14002270a  add     rsp, 28h
0x14002270e  retn
```

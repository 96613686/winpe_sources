# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x1400368f4`
- end: `0x140036980`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400367bc`

## callees

- `0x140008114`
- `0x1400368f4`

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
0x1400368f4  sub     rsp, 28h
0x1400368f8  lea     rcx, wil_details_featureDescriptors_a
0x1400368ff  mov     [rsp+28h+arg_0], 0
0x140036908  call    wil_details_FeatureDescriptors_SkipPadding
0x14003690d  mov     rdx, rax
0x140036910  test    rax, rax
0x140036913  jz      short loc_14003697A
0x140036915  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14003691a  mov     rcx, [rdx]
0x14003691d  mov     r8d, [rcx]
0x140036920  bt      r8d, 9
0x140036925  jnb     short loc_140036969
0x140036927  mov     ecx, r8d
0x14003692a  and     ecx, 180h
0x140036930  jnz     short loc_14003693C
0x140036932  xor     eax, eax
0x140036934  cmp     [rdx+1Fh], al
0x140036937  setnz   al
0x14003693a  jmp     short loc_140036947
0x14003693c  xor     eax, eax
0x14003693e  cmp     ecx, 100h
0x140036944  setz    al
0x140036947  shr     r8d, 6
0x14003694b  and     r8d, 1
0x14003694f  xor     r8d, eax
0x140036952  mov     eax, r9d
0x140036955  shl     r8d, 6
0x140036959  and     eax, 0FFFFFFBFh
0x14003695c  mov     r9d, r8d
0x14003695f  or      r9d, eax
0x140036962  mov     rax, [rdx]
0x140036965  lock xor [rax], r9d
0x140036969  lea     rcx, [rdx+38h]
0x14003696d  call    wil_details_FeatureDescriptors_SkipPadding
0x140036972  mov     rdx, rax
0x140036975  test    rax, rax
0x140036978  jnz     short loc_14003691A
0x14003697a  add     rsp, 28h
0x14003697e  retn
```

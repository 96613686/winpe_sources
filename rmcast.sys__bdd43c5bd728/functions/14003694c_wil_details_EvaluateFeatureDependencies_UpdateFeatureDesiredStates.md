# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14003694c`
- end: `0x1400369d8`
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
- `0x14003694c`

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
0x14003694c  sub     rsp, 28h
0x140036950  lea     rcx, wil_details_featureDescriptors_a
0x140036957  mov     [rsp+28h+arg_0], 0
0x140036960  call    wil_details_FeatureDescriptors_SkipPadding
0x140036965  mov     rdx, rax
0x140036968  test    rax, rax
0x14003696b  jz      short loc_1400369D2
0x14003696d  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140036972  mov     rcx, [rdx]
0x140036975  mov     r8d, [rcx]
0x140036978  bt      r8d, 9
0x14003697d  jnb     short loc_1400369C1
0x14003697f  mov     ecx, r8d
0x140036982  and     ecx, 180h
0x140036988  jnz     short loc_140036994
0x14003698a  xor     eax, eax
0x14003698c  cmp     [rdx+1Fh], al
0x14003698f  setnz   al
0x140036992  jmp     short loc_14003699F
0x140036994  xor     eax, eax
0x140036996  cmp     ecx, 100h
0x14003699c  setz    al
0x14003699f  shr     r8d, 6
0x1400369a3  and     r8d, 1
0x1400369a7  xor     r8d, eax
0x1400369aa  mov     eax, r9d
0x1400369ad  shl     r8d, 6
0x1400369b1  and     eax, 0FFFFFFBFh
0x1400369b4  mov     r9d, r8d
0x1400369b7  or      r9d, eax
0x1400369ba  mov     rax, [rdx]
0x1400369bd  lock xor [rax], r9d
0x1400369c1  lea     rcx, [rdx+38h]
0x1400369c5  call    wil_details_FeatureDescriptors_SkipPadding
0x1400369ca  mov     rdx, rax
0x1400369cd  test    rax, rax
0x1400369d0  jnz     short loc_140036972
0x1400369d2  add     rsp, 28h
0x1400369d6  retn
```

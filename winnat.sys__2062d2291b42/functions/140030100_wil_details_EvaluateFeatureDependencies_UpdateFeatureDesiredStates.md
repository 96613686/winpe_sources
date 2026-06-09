# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140030100`
- end: `0x14003018c`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002ff70`

## callees

- `0x14000e184`
- `0x140030100`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 *result; // rax
  __int64 *v1; // rdx
  int v2; // r9d
  unsigned int v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding((__int64 *)wil_details_featureDescriptors_a);
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
0x140030100  sub     rsp, 28h
0x140030104  lea     rcx, wil_details_featureDescriptors_a
0x14003010b  mov     [rsp+28h+arg_0], 0
0x140030114  call    wil_details_FeatureDescriptors_SkipPadding
0x140030119  mov     rdx, rax
0x14003011c  test    rax, rax
0x14003011f  jz      short loc_140030186
0x140030121  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140030126  mov     rcx, [rdx]
0x140030129  mov     r8d, [rcx]
0x14003012c  bt      r8d, 9
0x140030131  jnb     short loc_140030175
0x140030133  mov     ecx, r8d
0x140030136  and     ecx, 180h
0x14003013c  jnz     short loc_140030148
0x14003013e  xor     eax, eax
0x140030140  cmp     [rdx+1Fh], al
0x140030143  setnz   al
0x140030146  jmp     short loc_140030153
0x140030148  xor     eax, eax
0x14003014a  cmp     ecx, 100h
0x140030150  setz    al
0x140030153  shr     r8d, 6
0x140030157  and     r8d, 1
0x14003015b  xor     r8d, eax
0x14003015e  mov     eax, r9d
0x140030161  shl     r8d, 6
0x140030165  and     eax, 0FFFFFFBFh
0x140030168  mov     r9d, r8d
0x14003016b  or      r9d, eax
0x14003016e  mov     rax, [rdx]
0x140030171  lock xor [rax], r9d
0x140030175  lea     rcx, [rdx+38h]
0x140030179  call    wil_details_FeatureDescriptors_SkipPadding
0x14003017e  mov     rdx, rax
0x140030181  test    rax, rax
0x140030184  jnz     short loc_140030126
0x140030186  add     rsp, 28h
0x14003018a  retn
```

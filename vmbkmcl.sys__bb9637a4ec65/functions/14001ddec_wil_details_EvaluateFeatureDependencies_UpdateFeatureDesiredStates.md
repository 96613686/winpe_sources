# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14001ddec`
- end: `0x14001de78`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001dc5c`

## callees

- `0x140010464`
- `0x14001ddec`

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
0x14001ddec  sub     rsp, 28h
0x14001ddf0  lea     rcx, wil_details_featureDescriptors_a
0x14001ddf7  mov     [rsp+28h+arg_0], 0
0x14001de00  call    wil_details_FeatureDescriptors_SkipPadding
0x14001de05  mov     rdx, rax
0x14001de08  test    rax, rax
0x14001de0b  jz      short loc_14001DE72
0x14001de0d  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14001de12  mov     rcx, [rdx]
0x14001de15  mov     r8d, [rcx]
0x14001de18  bt      r8d, 9
0x14001de1d  jnb     short loc_14001DE61
0x14001de1f  mov     ecx, r8d
0x14001de22  and     ecx, 180h
0x14001de28  jnz     short loc_14001DE34
0x14001de2a  xor     eax, eax
0x14001de2c  cmp     [rdx+1Fh], al
0x14001de2f  setnz   al
0x14001de32  jmp     short loc_14001DE3F
0x14001de34  xor     eax, eax
0x14001de36  cmp     ecx, 100h
0x14001de3c  setz    al
0x14001de3f  shr     r8d, 6
0x14001de43  and     r8d, 1
0x14001de47  xor     r8d, eax
0x14001de4a  mov     eax, r9d
0x14001de4d  shl     r8d, 6
0x14001de51  and     eax, 0FFFFFFBFh
0x14001de54  mov     r9d, r8d
0x14001de57  or      r9d, eax
0x14001de5a  mov     rax, [rdx]
0x14001de5d  lock xor [rax], r9d
0x14001de61  lea     rcx, [rdx+38h]
0x14001de65  call    wil_details_FeatureDescriptors_SkipPadding
0x14001de6a  mov     rdx, rax
0x14001de6d  test    rax, rax
0x14001de70  jnz     short loc_14001DE12
0x14001de72  add     rsp, 28h
0x14001de76  retn
```

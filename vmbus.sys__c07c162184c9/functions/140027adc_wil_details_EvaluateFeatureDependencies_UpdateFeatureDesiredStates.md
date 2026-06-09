# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140027adc`
- end: `0x140027b68`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002794c`

## callees

- `0x140003944`
- `0x140027adc`

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
0x140027adc  sub     rsp, 28h
0x140027ae0  lea     rcx, wil_details_featureDescriptors_a
0x140027ae7  mov     [rsp+28h+arg_0], 0
0x140027af0  call    wil_details_FeatureDescriptors_SkipPadding
0x140027af5  mov     rdx, rax
0x140027af8  test    rax, rax
0x140027afb  jz      short loc_140027B62
0x140027afd  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140027b02  mov     rcx, [rdx]
0x140027b05  mov     r8d, [rcx]
0x140027b08  bt      r8d, 9
0x140027b0d  jnb     short loc_140027B51
0x140027b0f  mov     ecx, r8d
0x140027b12  and     ecx, 180h
0x140027b18  jnz     short loc_140027B24
0x140027b1a  xor     eax, eax
0x140027b1c  cmp     [rdx+1Fh], al
0x140027b1f  setnz   al
0x140027b22  jmp     short loc_140027B2F
0x140027b24  xor     eax, eax
0x140027b26  cmp     ecx, 100h
0x140027b2c  setz    al
0x140027b2f  shr     r8d, 6
0x140027b33  and     r8d, 1
0x140027b37  xor     r8d, eax
0x140027b3a  mov     eax, r9d
0x140027b3d  shl     r8d, 6
0x140027b41  and     eax, 0FFFFFFBFh
0x140027b44  mov     r9d, r8d
0x140027b47  or      r9d, eax
0x140027b4a  mov     rax, [rdx]
0x140027b4d  lock xor [rax], r9d
0x140027b51  lea     rcx, [rdx+38h]
0x140027b55  call    wil_details_FeatureDescriptors_SkipPadding
0x140027b5a  mov     rdx, rax
0x140027b5d  test    rax, rax
0x140027b60  jnz     short loc_140027B02
0x140027b62  add     rsp, 28h
0x140027b66  retn
```

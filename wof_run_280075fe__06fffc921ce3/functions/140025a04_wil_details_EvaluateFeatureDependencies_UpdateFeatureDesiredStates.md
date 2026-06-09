# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140025a04`
- end: `0x140025a90`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400258cc`

## callees

- `0x14000f4cc`
- `0x140025a04`

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
0x140025a04  sub     rsp, 28h
0x140025a08  lea     rcx, wil_details_featureDescriptors_a
0x140025a0f  mov     [rsp+28h+arg_0], 0
0x140025a18  call    wil_details_FeatureDescriptors_SkipPadding
0x140025a1d  mov     rdx, rax
0x140025a20  test    rax, rax
0x140025a23  jz      short loc_140025A8A
0x140025a25  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140025a2a  mov     rcx, [rdx]
0x140025a2d  mov     r8d, [rcx]
0x140025a30  bt      r8d, 9
0x140025a35  jnb     short loc_140025A79
0x140025a37  mov     ecx, r8d
0x140025a3a  and     ecx, 180h
0x140025a40  jnz     short loc_140025A4C
0x140025a42  xor     eax, eax
0x140025a44  cmp     [rdx+1Fh], al
0x140025a47  setnz   al
0x140025a4a  jmp     short loc_140025A57
0x140025a4c  xor     eax, eax
0x140025a4e  cmp     ecx, 100h
0x140025a54  setz    al
0x140025a57  shr     r8d, 6
0x140025a5b  and     r8d, 1
0x140025a5f  xor     r8d, eax
0x140025a62  mov     eax, r9d
0x140025a65  shl     r8d, 6
0x140025a69  and     eax, 0FFFFFFBFh
0x140025a6c  mov     r9d, r8d
0x140025a6f  or      r9d, eax
0x140025a72  mov     rax, [rdx]
0x140025a75  lock xor [rax], r9d
0x140025a79  lea     rcx, [rdx+38h]
0x140025a7d  call    wil_details_FeatureDescriptors_SkipPadding
0x140025a82  mov     rdx, rax
0x140025a85  test    rax, rax
0x140025a88  jnz     short loc_140025A2A
0x140025a8a  add     rsp, 28h
0x140025a8e  retn
```

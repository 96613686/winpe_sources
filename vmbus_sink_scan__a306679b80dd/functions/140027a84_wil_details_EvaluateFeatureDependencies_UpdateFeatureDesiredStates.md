# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140027a84`
- end: `0x140027b10`
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
- `0x140027a84`

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
0x140027a84  sub     rsp, 28h
0x140027a88  lea     rcx, wil_details_featureDescriptors_a
0x140027a8f  mov     [rsp+28h+arg_0], 0
0x140027a98  call    wil_details_FeatureDescriptors_SkipPadding
0x140027a9d  mov     rdx, rax
0x140027aa0  test    rax, rax
0x140027aa3  jz      short loc_140027B0A
0x140027aa5  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140027aaa  mov     rcx, [rdx]
0x140027aad  mov     r8d, [rcx]
0x140027ab0  bt      r8d, 9
0x140027ab5  jnb     short loc_140027AF9
0x140027ab7  mov     ecx, r8d
0x140027aba  and     ecx, 180h
0x140027ac0  jnz     short loc_140027ACC
0x140027ac2  xor     eax, eax
0x140027ac4  cmp     [rdx+1Fh], al
0x140027ac7  setnz   al
0x140027aca  jmp     short loc_140027AD7
0x140027acc  xor     eax, eax
0x140027ace  cmp     ecx, 100h
0x140027ad4  setz    al
0x140027ad7  shr     r8d, 6
0x140027adb  and     r8d, 1
0x140027adf  xor     r8d, eax
0x140027ae2  mov     eax, r9d
0x140027ae5  shl     r8d, 6
0x140027ae9  and     eax, 0FFFFFFBFh
0x140027aec  mov     r9d, r8d
0x140027aef  or      r9d, eax
0x140027af2  mov     rax, [rdx]
0x140027af5  lock xor [rax], r9d
0x140027af9  lea     rcx, [rdx+38h]
0x140027afd  call    wil_details_FeatureDescriptors_SkipPadding
0x140027b02  mov     rdx, rax
0x140027b05  test    rax, rax
0x140027b08  jnz     short loc_140027AAA
0x140027b0a  add     rsp, 28h
0x140027b0e  retn
```

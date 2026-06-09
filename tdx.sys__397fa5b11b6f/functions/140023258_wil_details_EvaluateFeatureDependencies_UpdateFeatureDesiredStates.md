# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140023258`
- end: `0x1400232e4`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400230c8`

## callees

- `0x140014694`
- `0x140023258`

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
0x140023258  sub     rsp, 28h
0x14002325c  lea     rcx, wil_details_featureDescriptors_a
0x140023263  mov     [rsp+28h+arg_0], 0
0x14002326c  call    wil_details_FeatureDescriptors_SkipPadding
0x140023271  mov     rdx, rax
0x140023274  test    rax, rax
0x140023277  jz      short loc_1400232DE
0x140023279  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14002327e  mov     rcx, [rdx]
0x140023281  mov     r8d, [rcx]
0x140023284  bt      r8d, 9
0x140023289  jnb     short loc_1400232CD
0x14002328b  mov     ecx, r8d
0x14002328e  and     ecx, 180h
0x140023294  jnz     short loc_1400232A0
0x140023296  xor     eax, eax
0x140023298  cmp     [rdx+1Fh], al
0x14002329b  setnz   al
0x14002329e  jmp     short loc_1400232AB
0x1400232a0  xor     eax, eax
0x1400232a2  cmp     ecx, 100h
0x1400232a8  setz    al
0x1400232ab  shr     r8d, 6
0x1400232af  and     r8d, 1
0x1400232b3  xor     r8d, eax
0x1400232b6  mov     eax, r9d
0x1400232b9  shl     r8d, 6
0x1400232bd  and     eax, 0FFFFFFBFh
0x1400232c0  mov     r9d, r8d
0x1400232c3  or      r9d, eax
0x1400232c6  mov     rax, [rdx]
0x1400232c9  lock xor [rax], r9d
0x1400232cd  lea     rcx, [rdx+38h]
0x1400232d1  call    wil_details_FeatureDescriptors_SkipPadding
0x1400232d6  mov     rdx, rax
0x1400232d9  test    rax, rax
0x1400232dc  jnz     short loc_14002327E
0x1400232de  add     rsp, 28h
0x1400232e2  retn
```

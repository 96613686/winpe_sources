# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14002f0a8`
- end: `0x14002f134`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002ef70`

## callees

- `0x14000e1b4`
- `0x14002f0a8`

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
0x14002f0a8  sub     rsp, 28h
0x14002f0ac  lea     rcx, wil_details_featureDescriptors_a
0x14002f0b3  mov     [rsp+28h+arg_0], 0
0x14002f0bc  call    wil_details_FeatureDescriptors_SkipPadding
0x14002f0c1  mov     rdx, rax
0x14002f0c4  test    rax, rax
0x14002f0c7  jz      short loc_14002F12E
0x14002f0c9  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14002f0ce  mov     rcx, [rdx]
0x14002f0d1  mov     r8d, [rcx]
0x14002f0d4  bt      r8d, 9
0x14002f0d9  jnb     short loc_14002F11D
0x14002f0db  mov     ecx, r8d
0x14002f0de  and     ecx, 180h
0x14002f0e4  jnz     short loc_14002F0F0
0x14002f0e6  xor     eax, eax
0x14002f0e8  cmp     [rdx+1Fh], al
0x14002f0eb  setnz   al
0x14002f0ee  jmp     short loc_14002F0FB
0x14002f0f0  xor     eax, eax
0x14002f0f2  cmp     ecx, 100h
0x14002f0f8  setz    al
0x14002f0fb  shr     r8d, 6
0x14002f0ff  and     r8d, 1
0x14002f103  xor     r8d, eax
0x14002f106  mov     eax, r9d
0x14002f109  shl     r8d, 6
0x14002f10d  and     eax, 0FFFFFFBFh
0x14002f110  mov     r9d, r8d
0x14002f113  or      r9d, eax
0x14002f116  mov     rax, [rdx]
0x14002f119  lock xor [rax], r9d
0x14002f11d  lea     rcx, [rdx+38h]
0x14002f121  call    wil_details_FeatureDescriptors_SkipPadding
0x14002f126  mov     rdx, rax
0x14002f129  test    rax, rax
0x14002f12c  jnz     short loc_14002F0CE
0x14002f12e  add     rsp, 28h
0x14002f132  retn
```

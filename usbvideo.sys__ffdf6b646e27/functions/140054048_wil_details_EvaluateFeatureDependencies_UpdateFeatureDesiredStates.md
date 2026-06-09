# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140054048`
- end: `0x1400540d4`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140054008`

## callees

- `0x140012d40`
- `0x140054048`

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
0x140054048  sub     rsp, 28h
0x14005404c  lea     rcx, wil_details_featureDescriptors_a
0x140054053  mov     [rsp+28h+arg_0], 0
0x14005405c  call    wil_details_FeatureDescriptors_SkipPadding
0x140054061  mov     rdx, rax
0x140054064  test    rax, rax
0x140054067  jz      short loc_1400540CE
0x140054069  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14005406e  mov     rcx, [rdx]
0x140054071  mov     r8d, [rcx]
0x140054074  bt      r8d, 9
0x140054079  jnb     short loc_1400540BD
0x14005407b  mov     ecx, r8d
0x14005407e  and     ecx, 180h
0x140054084  jnz     short loc_140054090
0x140054086  xor     eax, eax
0x140054088  cmp     [rdx+1Fh], al
0x14005408b  setnz   al
0x14005408e  jmp     short loc_14005409B
0x140054090  xor     eax, eax
0x140054092  cmp     ecx, 100h
0x140054098  setz    al
0x14005409b  shr     r8d, 6
0x14005409f  and     r8d, 1
0x1400540a3  xor     r8d, eax
0x1400540a6  mov     eax, r9d
0x1400540a9  shl     r8d, 6
0x1400540ad  and     eax, 0FFFFFFBFh
0x1400540b0  mov     r9d, r8d
0x1400540b3  or      r9d, eax
0x1400540b6  mov     rax, [rdx]
0x1400540b9  lock xor [rax], r9d
0x1400540bd  lea     rcx, [rdx+38h]
0x1400540c1  call    wil_details_FeatureDescriptors_SkipPadding
0x1400540c6  mov     rdx, rax
0x1400540c9  test    rax, rax
0x1400540cc  jnz     short loc_14005406E
0x1400540ce  add     rsp, 28h
0x1400540d2  retn
```

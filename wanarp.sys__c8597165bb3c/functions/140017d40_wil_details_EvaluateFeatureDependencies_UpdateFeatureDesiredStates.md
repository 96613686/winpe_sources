# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140017d40`
- end: `0x140017dcc`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140017bb0`

## callees

- `0x140003c5c`
- `0x140017d40`

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
0x140017d40  sub     rsp, 28h
0x140017d44  lea     rcx, wil_details_featureDescriptors_a
0x140017d4b  mov     [rsp+28h+arg_0], 0
0x140017d54  call    wil_details_FeatureDescriptors_SkipPadding
0x140017d59  mov     rdx, rax
0x140017d5c  test    rax, rax
0x140017d5f  jz      short loc_140017DC6
0x140017d61  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140017d66  mov     rcx, [rdx]
0x140017d69  mov     r8d, [rcx]
0x140017d6c  bt      r8d, 9
0x140017d71  jnb     short loc_140017DB5
0x140017d73  mov     ecx, r8d
0x140017d76  and     ecx, 180h
0x140017d7c  jnz     short loc_140017D88
0x140017d7e  xor     eax, eax
0x140017d80  cmp     [rdx+1Fh], al
0x140017d83  setnz   al
0x140017d86  jmp     short loc_140017D93
0x140017d88  xor     eax, eax
0x140017d8a  cmp     ecx, 100h
0x140017d90  setz    al
0x140017d93  shr     r8d, 6
0x140017d97  and     r8d, 1
0x140017d9b  xor     r8d, eax
0x140017d9e  mov     eax, r9d
0x140017da1  shl     r8d, 6
0x140017da5  and     eax, 0FFFFFFBFh
0x140017da8  mov     r9d, r8d
0x140017dab  or      r9d, eax
0x140017dae  mov     rax, [rdx]
0x140017db1  lock xor [rax], r9d
0x140017db5  lea     rcx, [rdx+38h]
0x140017db9  call    wil_details_FeatureDescriptors_SkipPadding
0x140017dbe  mov     rdx, rax
0x140017dc1  test    rax, rax
0x140017dc4  jnz     short loc_140017D66
0x140017dc6  add     rsp, 28h
0x140017dca  retn
```

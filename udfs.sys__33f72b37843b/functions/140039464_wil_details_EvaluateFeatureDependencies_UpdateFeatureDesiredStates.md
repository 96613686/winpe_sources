# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140039464`
- end: `0x1400394f0`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400392d4`

## callees

- `0x140015e64`
- `0x140039464`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 *result; // rax
  __int64 *v1; // rdx
  int v2; // r9d
  unsigned int v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding((__int64 *)Feature_SFS_CD_BugFixes_2409__private_descriptor);
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
0x140039464  sub     rsp, 28h
0x140039468  lea     rcx, Feature_SFS_CD_BugFixes_2409__private_descriptor
0x14003946f  mov     [rsp+28h+arg_0], 0
0x140039478  call    wil_details_FeatureDescriptors_SkipPadding
0x14003947d  mov     rdx, rax
0x140039480  test    rax, rax
0x140039483  jz      short loc_1400394EA
0x140039485  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14003948a  mov     rcx, [rdx]
0x14003948d  mov     r8d, [rcx]
0x140039490  bt      r8d, 9
0x140039495  jnb     short loc_1400394D9
0x140039497  mov     ecx, r8d
0x14003949a  and     ecx, 180h
0x1400394a0  jnz     short loc_1400394AC
0x1400394a2  xor     eax, eax
0x1400394a4  cmp     [rdx+1Fh], al
0x1400394a7  setnz   al
0x1400394aa  jmp     short loc_1400394B7
0x1400394ac  xor     eax, eax
0x1400394ae  cmp     ecx, 100h
0x1400394b4  setz    al
0x1400394b7  shr     r8d, 6
0x1400394bb  and     r8d, 1
0x1400394bf  xor     r8d, eax
0x1400394c2  mov     eax, r9d
0x1400394c5  shl     r8d, 6
0x1400394c9  and     eax, 0FFFFFFBFh
0x1400394cc  mov     r9d, r8d
0x1400394cf  or      r9d, eax
0x1400394d2  mov     rax, [rdx]
0x1400394d5  lock xor [rax], r9d
0x1400394d9  lea     rcx, [rdx+38h]
0x1400394dd  call    wil_details_FeatureDescriptors_SkipPadding
0x1400394e2  mov     rdx, rax
0x1400394e5  test    rax, rax
0x1400394e8  jnz     short loc_14003948A
0x1400394ea  add     rsp, 28h
0x1400394ee  retn
```

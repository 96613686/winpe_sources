# wil_details_EvaluateFeatureDependencies

- ea: `0x140010790`
- end: `0x14001089f`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `271`
- prototype: `void()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140010a80`
- `0x140012a94`

## callees

- `0x140010790`
- `0x1400108e4`

## pseudocode

```c
void wil_details_EvaluateFeatureDependencies()
{
  __int64 **v0; // rbx
  volatile signed __int32 **v1; // rcx
  unsigned int v2; // r9d
  volatile unsigned __int32 v3; // edx
  BOOL v4; // eax
  __int64 v5; // [rsp+30h] [rbp+8h]

  v0 = wil_details_featureDescriptors_a;
  v1 = (volatile signed __int32 **)wil_details_featureDescriptors_a;
  if ( wil_details_featureDescriptors_a < (__int64 **)wil_details_featureDescriptors_z )
  {
    while ( !*v1 )
    {
      if ( ++v1 >= (volatile signed __int32 **)wil_details_featureDescriptors_z )
        goto LABEL_21;
    }
    if ( !v1 )
      goto LABEL_21;
    v2 = 0;
    do
    {
      v3 = **v1;
      if ( (v3 & 0x200) != 0 )
      {
        if ( (v3 & 0x180) != 0 )
          v4 = (**v1 & 0x180) == 256;
        else
          v4 = *((_BYTE *)v1 + 31) != 0;
        v2 = v2 & 0xFFFFFFBF | ((v4 ^ (v3 >> 6) & 1) << 6);
        _InterlockedXor(*v1, v2);
      }
      for ( v1 += 7; ; ++v1 )
      {
        if ( v1 >= (volatile signed __int32 **)wil_details_featureDescriptors_z )
          goto LABEL_21;
        if ( *v1 )
          break;
      }
    }
    while ( v1 );
LABEL_21:
    while ( v0 < (__int64 **)wil_details_featureDescriptors_z )
    {
      if ( *v0 )
      {
LABEL_30:
        if ( v0 )
        {
          v5 = *(unsigned int *)*v0;
          if ( (v5 & 0x200) != 0 )
            wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(*v0, v5, v0);
          for ( v0 += 7; v0 < (__int64 **)wil_details_featureDescriptors_z; ++v0 )
          {
            if ( *v0 )
              goto LABEL_30;
          }
        }
        return;
      }
      ++v0;
    }
  }
}

```

## disassembly

```asm
0x140010790  mov     [rsp+arg_8], rbx
0x140010795  push    rsi
0x140010796  sub     rsp, 20h
0x14001079a  lea     rbx, wil_details_featureDescriptors_a
0x1400107a1  mov     [rsp+28h+arg_0], 0
0x1400107aa  lea     rsi, wil_details_featureDescriptors_z
0x1400107b1  mov     rcx, rbx
0x1400107b4  cmp     rbx, rsi
0x1400107b7  jnb     loc_140010893
0x1400107bd  cmp     qword ptr [rcx], 0
0x1400107c1  jnz     short loc_1400107CE
0x1400107c3  add     rcx, 8
0x1400107c7  cmp     rcx, rsi
0x1400107ca  jb      short loc_1400107BD
0x1400107cc  jmp     short loc_14001084B
0x1400107ce  test    rcx, rcx
0x1400107d1  jz      short loc_14001084B
0x1400107d3  mov     r9d, dword ptr [rsp+28h+arg_0]
0x1400107d8  mov     rax, [rcx]
0x1400107db  mov     edx, [rax]
0x1400107dd  bt      edx, 9
0x1400107e1  jnb     short loc_140010823
0x1400107e3  mov     r8d, edx
0x1400107e6  and     r8d, 180h
0x1400107ed  jnz     short loc_1400107F9
0x1400107ef  xor     eax, eax
0x1400107f1  cmp     [rcx+1Fh], al
0x1400107f4  setnz   al
0x1400107f7  jmp     short loc_140010805
0x1400107f9  xor     eax, eax
0x1400107fb  cmp     r8d, 100h
0x140010802  setz    al
0x140010805  shr     edx, 6
0x140010808  and     edx, 1
0x14001080b  xor     edx, eax
0x14001080d  mov     eax, r9d
0x140010810  shl     edx, 6
0x140010813  and     eax, 0FFFFFFBFh
0x140010816  mov     r9d, edx
0x140010819  or      r9d, eax
0x14001081c  mov     rax, [rcx]
0x14001081f  lock xor [rax], r9d
0x140010823  add     rcx, 38h ; '8'
0x140010827  jmp     short loc_140010833
0x140010829  cmp     qword ptr [rcx], 0
0x14001082d  jnz     short loc_14001083A
0x14001082f  add     rcx, 8
0x140010833  cmp     rcx, rsi
0x140010836  jb      short loc_140010829
0x140010838  jmp     short loc_14001084B
0x14001083a  test    rcx, rcx
0x14001083d  jnz     short loc_1400107D8
0x14001083f  jmp     short loc_14001084B
0x140010841  cmp     qword ptr [rbx], 0
0x140010845  jnz     short loc_14001088E
0x140010847  add     rbx, 8
0x14001084b  cmp     rbx, rsi
0x14001084e  jb      short loc_140010841
0x140010850  jmp     short loc_140010893
0x140010852  mov     rcx, [rbx]
0x140010855  mov     [rsp+28h+arg_0], 0
0x14001085e  mov     eax, [rcx]
0x140010860  mov     dword ptr [rsp+28h+arg_0], eax
0x140010864  bt      eax, 9
0x140010868  jnb     short loc_140010877
0x14001086a  mov     rdx, [rsp+28h+arg_0]
0x14001086f  mov     r8, rbx
0x140010872  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140010877  add     rbx, 38h ; '8'
0x14001087b  jmp     short loc_140010887
0x14001087d  cmp     qword ptr [rbx], 0
0x140010881  jnz     short loc_14001088E
0x140010883  add     rbx, 8
0x140010887  cmp     rbx, rsi
0x14001088a  jb      short loc_14001087D
0x14001088c  jmp     short loc_140010893
0x14001088e  test    rbx, rbx
0x140010891  jnz     short loc_140010852
0x140010893  mov     rbx, [rsp+28h+arg_8]
0x140010898  add     rsp, 20h
0x14001089c  pop     rsi
0x14001089d  retn
```

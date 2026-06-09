# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14005e24c`
- end: `0x14005e32b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14005e18c`

## callees

- `0x140012d40`
- `0x140040a30`
- `0x140054eec`
- `0x14005e24c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005e2ad`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005e2ad`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  _UNKNOWN **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v2 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v2 = (_QWORD **)result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *(_BYTE *)(result + 29) || *(_BYTE *)(result + 30) )
    {
      v3 = -1073741275;
    }
    else
    {
      v3 = RtlQueryFeatureConfiguration(
             *(unsigned int *)(result + 24),
             (unsigned __int8)(*(_BYTE *)(result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v3 == -2147483614 )
      {
        v5 = 518;
        v4 = 518;
        do
        {
          **v2 = v4;
          result = wil_details_FeatureDescriptors_SkipPadding(v2 + 7);
          v2 = (_QWORD **)result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v3, &v7, &v5);
    **v2 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x14005e24c  push    rbx
0x14005e24e  sub     rsp, 50h
0x14005e252  mov     rax, cs:__security_cookie
0x14005e259  xor     rax, rsp
0x14005e25c  mov     [rsp+58h+var_18], rax
0x14005e261  lea     rcx, wil_details_featureDescriptors_a
0x14005e268  call    wil_details_FeatureDescriptors_SkipPadding
0x14005e26d  mov     rbx, rax
0x14005e270  test    rax, rax
0x14005e273  jz      short loc_14005E2ED
0x14005e275  xor     eax, eax
0x14005e277  mov     [rsp+58h+var_28], rax
0x14005e27c  mov     [rsp+58h+var_20], eax
0x14005e280  mov     [rsp+58h+var_30], rax
0x14005e285  mov     [rsp+58h+var_38], rax
0x14005e28a  cmp     [rbx+1Dh], al
0x14005e28d  jnz     short loc_14005E301
0x14005e28f  cmp     [rbx+1Eh], al
0x14005e292  jnz     short loc_14005E301
0x14005e294  mov     al, [rbx+1Ch]
0x14005e297  lea     r9, [rsp+58h+var_28]
0x14005e29c  mov     ecx, [rbx+18h]
0x14005e29f  lea     r8, [rsp+58h+var_30]
0x14005e2a4  xor     edx, edx
0x14005e2a6  sub     al, 2
0x14005e2a8  cmp     al, 1
0x14005e2aa  setnbe  dl
0x14005e2ad  call    cs:__imp_RtlQueryFeatureConfiguration
0x14005e2b4  nop     dword ptr [rax+rax+00h]
0x14005e2b9  cmp     eax, 80000022h
0x14005e2be  jnz     short loc_14005E306
0x14005e2c0  mov     [rsp+58h+var_38], 0
0x14005e2c9  mov     dword ptr [rsp+58h+var_38], 206h
0x14005e2d1  mov     rdx, [rsp+58h+var_38]
0x14005e2d6  mov     rax, [rbx]
0x14005e2d9  lea     rcx, [rbx+38h]
0x14005e2dd  mov     [rax], rdx
0x14005e2e0  call    wil_details_FeatureDescriptors_SkipPadding
0x14005e2e5  mov     rbx, rax
0x14005e2e8  test    rax, rax
0x14005e2eb  jnz     short loc_14005E2D6
0x14005e2ed  mov     rcx, [rsp+58h+var_18]
0x14005e2f2  xor     rcx, rsp; StackCookie
0x14005e2f5  call    __security_check_cookie
0x14005e2fa  add     rsp, 50h
0x14005e2fe  pop     rbx
0x14005e2ff  retn
0x14005e301  mov     eax, 0C0000225h
0x14005e306  lea     r8, [rsp+58h+var_38]
0x14005e30b  mov     ecx, eax
0x14005e30d  lea     rdx, [rsp+58h+var_28]
0x14005e312  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14005e317  mov     rcx, [rbx]
0x14005e31a  mov     rax, [rsp+58h+var_38]
0x14005e31f  mov     [rcx], rax
0x14005e322  lea     rcx, [rbx+38h]
0x14005e326  jmp     loc_14005E268
```

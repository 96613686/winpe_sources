# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14005f6ec`
- end: `0x14005f7d1`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14005f62c`

## callees

- `0x140009af4`
- `0x14001b960`
- `0x14003d33c`
- `0x14005f6ec`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005f745`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005f745`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  _QWORD **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (_QWORD **)result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *(_BYTE *)(result + 29) || *(_BYTE *)(result + 30) )
    {
      v1 = -1073741275;
    }
    else
    {
      v1 = RtlQueryFeatureConfiguration(
             *(unsigned int *)(result + 24),
             (unsigned __int8)(*(_BYTE *)(result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v1 == -2147483614 )
      {
        v5 = 518;
        v2 = 518;
        do
        {
          **v4 = v2;
          result = wil_details_FeatureDescriptors_SkipPadding(v4 + 7);
          v4 = (_QWORD **)result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v1, &v7, &v5);
    **v4 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x14005f6ec  push    rbx
0x14005f6ee  sub     rsp, 50h
0x14005f6f2  mov     rax, cs:__security_cookie
0x14005f6f9  xor     rax, rsp
0x14005f6fc  mov     [rsp+58h+var_18], rax
0x14005f701  lea     rcx, wil_details_featureDescriptors_a
0x14005f708  jmp     loc_14005F7BE
0x14005f70d  xor     eax, eax
0x14005f70f  mov     [rsp+58h+var_28], rax
0x14005f714  mov     [rsp+58h+var_20], eax
0x14005f718  mov     [rsp+58h+var_30], rax
0x14005f71d  mov     [rsp+58h+var_38], rax
0x14005f722  cmp     [rbx+1Dh], al
0x14005f725  jnz     short loc_14005F799
0x14005f727  cmp     [rbx+1Eh], al
0x14005f72a  jnz     short loc_14005F799
0x14005f72c  mov     al, [rbx+1Ch]
0x14005f72f  lea     r9, [rsp+58h+var_28]
0x14005f734  mov     ecx, [rbx+18h]
0x14005f737  lea     r8, [rsp+58h+var_30]
0x14005f73c  xor     edx, edx
0x14005f73e  sub     al, 2
0x14005f740  cmp     al, 1
0x14005f742  setnbe  dl
0x14005f745  call    cs:__imp_RtlQueryFeatureConfiguration
0x14005f74c  nop     dword ptr [rax+rax+00h]
0x14005f751  cmp     eax, 80000022h
0x14005f756  jnz     short loc_14005F79E
0x14005f758  mov     [rsp+58h+var_38], 0
0x14005f761  mov     dword ptr [rsp+58h+var_38], 206h
0x14005f769  mov     rdx, [rsp+58h+var_38]
0x14005f76e  mov     rax, [rbx]
0x14005f771  lea     rcx, [rbx+38h]
0x14005f775  mov     [rax], rdx
0x14005f778  call    wil_details_FeatureDescriptors_SkipPadding
0x14005f77d  mov     rbx, rax
0x14005f780  test    rax, rax
0x14005f783  jnz     short loc_14005F76E
0x14005f785  mov     rcx, [rsp+58h+var_18]
0x14005f78a  xor     rcx, rsp; StackCookie
0x14005f78d  call    __security_check_cookie
0x14005f792  add     rsp, 50h
0x14005f796  pop     rbx
0x14005f797  retn
0x14005f799  mov     eax, 0C0000225h
0x14005f79e  lea     r8, [rsp+58h+var_38]
0x14005f7a3  mov     ecx, eax
0x14005f7a5  lea     rdx, [rsp+58h+var_28]
0x14005f7aa  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14005f7af  mov     rcx, [rbx]
0x14005f7b2  mov     rax, [rsp+58h+var_38]
0x14005f7b7  mov     [rcx], rax
0x14005f7ba  lea     rcx, [rbx+38h]
0x14005f7be  call    wil_details_FeatureDescriptors_SkipPadding
0x14005f7c3  mov     rbx, rax
0x14005f7c6  test    rax, rax
0x14005f7c9  jnz     loc_14005F70D
0x14005f7cf  jmp     short loc_14005F785
```

# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14003a2fc`
- end: `0x14003a3e1`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14003a23c`

## callees

- `0x140008114`
- `0x14001cdf0`
- `0x14003675c`
- `0x14003a2fc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14003a355`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14003a355`

## pseudocode

```c
__int64 *wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 *result; // rax
  __int64 *v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = v4 + 7 )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *((_BYTE *)result + 29) || *((_BYTE *)result + 30) )
    {
      v1 = -1073741275;
    }
    else
    {
      v1 = RtlQueryFeatureConfiguration(
             *((unsigned int *)result + 6),
             (unsigned __int8)(*((_BYTE *)result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v1 == -2147483614 )
      {
        v5 = 518;
        v2 = 518;
        do
        {
          *(_QWORD *)*v4 = v2;
          result = wil_details_FeatureDescriptors_SkipPadding(v4 + 7);
          v4 = result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v1, &v7, &v5);
    *(_QWORD *)*v4 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x14003a2fc  push    rbx
0x14003a2fe  sub     rsp, 50h
0x14003a302  mov     rax, cs:__security_cookie
0x14003a309  xor     rax, rsp
0x14003a30c  mov     [rsp+58h+var_18], rax
0x14003a311  lea     rcx, wil_details_featureDescriptors_a
0x14003a318  jmp     loc_14003A3CE
0x14003a31d  xor     eax, eax
0x14003a31f  mov     [rsp+58h+var_28], rax
0x14003a324  mov     [rsp+58h+var_20], eax
0x14003a328  mov     [rsp+58h+var_30], rax
0x14003a32d  mov     [rsp+58h+var_38], rax
0x14003a332  cmp     [rbx+1Dh], al
0x14003a335  jnz     short loc_14003A3A9
0x14003a337  cmp     [rbx+1Eh], al
0x14003a33a  jnz     short loc_14003A3A9
0x14003a33c  mov     al, [rbx+1Ch]
0x14003a33f  lea     r9, [rsp+58h+var_28]
0x14003a344  mov     ecx, [rbx+18h]
0x14003a347  lea     r8, [rsp+58h+var_30]
0x14003a34c  xor     edx, edx
0x14003a34e  sub     al, 2
0x14003a350  cmp     al, 1
0x14003a352  setnbe  dl
0x14003a355  call    cs:__imp_RtlQueryFeatureConfiguration
0x14003a35c  nop     dword ptr [rax+rax+00h]
0x14003a361  cmp     eax, 80000022h
0x14003a366  jnz     short loc_14003A3AE
0x14003a368  mov     [rsp+58h+var_38], 0
0x14003a371  mov     dword ptr [rsp+58h+var_38], 206h
0x14003a379  mov     rdx, [rsp+58h+var_38]
0x14003a37e  mov     rax, [rbx]
0x14003a381  lea     rcx, [rbx+38h]
0x14003a385  mov     [rax], rdx
0x14003a388  call    wil_details_FeatureDescriptors_SkipPadding
0x14003a38d  mov     rbx, rax
0x14003a390  test    rax, rax
0x14003a393  jnz     short loc_14003A37E
0x14003a395  mov     rcx, [rsp+58h+var_18]
0x14003a39a  xor     rcx, rsp; StackCookie
0x14003a39d  call    __security_check_cookie
0x14003a3a2  add     rsp, 50h
0x14003a3a6  pop     rbx
0x14003a3a7  retn
0x14003a3a9  mov     eax, 0C0000225h
0x14003a3ae  lea     r8, [rsp+58h+var_38]
0x14003a3b3  mov     ecx, eax
0x14003a3b5  lea     rdx, [rsp+58h+var_28]
0x14003a3ba  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14003a3bf  mov     rcx, [rbx]
0x14003a3c2  mov     rax, [rsp+58h+var_38]
0x14003a3c7  mov     [rcx], rax
0x14003a3ca  lea     rcx, [rbx+38h]
0x14003a3ce  call    wil_details_FeatureDescriptors_SkipPadding
0x14003a3d3  mov     rbx, rax
0x14003a3d6  test    rax, rax
0x14003a3d9  jnz     loc_14003A31D
0x14003a3df  jmp     short loc_14003A395
```

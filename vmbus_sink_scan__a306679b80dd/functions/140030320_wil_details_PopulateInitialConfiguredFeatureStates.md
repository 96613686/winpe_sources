# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140030320`
- end: `0x1400303ff`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140030260`

## callees

- `0x140003944`
- `0x140017000`
- `0x1400278ec`
- `0x140030320`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140030381`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140030381`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v2 + 7) )
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
0x140030320  push    rbx
0x140030322  sub     rsp, 50h
0x140030326  mov     rax, cs:__security_cookie
0x14003032d  xor     rax, rsp
0x140030330  mov     [rsp+58h+var_18], rax
0x140030335  lea     rcx, wil_details_featureDescriptors_a
0x14003033c  call    wil_details_FeatureDescriptors_SkipPadding
0x140030341  mov     rbx, rax
0x140030344  test    rax, rax
0x140030347  jz      short loc_1400303C1
0x140030349  xor     eax, eax
0x14003034b  mov     [rsp+58h+var_28], rax
0x140030350  mov     [rsp+58h+var_20], eax
0x140030354  mov     [rsp+58h+var_30], rax
0x140030359  mov     [rsp+58h+var_38], rax
0x14003035e  cmp     [rbx+1Dh], al
0x140030361  jnz     short loc_1400303D5
0x140030363  cmp     [rbx+1Eh], al
0x140030366  jnz     short loc_1400303D5
0x140030368  mov     al, [rbx+1Ch]
0x14003036b  lea     r9, [rsp+58h+var_28]
0x140030370  mov     ecx, [rbx+18h]
0x140030373  lea     r8, [rsp+58h+var_30]
0x140030378  xor     edx, edx
0x14003037a  sub     al, 2
0x14003037c  cmp     al, 1
0x14003037e  setnbe  dl
0x140030381  call    cs:__imp_RtlQueryFeatureConfiguration
0x140030388  nop     dword ptr [rax+rax+00h]
0x14003038d  cmp     eax, 80000022h
0x140030392  jnz     short loc_1400303DA
0x140030394  mov     [rsp+58h+var_38], 0
0x14003039d  mov     dword ptr [rsp+58h+var_38], 206h
0x1400303a5  mov     rdx, [rsp+58h+var_38]
0x1400303aa  mov     rax, [rbx]
0x1400303ad  lea     rcx, [rbx+38h]
0x1400303b1  mov     [rax], rdx
0x1400303b4  call    wil_details_FeatureDescriptors_SkipPadding
0x1400303b9  mov     rbx, rax
0x1400303bc  test    rax, rax
0x1400303bf  jnz     short loc_1400303AA
0x1400303c1  mov     rcx, [rsp+58h+var_18]
0x1400303c6  xor     rcx, rsp; StackCookie
0x1400303c9  call    __security_check_cookie
0x1400303ce  add     rsp, 50h
0x1400303d2  pop     rbx
0x1400303d3  retn
0x1400303d5  mov     eax, 0C0000225h
0x1400303da  lea     r8, [rsp+58h+var_38]
0x1400303df  mov     ecx, eax
0x1400303e1  lea     rdx, [rsp+58h+var_28]
0x1400303e6  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400303eb  mov     rcx, [rbx]
0x1400303ee  mov     rax, [rsp+58h+var_38]
0x1400303f3  mov     [rcx], rax
0x1400303f6  lea     rcx, [rbx+38h]
0x1400303fa  jmp     loc_14003033C
```

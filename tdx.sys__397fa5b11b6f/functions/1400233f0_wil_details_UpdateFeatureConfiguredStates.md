# wil_details_UpdateFeatureConfiguredStates

- ea: `0x1400233f0`
- end: `0x1400234a0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140023350`

## callees

- `0x140014694`
- `0x1400184b0`
- `0x140023068`
- `0x1400233f0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140023440`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140023440`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  __int64 *i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (volatile signed __int32 **)result;
    if ( !result )
      break;
    if ( !*(_BYTE *)(result + 29) && !*(_BYTE *)(result + 30) && !*(_BYTE *)(result + 28) )
    {
      v1 = *(unsigned int *)(result + 24);
      v7 = 0;
      v8 = 0;
      v6 = 0;
      v2 = RtlQueryFeatureConfiguration(v1, 1, &v6, &v7);
      v5 = 0;
      wil_details_BuildFeatureStateCacheFromQueryResults(v2, &v7, &v5);
      _InterlockedXor(*v4, ((unsigned __int16)v5 ^ (unsigned __int16)**v4) & 0xF80);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400233f0  push    rbx
0x1400233f2  sub     rsp, 50h
0x1400233f6  mov     rax, cs:__security_cookie
0x1400233fd  xor     rax, rsp
0x140023400  mov     [rsp+58h+var_18], rax
0x140023405  lea     rcx, wil_details_featureDescriptors_a
0x14002340c  jmp     short loc_14002347F
0x14002340e  cmp     byte ptr [rbx+1Dh], 0
0x140023412  jnz     short loc_14002347B
0x140023414  cmp     byte ptr [rbx+1Eh], 0
0x140023418  jnz     short loc_14002347B
0x14002341a  cmp     byte ptr [rbx+1Ch], 0
0x14002341e  jnz     short loc_14002347B
0x140023420  mov     ecx, [rbx+18h]
0x140023423  lea     r9, [rsp+58h+var_28]
0x140023428  xor     eax, eax
0x14002342a  lea     r8, [rsp+58h+var_30]
0x14002342f  mov     [rsp+58h+var_28], rax
0x140023434  mov     [rsp+58h+var_20], eax
0x140023438  mov     [rsp+58h+var_30], rax
0x14002343d  lea     edx, [rax+1]
0x140023440  call    cs:__imp_RtlQueryFeatureConfiguration
0x140023447  nop     dword ptr [rax+rax+00h]
0x14002344c  lea     r8, [rsp+58h+var_38]
0x140023451  mov     [rsp+58h+var_38], 0
0x14002345a  mov     ecx, eax
0x14002345c  lea     rdx, [rsp+58h+var_28]
0x140023461  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140023466  mov     rcx, [rbx]
0x140023469  mov     edx, [rcx]
0x14002346b  xor     edx, dword ptr [rsp+58h+var_38]
0x14002346f  mov     rax, [rbx]
0x140023472  and     edx, 0F80h
0x140023478  lock xor [rax], edx
0x14002347b  lea     rcx, [rbx+38h]
0x14002347f  call    wil_details_FeatureDescriptors_SkipPadding
0x140023484  mov     rbx, rax
0x140023487  test    rax, rax
0x14002348a  jnz     short loc_14002340E
0x14002348c  mov     rcx, [rsp+58h+var_18]
0x140023491  xor     rcx, rsp; StackCookie
0x140023494  call    __security_check_cookie
0x140023499  add     rsp, 50h
0x14002349d  pop     rbx
0x14002349e  retn
```

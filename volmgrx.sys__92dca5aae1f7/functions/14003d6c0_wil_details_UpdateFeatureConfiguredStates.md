# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14003d6c0`
- end: `0x14003d770`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14003d620`

## callees

- `0x140009af4`
- `0x14001b960`
- `0x14003d33c`
- `0x14003d6c0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14003d710`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14003d710`

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
0x14003d6c0  push    rbx
0x14003d6c2  sub     rsp, 50h
0x14003d6c6  mov     rax, cs:__security_cookie
0x14003d6cd  xor     rax, rsp
0x14003d6d0  mov     [rsp+58h+var_18], rax
0x14003d6d5  lea     rcx, wil_details_featureDescriptors_a
0x14003d6dc  jmp     short loc_14003D74F
0x14003d6de  cmp     byte ptr [rbx+1Dh], 0
0x14003d6e2  jnz     short loc_14003D74B
0x14003d6e4  cmp     byte ptr [rbx+1Eh], 0
0x14003d6e8  jnz     short loc_14003D74B
0x14003d6ea  cmp     byte ptr [rbx+1Ch], 0
0x14003d6ee  jnz     short loc_14003D74B
0x14003d6f0  mov     ecx, [rbx+18h]
0x14003d6f3  lea     r9, [rsp+58h+var_28]
0x14003d6f8  xor     eax, eax
0x14003d6fa  lea     r8, [rsp+58h+var_30]
0x14003d6ff  mov     [rsp+58h+var_28], rax
0x14003d704  mov     [rsp+58h+var_20], eax
0x14003d708  mov     [rsp+58h+var_30], rax
0x14003d70d  lea     edx, [rax+1]
0x14003d710  call    cs:__imp_RtlQueryFeatureConfiguration
0x14003d717  nop     dword ptr [rax+rax+00h]
0x14003d71c  lea     r8, [rsp+58h+var_38]
0x14003d721  mov     [rsp+58h+var_38], 0
0x14003d72a  mov     ecx, eax
0x14003d72c  lea     rdx, [rsp+58h+var_28]
0x14003d731  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14003d736  mov     rcx, [rbx]
0x14003d739  mov     edx, [rcx]
0x14003d73b  xor     edx, dword ptr [rsp+58h+var_38]
0x14003d73f  mov     rax, [rbx]
0x14003d742  and     edx, 0F80h
0x14003d748  lock xor [rax], edx
0x14003d74b  lea     rcx, [rbx+38h]
0x14003d74f  call    wil_details_FeatureDescriptors_SkipPadding
0x14003d754  mov     rbx, rax
0x14003d757  test    rax, rax
0x14003d75a  jnz     short loc_14003D6DE
0x14003d75c  mov     rcx, [rsp+58h+var_18]
0x14003d761  xor     rcx, rsp; StackCookie
0x14003d764  call    __security_check_cookie
0x14003d769  add     rsp, 50h
0x14003d76d  pop     rbx
0x14003d76e  retn
```

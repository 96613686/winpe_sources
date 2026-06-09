# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140025ba0`
- end: `0x140025c50`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140025b00`

## callees

- `0x14000f4cc`
- `0x140011560`
- `0x14002586c`
- `0x140025ba0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140025bf0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140025bf0`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  void *i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = v4 + 7 )
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
0x140025ba0  push    rbx
0x140025ba2  sub     rsp, 50h
0x140025ba6  mov     rax, cs:__security_cookie
0x140025bad  xor     rax, rsp
0x140025bb0  mov     [rsp+58h+var_18], rax
0x140025bb5  lea     rcx, wil_details_featureDescriptors_a
0x140025bbc  jmp     short loc_140025C2F
0x140025bbe  cmp     byte ptr [rbx+1Dh], 0
0x140025bc2  jnz     short loc_140025C2B
0x140025bc4  cmp     byte ptr [rbx+1Eh], 0
0x140025bc8  jnz     short loc_140025C2B
0x140025bca  cmp     byte ptr [rbx+1Ch], 0
0x140025bce  jnz     short loc_140025C2B
0x140025bd0  mov     ecx, [rbx+18h]
0x140025bd3  lea     r9, [rsp+58h+var_28]
0x140025bd8  xor     eax, eax
0x140025bda  lea     r8, [rsp+58h+var_30]
0x140025bdf  mov     [rsp+58h+var_28], rax
0x140025be4  mov     [rsp+58h+var_20], eax
0x140025be8  mov     [rsp+58h+var_30], rax
0x140025bed  lea     edx, [rax+1]
0x140025bf0  call    cs:__imp_RtlQueryFeatureConfiguration
0x140025bf7  nop     dword ptr [rax+rax+00h]
0x140025bfc  lea     r8, [rsp+58h+var_38]
0x140025c01  mov     [rsp+58h+var_38], 0
0x140025c0a  mov     ecx, eax
0x140025c0c  lea     rdx, [rsp+58h+var_28]
0x140025c11  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140025c16  mov     rcx, [rbx]
0x140025c19  mov     edx, [rcx]
0x140025c1b  xor     edx, dword ptr [rsp+58h+var_38]
0x140025c1f  mov     rax, [rbx]
0x140025c22  and     edx, 0F80h
0x140025c28  lock xor [rax], edx
0x140025c2b  lea     rcx, [rbx+38h]
0x140025c2f  call    wil_details_FeatureDescriptors_SkipPadding
0x140025c34  mov     rbx, rax
0x140025c37  test    rax, rax
0x140025c3a  jnz     short loc_140025BBE
0x140025c3c  mov     rcx, [rsp+58h+var_18]
0x140025c41  xor     rcx, rsp; StackCookie
0x140025c44  call    __security_check_cookie
0x140025c49  add     rsp, 50h
0x140025c4d  pop     rbx
0x140025c4e  retn
```

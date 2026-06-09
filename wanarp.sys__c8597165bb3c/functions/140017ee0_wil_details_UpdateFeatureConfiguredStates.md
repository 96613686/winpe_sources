# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140017ee0`
- end: `0x140017f90`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140017e40`

## callees

- `0x140003c5c`
- `0x1400050b0`
- `0x140017b50`
- `0x140017ee0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140017f30`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140017f30`

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
0x140017ee0  push    rbx
0x140017ee2  sub     rsp, 50h
0x140017ee6  mov     rax, cs:__security_cookie
0x140017eed  xor     rax, rsp
0x140017ef0  mov     [rsp+58h+var_18], rax
0x140017ef5  lea     rcx, wil_details_featureDescriptors_a
0x140017efc  jmp     short loc_140017F6F
0x140017efe  cmp     byte ptr [rbx+1Dh], 0
0x140017f02  jnz     short loc_140017F6B
0x140017f04  cmp     byte ptr [rbx+1Eh], 0
0x140017f08  jnz     short loc_140017F6B
0x140017f0a  cmp     byte ptr [rbx+1Ch], 0
0x140017f0e  jnz     short loc_140017F6B
0x140017f10  mov     ecx, [rbx+18h]
0x140017f13  lea     r9, [rsp+58h+var_28]
0x140017f18  xor     eax, eax
0x140017f1a  lea     r8, [rsp+58h+var_30]
0x140017f1f  mov     [rsp+58h+var_28], rax
0x140017f24  mov     [rsp+58h+var_20], eax
0x140017f28  mov     [rsp+58h+var_30], rax
0x140017f2d  lea     edx, [rax+1]
0x140017f30  call    cs:__imp_RtlQueryFeatureConfiguration
0x140017f37  nop     dword ptr [rax+rax+00h]
0x140017f3c  lea     r8, [rsp+58h+var_38]
0x140017f41  mov     [rsp+58h+var_38], 0
0x140017f4a  mov     ecx, eax
0x140017f4c  lea     rdx, [rsp+58h+var_28]
0x140017f51  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140017f56  mov     rcx, [rbx]
0x140017f59  mov     edx, [rcx]
0x140017f5b  xor     edx, dword ptr [rsp+58h+var_38]
0x140017f5f  mov     rax, [rbx]
0x140017f62  and     edx, 0F80h
0x140017f68  lock xor [rax], edx
0x140017f6b  lea     rcx, [rbx+38h]
0x140017f6f  call    wil_details_FeatureDescriptors_SkipPadding
0x140017f74  mov     rbx, rax
0x140017f77  test    rax, rax
0x140017f7a  jnz     short loc_140017EFE
0x140017f7c  mov     rcx, [rsp+58h+var_18]
0x140017f81  xor     rcx, rsp; StackCookie
0x140017f84  call    __security_check_cookie
0x140017f89  add     rsp, 50h
0x140017f8d  pop     rbx
0x140017f8e  retn
```

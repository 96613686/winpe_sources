# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140025bf0`
- end: `0x140025ca0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140025b50`

## callees

- `0x14000f4cc`
- `0x140011560`
- `0x14002586c`
- `0x140025bf0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140025c40`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140025c40`

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
0x140025bf0  push    rbx
0x140025bf2  sub     rsp, 50h
0x140025bf6  mov     rax, cs:__security_cookie
0x140025bfd  xor     rax, rsp
0x140025c00  mov     [rsp+58h+var_18], rax
0x140025c05  lea     rcx, wil_details_featureDescriptors_a
0x140025c0c  jmp     short loc_140025C7F
0x140025c0e  cmp     byte ptr [rbx+1Dh], 0
0x140025c12  jnz     short loc_140025C7B
0x140025c14  cmp     byte ptr [rbx+1Eh], 0
0x140025c18  jnz     short loc_140025C7B
0x140025c1a  cmp     byte ptr [rbx+1Ch], 0
0x140025c1e  jnz     short loc_140025C7B
0x140025c20  mov     ecx, [rbx+18h]
0x140025c23  lea     r9, [rsp+58h+var_28]
0x140025c28  xor     eax, eax
0x140025c2a  lea     r8, [rsp+58h+var_30]
0x140025c2f  mov     [rsp+58h+var_28], rax
0x140025c34  mov     [rsp+58h+var_20], eax
0x140025c38  mov     [rsp+58h+var_30], rax
0x140025c3d  lea     edx, [rax+1]
0x140025c40  call    cs:__imp_RtlQueryFeatureConfiguration
0x140025c47  nop     dword ptr [rax+rax+00h]
0x140025c4c  lea     r8, [rsp+58h+var_38]
0x140025c51  mov     [rsp+58h+var_38], 0
0x140025c5a  mov     ecx, eax
0x140025c5c  lea     rdx, [rsp+58h+var_28]
0x140025c61  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140025c66  mov     rcx, [rbx]
0x140025c69  mov     edx, [rcx]
0x140025c6b  xor     edx, dword ptr [rsp+58h+var_38]
0x140025c6f  mov     rax, [rbx]
0x140025c72  and     edx, 0F80h
0x140025c78  lock xor [rax], edx
0x140025c7b  lea     rcx, [rbx+38h]
0x140025c7f  call    wil_details_FeatureDescriptors_SkipPadding
0x140025c84  mov     rbx, rax
0x140025c87  test    rax, rax
0x140025c8a  jnz     short loc_140025C0E
0x140025c8c  mov     rcx, [rsp+58h+var_18]
0x140025c91  xor     rcx, rsp; StackCookie
0x140025c94  call    __security_check_cookie
0x140025c99  add     rsp, 50h
0x140025c9d  pop     rbx
0x140025c9e  retn
```

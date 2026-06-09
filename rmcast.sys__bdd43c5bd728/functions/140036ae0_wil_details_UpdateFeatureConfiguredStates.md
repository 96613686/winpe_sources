# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140036ae0`
- end: `0x140036b90`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140036a40`

## callees

- `0x140008114`
- `0x14001cdf0`
- `0x14003675c`
- `0x140036ae0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140036b30`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140036b30`

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
0x140036ae0  push    rbx
0x140036ae2  sub     rsp, 50h
0x140036ae6  mov     rax, cs:__security_cookie
0x140036aed  xor     rax, rsp
0x140036af0  mov     [rsp+58h+var_18], rax
0x140036af5  lea     rcx, wil_details_featureDescriptors_a
0x140036afc  jmp     short loc_140036B6F
0x140036afe  cmp     byte ptr [rbx+1Dh], 0
0x140036b02  jnz     short loc_140036B6B
0x140036b04  cmp     byte ptr [rbx+1Eh], 0
0x140036b08  jnz     short loc_140036B6B
0x140036b0a  cmp     byte ptr [rbx+1Ch], 0
0x140036b0e  jnz     short loc_140036B6B
0x140036b10  mov     ecx, [rbx+18h]
0x140036b13  lea     r9, [rsp+58h+var_28]
0x140036b18  xor     eax, eax
0x140036b1a  lea     r8, [rsp+58h+var_30]
0x140036b1f  mov     [rsp+58h+var_28], rax
0x140036b24  mov     [rsp+58h+var_20], eax
0x140036b28  mov     [rsp+58h+var_30], rax
0x140036b2d  lea     edx, [rax+1]
0x140036b30  call    cs:__imp_RtlQueryFeatureConfiguration
0x140036b37  nop     dword ptr [rax+rax+00h]
0x140036b3c  lea     r8, [rsp+58h+var_38]
0x140036b41  mov     [rsp+58h+var_38], 0
0x140036b4a  mov     ecx, eax
0x140036b4c  lea     rdx, [rsp+58h+var_28]
0x140036b51  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140036b56  mov     rcx, [rbx]
0x140036b59  mov     edx, [rcx]
0x140036b5b  xor     edx, dword ptr [rsp+58h+var_38]
0x140036b5f  mov     rax, [rbx]
0x140036b62  and     edx, 0F80h
0x140036b68  lock xor [rax], edx
0x140036b6b  lea     rcx, [rbx+38h]
0x140036b6f  call    wil_details_FeatureDescriptors_SkipPadding
0x140036b74  mov     rbx, rax
0x140036b77  test    rax, rax
0x140036b7a  jnz     short loc_140036AFE
0x140036b7c  mov     rcx, [rsp+58h+var_18]
0x140036b81  xor     rcx, rsp; StackCookie
0x140036b84  call    __security_check_cookie
0x140036b89  add     rsp, 50h
0x140036b8d  pop     rbx
0x140036b8e  retn
```

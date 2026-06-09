# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140027c70`
- end: `0x140027d20`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140027bd0`

## callees

- `0x140003944`
- `0x140017000`
- `0x1400278ec`
- `0x140027c70`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140027cc0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140027cc0`

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
0x140027c70  push    rbx
0x140027c72  sub     rsp, 50h
0x140027c76  mov     rax, cs:__security_cookie
0x140027c7d  xor     rax, rsp
0x140027c80  mov     [rsp+58h+var_18], rax
0x140027c85  lea     rcx, wil_details_featureDescriptors_a
0x140027c8c  jmp     short loc_140027CFF
0x140027c8e  cmp     byte ptr [rbx+1Dh], 0
0x140027c92  jnz     short loc_140027CFB
0x140027c94  cmp     byte ptr [rbx+1Eh], 0
0x140027c98  jnz     short loc_140027CFB
0x140027c9a  cmp     byte ptr [rbx+1Ch], 0
0x140027c9e  jnz     short loc_140027CFB
0x140027ca0  mov     ecx, [rbx+18h]
0x140027ca3  lea     r9, [rsp+58h+var_28]
0x140027ca8  xor     eax, eax
0x140027caa  lea     r8, [rsp+58h+var_30]
0x140027caf  mov     [rsp+58h+var_28], rax
0x140027cb4  mov     [rsp+58h+var_20], eax
0x140027cb8  mov     [rsp+58h+var_30], rax
0x140027cbd  lea     edx, [rax+1]
0x140027cc0  call    cs:__imp_RtlQueryFeatureConfiguration
0x140027cc7  nop     dword ptr [rax+rax+00h]
0x140027ccc  lea     r8, [rsp+58h+var_38]
0x140027cd1  mov     [rsp+58h+var_38], 0
0x140027cda  mov     ecx, eax
0x140027cdc  lea     rdx, [rsp+58h+var_28]
0x140027ce1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140027ce6  mov     rcx, [rbx]
0x140027ce9  mov     edx, [rcx]
0x140027ceb  xor     edx, dword ptr [rsp+58h+var_38]
0x140027cef  mov     rax, [rbx]
0x140027cf2  and     edx, 0F80h
0x140027cf8  lock xor [rax], edx
0x140027cfb  lea     rcx, [rbx+38h]
0x140027cff  call    wil_details_FeatureDescriptors_SkipPadding
0x140027d04  mov     rbx, rax
0x140027d07  test    rax, rax
0x140027d0a  jnz     short loc_140027C8E
0x140027d0c  mov     rcx, [rsp+58h+var_18]
0x140027d11  xor     rcx, rsp; StackCookie
0x140027d14  call    __security_check_cookie
0x140027d19  add     rsp, 50h
0x140027d1d  pop     rbx
0x140027d1e  retn
```

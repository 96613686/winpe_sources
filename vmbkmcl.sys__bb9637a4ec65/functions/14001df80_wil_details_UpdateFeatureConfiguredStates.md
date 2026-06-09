# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14001df80`
- end: `0x14001e030`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14001dee0`

## callees

- `0x140010464`
- `0x140011e90`
- `0x14001dbfc`
- `0x14001df80`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001dfd0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001dfd0`

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
0x14001df80  push    rbx
0x14001df82  sub     rsp, 50h
0x14001df86  mov     rax, cs:__security_cookie
0x14001df8d  xor     rax, rsp
0x14001df90  mov     [rsp+58h+var_18], rax
0x14001df95  lea     rcx, wil_details_featureDescriptors_a
0x14001df9c  jmp     short loc_14001E00F
0x14001df9e  cmp     byte ptr [rbx+1Dh], 0
0x14001dfa2  jnz     short loc_14001E00B
0x14001dfa4  cmp     byte ptr [rbx+1Eh], 0
0x14001dfa8  jnz     short loc_14001E00B
0x14001dfaa  cmp     byte ptr [rbx+1Ch], 0
0x14001dfae  jnz     short loc_14001E00B
0x14001dfb0  mov     ecx, [rbx+18h]
0x14001dfb3  lea     r9, [rsp+58h+var_28]
0x14001dfb8  xor     eax, eax
0x14001dfba  lea     r8, [rsp+58h+var_30]
0x14001dfbf  mov     [rsp+58h+var_28], rax
0x14001dfc4  mov     [rsp+58h+var_20], eax
0x14001dfc8  mov     [rsp+58h+var_30], rax
0x14001dfcd  lea     edx, [rax+1]
0x14001dfd0  call    cs:__imp_RtlQueryFeatureConfiguration
0x14001dfd7  nop     dword ptr [rax+rax+00h]
0x14001dfdc  lea     r8, [rsp+58h+var_38]
0x14001dfe1  mov     [rsp+58h+var_38], 0
0x14001dfea  mov     ecx, eax
0x14001dfec  lea     rdx, [rsp+58h+var_28]
0x14001dff1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14001dff6  mov     rcx, [rbx]
0x14001dff9  mov     edx, [rcx]
0x14001dffb  xor     edx, dword ptr [rsp+58h+var_38]
0x14001dfff  mov     rax, [rbx]
0x14001e002  and     edx, 0F80h
0x14001e008  lock xor [rax], edx
0x14001e00b  lea     rcx, [rbx+38h]
0x14001e00f  call    wil_details_FeatureDescriptors_SkipPadding
0x14001e014  mov     rbx, rax
0x14001e017  test    rax, rax
0x14001e01a  jnz     short loc_14001DF9E
0x14001e01c  mov     rcx, [rsp+58h+var_18]
0x14001e021  xor     rcx, rsp; StackCookie
0x14001e024  call    __security_check_cookie
0x14001e029  add     rsp, 50h
0x14001e02d  pop     rbx
0x14001e02e  retn
```

# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140036a90`
- end: `0x140036b40`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1400369f0`

## callees

- `0x140008114`
- `0x14001cdf0`
- `0x14003675c`
- `0x140036a90`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140036ae0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140036ae0`

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
0x140036a90  push    rbx
0x140036a92  sub     rsp, 50h
0x140036a96  mov     rax, cs:__security_cookie
0x140036a9d  xor     rax, rsp
0x140036aa0  mov     [rsp+58h+var_18], rax
0x140036aa5  lea     rcx, wil_details_featureDescriptors_a
0x140036aac  jmp     short loc_140036B1F
0x140036aae  cmp     byte ptr [rbx+1Dh], 0
0x140036ab2  jnz     short loc_140036B1B
0x140036ab4  cmp     byte ptr [rbx+1Eh], 0
0x140036ab8  jnz     short loc_140036B1B
0x140036aba  cmp     byte ptr [rbx+1Ch], 0
0x140036abe  jnz     short loc_140036B1B
0x140036ac0  mov     ecx, [rbx+18h]
0x140036ac3  lea     r9, [rsp+58h+var_28]
0x140036ac8  xor     eax, eax
0x140036aca  lea     r8, [rsp+58h+var_30]
0x140036acf  mov     [rsp+58h+var_28], rax
0x140036ad4  mov     [rsp+58h+var_20], eax
0x140036ad8  mov     [rsp+58h+var_30], rax
0x140036add  lea     edx, [rax+1]
0x140036ae0  call    cs:__imp_RtlQueryFeatureConfiguration
0x140036ae7  nop     dword ptr [rax+rax+00h]
0x140036aec  lea     r8, [rsp+58h+var_38]
0x140036af1  mov     [rsp+58h+var_38], 0
0x140036afa  mov     ecx, eax
0x140036afc  lea     rdx, [rsp+58h+var_28]
0x140036b01  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140036b06  mov     rcx, [rbx]
0x140036b09  mov     edx, [rcx]
0x140036b0b  xor     edx, dword ptr [rsp+58h+var_38]
0x140036b0f  mov     rax, [rbx]
0x140036b12  and     edx, 0F80h
0x140036b18  lock xor [rax], edx
0x140036b1b  lea     rcx, [rbx+38h]
0x140036b1f  call    wil_details_FeatureDescriptors_SkipPadding
0x140036b24  mov     rbx, rax
0x140036b27  test    rax, rax
0x140036b2a  jnz     short loc_140036AAE
0x140036b2c  mov     rcx, [rsp+58h+var_18]
0x140036b31  xor     rcx, rsp; StackCookie
0x140036b34  call    __security_check_cookie
0x140036b39  add     rsp, 50h
0x140036b3d  pop     rbx
0x140036b3e  retn
```

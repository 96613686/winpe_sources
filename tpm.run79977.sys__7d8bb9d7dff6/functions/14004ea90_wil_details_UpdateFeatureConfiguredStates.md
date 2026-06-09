# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14004ea90`
- end: `0x14004eb40`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14004e9f0`

## callees

- `0x14001e658`
- `0x140039740`
- `0x14004e710`
- `0x14004ea90`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14004eae0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14004eae0`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  int **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
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
0x14004ea90  push    rbx
0x14004ea92  sub     rsp, 50h
0x14004ea96  mov     rax, cs:__security_cookie
0x14004ea9d  xor     rax, rsp
0x14004eaa0  mov     [rsp+58h+var_18], rax
0x14004eaa5  lea     rcx, wil_details_featureDescriptors_a
0x14004eaac  jmp     short loc_14004EB1F
0x14004eaae  cmp     byte ptr [rbx+1Dh], 0
0x14004eab2  jnz     short loc_14004EB1B
0x14004eab4  cmp     byte ptr [rbx+1Eh], 0
0x14004eab8  jnz     short loc_14004EB1B
0x14004eaba  cmp     byte ptr [rbx+1Ch], 0
0x14004eabe  jnz     short loc_14004EB1B
0x14004eac0  mov     ecx, [rbx+18h]
0x14004eac3  lea     r9, [rsp+58h+var_28]
0x14004eac8  xor     eax, eax
0x14004eaca  lea     r8, [rsp+58h+var_30]
0x14004eacf  mov     [rsp+58h+var_28], rax
0x14004ead4  mov     [rsp+58h+var_20], eax
0x14004ead8  mov     [rsp+58h+var_30], rax
0x14004eadd  lea     edx, [rax+1]
0x14004eae0  call    cs:__imp_RtlQueryFeatureConfiguration
0x14004eae7  nop     dword ptr [rax+rax+00h]
0x14004eaec  lea     r8, [rsp+58h+var_38]
0x14004eaf1  mov     [rsp+58h+var_38], 0
0x14004eafa  mov     ecx, eax
0x14004eafc  lea     rdx, [rsp+58h+var_28]
0x14004eb01  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14004eb06  mov     rcx, [rbx]
0x14004eb09  mov     edx, [rcx]
0x14004eb0b  xor     edx, dword ptr [rsp+58h+var_38]
0x14004eb0f  mov     rax, [rbx]
0x14004eb12  and     edx, 0F80h
0x14004eb18  lock xor [rax], edx
0x14004eb1b  lea     rcx, [rbx+38h]
0x14004eb1f  call    wil_details_FeatureDescriptors_SkipPadding
0x14004eb24  mov     rbx, rax
0x14004eb27  test    rax, rax
0x14004eb2a  jnz     short loc_14004EAAE
0x14004eb2c  mov     rcx, [rsp+58h+var_18]
0x14004eb31  xor     rcx, rsp; StackCookie
0x14004eb34  call    __security_check_cookie
0x14004eb39  add     rsp, 50h
0x14004eb3d  pop     rbx
0x14004eb3e  retn
```

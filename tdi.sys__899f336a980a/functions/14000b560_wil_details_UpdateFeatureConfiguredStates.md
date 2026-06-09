# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14000b560`
- end: `0x14000b610`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14000b4c0`

## callees

- `0x140004f0c`
- `0x1400054b0`
- `0x14000b1d8`
- `0x14000b560`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000b5b0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000b5b0`

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
0x14000b560  push    rbx
0x14000b562  sub     rsp, 50h
0x14000b566  mov     rax, cs:__security_cookie
0x14000b56d  xor     rax, rsp
0x14000b570  mov     [rsp+58h+var_18], rax
0x14000b575  lea     rcx, wil_details_featureDescriptors_a
0x14000b57c  jmp     short loc_14000B5EF
0x14000b57e  cmp     byte ptr [rbx+1Dh], 0
0x14000b582  jnz     short loc_14000B5EB
0x14000b584  cmp     byte ptr [rbx+1Eh], 0
0x14000b588  jnz     short loc_14000B5EB
0x14000b58a  cmp     byte ptr [rbx+1Ch], 0
0x14000b58e  jnz     short loc_14000B5EB
0x14000b590  mov     ecx, [rbx+18h]
0x14000b593  lea     r9, [rsp+58h+var_28]
0x14000b598  xor     eax, eax
0x14000b59a  lea     r8, [rsp+58h+var_30]
0x14000b59f  mov     [rsp+58h+var_28], rax
0x14000b5a4  mov     [rsp+58h+var_20], eax
0x14000b5a8  mov     [rsp+58h+var_30], rax
0x14000b5ad  lea     edx, [rax+1]
0x14000b5b0  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000b5b7  nop     dword ptr [rax+rax+00h]
0x14000b5bc  lea     r8, [rsp+58h+var_38]
0x14000b5c1  mov     [rsp+58h+var_38], 0
0x14000b5ca  mov     ecx, eax
0x14000b5cc  lea     rdx, [rsp+58h+var_28]
0x14000b5d1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14000b5d6  mov     rcx, [rbx]
0x14000b5d9  mov     edx, [rcx]
0x14000b5db  xor     edx, dword ptr [rsp+58h+var_38]
0x14000b5df  mov     rax, [rbx]
0x14000b5e2  and     edx, 0F80h
0x14000b5e8  lock xor [rax], edx
0x14000b5eb  lea     rcx, [rbx+38h]
0x14000b5ef  call    wil_details_FeatureDescriptors_SkipPadding
0x14000b5f4  mov     rbx, rax
0x14000b5f7  test    rax, rax
0x14000b5fa  jnz     short loc_14000B57E
0x14000b5fc  mov     rcx, [rsp+58h+var_18]
0x14000b601  xor     rcx, rsp; StackCookie
0x14000b604  call    __security_check_cookie
0x14000b609  add     rsp, 50h
0x14000b60d  pop     rbx
0x14000b60e  retn
```

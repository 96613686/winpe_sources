# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140013c40`
- end: `0x140013cf0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140013ba0`

## callees

- `0x1400084a4`
- `0x140008d20`
- `0x14001390c`
- `0x140013c40`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140013c90`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140013c90`

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
0x140013c40  push    rbx
0x140013c42  sub     rsp, 50h
0x140013c46  mov     rax, cs:__security_cookie
0x140013c4d  xor     rax, rsp
0x140013c50  mov     [rsp+58h+var_18], rax
0x140013c55  lea     rcx, wil_details_featureDescriptors_a
0x140013c5c  jmp     short loc_140013CCF
0x140013c5e  cmp     byte ptr [rbx+1Dh], 0
0x140013c62  jnz     short loc_140013CCB
0x140013c64  cmp     byte ptr [rbx+1Eh], 0
0x140013c68  jnz     short loc_140013CCB
0x140013c6a  cmp     byte ptr [rbx+1Ch], 0
0x140013c6e  jnz     short loc_140013CCB
0x140013c70  mov     ecx, [rbx+18h]
0x140013c73  lea     r9, [rsp+58h+var_28]
0x140013c78  xor     eax, eax
0x140013c7a  lea     r8, [rsp+58h+var_30]
0x140013c7f  mov     [rsp+58h+var_28], rax
0x140013c84  mov     [rsp+58h+var_20], eax
0x140013c88  mov     [rsp+58h+var_30], rax
0x140013c8d  lea     edx, [rax+1]
0x140013c90  call    cs:__imp_RtlQueryFeatureConfiguration
0x140013c97  nop     dword ptr [rax+rax+00h]
0x140013c9c  lea     r8, [rsp+58h+var_38]
0x140013ca1  mov     [rsp+58h+var_38], 0
0x140013caa  mov     ecx, eax
0x140013cac  lea     rdx, [rsp+58h+var_28]
0x140013cb1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140013cb6  mov     rcx, [rbx]
0x140013cb9  mov     edx, [rcx]
0x140013cbb  xor     edx, dword ptr [rsp+58h+var_38]
0x140013cbf  mov     rax, [rbx]
0x140013cc2  and     edx, 0F80h
0x140013cc8  lock xor [rax], edx
0x140013ccb  lea     rcx, [rbx+38h]
0x140013ccf  call    wil_details_FeatureDescriptors_SkipPadding
0x140013cd4  mov     rbx, rax
0x140013cd7  test    rax, rax
0x140013cda  jnz     short loc_140013C5E
0x140013cdc  mov     rcx, [rsp+58h+var_18]
0x140013ce1  xor     rcx, rsp; StackCookie
0x140013ce4  call    __security_check_cookie
0x140013ce9  add     rsp, 50h
0x140013ced  pop     rbx
0x140013cee  retn
```

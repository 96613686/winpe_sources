# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140027c20`
- end: `0x140027cd0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140027b80`

## callees

- `0x140003944`
- `0x140017000`
- `0x1400278ec`
- `0x140027c20`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140027c70`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140027c70`

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
0x140027c20  push    rbx
0x140027c22  sub     rsp, 50h
0x140027c26  mov     rax, cs:__security_cookie
0x140027c2d  xor     rax, rsp
0x140027c30  mov     [rsp+58h+var_18], rax
0x140027c35  lea     rcx, wil_details_featureDescriptors_a
0x140027c3c  jmp     short loc_140027CAF
0x140027c3e  cmp     byte ptr [rbx+1Dh], 0
0x140027c42  jnz     short loc_140027CAB
0x140027c44  cmp     byte ptr [rbx+1Eh], 0
0x140027c48  jnz     short loc_140027CAB
0x140027c4a  cmp     byte ptr [rbx+1Ch], 0
0x140027c4e  jnz     short loc_140027CAB
0x140027c50  mov     ecx, [rbx+18h]
0x140027c53  lea     r9, [rsp+58h+var_28]
0x140027c58  xor     eax, eax
0x140027c5a  lea     r8, [rsp+58h+var_30]
0x140027c5f  mov     [rsp+58h+var_28], rax
0x140027c64  mov     [rsp+58h+var_20], eax
0x140027c68  mov     [rsp+58h+var_30], rax
0x140027c6d  lea     edx, [rax+1]
0x140027c70  call    cs:__imp_RtlQueryFeatureConfiguration
0x140027c77  nop     dword ptr [rax+rax+00h]
0x140027c7c  lea     r8, [rsp+58h+var_38]
0x140027c81  mov     [rsp+58h+var_38], 0
0x140027c8a  mov     ecx, eax
0x140027c8c  lea     rdx, [rsp+58h+var_28]
0x140027c91  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140027c96  mov     rcx, [rbx]
0x140027c99  mov     edx, [rcx]
0x140027c9b  xor     edx, dword ptr [rsp+58h+var_38]
0x140027c9f  mov     rax, [rbx]
0x140027ca2  and     edx, 0F80h
0x140027ca8  lock xor [rax], edx
0x140027cab  lea     rcx, [rbx+38h]
0x140027caf  call    wil_details_FeatureDescriptors_SkipPadding
0x140027cb4  mov     rbx, rax
0x140027cb7  test    rax, rax
0x140027cba  jnz     short loc_140027C3E
0x140027cbc  mov     rcx, [rsp+58h+var_18]
0x140027cc1  xor     rcx, rsp; StackCookie
0x140027cc4  call    __security_check_cookie
0x140027cc9  add     rsp, 50h
0x140027ccd  pop     rbx
0x140027cce  retn
```

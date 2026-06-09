# wil_details_UpdateFeatureConfiguredStates

- ea: `0x1400a8160`
- end: `0x1400a8210`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1400a80c0`

## callees

- `0x140035d80`
- `0x140067fc0`
- `0x1400a7e3c`
- `0x1400a8160`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400a81b0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400a81b0`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  _UNKNOWN **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v4 + 7) )
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
0x1400a8160  push    rbx
0x1400a8162  sub     rsp, 50h
0x1400a8166  mov     rax, cs:__security_cookie
0x1400a816d  xor     rax, rsp
0x1400a8170  mov     [rsp+58h+var_18], rax
0x1400a8175  lea     rcx, wil_details_featureDescriptors_a
0x1400a817c  jmp     short loc_1400A81EF
0x1400a817e  cmp     byte ptr [rbx+1Dh], 0
0x1400a8182  jnz     short loc_1400A81EB
0x1400a8184  cmp     byte ptr [rbx+1Eh], 0
0x1400a8188  jnz     short loc_1400A81EB
0x1400a818a  cmp     byte ptr [rbx+1Ch], 0
0x1400a818e  jnz     short loc_1400A81EB
0x1400a8190  mov     ecx, [rbx+18h]
0x1400a8193  lea     r9, [rsp+58h+var_28]
0x1400a8198  xor     eax, eax
0x1400a819a  lea     r8, [rsp+58h+var_30]
0x1400a819f  mov     [rsp+58h+var_28], rax
0x1400a81a4  mov     [rsp+58h+var_20], eax
0x1400a81a8  mov     [rsp+58h+var_30], rax
0x1400a81ad  lea     edx, [rax+1]
0x1400a81b0  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400a81b7  nop     dword ptr [rax+rax+00h]
0x1400a81bc  lea     r8, [rsp+58h+var_38]
0x1400a81c1  mov     [rsp+58h+var_38], 0
0x1400a81ca  mov     ecx, eax
0x1400a81cc  lea     rdx, [rsp+58h+var_28]
0x1400a81d1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400a81d6  mov     rcx, [rbx]
0x1400a81d9  mov     edx, [rcx]
0x1400a81db  xor     edx, dword ptr [rsp+58h+var_38]
0x1400a81df  mov     rax, [rbx]
0x1400a81e2  and     edx, 0F80h
0x1400a81e8  lock xor [rax], edx
0x1400a81eb  lea     rcx, [rbx+38h]
0x1400a81ef  call    wil_details_FeatureDescriptors_SkipPadding
0x1400a81f4  mov     rbx, rax
0x1400a81f7  test    rax, rax
0x1400a81fa  jnz     short loc_1400A817E
0x1400a81fc  mov     rcx, [rsp+58h+var_18]
0x1400a8201  xor     rcx, rsp; StackCookie
0x1400a8204  call    __security_check_cookie
0x1400a8209  add     rsp, 50h
0x1400a820d  pop     rbx
0x1400a820e  retn
```

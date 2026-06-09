# wil_details_UpdateFeatureConfiguredStates

- ea: `0x1400a82f0`
- end: `0x1400a83a0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1400a8250`

## callees

- `0x140035e40`
- `0x140068110`
- `0x1400a7f6c`
- `0x1400a82f0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400a8340`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400a8340`

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
0x1400a82f0  push    rbx
0x1400a82f2  sub     rsp, 50h
0x1400a82f6  mov     rax, cs:__security_cookie
0x1400a82fd  xor     rax, rsp
0x1400a8300  mov     [rsp+58h+var_18], rax
0x1400a8305  lea     rcx, wil_details_featureDescriptors_a
0x1400a830c  jmp     short loc_1400A837F
0x1400a830e  cmp     byte ptr [rbx+1Dh], 0
0x1400a8312  jnz     short loc_1400A837B
0x1400a8314  cmp     byte ptr [rbx+1Eh], 0
0x1400a8318  jnz     short loc_1400A837B
0x1400a831a  cmp     byte ptr [rbx+1Ch], 0
0x1400a831e  jnz     short loc_1400A837B
0x1400a8320  mov     ecx, [rbx+18h]
0x1400a8323  lea     r9, [rsp+58h+var_28]
0x1400a8328  xor     eax, eax
0x1400a832a  lea     r8, [rsp+58h+var_30]
0x1400a832f  mov     [rsp+58h+var_28], rax
0x1400a8334  mov     [rsp+58h+var_20], eax
0x1400a8338  mov     [rsp+58h+var_30], rax
0x1400a833d  lea     edx, [rax+1]
0x1400a8340  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400a8347  nop     dword ptr [rax+rax+00h]
0x1400a834c  lea     r8, [rsp+58h+var_38]
0x1400a8351  mov     [rsp+58h+var_38], 0
0x1400a835a  mov     ecx, eax
0x1400a835c  lea     rdx, [rsp+58h+var_28]
0x1400a8361  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400a8366  mov     rcx, [rbx]
0x1400a8369  mov     edx, [rcx]
0x1400a836b  xor     edx, dword ptr [rsp+58h+var_38]
0x1400a836f  mov     rax, [rbx]
0x1400a8372  and     edx, 0F80h
0x1400a8378  lock xor [rax], edx
0x1400a837b  lea     rcx, [rbx+38h]
0x1400a837f  call    wil_details_FeatureDescriptors_SkipPadding
0x1400a8384  mov     rbx, rax
0x1400a8387  test    rax, rax
0x1400a838a  jnz     short loc_1400A830E
0x1400a838c  mov     rcx, [rsp+58h+var_18]
0x1400a8391  xor     rcx, rsp; StackCookie
0x1400a8394  call    __security_check_cookie
0x1400a8399  add     rsp, 50h
0x1400a839d  pop     rbx
0x1400a839e  retn
```

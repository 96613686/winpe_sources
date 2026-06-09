# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14002f240`
- end: `0x14002f2f0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14002f1a0`

## callees

- `0x14000e1b4`
- `0x14001ede0`
- `0x14002ef10`
- `0x14002f240`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002f290`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002f290`

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

  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
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
0x14002f240  push    rbx
0x14002f242  sub     rsp, 50h
0x14002f246  mov     rax, cs:__security_cookie
0x14002f24d  xor     rax, rsp
0x14002f250  mov     [rsp+58h+var_18], rax
0x14002f255  lea     rcx, wil_details_featureDescriptors_a
0x14002f25c  jmp     short loc_14002F2CF
0x14002f25e  cmp     byte ptr [rbx+1Dh], 0
0x14002f262  jnz     short loc_14002F2CB
0x14002f264  cmp     byte ptr [rbx+1Eh], 0
0x14002f268  jnz     short loc_14002F2CB
0x14002f26a  cmp     byte ptr [rbx+1Ch], 0
0x14002f26e  jnz     short loc_14002F2CB
0x14002f270  mov     ecx, [rbx+18h]
0x14002f273  lea     r9, [rsp+58h+var_28]
0x14002f278  xor     eax, eax
0x14002f27a  lea     r8, [rsp+58h+var_30]
0x14002f27f  mov     [rsp+58h+var_28], rax
0x14002f284  mov     [rsp+58h+var_20], eax
0x14002f288  mov     [rsp+58h+var_30], rax
0x14002f28d  lea     edx, [rax+1]
0x14002f290  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002f297  nop     dword ptr [rax+rax+00h]
0x14002f29c  lea     r8, [rsp+58h+var_38]
0x14002f2a1  mov     [rsp+58h+var_38], 0
0x14002f2aa  mov     ecx, eax
0x14002f2ac  lea     rdx, [rsp+58h+var_28]
0x14002f2b1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14002f2b6  mov     rcx, [rbx]
0x14002f2b9  mov     edx, [rcx]
0x14002f2bb  xor     edx, dword ptr [rsp+58h+var_38]
0x14002f2bf  mov     rax, [rbx]
0x14002f2c2  and     edx, 0F80h
0x14002f2c8  lock xor [rax], edx
0x14002f2cb  lea     rcx, [rbx+38h]
0x14002f2cf  call    wil_details_FeatureDescriptors_SkipPadding
0x14002f2d4  mov     rbx, rax
0x14002f2d7  test    rax, rax
0x14002f2da  jnz     short loc_14002F25E
0x14002f2dc  mov     rcx, [rsp+58h+var_18]
0x14002f2e1  xor     rcx, rsp; StackCookie
0x14002f2e4  call    __security_check_cookie
0x14002f2e9  add     rsp, 50h
0x14002f2ed  pop     rbx
0x14002f2ee  retn
```

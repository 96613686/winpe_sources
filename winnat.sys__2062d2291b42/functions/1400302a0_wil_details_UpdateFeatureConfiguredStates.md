# wil_details_UpdateFeatureConfiguredStates

- ea: `0x1400302a0`
- end: `0x140030350`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140030200`

## callees

- `0x14000e184`
- `0x14001f320`
- `0x14002ff10`
- `0x1400302a0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400302f0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400302f0`

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
0x1400302a0  push    rbx
0x1400302a2  sub     rsp, 50h
0x1400302a6  mov     rax, cs:__security_cookie
0x1400302ad  xor     rax, rsp
0x1400302b0  mov     [rsp+58h+var_18], rax
0x1400302b5  lea     rcx, wil_details_featureDescriptors_a
0x1400302bc  jmp     short loc_14003032F
0x1400302be  cmp     byte ptr [rbx+1Dh], 0
0x1400302c2  jnz     short loc_14003032B
0x1400302c4  cmp     byte ptr [rbx+1Eh], 0
0x1400302c8  jnz     short loc_14003032B
0x1400302ca  cmp     byte ptr [rbx+1Ch], 0
0x1400302ce  jnz     short loc_14003032B
0x1400302d0  mov     ecx, [rbx+18h]
0x1400302d3  lea     r9, [rsp+58h+var_28]
0x1400302d8  xor     eax, eax
0x1400302da  lea     r8, [rsp+58h+var_30]
0x1400302df  mov     [rsp+58h+var_28], rax
0x1400302e4  mov     [rsp+58h+var_20], eax
0x1400302e8  mov     [rsp+58h+var_30], rax
0x1400302ed  lea     edx, [rax+1]
0x1400302f0  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400302f7  nop     dword ptr [rax+rax+00h]
0x1400302fc  lea     r8, [rsp+58h+var_38]
0x140030301  mov     [rsp+58h+var_38], 0
0x14003030a  mov     ecx, eax
0x14003030c  lea     rdx, [rsp+58h+var_28]
0x140030311  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140030316  mov     rcx, [rbx]
0x140030319  mov     edx, [rcx]
0x14003031b  xor     edx, dword ptr [rsp+58h+var_38]
0x14003031f  mov     rax, [rbx]
0x140030322  and     edx, 0F80h
0x140030328  lock xor [rax], edx
0x14003032b  lea     rcx, [rbx+38h]
0x14003032f  call    wil_details_FeatureDescriptors_SkipPadding
0x140030334  mov     rbx, rax
0x140030337  test    rax, rax
0x14003033a  jnz     short loc_1400302BE
0x14003033c  mov     rcx, [rsp+58h+var_18]
0x140030341  xor     rcx, rsp; StackCookie
0x140030344  call    __security_check_cookie
0x140030349  add     rsp, 50h
0x14003034d  pop     rbx
0x14003034e  retn
```

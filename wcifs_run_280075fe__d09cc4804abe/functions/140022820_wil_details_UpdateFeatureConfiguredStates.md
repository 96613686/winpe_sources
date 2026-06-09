# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140022820`
- end: `0x1400228d0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140022780`

## callees

- `0x140003248`
- `0x140007c60`
- `0x1400224ec`
- `0x140022820`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140022870`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140022870`

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
0x140022820  push    rbx
0x140022822  sub     rsp, 50h
0x140022826  mov     rax, cs:__security_cookie
0x14002282d  xor     rax, rsp
0x140022830  mov     [rsp+58h+var_18], rax
0x140022835  lea     rcx, wil_details_featureDescriptors_a
0x14002283c  jmp     short loc_1400228AF
0x14002283e  cmp     byte ptr [rbx+1Dh], 0
0x140022842  jnz     short loc_1400228AB
0x140022844  cmp     byte ptr [rbx+1Eh], 0
0x140022848  jnz     short loc_1400228AB
0x14002284a  cmp     byte ptr [rbx+1Ch], 0
0x14002284e  jnz     short loc_1400228AB
0x140022850  mov     ecx, [rbx+18h]
0x140022853  lea     r9, [rsp+58h+var_28]
0x140022858  xor     eax, eax
0x14002285a  lea     r8, [rsp+58h+var_30]
0x14002285f  mov     [rsp+58h+var_28], rax
0x140022864  mov     [rsp+58h+var_20], eax
0x140022868  mov     [rsp+58h+var_30], rax
0x14002286d  lea     edx, [rax+1]
0x140022870  call    cs:__imp_RtlQueryFeatureConfiguration
0x140022877  nop     dword ptr [rax+rax+00h]
0x14002287c  lea     r8, [rsp+58h+var_38]
0x140022881  mov     [rsp+58h+var_38], 0
0x14002288a  mov     ecx, eax
0x14002288c  lea     rdx, [rsp+58h+var_28]
0x140022891  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140022896  mov     rcx, [rbx]
0x140022899  mov     edx, [rcx]
0x14002289b  xor     edx, dword ptr [rsp+58h+var_38]
0x14002289f  mov     rax, [rbx]
0x1400228a2  and     edx, 0F80h
0x1400228a8  lock xor [rax], edx
0x1400228ab  lea     rcx, [rbx+38h]
0x1400228af  call    wil_details_FeatureDescriptors_SkipPadding
0x1400228b4  mov     rbx, rax
0x1400228b7  test    rax, rax
0x1400228ba  jnz     short loc_14002283E
0x1400228bc  mov     rcx, [rsp+58h+var_18]
0x1400228c1  xor     rcx, rsp; StackCookie
0x1400228c4  call    __security_check_cookie
0x1400228c9  add     rsp, 50h
0x1400228cd  pop     rbx
0x1400228ce  retn
```

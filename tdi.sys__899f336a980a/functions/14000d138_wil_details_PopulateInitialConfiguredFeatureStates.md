# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14000d138`
- end: `0x14000d217`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000d078`

## callees

- `0x140004f0c`
- `0x1400054b0`
- `0x14000b1d8`
- `0x14000d138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000d199`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000d199`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v2 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v2 = (_QWORD **)result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *(_BYTE *)(result + 29) || *(_BYTE *)(result + 30) )
    {
      v3 = -1073741275;
    }
    else
    {
      v3 = RtlQueryFeatureConfiguration(
             *(unsigned int *)(result + 24),
             (unsigned __int8)(*(_BYTE *)(result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v3 == -2147483614 )
      {
        v5 = 518;
        v4 = 518;
        do
        {
          **v2 = v4;
          result = wil_details_FeatureDescriptors_SkipPadding(v2 + 7);
          v2 = (_QWORD **)result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v3, &v7, &v5);
    **v2 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000d138  push    rbx
0x14000d13a  sub     rsp, 50h
0x14000d13e  mov     rax, cs:__security_cookie
0x14000d145  xor     rax, rsp
0x14000d148  mov     [rsp+58h+var_18], rax
0x14000d14d  lea     rcx, wil_details_featureDescriptors_a
0x14000d154  call    wil_details_FeatureDescriptors_SkipPadding
0x14000d159  mov     rbx, rax
0x14000d15c  test    rax, rax
0x14000d15f  jz      short loc_14000D1D9
0x14000d161  xor     eax, eax
0x14000d163  mov     [rsp+58h+var_28], rax
0x14000d168  mov     [rsp+58h+var_20], eax
0x14000d16c  mov     [rsp+58h+var_30], rax
0x14000d171  mov     [rsp+58h+var_38], rax
0x14000d176  cmp     [rbx+1Dh], al
0x14000d179  jnz     short loc_14000D1ED
0x14000d17b  cmp     [rbx+1Eh], al
0x14000d17e  jnz     short loc_14000D1ED
0x14000d180  mov     al, [rbx+1Ch]
0x14000d183  lea     r9, [rsp+58h+var_28]
0x14000d188  mov     ecx, [rbx+18h]
0x14000d18b  lea     r8, [rsp+58h+var_30]
0x14000d190  xor     edx, edx
0x14000d192  sub     al, 2
0x14000d194  cmp     al, 1
0x14000d196  setnbe  dl
0x14000d199  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000d1a0  nop     dword ptr [rax+rax+00h]
0x14000d1a5  cmp     eax, 80000022h
0x14000d1aa  jnz     short loc_14000D1F2
0x14000d1ac  mov     [rsp+58h+var_38], 0
0x14000d1b5  mov     dword ptr [rsp+58h+var_38], 206h
0x14000d1bd  mov     rdx, [rsp+58h+var_38]
0x14000d1c2  mov     rax, [rbx]
0x14000d1c5  lea     rcx, [rbx+38h]
0x14000d1c9  mov     [rax], rdx
0x14000d1cc  call    wil_details_FeatureDescriptors_SkipPadding
0x14000d1d1  mov     rbx, rax
0x14000d1d4  test    rax, rax
0x14000d1d7  jnz     short loc_14000D1C2
0x14000d1d9  mov     rcx, [rsp+58h+var_18]
0x14000d1de  xor     rcx, rsp; StackCookie
0x14000d1e1  call    __security_check_cookie
0x14000d1e6  add     rsp, 50h
0x14000d1ea  pop     rbx
0x14000d1eb  retn
0x14000d1ed  mov     eax, 0C0000225h
0x14000d1f2  lea     r8, [rsp+58h+var_38]
0x14000d1f7  mov     ecx, eax
0x14000d1f9  lea     rdx, [rsp+58h+var_28]
0x14000d1fe  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14000d203  mov     rcx, [rbx]
0x14000d206  mov     rax, [rsp+58h+var_38]
0x14000d20b  mov     [rcx], rax
0x14000d20e  lea     rcx, [rbx+38h]
0x14000d212  jmp     loc_14000D154
```

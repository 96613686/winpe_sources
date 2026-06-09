# wil_details_UpdateFeatureConfiguredStates

- ea: `0x1400422b0`
- end: `0x140042360`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140042210`

## callees

- `0x1400131bc`
- `0x14002a3e0`
- `0x140041ffc`
- `0x1400422b0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140042300`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140042300`

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
0x1400422b0  push    rbx
0x1400422b2  sub     rsp, 50h
0x1400422b6  mov     rax, cs:__security_cookie
0x1400422bd  xor     rax, rsp
0x1400422c0  mov     [rsp+58h+var_18], rax
0x1400422c5  lea     rcx, wil_details_featureDescriptors_a
0x1400422cc  jmp     short loc_14004233F
0x1400422ce  cmp     byte ptr [rbx+1Dh], 0
0x1400422d2  jnz     short loc_14004233B
0x1400422d4  cmp     byte ptr [rbx+1Eh], 0
0x1400422d8  jnz     short loc_14004233B
0x1400422da  cmp     byte ptr [rbx+1Ch], 0
0x1400422de  jnz     short loc_14004233B
0x1400422e0  mov     ecx, [rbx+18h]
0x1400422e3  lea     r9, [rsp+58h+var_28]
0x1400422e8  xor     eax, eax
0x1400422ea  lea     r8, [rsp+58h+var_30]
0x1400422ef  mov     [rsp+58h+var_28], rax
0x1400422f4  mov     [rsp+58h+var_20], eax
0x1400422f8  mov     [rsp+58h+var_30], rax
0x1400422fd  lea     edx, [rax+1]
0x140042300  call    cs:__imp_RtlQueryFeatureConfiguration
0x140042307  nop     dword ptr [rax+rax+00h]
0x14004230c  lea     r8, [rsp+58h+var_38]
0x140042311  mov     [rsp+58h+var_38], 0
0x14004231a  mov     ecx, eax
0x14004231c  lea     rdx, [rsp+58h+var_28]
0x140042321  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140042326  mov     rcx, [rbx]
0x140042329  mov     edx, [rcx]
0x14004232b  xor     edx, dword ptr [rsp+58h+var_38]
0x14004232f  mov     rax, [rbx]
0x140042332  and     edx, 0F80h
0x140042338  lock xor [rax], edx
0x14004233b  lea     rcx, [rbx+38h]
0x14004233f  call    wil_details_FeatureDescriptors_SkipPadding
0x140042344  mov     rbx, rax
0x140042347  test    rax, rax
0x14004234a  jnz     short loc_1400422CE
0x14004234c  mov     rcx, [rsp+58h+var_18]
0x140042351  xor     rcx, rsp; StackCookie
0x140042354  call    __security_check_cookie
0x140042359  add     rsp, 50h
0x14004235d  pop     rbx
0x14004235e  retn
```

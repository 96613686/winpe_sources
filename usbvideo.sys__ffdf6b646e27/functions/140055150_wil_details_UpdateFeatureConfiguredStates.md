# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140055150`
- end: `0x140055200`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1400550b0`

## callees

- `0x140012d40`
- `0x140040a30`
- `0x140054eec`
- `0x140055150`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400551a0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400551a0`

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
0x140055150  push    rbx
0x140055152  sub     rsp, 50h
0x140055156  mov     rax, cs:__security_cookie
0x14005515d  xor     rax, rsp
0x140055160  mov     [rsp+58h+var_18], rax
0x140055165  lea     rcx, wil_details_featureDescriptors_a
0x14005516c  jmp     short loc_1400551DF
0x14005516e  cmp     byte ptr [rbx+1Dh], 0
0x140055172  jnz     short loc_1400551DB
0x140055174  cmp     byte ptr [rbx+1Eh], 0
0x140055178  jnz     short loc_1400551DB
0x14005517a  cmp     byte ptr [rbx+1Ch], 0
0x14005517e  jnz     short loc_1400551DB
0x140055180  mov     ecx, [rbx+18h]
0x140055183  lea     r9, [rsp+58h+var_28]
0x140055188  xor     eax, eax
0x14005518a  lea     r8, [rsp+58h+var_30]
0x14005518f  mov     [rsp+58h+var_28], rax
0x140055194  mov     [rsp+58h+var_20], eax
0x140055198  mov     [rsp+58h+var_30], rax
0x14005519d  lea     edx, [rax+1]
0x1400551a0  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400551a7  nop     dword ptr [rax+rax+00h]
0x1400551ac  lea     r8, [rsp+58h+var_38]
0x1400551b1  mov     [rsp+58h+var_38], 0
0x1400551ba  mov     ecx, eax
0x1400551bc  lea     rdx, [rsp+58h+var_28]
0x1400551c1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400551c6  mov     rcx, [rbx]
0x1400551c9  mov     edx, [rcx]
0x1400551cb  xor     edx, dword ptr [rsp+58h+var_38]
0x1400551cf  mov     rax, [rbx]
0x1400551d2  and     edx, 0F80h
0x1400551d8  lock xor [rax], edx
0x1400551db  lea     rcx, [rbx+38h]
0x1400551df  call    wil_details_FeatureDescriptors_SkipPadding
0x1400551e4  mov     rbx, rax
0x1400551e7  test    rax, rax
0x1400551ea  jnz     short loc_14005516E
0x1400551ec  mov     rcx, [rsp+58h+var_18]
0x1400551f1  xor     rcx, rsp; StackCookie
0x1400551f4  call    __security_check_cookie
0x1400551f9  add     rsp, 50h
0x1400551fd  pop     rbx
0x1400551fe  retn
```

# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140022870`
- end: `0x140022920`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: `PDEVICE_OBJECT *()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1400227d0`

## callees

- `0x140003248`
- `0x140007c60`
- `0x1400224ec`
- `0x140022870`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400228c0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400228c0`

## pseudocode

```c
PDEVICE_OBJECT *wil_details_UpdateFeatureConfiguredStates()
{
  PDEVICE_OBJECT *i; // rcx
  __int64 v1; // rcx
  int v2; // eax
  PDEVICE_OBJECT *result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (PDEVICE_OBJECT *)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (volatile signed __int32 **)result;
    if ( !result )
      break;
    if ( !*((_BYTE *)result + 29) && !*((_BYTE *)result + 30) && !*((_BYTE *)result + 28) )
    {
      v1 = *((unsigned int *)result + 6);
      v7 = 0;
      v8 = 0;
      v6 = 0;
      v2 = RtlQueryFeatureConfiguration(v1, 1, &v6, &v7);
      v5 = 0;
      wil_details_BuildFeatureStateCacheFromQueryResults(v2, (__int64)&v7, &v5);
      _InterlockedXor(*v4, ((unsigned __int16)v5 ^ (unsigned __int16)**v4) & 0xF80);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140022870  push    rbx
0x140022872  sub     rsp, 50h
0x140022876  mov     rax, cs:__security_cookie
0x14002287d  xor     rax, rsp
0x140022880  mov     [rsp+58h+var_18], rax
0x140022885  lea     rcx, wil_details_featureDescriptors_a
0x14002288c  jmp     short loc_1400228FF
0x14002288e  cmp     byte ptr [rbx+1Dh], 0
0x140022892  jnz     short loc_1400228FB
0x140022894  cmp     byte ptr [rbx+1Eh], 0
0x140022898  jnz     short loc_1400228FB
0x14002289a  cmp     byte ptr [rbx+1Ch], 0
0x14002289e  jnz     short loc_1400228FB
0x1400228a0  mov     ecx, [rbx+18h]
0x1400228a3  lea     r9, [rsp+58h+var_28]
0x1400228a8  xor     eax, eax
0x1400228aa  lea     r8, [rsp+58h+var_30]
0x1400228af  mov     [rsp+58h+var_28], rax
0x1400228b4  mov     [rsp+58h+var_20], eax
0x1400228b8  mov     [rsp+58h+var_30], rax
0x1400228bd  lea     edx, [rax+1]
0x1400228c0  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400228c7  nop     dword ptr [rax+rax+00h]
0x1400228cc  lea     r8, [rsp+58h+var_38]
0x1400228d1  mov     [rsp+58h+var_38], 0
0x1400228da  mov     ecx, eax
0x1400228dc  lea     rdx, [rsp+58h+var_28]
0x1400228e1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400228e6  mov     rcx, [rbx]
0x1400228e9  mov     edx, [rcx]
0x1400228eb  xor     edx, dword ptr [rsp+58h+var_38]
0x1400228ef  mov     rax, [rbx]
0x1400228f2  and     edx, 0F80h
0x1400228f8  lock xor [rax], edx
0x1400228fb  lea     rcx, [rbx+38h]
0x1400228ff  call    wil_details_FeatureDescriptors_SkipPadding
0x140022904  mov     rbx, rax
0x140022907  test    rax, rax
0x14002290a  jnz     short loc_14002288E
0x14002290c  mov     rcx, [rsp+58h+var_18]
0x140022911  xor     rcx, rsp; StackCookie
0x140022914  call    __security_check_cookie
0x140022919  add     rsp, 50h
0x14002291d  pop     rbx
0x14002291e  retn
```

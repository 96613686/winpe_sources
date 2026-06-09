# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140039600`
- end: `0x1400396b0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140039560`

## callees

- `0x140015e64`
- `0x14001bc30`
- `0x140039274`
- `0x140039600`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140039650`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140039650`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  __int64 **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = Feature_SFS_CD_BugFixes_2409__private_descriptor; ; i = (__int64 **)(v4 + 7) )
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
0x140039600  push    rbx
0x140039602  sub     rsp, 50h
0x140039606  mov     rax, cs:__security_cookie
0x14003960d  xor     rax, rsp
0x140039610  mov     [rsp+58h+var_18], rax
0x140039615  lea     rcx, Feature_SFS_CD_BugFixes_2409__private_descriptor
0x14003961c  jmp     short loc_14003968F
0x14003961e  cmp     byte ptr [rbx+1Dh], 0
0x140039622  jnz     short loc_14003968B
0x140039624  cmp     byte ptr [rbx+1Eh], 0
0x140039628  jnz     short loc_14003968B
0x14003962a  cmp     byte ptr [rbx+1Ch], 0
0x14003962e  jnz     short loc_14003968B
0x140039630  mov     ecx, [rbx+18h]
0x140039633  lea     r9, [rsp+58h+var_28]
0x140039638  xor     eax, eax
0x14003963a  lea     r8, [rsp+58h+var_30]
0x14003963f  mov     [rsp+58h+var_28], rax
0x140039644  mov     [rsp+58h+var_20], eax
0x140039648  mov     [rsp+58h+var_30], rax
0x14003964d  lea     edx, [rax+1]
0x140039650  call    cs:__imp_RtlQueryFeatureConfiguration
0x140039657  nop     dword ptr [rax+rax+00h]
0x14003965c  lea     r8, [rsp+58h+var_38]
0x140039661  mov     [rsp+58h+var_38], 0
0x14003966a  mov     ecx, eax
0x14003966c  lea     rdx, [rsp+58h+var_28]
0x140039671  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140039676  mov     rcx, [rbx]
0x140039679  mov     edx, [rcx]
0x14003967b  xor     edx, dword ptr [rsp+58h+var_38]
0x14003967f  mov     rax, [rbx]
0x140039682  and     edx, 0F80h
0x140039688  lock xor [rax], edx
0x14003968b  lea     rcx, [rbx+38h]
0x14003968f  call    wil_details_FeatureDescriptors_SkipPadding
0x140039694  mov     rbx, rax
0x140039697  test    rax, rax
0x14003969a  jnz     short loc_14003961E
0x14003969c  mov     rcx, [rsp+58h+var_18]
0x1400396a1  xor     rcx, rsp; StackCookie
0x1400396a4  call    __security_check_cookie
0x1400396a9  add     rsp, 50h
0x1400396ad  pop     rbx
0x1400396ae  retn
```

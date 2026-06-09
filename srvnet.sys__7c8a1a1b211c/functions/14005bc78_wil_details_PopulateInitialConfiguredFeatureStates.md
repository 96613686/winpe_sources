# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14005bc78`
- end: `0x14005bd57`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14005bbb8`

## callees

- `0x1400131bc`
- `0x14002a3e0`
- `0x140041ffc`
- `0x14005bc78`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005bcd9`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005bcd9`

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
0x14005bc78  push    rbx
0x14005bc7a  sub     rsp, 50h
0x14005bc7e  mov     rax, cs:__security_cookie
0x14005bc85  xor     rax, rsp
0x14005bc88  mov     [rsp+58h+var_18], rax
0x14005bc8d  lea     rcx, wil_details_featureDescriptors_a
0x14005bc94  call    wil_details_FeatureDescriptors_SkipPadding
0x14005bc99  mov     rbx, rax
0x14005bc9c  test    rax, rax
0x14005bc9f  jz      short loc_14005BD19
0x14005bca1  xor     eax, eax
0x14005bca3  mov     [rsp+58h+var_28], rax
0x14005bca8  mov     [rsp+58h+var_20], eax
0x14005bcac  mov     [rsp+58h+var_30], rax
0x14005bcb1  mov     [rsp+58h+var_38], rax
0x14005bcb6  cmp     [rbx+1Dh], al
0x14005bcb9  jnz     short loc_14005BD2D
0x14005bcbb  cmp     [rbx+1Eh], al
0x14005bcbe  jnz     short loc_14005BD2D
0x14005bcc0  mov     al, [rbx+1Ch]
0x14005bcc3  lea     r9, [rsp+58h+var_28]
0x14005bcc8  mov     ecx, [rbx+18h]
0x14005bccb  lea     r8, [rsp+58h+var_30]
0x14005bcd0  xor     edx, edx
0x14005bcd2  sub     al, 2
0x14005bcd4  cmp     al, 1
0x14005bcd6  setnbe  dl
0x14005bcd9  call    cs:__imp_RtlQueryFeatureConfiguration
0x14005bce0  nop     dword ptr [rax+rax+00h]
0x14005bce5  cmp     eax, 80000022h
0x14005bcea  jnz     short loc_14005BD32
0x14005bcec  mov     [rsp+58h+var_38], 0
0x14005bcf5  mov     dword ptr [rsp+58h+var_38], 206h
0x14005bcfd  mov     rdx, [rsp+58h+var_38]
0x14005bd02  mov     rax, [rbx]
0x14005bd05  lea     rcx, [rbx+38h]
0x14005bd09  mov     [rax], rdx
0x14005bd0c  call    wil_details_FeatureDescriptors_SkipPadding
0x14005bd11  mov     rbx, rax
0x14005bd14  test    rax, rax
0x14005bd17  jnz     short loc_14005BD02
0x14005bd19  mov     rcx, [rsp+58h+var_18]
0x14005bd1e  xor     rcx, rsp; StackCookie
0x14005bd21  call    __security_check_cookie
0x14005bd26  add     rsp, 50h
0x14005bd2a  pop     rbx
0x14005bd2b  retn
0x14005bd2d  mov     eax, 0C0000225h
0x14005bd32  lea     r8, [rsp+58h+var_38]
0x14005bd37  mov     ecx, eax
0x14005bd39  lea     rdx, [rsp+58h+var_28]
0x14005bd3e  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14005bd43  mov     rcx, [rbx]
0x14005bd46  mov     rax, [rsp+58h+var_38]
0x14005bd4b  mov     [rcx], rax
0x14005bd4e  lea     rcx, [rbx+38h]
0x14005bd52  jmp     loc_14005BC94
```

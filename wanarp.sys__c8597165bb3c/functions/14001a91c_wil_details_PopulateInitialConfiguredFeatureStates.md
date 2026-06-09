# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14001a91c`
- end: `0x14001a9fb`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001a85c`

## callees

- `0x140003c5c`
- `0x1400050b0`
- `0x140017b50`
- `0x14001a91c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001a97d`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001a97d`

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
0x14001a91c  push    rbx
0x14001a91e  sub     rsp, 50h
0x14001a922  mov     rax, cs:__security_cookie
0x14001a929  xor     rax, rsp
0x14001a92c  mov     [rsp+58h+var_18], rax
0x14001a931  lea     rcx, wil_details_featureDescriptors_a
0x14001a938  call    wil_details_FeatureDescriptors_SkipPadding
0x14001a93d  mov     rbx, rax
0x14001a940  test    rax, rax
0x14001a943  jz      short loc_14001A9BD
0x14001a945  xor     eax, eax
0x14001a947  mov     [rsp+58h+var_28], rax
0x14001a94c  mov     [rsp+58h+var_20], eax
0x14001a950  mov     [rsp+58h+var_30], rax
0x14001a955  mov     [rsp+58h+var_38], rax
0x14001a95a  cmp     [rbx+1Dh], al
0x14001a95d  jnz     short loc_14001A9D1
0x14001a95f  cmp     [rbx+1Eh], al
0x14001a962  jnz     short loc_14001A9D1
0x14001a964  mov     al, [rbx+1Ch]
0x14001a967  lea     r9, [rsp+58h+var_28]
0x14001a96c  mov     ecx, [rbx+18h]
0x14001a96f  lea     r8, [rsp+58h+var_30]
0x14001a974  xor     edx, edx
0x14001a976  sub     al, 2
0x14001a978  cmp     al, 1
0x14001a97a  setnbe  dl
0x14001a97d  call    cs:__imp_RtlQueryFeatureConfiguration
0x14001a984  nop     dword ptr [rax+rax+00h]
0x14001a989  cmp     eax, 80000022h
0x14001a98e  jnz     short loc_14001A9D6
0x14001a990  mov     [rsp+58h+var_38], 0
0x14001a999  mov     dword ptr [rsp+58h+var_38], 206h
0x14001a9a1  mov     rdx, [rsp+58h+var_38]
0x14001a9a6  mov     rax, [rbx]
0x14001a9a9  lea     rcx, [rbx+38h]
0x14001a9ad  mov     [rax], rdx
0x14001a9b0  call    wil_details_FeatureDescriptors_SkipPadding
0x14001a9b5  mov     rbx, rax
0x14001a9b8  test    rax, rax
0x14001a9bb  jnz     short loc_14001A9A6
0x14001a9bd  mov     rcx, [rsp+58h+var_18]
0x14001a9c2  xor     rcx, rsp; StackCookie
0x14001a9c5  call    __security_check_cookie
0x14001a9ca  add     rsp, 50h
0x14001a9ce  pop     rbx
0x14001a9cf  retn
0x14001a9d1  mov     eax, 0C0000225h
0x14001a9d6  lea     r8, [rsp+58h+var_38]
0x14001a9db  mov     ecx, eax
0x14001a9dd  lea     rdx, [rsp+58h+var_28]
0x14001a9e2  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14001a9e7  mov     rcx, [rbx]
0x14001a9ea  mov     rax, [rsp+58h+var_38]
0x14001a9ef  mov     [rcx], rax
0x14001a9f2  lea     rcx, [rbx+38h]
0x14001a9f6  jmp     loc_14001A938
```

# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400169e0`
- end: `0x140016abf`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140016920`

## callees

- `0x1400084a4`
- `0x140008d20`
- `0x14001390c`
- `0x1400169e0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140016a41`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140016a41`

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
0x1400169e0  push    rbx
0x1400169e2  sub     rsp, 50h
0x1400169e6  mov     rax, cs:__security_cookie
0x1400169ed  xor     rax, rsp
0x1400169f0  mov     [rsp+58h+var_18], rax
0x1400169f5  lea     rcx, wil_details_featureDescriptors_a
0x1400169fc  call    wil_details_FeatureDescriptors_SkipPadding
0x140016a01  mov     rbx, rax
0x140016a04  test    rax, rax
0x140016a07  jz      short loc_140016A81
0x140016a09  xor     eax, eax
0x140016a0b  mov     [rsp+58h+var_28], rax
0x140016a10  mov     [rsp+58h+var_20], eax
0x140016a14  mov     [rsp+58h+var_30], rax
0x140016a19  mov     [rsp+58h+var_38], rax
0x140016a1e  cmp     [rbx+1Dh], al
0x140016a21  jnz     short loc_140016A95
0x140016a23  cmp     [rbx+1Eh], al
0x140016a26  jnz     short loc_140016A95
0x140016a28  mov     al, [rbx+1Ch]
0x140016a2b  lea     r9, [rsp+58h+var_28]
0x140016a30  mov     ecx, [rbx+18h]
0x140016a33  lea     r8, [rsp+58h+var_30]
0x140016a38  xor     edx, edx
0x140016a3a  sub     al, 2
0x140016a3c  cmp     al, 1
0x140016a3e  setnbe  dl
0x140016a41  call    cs:__imp_RtlQueryFeatureConfiguration
0x140016a48  nop     dword ptr [rax+rax+00h]
0x140016a4d  cmp     eax, 80000022h
0x140016a52  jnz     short loc_140016A9A
0x140016a54  mov     [rsp+58h+var_38], 0
0x140016a5d  mov     dword ptr [rsp+58h+var_38], 206h
0x140016a65  mov     rdx, [rsp+58h+var_38]
0x140016a6a  mov     rax, [rbx]
0x140016a6d  lea     rcx, [rbx+38h]
0x140016a71  mov     [rax], rdx
0x140016a74  call    wil_details_FeatureDescriptors_SkipPadding
0x140016a79  mov     rbx, rax
0x140016a7c  test    rax, rax
0x140016a7f  jnz     short loc_140016A6A
0x140016a81  mov     rcx, [rsp+58h+var_18]
0x140016a86  xor     rcx, rsp; StackCookie
0x140016a89  call    __security_check_cookie
0x140016a8e  add     rsp, 50h
0x140016a92  pop     rbx
0x140016a93  retn
0x140016a95  mov     eax, 0C0000225h
0x140016a9a  lea     r8, [rsp+58h+var_38]
0x140016a9f  mov     ecx, eax
0x140016aa1  lea     rdx, [rsp+58h+var_28]
0x140016aa6  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140016aab  mov     rcx, [rbx]
0x140016aae  mov     rax, [rsp+58h+var_38]
0x140016ab3  mov     [rcx], rax
0x140016ab6  lea     rcx, [rbx+38h]
0x140016aba  jmp     loc_1400169FC
```

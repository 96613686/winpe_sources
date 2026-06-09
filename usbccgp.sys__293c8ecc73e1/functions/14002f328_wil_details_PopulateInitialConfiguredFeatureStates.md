# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14002f328`
- end: `0x14002f407`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002f268`

## callees

- `0x14000ef2c`
- `0x140014d10`
- `0x140022bbc`
- `0x14002f328`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002f389`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002f389`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  _UNKNOWN **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v2 + 7) )
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
0x14002f328  push    rbx
0x14002f32a  sub     rsp, 50h
0x14002f32e  mov     rax, cs:__security_cookie
0x14002f335  xor     rax, rsp
0x14002f338  mov     [rsp+58h+var_18], rax
0x14002f33d  lea     rcx, wil_details_featureDescriptors_a
0x14002f344  call    wil_details_FeatureDescriptors_SkipPadding
0x14002f349  mov     rbx, rax
0x14002f34c  test    rax, rax
0x14002f34f  jz      short loc_14002F3C9
0x14002f351  xor     eax, eax
0x14002f353  mov     [rsp+58h+var_28], rax
0x14002f358  mov     [rsp+58h+var_20], eax
0x14002f35c  mov     [rsp+58h+var_30], rax
0x14002f361  mov     [rsp+58h+var_38], rax
0x14002f366  cmp     [rbx+1Dh], al
0x14002f369  jnz     short loc_14002F3DD
0x14002f36b  cmp     [rbx+1Eh], al
0x14002f36e  jnz     short loc_14002F3DD
0x14002f370  mov     al, [rbx+1Ch]
0x14002f373  lea     r9, [rsp+58h+var_28]
0x14002f378  mov     ecx, [rbx+18h]
0x14002f37b  lea     r8, [rsp+58h+var_30]
0x14002f380  xor     edx, edx
0x14002f382  sub     al, 2
0x14002f384  cmp     al, 1
0x14002f386  setnbe  dl
0x14002f389  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002f390  nop     dword ptr [rax+rax+00h]
0x14002f395  cmp     eax, 80000022h
0x14002f39a  jnz     short loc_14002F3E2
0x14002f39c  mov     [rsp+58h+var_38], 0
0x14002f3a5  mov     dword ptr [rsp+58h+var_38], 206h
0x14002f3ad  mov     rdx, [rsp+58h+var_38]
0x14002f3b2  mov     rax, [rbx]
0x14002f3b5  lea     rcx, [rbx+38h]
0x14002f3b9  mov     [rax], rdx
0x14002f3bc  call    wil_details_FeatureDescriptors_SkipPadding
0x14002f3c1  mov     rbx, rax
0x14002f3c4  test    rax, rax
0x14002f3c7  jnz     short loc_14002F3B2
0x14002f3c9  mov     rcx, [rsp+58h+var_18]
0x14002f3ce  xor     rcx, rsp; StackCookie
0x14002f3d1  call    __security_check_cookie
0x14002f3d6  add     rsp, 50h
0x14002f3da  pop     rbx
0x14002f3db  retn
0x14002f3dd  mov     eax, 0C0000225h
0x14002f3e2  lea     r8, [rsp+58h+var_38]
0x14002f3e7  mov     ecx, eax
0x14002f3e9  lea     rdx, [rsp+58h+var_28]
0x14002f3ee  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14002f3f3  mov     rcx, [rbx]
0x14002f3f6  mov     rax, [rsp+58h+var_38]
0x14002f3fb  mov     [rcx], rax
0x14002f3fe  lea     rcx, [rbx+38h]
0x14002f402  jmp     loc_14002F344
```

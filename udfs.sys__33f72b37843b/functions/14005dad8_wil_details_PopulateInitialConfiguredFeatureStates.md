# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14005dad8`
- end: `0x14005dbb7`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14005da18`

## callees

- `0x140015e64`
- `0x14001bc30`
- `0x140039274`
- `0x14005dad8`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005db39`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005db39`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = Feature_SFS_CD_BugFixes_2409__private_descriptor; ; i = v2 + 7 )
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
0x14005dad8  push    rbx
0x14005dada  sub     rsp, 50h
0x14005dade  mov     rax, cs:__security_cookie
0x14005dae5  xor     rax, rsp
0x14005dae8  mov     [rsp+58h+var_18], rax
0x14005daed  lea     rcx, Feature_SFS_CD_BugFixes_2409__private_descriptor
0x14005daf4  call    wil_details_FeatureDescriptors_SkipPadding
0x14005daf9  mov     rbx, rax
0x14005dafc  test    rax, rax
0x14005daff  jz      short loc_14005DB79
0x14005db01  xor     eax, eax
0x14005db03  mov     [rsp+58h+var_28], rax
0x14005db08  mov     [rsp+58h+var_20], eax
0x14005db0c  mov     [rsp+58h+var_30], rax
0x14005db11  mov     [rsp+58h+var_38], rax
0x14005db16  cmp     [rbx+1Dh], al
0x14005db19  jnz     short loc_14005DB8D
0x14005db1b  cmp     [rbx+1Eh], al
0x14005db1e  jnz     short loc_14005DB8D
0x14005db20  mov     al, [rbx+1Ch]
0x14005db23  lea     r9, [rsp+58h+var_28]
0x14005db28  mov     ecx, [rbx+18h]
0x14005db2b  lea     r8, [rsp+58h+var_30]
0x14005db30  xor     edx, edx
0x14005db32  sub     al, 2
0x14005db34  cmp     al, 1
0x14005db36  setnbe  dl
0x14005db39  call    cs:__imp_RtlQueryFeatureConfiguration
0x14005db40  nop     dword ptr [rax+rax+00h]
0x14005db45  cmp     eax, 80000022h
0x14005db4a  jnz     short loc_14005DB92
0x14005db4c  mov     [rsp+58h+var_38], 0
0x14005db55  mov     dword ptr [rsp+58h+var_38], 206h
0x14005db5d  mov     rdx, [rsp+58h+var_38]
0x14005db62  mov     rax, [rbx]
0x14005db65  lea     rcx, [rbx+38h]
0x14005db69  mov     [rax], rdx
0x14005db6c  call    wil_details_FeatureDescriptors_SkipPadding
0x14005db71  mov     rbx, rax
0x14005db74  test    rax, rax
0x14005db77  jnz     short loc_14005DB62
0x14005db79  mov     rcx, [rsp+58h+var_18]
0x14005db7e  xor     rcx, rsp; StackCookie
0x14005db81  call    __security_check_cookie
0x14005db86  add     rsp, 50h
0x14005db8a  pop     rbx
0x14005db8b  retn
0x14005db8d  mov     eax, 0C0000225h
0x14005db92  lea     r8, [rsp+58h+var_38]
0x14005db97  mov     ecx, eax
0x14005db99  lea     rdx, [rsp+58h+var_28]
0x14005db9e  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14005dba3  mov     rcx, [rbx]
0x14005dba6  mov     rax, [rsp+58h+var_38]
0x14005dbab  mov     [rcx], rax
0x14005dbae  lea     rcx, [rbx+38h]
0x14005dbb2  jmp     loc_14005DAF4
```

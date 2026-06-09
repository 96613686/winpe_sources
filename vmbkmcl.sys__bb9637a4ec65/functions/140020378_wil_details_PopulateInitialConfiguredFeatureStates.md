# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140020378`
- end: `0x140020457`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400202b8`

## callees

- `0x140010464`
- `0x140011e90`
- `0x14001dbfc`
- `0x140020378`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400203d9`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400203d9`

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
0x140020378  push    rbx
0x14002037a  sub     rsp, 50h
0x14002037e  mov     rax, cs:__security_cookie
0x140020385  xor     rax, rsp
0x140020388  mov     [rsp+58h+var_18], rax
0x14002038d  lea     rcx, wil_details_featureDescriptors_a
0x140020394  call    wil_details_FeatureDescriptors_SkipPadding
0x140020399  mov     rbx, rax
0x14002039c  test    rax, rax
0x14002039f  jz      short loc_140020419
0x1400203a1  xor     eax, eax
0x1400203a3  mov     [rsp+58h+var_28], rax
0x1400203a8  mov     [rsp+58h+var_20], eax
0x1400203ac  mov     [rsp+58h+var_30], rax
0x1400203b1  mov     [rsp+58h+var_38], rax
0x1400203b6  cmp     [rbx+1Dh], al
0x1400203b9  jnz     short loc_14002042D
0x1400203bb  cmp     [rbx+1Eh], al
0x1400203be  jnz     short loc_14002042D
0x1400203c0  mov     al, [rbx+1Ch]
0x1400203c3  lea     r9, [rsp+58h+var_28]
0x1400203c8  mov     ecx, [rbx+18h]
0x1400203cb  lea     r8, [rsp+58h+var_30]
0x1400203d0  xor     edx, edx
0x1400203d2  sub     al, 2
0x1400203d4  cmp     al, 1
0x1400203d6  setnbe  dl
0x1400203d9  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400203e0  nop     dword ptr [rax+rax+00h]
0x1400203e5  cmp     eax, 80000022h
0x1400203ea  jnz     short loc_140020432
0x1400203ec  mov     [rsp+58h+var_38], 0
0x1400203f5  mov     dword ptr [rsp+58h+var_38], 206h
0x1400203fd  mov     rdx, [rsp+58h+var_38]
0x140020402  mov     rax, [rbx]
0x140020405  lea     rcx, [rbx+38h]
0x140020409  mov     [rax], rdx
0x14002040c  call    wil_details_FeatureDescriptors_SkipPadding
0x140020411  mov     rbx, rax
0x140020414  test    rax, rax
0x140020417  jnz     short loc_140020402
0x140020419  mov     rcx, [rsp+58h+var_18]
0x14002041e  xor     rcx, rsp; StackCookie
0x140020421  call    __security_check_cookie
0x140020426  add     rsp, 50h
0x14002042a  pop     rbx
0x14002042b  retn
0x14002042d  mov     eax, 0C0000225h
0x140020432  lea     r8, [rsp+58h+var_38]
0x140020437  mov     ecx, eax
0x140020439  lea     rdx, [rsp+58h+var_28]
0x14002043e  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140020443  mov     rcx, [rbx]
0x140020446  mov     rax, [rsp+58h+var_38]
0x14002044b  mov     [rcx], rax
0x14002044e  lea     rcx, [rbx+38h]
0x140020452  jmp     loc_140020394
```

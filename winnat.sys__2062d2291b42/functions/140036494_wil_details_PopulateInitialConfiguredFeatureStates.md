# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140036494`
- end: `0x140036579`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400363d4`

## callees

- `0x14000e184`
- `0x14001f320`
- `0x14002ff10`
- `0x140036494`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400364ed`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400364ed`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  int **i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  _QWORD **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (_QWORD **)result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *(_BYTE *)(result + 29) || *(_BYTE *)(result + 30) )
    {
      v1 = -1073741275;
    }
    else
    {
      v1 = RtlQueryFeatureConfiguration(
             *(unsigned int *)(result + 24),
             (unsigned __int8)(*(_BYTE *)(result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v1 == -2147483614 )
      {
        v5 = 518;
        v2 = 518;
        do
        {
          **v4 = v2;
          result = wil_details_FeatureDescriptors_SkipPadding(v4 + 7);
          v4 = (_QWORD **)result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v1, &v7, &v5);
    **v4 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x140036494  push    rbx
0x140036496  sub     rsp, 50h
0x14003649a  mov     rax, cs:__security_cookie
0x1400364a1  xor     rax, rsp
0x1400364a4  mov     [rsp+58h+var_18], rax
0x1400364a9  lea     rcx, wil_details_featureDescriptors_a
0x1400364b0  jmp     loc_140036566
0x1400364b5  xor     eax, eax
0x1400364b7  mov     [rsp+58h+var_28], rax
0x1400364bc  mov     [rsp+58h+var_20], eax
0x1400364c0  mov     [rsp+58h+var_30], rax
0x1400364c5  mov     [rsp+58h+var_38], rax
0x1400364ca  cmp     [rbx+1Dh], al
0x1400364cd  jnz     short loc_140036541
0x1400364cf  cmp     [rbx+1Eh], al
0x1400364d2  jnz     short loc_140036541
0x1400364d4  mov     al, [rbx+1Ch]
0x1400364d7  lea     r9, [rsp+58h+var_28]
0x1400364dc  mov     ecx, [rbx+18h]
0x1400364df  lea     r8, [rsp+58h+var_30]
0x1400364e4  xor     edx, edx
0x1400364e6  sub     al, 2
0x1400364e8  cmp     al, 1
0x1400364ea  setnbe  dl
0x1400364ed  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400364f4  nop     dword ptr [rax+rax+00h]
0x1400364f9  cmp     eax, 80000022h
0x1400364fe  jnz     short loc_140036546
0x140036500  mov     [rsp+58h+var_38], 0
0x140036509  mov     dword ptr [rsp+58h+var_38], 206h
0x140036511  mov     rdx, [rsp+58h+var_38]
0x140036516  mov     rax, [rbx]
0x140036519  lea     rcx, [rbx+38h]
0x14003651d  mov     [rax], rdx
0x140036520  call    wil_details_FeatureDescriptors_SkipPadding
0x140036525  mov     rbx, rax
0x140036528  test    rax, rax
0x14003652b  jnz     short loc_140036516
0x14003652d  mov     rcx, [rsp+58h+var_18]
0x140036532  xor     rcx, rsp; StackCookie
0x140036535  call    __security_check_cookie
0x14003653a  add     rsp, 50h
0x14003653e  pop     rbx
0x14003653f  retn
0x140036541  mov     eax, 0C0000225h
0x140036546  lea     r8, [rsp+58h+var_38]
0x14003654b  mov     ecx, eax
0x14003654d  lea     rdx, [rsp+58h+var_28]
0x140036552  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140036557  mov     rcx, [rbx]
0x14003655a  mov     rax, [rsp+58h+var_38]
0x14003655f  mov     [rcx], rax
0x140036562  lea     rcx, [rbx+38h]
0x140036566  call    wil_details_FeatureDescriptors_SkipPadding
0x14003656b  mov     rbx, rax
0x14003656e  test    rax, rax
0x140036571  jnz     loc_1400364B5
0x140036577  jmp     short loc_14003652D
```

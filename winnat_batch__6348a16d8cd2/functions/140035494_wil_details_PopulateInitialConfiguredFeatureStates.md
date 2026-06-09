# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140035494`
- end: `0x140035579`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400353d4`

## callees

- `0x14000e1b4`
- `0x14001ede0`
- `0x14002ef10`
- `0x140035494`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400354ed`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400354ed`

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
0x140035494  push    rbx
0x140035496  sub     rsp, 50h
0x14003549a  mov     rax, cs:__security_cookie
0x1400354a1  xor     rax, rsp
0x1400354a4  mov     [rsp+58h+var_18], rax
0x1400354a9  lea     rcx, wil_details_featureDescriptors_a
0x1400354b0  jmp     loc_140035566
0x1400354b5  xor     eax, eax
0x1400354b7  mov     [rsp+58h+var_28], rax
0x1400354bc  mov     [rsp+58h+var_20], eax
0x1400354c0  mov     [rsp+58h+var_30], rax
0x1400354c5  mov     [rsp+58h+var_38], rax
0x1400354ca  cmp     [rbx+1Dh], al
0x1400354cd  jnz     short loc_140035541
0x1400354cf  cmp     [rbx+1Eh], al
0x1400354d2  jnz     short loc_140035541
0x1400354d4  mov     al, [rbx+1Ch]
0x1400354d7  lea     r9, [rsp+58h+var_28]
0x1400354dc  mov     ecx, [rbx+18h]
0x1400354df  lea     r8, [rsp+58h+var_30]
0x1400354e4  xor     edx, edx
0x1400354e6  sub     al, 2
0x1400354e8  cmp     al, 1
0x1400354ea  setnbe  dl
0x1400354ed  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400354f4  nop     dword ptr [rax+rax+00h]
0x1400354f9  cmp     eax, 80000022h
0x1400354fe  jnz     short loc_140035546
0x140035500  mov     [rsp+58h+var_38], 0
0x140035509  mov     dword ptr [rsp+58h+var_38], 206h
0x140035511  mov     rdx, [rsp+58h+var_38]
0x140035516  mov     rax, [rbx]
0x140035519  lea     rcx, [rbx+38h]
0x14003551d  mov     [rax], rdx
0x140035520  call    wil_details_FeatureDescriptors_SkipPadding
0x140035525  mov     rbx, rax
0x140035528  test    rax, rax
0x14003552b  jnz     short loc_140035516
0x14003552d  mov     rcx, [rsp+58h+var_18]
0x140035532  xor     rcx, rsp; StackCookie
0x140035535  call    __security_check_cookie
0x14003553a  add     rsp, 50h
0x14003553e  pop     rbx
0x14003553f  retn
0x140035541  mov     eax, 0C0000225h
0x140035546  lea     r8, [rsp+58h+var_38]
0x14003554b  mov     ecx, eax
0x14003554d  lea     rdx, [rsp+58h+var_28]
0x140035552  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140035557  mov     rcx, [rbx]
0x14003555a  mov     rax, [rsp+58h+var_38]
0x14003555f  mov     [rcx], rax
0x140035562  lea     rcx, [rbx+38h]
0x140035566  call    wil_details_FeatureDescriptors_SkipPadding
0x14003556b  mov     rbx, rax
0x14003556e  test    rax, rax
0x140035571  jnz     loc_1400354B5
0x140035577  jmp     short loc_14003552D
```

# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140050230`
- end: `0x14005030f`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140050170`

## callees

- `0x14001e658`
- `0x140039740`
- `0x14004e710`
- `0x140050230`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140050291`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140050291`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  int **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (int **)(v2 + 7) )
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
0x140050230  push    rbx
0x140050232  sub     rsp, 50h
0x140050236  mov     rax, cs:__security_cookie
0x14005023d  xor     rax, rsp
0x140050240  mov     [rsp+58h+var_18], rax
0x140050245  lea     rcx, wil_details_featureDescriptors_a
0x14005024c  call    wil_details_FeatureDescriptors_SkipPadding
0x140050251  mov     rbx, rax
0x140050254  test    rax, rax
0x140050257  jz      short loc_1400502D1
0x140050259  xor     eax, eax
0x14005025b  mov     [rsp+58h+var_28], rax
0x140050260  mov     [rsp+58h+var_20], eax
0x140050264  mov     [rsp+58h+var_30], rax
0x140050269  mov     [rsp+58h+var_38], rax
0x14005026e  cmp     [rbx+1Dh], al
0x140050271  jnz     short loc_1400502E5
0x140050273  cmp     [rbx+1Eh], al
0x140050276  jnz     short loc_1400502E5
0x140050278  mov     al, [rbx+1Ch]
0x14005027b  lea     r9, [rsp+58h+var_28]
0x140050280  mov     ecx, [rbx+18h]
0x140050283  lea     r8, [rsp+58h+var_30]
0x140050288  xor     edx, edx
0x14005028a  sub     al, 2
0x14005028c  cmp     al, 1
0x14005028e  setnbe  dl
0x140050291  call    cs:__imp_RtlQueryFeatureConfiguration
0x140050298  nop     dword ptr [rax+rax+00h]
0x14005029d  cmp     eax, 80000022h
0x1400502a2  jnz     short loc_1400502EA
0x1400502a4  mov     [rsp+58h+var_38], 0
0x1400502ad  mov     dword ptr [rsp+58h+var_38], 206h
0x1400502b5  mov     rdx, [rsp+58h+var_38]
0x1400502ba  mov     rax, [rbx]
0x1400502bd  lea     rcx, [rbx+38h]
0x1400502c1  mov     [rax], rdx
0x1400502c4  call    wil_details_FeatureDescriptors_SkipPadding
0x1400502c9  mov     rbx, rax
0x1400502cc  test    rax, rax
0x1400502cf  jnz     short loc_1400502BA
0x1400502d1  mov     rcx, [rsp+58h+var_18]
0x1400502d6  xor     rcx, rsp; StackCookie
0x1400502d9  call    __security_check_cookie
0x1400502de  add     rsp, 50h
0x1400502e2  pop     rbx
0x1400502e3  retn
0x1400502e5  mov     eax, 0C0000225h
0x1400502ea  lea     r8, [rsp+58h+var_38]
0x1400502ef  mov     ecx, eax
0x1400502f1  lea     rdx, [rsp+58h+var_28]
0x1400502f6  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400502fb  mov     rcx, [rbx]
0x1400502fe  mov     rax, [rsp+58h+var_38]
0x140050303  mov     [rcx], rax
0x140050306  lea     rcx, [rbx+38h]
0x14005030a  jmp     loc_14005024C
```

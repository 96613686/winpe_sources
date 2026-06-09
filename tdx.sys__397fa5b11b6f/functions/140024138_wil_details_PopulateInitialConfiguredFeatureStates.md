# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140024138`
- end: `0x140024217`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140024078`

## callees

- `0x140014694`
- `0x1400184b0`
- `0x140023068`
- `0x140024138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140024199`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140024199`

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
0x140024138  push    rbx
0x14002413a  sub     rsp, 50h
0x14002413e  mov     rax, cs:__security_cookie
0x140024145  xor     rax, rsp
0x140024148  mov     [rsp+58h+var_18], rax
0x14002414d  lea     rcx, wil_details_featureDescriptors_a
0x140024154  call    wil_details_FeatureDescriptors_SkipPadding
0x140024159  mov     rbx, rax
0x14002415c  test    rax, rax
0x14002415f  jz      short loc_1400241D9
0x140024161  xor     eax, eax
0x140024163  mov     [rsp+58h+var_28], rax
0x140024168  mov     [rsp+58h+var_20], eax
0x14002416c  mov     [rsp+58h+var_30], rax
0x140024171  mov     [rsp+58h+var_38], rax
0x140024176  cmp     [rbx+1Dh], al
0x140024179  jnz     short loc_1400241ED
0x14002417b  cmp     [rbx+1Eh], al
0x14002417e  jnz     short loc_1400241ED
0x140024180  mov     al, [rbx+1Ch]
0x140024183  lea     r9, [rsp+58h+var_28]
0x140024188  mov     ecx, [rbx+18h]
0x14002418b  lea     r8, [rsp+58h+var_30]
0x140024190  xor     edx, edx
0x140024192  sub     al, 2
0x140024194  cmp     al, 1
0x140024196  setnbe  dl
0x140024199  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400241a0  nop     dword ptr [rax+rax+00h]
0x1400241a5  cmp     eax, 80000022h
0x1400241aa  jnz     short loc_1400241F2
0x1400241ac  mov     [rsp+58h+var_38], 0
0x1400241b5  mov     dword ptr [rsp+58h+var_38], 206h
0x1400241bd  mov     rdx, [rsp+58h+var_38]
0x1400241c2  mov     rax, [rbx]
0x1400241c5  lea     rcx, [rbx+38h]
0x1400241c9  mov     [rax], rdx
0x1400241cc  call    wil_details_FeatureDescriptors_SkipPadding
0x1400241d1  mov     rbx, rax
0x1400241d4  test    rax, rax
0x1400241d7  jnz     short loc_1400241C2
0x1400241d9  mov     rcx, [rsp+58h+var_18]
0x1400241de  xor     rcx, rsp; StackCookie
0x1400241e1  call    __security_check_cookie
0x1400241e6  add     rsp, 50h
0x1400241ea  pop     rbx
0x1400241eb  retn
0x1400241ed  mov     eax, 0C0000225h
0x1400241f2  lea     r8, [rsp+58h+var_38]
0x1400241f7  mov     ecx, eax
0x1400241f9  lea     rdx, [rsp+58h+var_28]
0x1400241fe  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140024203  mov     rcx, [rbx]
0x140024206  mov     rax, [rsp+58h+var_38]
0x14002420b  mov     [rcx], rax
0x14002420e  lea     rcx, [rbx+38h]
0x140024212  jmp     loc_140024154
```

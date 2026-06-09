# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140036164`
- end: `0x140036249`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: `PDEVICE_OBJECT *()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400360a4`

## callees

- `0x140003248`
- `0x140007c60`
- `0x1400224ec`
- `0x140036164`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400361bd`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400361bd`

## pseudocode

```c
PDEVICE_OBJECT *wil_details_PopulateInitialConfiguredFeatureStates()
{
  PDEVICE_OBJECT *i; // rcx
  int v1; // eax
  __int64 v2; // rdx
  PDEVICE_OBJECT *result; // rax
  PDEVICE_OBJECT *v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = v4 + 7 )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *((_BYTE *)result + 29) || *((_BYTE *)result + 30) )
    {
      v1 = -1073741275;
    }
    else
    {
      v1 = RtlQueryFeatureConfiguration(
             *((unsigned int *)result + 6),
             (unsigned __int8)(*((_BYTE *)result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v1 == -2147483614 )
      {
        v5 = 518;
        v2 = 518;
        do
        {
          *(_QWORD *)&(*v4)->Type = v2;
          result = wil_details_FeatureDescriptors_SkipPadding(v4 + 7);
          v4 = result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v1, (__int64)&v7, &v5);
    *(_QWORD *)&(*v4)->Type = v5;
  }
  return result;
}

```

## disassembly

```asm
0x140036164  push    rbx
0x140036166  sub     rsp, 50h
0x14003616a  mov     rax, cs:__security_cookie
0x140036171  xor     rax, rsp
0x140036174  mov     [rsp+58h+var_18], rax
0x140036179  lea     rcx, wil_details_featureDescriptors_a
0x140036180  jmp     loc_140036236
0x140036185  xor     eax, eax
0x140036187  mov     [rsp+58h+var_28], rax
0x14003618c  mov     [rsp+58h+var_20], eax
0x140036190  mov     [rsp+58h+var_30], rax
0x140036195  mov     [rsp+58h+var_38], rax
0x14003619a  cmp     [rbx+1Dh], al
0x14003619d  jnz     short loc_140036211
0x14003619f  cmp     [rbx+1Eh], al
0x1400361a2  jnz     short loc_140036211
0x1400361a4  mov     al, [rbx+1Ch]
0x1400361a7  lea     r9, [rsp+58h+var_28]
0x1400361ac  mov     ecx, [rbx+18h]
0x1400361af  lea     r8, [rsp+58h+var_30]
0x1400361b4  xor     edx, edx
0x1400361b6  sub     al, 2
0x1400361b8  cmp     al, 1
0x1400361ba  setnbe  dl
0x1400361bd  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400361c4  nop     dword ptr [rax+rax+00h]
0x1400361c9  cmp     eax, 80000022h
0x1400361ce  jnz     short loc_140036216
0x1400361d0  mov     [rsp+58h+var_38], 0
0x1400361d9  mov     dword ptr [rsp+58h+var_38], 206h
0x1400361e1  mov     rdx, [rsp+58h+var_38]
0x1400361e6  mov     rax, [rbx]
0x1400361e9  lea     rcx, [rbx+38h]
0x1400361ed  mov     [rax], rdx
0x1400361f0  call    wil_details_FeatureDescriptors_SkipPadding
0x1400361f5  mov     rbx, rax
0x1400361f8  test    rax, rax
0x1400361fb  jnz     short loc_1400361E6
0x1400361fd  mov     rcx, [rsp+58h+var_18]
0x140036202  xor     rcx, rsp; StackCookie
0x140036205  call    __security_check_cookie
0x14003620a  add     rsp, 50h
0x14003620e  pop     rbx
0x14003620f  retn
0x140036211  mov     eax, 0C0000225h
0x140036216  lea     r8, [rsp+58h+var_38]
0x14003621b  mov     ecx, eax
0x14003621d  lea     rdx, [rsp+58h+var_28]
0x140036222  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140036227  mov     rcx, [rbx]
0x14003622a  mov     rax, [rsp+58h+var_38]
0x14003622f  mov     [rcx], rax
0x140036232  lea     rcx, [rbx+38h]
0x140036236  call    wil_details_FeatureDescriptors_SkipPadding
0x14003623b  mov     rbx, rax
0x14003623e  test    rax, rax
0x140036241  jnz     loc_140036185
0x140036247  jmp     short loc_1400361FD
```

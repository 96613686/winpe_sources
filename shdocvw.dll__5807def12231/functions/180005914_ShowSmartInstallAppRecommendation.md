# ShowSmartInstallAppRecommendation

- ea: `0x180005914`
- end: `0x180005ab0`
- name: `ShowSmartInstallAppRecommendation`
- size: `412`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, __int64, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180014fc0`
- `0x180015dc4`

## callees

- `0x180003660`
- `0x180005914`
- `0x180005ab8`
- `0x180005b0c`
- `0x1800069bc`
- `0x180006c3c`
- `0x180017d88`
- `0x18001835c`
- `0x180018824`
- `0x1800197b8`
- `0x18001a59c`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18000595d`
- `SHLWAPI!PathFindFileNameW` at `0x18000595d`
- `USER32!EnableWindow` at `0x180005a6c`
- `USER32!EnableWindow` at `0x180005a91`
- `USER32!EnableWindow` at `0x180005a6c`
- `USER32!EnableWindow` at `0x180005a91`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShowSmartInstallAppRecommendation(
        HWND a1,
        HWND a2,
        WCHAR *a3,
        char a4,
        __int64 a5,
        int a6,
        __int64 a7,
        unsigned int *a8)
{
  __int64 result; // rax
  const unsigned __int16 *FileNameW; // rax
  const unsigned __int16 *v14; // rcx
  const unsigned __int16 *v15; // rdx
  unsigned int v16; // ecx
  const unsigned __int16 *v17; // r8
  __int64 v18; // r8
  int v19; // eax
  unsigned int v20; // r8d
  _DWORD *v21; // rbx
  int v22; // eax
  unsigned int v23; // r8d
  int v24; // [rsp+20h] [rbp-30h]
  bool v25[8]; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v26[8]; // [rsp+38h] [rbp-18h] BYREF
  HWND hWnd; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( !a6 )
    return *a8;
  v25[0] = 0;
  if ( IsValidMicrosoftPSIFile(a3, v25) && v25[0] )
  {
    FileNameW = PathFindFileNameW(a3);
    SendPSITelemetryEvent(FileNameW);
    return *a8;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent>::GetImpl'::`2'::impl)
    && !IsPackageInstalled(v14) )
  {
    PurchaseAppNotPresentTelemetry(v16, v15, v17);
    LOBYTE(v18) = a4;
    result = DisplayLegacyBlockUX(a1, a3, v18, a5, a7);
    *a8 = result;
    return result;
  }
  if ( a6 == 3 )
  {
    OwnerWindowDisabler::OwnerWindowDisabler((OwnerWindowDisabler *)v26, a1);
    LOBYTE(a6) = 0;
    v19 = ShowSmartInstallAppRecommendation((__int64)a2, a3, 3, &a6);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x9F2, v20, (const char *)(unsigned int)v19, v24);
    *a8 = 1223;
    goto LABEL_22;
  }
  v21 = a8;
  if ( *a8 )
  {
    *a8 = 1223;
    return 1223;
  }
  OwnerWindowDisabler::OwnerWindowDisabler((OwnerWindowDisabler *)v26, a1);
  v25[0] = 0;
  v22 = ShowSmartInstallAppRecommendation((__int64)a2, a3, a6, v25);
  if ( v22 >= 0 )
  {
    if ( !v25[0] )
    {
      *v21 = 1223;
LABEL_22:
      if ( v26[0] )
        EnableWindow(hWnd, 1);
      return 1223;
    }
    goto LABEL_16;
  }
  wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xA00, v23, (const char *)(unsigned int)v22, v24);
  if ( v25[0] )
LABEL_16:
    RemoveMarkOfTheWeb(a3, a2);
  *v21 = 0;
  if ( v26[0] )
    EnableWindow(hWnd, 1);
  return 0;
}

```

## disassembly

```asm
0x180005914  push    rbp
0x180005916  push    rbx
0x180005917  push    rdi
0x180005918  push    r14
0x18000591a  push    r15
0x18000591c  mov     rbp, rsp
0x18000591f  sub     rsp, 50h
0x180005923  mov     bl, r9b
0x180005926  mov     rdi, r8
0x180005929  mov     r14, rdx
0x18000592c  mov     r15, rcx
0x18000592f  cmp     [rbp+arg_28], 0
0x180005933  jnz     short loc_180005940
0x180005935  mov     rax, [rbp+arg_38]
0x180005939  mov     eax, [rax]
0x18000593b  jmp     loc_180005AA4
0x180005940  mov     [rbp+var_20], 0
0x180005944  lea     rdx, [rbp+var_20]; bool *
0x180005948  mov     rcx, rdi; unsigned __int16 *
0x18000594b  call    ?IsValidMicrosoftPSIFile@@YA_NPEBGAEA_N@Z; IsValidMicrosoftPSIFile(ushort const *,bool &)
0x180005950  test    al, al
0x180005952  jz      short loc_18000596D
0x180005954  cmp     [rbp+var_20], 0
0x180005958  jz      short loc_18000596D
0x18000595a  mov     rcx, rdi; pszPath
0x18000595d  call    cs:__imp_PathFindFileNameW
0x180005963  mov     rcx, rax; unsigned __int16 *
0x180005966  call    ?SendPSITelemetryEvent@@YAXQEBG@Z; SendPSITelemetryEvent(ushort const * const)
0x18000596b  jmp     short loc_180005935
0x18000596d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent> `wil::Feature<__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent>::GetImpl(void)'::`2'::impl
0x180005974  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyUXIfPurchaseAppNotPresent>::__private_IsEnabled(void)
0x180005979  test    al, al
0x18000597b  jz      short loc_1800059B1
0x18000597d  call    ?IsPackageInstalled@@YA_NPEBG@Z; IsPackageInstalled(ushort const *)
0x180005982  test    al, al
0x180005984  jnz     short loc_1800059B1
0x180005986  call    ?PurchaseAppNotPresentTelemetry@@YAXIPEBG0@Z; PurchaseAppNotPresentTelemetry(uint,ushort const *,ushort const *)
0x18000598b  mov     rax, [rbp+arg_30]
0x18000598f  mov     qword ptr [rsp+50h+var_30], rax
0x180005994  mov     r9, [rbp+arg_20]
0x180005998  mov     r8b, bl
0x18000599b  mov     rdx, rdi
0x18000599e  mov     rcx, r15
0x1800059a1  call    DisplayLegacyBlockUX
0x1800059a6  mov     rcx, [rbp+arg_38]
0x1800059aa  mov     [rcx], eax
0x1800059ac  jmp     loc_180005AA4
0x1800059b1  cmp     [rbp+arg_28], 3
0x1800059b5  jnz     short loc_180005A00
0x1800059b7  mov     rdx, r15; HWND
0x1800059ba  lea     rcx, [rbp+var_18]; this
0x1800059be  call    ??0OwnerWindowDisabler@@QEAA@PEAUHWND__@@@Z; OwnerWindowDisabler::OwnerWindowDisabler(HWND__ *)
0x1800059c3  mov     byte ptr [rbp+arg_28], 0
0x1800059c7  lea     r9, [rbp+arg_28]
0x1800059cb  mov     r8d, 3
0x1800059d1  mov     rdx, rdi
0x1800059d4  mov     rcx, r14
0x1800059d7  call    ?ShowSmartInstallAppRecommendation@@YAJPEAUHWND__@@PEBGW4AppControlEnforcementLevel@SmartScreen@Security@Internal@Windows@@AEA_N@Z; ShowSmartInstallAppRecommendation(HWND__ *,ushort const *,Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel,bool &)
0x1800059dc  test    eax, eax
0x1800059de  jns     short loc_1800059F1
0x1800059e0  mov     rcx, [rbp+28h]; this
0x1800059e4  mov     r9d, eax; char *
0x1800059e7  mov     edx, 9F2h; void *
0x1800059ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800059f1  mov     rax, [rbp+arg_38]
0x1800059f5  mov     dword ptr [rax], 4C7h
0x1800059fb  jmp     loc_180005A82
0x180005a00  mov     rbx, [rbp+arg_38]
0x180005a04  cmp     dword ptr [rbx], 0
0x180005a07  jnz     loc_180005A99
0x180005a0d  mov     rdx, r15; HWND
0x180005a10  lea     rcx, [rbp+var_18]; this
0x180005a14  call    ??0OwnerWindowDisabler@@QEAA@PEAUHWND__@@@Z; OwnerWindowDisabler::OwnerWindowDisabler(HWND__ *)
0x180005a19  nop
0x180005a1a  mov     [rbp+var_20], 0
0x180005a1e  lea     r9, [rbp+var_20]
0x180005a22  mov     r8d, [rbp+arg_28]
0x180005a26  mov     rdx, rdi
0x180005a29  mov     rcx, r14
0x180005a2c  call    ?ShowSmartInstallAppRecommendation@@YAJPEAUHWND__@@PEBGW4AppControlEnforcementLevel@SmartScreen@Security@Internal@Windows@@AEA_N@Z; ShowSmartInstallAppRecommendation(HWND__ *,ushort const *,Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel,bool &)
0x180005a31  mov     rcx, [rbp+28h]; this
0x180005a35  test    eax, eax
0x180005a37  jns     short loc_180005A76
0x180005a39  mov     r9d, eax; char *
0x180005a3c  mov     edx, 0A00h; void *
0x180005a41  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005a46  cmp     [rbp+var_20], 0
0x180005a4a  jz      short loc_180005A57
0x180005a4c  mov     rdx, r14
0x180005a4f  mov     rcx, rdi
0x180005a52  call    RemoveMarkOfTheWeb
0x180005a57  mov     dword ptr [rbx], 0
0x180005a5d  cmp     [rbp+var_18], 0
0x180005a61  jz      short loc_180005A72
0x180005a63  mov     edx, 1; bEnable
0x180005a68  mov     rcx, [rbp+hWnd]; hWnd
0x180005a6c  call    cs:__imp_EnableWindow
0x180005a72  xor     eax, eax
0x180005a74  jmp     short loc_180005AA4
0x180005a76  cmp     [rbp+var_20], 0
0x180005a7a  jnz     short loc_180005A4C
0x180005a7c  mov     dword ptr [rbx], 4C7h
0x180005a82  cmp     [rbp+var_18], 0
0x180005a86  jz      short loc_180005A9F
0x180005a88  mov     edx, 1; bEnable
0x180005a8d  mov     rcx, [rbp+hWnd]; hWnd
0x180005a91  call    cs:__imp_EnableWindow
0x180005a97  jmp     short loc_180005A9F
0x180005a99  mov     dword ptr [rbx], 4C7h
0x180005a9f  mov     eax, 4C7h
0x180005aa4  add     rsp, 50h
0x180005aa8  pop     r15
0x180005aaa  pop     r14
0x180005aac  pop     rdi
0x180005aad  pop     rbx
0x180005aae  pop     rbp
0x180005aaf  retn
```

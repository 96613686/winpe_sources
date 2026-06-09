# SafeOpenPromptForShellExec

- ea: `0x180004d30`
- end: `0x180004eae`
- name: `SafeOpenPromptForShellExec`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004d30`
- `0x180004eb4`
- `0x1800067a0`
- `0x180008320`
- `0x180009018`
- `0x18000bf34`
- `0x18001d120`
- `0x180029010`

## import_xrefs

- `Wldp!__imp_?WldpQueryPolicySettingEnabled2@@YAJPEBGPEAH@Z` at `0x180004d99`
- `Wldp!__imp_?WldpQueryPolicySettingEnabled2@@YAJPEBGPEAH@Z` at `0x180004d99`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SafeOpenPromptForShellExec(__int64 a1, WCHAR *a2, __int64 a3, char a4, IUnknown *a5)
{
  unsigned int v9; // edi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v11; // rcx
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v17[262]; // [rsp+44h] [rbp-BCh] BYREF

  v13 = 1;
  v9 = 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_NightsWatchEnablement>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_NightsWatchEnablement>::GetImpl'::`2'::impl);
  if ( (a4 & 2) != 0 )
  {
    v14 = 0;
    if ( (int)WldpQueryPolicySettingEnabled2(L"ShellSmartscreenSuppressed", &v14) >= 0 && v14 )
    {
      if ( (a4 & 4) != 0 )
        v9 = 4558;
    }
    else
    {
      v9 = DoSafeOpenPromptForShellExec(a1, a2, a3, a4 & 1, (__int64)&v13, a5);
    }
    v13 |= 0x80u;
  }
  v15 = 0;
  if ( !v9 )
  {
    if ( a5 )
    {
      QueryInterface = a5->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      if ( ((int (__fastcall *)(IUnknown *, GUID *, __int64 *))QueryInterface)(
             a5,
             &GUID_a8cfdc36_0812_41e8_822a_0b69e430a412,
             &v15) >= 0 )
      {
        memset_0(v17, 0, 0x208u);
        v16 = v13;
        StringCchCopyW(v17, 0x104u, (size_t *)a2);
        (*(void (__fastcall **)(__int64, __int64, int *, __int64))(*(_QWORD *)v15 + 80LL))(v15, 131089, &v16, 524);
      }
    }
  }
  v11 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return v9;
}

```

## disassembly

```asm
0x180004d30  push    rbp
0x180004d32  push    rbx
0x180004d33  push    rsi
0x180004d34  push    rdi
0x180004d35  push    r12
0x180004d37  push    r14
0x180004d39  push    r15
0x180004d3b  lea     rbp, [rsp-160h]
0x180004d43  sub     rsp, 260h
0x180004d4a  mov     rax, cs:__security_cookie
0x180004d51  xor     rax, rsp
0x180004d54  mov     [rbp+190h+var_40], rax
0x180004d5b  mov     ebx, r9d
0x180004d5e  mov     r15, r8
0x180004d61  mov     r12, rdx
0x180004d64  mov     r14, rcx
0x180004d67  mov     rsi, [rbp+190h+arg_20]
0x180004d6e  mov     [rsp+290h+var_260], 1
0x180004d76  xor     edi, edi
0x180004d78  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NightsWatchEnablement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NightsWatchEnablement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NightsWatchEnablement> `wil::Feature<__WilFeatureTraits_Feature_NightsWatchEnablement>::GetImpl(void)'::`2'::impl
0x180004d7f  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_NightsWatchEnablement@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NightsWatchEnablement>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180004d84  test    bl, 2
0x180004d87  jz      short loc_180004DE0
0x180004d89  mov     [rsp+290h+var_25C], edi
0x180004d8d  lea     rdx, [rsp+290h+var_25C]
0x180004d92  lea     rcx, aShellsmartscre; "ShellSmartscreenSuppressed"
0x180004d99  call    cs:__imp_?WldpQueryPolicySettingEnabled2@@YAJPEBGPEAH@Z; WldpQueryPolicySettingEnabled2(ushort const *,int *)
0x180004d9f  test    eax, eax
0x180004da1  js      short loc_180004DB5
0x180004da3  cmp     [rsp+290h+var_25C], edi
0x180004da7  jz      short loc_180004DB5
0x180004da9  test    bl, 4
0x180004dac  jz      short loc_180004DDA
0x180004dae  mov     edi, 11CEh
0x180004db3  jmp     short loc_180004DDA
0x180004db5  and     ebx, 1
0x180004db8  mov     [rsp+290h+var_268], rsi
0x180004dbd  lea     rax, [rsp+290h+var_260]
0x180004dc2  mov     [rsp+290h+var_270], rax
0x180004dc7  mov     r9d, ebx
0x180004dca  mov     r8, r15
0x180004dcd  mov     rdx, r12
0x180004dd0  mov     rcx, r14
0x180004dd3  call    DoSafeOpenPromptForShellExec
0x180004dd8  mov     edi, eax
0x180004dda  bts     [rsp+290h+var_260], 7
0x180004de0  mov     [rsp+290h+var_258], 0
0x180004de9  test    edi, edi
0x180004deb  jnz     short loc_180004E6B
0x180004ded  test    rsi, rsi
0x180004df0  jz      short loc_180004E6B
0x180004df2  mov     rdx, [rsi]
0x180004df5  mov     rbx, [rdx]
0x180004df8  lea     rcx, [rsp+290h+var_258]
0x180004dfd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004e02  lea     r8, [rsp+290h+var_258]
0x180004e07  lea     rdx, _GUID_a8cfdc36_0812_41e8_822a_0b69e430a412
0x180004e0e  mov     rcx, rsi
0x180004e11  mov     rax, rbx
0x180004e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e19  test    eax, eax
0x180004e1b  js      short loc_180004E6B
0x180004e1d  xor     edx, edx; Val
0x180004e1f  mov     r8d, 208h; Size
0x180004e25  lea     rcx, [rsp+290h+var_24C]; void *
0x180004e2a  call    memset_0
0x180004e2f  mov     eax, [rsp+290h+var_260]
0x180004e33  mov     [rsp+290h+var_250], eax
0x180004e37  mov     r8, r12; unsigned __int16 *
0x180004e3a  mov     edx, 104h; unsigned __int64
0x180004e3f  lea     rcx, [rsp+290h+var_24C]; unsigned __int16 *
0x180004e44  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004e49  mov     rcx, [rsp+290h+var_258]
0x180004e4e  mov     rax, [rcx]
0x180004e51  mov     r9d, 20Ch
0x180004e57  lea     r8, [rsp+290h+var_250]
0x180004e5c  mov     edx, 20011h
0x180004e61  mov     rax, [rax+50h]
0x180004e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e6a  nop
0x180004e6b  mov     rcx, [rsp+290h+var_258]
0x180004e70  test    rcx, rcx
0x180004e73  jz      short loc_180004E8B
0x180004e75  mov     [rsp+290h+var_258], 0
0x180004e7e  mov     rax, [rcx]
0x180004e81  mov     rax, [rax+10h]
0x180004e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e8a  nop
0x180004e8b  mov     eax, edi
0x180004e8d  mov     rcx, [rbp+190h+var_40]
0x180004e94  xor     rcx, rsp; StackCookie
0x180004e97  call    __security_check_cookie
0x180004e9c  add     rsp, 260h
0x180004ea3  pop     r15
0x180004ea5  pop     r14
0x180004ea7  pop     r12
0x180004ea9  pop     rdi
0x180004eaa  pop     rsi
0x180004eab  pop     rbx
0x180004eac  pop     rbp
0x180004ead  retn
```

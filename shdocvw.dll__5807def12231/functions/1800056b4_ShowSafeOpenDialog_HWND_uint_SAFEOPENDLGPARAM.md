# _ShowSafeOpenDialog(HWND__ *,uint,SAFEOPENDLGPARAM *)

- ea: `0x1800056b4`
- end: `0x1800057f4`
- name: `?_ShowSafeOpenDialog@@YAIPEAUHWND__@@IPEAUSAFEOPENDLGPARAM@@@Z`
- size: `320`
- prototype: `unsigned int __fastcall(HWND hWndParent, unsigned int, struct SAFEOPENDLGPARAM *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003810`
- `0x18001d5d8`

## callees

- `0x180002ca0`
- `0x1800056b4`
- `0x1800057fc`
- `0x180005880`
- `0x180005898`
- `0x180006880`
- `0x18000b924`
- `0x18001911c`
- `0x1800196e4`
- `0x18001a630`

## import_xrefs

- `USER32!DialogBoxIndirectParamW` at `0x1800057d2`
- `USER32!DialogBoxIndirectParamW` at `0x1800057d2`

## string_xrefs

- `0x180005701`: `Software\Microsoft\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _ShowSafeOpenDialog(HWND hWndParent, unsigned int a2, struct SAFEOPENDLGPARAM *a3)
{
  HKEY v5; // rcx
  HINSTANCE v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  HINSTANCE v11; // rbx
  unsigned int v12; // ebx
  int dwInitParam; // [rsp+20h] [rbp-28h]
  _QWORD v14[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v16; // [rsp+58h] [rbp+10h] BYREF
  LPCDLGTEMPLATEW hDialogTemplate; // [rsp+68h] [rbp+20h] BYREF

  v16 = a2;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59793074>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59793074>::GetImpl'::`2'::impl) )
    return SHFusionDialogBoxParam(g_hinst, (LPCWSTR)0x1140, hWndParent, (DLGPROC)SafeOpenDlgProc, (LPARAM)a3);
  hDialogTemplate = 0;
  v6 = g_hinst;
  v16 = 0;
  if ( (int)SHRegGetDWORD(v5, L"Software\\Microsoft\\Accessibility", L"TextScaleFactor", &v16) < 0
    || (v8 = v16, v16 - 101 > 0x7C) )
  {
    v8 = 100;
  }
  v9 = anonymous_namespace_::ScaleDialogTemplate(v6, v7, v8, &hDialogTemplate);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecore\\internal\\shell\\inc\\private\\ShCore-Win32DialogResourceHelpers.h",
      (const char *)(unsigned int)v9,
      dwInitParam);
    wil::details::unique_storage<wil::details::resource_policy<DLGTEMPLATE *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,DLGTEMPLATE *,DLGTEMPLATE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DLGTEMPLATE *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,DLGTEMPLATE *,DLGTEMPLATE *,0,std::nullptr_t>>(&hDialogTemplate);
    return SHFusionDialogBoxParam(g_hinst, (LPCWSTR)0x1140, hWndParent, (DLGPROC)SafeOpenDlgProc, (LPARAM)a3);
  }
  v11 = g_hinst;
  v14[0] = 0;
  if ( (unsigned int)SHActivateContext(v14) )
  {
    if ( g_hActCtx != (HANDLE)-3LL )
      DelayLoadCC();
    v12 = DialogBoxIndirectParamW(v11, hDialogTemplate, hWndParent, (DLGPROC)SafeOpenDlgProc, (LPARAM)a3);
    SHDeactivateContext(v14[0]);
  }
  else
  {
    v12 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<DLGTEMPLATE *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,DLGTEMPLATE *,DLGTEMPLATE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DLGTEMPLATE *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,DLGTEMPLATE *,DLGTEMPLATE *,0,std::nullptr_t>>(&hDialogTemplate);
  return v12;
}

```

## disassembly

```asm
0x1800056b4  mov     [rsp+arg_0], rbx
0x1800056b9  mov     [rsp+arg_10], rsi
0x1800056be  mov     [rsp+arg_8], edx
0x1800056c2  push    rdi
0x1800056c3  sub     rsp, 40h
0x1800056c7  mov     rdi, r8
0x1800056ca  mov     rsi, rcx
0x1800056cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59793074@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59793074@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59793074> `wil::Feature<__WilFeatureTraits_Feature_59793074>::GetImpl(void)'::`2'::impl
0x1800056d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59793074@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59793074>::__private_IsEnabled(void)
0x1800056d9  test    al, al
0x1800056db  jz      short loc_18000575A
0x1800056dd  mov     [rsp+48h+hDialogTemplate], 0
0x1800056e6  mov     rbx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x1800056ed  mov     [rsp+48h+arg_8], 0
0x1800056f5  lea     r9, [rsp+48h+arg_8]; unsigned int *
0x1800056fa  lea     r8, aTextscalefacto; "TextScaleFactor"
0x180005701  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Accessibility"
0x180005708  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000570d  test    eax, eax
0x18000570f  js      short loc_18000571F
0x180005711  mov     r8d, [rsp+48h+arg_8]
0x180005716  lea     eax, [r8-65h]
0x18000571a  cmp     eax, 7Ch ; '|'
0x18000571d  jbe     short loc_180005725
0x18000571f  mov     r8d, 64h ; 'd'
0x180005725  lea     r9, [rsp+48h+hDialogTemplate]
0x18000572a  mov     rcx, rbx
0x18000572d  call    _anonymous_namespace___ScaleDialogTemplate
0x180005732  test    eax, eax
0x180005734  jns     short loc_18000578A
0x180005736  mov     rcx, [rsp+48h]; this
0x18000573b  mov     r9d, eax; char *
0x18000573e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\private"...
0x180005745  mov     edx, 0A2h; void *
0x18000574a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000574f  nop
0x180005750  lea     rcx, [rsp+48h+hDialogTemplate]
0x180005755  call    ??1?$unique_storage@U?$resource_policy@PEAUDLGTEMPLATE@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<DLGTEMPLATE *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,DLGTEMPLATE *,DLGTEMPLATE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DLGTEMPLATE *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,DLGTEMPLATE *,DLGTEMPLATE *,0,std::nullptr_t>>(void)
0x18000575a  mov     qword ptr [rsp+48h+dwInitParam], rdi; LPARAM
0x18000575f  lea     r9, ?SafeOpenDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180005766  mov     r8, rsi; hWndParent
0x180005769  mov     edx, 1140h; lpTemplateName
0x18000576e  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180005775  call    SHFusionDialogBoxParam
0x18000577a  mov     rbx, [rsp+48h+arg_0]
0x18000577f  mov     rsi, [rsp+48h+arg_10]
0x180005784  add     rsp, 40h
0x180005788  pop     rdi
0x180005789  retn
0x18000578a  mov     rbx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x180005791  mov     [rsp+48h+var_18], 0
0x18000579a  lea     rcx, [rsp+48h+var_18]
0x18000579f  call    SHActivateContext
0x1800057a4  test    eax, eax
0x1800057a6  jnz     short loc_1800057AC
0x1800057a8  xor     ebx, ebx
0x1800057aa  jmp     short loc_1800057E6
0x1800057ac  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x1800057b4  jz      short loc_1800057BB
0x1800057b6  call    DelayLoadCC
0x1800057bb  mov     qword ptr [rsp+48h+dwInitParam], rdi; dwInitParam
0x1800057c0  lea     r9, ?SafeOpenDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800057c7  mov     r8, rsi; hWndParent
0x1800057ca  mov     rdx, [rsp+48h+hDialogTemplate]; hDialogTemplate
0x1800057cf  mov     rcx, rbx; hInstance
0x1800057d2  call    cs:__imp_DialogBoxIndirectParamW
0x1800057d8  mov     rbx, rax
0x1800057db  mov     rcx, [rsp+48h+var_18]
0x1800057e0  call    SHDeactivateContext
0x1800057e5  nop
0x1800057e6  lea     rcx, [rsp+48h+hDialogTemplate]
0x1800057eb  call    ??1?$unique_storage@U?$resource_policy@PEAUDLGTEMPLATE@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<DLGTEMPLATE *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,DLGTEMPLATE *,DLGTEMPLATE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DLGTEMPLATE *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,DLGTEMPLATE *,DLGTEMPLATE *,0,std::nullptr_t>>(void)
0x1800057f0  mov     eax, ebx
0x1800057f2  jmp     short loc_18000577A
```

# QuietHoursService::OnRudeWindowStateChange(RudeWindowStateChangeFlags,HWND__ *)

- ea: `0x1800174b0`
- end: `0x1800177e4`
- name: `?OnRudeWindowStateChange@QuietHoursService@@UEAAJW4RudeWindowStateChangeFlags@@PEAUHWND__@@@Z`
- size: `820`
- prototype: `int __high(enum RudeWindowStateChangeFlags, HWND)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task`

## callees

- `0x1800174b0`
- `0x1800177ec`
- `0x180017844`
- `0x180017930`
- `0x1800179e8`
- `0x180017aa8`
- `0x180017adc`
- `0x180017b78`
- `0x180045368`
- `0x180076e38`
- `0x180094bfc`
- `0x1800c9884`
- `0x1800c98dc`
- `0x1800cc444`
- `0x18013d330`
- `0x18013df8c`

## import_xrefs

- `USER32!InternalGetWindowText` at `0x1800176e6`
- `USER32!InternalGetWindowText` at `0x1800176e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017564`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001763e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001779f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017564`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001763e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001779f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001764f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001764f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x1800176fc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18001770e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x1800176fc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18001770e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x1800176ae`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x1800176ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1800175f1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180017724`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1800175f1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180017724`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180017606`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180017739`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180017606`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180017739`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall QuietHoursService::OnRudeWindowStateChange(__int64 a1, char a2, HWND a3)
{
  bool v5; // si
  __int64 v6; // rdx
  QuietHoursService *v7; // rcx
  unsigned int v8; // r9d
  QuietHoursService *v9; // r14
  WCHAR *FileNameW; // rsi
  HSTRING *v12; // rbx
  unsigned __int64 v13; // rdi
  UINT32 v14; // edx
  const WCHAR *v15; // rcx
  bool IsProcessInExclusionList; // r14
  WCHAR *v17; // rax
  bool v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  int WindowLongPtrW; // [rsp+4Ch] [rbp-B4h] BYREF
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR *v22; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR *v23; // [rsp+60h] [rbp-A0h] BYREF
  void **v24; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[272]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v26[8]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v27[24]; // [rsp+190h] [rbp+90h] BYREF
  int v28; // [rsp+1A8h] [rbp+A8h]
  WCHAR pszPath[264]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR ClassName[264]; // [rsp+3D0h] [rbp+2D0h] BYREF
  WCHAR pString[264]; // [rsp+5E0h] [rbp+4E0h] BYREF

  v5 = a2 & 1;
  wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v24,
    "OnRudeWindowStateChange");
  v24 = &QuietHoursServiceTraceProvider::OnRudeWindowStateChange::`vftable';
  QuietHoursServiceTraceProvider::OnRudeWindowStateChange::StartActivity(
    (QuietHoursServiceTraceProvider::OnRudeWindowStateChange *)&v24,
    v5);
  memset_0(pszPath, 0, 0x208u);
  if ( !v5 || !a3 || QuietHoursService::GetProcessPathOrAppIdFromHwnd(v7, a3, pszPath, v8) < 0 )
    goto LABEL_2;
  IsProcessInExclusionList = QuietHoursService::IsProcessInExclusionList((QuietHoursService *)(a1 - 96), pszPath);
  memset_0(ClassName, 0, 0x208u);
  GetClassNameW(a3, ClassName, 260);
  v22 = ClassName;
  v18 = IsProcessInExclusionList;
  memset_0(pString, 0, 0x208u);
  if ( InternalGetWindowText(a3, pString, 260) )
    QuietHoursServiceTraceProvider::OnRudeWindowStateChange::RudeWindowText<unsigned short (&)[260]>(&v24, pString);
  WindowLongPtrW = GetWindowLongPtrW(a3, -16);
  v19 = GetWindowLongPtrW(a3, -20);
  v21 = 0;
  v17 = PathIsFileSpecW(pszPath) ? pszPath : PathFindFileNameW(pszPath);
  v23 = v17;
  QuietHoursServiceTraceProvider::OnRudeWindowStateChange::QuietHoursFullScreenProcess<unsigned short const *,int,bool &,unsigned short const * &,unsigned long &,unsigned long &>(
    (unsigned int)&v24,
    (unsigned int)&v23,
    (unsigned int)&v21,
    (unsigned int)&v18,
    (__int64)&v22,
    (__int64)&WindowLongPtrW,
    (__int64)&v19);
  if ( !IsProcessInExclusionList )
  {
LABEL_2:
    LOBYTE(v6) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImportantNotifications>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_ImportantNotifications>::GetImpl'::`2'::impl,
      v6);
    v9 = (QuietHoursService *)(a1 - 96);
    *(_BYTE *)(a1 - 96 + 441) = v5;
    if ( !v5 )
    {
      WindowsDeleteString(*(HSTRING *)(a1 + 352));
      *(_QWORD *)(a1 + 352) = 0;
LABEL_4:
      QuietHoursService::RaiseWnfIfStateChanged(v9);
      goto LABEL_5;
    }
    if ( PathIsFileSpecW(pszPath) )
    {
      FileNameW = pszPath;
      v12 = (HSTRING *)(a1 + 352);
    }
    else
    {
      FileNameW = PathFindFileNameW(pszPath);
      v12 = (HSTRING *)(a1 + 352);
      if ( !FileNameW )
      {
        WindowsDeleteString(*v12);
        v14 = 0;
        v15 = &pszDefault;
LABEL_14:
        *v12 = 0;
        WindowsCreateString(v15, v14, v12);
        goto LABEL_4;
      }
    }
    v13 = -1;
    do
      ++v13;
    while ( FileNameW[v13] );
    if ( v13 > 0xFFFFFFFF )
      goto LABEL_4;
    WindowsDeleteString(*v12);
    v14 = v13;
    v15 = FileNameW;
    goto LABEL_14;
  }
LABEL_5:
  wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v24);
  v24 = &QuietHoursServiceTraceProvider::OnRudeWindowStateChange::`vftable';
  wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v24);
  if ( v28 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v27);
  wil::details::shared_object<wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v26);
  wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>(v25);
  return 0;
}

```

## disassembly

```asm
0x1800174b0  mov     [rsp-8+arg_8], rbx
0x1800174b5  mov     [rsp-8+arg_18], rsi
0x1800174ba  push    rbp
0x1800174bb  push    rdi
0x1800174bc  push    r12
0x1800174be  push    r13
0x1800174c0  push    r14
0x1800174c2  lea     rbp, [rsp-700h]
0x1800174ca  sub     rsp, 800h
0x1800174d1  mov     rax, cs:__security_cookie
0x1800174d8  xor     rax, rsp
0x1800174db  mov     [rbp+720h+var_30], rax
0x1800174e2  mov     rdi, r8
0x1800174e5  mov     esi, edx
0x1800174e7  mov     rbx, rcx
0x1800174ea  and     esi, 1
0x1800174ed  lea     rdx, aOnrudewindowst; "OnRudeWindowStateChange"
0x1800174f4  lea     rcx, [rsp+820h+var_7B0]
0x1800174f9  call    ??0?$ActivityBase@VQuietHoursServiceTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800174fe  lea     rax, ??_7OnRudeWindowStateChange@QuietHoursServiceTraceProvider@@6B@; const QuietHoursServiceTraceProvider::OnRudeWindowStateChange::`vftable'
0x180017505  mov     [rsp+820h+var_7B0], rax
0x18001750a  mov     dl, sil; bool
0x18001750d  lea     rcx, [rsp+820h+var_7B0]; this
0x180017512  call    ?StartActivity@OnRudeWindowStateChange@QuietHoursServiceTraceProvider@@QEAAX_N@Z; QuietHoursServiceTraceProvider::OnRudeWindowStateChange::StartActivity(bool)
0x180017517  nop
0x180017518  mov     r13d, 208h
0x18001751e  mov     r8d, r13d; Size
0x180017521  xor     edx, edx; Val
0x180017523  lea     rcx, [rbp+720h+pszPath]; void *
0x18001752a  call    memset_0
0x18001752f  xor     r12d, r12d
0x180017532  test    sil, sil
0x180017535  jnz     loc_18001765A
0x18001753b  mov     dl, 1
0x18001753d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ImportantNotifications@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ImportantNotifications@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImportantNotifications> `wil::Feature<__WilFeatureTraits_Feature_ImportantNotifications>::GetImpl(void)'::`2'::impl
0x180017544  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ImportantNotifications@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImportantNotifications>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180017549  lea     r14, [rbx-60h]
0x18001754d  mov     [r14+1B9h], sil
0x180017554  test    sil, sil
0x180017557  jnz     loc_1800175EA
0x18001755d  mov     rcx, [rbx+160h]; string
0x180017564  call    cs:__imp_WindowsDeleteString
0x18001756a  mov     [rbx+160h], r12
0x180017571  mov     rcx, r14; this
0x180017574  call    ?RaiseWnfIfStateChanged@QuietHoursService@@AEAAXXZ; QuietHoursService::RaiseWnfIfStateChanged(void)
0x180017579  lea     rcx, [rsp+820h+var_7B0]
0x18001757e  call    ?Stop@?$ActivityBase@VQuietHoursServiceTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180017583  lea     rax, ??_7OnRudeWindowStateChange@QuietHoursServiceTraceProvider@@6B@; const QuietHoursServiceTraceProvider::OnRudeWindowStateChange::`vftable'
0x18001758a  mov     [rsp+820h+var_7B0], rax
0x18001758f  lea     rcx, [rsp+820h+var_7B0]
0x180017594  call    ?Destroy@?$ActivityBase@VQuietHoursServiceTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017599  nop
0x18001759a  cmp     [rbp+720h+var_678], r12d
0x1800175a1  jnz     loc_1800177D2
0x1800175a7  lea     rcx, [rbp+720h+var_698]
0x1800175ae  call    ?reset@?$shared_object@V?$ActivityData@VQuietHoursServiceTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VQuietHoursServiceTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800175b3  lea     rcx, [rsp+820h+var_7A8]
0x1800175b8  call    ??1?$ActivityData@VQuietHoursServiceTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VQuietHoursServiceTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800175bd  xor     eax, eax
0x1800175bf  mov     rcx, [rbp+720h+var_30]
0x1800175c6  xor     rcx, rsp; StackCookie
0x1800175c9  call    __security_check_cookie
0x1800175ce  lea     r11, [rsp+820h+var_20]
0x1800175d6  mov     rbx, [r11+38h]
0x1800175da  mov     rsi, [r11+48h]
0x1800175de  mov     rsp, r11
0x1800175e1  pop     r14
0x1800175e3  pop     r13
0x1800175e5  pop     r12
0x1800175e7  pop     rdi
0x1800175e8  pop     rbp
0x1800175e9  retn
0x1800175ea  lea     rcx, [rbp+720h+pszPath]; pszPath
0x1800175f1  call    cs:__imp_PathIsFileSpecW
0x1800175f7  test    eax, eax
0x1800175f9  jnz     loc_180017789
0x1800175ff  lea     rcx, [rbp+720h+pszPath]; pszPath
0x180017606  call    cs:__imp_PathFindFileNameW
0x18001760c  mov     rsi, rax
0x18001760f  add     rbx, 160h
0x180017616  test    rax, rax
0x180017619  jz      loc_18001779C
0x18001761f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017623  inc     rdi
0x180017626  cmp     [rsi+rdi*2], r12w
0x18001762b  jnz     short loc_180017623
0x18001762d  mov     eax, 0FFFFFFFFh
0x180017632  cmp     rdi, rax
0x180017635  ja      loc_180017571
0x18001763b  mov     rcx, [rbx]; string
0x18001763e  call    cs:__imp_WindowsDeleteString
0x180017644  mov     edx, edi; length
0x180017646  mov     rcx, rsi; sourceString
0x180017649  mov     r8, rbx; string
0x18001764c  mov     [rbx], r12
0x18001764f  call    cs:__imp_WindowsCreateString
0x180017655  jmp     loc_180017571
0x18001765a  test    rdi, rdi
0x18001765d  jz      loc_18001753B
0x180017663  lea     r8, [rbp+720h+pszPath]; unsigned __int16 *
0x18001766a  mov     rdx, rdi; HWND
0x18001766d  call    ?GetProcessPathOrAppIdFromHwnd@QuietHoursService@@AEAAJPEAUHWND__@@PEAGI@Z; QuietHoursService::GetProcessPathOrAppIdFromHwnd(HWND__ *,ushort *,uint)
0x180017672  test    eax, eax
0x180017674  js      loc_18001753B
0x18001767a  lea     rcx, [rbx-60h]; this
0x18001767e  lea     rdx, [rbp+720h+pszPath]; unsigned __int16 *
0x180017685  call    ?IsProcessInExclusionList@QuietHoursService@@AEBA_NPEBG@Z; QuietHoursService::IsProcessInExclusionList(ushort const *)
0x18001768a  mov     r14b, al
0x18001768d  mov     r8, r13; Size
0x180017690  xor     edx, edx; Val
0x180017692  lea     rcx, [rbp+720h+ClassName]; void *
0x180017699  call    memset_0
0x18001769e  mov     r8d, 104h; nMaxCount
0x1800176a4  lea     rdx, [rbp+720h+ClassName]; lpClassName
0x1800176ab  mov     rcx, rdi; hWnd
0x1800176ae  call    cs:__imp_GetClassNameW
0x1800176b4  lea     rax, [rbp+720h+ClassName]
0x1800176bb  mov     [rsp+820h+var_7C8], rax
0x1800176c0  mov     [rsp+820h+var_7E0], r14b
0x1800176c5  mov     r8, r13; Size
0x1800176c8  xor     edx, edx; Val
0x1800176ca  lea     rcx, [rbp+720h+pString]; void *
0x1800176d1  call    memset_0
0x1800176d6  mov     r8d, 104h; cchMaxCount
0x1800176dc  lea     rdx, [rbp+720h+pString]; pString
0x1800176e3  mov     rcx, rdi; hWnd
0x1800176e6  call    cs:__imp_InternalGetWindowText
0x1800176ec  test    eax, eax
0x1800176ee  jnz     loc_1800177BC
0x1800176f4  mov     edx, 0FFFFFFF0h; nIndex
0x1800176f9  mov     rcx, rdi; hWnd
0x1800176fc  call    cs:__imp_GetWindowLongPtrW
0x180017702  mov     [rsp+820h+var_7D4], eax
0x180017706  mov     edx, 0FFFFFFECh; nIndex
0x18001770b  mov     rcx, rdi; hWnd
0x18001770e  call    cs:__imp_GetWindowLongPtrW
0x180017714  mov     [rsp+820h+var_7D8], eax
0x180017718  mov     [rsp+820h+var_7D0], r12d
0x18001771d  lea     rcx, [rbp+720h+pszPath]; pszPath
0x180017724  call    cs:__imp_PathIsFileSpecW
0x18001772a  test    eax, eax
0x18001772c  jnz     loc_1800177B3
0x180017732  lea     rcx, [rbp+720h+pszPath]; pszPath
0x180017739  call    cs:__imp_PathFindFileNameW
0x18001773f  mov     [rsp+820h+var_7C0], rax
0x180017744  lea     rax, [rsp+820h+var_7D8]
0x180017749  mov     [rsp+820h+var_7F0], rax
0x18001774e  lea     rax, [rsp+820h+var_7D4]
0x180017753  mov     [rsp+820h+var_7F8], rax
0x180017758  lea     rax, [rsp+820h+var_7C8]
0x18001775d  mov     [rsp+820h+var_800], rax
0x180017762  lea     r9, [rsp+820h+var_7E0]
0x180017767  lea     r8, [rsp+820h+var_7D0]
0x18001776c  lea     rdx, [rsp+820h+var_7C0]
0x180017771  lea     rcx, [rsp+820h+var_7B0]
0x180017776  call    ??$QuietHoursFullScreenProcess@PEBGHAEA_NAEAPEBGAEAKAEAK@OnRudeWindowStateChange@QuietHoursServiceTraceProvider@@QEAAX$$QEAPEBG$$QEAHAEA_NAEAPEBGAEAK4@Z; QuietHoursServiceTraceProvider::OnRudeWindowStateChange::QuietHoursFullScreenProcess<ushort const *,int,bool &,ushort const * &,ulong &,ulong &>(ushort const * &&,int &&,bool &,ushort const * &,ulong &,ulong &)
0x18001777b  test    r14b, r14b
0x18001777e  jz      loc_18001753B
0x180017784  jmp     loc_180017579
0x180017789  lea     rsi, [rbp+720h+pszPath]
0x180017790  add     rbx, 160h
0x180017797  jmp     loc_18001761F
0x18001779c  mov     rcx, [rbx]; string
0x18001779f  call    cs:__imp_WindowsDeleteString
0x1800177a5  xor     edx, edx
0x1800177a7  lea     rcx, pszDefault
0x1800177ae  jmp     loc_180017649
0x1800177b3  lea     rax, [rbp+720h+pszPath]
0x1800177ba  jmp     short loc_18001773F
0x1800177bc  lea     rdx, [rbp+720h+pString]
0x1800177c3  lea     rcx, [rsp+820h+var_7B0]
0x1800177c8  call    ??$RudeWindowText@AEAY0BAE@G@OnRudeWindowStateChange@QuietHoursServiceTraceProvider@@QEAAXAEAY0BAE@G@Z; QuietHoursServiceTraceProvider::OnRudeWindowStateChange::RudeWindowText<ushort (&)[260]>(ushort (&)[260])
0x1800177cd  jmp     loc_1800176F4
0x1800177d2  lea     rcx, [rbp+720h+var_690]; this
0x1800177d9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800177de  jmp     loc_1800175A7
```

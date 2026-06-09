# CActivationErrorPopup::CreateAndShowModal(ushort const *,ACTIVATIONERROR_DISMISS_METHOD *)

- ea: `0x180164594`
- end: `0x18016479e`
- name: `?CreateAndShowModal@CActivationErrorPopup@@QEAAJPEBGPEAW4ACTIVATIONERROR_DISMISS_METHOD@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(CActivationErrorPopup *__hidden this, const unsigned __int16 *, enum ACTIVATIONERROR_DISMISS_METHOD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180166470`

## callees

- `0x180027ee4`
- `0x180036250`
- `0x1800f8344`
- `0x1801601ec`
- `0x18016029c`
- `0x180163ad0`
- `0x180164594`
- `0x180165f54`
- `0x180165fa0`
- `0x180165fd4`
- `0x1801661e0`
- `0x180168878`
- `0x18016b4c4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18016466c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18016466c`
- `Wldp!__imp_?WldpTraceLoggingWDACBlockDialogShown@@YAXPEBGJU_GUID@@0@Z` at `0x1801646e9`
- `Wldp!__imp_?WldpTraceLoggingWDACBlockDialogShown@@YAXPEBGJU_GUID@@0@Z` at `0x1801646e9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1801645d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016475b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1801645d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016475b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801645dd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180164697`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180164768`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801645dd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180164697`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180164768`

## string_xrefs

- `0x180164660`: `Microsoft.GamingServices_8wekyb3d8bbwe!GamingServices`
- `0x18016467a`: `GamingServices`

## pseudocode

```c
__int64 __fastcall CActivationErrorPopup::CreateAndShowModal(
        CActivationErrorPopup *this,
        WCHAR *a2,
        enum ACTIVATIONERROR_DISMISS_METHOD *a3)
{
  LPWSTR FileNameW; // rax
  __int64 v7; // rdx
  int v8; // ecx
  unsigned __int16 **v9; // r8
  LPWSTR v10; // rax
  __int64 v11; // rdx
  struct _GUID v12; // xmm0
  int v13; // edx
  int v14; // esi
  __int64 v15; // rax
  LPWSTR v16; // rax
  __int64 v17; // rcx
  struct _GUID v19; // [rsp+30h] [rbp-28h] BYREF
  LPWSTR v20; // [rsp+60h] [rbp+8h] BYREF
  LPWSTR v21; // [rsp+68h] [rbp+10h] BYREF

  *(_DWORD *)a3 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv>::GetImpl'::`2'::impl) )
  {
    FileNameW = 0;
    if ( a2 )
    {
      if ( PathIsFileSpecW(a2) )
        FileNameW = a2;
      else
        FileNameW = PathFindFileNameW(a2);
    }
    v7 = *((_QWORD *)this + 3);
    v21 = FileNameW;
    LODWORD(v20) = *(_DWORD *)(v7 + 116);
    ActivationErrorTelemetry::ActivationErrorDialogLaunch<int,long const &,unsigned short const *>(&v20, v7, &v21);
  }
  if ( a2 )
  {
    if ( IsCodeIntegrityError(**((_DWORD **)this + 3)) || IsNightsWatchDesktopError(v8) )
    {
      if ( IsRunningWdagContainer() )
        v10 = PathFindFileNameW(a2);
      else
        v10 = a2;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 32,
        v10,
        -1);
      if ( IsCodeIntegrityError(**((_DWORD **)this + 3)) && !IsNightsWatchUIEnabled() )
      {
        v11 = *((_QWORD *)this + 3);
        v12 = *(struct _GUID *)(v11 + 100);
        LODWORD(v11) = *(_DWORD *)v11;
        v19 = v12;
        WldpTraceLoggingWDACBlockDialogShown(a2, v11, &v19, &pszDefault);
      }
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 32);
      *((_QWORD *)this + 5) = -1;
      *((_QWORD *)this + 6) = -1;
      ImmersiveAppHelpers::GetNormalDisplayNameFromAppId(a2, (const unsigned __int16 *)this + 16, v9);
      if ( !*((_QWORD *)this + 4)
        && CompareStringOrdinal(a2, -1, L"Microsoft.GamingServices_8wekyb3d8bbwe!GamingServices", -1, 1) == 2 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          (char *)this + 32,
          L"GamingServices",
          -1);
      }
    }
  }
  v14 = CActivationErrorPopup::CreateAndShowAlert(this, a2);
  if ( v14 >= 0 )
  {
    *(_DWORD *)a3 = *((_DWORD *)this + 14);
    if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
      McTemplateU0zqjq_EventWriteTransfer(
        *((_QWORD *)this + 3) + 100,
        v13,
        (_DWORD)a2,
        **((_DWORD **)this + 3),
        *((_QWORD *)this + 3) + 100LL,
        *((_DWORD *)this + 14));
    v15 = *((_QWORD *)this + 3);
    v14 = *(_DWORD *)(v15 + 88);
    if ( !v14 || *((_DWORD *)this + 14) != 2 )
    {
      v14 = *(_DWORD *)(v15 + 92);
      if ( !v14 || *((_DWORD *)this + 14) != 3 )
        v14 = 2556505;
    }
  }
  v16 = 0;
  if ( a2 )
  {
    if ( PathIsFileSpecW(a2) )
      v16 = a2;
    else
      v16 = PathFindFileNameW(a2);
  }
  v17 = *((_QWORD *)this + 3);
  v20 = v16;
  ActivationErrorTelemetry::ActivationBlocked<long const &,enum ACTIVATIONERROR_DISMISS_METHOD &,unsigned short const *>(
    v17,
    a3,
    &v20);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180164594  mov     [rsp+arg_10], rbx
0x180164599  mov     [rsp+arg_18], rbp
0x18016459e  push    rsi
0x18016459f  push    rdi
0x1801645a0  push    r14
0x1801645a2  sub     rsp, 40h
0x1801645a6  mov     r14, r8
0x1801645a9  mov     dword ptr [r8], 0
0x1801645b0  mov     rbx, rdx
0x1801645b3  mov     rdi, rcx
0x1801645b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv> `wil::Feature<__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv>::GetImpl(void)'::`2'::impl
0x1801645bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv>::__private_IsEnabled(void)
0x1801645c2  test    al, al
0x1801645c4  jz      short loc_180164607
0x1801645c6  xor     eax, eax
0x1801645c8  test    rbx, rbx
0x1801645cb  jz      short loc_1801645E8
0x1801645cd  mov     rcx, rbx; pszPath
0x1801645d0  call    cs:__imp_PathIsFileSpecW
0x1801645d6  test    eax, eax
0x1801645d8  jnz     short loc_1801645E5
0x1801645da  mov     rcx, rbx; pszPath
0x1801645dd  call    cs:__imp_PathFindFileNameW
0x1801645e3  jmp     short loc_1801645E8
0x1801645e5  mov     rax, rbx
0x1801645e8  mov     rdx, [rdi+18h]
0x1801645ec  lea     r8, [rsp+58h+arg_8]
0x1801645f1  mov     [rsp+58h+arg_8], rax
0x1801645f6  lea     rcx, [rsp+58h+arg_0]
0x1801645fb  mov     eax, [rdx+74h]
0x1801645fe  mov     dword ptr [rsp+58h+arg_0], eax
0x180164602  call    ??$ActivationErrorDialogLaunch@HAEBJPEBG@ActivationErrorTelemetry@@SAX$$QEAHAEBJ$$QEAPEBG@Z; ActivationErrorTelemetry::ActivationErrorDialogLaunch<int,long const &,ushort const *>(int &&,long const &,ushort const * &&)
0x180164607  test    rbx, rbx
0x18016460a  jz      loc_1801646EF
0x180164610  mov     rax, [rdi+18h]
0x180164614  mov     ecx, [rax]; int
0x180164616  call    ?IsCodeIntegrityError@@YA_NJ@Z; IsCodeIntegrityError(long)
0x18016461b  test    al, al
0x18016461d  jnz     short loc_18016468B
0x18016461f  call    ?IsNightsWatchDesktopError@@YA_NJ@Z; IsNightsWatchDesktopError(long)
0x180164624  test    al, al
0x180164626  jnz     short loc_18016468B
0x180164628  lea     rsi, [rdi+20h]
0x18016462c  mov     rcx, rsi
0x18016462f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180164634  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180164638  mov     rdx, rsi; unsigned __int16 *
0x18016463b  mov     rcx, rbx; pszItem
0x18016463e  mov     [rsi+8], rbp
0x180164642  mov     [rsi+10h], rbp
0x180164646  call    ?GetNormalDisplayNameFromAppId@ImmersiveAppHelpers@@YAJPEBGPEAPEAG@Z; ImmersiveAppHelpers::GetNormalDisplayNameFromAppId(ushort const *,ushort * *)
0x18016464b  cmp     qword ptr [rsi], 0
0x18016464f  jnz     loc_1801646EF
0x180164655  mov     r9d, ebp; cchCount2
0x180164658  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180164660  lea     r8, aMicrosoftGamin_0; "Microsoft.GamingServices_8wekyb3d8bbwe!"...
0x180164667  mov     edx, ebp; cchCount1
0x180164669  mov     rcx, rbx; lpString1
0x18016466c  call    cs:__imp_CompareStringOrdinal
0x180164672  cmp     eax, 2
0x180164675  jnz     short loc_1801646EF
0x180164677  mov     r8, rbp
0x18016467a  lea     rdx, aGamingservices; "GamingServices"
0x180164681  mov     rcx, rsi
0x180164684  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180164689  jmp     short loc_1801646EF
0x18016468b  call    ?IsRunningWdagContainer@@YA_NXZ; IsRunningWdagContainer(void)
0x180164690  test    al, al
0x180164692  jz      short loc_18016469F
0x180164694  mov     rcx, rbx; pszPath
0x180164697  call    cs:__imp_PathFindFileNameW
0x18016469d  jmp     short loc_1801646A2
0x18016469f  mov     rax, rbx
0x1801646a2  lea     rcx, [rdi+20h]
0x1801646a6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801646aa  mov     rdx, rax
0x1801646ad  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801646b2  mov     rcx, [rdi+18h]
0x1801646b6  mov     ecx, [rcx]; int
0x1801646b8  call    ?IsCodeIntegrityError@@YA_NJ@Z; IsCodeIntegrityError(long)
0x1801646bd  test    al, al
0x1801646bf  jz      short loc_1801646EF
0x1801646c1  call    ?IsNightsWatchUIEnabled@@YA_NXZ; IsNightsWatchUIEnabled(void)
0x1801646c6  test    al, al
0x1801646c8  jnz     short loc_1801646EF
0x1801646ca  mov     rdx, [rdi+18h]
0x1801646ce  lea     r9, pszDefault
0x1801646d5  lea     r8, [rsp+58h+var_28]
0x1801646da  mov     rcx, rbx
0x1801646dd  movups  xmm0, xmmword ptr [rdx+64h]
0x1801646e1  mov     edx, [rdx]
0x1801646e3  movdqu  [rsp+58h+var_28], xmm0
0x1801646e9  call    cs:__imp_?WldpTraceLoggingWDACBlockDialogShown@@YAXPEBGJU_GUID@@0@Z; WldpTraceLoggingWDACBlockDialogShown(ushort const *,long,_GUID,ushort const *)
0x1801646ef  mov     rdx, rbx; unsigned __int16 *
0x1801646f2  mov     rcx, rdi; this
0x1801646f5  call    ?CreateAndShowAlert@CActivationErrorPopup@@AEAAJPEBG@Z; CActivationErrorPopup::CreateAndShowAlert(ushort const *)
0x1801646fa  mov     esi, eax
0x1801646fc  test    eax, eax
0x1801646fe  js      short loc_180164751
0x180164700  mov     eax, [rdi+38h]
0x180164703  mov     [r14], eax
0x180164706  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18016470d  jz      short loc_18016472E
0x18016470f  mov     r9, [rdi+18h]
0x180164713  mov     r8, rbx
0x180164716  mov     eax, [rdi+38h]
0x180164719  mov     [rsp+58h+var_30], eax
0x18016471d  lea     rcx, [r9+64h]
0x180164721  mov     r9d, [r9]
0x180164724  mov     qword ptr [rsp+58h+bIgnoreCase], rcx
0x180164729  call    McTemplateU0zqjq_EventWriteTransfer
0x18016472e  mov     rax, [rdi+18h]
0x180164732  mov     esi, [rax+58h]
0x180164735  test    esi, esi
0x180164737  jz      short loc_18016473F
0x180164739  cmp     dword ptr [rdi+38h], 2
0x18016473d  jz      short loc_180164751
0x18016473f  mov     esi, [rax+5Ch]
0x180164742  test    esi, esi
0x180164744  jz      short loc_18016474C
0x180164746  cmp     dword ptr [rdi+38h], 3
0x18016474a  jz      short loc_180164751
0x18016474c  mov     esi, 270259h
0x180164751  xor     eax, eax
0x180164753  test    rbx, rbx
0x180164756  jz      short loc_180164773
0x180164758  mov     rcx, rbx; pszPath
0x18016475b  call    cs:__imp_PathIsFileSpecW
0x180164761  test    eax, eax
0x180164763  jnz     short loc_180164770
0x180164765  mov     rcx, rbx; pszPath
0x180164768  call    cs:__imp_PathFindFileNameW
0x18016476e  jmp     short loc_180164773
0x180164770  mov     rax, rbx
0x180164773  mov     rcx, [rdi+18h]
0x180164777  lea     r8, [rsp+58h+arg_0]
0x18016477c  mov     rdx, r14
0x18016477f  mov     [rsp+58h+arg_0], rax
0x180164784  call    ??$ActivationBlocked@AEBJAEAW4ACTIVATIONERROR_DISMISS_METHOD@@PEBG@ActivationErrorTelemetry@@SAXAEBJAEAW4ACTIVATIONERROR_DISMISS_METHOD@@$$QEAPEBG@Z; ActivationErrorTelemetry::ActivationBlocked<long const &,ACTIVATIONERROR_DISMISS_METHOD &,ushort const *>(long const &,ACTIVATIONERROR_DISMISS_METHOD &,ushort const * &&)
0x180164789  mov     rbx, [rsp+58h+arg_10]
0x18016478e  mov     eax, esi
0x180164790  mov     rbp, [rsp+58h+arg_18]
0x180164795  add     rsp, 40h
0x180164799  pop     r14
0x18016479b  pop     rdi
0x18016479c  pop     rsi
0x18016479d  retn
```

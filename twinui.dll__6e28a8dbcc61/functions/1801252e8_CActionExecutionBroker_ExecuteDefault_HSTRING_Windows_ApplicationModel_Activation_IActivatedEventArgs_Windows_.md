# CActionExecutionBroker::_ExecuteDefault(HSTRING__ *,Windows::ApplicationModel::Activation::IActivatedEventArgs *,Windows::ApplicationModel::Actions::IActionActivationInfo *,HSTRING__ *)

- ea: `0x1801252e8`
- end: `0x180125716`
- name: `?_ExecuteDefault@CActionExecutionBroker@@AEAAJPEAUHSTRING__@@PEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIActionActivationInfo@Actions@56@0@Z`
- size: `1070`
- prototype: `__int64 __fastcall(CActionExecutionBroker *__hidden this, HSTRING, struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct Windows::ApplicationModel::Actions::IActionActivationInfo *, HSTRING)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801250f0`

## callees

- `0x180027ee4`
- `0x1801252e8`
- `0x18012571c`
- `0x180150e08`
- `0x180150ed4`
- `0x180150fd0`
- `0x1801510d8`
- `0x18035fea4`
- `0x18036034c`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012537c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012537c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180125428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012546b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012555f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801256ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801256ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180125428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012546b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012555f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801256ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801256ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180125347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180125598`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180125347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180125598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012540c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801254f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180125649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012540c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801254f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180125649`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x180125324`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x180125324`

## pseudocode

```c
__int64 __fastcall CActionExecutionBroker::_ExecuteDefault(
        CActionExecutionBroker *this,
        HSTRING a2,
        struct Windows::ApplicationModel::Activation::IActivatedEventArgs *a3,
        IUnknown *a4,
        HSTRING a5)
{
  CActionExecutionBroker *v6; // rsi
  struct Windows::ApplicationModel::Activation::IActivatedEventArgs *v8; // r12
  HRESULT Window; // ebx
  const WCHAR *StringRawBuffer; // r14
  wchar_t **i; // rdi
  wchar_t *v12; // rcx
  void *v13; // rsi
  __int64 v14; // rdx
  unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rcx
  wchar_t *v17; // rcx
  void *v18; // rsi
  __int64 v19; // rdx
  unsigned __int16 *v20; // r12
  wchar_t *v21; // rcx
  HRESULT v22; // eax
  ImmersiveAssociationHelpers *v23; // rax
  unsigned __int16 **v24; // r9
  CActionExecutionBroker *v25; // rcx
  int v26; // eax
  void *v27; // rdi
  __int64 v28; // rdx
  unsigned __int16 *v29; // rsi
  HRESULT v30; // eax
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  HWND phwnd; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-30h] BYREF
  __int64 v35; // [rsp+48h] [rbp-28h]
  __int64 v36; // [rsp+50h] [rbp-20h]
  unsigned __int16 *v37; // [rsp+58h] [rbp-18h] BYREF
  __int64 v38; // [rsp+60h] [rbp-10h]
  __int64 v39; // [rsp+68h] [rbp-8h]

  phwnd = 0;
  v6 = this;
  v8 = a3;
  Window = IUnknown_GetWindow(a4, &phwnd);
  if ( Window >= 0 )
  {
    pv = 0;
    v35 = 0;
    v36 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    for ( i = off_1804A8000; i != (wchar_t **)&g_appCrashUIRegisterProc; i += 4 )
    {
      if ( CompareStringOrdinal(*i, -1, StringRawBuffer, -1, 1) == 2 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        v35 = -1;
        v36 = -1;
        if ( (int)CActionExecutionBroker::s_GetProgIdFromRegistration(StringRawBuffer, (unsigned __int16 **)&pv) >= 0 )
        {
          v37 = 0;
          v38 = 0;
          v39 = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
          v12 = i[1];
          v38 = -1;
          v39 = -1;
          v13 = pv;
          Window = CActionExecutionBroker::s_EnsureUserChosenAssociation(v12, v14, pv);
          if ( Window >= 0 )
          {
            v15 = v37;
            v37 = 0;
            v39 = 0;
            v38 = 0;
            if ( v13 )
              CoTaskMemFree(v13);
            pv = v15;
            v36 = -1;
            v35 = -1;
            WindowsDeleteString(0);
            string = 0;
            Window = GetAppIdFromProgId(v15, (HSTRING)&string);
            if ( Window >= 0 )
              Window = CActionExecutionBroker::_ExecuteAction(
                         this,
                         a2,
                         string,
                         v8,
                         (struct Windows::ApplicationModel::Actions::IActionActivationInfo *)a4,
                         a5);
            WindowsDeleteString(string);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
          goto LABEL_39;
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        v16 = i[1];
        v35 = -1;
        v36 = -1;
        if ( (int)CActionExecutionBroker::s_GetProgIdFromAssoc(v16, (unsigned __int16 **)&pv) < 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          v21 = i[1];
          v35 = -1;
          v36 = -1;
          v22 = CActionExecutionBroker::s_ShowOpenWith(v21, phwnd, 12, &pv);
          v18 = pv;
          Window = v22;
        }
        else
        {
          v37 = 0;
          v38 = 0;
          v39 = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
          v17 = i[1];
          v38 = -1;
          v39 = -1;
          v18 = pv;
          Window = CActionExecutionBroker::s_EnsureUserChosenAssociation(v17, v19, pv);
          if ( Window >= 0 )
          {
            v20 = v37;
            v37 = 0;
            v39 = 0;
            v38 = 0;
            if ( v18 )
              CoTaskMemFree(v18);
            pv = v20;
            v18 = v20;
            v36 = -1;
            v8 = a3;
            v35 = -1;
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
        }
        if ( Window >= 0 )
        {
          WindowsDeleteString(0);
          string = 0;
          if ( (int)GetAppIdFromProgId((unsigned __int16 *)v18, (HSTRING)&string) >= 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
            v35 = -1;
            v36 = -1;
            v23 = (ImmersiveAssociationHelpers *)WindowsGetStringRawBuffer(string, 0);
            if ( (int)ImmersiveAssociationHelpers::GetAppProgIdForProtocol(v23, StringRawBuffer, &pv, v24) >= 0 )
            {
              v25 = this;
              goto LABEL_36;
            }
          }
          v26 = ((__int64 (__fastcall *)(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, IUnknown *))i[3])(
                  v8,
                  a4);
LABEL_37:
          Window = v26;
          goto LABEL_38;
        }
        goto LABEL_39;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    v35 = -1;
    v36 = -1;
    if ( (int)CActionExecutionBroker::s_GetProgIdFromAssoc(StringRawBuffer, (unsigned __int16 **)&pv) < 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      v35 = -1;
      v36 = -1;
      v30 = CActionExecutionBroker::s_ShowOpenWith(StringRawBuffer, phwnd, 140, &pv);
      v27 = pv;
      Window = v30;
    }
    else
    {
      v37 = 0;
      v38 = 0;
      v39 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
      v38 = -1;
      v39 = -1;
      v27 = pv;
      Window = CActionExecutionBroker::s_EnsureUserChosenAssociation(StringRawBuffer, v28, pv);
      if ( Window >= 0 )
      {
        v29 = v37;
        v37 = 0;
        v39 = 0;
        v38 = 0;
        if ( v27 )
          CoTaskMemFree(v27);
        pv = v29;
        v27 = v29;
        v36 = -1;
        v6 = this;
        v35 = -1;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
    }
    if ( Window >= 0 )
    {
      WindowsDeleteString(0);
      string = 0;
      Window = GetAppIdFromProgId((unsigned __int16 *)v27, (HSTRING)&string);
      if ( Window >= 0 )
      {
        v25 = v6;
LABEL_36:
        v26 = CActionExecutionBroker::_ExecuteAction(
                v25,
                a2,
                string,
                v8,
                (struct Windows::ApplicationModel::Actions::IActionActivationInfo *)a4,
                a5);
        goto LABEL_37;
      }
LABEL_38:
      WindowsDeleteString(string);
    }
LABEL_39:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
  }
  return (unsigned int)Window;
}

```

## disassembly

```asm
0x1801252e8  mov     [rsp-38h+arg_8], rbx
0x1801252ed  mov     [rsp-38h+arg_10], r8
0x1801252f2  mov     [rsp-38h+arg_0], rcx
0x1801252f7  push    rbp
0x1801252f8  push    rsi
0x1801252f9  push    rdi
0x1801252fa  push    r12
0x1801252fc  push    r13
0x1801252fe  push    r14
0x180125300  push    r15
0x180125302  mov     rbp, rsp
0x180125305  sub     rsp, 70h
0x180125309  mov     r13, rdx
0x18012530c  mov     [rbp+phwnd], 0
0x180125314  mov     rsi, rcx
0x180125317  lea     rdx, [rbp+phwnd]; phwnd
0x18012531b  mov     rcx, r9; punk
0x18012531e  mov     r15, r9
0x180125321  mov     r12, r8
0x180125324  call    cs:__imp_IUnknown_GetWindow
0x18012532a  mov     ebx, eax
0x18012532c  test    eax, eax
0x18012532e  js      loc_1801256FC
0x180125334  xor     ebx, ebx
0x180125336  xor     edx, edx; length
0x180125338  mov     rcx, r13; string
0x18012533b  mov     [rbp+pv], rbx
0x18012533f  mov     [rbp+var_28], rbx
0x180125343  mov     [rbp+var_20], rbx
0x180125347  call    cs:__imp_WindowsGetStringRawBuffer
0x18012534d  mov     r14, rax
0x180125350  lea     rdi, off_1804A8000; "Windows.Contact.Call+telephone"
0x180125357  lea     rax, ?g_appCrashUIRegisterProc@@3PAP6AJXZA; long (*near * g_appCrashUIRegisterProc)(void)
0x18012535e  cmp     rdi, rax
0x180125361  jz      loc_1801255CE
0x180125367  mov     rcx, [rdi]; lpString1
0x18012536a  or      r9d, 0FFFFFFFFh; cchCount2
0x18012536e  or      edx, r9d; cchCount1
0x180125371  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x180125379  mov     r8, r14; lpString2
0x18012537c  call    cs:__imp_CompareStringOrdinal
0x180125382  cmp     eax, 2
0x180125385  jz      short loc_18012538D
0x180125387  add     rdi, 20h ; ' '
0x18012538b  jmp     short loc_180125357
0x18012538d  lea     rcx, [rbp+pv]
0x180125391  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180125396  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18012539a  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18012539e  mov     rcx, r14; lpString2
0x1801253a1  mov     [rbp+var_28], rsi
0x1801253a5  mov     [rbp+var_20], rsi
0x1801253a9  call    ?s_GetProgIdFromRegistration@CActionExecutionBroker@@CAJPEBGPEAPEAG@Z; CActionExecutionBroker::s_GetProgIdFromRegistration(ushort const *,ushort * *)
0x1801253ae  test    eax, eax
0x1801253b0  js      loc_18012547F
0x1801253b6  lea     rcx, [rbp+var_18]
0x1801253ba  mov     [rbp+var_18], rbx
0x1801253be  mov     [rbp+var_10], rbx
0x1801253c2  mov     [rbp+var_8], rbx
0x1801253c6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801253cb  mov     rcx, [rdi+8]
0x1801253cf  lea     rax, [rbp+var_18]
0x1801253d3  mov     [rbp+var_10], rsi
0x1801253d7  mov     [rbp+var_8], rsi
0x1801253db  mov     rsi, [rbp+pv]
0x1801253df  mov     r8, rsi
0x1801253e2  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x1801253e7  call    ?s_EnsureUserChosenAssociation@CActionExecutionBroker@@CAJPEBGPEAUHWND__@@0W4IMMERSIVE_OPENWITH_FLAGS@@PEAPEAG@Z; CActionExecutionBroker::s_EnsureUserChosenAssociation(ushort const *,HWND__ *,ushort const *,IMMERSIVE_OPENWITH_FLAGS,ushort * *)
0x1801253ec  xor     edi, edi
0x1801253ee  mov     ebx, eax
0x1801253f0  test    eax, eax
0x1801253f2  js      short loc_180125471
0x1801253f4  mov     rbx, [rbp+var_18]
0x1801253f8  mov     [rbp+var_18], rdi
0x1801253fc  mov     [rbp+var_8], rdi
0x180125400  mov     [rbp+var_10], rdi
0x180125404  test    rsi, rsi
0x180125407  jz      short loc_180125412
0x180125409  mov     rcx, rsi; pv
0x18012540c  call    cs:__imp_CoTaskMemFree
0x180125412  or      rax, 0FFFFFFFFFFFFFFFFh
0x180125416  mov     [rbp+pv], rbx
0x18012541a  xor     ecx, ecx; string
0x18012541c  mov     [rbp+var_20], rax
0x180125420  mov     [rbp+var_28], rax
0x180125424  mov     [rbp+string], rdi
0x180125428  call    cs:__imp_WindowsDeleteString
0x18012542e  lea     rdx, [rbp+string]; HSTRING
0x180125432  mov     [rbp+string], rdi
0x180125436  mov     rcx, rbx; unsigned __int16 *
0x180125439  call    GetAppIdFromProgId
0x18012543e  mov     ebx, eax
0x180125440  test    eax, eax
0x180125442  js      short loc_180125467
0x180125444  mov     rax, [rbp+arg_20]
0x180125448  mov     r9, r12; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x18012544b  mov     r8, [rbp+string]; HSTRING
0x18012544f  mov     rdx, r13; HSTRING
0x180125452  mov     rcx, [rbp+arg_0]; this
0x180125456  mov     [rsp+70h+var_48], rax; HSTRING
0x18012545b  mov     qword ptr [rsp+70h+bIgnoreCase], r15; struct Windows::ApplicationModel::Actions::IActionActivationInfo *
0x180125460  call    ?_ExecuteAction@CActionExecutionBroker@@AEAAJPEAUHSTRING__@@0PEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIActionActivationInfo@Actions@56@0@Z; CActionExecutionBroker::_ExecuteAction(HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Activation::IActivatedEventArgs *,Windows::ApplicationModel::Actions::IActionActivationInfo *,HSTRING__ *)
0x180125465  mov     ebx, eax
0x180125467  mov     rcx, [rbp+string]; string
0x18012546b  call    cs:__imp_WindowsDeleteString
0x180125471  lea     rcx, [rbp+var_18]
0x180125475  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18012547a  jmp     loc_1801256F3
0x18012547f  lea     rcx, [rbp+pv]
0x180125483  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180125488  mov     rcx, [rdi+8]; unsigned __int16 *
0x18012548c  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180125490  mov     [rbp+var_28], rsi
0x180125494  mov     [rbp+var_20], rsi
0x180125498  call    ?s_GetProgIdFromAssoc@CActionExecutionBroker@@CAJPEBGPEAPEAG@Z; CActionExecutionBroker::s_GetProgIdFromAssoc(ushort const *,ushort * *)
0x18012549d  test    eax, eax
0x18012549f  js      short loc_18012551F
0x1801254a1  lea     rcx, [rbp+var_18]
0x1801254a5  mov     [rbp+var_18], rbx
0x1801254a9  mov     [rbp+var_10], rbx
0x1801254ad  mov     [rbp+var_8], rbx
0x1801254b1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801254b6  mov     rcx, [rdi+8]
0x1801254ba  lea     rax, [rbp+var_18]
0x1801254be  mov     [rbp+var_10], rsi
0x1801254c2  mov     [rbp+var_8], rsi
0x1801254c6  mov     rsi, [rbp+pv]
0x1801254ca  mov     r8, rsi
0x1801254cd  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x1801254d2  call    ?s_EnsureUserChosenAssociation@CActionExecutionBroker@@CAJPEBGPEAUHWND__@@0W4IMMERSIVE_OPENWITH_FLAGS@@PEAPEAG@Z; CActionExecutionBroker::s_EnsureUserChosenAssociation(ushort const *,HWND__ *,ushort const *,IMMERSIVE_OPENWITH_FLAGS,ushort * *)
0x1801254d7  mov     ebx, eax
0x1801254d9  xor     eax, eax
0x1801254db  test    ebx, ebx
0x1801254dd  js      short loc_180125514
0x1801254df  mov     r12, [rbp+var_18]
0x1801254e3  mov     [rbp+var_18], rax
0x1801254e7  mov     [rbp+var_8], rax
0x1801254eb  mov     [rbp+var_10], rax
0x1801254ef  test    rsi, rsi
0x1801254f2  jz      short loc_1801254FD
0x1801254f4  mov     rcx, rsi; pv
0x1801254f7  call    cs:__imp_CoTaskMemFree
0x1801254fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180125501  mov     [rbp+pv], r12
0x180125505  mov     rsi, r12
0x180125508  mov     [rbp+var_20], rax
0x18012550c  mov     r12, [rbp+arg_10]
0x180125510  mov     [rbp+var_28], rax
0x180125514  lea     rcx, [rbp+var_18]
0x180125518  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18012551d  jmp     short loc_18012554D
0x18012551f  lea     rcx, [rbp+pv]
0x180125523  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180125528  mov     rdx, [rbp+phwnd]
0x18012552c  lea     r9, [rbp+pv]
0x180125530  mov     rcx, [rdi+8]
0x180125534  mov     r8d, 0Ch
0x18012553a  mov     [rbp+var_28], rsi
0x18012553e  mov     [rbp+var_20], rsi
0x180125542  call    ?s_ShowOpenWith@CActionExecutionBroker@@CAJPEBGPEAUHWND__@@W4IMMERSIVE_OPENWITH_FLAGS@@PEAPEAG@Z; CActionExecutionBroker::s_ShowOpenWith(ushort const *,HWND__ *,IMMERSIVE_OPENWITH_FLAGS,ushort * *)
0x180125547  mov     rsi, [rbp+pv]
0x18012554b  mov     ebx, eax
0x18012554d  test    ebx, ebx
0x18012554f  js      loc_1801256F3
0x180125555  xor     ecx, ecx; string
0x180125557  mov     [rbp+string], 0
0x18012555f  call    cs:__imp_WindowsDeleteString
0x180125565  lea     rdx, [rbp+string]; HSTRING
0x180125569  mov     [rbp+string], 0
0x180125571  mov     rcx, rsi; unsigned __int16 *
0x180125574  call    GetAppIdFromProgId
0x180125579  test    eax, eax
0x18012557b  js      short loc_1801255BA
0x18012557d  lea     rcx, [rbp+pv]
0x180125581  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180125586  mov     rcx, [rbp+string]; string
0x18012558a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012558e  xor     edx, edx; length
0x180125590  mov     [rbp+var_28], rax
0x180125594  mov     [rbp+var_20], rax
0x180125598  call    cs:__imp_WindowsGetStringRawBuffer
0x18012559e  lea     r8, [rbp+pv]; void **
0x1801255a2  mov     rdx, r14; unsigned __int16 *
0x1801255a5  mov     rcx, rax; this
0x1801255a8  call    ?GetAppProgIdForProtocol@ImmersiveAssociationHelpers@@YAJPEBG0PEAPEAG@Z; ImmersiveAssociationHelpers::GetAppProgIdForProtocol(ushort const *,ushort const *,ushort * *)
0x1801255ad  test    eax, eax
0x1801255af  js      short loc_1801255BA
0x1801255b1  mov     rcx, [rbp+arg_0]
0x1801255b5  jmp     loc_1801256CA
0x1801255ba  mov     rax, [rdi+18h]
0x1801255be  mov     rdx, r15
0x1801255c1  mov     rcx, r12
0x1801255c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801255c9  jmp     loc_1801256E7
0x1801255ce  lea     rcx, [rbp+pv]
0x1801255d2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801255d7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801255db  lea     rdx, [rbp+pv]; unsigned __int16 **
0x1801255df  mov     rcx, r14; unsigned __int16 *
0x1801255e2  mov     [rbp+var_28], rdi
0x1801255e6  mov     [rbp+var_20], rdi
0x1801255ea  call    ?s_GetProgIdFromAssoc@CActionExecutionBroker@@CAJPEBGPEAPEAG@Z; CActionExecutionBroker::s_GetProgIdFromAssoc(ushort const *,ushort * *)
0x1801255ef  test    eax, eax
0x1801255f1  js      short loc_180125671
0x1801255f3  lea     rcx, [rbp+var_18]
0x1801255f7  mov     [rbp+var_18], rbx
0x1801255fb  mov     [rbp+var_10], rbx
0x1801255ff  mov     [rbp+var_8], rbx
0x180125603  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180125608  mov     [rbp+var_10], rdi
0x18012560c  lea     rax, [rbp+var_18]
0x180125610  mov     [rbp+var_8], rdi
0x180125614  mov     rcx, r14
0x180125617  mov     rdi, [rbp+pv]
0x18012561b  mov     r8, rdi
0x18012561e  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x180125623  call    ?s_EnsureUserChosenAssociation@CActionExecutionBroker@@CAJPEBGPEAUHWND__@@0W4IMMERSIVE_OPENWITH_FLAGS@@PEAPEAG@Z; CActionExecutionBroker::s_EnsureUserChosenAssociation(ushort const *,HWND__ *,ushort const *,IMMERSIVE_OPENWITH_FLAGS,ushort * *)
0x180125628  xor     r14d, r14d
0x18012562b  mov     ebx, eax
0x18012562d  test    eax, eax
0x18012562f  js      short loc_180125666
0x180125631  mov     rsi, [rbp+var_18]
0x180125635  mov     [rbp+var_18], r14
0x180125639  mov     [rbp+var_8], r14
0x18012563d  mov     [rbp+var_10], r14
0x180125641  test    rdi, rdi
0x180125644  jz      short loc_18012564F
0x180125646  mov     rcx, rdi; pv
0x180125649  call    cs:__imp_CoTaskMemFree
0x18012564f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180125653  mov     [rbp+pv], rsi
0x180125657  mov     rdi, rsi
0x18012565a  mov     [rbp+var_20], rax
0x18012565e  mov     rsi, [rbp+arg_0]
0x180125662  mov     [rbp+var_28], rax
0x180125666  lea     rcx, [rbp+var_18]
0x18012566a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18012566f  jmp     short loc_1801256A1
0x180125671  lea     rcx, [rbp+pv]
0x180125675  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18012567a  mov     rdx, [rbp+phwnd]
0x18012567e  lea     r9, [rbp+pv]
0x180125682  mov     r8d, 8Ch
0x180125688  mov     [rbp+var_28], rdi
0x18012568c  mov     rcx, r14
0x18012568f  mov     [rbp+var_20], rdi
0x180125693  call    ?s_ShowOpenWith@CActionExecutionBroker@@CAJPEBGPEAUHWND__@@W4IMMERSIVE_OPENWITH_FLAGS@@PEAPEAG@Z; CActionExecutionBroker::s_ShowOpenWith(ushort const *,HWND__ *,IMMERSIVE_OPENWITH_FLAGS,ushort * *)
0x180125698  mov     rdi, [rbp+pv]
0x18012569c  mov     ebx, eax
0x18012569e  xor     r14d, r14d
0x1801256a1  test    ebx, ebx
0x1801256a3  js      short loc_1801256F3
0x1801256a5  xor     ecx, ecx; string
0x1801256a7  mov     [rbp+string], r14
0x1801256ab  call    cs:__imp_WindowsDeleteString
0x1801256b1  lea     rdx, [rbp+string]; HSTRING
0x1801256b5  mov     [rbp+string], r14
0x1801256b9  mov     rcx, rdi; unsigned __int16 *
0x1801256bc  call    GetAppIdFromProgId
0x1801256c1  mov     ebx, eax
0x1801256c3  test    eax, eax
0x1801256c5  js      short loc_1801256E9
0x1801256c7  mov     rcx, rsi; this
0x1801256ca  mov     rax, [rbp+arg_20]
0x1801256ce  mov     r9, r12; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x1801256d1  mov     r8, [rbp+string]; HSTRING
0x1801256d5  mov     rdx, r13; HSTRING
0x1801256d8  mov     [rsp+70h+var_48], rax; HSTRING
0x1801256dd  mov     qword ptr [rsp+70h+bIgnoreCase], r15; struct Windows::ApplicationModel::Actions::IActionActivationInfo *
0x1801256e2  call    ?_ExecuteAction@CActionExecutionBroker@@AEAAJPEAUHSTRING__@@0PEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIActionActivationInfo@Actions@56@0@Z; CActionExecutionBroker::_ExecuteAction(HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Activation::IActivatedEventArgs *,Windows::ApplicationModel::Actions::IActionActivationInfo *,HSTRING__ *)
0x1801256e7  mov     ebx, eax
0x1801256e9  mov     rcx, [rbp+string]; string
0x1801256ed  call    cs:__imp_WindowsDeleteString
0x1801256f3  lea     rcx, [rbp+pv]
0x1801256f7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801256fc  mov     eax, ebx
0x1801256fe  mov     rbx, [rsp+70h+arg_8]
0x180125706  add     rsp, 70h
0x18012570a  pop     r15
0x18012570c  pop     r14
0x18012570e  pop     r13
0x180125710  pop     r12
0x180125712  pop     rdi
0x180125713  pop     rsi
0x180125714  pop     rbp
0x180125715  retn
```

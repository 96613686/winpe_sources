# VaultCDSSaveCredential(ushort const *,ushort const *,eVaultType,_GUID const *,uchar)

- ea: `0x180020030`
- end: `0x18002078b`
- name: `?VaultCDSSaveCredential@@YAJPEBG0W4eVaultType@@PEBU_GUID@@E@Z`
- size: `1883`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000f7d0`
- `0x180023c90`

## callees

- `0x180003140`
- `0x18000df38`
- `0x18001cea8`
- `0x18001f668`
- `0x180020030`
- `0x180020794`
- `0x180033178`
- `0x180038c6c`
- `0x18003a580`
- `0x18003b148`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004518c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002015d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002015d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002053a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002053a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020669`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020669`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020121`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020103`
- `ext-ms-win-security-vaultcds-l1-1-0!VaultCDSSaveItem` at `0x18002071a`
- `ext-ms-win-security-vaultcds-l1-1-0!VaultCDSSaveItem` at `0x18002071a`

## string_xrefs

- `0x1800200fc`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x18002030d`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x1800203ce`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x180020466`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x180020548`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18002058e`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x1800205e0`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18002061d`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x1800206bf`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall VaultCDSSaveCredential(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned int a3,
        struct _GUID *a4,
        char a5)
{
  struct _SETTING_UNIT *v9; // r15
  unsigned int RoamingCredential; // ebx
  IUnknown *v11; // rcx
  HRESULT v12; // eax
  int ActivationFactory; // eax
  HRESULT v14; // eax
  int DefaultAccount; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 (__fastcall **v18)(__int64, GUID *, __int64 **); // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // r8d
  int Account; // eax
  int v25; // eax
  struct _FILETIME *v26; // r8
  int dwAuthnLevel; // [rsp+20h] [rbp-B1h]
  int dwAuthnLevela; // [rsp+20h] [rbp-B1h]
  char v29[8]; // [rsp+40h] [rbp-91h] BYREF
  __int64 *v30; // [rsp+48h] [rbp-89h] BYREF
  IUnknown *pProxy; // [rsp+50h] [rbp-81h] BYREF
  __int64 (__fastcall ***v32)(__int64, GUID *, __int64 **); // [rsp+58h] [rbp-79h] BYREF
  __int64 *v33; // [rsp+60h] [rbp-71h] BYREF
  __int64 v34; // [rsp+68h] [rbp-69h] BYREF
  __int64 v35; // [rsp+70h] [rbp-61h] BYREF
  struct _SETTING_UNIT *v36; // [rsp+78h] [rbp-59h] BYREF
  int v37; // [rsp+80h] [rbp-51h]
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+88h] [rbp-49h] BYREF
  _OWORD v39[2]; // [rsp+98h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-19h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  pProxy = 0;
  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
  memset(v39, 0, sizeof(v39));
  v9 = 0;
  v36 = 0;
  v37 = 0;
  v35 = 0;
  v29[0] = 0;
  if ( a1 && a2 )
  {
    if ( ((a3 - 1) & 0xFFFFFFFA) == 0 && a3 != 2 )
    {
      RoamingCredential = CheckSpecialCaller(v29);
      if ( RoamingCredential )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids,
            RoamingCredential);
        if ( (int)RoamingCredential > 0 )
          RoamingCredential = (unsigned __int16)RoamingCredential | 0x80070000;
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
        if ( pProxy )
          ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
        return RoamingCredential;
      }
      if ( v29[0] )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
        RoamingCredential = 0;
        goto LABEL_84;
      }
      v11 = pProxy;
      pProxy = 0;
      if ( v11 )
        ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
      string = 0;
      v12 = WindowsCreateStringReference(
              L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
              0x40u,
              &hstringHeader,
              &string);
      if ( v12 < 0 )
      {
        RaiseException(v12, 1u, 0, 0);
        __debugbreak();
      }
      ActivationFactory = RoGetActivationFactory(string, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &pProxy);
      RoamingCredential = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x245,
          (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
          (const char *)(unsigned int)ActivationFactory,
          dwAuthnLevel);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
        if ( pProxy )
          ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
        return RoamingCredential;
      }
      v14 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 2u, 3u, 0, 0x20u);
      RoamingCredential = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x252,
          (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
          (const char *)(unsigned int)v14,
          dwAuthnLevela);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
      }
      else
      {
        if ( a3 == 1 )
        {
          v30 = 0;
          DefaultAccount = GetDefaultAccount(pProxy, &v30);
          RoamingCredential = DefaultAccount;
          if ( DefaultAccount < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x25A,
              (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
              (const char *)(unsigned int)DefaultAccount,
              dwAuthnLevela);
            if ( v30 )
              (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
            CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
            if ( pProxy )
              ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
            return RoamingCredential;
          }
        }
        else
        {
          v30 = 0;
          Account = FindAccount(a3, a2, &v30);
          RoamingCredential = Account;
          if ( Account < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x25F,
              (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
              (const char *)(unsigned int)Account,
              dwAuthnLevela);
            wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v30);
            CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
            goto LABEL_84;
          }
        }
        if ( v30 )
        {
          v32 = 0;
          v16 = *v30;
          v32 = 0;
          v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(__int64, GUID *, __int64 **)))(v16 + 48))(
                  v30,
                  &v32);
          RoamingCredential = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x264,
              (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
              (const char *)(unsigned int)v17,
              dwAuthnLevela);
            wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v32);
            wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v30);
            CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
          }
          else
          {
            v33 = 0;
            v18 = *v32;
            v33 = 0;
            v19 = (*v18)((__int64)v32, &GUID_da1c518b_970d_4d49_825c_f2706f8ca7fe, &v33);
            RoamingCredential = v19;
            if ( v19 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x267,
                (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
                (const char *)(unsigned int)v19,
                dwAuthnLevela);
              wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v33);
              wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v32);
              wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v30);
              CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
            }
            else
            {
              v34 = 0;
              v20 = *v33;
              v34 = 0;
              v21 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v20 + 48))(v33, &v34);
              RoamingCredential = v21;
              if ( v21 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x26A,
                  (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
                  (const char *)(unsigned int)v21,
                  dwAuthnLevela);
                if ( v34 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                if ( v33 )
                  (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
                if ( v32 )
                  ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **)))(*v32)[2])(v32);
                if ( v30 )
                  (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
                CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
                if ( pProxy )
                  ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
                return RoamingCredential;
              }
              if ( a5 )
              {
                SystemTimeAsFileTime[0] = (struct _FILETIME)a1;
                SystemTimeAsFileTime[1].dwLowDateTime = 0;
                GetSystemTimeAsFileTime((LPFILETIME)&SystemTimeAsFileTime[1].dwHighDateTime);
                memset((char *)v39 + 8, 0, 17);
              }
              else
              {
                RoamingCredential = VaultGetRoamingCredential(
                                      (struct IVaultAllocator *)VaultGlobals::g_HeapAlloc,
                                      a1,
                                      v22,
                                      &v36,
                                      a4);
                if ( RoamingCredential )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      29,
                      WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids,
                      RoamingCredential);
                  if ( (int)RoamingCredential > 0 )
                    RoamingCredential = (unsigned __int16)RoamingCredential | 0x80070000;
                  if ( v34 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                  if ( v33 )
                    (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
                  if ( v32 )
                    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **)))(*v32)[2])(v32);
                  if ( v30 )
                    (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
                  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
                  if ( pProxy )
                    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
                  return RoamingCredential;
                }
                v9 = v36;
              }
              v25 = FilterCredential(a4, a1, (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **))v30);
              RoamingCredential = v25;
              if ( v25 >= 0 )
              {
                RoamingCredential = 0;
                if ( (unsigned __int8)IsVaultCDSSaveItemPresent() )
                {
                  v26 = SystemTimeAsFileTime;
                  if ( !a5 )
                    v26 = (struct _FILETIME *)v9;
                  RoamingCredential = VaultCDSSaveItem(v34, v30, v26);
                }
                wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v34);
                wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v33);
                wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v32);
                wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v30);
                CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x287,
                  (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
                  (const char *)(unsigned int)v25,
                  dwAuthnLevela);
                wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v34);
                wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v33);
                wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v32);
                wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v30);
                CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
              }
            }
          }
        }
        else
        {
          wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v30);
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
          RoamingCredential = -2147023579;
        }
      }
LABEL_84:
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&pProxy);
      return RoamingCredential;
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
  }
  else
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v35);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&pProxy);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180020030  push    rbp
0x180020032  push    rbx
0x180020033  push    rsi
0x180020034  push    rdi
0x180020035  push    r12
0x180020037  push    r13
0x180020039  push    r14
0x18002003b  push    r15
0x18002003d  lea     rbp, [rsp-17h]
0x180020042  sub     rsp, 0E8h
0x180020049  mov     rax, cs:__security_cookie
0x180020050  xor     rax, rsp
0x180020053  mov     [rbp+4Fh+var_48], rax
0x180020057  mov     r12, r9
0x18002005a  mov     edi, r8d
0x18002005d  mov     r14, rdx
0x180020060  mov     rsi, rcx
0x180020063  xor     r13d, r13d
0x180020066  mov     [rsp+120h+pProxy], r13
0x18002006b  xorps   xmm0, xmm0
0x18002006e  movups  xmmword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x180020072  movups  [rbp+4Fh+var_88], xmm0
0x180020076  movups  [rbp+4Fh+var_78], xmm0
0x18002007a  mov     r15d, r13d
0x18002007d  mov     [rbp+4Fh+var_A8], r13
0x180020081  mov     [rbp+4Fh+var_A0], r13d
0x180020085  mov     [rbp+4Fh+var_B0], r13
0x180020089  mov     [rsp+120h+var_E0], r13b
0x18002008e  test    rcx, rcx
0x180020091  jz      loc_180020772
0x180020097  test    rdx, rdx
0x18002009a  jz      loc_180020772
0x1800200a0  lea     eax, [r8-1]
0x1800200a4  test    eax, 0FFFFFFFAh
0x1800200a9  jnz     loc_180020342
0x1800200af  cmp     r8d, 2
0x1800200b3  jz      loc_180020342
0x1800200b9  lea     rcx, [rsp+120h+var_E0]
0x1800200be  call    _CheckSpecialCaller
0x1800200c3  mov     ebx, eax
0x1800200c5  test    eax, eax
0x1800200c7  jnz     loc_18002036D
0x1800200cd  cmp     [rsp+120h+var_E0], r13b
0x1800200d2  jnz     loc_1800204DC
0x1800200d8  mov     rcx, [rsp+120h+pProxy]
0x1800200dd  mov     [rsp+120h+pProxy], r13
0x1800200e2  test    rcx, rcx
0x1800200e5  jnz     loc_18002051D
0x1800200eb  mov     [rbp+4Fh+string], r13
0x1800200ef  lea     r9, [rbp+4Fh+string]; string
0x1800200f3  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800200f7  mov     edx, 40h ; '@'; length
0x1800200fc  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180020103  call    cs:__imp_WindowsCreateStringReference
0x180020109  test    eax, eax
0x18002010b  js      loc_18002052E
0x180020111  lea     r8, [rsp+120h+pProxy]
0x180020116  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x18002011d  mov     rcx, [rbp+4Fh+string]
0x180020121  call    cs:__imp_RoGetActivationFactory
0x180020127  mov     ebx, eax
0x180020129  test    eax, eax
0x18002012b  js      loc_180020306
0x180020131  mov     [rsp+120h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180020139  mov     [rsp+120h+pAuthInfo], r13; pAuthInfo
0x18002013e  mov     [rsp+120h+dwImpLevel], 3; dwImpLevel
0x180020146  mov     [rsp+120h+dwAuthnLevel], 2; int
0x18002014e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180020152  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180020155  mov     r8d, edx; dwAuthzSvc
0x180020158  mov     rcx, [rsp+120h+pProxy]; pProxy
0x18002015d  call    cs:__imp_CoSetProxyBlanket
0x180020163  mov     ebx, eax
0x180020165  test    eax, eax
0x180020167  js      loc_180020541
0x18002016d  cmp     edi, 1
0x180020170  jnz     loc_180020569
0x180020176  mov     [rsp+120h+var_D8], r13
0x18002017b  lea     rdx, [rsp+120h+var_D8]
0x180020180  mov     rcx, [rsp+120h+pProxy]
0x180020185  call    _GetDefaultAccount
0x18002018a  mov     ebx, eax
0x18002018c  test    eax, eax
0x18002018e  js      loc_18002045F
0x180020194  mov     rcx, [rsp+120h+var_D8]
0x180020199  test    rcx, rcx
0x18002019c  jz      loc_1800205BA
0x1800201a2  mov     [rbp+4Fh+var_C8], r13
0x1800201a6  mov     rax, [rcx]
0x1800201a9  mov     [rbp+4Fh+var_C8], r13
0x1800201ad  lea     rdx, [rbp+4Fh+var_C8]
0x1800201b1  mov     rax, [rax+30h]
0x1800201b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201ba  mov     ebx, eax
0x1800201bc  test    eax, eax
0x1800201be  js      loc_1800205D9
0x1800201c4  mov     [rbp+4Fh+var_C0], r13
0x1800201c8  mov     rcx, [rbp+4Fh+var_C8]
0x1800201cc  mov     rax, [rcx]
0x1800201cf  mov     [rbp+4Fh+var_C0], r13
0x1800201d3  lea     r8, [rbp+4Fh+var_C0]
0x1800201d7  lea     rdx, _GUID_da1c518b_970d_4d49_825c_f2706f8ca7fe
0x1800201de  mov     rax, [rax]
0x1800201e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201e6  mov     ebx, eax
0x1800201e8  test    eax, eax
0x1800201ea  js      loc_180020616
0x1800201f0  mov     [rbp+4Fh+var_B8], r13
0x1800201f4  mov     rcx, [rbp+4Fh+var_C0]
0x1800201f8  mov     rax, [rcx]
0x1800201fb  mov     [rbp+4Fh+var_B8], r13
0x1800201ff  lea     rdx, [rbp+4Fh+var_B8]
0x180020203  mov     rax, [rax+30h]
0x180020207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002020c  mov     ebx, eax
0x18002020e  test    eax, eax
0x180020210  js      loc_1800203C7
0x180020216  mov     dil, [rbp+4Fh+arg_20]
0x18002021a  test    dil, dil
0x18002021d  jnz     loc_18002065D
0x180020223  mov     qword ptr [rsp+120h+dwAuthnLevel], r12; int
0x180020228  lea     r9, [rbp+4Fh+var_A8]; struct _SETTING_UNIT **
0x18002022c  mov     rdx, rsi; unsigned __int16 *
0x18002022f  lea     rcx, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; struct IVaultAllocator *
0x180020236  call    ?VaultGetRoamingCredential@@YAKPEAUIVaultAllocator@@PEBGKPEAPEAU_SETTING_UNIT@@PEBU_GUID@@@Z; VaultGetRoamingCredential(IVaultAllocator *,ushort const *,ulong,_SETTING_UNIT * *,_GUID const *)
0x18002023b  mov     ebx, eax
0x18002023d  test    eax, eax
0x18002023f  jz      loc_18002069A
0x180020245  lea     rax, WPP_GLOBAL_Control
0x18002024c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020253  cmp     rcx, rax
0x180020256  jz      short loc_180020262
0x180020258  test    byte ptr [rcx+1Ch], 2
0x18002025c  jnz     loc_18002067D
0x180020262  test    ebx, ebx
0x180020264  jg      loc_1800203AE
0x18002026a  mov     rcx, [rbp+4Fh+var_B8]
0x18002026e  test    rcx, rcx
0x180020271  jz      short loc_180020280
0x180020273  mov     rax, [rcx]
0x180020276  mov     rax, [rax+10h]
0x18002027a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002027f  nop
0x180020280  mov     rcx, [rbp+4Fh+var_C0]
0x180020284  test    rcx, rcx
0x180020287  jz      short loc_180020296
0x180020289  mov     rax, [rcx]
0x18002028c  mov     rax, [rax+10h]
0x180020290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020295  nop
0x180020296  mov     rcx, [rbp+4Fh+var_C8]
0x18002029a  test    rcx, rcx
0x18002029d  jz      short loc_1800202AC
0x18002029f  mov     rax, [rcx]
0x1800202a2  mov     rax, [rax+10h]
0x1800202a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202ab  nop
0x1800202ac  mov     rcx, [rsp+120h+var_D8]
0x1800202b1  test    rcx, rcx
0x1800202b4  jz      short loc_1800202C3
0x1800202b6  mov     rax, [rcx]
0x1800202b9  mov     rax, [rax+10h]
0x1800202bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202c2  nop
0x1800202c3  lea     rcx, [rbp+4Fh+var_B0]
0x1800202c7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800202cc  nop
0x1800202cd  mov     rcx, [rsp+120h+pProxy]
0x1800202d2  test    rcx, rcx
0x1800202d5  jz      short loc_1800202E4
0x1800202d7  mov     rdx, [rcx]
0x1800202da  mov     rax, [rdx+10h]
0x1800202de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202e3  nop
0x1800202e4  mov     eax, ebx
0x1800202e6  mov     rcx, [rbp+4Fh+var_48]
0x1800202ea  xor     rcx, rsp; StackCookie
0x1800202ed  call    __security_check_cookie
0x1800202f2  add     rsp, 0E8h
0x1800202f9  pop     r15
0x1800202fb  pop     r14
0x1800202fd  pop     r13
0x1800202ff  pop     r12
0x180020301  pop     rdi
0x180020302  pop     rsi
0x180020303  pop     rbx
0x180020304  pop     rbp
0x180020305  retn
0x180020306  mov     rcx, [rbp+57h]; this
0x18002030a  mov     r9d, ebx; char *
0x18002030d  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x180020314  mov     edx, 245h; void *
0x180020319  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002031e  nop
0x18002031f  lea     rcx, [rbp+4Fh+var_B0]
0x180020323  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020328  nop
0x180020329  mov     rcx, [rsp+120h+pProxy]
0x18002032e  test    rcx, rcx
0x180020331  jz      short loc_180020340
0x180020333  mov     rax, [rcx]
0x180020336  mov     rax, [rax+10h]
0x18002033a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002033f  nop
0x180020340  jmp     short loc_1800202E4
0x180020342  lea     rcx, [rbp+4Fh+var_B0]
0x180020346  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002034b  nop
0x18002034c  mov     rcx, [rsp+120h+pProxy]
0x180020351  test    rcx, rcx
0x180020354  jz      short loc_180020363
0x180020356  mov     rax, [rcx]
0x180020359  mov     rax, [rax+10h]
0x18002035d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020362  nop
0x180020363  mov     eax, 80070057h
0x180020368  jmp     loc_1800202E6
0x18002036d  lea     rax, WPP_GLOBAL_Control
0x180020374  mov     rcx, cs:WPP_GLOBAL_Control
0x18002037b  cmp     rcx, rax
0x18002037e  jnz     loc_1800204B5
0x180020384  test    ebx, ebx
0x180020386  jg      short loc_1800203BC
0x180020388  lea     rcx, [rbp+4Fh+var_B0]
0x18002038c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020391  nop
0x180020392  mov     rcx, [rsp+120h+pProxy]
0x180020397  test    rcx, rcx
0x18002039a  jz      short loc_1800203A9
0x18002039c  mov     rdx, [rcx]
0x18002039f  mov     rax, [rdx+10h]
0x1800203a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203a8  nop
0x1800203a9  jmp     loc_1800202E4
0x1800203ae  movzx   ebx, bx
0x1800203b1  or      ebx, 80070000h
0x1800203b7  jmp     loc_18002026A
0x1800203bc  movzx   ebx, bx
0x1800203bf  or      ebx, 80070000h
0x1800203c5  jmp     short loc_180020388
0x1800203c7  mov     rcx, [rbp+57h]; this
0x1800203cb  mov     r9d, ebx; char *
0x1800203ce  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x1800203d5  mov     edx, 26Ah; void *
0x1800203da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800203df  nop
0x1800203e0  mov     rcx, [rbp+4Fh+var_B8]
0x1800203e4  test    rcx, rcx
0x1800203e7  jz      short loc_1800203F6
0x1800203e9  mov     rax, [rcx]
0x1800203ec  mov     rax, [rax+10h]
0x1800203f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203f5  nop
0x1800203f6  mov     rcx, [rbp+4Fh+var_C0]
0x1800203fa  test    rcx, rcx
0x1800203fd  jz      short loc_18002040C
0x1800203ff  mov     rax, [rcx]
0x180020402  mov     rax, [rax+10h]
0x180020406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002040b  nop
0x18002040c  mov     rcx, [rbp+4Fh+var_C8]
0x180020410  test    rcx, rcx
0x180020413  jz      short loc_180020422
0x180020415  mov     rax, [rcx]
0x180020418  mov     rax, [rax+10h]
0x18002041c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020421  nop
0x180020422  mov     rcx, [rsp+120h+var_D8]
0x180020427  test    rcx, rcx
0x18002042a  jz      short loc_180020439
0x18002042c  mov     rax, [rcx]
0x18002042f  mov     rax, [rax+10h]
0x180020433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020438  nop
0x180020439  lea     rcx, [rbp+4Fh+var_B0]
0x18002043d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020442  nop
0x180020443  mov     rcx, [rsp+120h+pProxy]
0x180020448  test    rcx, rcx
0x18002044b  jz      short loc_18002045A
0x18002044d  mov     rax, [rcx]
0x180020450  mov     rax, [rax+10h]
0x180020454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020459  nop
0x18002045a  jmp     loc_1800202E4
0x18002045f  mov     rcx, [rbp+57h]; this
0x180020463  mov     r9d, ebx; char *
0x180020466  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18002046d  mov     edx, 25Ah; void *
0x180020472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020477  nop
0x180020478  mov     rcx, [rsp+120h+var_D8]
0x18002047d  test    rcx, rcx
0x180020480  jz      short loc_18002048F
0x180020482  mov     rax, [rcx]
0x180020485  mov     rax, [rax+10h]
0x180020489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002048e  nop
0x18002048f  lea     rcx, [rbp+4Fh+var_B0]
0x180020493  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
  ... truncated ...
```

# ActiveSystemUserUtilities::GetIUserSID(Windows::System::IUser *,CSpDynamicString &)

- ea: `0x1800cedc8`
- end: `0x1800cf05a`
- name: `?GetIUserSID@ActiveSystemUserUtilities@@SAJPEAUIUser@System@Windows@@AEAVCSpDynamicString@@@Z`
- size: `658`
- prototype: `static int(struct Windows::System::IUser *, struct CSpDynamicString *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180058440`
- `0x1800cc140`

## callees

- `0x18000a590`
- `0x18000bec4`
- `0x180011cb0`
- `0x180026508`
- `0x180026ae4`
- `0x18005cd84`
- `0x18007e5ac`
- `0x1800c94dc`
- `0x1800cec88`
- `0x1800cedc8`
- `0x1800cf060`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cef3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cef3e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cef4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cef4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cef13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cef13`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800cefbe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800cefbe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ceefa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800cef83`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ceefa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800cef83`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800ceeaa`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800ceeaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ActiveSystemUserUtilities::GetIUserSID(
        struct Windows::System::IUser *a1,
        struct CSpDynamicString *a2)
{
  int UserManagerStatics; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // r9
  __int64 v10; // rdx
  signed int LastError; // eax
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  wil::details *v14; // rdi
  const char *v15; // r9
  void *v16; // rdx
  const char *v17; // r9
  int appended; // eax
  void *v19; // rdx
  int ReturnLength; // [rsp+20h] [rbp-30h]
  int ReturnLengtha; // [rsp+20h] [rbp-30h]
  __int64 v23; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-18h] BYREF
  struct Windows::System::Internal::IUserManagerStatics *v25; // [rsp+40h] [rbp-10h] BYREF
  __int64 v26; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD TokenInformationLength; // [rsp+80h] [rbp+30h] BYREF
  HANDLE TokenHandle; // [rsp+88h] [rbp+38h] BYREF

  v25 = 0;
  UserManagerStatics = ActiveSystemUserUtilities::GetUserManagerStatics(&v25);
  v5 = UserManagerStatics;
  if ( UserManagerStatics >= 0 )
  {
    v23 = 0;
    v6 = (**(__int64 (__fastcall ***)(struct Windows::System::Internal::IUserManagerStatics *, GUID *, __int64 *))v25)(
           v25,
           &GUID_100eb64b_b24c_4c38_8964_720d926d05a4,
           &v23);
    v5 = v6;
    if ( v6 < 0 )
    {
      v7 = 74;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\activesystemuserutilities.cpp",
        (const char *)(unsigned int)v6,
        ReturnLength);
LABEL_6:
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v23);
      goto LABEL_31;
    }
    v26 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *, __int64 *))(*(_QWORD *)v23 + 136LL))(
           v23,
           a1,
           &v26);
    v5 = v6;
    if ( v6 < 0 )
    {
      v7 = 77;
      goto LABEL_5;
    }
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    v8 = UMgrQueryUserToken(v26, &TokenHandle);
    v5 = v8;
    if ( v8 >= 0 )
    {
      TokenInformationLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
      {
        v5 = -2147418113;
        v9 = 2147549183LL;
        v10 = 84;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError == 122 )
        {
          v12 = TokenInformationLength;
          ProcessHeap = GetProcessHeap();
          v14 = (wil::details *)HeapAlloc(ProcessHeap, 0, v12);
          if ( v14 )
          {
            if ( GetTokenInformation(TokenHandle, TokenUser, v14, TokenInformationLength, &TokenInformationLength) )
            {
              StringSid = 0;
              if ( ConvertSidToStringSidW(*(PSID *)v14, &StringSid) )
              {
                SPPIPEINFO::~SPPIPEINFO(a2);
                appended = CSpDynamicString::AppendHR(a2, StringSid);
                v5 = appended;
                if ( appended >= 0 )
                {
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
                  wil::details::FreeProcessHeap(v14, v19);
                  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
                  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v23);
                  v5 = 0;
                  goto LABEL_31;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x62,
                  (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\activesystemuserutilities.cpp",
                  (const char *)(unsigned int)appended,
                  ReturnLengtha);
              }
              else
              {
                v5 = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x5F,
                       (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\activesystemuserutilities.cpp",
                       v17);
              }
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
            }
            else
            {
              v5 = wil::details::in1diag3::Return_GetLastError(
                     retaddr,
                     (void *)0x5C,
                     (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\activesystemuserutilities.cpp",
                     v15);
            }
            wil::details::FreeProcessHeap(v14, v16);
            goto LABEL_12;
          }
          v5 = -2147024882;
          v9 = 2147942414LL;
          v10 = 90;
        }
        else
        {
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          if ( (v5 & 0x80000000) == 0 )
            goto LABEL_12;
          v9 = v5;
          v10 = 87;
        }
      }
    }
    else
    {
      v9 = (unsigned int)v8;
      v10 = 80;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\activesystemuserutilities.cpp",
      (const char *)v9,
      ReturnLength);
LABEL_12:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x47,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\activesystemuserutilities.cpp",
    (const char *)(unsigned int)UserManagerStatics,
    ReturnLength);
LABEL_31:
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v25);
  return v5;
}

```

## disassembly

```asm
0x1800cedc8  mov     [rsp-18h+arg_0], rbx
0x1800cedcd  push    rbp
0x1800cedce  push    rsi
0x1800cedcf  push    rdi
0x1800cedd0  mov     rbp, rsp
0x1800cedd3  sub     rsp, 50h
0x1800cedd7  mov     rsi, rdx
0x1800cedda  mov     rdi, rcx
0x1800ceddd  mov     [rbp+var_10], 0
0x1800cede5  lea     rcx, [rbp+var_10]; struct Windows::System::Internal::IUserManagerStatics **
0x1800cede9  call    ?GetUserManagerStatics@ActiveSystemUserUtilities@@SAJPEAPEAUIUserManagerStatics@Internal@System@Windows@@@Z; ActiveSystemUserUtilities::GetUserManagerStatics(Windows::System::Internal::IUserManagerStatics * *)
0x1800cedee  mov     ebx, eax
0x1800cedf0  test    eax, eax
0x1800cedf2  jns     short loc_1800CEE11
0x1800cedf4  mov     rcx, [rbp+18h]; this
0x1800cedf8  mov     r9d, eax; char *
0x1800cedfb  lea     r8, aOnecoreuapEndu_122; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800cee02  mov     edx, 47h ; 'G'; void *
0x1800cee07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cee0c  jmp     loc_1800CF042
0x1800cee11  mov     [rbp+var_20], 0
0x1800cee19  mov     rcx, [rbp+var_10]
0x1800cee1d  mov     rax, [rcx]
0x1800cee20  lea     r8, [rbp+var_20]
0x1800cee24  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x1800cee2b  mov     rax, [rax]
0x1800cee2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cee33  mov     ebx, eax
0x1800cee35  test    eax, eax
0x1800cee37  jns     short loc_1800CEE60
0x1800cee39  mov     edx, 4Ah ; 'J'; void *
0x1800cee3e  lea     r8, aOnecoreuapEndu_122; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800cee45  mov     r9d, eax; char *
0x1800cee48  mov     rcx, [rbp+18h]; this
0x1800cee4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cee51  nop
0x1800cee52  lea     rcx, [rbp+var_20]
0x1800cee56  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800cee5b  jmp     loc_1800CF042
0x1800cee60  mov     [rbp+var_8], 0
0x1800cee68  mov     rcx, [rbp+var_20]
0x1800cee6c  mov     rax, [rcx]
0x1800cee6f  lea     r8, [rbp+var_8]
0x1800cee73  mov     rdx, rdi
0x1800cee76  mov     rax, [rax+88h]
0x1800cee7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cee82  mov     ebx, eax
0x1800cee84  test    eax, eax
0x1800cee86  jns     short loc_1800CEE8F
0x1800cee88  mov     edx, 4Dh ; 'M'
0x1800cee8d  jmp     short loc_1800CEE3E
0x1800cee8f  mov     [rbp+TokenHandle], 0
0x1800cee97  xor     edx, edx
0x1800cee99  lea     rcx, [rbp+TokenHandle]
0x1800cee9d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800ceea2  lea     rdx, [rbp+TokenHandle]
0x1800ceea6  mov     rcx, [rbp+var_8]
0x1800ceeaa  call    cs:__imp_UMgrQueryUserToken
0x1800ceeb0  mov     ebx, eax
0x1800ceeb2  test    eax, eax
0x1800ceeb4  jns     short loc_1800CEEDC
0x1800ceeb6  mov     r9d, eax; char *
0x1800ceeb9  mov     edx, 50h ; 'P'; void *
0x1800ceebe  lea     r8, aOnecoreuapEndu_122; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800ceec5  mov     rcx, [rbp+18h]; this
0x1800ceec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ceece  lea     rcx, [rbp+TokenHandle]
0x1800ceed2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ceed7  jmp     loc_1800CEE52
0x1800ceedc  mov     [rbp+TokenInformationLength], 0
0x1800ceee3  lea     rax, [rbp+TokenInformationLength]
0x1800ceee7  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x1800ceeec  xor     r9d, r9d; TokenInformationLength
0x1800ceeef  xor     r8d, r8d; TokenInformation
0x1800ceef2  lea     edx, [r9+1]; TokenInformationClass
0x1800ceef6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ceefa  call    cs:__imp_GetTokenInformation
0x1800cef00  test    eax, eax
0x1800cef02  jz      short loc_1800CEF13
0x1800cef04  mov     ebx, 8000FFFFh
0x1800cef09  mov     r9d, ebx
0x1800cef0c  mov     edx, 54h ; 'T'
0x1800cef11  jmp     short loc_1800CEEBE
0x1800cef13  call    cs:__imp_GetLastError
0x1800cef19  mov     ebx, eax
0x1800cef1b  cmp     eax, 7Ah ; 'z'
0x1800cef1e  jz      short loc_1800CEF3B
0x1800cef20  test    eax, eax
0x1800cef22  jle     short loc_1800CEF2D
0x1800cef24  movzx   ebx, ax
0x1800cef27  or      ebx, 80070000h
0x1800cef2d  test    ebx, ebx
0x1800cef2f  jns     short loc_1800CEECE
0x1800cef31  mov     r9d, ebx
0x1800cef34  mov     edx, 57h ; 'W'
0x1800cef39  jmp     short loc_1800CEEBE
0x1800cef3b  mov     ebx, [rbp+TokenInformationLength]
0x1800cef3e  call    cs:__imp_GetProcessHeap
0x1800cef44  mov     r8d, ebx; dwBytes
0x1800cef47  xor     edx, edx; dwFlags
0x1800cef49  mov     rcx, rax; hHeap
0x1800cef4c  call    cs:__imp_HeapAlloc
0x1800cef52  mov     rdi, rax
0x1800cef55  test    rax, rax
0x1800cef58  jnz     short loc_1800CEF6A
0x1800cef5a  mov     ebx, 8007000Eh
0x1800cef5f  mov     r9d, ebx
0x1800cef62  lea     edx, [rax+5Ah]
0x1800cef65  jmp     loc_1800CEEBE
0x1800cef6a  lea     rax, [rbp+TokenInformationLength]
0x1800cef6e  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x1800cef73  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800cef77  mov     r8, rdi; TokenInformation
0x1800cef7a  mov     edx, 1; TokenInformationClass
0x1800cef7f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800cef83  call    cs:__imp_GetTokenInformation
0x1800cef89  test    eax, eax
0x1800cef8b  jnz     short loc_1800CEFAF
0x1800cef8d  mov     rcx, [rbp+18h]; this
0x1800cef91  lea     r8, aOnecoreuapEndu_122; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800cef98  lea     edx, [rax+5Ch]; void *
0x1800cef9b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cefa0  mov     ebx, eax
0x1800cefa2  mov     rcx, rdi; this
0x1800cefa5  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800cefaa  jmp     loc_1800CEECE
0x1800cefaf  mov     [rbp+StringSid], 0
0x1800cefb7  lea     rdx, [rbp+StringSid]; StringSid
0x1800cefbb  mov     rcx, [rdi]; Sid
0x1800cefbe  call    cs:__imp_ConvertSidToStringSidW
0x1800cefc4  test    eax, eax
0x1800cefc6  jnz     short loc_1800CEFE8
0x1800cefc8  mov     rcx, [rbp+18h]; this
0x1800cefcc  lea     r8, aOnecoreuapEndu_122; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800cefd3  lea     edx, [rax+5Fh]; void *
0x1800cefd6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cefdb  mov     ebx, eax
0x1800cefdd  lea     rcx, [rbp+StringSid]
0x1800cefe1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800cefe6  jmp     short loc_1800CEFA2
0x1800cefe8  mov     rcx, rsi; this
0x1800cefeb  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ceff0  mov     rdx, [rbp+StringSid]; Src
0x1800ceff4  mov     rcx, rsi; this
0x1800ceff7  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x1800ceffc  mov     ebx, eax
0x1800ceffe  test    eax, eax
0x1800cf000  jns     short loc_1800CF01C
0x1800cf002  mov     rcx, [rbp+18h]; this
0x1800cf006  mov     r9d, eax; char *
0x1800cf009  lea     r8, aOnecoreuapEndu_122; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800cf010  mov     edx, 62h ; 'b'; void *
0x1800cf015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf01a  jmp     short loc_1800CEFDD
0x1800cf01c  lea     rcx, [rbp+StringSid]
0x1800cf020  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800cf025  mov     rcx, rdi; this
0x1800cf028  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800cf02d  lea     rcx, [rbp+TokenHandle]
0x1800cf031  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800cf036  nop
0x1800cf037  lea     rcx, [rbp+var_20]
0x1800cf03b  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800cf040  xor     ebx, ebx
0x1800cf042  lea     rcx, [rbp+var_10]
0x1800cf046  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800cf04b  mov     eax, ebx
0x1800cf04d  mov     rbx, [rsp+50h+arg_0]
0x1800cf052  add     rsp, 50h
0x1800cf056  pop     rdi
0x1800cf057  pop     rsi
0x1800cf058  pop     rbp
0x1800cf059  retn
```

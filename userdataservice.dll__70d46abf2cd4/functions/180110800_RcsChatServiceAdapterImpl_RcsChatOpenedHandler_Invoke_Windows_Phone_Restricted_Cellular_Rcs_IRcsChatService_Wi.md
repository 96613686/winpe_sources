# RcsChatServiceAdapterImpl::RcsChatOpenedHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IRcsChatService *,Windows::Phone::Restricted::Cellular::Rcs::IRcsChatOpenedEventArgs *)

- ea: `0x180110800`
- end: `0x180110a89`
- name: `?Invoke@RcsChatOpenedHandler@RcsChatServiceAdapterImpl@@UEAAJPEAUIRcsChatService@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIRcsChatOpenedEventArgs@45678@@Z`
- size: `649`
- prototype: `__int64 __fastcall(RcsChatServiceAdapterImpl::RcsChatOpenedHandler *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsChatService *, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsChatOpenedEventArgs *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004658`
- `0x180005bac`
- `0x180018c20`
- `0x18001b340`
- `0x18008b320`
- `0x1801099a4`
- `0x18010b8dc`
- `0x180110800`
- `0x18011382c`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PhoneUtil!MaskPhoneUri` at `0x180110903`
- `PhoneUtil!MaskPhoneUri` at `0x180110903`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801108c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110a4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801108c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110a4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801108ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801108ef`

## string_xrefs

- `0x180110854`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatserviceadapterimpl.cpp`
- `0x1801108b0`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatserviceadapterimpl.cpp`
- `0x180110951`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatserviceadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsChatServiceAdapterImpl::RcsChatOpenedHandler::Invoke(
        RcsChatServiceAdapterImpl::RcsChatOpenedHandler *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsChatService *a2,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsChatOpenedEventArgs *a3)
{
  __int64 v3; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  PCWSTR StringRawBuffer; // rax
  HRESULT DialStringFromUri; // eax
  size_t v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  STRSAFE_LPCWSTR pszSrc[4]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v19[9]; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+F0h] [rbp-10h]
  wchar_t pszDest[8]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v22; // [rsp+110h] [rbp+10h]
  __int128 v23; // [rsp+120h] [rbp+20h]
  __int128 v24; // [rsp+130h] [rbp+30h]
  __int128 v25; // [rsp+140h] [rbp+40h]
  __int128 v26; // [rsp+150h] [rbp+50h]
  __int128 v27; // [rsp+160h] [rbp+60h]
  __int128 v28; // [rsp+170h] [rbp+70h]
  _OWORD v29[2]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v30[128]; // [rsp+1A0h] [rbp+A0h] BYREF

  v3 = *(_QWORD *)a3;
  v17 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsChatOpenedEventArgs *, __int64 *))(v3 + 48))(
         a3,
         &v17);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = v17;
    string = 0;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 128LL);
    WindowsDeleteString(0);
    string = 0;
    v9 = v8(v7, &string);
    v6 = v9;
    if ( v9 >= 0 )
    {
      memset_0(v30, 0, sizeof(v30));
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      MaskPhoneUri(StringRawBuffer, v30, 64);
      if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context,
          ChatServiceChatOpened,
          v30);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(pszSrc);
      DialStringFromUri = GetDialStringFromUri(v17, pszSrc);
      v6 = DialStringFromUri;
      if ( DialStringFromUri >= 0 )
      {
        memset(v29, 0, 20);
        memset_0(pszDest, 0, 0x80u);
        DialStringFromUri = StringCchCopyW(pszDest, v12, pszSrc[0]);
        v6 = DialStringFromUri;
        if ( DialStringFromUri >= 0 )
        {
          v13 = *((_QWORD *)this + 16);
          v19[0] = *(_OWORD *)pszDest;
          *(_QWORD *)((char *)v29 + 4) = v13;
          v14 = *((_QWORD *)this + 17);
          v19[2] = v23;
          *(_QWORD *)((char *)v29 + 12) = v14;
          v19[1] = v22;
          LODWORD(v29[0]) = 0;
          v19[4] = v25;
          v20 = HIDWORD(v14);
          v19[3] = v24;
          v19[6] = v27;
          v19[5] = v26;
          v19[8] = v29[0];
          v19[7] = v28;
          RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatOpenedEventArgs,RcsChatOpenedNotificationArgs>::_PublishNotifications(
            (char *)this - 8,
            v19);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pszSrc);
          WindowsDeleteString(string);
          v6 = 0;
          goto LABEL_12;
        }
      }
      Log_HREvent_38(
        (unsigned int)DialStringFromUri,
        1,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatserviceadapterimpl.cpp");
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pszSrc);
    }
    else
    {
      Log_HREvent_38(
        (unsigned int)v9,
        1,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatserviceadapterimpl.cpp");
    }
    WindowsDeleteString(string);
LABEL_12:
    string = 0;
    goto LABEL_13;
  }
  Log_HREvent_38(
    (unsigned int)v5,
    1,
    "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatserviceadapterimpl.cpp");
LABEL_13:
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v17);
  return v6;
}

```

## disassembly

```asm
0x180110800  mov     [rsp-8+arg_8], rbx
0x180110805  push    rbp
0x180110806  push    rsi
0x180110807  push    rdi
0x180110808  lea     rbp, [rsp-130h]
0x180110810  sub     rsp, 230h
0x180110817  mov     rax, cs:__security_cookie
0x18011081e  xor     rax, rsp
0x180110821  mov     [rbp+140h+var_20], rax
0x180110828  mov     rax, [r8]
0x18011082b  lea     rdx, [rsp+240h+var_208]
0x180110830  mov     rsi, rcx
0x180110833  mov     [rsp+240h+var_208], 0
0x18011083c  mov     rcx, r8
0x18011083f  mov     rax, [rax+30h]
0x180110843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110848  mov     ebx, eax
0x18011084a  test    eax, eax
0x18011084c  jns     short loc_18011086B
0x18011084e  mov     r9d, 74h ; 't'
0x180110854  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\appmodel\\messagingom"...
0x18011085b  mov     ecx, eax
0x18011085d  lea     edx, [r9-73h]
0x180110861  call    Log_HREvent_38
0x180110866  jmp     loc_180110A5B
0x18011086b  mov     rdi, [rsp+240h+var_208]
0x180110870  xor     ecx, ecx; string
0x180110872  mov     [rsp+240h+string], 0
0x18011087b  mov     rax, [rdi]
0x18011087e  mov     rbx, [rax+80h]
0x180110885  call    cs:__imp_WindowsDeleteString
0x18011088b  lea     rdx, [rsp+240h+string]
0x180110890  mov     [rsp+240h+string], 0
0x180110899  mov     rcx, rdi
0x18011089c  mov     rax, rbx
0x18011089f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801108a4  mov     ebx, eax
0x1801108a6  test    eax, eax
0x1801108a8  jns     short loc_1801108D2
0x1801108aa  mov     r9d, 77h ; 'w'
0x1801108b0  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\appmodel\\messagingom"...
0x1801108b7  mov     ecx, eax
0x1801108b9  lea     edx, [r9-76h]
0x1801108bd  call    Log_HREvent_38
0x1801108c2  mov     rcx, [rsp+240h+string]; string
0x1801108c7  call    cs:__imp_WindowsDeleteString
0x1801108cd  jmp     loc_180110A52
0x1801108d2  mov     edi, 80h
0x1801108d7  lea     rcx, [rbp+140h+var_A0]; void *
0x1801108de  mov     r8d, edi; Size
0x1801108e1  xor     edx, edx; Val
0x1801108e3  call    memset_0
0x1801108e8  mov     rcx, [rsp+240h+string]; string
0x1801108ed  xor     edx, edx; length
0x1801108ef  call    cs:__imp_WindowsGetStringRawBuffer
0x1801108f5  mov     rcx, rax
0x1801108f8  lea     r8d, [rdi-40h]
0x1801108fc  lea     rdx, [rbp+140h+var_A0]
0x180110903  call    cs:__imp_MaskPhoneUri
0x180110909  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x180110910  jz      short loc_18011092C
0x180110912  lea     r8, [rbp+140h+var_A0]
0x180110919  lea     rdx, ChatServiceChatOpened
0x180110920  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context
0x180110927  call    McTemplateU0z_EventWriteTransfer
0x18011092c  lea     rcx, [rsp+240h+pszSrc]; void *
0x180110931  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180110936  mov     rcx, [rsp+240h+var_208]
0x18011093b  lea     rdx, [rsp+240h+pszSrc]
0x180110940  call    ?GetDialStringFromUri@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetDialStringFromUri(Windows::Foundation::IUriRuntimeClass *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180110945  mov     ebx, eax
0x180110947  test    eax, eax
0x180110949  jns     short loc_180110973
0x18011094b  mov     r9d, 7Eh ; '~'
0x180110951  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\appmodel\\messagingom"...
0x180110958  mov     edx, 1
0x18011095d  mov     ecx, eax
0x18011095f  call    Log_HREvent_38
0x180110964  lea     rcx, [rsp+240h+pszSrc]; void *
0x180110969  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18011096e  jmp     loc_1801108C2
0x180110973  xorps   xmm0, xmm0
0x180110976  mov     dword ptr [rbp+140h+var_C0], 0
0x180110980  mov     r8, rdi; Size
0x180110983  lea     rcx, [rbp+140h+pszDest]; void *
0x180110987  xor     edx, edx; Val
0x180110989  movups  xmmword ptr [rbp+140h+var_C0+4], xmm0
0x180110990  call    memset_0
0x180110995  mov     r8, [rsp+240h+pszSrc]; pszSrc
0x18011099a  lea     rcx, [rbp+140h+pszDest]; pszDest
0x18011099e  call    StringCchCopyW
0x1801109a3  mov     ebx, eax
0x1801109a5  test    eax, eax
0x1801109a7  jns     short loc_1801109B1
0x1801109a9  mov     r9d, 81h
0x1801109af  jmp     short loc_180110951
0x1801109b1  movaps  xmm0, xmmword ptr [rbp+140h+pszDest]
0x1801109b5  lea     rcx, [rsi-8]
0x1801109b9  movaps  xmm1, [rbp+140h+var_130]
0x1801109bd  lea     rdx, [rsp+240h+var_1E0]
0x1801109c2  mov     rax, [rsi+80h]
0x1801109c9  movups  [rsp+240h+var_1E0], xmm0
0x1801109ce  mov     qword ptr [rbp+140h+var_C0+4], rax
0x1801109d5  movaps  xmm0, [rbp+140h+var_120]
0x1801109d9  mov     rax, [rsi+88h]
0x1801109e0  movups  [rbp+140h+var_1C0], xmm0
0x1801109e4  mov     qword ptr [rbp+140h+var_C0+0Ch], rax
0x1801109eb  movaps  xmm0, [rbp+140h+var_100]
0x1801109ef  mov     eax, dword ptr [rbp+140h+var_C0+10h]
0x1801109f5  movups  [rsp+240h+var_1D0], xmm1
0x1801109fa  mov     dword ptr [rbp+140h+var_C0], 0
0x180110a04  movaps  xmm1, [rbp+140h+var_110]
0x180110a08  movups  [rbp+140h+var_1A0], xmm0
0x180110a0c  mov     [rbp+140h+var_150], eax
0x180110a0f  movaps  xmm0, [rbp+140h+var_E0]
0x180110a13  movups  [rbp+140h+var_1B0], xmm1
0x180110a17  movaps  xmm1, [rbp+140h+var_F0]
0x180110a1b  movups  [rbp+140h+var_180], xmm0
0x180110a1f  movaps  xmm0, xmmword ptr [rbp+140h+var_C0]
0x180110a26  movups  [rbp+140h+var_190], xmm1
0x180110a2a  movaps  xmm1, [rbp+140h+var_D0]
0x180110a2e  movups  [rbp+140h+var_160], xmm0
0x180110a32  movups  [rbp+140h+var_170], xmm1
0x180110a36  call    ?_PublishNotifications@?$RcsEventHandler@VRcsGroupChatService@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsGroupChatService@23456@VRcsGroupChatOpenedEventArgs@23456@URcsChatOpenedNotificationArgs@@@@IEAAXURcsChatOpenedNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatOpenedEventArgs,RcsChatOpenedNotificationArgs>::_PublishNotifications(RcsChatOpenedNotificationArgs)
0x180110a3b  lea     rcx, [rsp+240h+pszSrc]; void *
0x180110a40  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180110a45  mov     rcx, [rsp+240h+string]; string
0x180110a4a  call    cs:__imp_WindowsDeleteString
0x180110a50  xor     ebx, ebx
0x180110a52  mov     [rsp+240h+string], 0
0x180110a5b  lea     rcx, [rsp+240h+var_208]
0x180110a60  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180110a65  mov     eax, ebx
0x180110a67  mov     rcx, [rbp+140h+var_20]
0x180110a6e  xor     rcx, rsp; StackCookie
0x180110a71  call    __security_check_cookie
0x180110a76  mov     rbx, [rsp+240h+arg_8]
0x180110a7e  add     rsp, 230h
0x180110a85  pop     rdi
0x180110a86  pop     rsi
0x180110a87  pop     rbp
0x180110a88  retn
```

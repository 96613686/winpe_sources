# RcsChatServiceAdapterImpl::RcsGroupChatOpenedHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatService *,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatOpenedEventArgs *)

- ea: `0x180110a90`
- end: `0x180110ca7`
- name: `?Invoke@RcsGroupChatOpenedHandler@RcsChatServiceAdapterImpl@@UEAAJPEAUIRcsGroupChatService@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIRcsGroupChatOpenedEventArgs@45678@@Z`
- size: `535`
- prototype: `__int64 __fastcall(RcsChatServiceAdapterImpl::RcsGroupChatOpenedHandler *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatService *, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatOpenedEventArgs *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004658`
- `0x180005bac`
- `0x18008b320`
- `0x1801099a4`
- `0x18010b8dc`
- `0x180110a90`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110c68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110c68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110b81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110bc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110b81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110bc3`

## string_xrefs

- `0x180110af4`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatserviceadapterimpl.cpp`
- `0x180110b4e`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatserviceadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsChatServiceAdapterImpl::RcsGroupChatOpenedHandler::Invoke(
        RcsChatServiceAdapterImpl::RcsGroupChatOpenedHandler *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatService *a2,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatOpenedEventArgs *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatOpenedEventArgs *, __int64 *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  HRESULT v11; // eax
  PCWSTR StringRawBuffer; // rax
  const wchar_t *v13; // rax
  size_t v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v20[9]; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+D0h] [rbp-30h]
  wchar_t pszDest[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v23; // [rsp+F0h] [rbp-10h]
  __int128 v24; // [rsp+100h] [rbp+0h]
  __int128 v25; // [rsp+110h] [rbp+10h]
  __int128 v26; // [rsp+120h] [rbp+20h]
  __int128 v27; // [rsp+130h] [rbp+30h]
  __int128 v28; // [rsp+140h] [rbp+40h]
  __int128 v29; // [rsp+150h] [rbp+50h]
  _OWORD v30[2]; // [rsp+160h] [rbp+60h] BYREF

  v3 = *(_QWORD *)a3;
  v19 = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatOpenedEventArgs *, __int64 *))(v3 + 48);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v19);
  v7 = v6(a3, &v19);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = v19;
    string = 0;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10(v9, &string);
    v8 = v11;
    if ( v11 < 0 )
      goto LABEL_4;
    if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      McTemplateU0z_EventWriteTransfer(
        MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context,
        GroupChatServiceGroupChatOpened,
        StringRawBuffer);
    }
    memset(v30, 0, 20);
    memset_0(pszDest, 0, 0x80u);
    v13 = WindowsGetStringRawBuffer(string, 0);
    v11 = StringCchCopyW(pszDest, v14, v13);
    v8 = v11;
    if ( v11 < 0 )
    {
LABEL_4:
      Log_HREvent_38(
        (unsigned int)v11,
        1,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatserviceadapterimpl.cpp");
      WindowsDeleteString(string);
    }
    else
    {
      v15 = *((_QWORD *)this + 16);
      v20[0] = *(_OWORD *)pszDest;
      *(_QWORD *)((char *)v30 + 4) = v15;
      v16 = *((_QWORD *)this + 17);
      v20[2] = v24;
      *(_QWORD *)((char *)v30 + 12) = v16;
      v20[1] = v23;
      LODWORD(v30[0]) = 1;
      v20[4] = v26;
      v21 = HIDWORD(v16);
      v20[3] = v25;
      v20[6] = v28;
      v20[5] = v27;
      v20[8] = v30[0];
      v20[7] = v29;
      RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatOpenedEventArgs,RcsChatOpenedNotificationArgs>::_PublishNotifications(
        (char *)this - 8,
        v20);
      WindowsDeleteString(string);
      v8 = 0;
    }
    string = 0;
  }
  else
  {
    Log_HREvent_38(
      (unsigned int)v7,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatserviceadapterimpl.cpp");
  }
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v19);
  return v8;
}

```

## disassembly

```asm
0x180110a90  mov     [rsp-8+arg_8], rbx
0x180110a95  push    rbp
0x180110a96  push    rsi
0x180110a97  push    rdi
0x180110a98  lea     rbp, [rsp-90h]
0x180110aa0  sub     rsp, 190h
0x180110aa7  mov     rax, cs:__security_cookie
0x180110aae  xor     rax, rsp
0x180110ab1  mov     [rbp+0A0h+var_20], rax
0x180110ab8  mov     rax, [r8]
0x180110abb  mov     rsi, rcx
0x180110abe  lea     rcx, [rsp+1A0h+var_168]
0x180110ac3  mov     [rsp+1A0h+var_168], 0
0x180110acc  mov     rdi, r8
0x180110acf  mov     rbx, [rax+30h]
0x180110ad3  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180110ad8  lea     rdx, [rsp+1A0h+var_168]
0x180110add  mov     rcx, rdi
0x180110ae0  mov     rax, rbx
0x180110ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110ae8  mov     ebx, eax
0x180110aea  test    eax, eax
0x180110aec  jns     short loc_180110B0C
0x180110aee  mov     r9d, 9Fh
0x180110af4  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\appmodel\\messagingom"...
0x180110afb  mov     edx, 1
0x180110b00  mov     ecx, eax
0x180110b02  call    Log_HREvent_38
0x180110b07  jmp     loc_180110C79
0x180110b0c  mov     rdi, [rsp+1A0h+var_168]
0x180110b11  xor     ecx, ecx; string
0x180110b13  mov     [rsp+1A0h+string], 0
0x180110b1c  mov     rax, [rdi]
0x180110b1f  mov     rbx, [rax+30h]
0x180110b23  call    cs:__imp_WindowsDeleteString
0x180110b29  lea     rdx, [rsp+1A0h+string]
0x180110b2e  mov     [rsp+1A0h+string], 0
0x180110b37  mov     rcx, rdi
0x180110b3a  mov     rax, rbx
0x180110b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110b42  mov     ebx, eax
0x180110b44  test    eax, eax
0x180110b46  jns     short loc_180110B71
0x180110b48  mov     r9d, 0A2h
0x180110b4e  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\appmodel\\messagingom"...
0x180110b55  mov     edx, 1
0x180110b5a  mov     ecx, eax
0x180110b5c  call    Log_HREvent_38
0x180110b61  mov     rcx, [rsp+1A0h+string]; string
0x180110b66  call    cs:__imp_WindowsDeleteString
0x180110b6c  jmp     loc_180110C70
0x180110b71  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x180110b78  jz      short loc_180110B9D
0x180110b7a  mov     rcx, [rsp+1A0h+string]; string
0x180110b7f  xor     edx, edx; length
0x180110b81  call    cs:__imp_WindowsGetStringRawBuffer
0x180110b87  mov     r8, rax
0x180110b8a  lea     rdx, GroupChatServiceGroupChatOpened
0x180110b91  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context
0x180110b98  call    McTemplateU0z_EventWriteTransfer
0x180110b9d  xorps   xmm0, xmm0
0x180110ba0  mov     dword ptr [rbp+0A0h+var_40], 0
0x180110ba7  xor     edx, edx; Val
0x180110ba9  lea     rcx, [rbp+0A0h+pszDest]; void *
0x180110bad  mov     r8d, 80h; Size
0x180110bb3  movups  xmmword ptr [rbp+0A0h+var_40+4], xmm0
0x180110bb7  call    memset_0
0x180110bbc  mov     rcx, [rsp+1A0h+string]; string
0x180110bc1  xor     edx, edx; length
0x180110bc3  call    cs:__imp_WindowsGetStringRawBuffer
0x180110bc9  mov     r8, rax; pszSrc
0x180110bcc  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x180110bd0  call    StringCchCopyW
0x180110bd5  mov     ebx, eax
0x180110bd7  test    eax, eax
0x180110bd9  jns     short loc_180110BE6
0x180110bdb  mov     r9d, 0A7h
0x180110be1  jmp     loc_180110B4E
0x180110be6  movaps  xmm0, xmmword ptr [rbp+0A0h+pszDest]
0x180110bea  lea     rcx, [rsi-8]
0x180110bee  movaps  xmm1, [rbp+0A0h+var_B0]
0x180110bf2  lea     rdx, [rsp+1A0h+var_160]
0x180110bf7  mov     rax, [rsi+80h]
0x180110bfe  movups  [rsp+1A0h+var_160], xmm0
0x180110c03  mov     qword ptr [rbp+0A0h+var_40+4], rax
0x180110c07  movaps  xmm0, [rbp+0A0h+var_A0]
0x180110c0b  mov     rax, [rsi+88h]
0x180110c12  movups  [rsp+1A0h+var_140], xmm0
0x180110c17  mov     qword ptr [rbp+0A0h+var_40+0Ch], rax
0x180110c1b  movaps  xmm0, [rbp+0A0h+var_80]
0x180110c1f  mov     eax, dword ptr [rbp+0A0h+var_40+10h]
0x180110c22  movups  [rsp+1A0h+var_150], xmm1
0x180110c27  mov     dword ptr [rbp+0A0h+var_40], 1
0x180110c2e  movaps  xmm1, [rbp+0A0h+var_90]
0x180110c32  movups  [rbp+0A0h+var_120], xmm0
0x180110c36  mov     [rbp+0A0h+var_D0], eax
0x180110c39  movaps  xmm0, [rbp+0A0h+var_60]
0x180110c3d  movups  [rsp+1A0h+var_130], xmm1
0x180110c42  movaps  xmm1, [rbp+0A0h+var_70]
0x180110c46  movups  [rbp+0A0h+var_100], xmm0
0x180110c4a  movaps  xmm0, xmmword ptr [rbp+0A0h+var_40]
0x180110c4e  movups  [rbp+0A0h+var_110], xmm1
0x180110c52  movaps  xmm1, [rbp+0A0h+var_50]
0x180110c56  movups  [rbp+0A0h+var_E0], xmm0
0x180110c5a  movups  [rbp+0A0h+var_F0], xmm1
0x180110c5e  call    ?_PublishNotifications@?$RcsEventHandler@VRcsGroupChatService@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsGroupChatService@23456@VRcsGroupChatOpenedEventArgs@23456@URcsChatOpenedNotificationArgs@@@@IEAAXURcsChatOpenedNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatOpenedEventArgs,RcsChatOpenedNotificationArgs>::_PublishNotifications(RcsChatOpenedNotificationArgs)
0x180110c63  mov     rcx, [rsp+1A0h+string]; string
0x180110c68  call    cs:__imp_WindowsDeleteString
0x180110c6e  xor     ebx, ebx
0x180110c70  mov     [rsp+1A0h+string], 0
0x180110c79  lea     rcx, [rsp+1A0h+var_168]
0x180110c7e  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180110c83  mov     eax, ebx
0x180110c85  mov     rcx, [rbp+0A0h+var_20]
0x180110c8c  xor     rcx, rsp; StackCookie
0x180110c8f  call    __security_check_cookie
0x180110c94  mov     rbx, [rsp+1A0h+arg_8]
0x180110c9c  add     rsp, 190h
0x180110ca3  pop     rdi
0x180110ca4  pop     rsi
0x180110ca5  pop     rbp
0x180110ca6  retn
```

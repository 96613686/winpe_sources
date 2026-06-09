# RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat>::RcsChatRemoteContactComposingHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat *,Windows::Phone::Restricted::Cellular::Rcs::IRcsRemoteContactComposingEventArgs *)

- ea: `0x18010dc70`
- end: `0x18010df3b`
- name: `?Invoke@RcsChatRemoteContactComposingHandler@?$RcsChatAdapterImplBase@VRcsGroupChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsGroupChat@23456@@@UEAAJPEAUIRcsGroupChat@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIRcsRemoteContactComposingEventArgs@45678@@Z`
- size: `715`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004658`
- `0x18008b320`
- `0x1801099a4`
- `0x18010dc70`
- `0x18010f994`
- `0x18010fda0`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PhoneUtil!GetDialStringFromTelUri` at `0x18010de3f`
- `PhoneUtil!GetDialStringFromTelUri` at `0x18010de3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18010dd9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18010dd9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010dd36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010dd75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010defa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010dd36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010dd75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010defa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010de29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010de29`

## string_xrefs

- `0x18010dccc`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`
- `0x18010dd08`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`
- `0x18010dd5d`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat>::RcsChatRemoteContactComposingHandler::Invoke(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  HRESULT DialStringFromTelUri; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  const wchar_t *v15; // r8
  size_t v16; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  wchar_t *v18; // rcx
  __int64 v19; // rdx
  _OWORD *v20; // rax
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm1
  _BYTE v30[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v34[288]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[64]; // [rsp+170h] [rbp+70h] BYREF
  int v36; // [rsp+1F0h] [rbp+F0h]
  _DWORD v37[35]; // [rsp+1F4h] [rbp+F4h] BYREF
  __int128 v38; // [rsp+280h] [rbp+180h]

  v3 = *a3;
  v30[0] = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(v3 + 56))(a3, v30);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = *a3;
    v33 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v8 + 48))(a3, &v33);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v10 = v33;
      string = 0;
      v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 128LL);
      WindowsDeleteString(0);
      string = 0;
      DialStringFromTelUri = v11(v10, &string);
      v7 = DialStringFromTelUri;
      if ( DialStringFromTelUri < 0 )
        goto LABEL_6;
      if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
        McTemplateU0t_EventWriteTransfer(v14, v13, v30[0]);
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v36 = 0;
      memset(&v37[32], 0, 12);
      v38 = 0;
      memset_0(v37, 0, 0x80u);
      memset_0(pszDest, 0, sizeof(pszDest));
      v15 = *(const wchar_t **)(a1 + 128);
      v38 = *(_OWORD *)(a1 + 164);
      DialStringFromTelUri = StringCchCopyW(pszDest, v16, v15);
      v7 = DialStringFromTelUri;
      if ( DialStringFromTelUri < 0
        || (StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
            DialStringFromTelUri = GetDialStringFromTelUri(StringRawBuffer, (unsigned __int16 *)v37, 0x40u),
            v7 = DialStringFromTelUri,
            DialStringFromTelUri < 0) )
      {
LABEL_6:
        Log_HREvent_38(
          (unsigned int)DialStringFromTelUri,
          1,
          "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp");
        WindowsDeleteString(string);
      }
      else
      {
        v18 = pszDest;
        v36 = *(_DWORD *)(a1 + 160);
        v19 = 2;
        v37[32] = v30[0];
        *(struct _FILETIME *)&v37[33] = SystemTimeAsFileTime;
        v20 = v34;
        do
        {
          v21 = *((_OWORD *)v18 + 1);
          *v20 = *(_OWORD *)v18;
          v22 = *((_OWORD *)v18 + 2);
          v20[1] = v21;
          v23 = *((_OWORD *)v18 + 3);
          v20[2] = v22;
          v24 = *((_OWORD *)v18 + 4);
          v20[3] = v23;
          v25 = *((_OWORD *)v18 + 5);
          v20[4] = v24;
          v26 = *((_OWORD *)v18 + 6);
          v20[5] = v25;
          v27 = *((_OWORD *)v18 + 7);
          v18 += 64;
          v20[6] = v26;
          v20[7] = v27;
          v20 += 8;
          --v19;
        }
        while ( v19 );
        v28 = *((_OWORD *)v18 + 1);
        *v20 = *(_OWORD *)v18;
        v20[1] = v28;
        RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat,Windows::Phone::Restricted::Cellular::Rcs::RcsRemoteContactComposingEventArgs,RcsRemoteContactComposingNotificationArgs>::_PublishNotifications(
          a1 - 8,
          v34);
        WindowsDeleteString(string);
        v7 = 0;
      }
      string = 0;
    }
    else
    {
      Log_HREvent_38(
        (unsigned int)v9,
        1,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp");
    }
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v33);
  }
  else
  {
    Log_HREvent_38(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp");
  }
  return v7;
}

```

## disassembly

```asm
0x18010dc70  mov     [rsp-8+arg_8], rbx
0x18010dc75  mov     [rsp-8+arg_18], rsi
0x18010dc7a  push    rbp
0x18010dc7b  push    rdi
0x18010dc7c  push    r14
0x18010dc7e  lea     rbp, [rsp-1A0h]
0x18010dc86  sub     rsp, 2A0h
0x18010dc8d  mov     rax, cs:__security_cookie
0x18010dc94  xor     rax, rsp
0x18010dc97  mov     [rbp+1B0h+var_20], rax
0x18010dc9e  mov     rax, [r8]
0x18010dca1  lea     rdx, [rsp+2B0h+var_280]
0x18010dca6  mov     rsi, rcx
0x18010dca9  xor     r14d, r14d
0x18010dcac  mov     rcx, r8
0x18010dcaf  mov     [rsp+2B0h+var_280], r14b
0x18010dcb4  mov     rdi, r8
0x18010dcb7  mov     rax, [rax+38h]
0x18010dcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dcc0  mov     ebx, eax
0x18010dcc2  test    eax, eax
0x18010dcc4  jns     short loc_18010DCE3
0x18010dcc6  mov     r9d, 8Ah
0x18010dccc  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010dcd3  lea     edx, [r14+1]
0x18010dcd7  mov     ecx, eax
0x18010dcd9  call    Log_HREvent_38
0x18010dcde  jmp     loc_18010DF12
0x18010dce3  mov     rax, [rdi]
0x18010dce6  lea     rdx, [rsp+2B0h+var_268]
0x18010dceb  mov     rcx, rdi
0x18010dcee  mov     [rsp+2B0h+var_268], r14
0x18010dcf3  mov     rax, [rax+30h]
0x18010dcf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dcfc  mov     ebx, eax
0x18010dcfe  test    eax, eax
0x18010dd00  jns     short loc_18010DD20
0x18010dd02  mov     r9d, 8Dh
0x18010dd08  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010dd0f  mov     edx, 1
0x18010dd14  mov     ecx, eax
0x18010dd16  call    Log_HREvent_38
0x18010dd1b  jmp     loc_18010DF08
0x18010dd20  mov     rdi, [rsp+2B0h+var_268]
0x18010dd25  xor     ecx, ecx; string
0x18010dd27  mov     [rsp+2B0h+string], r14
0x18010dd2c  mov     rax, [rdi]
0x18010dd2f  mov     rbx, [rax+80h]
0x18010dd36  call    cs:__imp_WindowsDeleteString
0x18010dd3c  lea     rdx, [rsp+2B0h+string]
0x18010dd41  mov     [rsp+2B0h+string], r14
0x18010dd46  mov     rcx, rdi
0x18010dd49  mov     rax, rbx
0x18010dd4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dd51  mov     ebx, eax
0x18010dd53  test    eax, eax
0x18010dd55  jns     short loc_18010DD80
0x18010dd57  mov     r9d, 90h
0x18010dd5d  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010dd64  mov     edx, 1
0x18010dd69  mov     ecx, eax
0x18010dd6b  call    Log_HREvent_38
0x18010dd70  mov     rcx, [rsp+2B0h+string]; string
0x18010dd75  call    cs:__imp_WindowsDeleteString
0x18010dd7b  jmp     loc_18010DF03
0x18010dd80  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x18010dd87  jz      short loc_18010DD94
0x18010dd89  movzx   r8d, [rsp+2B0h+var_280]
0x18010dd8f  call    McTemplateU0t_EventWriteTransfer
0x18010dd94  lea     rcx, [rsp+2B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18010dd99  mov     qword ptr [rsp+2B0h+SystemTimeAsFileTime.dwLowDateTime], r14
0x18010dd9e  call    cs:__imp_GetSystemTimeAsFileTime
0x18010dda4  xorps   xmm0, xmm0
0x18010dda7  mov     [rbp+1B0h+var_C0], r14d
0x18010ddae  mov     edi, 80h
0x18010ddb3  mov     [rbp+1B0h+var_3C], r14
0x18010ddba  mov     r8d, edi; Size
0x18010ddbd  mov     [rbp+1B0h+var_34], r14d
0x18010ddc4  xor     edx, edx; Val
0x18010ddc6  lea     rcx, [rbp+1B0h+var_BC]; void *
0x18010ddcd  movups  [rbp+1B0h+var_30], xmm0
0x18010ddd4  call    memset_0
0x18010ddd9  mov     r8d, edi; Size
0x18010dddc  lea     rcx, [rbp+1B0h+pszDest]; void *
0x18010dde0  xor     edx, edx; Val
0x18010dde2  call    memset_0
0x18010dde7  mov     rax, [rsi+0A4h]
0x18010ddee  lea     rcx, [rbp+1B0h+pszDest]; pszDest
0x18010ddf2  mov     r8, [rsi+80h]; pszSrc
0x18010ddf9  mov     qword ptr [rbp+1B0h+var_30], rax
0x18010de00  mov     rax, [rsi+0ACh]
0x18010de07  mov     qword ptr [rbp+1B0h+var_30+8], rax
0x18010de0e  call    StringCchCopyW
0x18010de13  mov     ebx, eax
0x18010de15  test    eax, eax
0x18010de17  jns     short loc_18010DE22
0x18010de19  lea     r9d, [rdi+1Ah]
0x18010de1d  jmp     loc_18010DD5D
0x18010de22  mov     rcx, [rsp+2B0h+string]; string
0x18010de27  xor     edx, edx; length
0x18010de29  call    cs:__imp_WindowsGetStringRawBuffer
0x18010de2f  mov     r8d, 40h ; '@'
0x18010de35  lea     rdx, [rbp+1B0h+var_BC]
0x18010de3c  mov     rcx, rax
0x18010de3f  call    cs:__imp_?GetDialStringFromTelUri@@YAJPEBGPEAGI@Z; GetDialStringFromTelUri(ushort const *,ushort *,uint)
0x18010de45  mov     ebx, eax
0x18010de47  test    eax, eax
0x18010de49  jns     short loc_18010DE56
0x18010de4b  mov     r9d, 9Ch
0x18010de51  jmp     loc_18010DD5D
0x18010de56  mov     eax, [rsi+0A0h]
0x18010de5c  lea     rcx, [rbp+1B0h+pszDest]
0x18010de60  mov     [rbp+1B0h+var_C0], eax
0x18010de66  mov     edx, 2
0x18010de6b  movzx   eax, [rsp+2B0h+var_280]
0x18010de70  mov     dword ptr [rbp+1B0h+var_3C], eax
0x18010de76  mov     eax, [rsp+2B0h+SystemTimeAsFileTime.dwLowDateTime]
0x18010de7a  mov     dword ptr [rbp+1B0h+var_3C+4], eax
0x18010de80  mov     eax, [rsp+2B0h+SystemTimeAsFileTime.dwHighDateTime]
0x18010de84  mov     [rbp+1B0h+var_34], eax
0x18010de8a  lea     rax, [rsp+2B0h+var_260]
0x18010de8f  movups  xmm0, xmmword ptr [rcx]
0x18010de92  movups  xmm1, xmmword ptr [rcx+10h]
0x18010de96  movups  xmmword ptr [rax], xmm0
0x18010de99  movups  xmm0, xmmword ptr [rcx+20h]
0x18010de9d  movups  xmmword ptr [rax+10h], xmm1
0x18010dea1  movups  xmm1, xmmword ptr [rcx+30h]
0x18010dea5  movups  xmmword ptr [rax+20h], xmm0
0x18010dea9  movups  xmm0, xmmword ptr [rcx+40h]
0x18010dead  movups  xmmword ptr [rax+30h], xmm1
0x18010deb1  movups  xmm1, xmmword ptr [rcx+50h]
0x18010deb5  movups  xmmword ptr [rax+40h], xmm0
0x18010deb9  movups  xmm0, xmmword ptr [rcx+60h]
0x18010debd  movups  xmmword ptr [rax+50h], xmm1
0x18010dec1  movups  xmm1, xmmword ptr [rcx+70h]
0x18010dec5  add     rcx, rdi
0x18010dec8  movups  xmmword ptr [rax+60h], xmm0
0x18010decc  movups  xmmword ptr [rax+70h], xmm1
0x18010ded0  add     rax, rdi
0x18010ded3  sub     rdx, 1
0x18010ded7  jnz     short loc_18010DE8F
0x18010ded9  movups  xmm0, xmmword ptr [rcx]
0x18010dedc  lea     rdx, [rsp+2B0h+var_260]
0x18010dee1  movups  xmm1, xmmword ptr [rcx+10h]
0x18010dee5  lea     rcx, [rsi-8]
0x18010dee9  movups  xmmword ptr [rax], xmm0
0x18010deec  movups  xmmword ptr [rax+10h], xmm1
0x18010def0  call    ?_PublishNotifications@?$RcsEventHandler@VRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsChat@23456@VRcsRemoteContactComposingEventArgs@23456@URcsRemoteContactComposingNotificationArgs@@@@IEAAXURcsRemoteContactComposingNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat,Windows::Phone::Restricted::Cellular::Rcs::RcsRemoteContactComposingEventArgs,RcsRemoteContactComposingNotificationArgs>::_PublishNotifications(RcsRemoteContactComposingNotificationArgs)
0x18010def5  mov     rcx, [rsp+2B0h+string]; string
0x18010defa  call    cs:__imp_WindowsDeleteString
0x18010df00  mov     ebx, r14d
0x18010df03  mov     [rsp+2B0h+string], r14
0x18010df08  lea     rcx, [rsp+2B0h+var_268]
0x18010df0d  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18010df12  mov     eax, ebx
0x18010df14  mov     rcx, [rbp+1B0h+var_20]
0x18010df1b  xor     rcx, rsp; StackCookie
0x18010df1e  call    __security_check_cookie
0x18010df23  lea     r11, [rsp+2B0h+var_10]
0x18010df2b  mov     rbx, [r11+28h]
0x18010df2f  mov     rsi, [r11+38h]
0x18010df33  mov     rsp, r11
0x18010df36  pop     r14
0x18010df38  pop     rdi
0x18010df39  pop     rbp
0x18010df3a  retn
```

# RcsFileTransferServiceAdapterImpl::RcsFileTransferCreatedHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferService *,Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferCreatedEventArgs *)

- ea: `0x180109130`
- end: `0x180109344`
- name: `?Invoke@RcsFileTransferCreatedHandler@RcsFileTransferServiceAdapterImpl@@UEAAJPEAUIRcsFileTransferService@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIRcsFileTransferCreatedEventArgs@45678@@Z`
- size: `532`
- prototype: `__int64 __fastcall(RcsFileTransferServiceAdapterImpl::RcsFileTransferCreatedHandler *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferService *, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferCreatedEventArgs *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004658`
- `0x180005bac`
- `0x18008b320`
- `0x180109130`
- `0x18010965c`
- `0x1801099a4`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801091c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801091c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180109305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180109221`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180109264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180109221`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180109264`

## string_xrefs

- `0x180109194`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferserviceadapterimpl.cpp`
- `0x1801091ee`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferserviceadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsFileTransferServiceAdapterImpl::RcsFileTransferCreatedHandler::Invoke(
        RcsFileTransferServiceAdapterImpl::RcsFileTransferCreatedHandler *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferService *a2,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferCreatedEventArgs *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferCreatedEventArgs *, __int64 *); // rbx
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
  __int64 v21; // [rsp+D0h] [rbp-30h]
  wchar_t pszDest[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v23; // [rsp+F0h] [rbp-10h]
  __int128 v24; // [rsp+100h] [rbp+0h]
  __int128 v25; // [rsp+110h] [rbp+10h]
  __int128 v26; // [rsp+120h] [rbp+20h]
  __int128 v27; // [rsp+130h] [rbp+30h]
  __int128 v28; // [rsp+140h] [rbp+40h]
  __int128 v29; // [rsp+150h] [rbp+50h]
  __int128 v30; // [rsp+160h] [rbp+60h]
  __int64 v31; // [rsp+170h] [rbp+70h]

  v3 = *(_QWORD *)a3;
  v19 = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferCreatedEventArgs *, __int64 *))(v3 + 48);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v19);
  v7 = v6(a3, &v19);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = v19;
    string = 0;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 80LL);
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
        FileTransferServiceFileTransferCreated,
        StringRawBuffer);
    }
    v31 = 0;
    v30 = 0;
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
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferserviceadapterimpl.cpp");
      WindowsDeleteString(string);
    }
    else
    {
      v15 = *((_QWORD *)this + 16);
      v20[0] = *(_OWORD *)pszDest;
      *(_QWORD *)&v30 = v15;
      v16 = *((_QWORD *)this + 17);
      v20[2] = v24;
      *((_QWORD *)&v30 + 1) = v16;
      v20[1] = v23;
      v21 = v19;
      v20[4] = v26;
      v20[3] = v25;
      v20[6] = v28;
      v20[5] = v27;
      v20[8] = v30;
      v20[7] = v29;
      RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsFileTransferService,Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferService,Windows::Phone::Restricted::Cellular::Rcs::RcsFileTransferCreatedEventArgs,RcsFileTransferCreatedNotificationArgs>::_PublishNotifications(
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
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferserviceadapterimpl.cpp");
  }
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v19);
  return v8;
}

```

## disassembly

```asm
0x180109130  mov     [rsp-8+arg_8], rbx
0x180109135  push    rbp
0x180109136  push    rsi
0x180109137  push    rdi
0x180109138  lea     rbp, [rsp-90h]
0x180109140  sub     rsp, 190h
0x180109147  mov     rax, cs:__security_cookie
0x18010914e  xor     rax, rsp
0x180109151  mov     [rbp+0A0h+var_20], rax
0x180109158  mov     rax, [r8]
0x18010915b  mov     rsi, rcx
0x18010915e  lea     rcx, [rsp+1A0h+var_168]
0x180109163  mov     [rsp+1A0h+var_168], 0
0x18010916c  mov     rdi, r8
0x18010916f  mov     rbx, [rax+30h]
0x180109173  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180109178  lea     rdx, [rsp+1A0h+var_168]
0x18010917d  mov     rcx, rdi
0x180109180  mov     rax, rbx
0x180109183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109188  mov     ebx, eax
0x18010918a  test    eax, eax
0x18010918c  jns     short loc_1801091AC
0x18010918e  mov     r9d, 88h
0x180109194  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010919b  mov     edx, 1
0x1801091a0  mov     ecx, eax
0x1801091a2  call    Log_HREvent_38
0x1801091a7  jmp     loc_180109316
0x1801091ac  mov     rdi, [rsp+1A0h+var_168]
0x1801091b1  xor     ecx, ecx; string
0x1801091b3  mov     [rsp+1A0h+string], 0
0x1801091bc  mov     rax, [rdi]
0x1801091bf  mov     rbx, [rax+50h]
0x1801091c3  call    cs:__imp_WindowsDeleteString
0x1801091c9  lea     rdx, [rsp+1A0h+string]
0x1801091ce  mov     [rsp+1A0h+string], 0
0x1801091d7  mov     rcx, rdi
0x1801091da  mov     rax, rbx
0x1801091dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801091e2  mov     ebx, eax
0x1801091e4  test    eax, eax
0x1801091e6  jns     short loc_180109211
0x1801091e8  mov     r9d, 8Bh
0x1801091ee  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x1801091f5  mov     edx, 1
0x1801091fa  mov     ecx, eax
0x1801091fc  call    Log_HREvent_38
0x180109201  mov     rcx, [rsp+1A0h+string]; string
0x180109206  call    cs:__imp_WindowsDeleteString
0x18010920c  jmp     loc_18010930D
0x180109211  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x180109218  jz      short loc_18010923D
0x18010921a  mov     rcx, [rsp+1A0h+string]; string
0x18010921f  xor     edx, edx; length
0x180109221  call    cs:__imp_WindowsGetStringRawBuffer
0x180109227  mov     r8, rax
0x18010922a  lea     rdx, FileTransferServiceFileTransferCreated
0x180109231  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context
0x180109238  call    McTemplateU0z_EventWriteTransfer
0x18010923d  xorps   xmm0, xmm0
0x180109240  mov     [rbp+0A0h+var_30], 0
0x180109248  xor     edx, edx; Val
0x18010924a  lea     rcx, [rbp+0A0h+pszDest]; void *
0x18010924e  mov     r8d, 80h; Size
0x180109254  movups  [rbp+0A0h+var_40], xmm0
0x180109258  call    memset_0
0x18010925d  mov     rcx, [rsp+1A0h+string]; string
0x180109262  xor     edx, edx; length
0x180109264  call    cs:__imp_WindowsGetStringRawBuffer
0x18010926a  mov     r8, rax; pszSrc
0x18010926d  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x180109271  call    StringCchCopyW
0x180109276  mov     ebx, eax
0x180109278  test    eax, eax
0x18010927a  jns     short loc_180109287
0x18010927c  mov     r9d, 91h
0x180109282  jmp     loc_1801091EE
0x180109287  movaps  xmm0, xmmword ptr [rbp+0A0h+pszDest]
0x18010928b  lea     rcx, [rsi-8]
0x18010928f  movaps  xmm1, [rbp+0A0h+var_B0]
0x180109293  lea     rdx, [rsp+1A0h+var_160]
0x180109298  mov     rax, [rsi+80h]
0x18010929f  movups  [rsp+1A0h+var_160], xmm0
0x1801092a4  mov     qword ptr [rbp+0A0h+var_40], rax
0x1801092a8  movaps  xmm0, [rbp+0A0h+var_A0]
0x1801092ac  mov     rax, [rsi+88h]
0x1801092b3  movups  [rsp+1A0h+var_140], xmm0
0x1801092b8  mov     qword ptr [rbp+0A0h+var_40+8], rax
0x1801092bc  movaps  xmm0, [rbp+0A0h+var_80]
0x1801092c0  mov     rax, [rsp+1A0h+var_168]
0x1801092c5  movups  [rsp+1A0h+var_150], xmm1
0x1801092ca  mov     [rbp+0A0h+var_D0], rax
0x1801092ce  movaps  xmm1, [rbp+0A0h+var_90]
0x1801092d2  movups  [rbp+0A0h+var_120], xmm0
0x1801092d6  movaps  xmm0, [rbp+0A0h+var_60]
0x1801092da  movups  [rsp+1A0h+var_130], xmm1
0x1801092df  movaps  xmm1, [rbp+0A0h+var_70]
0x1801092e3  movups  [rbp+0A0h+var_100], xmm0
0x1801092e7  movaps  xmm0, [rbp+0A0h+var_40]
0x1801092eb  movups  [rbp+0A0h+var_110], xmm1
0x1801092ef  movaps  xmm1, [rbp+0A0h+var_50]
0x1801092f3  movups  [rbp+0A0h+var_E0], xmm0
0x1801092f7  movups  [rbp+0A0h+var_F0], xmm1
0x1801092fb  call    ?_PublishNotifications@?$RcsEventHandler@VRcsFileTransferService@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsFileTransferService@23456@VRcsFileTransferCreatedEventArgs@23456@URcsFileTransferCreatedNotificationArgs@@@@IEAAXURcsFileTransferCreatedNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsFileTransferService,Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferService,Windows::Phone::Restricted::Cellular::Rcs::RcsFileTransferCreatedEventArgs,RcsFileTransferCreatedNotificationArgs>::_PublishNotifications(RcsFileTransferCreatedNotificationArgs)
0x180109300  mov     rcx, [rsp+1A0h+string]; string
0x180109305  call    cs:__imp_WindowsDeleteString
0x18010930b  xor     ebx, ebx
0x18010930d  mov     [rsp+1A0h+string], 0
0x180109316  lea     rcx, [rsp+1A0h+var_168]
0x18010931b  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180109320  mov     eax, ebx
0x180109322  mov     rcx, [rbp+0A0h+var_20]
0x180109329  xor     rcx, rsp; StackCookie
0x18010932c  call    __security_check_cookie
0x180109331  mov     rbx, [rsp+1A0h+arg_8]
0x180109339  add     rsp, 190h
0x180109340  pop     rdi
0x180109341  pop     rsi
0x180109342  pop     rbp
0x180109343  retn
```

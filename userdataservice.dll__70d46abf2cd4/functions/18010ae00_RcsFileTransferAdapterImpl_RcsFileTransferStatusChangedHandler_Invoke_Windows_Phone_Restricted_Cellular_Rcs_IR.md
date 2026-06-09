# RcsFileTransferAdapterImpl::RcsFileTransferStatusChangedHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *,Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferStatusChangedEventArgs *)

- ea: `0x18010ae00`
- end: `0x18010aff9`
- name: `?Invoke@RcsFileTransferStatusChangedHandler@RcsFileTransferAdapterImpl@@UEAAJPEAUIRcsFileTransfer@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIRcsFileTransferStatusChangedEventArgs@45678@@Z`
- size: `505`
- prototype: `__int64 __fastcall(RcsFileTransferAdapterImpl::RcsFileTransferStatusChangedHandler *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferStatusChangedEventArgs *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005c2c`
- `0x18008b320`
- `0x1801099a4`
- `0x18010ae00`
- `0x18010b8dc`
- `0x18010b9c4`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ae80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010afcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ae80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010afcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010aedf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010af49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010aedf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010af49`

## string_xrefs

- `0x18010ae56`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`
- `0x18010aea9`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`
- `0x18010aefd`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsFileTransferAdapterImpl::RcsFileTransferStatusChangedHandler::Invoke(
        RcsFileTransferAdapterImpl::RcsFileTransferStatusChangedHandler *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *a2,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferStatusChangedEventArgs *a3)
{
  __int64 v3; // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, HSTRING *); // rbx
  int v10; // eax
  const wchar_t *StringRawBuffer; // rax
  size_t v12; // rdx
  HRESULT v13; // eax
  unsigned int v14; // ebx
  PCWSTR v15; // rax
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v19[9]; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+D0h] [rbp-30h]
  wchar_t pszDest[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v22; // [rsp+F0h] [rbp-10h]
  __int128 v23; // [rsp+100h] [rbp+0h]
  __int128 v24; // [rsp+110h] [rbp+10h]
  __int128 v25; // [rsp+120h] [rbp+20h]
  __int128 v26; // [rsp+130h] [rbp+30h]
  __int128 v27; // [rsp+140h] [rbp+40h]
  __int128 v28; // [rsp+150h] [rbp+50h]
  _OWORD v29[2]; // [rsp+160h] [rbp+60h] BYREF

  v3 = *(_QWORD *)a3;
  v17 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferStatusChangedEventArgs *, unsigned int *))(v3 + 48))(
         a3,
         &v17);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = *(_QWORD *)a2;
    string = 0;
    v9 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, HSTRING *))(v8 + 80);
    WindowsDeleteString(0);
    string = 0;
    v10 = v9(a2, &string);
    if ( v10 < 0 )
      Log_HREvent_38(
        (unsigned int)v10,
        0,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp");
    memset(v29, 0, 20);
    memset_0(pszDest, 0, 0x80u);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v13 = StringCchCopyW(pszDest, v12, StringRawBuffer);
    v7 = v13;
    if ( v13 >= 0 )
    {
      *(_OWORD *)((char *)v29 + 4) = *((_OWORD *)this + 8);
      v14 = RcsFileTransferStatusToAdapterStatus(v17);
      LODWORD(v29[0]) = v14;
      if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
      {
        v15 = WindowsGetStringRawBuffer(string, 0);
        McTemplateU0zq_EventWriteTransfer(
          MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context,
          FileTransferStatusChanged,
          v15,
          v14);
      }
      v19[0] = *(_OWORD *)pszDest;
      v20 = v29[1];
      v19[2] = v23;
      v19[1] = v22;
      v19[4] = v25;
      v19[3] = v24;
      v19[6] = v27;
      v19[5] = v26;
      v19[8] = v29[0];
      v19[7] = v28;
      RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatOpenedEventArgs,RcsChatOpenedNotificationArgs>::_PublishNotifications(
        (char *)this - 8,
        v19);
      v7 = 0;
    }
    else
    {
      Log_HREvent_38(
        (unsigned int)v13,
        1,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp");
    }
    WindowsDeleteString(string);
  }
  else
  {
    Log_HREvent_38(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp");
  }
  return v7;
}

```

## disassembly

```asm
0x18010ae00  mov     [rsp-8+arg_18], rbx
0x18010ae05  push    rbp
0x18010ae06  push    rsi
0x18010ae07  push    rdi
0x18010ae08  lea     rbp, [rsp-90h]
0x18010ae10  sub     rsp, 190h
0x18010ae17  mov     rax, cs:__security_cookie
0x18010ae1e  xor     rax, rsp
0x18010ae21  mov     [rbp+0A0h+var_20], rax
0x18010ae28  mov     rax, [r8]
0x18010ae2b  mov     rsi, rdx
0x18010ae2e  mov     rdi, rcx
0x18010ae31  mov     [rsp+1A0h+var_170], 0
0x18010ae39  lea     rdx, [rsp+1A0h+var_170]
0x18010ae3e  mov     rcx, r8
0x18010ae41  mov     rax, [rax+30h]
0x18010ae45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ae4a  mov     ebx, eax
0x18010ae4c  test    eax, eax
0x18010ae4e  jns     short loc_18010AE6E
0x18010ae50  mov     r9d, 12Eh
0x18010ae56  lea     r8, aOnecoreuapBase_126; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010ae5d  mov     edx, 1
0x18010ae62  mov     ecx, eax
0x18010ae64  call    Log_HREvent_38
0x18010ae69  jmp     loc_18010AFD5
0x18010ae6e  mov     rax, [rsi]
0x18010ae71  xor     ecx, ecx; string
0x18010ae73  mov     [rsp+1A0h+string], 0
0x18010ae7c  mov     rbx, [rax+50h]
0x18010ae80  call    cs:__imp_WindowsDeleteString
0x18010ae86  lea     rdx, [rsp+1A0h+string]
0x18010ae8b  mov     [rsp+1A0h+string], 0
0x18010ae94  mov     rcx, rsi
0x18010ae97  mov     rax, rbx
0x18010ae9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ae9f  test    eax, eax
0x18010aea1  jns     short loc_18010AEB9
0x18010aea3  mov     r9d, 131h
0x18010aea9  lea     r8, aOnecoreuapBase_126; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010aeb0  xor     edx, edx
0x18010aeb2  mov     ecx, eax
0x18010aeb4  call    Log_HREvent_38
0x18010aeb9  xorps   xmm0, xmm0
0x18010aebc  mov     dword ptr [rbp+0A0h+var_40], 0
0x18010aec3  xor     edx, edx; Val
0x18010aec5  lea     rcx, [rbp+0A0h+pszDest]; void *
0x18010aec9  mov     r8d, 80h; Size
0x18010aecf  movups  xmmword ptr [rbp+0A0h+var_40+4], xmm0
0x18010aed3  call    memset_0
0x18010aed8  mov     rcx, [rsp+1A0h+string]; string
0x18010aedd  xor     edx, edx; length
0x18010aedf  call    cs:__imp_WindowsGetStringRawBuffer
0x18010aee5  mov     r8, rax; pszSrc
0x18010aee8  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x18010aeec  call    StringCchCopyW
0x18010aef1  mov     ebx, eax
0x18010aef3  test    eax, eax
0x18010aef5  jns     short loc_18010AF15
0x18010aef7  mov     r9d, 135h
0x18010aefd  lea     r8, aOnecoreuapBase_126; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010af04  mov     edx, 1
0x18010af09  mov     ecx, eax
0x18010af0b  call    Log_HREvent_38
0x18010af10  jmp     loc_18010AFCA
0x18010af15  mov     rax, [rdi+80h]
0x18010af1c  mov     ecx, [rsp+1A0h+var_170]
0x18010af20  mov     qword ptr [rbp+0A0h+var_40+4], rax
0x18010af24  mov     rax, [rdi+88h]
0x18010af2b  mov     qword ptr [rbp+0A0h+var_40+0Ch], rax
0x18010af2f  call    _RcsFileTransferStatusToAdapterStatus
0x18010af34  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x18010af3b  mov     ebx, eax
0x18010af3d  mov     dword ptr [rbp+0A0h+var_40], eax
0x18010af40  jz      short loc_18010AF68
0x18010af42  mov     rcx, [rsp+1A0h+string]; string
0x18010af47  xor     edx, edx; length
0x18010af49  call    cs:__imp_WindowsGetStringRawBuffer
0x18010af4f  mov     r9d, ebx
0x18010af52  lea     rdx, FileTransferStatusChanged
0x18010af59  mov     r8, rax
0x18010af5c  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context
0x18010af63  call    McTemplateU0zq_EventWriteTransfer
0x18010af68  movaps  xmm0, xmmword ptr [rbp+0A0h+pszDest]
0x18010af6c  lea     rdx, [rsp+1A0h+var_160]
0x18010af71  movaps  xmm1, [rbp+0A0h+var_B0]
0x18010af75  lea     rcx, [rdi-8]
0x18010af79  mov     eax, dword ptr [rbp+0A0h+var_40+10h]
0x18010af7c  movups  [rsp+1A0h+var_160], xmm0
0x18010af81  mov     [rbp+0A0h+var_D0], eax
0x18010af84  movaps  xmm0, [rbp+0A0h+var_A0]
0x18010af88  movups  [rsp+1A0h+var_140], xmm0
0x18010af8d  movaps  xmm0, [rbp+0A0h+var_80]
0x18010af91  movups  [rsp+1A0h+var_150], xmm1
0x18010af96  movaps  xmm1, [rbp+0A0h+var_90]
0x18010af9a  movups  [rbp+0A0h+var_120], xmm0
0x18010af9e  movaps  xmm0, [rbp+0A0h+var_60]
0x18010afa2  movups  [rsp+1A0h+var_130], xmm1
0x18010afa7  movaps  xmm1, [rbp+0A0h+var_70]
0x18010afab  movups  [rbp+0A0h+var_100], xmm0
0x18010afaf  movaps  xmm0, xmmword ptr [rbp+0A0h+var_40]
0x18010afb3  movups  [rbp+0A0h+var_110], xmm1
0x18010afb7  movaps  xmm1, [rbp+0A0h+var_50]
0x18010afbb  movups  [rbp+0A0h+var_E0], xmm0
0x18010afbf  movups  [rbp+0A0h+var_F0], xmm1
0x18010afc3  call    ?_PublishNotifications@?$RcsEventHandler@VRcsGroupChatService@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsGroupChatService@23456@VRcsGroupChatOpenedEventArgs@23456@URcsChatOpenedNotificationArgs@@@@IEAAXURcsChatOpenedNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChatService,Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChatOpenedEventArgs,RcsChatOpenedNotificationArgs>::_PublishNotifications(RcsChatOpenedNotificationArgs)
0x18010afc8  xor     ebx, ebx
0x18010afca  mov     rcx, [rsp+1A0h+string]; string
0x18010afcf  call    cs:__imp_WindowsDeleteString
0x18010afd5  mov     eax, ebx
0x18010afd7  mov     rcx, [rbp+0A0h+var_20]
0x18010afde  xor     rcx, rsp; StackCookie
0x18010afe1  call    __security_check_cookie
0x18010afe6  mov     rbx, [rsp+1A0h+arg_18]
0x18010afee  add     rsp, 190h
0x18010aff5  pop     rdi
0x18010aff6  pop     rsi
0x18010aff7  pop     rbp
0x18010aff8  retn
```

# RcsFileTransferAdapterImpl::RcsFileTransferProgressHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *,Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferProgressUpdatedEventArgs *)

- ea: `0x18010ab90`
- end: `0x18010adf9`
- name: `?Invoke@RcsFileTransferProgressHandler@RcsFileTransferAdapterImpl@@UEAAJPEAUIRcsFileTransfer@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIRcsFileTransferProgressUpdatedEventArgs@45678@@Z`
- size: `617`
- prototype: `__int64 __fastcall(RcsFileTransferAdapterImpl::RcsFileTransferProgressHandler *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferProgressUpdatedEventArgs *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18008b320`
- `0x1801099a4`
- `0x18010ab90`
- `0x18010b7f0`
- `0x18010bc50`
- `0x1801137c0`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ac55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010adcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ac55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010adcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010aca8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010acfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010aca8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010acfd`

## string_xrefs

- `0x18010abee`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`
- `0x18010ac7e`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`
- `0x18010ad1b`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsFileTransferAdapterImpl::RcsFileTransferProgressHandler::Invoke(
        RcsFileTransferAdapterImpl::RcsFileTransferProgressHandler *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *a2,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferProgressUpdatedEventArgs *a3)
{
  __int64 v3; // rax
  int v7; // ebx
  __int64 v8; // rax
  double v9; // xmm0_8
  __int64 v10; // rax
  __int64 (__fastcall *v11)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, HSTRING *); // rbx
  int v12; // eax
  char v13; // bl
  int v14; // edi
  unsigned int StringRawBuffer; // eax
  int v16; // ecx
  const wchar_t *v17; // rax
  size_t v18; // rdx
  HRESULT v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  HSTRING string; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+40h] [rbp-C8h] BYREF
  _OWORD v25[10]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t pszDest[8]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v27; // [rsp+108h] [rbp+0h]
  __int128 v28; // [rsp+118h] [rbp+10h]
  __int128 v29; // [rsp+128h] [rbp+20h]
  __int128 v30; // [rsp+138h] [rbp+30h]
  __int128 v31; // [rsp+148h] [rbp+40h]
  __int128 v32; // [rsp+158h] [rbp+50h]
  __int128 v33; // [rsp+168h] [rbp+60h]
  __int128 v34; // [rsp+178h] [rbp+70h]
  __int128 v35; // [rsp+188h] [rbp+80h]

  v3 = *(_QWORD *)a3;
  *(_QWORD *)&v24 = 0;
  v7 = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferProgressUpdatedEventArgs *, __int128 *))(v3 + 56))(
         a3,
         &v24);
  if ( v7 < 0
    || (v8 = *(_QWORD *)a3,
        *((_QWORD *)&v24 + 1) = 0,
        v7 = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferProgressUpdatedEventArgs *, char *))(v8 + 48))(
               a3,
               (char *)&v24 + 8),
        v7 < 0) )
  {
    Log_HREvent_38(
      (unsigned int)v7,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp");
  }
  else
  {
    v9 = CalculateFileTransferProgress(v24, *((unsigned __int64 *)&v24 + 1));
    v10 = *(_QWORD *)a2;
    string = 0;
    v11 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, HSTRING *))(v10 + 80);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11(a2, &string);
    if ( v12 < 0 )
      Log_HREvent_38(
        (unsigned int)v12,
        0,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp");
    if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
    {
      v13 = BYTE8(v24);
      v14 = v24;
      StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(string, 0);
      McTemplateU0zxxg_EventWriteTransfer(
        v16,
        (unsigned int)FileTransferProgressUpdated,
        StringRawBuffer,
        v14,
        v13,
        SLOBYTE(v9));
    }
    v34 = 0u;
    v35 = 0;
    memset_0(pszDest, 0, 0x80u);
    v17 = WindowsGetStringRawBuffer(string, 0);
    v19 = StringCchCopyW(pszDest, v18, v17);
    v7 = v19;
    if ( v19 >= 0 )
    {
      v34 = v24;
      v25[0] = *(_OWORD *)pszDest;
      v20 = *((_QWORD *)this + 16);
      v25[1] = v27;
      *(_QWORD *)&v35 = v20;
      v21 = *((_QWORD *)this + 17);
      v25[2] = v28;
      *((_QWORD *)&v35 + 1) = v21;
      v25[3] = v29;
      v25[4] = v30;
      v25[5] = v31;
      v25[6] = v32;
      v25[7] = v33;
      v25[8] = v24;
      v25[9] = v35;
      RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat,Windows::Phone::Restricted::Cellular::Rcs::RcsChatMultipartMessageFileTransferProgressUpdatedEventArgs,RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs>::_PublishNotifications(
        (char *)this - 8,
        v25);
      v7 = 0;
    }
    else
    {
      Log_HREvent_38(
        (unsigned int)v19,
        1,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp");
    }
    WindowsDeleteString(string);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18010ab90  mov     rax, rsp
0x18010ab93  push    rbp
0x18010ab94  push    rbx
0x18010ab95  push    rsi
0x18010ab96  push    rdi
0x18010ab97  push    r14
0x18010ab99  lea     rbp, [rax-0D8h]
0x18010aba0  sub     rsp, 1B0h
0x18010aba7  movaps  xmmword ptr [rax-38h], xmm6
0x18010abab  mov     rax, cs:__security_cookie
0x18010abb2  xor     rax, rsp
0x18010abb5  mov     [rbp+0D0h+var_40], rax
0x18010abbc  mov     rax, [r8]
0x18010abbf  mov     rsi, rdx
0x18010abc2  mov     r14, rcx
0x18010abc5  mov     qword ptr [rsp+1D0h+var_198], 0
0x18010abce  lea     rdx, [rsp+1D0h+var_198]
0x18010abd3  mov     rcx, r8
0x18010abd6  mov     rdi, r8
0x18010abd9  mov     rax, [rax+38h]
0x18010abdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010abe2  mov     ebx, eax
0x18010abe4  test    eax, eax
0x18010abe6  jns     short loc_18010AC06
0x18010abe8  mov     r9d, 105h
0x18010abee  lea     r8, aOnecoreuapBase_126; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010abf5  mov     edx, 1
0x18010abfa  mov     ecx, ebx
0x18010abfc  call    Log_HREvent_38
0x18010ac01  jmp     loc_18010ADD2
0x18010ac06  mov     rax, [rdi]
0x18010ac09  lea     rdx, [rsp+1D0h+var_198+8]
0x18010ac0e  mov     rcx, rdi
0x18010ac11  mov     qword ptr [rsp+1D0h+var_198+8], 0
0x18010ac1a  mov     rax, [rax+30h]
0x18010ac1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ac23  mov     ebx, eax
0x18010ac25  test    eax, eax
0x18010ac27  jns     short loc_18010AC31
0x18010ac29  mov     r9d, 108h
0x18010ac2f  jmp     short loc_18010ABEE
0x18010ac31  mov     rdx, qword ptr [rsp+1D0h+var_198+8]; unsigned __int64
0x18010ac36  mov     rcx, qword ptr [rsp+1D0h+var_198]; unsigned __int64
0x18010ac3b  call    ?CalculateFileTransferProgress@@YAN_K0@Z; CalculateFileTransferProgress(unsigned __int64,unsigned __int64)
0x18010ac40  mov     rax, [rsi]
0x18010ac43  xor     ecx, ecx; string
0x18010ac45  movaps  xmm6, xmm0
0x18010ac48  mov     [rsp+1D0h+string], 0
0x18010ac51  mov     rbx, [rax+50h]
0x18010ac55  call    cs:__imp_WindowsDeleteString
0x18010ac5b  lea     rdx, [rsp+1D0h+string]
0x18010ac60  mov     [rsp+1D0h+string], 0
0x18010ac69  mov     rcx, rsi
0x18010ac6c  mov     rax, rbx
0x18010ac6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ac74  test    eax, eax
0x18010ac76  jns     short loc_18010AC8E
0x18010ac78  mov     r9d, 10Dh
0x18010ac7e  lea     r8, aOnecoreuapBase_126; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010ac85  xor     edx, edx
0x18010ac87  mov     ecx, eax
0x18010ac89  call    Log_HREvent_38
0x18010ac8e  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x18010ac95  jz      short loc_18010ACCB
0x18010ac97  mov     rcx, [rsp+1D0h+string]; string
0x18010ac9c  xor     edx, edx; length
0x18010ac9e  mov     rbx, qword ptr [rsp+1D0h+var_198+8]
0x18010aca3  mov     rdi, qword ptr [rsp+1D0h+var_198]
0x18010aca8  call    cs:__imp_WindowsGetStringRawBuffer
0x18010acae  movsd   [rsp+1D0h+var_1A8], xmm6
0x18010acb4  lea     rdx, FileTransferProgressUpdated
0x18010acbb  mov     r8, rax
0x18010acbe  mov     [rsp+1D0h+var_1B0], rbx
0x18010acc3  mov     r9, rdi
0x18010acc6  call    McTemplateU0zxxg_EventWriteTransfer
0x18010accb  xorps   xmm0, xmm0
0x18010acce  mov     qword ptr [rbp+0D0h+var_60], 0
0x18010acd6  xor     edx, edx; Val
0x18010acd8  mov     qword ptr [rbp+0D0h+var_60+8], 0
0x18010ace0  mov     r8d, 80h; Size
0x18010ace6  lea     rcx, [rbp+0D0h+pszDest]; void *
0x18010acea  movups  [rbp+0D0h+var_50], xmm0
0x18010acf1  call    memset_0
0x18010acf6  mov     rcx, [rsp+1D0h+string]; string
0x18010acfb  xor     edx, edx; length
0x18010acfd  call    cs:__imp_WindowsGetStringRawBuffer
0x18010ad03  mov     r8, rax; pszSrc
0x18010ad06  lea     rcx, [rbp+0D0h+pszDest]; pszDest
0x18010ad0a  call    StringCchCopyW
0x18010ad0f  mov     ebx, eax
0x18010ad11  test    eax, eax
0x18010ad13  jns     short loc_18010AD33
0x18010ad15  mov     r9d, 112h
0x18010ad1b  lea     r8, aOnecoreuapBase_126; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010ad22  mov     edx, 1
0x18010ad27  mov     ecx, eax
0x18010ad29  call    Log_HREvent_38
0x18010ad2e  jmp     loc_18010ADC7
0x18010ad33  mov     rax, qword ptr [rsp+1D0h+var_198]
0x18010ad38  lea     rcx, [r14-8]
0x18010ad3c  movaps  xmm0, xmmword ptr [rbp+0D0h+pszDest]
0x18010ad40  lea     rdx, [rsp+1D0h+var_188+8]
0x18010ad45  movaps  xmm1, [rbp+0D0h+var_D0]
0x18010ad49  mov     qword ptr [rbp+0D0h+var_60], rax
0x18010ad4d  mov     rax, qword ptr [rsp+1D0h+var_198+8]
0x18010ad52  movups  [rsp+1D0h+var_188+8], xmm0
0x18010ad57  mov     qword ptr [rbp+0D0h+var_60+8], rax
0x18010ad5b  movaps  xmm0, [rbp+0D0h+var_C0]
0x18010ad5f  mov     rax, [r14+80h]
0x18010ad66  movups  [rsp+1D0h+var_178+8], xmm1
0x18010ad6b  mov     qword ptr [rbp+0D0h+var_50], rax
0x18010ad72  movaps  xmm1, [rbp+0D0h+var_B0]
0x18010ad76  mov     rax, [r14+88h]
0x18010ad7d  movups  [rsp+1D0h+var_168+8], xmm0
0x18010ad82  mov     qword ptr [rbp+0D0h+var_50+8], rax
0x18010ad89  movaps  xmm0, [rbp+0D0h+var_A0]
0x18010ad8d  movups  [rbp+0D0h+var_150], xmm1
0x18010ad91  movaps  xmm1, [rbp+0D0h+var_90]
0x18010ad95  movups  [rbp+0D0h+var_140], xmm0
0x18010ad99  movaps  xmm0, [rbp+0D0h+var_80]
0x18010ad9d  movups  [rbp+0D0h+var_130], xmm1
0x18010ada1  movaps  xmm1, [rbp+0D0h+var_70]
0x18010ada5  movups  [rbp+0D0h+var_120], xmm0
0x18010ada9  movaps  xmm0, [rbp+0D0h+var_60]
0x18010adad  movups  [rbp+0D0h+var_110], xmm1
0x18010adb1  movaps  xmm1, [rbp+0D0h+var_50]
0x18010adb8  movups  [rbp+0D0h+var_100], xmm0
0x18010adbc  movups  [rbp+0D0h+var_F0], xmm1
0x18010adc0  call    ?_PublishNotifications@?$RcsEventHandler@VRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsChat@23456@VRcsChatMultipartMessageFileTransferProgressUpdatedEventArgs@23456@URcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs@@@@IEAAXURcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat,Windows::Phone::Restricted::Cellular::Rcs::RcsChatMultipartMessageFileTransferProgressUpdatedEventArgs,RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs>::_PublishNotifications(RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs)
0x18010adc5  xor     ebx, ebx
0x18010adc7  mov     rcx, [rsp+1D0h+string]; string
0x18010adcc  call    cs:__imp_WindowsDeleteString
0x18010add2  mov     eax, ebx
0x18010add4  mov     rcx, [rbp+0D0h+var_40]
0x18010addb  xor     rcx, rsp; StackCookie
0x18010adde  call    __security_check_cookie
0x18010ade3  movaps  xmm6, [rsp+1D0h+var_38+8]
0x18010adeb  add     rsp, 1B0h
0x18010adf2  pop     r14
0x18010adf4  pop     rdi
0x18010adf5  pop     rsi
0x18010adf6  pop     rbx
0x18010adf7  pop     rbp
0x18010adf8  retn
```

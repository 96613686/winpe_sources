# CloudFilesToastCallbackHandler::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x18034e440`
- end: `0x18034e9fd`
- name: `?Activate@CloudFilesToastCallbackHandler@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `1469`
- prototype: `int(CloudFilesToastCallbackHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18002d710`
- `0x18002f7c0`
- `0x180038f50`
- `0x180133f50`
- `0x1801f4760`
- `0x1801f4de8`
- `0x180266d70`
- `0x18034e33c`
- `0x18034e440`
- `0x18034ea04`
- `0x18034ea48`
- `0x18034eb30`
- `0x18034ebe8`
- `0x18036a5b8`
- `0x18038af1c`
- `0x180391f34`
- `0x1803b1f60`
- `0x18058ae94`
- `0x18058af08`
- `0x18058af70`
- `0x18058afa0`
- `0x18058b39c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x18034e7a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x18034e7cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x18034e7fe`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x18034e7a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x18034e7cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x18034e7fe`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18034e537`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18034e537`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18034e892`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18034e892`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e488`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e61a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e694`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e6c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e716`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e841`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e488`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e61a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e694`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e6c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e716`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034e841`
- `cldapi!CfAbortOperation` at `0x18034e8a9`
- `cldapi!CfAbortOperation` at `0x18034e8d1`
- `cldapi!CfAbortOperation` at `0x18034e8a9`
- `cldapi!CfAbortOperation` at `0x18034e8d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CloudFilesToastCallbackHandler::Activate(
        CloudFilesToastCallbackHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4,
        unsigned int a5)
{
  unsigned int v6; // edi
  int v7; // ebx
  __int64 v8; // rdx
  wchar_t *v10; // rcx
  wchar_t *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  const char *v14; // r9
  unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rsi
  unsigned __int16 *v17; // rcx
  int v18; // eax
  const unsigned __int16 *v19; // r9
  unsigned __int16 *v20; // rcx
  unsigned __int16 *v21; // r8
  unsigned __int16 *v22; // rdx
  CloudFiles::UI::Toast::ToastFactory *v23; // rcx
  int CloudFilesHydrationConfirmToast; // eax
  __int64 v25; // rdx
  unsigned __int16 *v26; // rcx
  unsigned __int16 *v27; // rcx
  unsigned __int16 *v28; // rdx
  int v29; // ebx
  unsigned __int16 *v30; // rcx
  unsigned __int16 *v31; // rcx
  unsigned __int16 *v32; // rcx
  unsigned __int16 *v33; // rcx
  unsigned __int16 *v34; // rcx
  unsigned __int16 *v35; // rax
  unsigned __int16 *v36; // rcx
  __int64 v37; // rcx
  unsigned __int16 *v38; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-608h]
  int bIgnoreCasea; // [rsp+20h] [rbp-608h]
  unsigned int v41; // [rsp+30h] [rbp-5F8h] BYREF
  wchar_t v42[16]; // [rsp+38h] [rbp-5F0h] BYREF
  wchar_t *v43; // [rsp+58h] [rbp-5D0h] BYREF
  wchar_t *Context; // [rsp+60h] [rbp-5C8h] BYREF
  unsigned __int16 *v45; // [rsp+68h] [rbp-5C0h] BYREF
  __int64 v46; // [rsp+70h] [rbp-5B8h]
  wchar_t Delimiter; // [rsp+80h] [rbp-5A8h] BYREF
  __int128 v48; // [rsp+88h] [rbp-5A0h] BYREF
  __int128 v49; // [rsp+98h] [rbp-590h]
  _QWORD v50[42]; // [rsp+B0h] [rbp-578h] BYREF
  wchar_t String[512]; // [rsp+200h] [rbp-428h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+628h] [rbp+0h]

  v6 = 1;
  if ( CompareStringOrdinal(a2, -1, L"Windows.System.AppInitiatedDownload", -1, 1) != 2 || !a3 || !*a3 )
    return 2147942487LL;
  v7 = StringCchCopyW(&Delimiter, 2u, L"$");
  if ( v7 < 0 )
  {
    v8 = 46;
    goto LABEL_6;
  }
  v7 = StringCchCopyW(String, 0x200u, a3);
  if ( v7 >= 0 )
  {
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,wil::com_ptr_t<ITransferBatch,wil::err_returncode_policy>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,wil::com_ptr_t<ITransferBatch,wil::err_returncode_policy>>>>>>>(&v45);
    Context = 0;
    v10 = String;
    while ( 1 )
    {
      v11 = wcstok_s(v10, &Delimiter, &Context);
      v43 = v11;
      if ( !v11 )
        break;
      v13 = -1;
      do
        ++v13;
      while ( v11[v13] );
      try
      {
        v41 = v13;
        std::vector<std::wstring>::emplace_back<unsigned short * &,unsigned int>(&v45, &v43, &v41);
        v10 = 0;
      }
      catch ( ... )
      {
        v41 = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x3C,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasthandler.cpp",
                v14);
        std::vector<std::wstring>::_Tidy(&v45);
        return v41;
      }
    }
    v15 = v45;
    if ( (unsigned __int64)((v46 - (__int64)v45) >> 5) < 4 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v12);
      v15 = v45;
    }
    if ( a5 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v12);
      v15 = v45;
    }
    v16 = v15 + 48;
    if ( *((_QWORD *)v15 + 15) > 7u )
      v16 = *(const unsigned __int16 **)v16;
    if ( *((_QWORD *)v15 + 3) > 7u )
      v15 = *(unsigned __int16 **)v15;
    wil::ActivityBase<CloudFileProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudFileProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v50);
    v50[0] = &CloudFilesTelemetry::AID_ButtonClickHandler::`vftable';
    CloudFilesTelemetry::AID_ButtonClickHandler::StartActivity(
      (CloudFilesTelemetry::AID_ButtonClickHandler *)v50,
      v15,
      v16);
    v17 = v45;
    if ( *((_QWORD *)v45 + 3) > 7u )
      v17 = *(unsigned __int16 **)v45;
    v18 = CompareStringOrdinal(v17, -1, L"Toast.Progress.Button.CancelDownload", -1, 1);
    v20 = v45;
    if ( v18 == 2 )
    {
      v21 = v45 + 16;
      if ( *((_QWORD *)v45 + 7) > 7u )
        v21 = *(unsigned __int16 **)v21;
      v22 = v45 + 48;
      if ( *((_QWORD *)v45 + 15) > 7u )
        v22 = *(unsigned __int16 **)v22;
      v23 = (CloudFiles::UI::Toast::ToastFactory *)(v45 + 32);
      if ( *((_QWORD *)v45 + 11) > 7u )
        v23 = *(CloudFiles::UI::Toast::ToastFactory **)v23;
      CloudFilesHydrationConfirmToast = CloudFiles::UI::Toast::ToastFactory::MakeCloudFilesHydrationConfirmToast(
                                          v23,
                                          v22,
                                          v21,
                                          v19);
      v7 = CloudFilesHydrationConfirmToast;
      if ( CloudFilesHydrationConfirmToast < 0 )
      {
        v25 = 74;
LABEL_75:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasthandler.cpp",
          (const char *)(unsigned int)CloudFilesHydrationConfirmToast,
          bIgnoreCasea);
        goto LABEL_76;
      }
      CloudFilesTelemetry::AIDToast_LaunchConfirm();
    }
    else
    {
      if ( *((_QWORD *)v45 + 3) > 7u )
        v20 = *(unsigned __int16 **)v45;
      if ( CompareStringOrdinal(v20, -1, L"Toast.Progress.Body", -1, 1) == 2 )
        goto LABEL_71;
      v26 = v45;
      if ( *((_QWORD *)v45 + 3) > 7u )
        v26 = *(unsigned __int16 **)v45;
      if ( CompareStringOrdinal(v26, -1, L"Toast.Confirm.Body", -1, 1) == 2 )
      {
LABEL_71:
        v38 = v45 + 32;
        if ( *((_QWORD *)v45 + 11) > 7u )
          v38 = *(unsigned __int16 **)v38;
        CloudFilesHydrationConfirmToast = CloudFiles::UI::Toast::Utility::UpdateToast(v38, 0, 1);
        v7 = CloudFilesHydrationConfirmToast;
        if ( CloudFilesHydrationConfirmToast < 0 )
        {
          v25 = 81;
          goto LABEL_75;
        }
        ShellExecuteW(0, 0, L"ms-settings:privacy-automaticfiledownloads", 0, 0, 1);
        CloudFilesTelemetry::AIDToast_LaunchSettings();
      }
      else
      {
        v48 = 0;
        v49 = 0;
        v27 = v45;
        if ( *((_QWORD *)v45 + 3) > 7u )
          v27 = *(unsigned __int16 **)v45;
        if ( CompareStringOrdinal(v27, -1, L"Toast.Confirm.Button.Cancel", -1, 1) == 2 )
        {
          v28 = v45 + 64;
          if ( *((_QWORD *)v45 + 19) > 7u )
            v28 = *(unsigned __int16 **)v28;
          std::wstring::wstring(v42, v28);
          v29 = std::stoi(v42);
          v41 = v29;
          std::pair<std::wstring,int>::~pair<std::wstring,int>(v42);
          if ( v29 <= 1 )
          {
            v30 = v45;
            if ( v46 - (_QWORD)v45 != 256 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v45);
              v30 = v45;
            }
            v31 = v30 + 80;
            if ( *((_QWORD *)v31 + 3) > 7u )
              v31 = *(unsigned __int16 **)v31;
            *(_QWORD *)&v48 = _wcstoi64(v31, 0, 0);
            v32 = v45 + 96;
            if ( *((_QWORD *)v45 + 27) > 7u )
              v32 = *(unsigned __int16 **)v32;
            *((_QWORD *)&v48 + 1) = _wcstoi64(v32, 0, 0);
            v33 = v45 + 112;
            if ( *((_QWORD *)v45 + 31) > 7u )
              v33 = *(unsigned __int16 **)v33;
            *(_QWORD *)&v49 = _wcstoi64(v33, 0, 0);
            v6 = 0;
          }
          CloudFilesTelemetry::AIDToast_Canceled<int const &>(&v41);
        }
        else
        {
          v34 = v45;
          if ( *((_QWORD *)v45 + 3) > 7u )
            v34 = *(unsigned __int16 **)v45;
          if ( CompareStringOrdinal(v34, -1, L"Toast.Confirm.Button.Block", -1, 1) != 2 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7A,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasthandler.cpp",
              (const char *)0x80070057LL,
              bIgnoreCasea);
            v7 = -2147024809;
LABEL_76:
            CloudFilesTelemetry::AID_ButtonClickHandler::~AID_ButtonClickHandler((CloudFilesTelemetry::AID_ButtonClickHandler *)v50);
            std::vector<std::wstring>::_Tidy(&v45);
            return (unsigned int)v7;
          }
          v6 = 2;
          v35 = v45 + 48;
          if ( *((_QWORD *)v45 + 15) > 7u )
            v35 = *(unsigned __int16 **)v35;
          v43 = v35;
          CloudFilesTelemetry::AIDToast_BlockApp<unsigned short const *>(&v43);
        }
        v36 = v45 + 32;
        if ( *((_QWORD *)v45 + 11) > 7u )
          v36 = *(unsigned __int16 **)v36;
        v37 = wcstoul(v36, 0, 0);
        if ( v6 )
        {
          CloudFilesHydrationConfirmToast = CfAbortOperation(v37, 0, v6);
          v7 = CloudFilesHydrationConfirmToast;
          if ( CloudFilesHydrationConfirmToast < 0 )
          {
            v25 = 130;
            goto LABEL_75;
          }
        }
        else
        {
          CloudFilesHydrationConfirmToast = CfAbortOperation(v37, &v48, 0);
          v7 = CloudFilesHydrationConfirmToast;
          if ( CloudFilesHydrationConfirmToast < 0 )
          {
            v25 = 134;
            goto LABEL_75;
          }
        }
      }
    }
    wil::ActivityBase<CloudFileProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v50, 0);
    CloudFilesTelemetry::AID_ButtonClickHandler::~AID_ButtonClickHandler((CloudFilesTelemetry::AID_ButtonClickHandler *)v50);
    std::vector<std::wstring>::_Tidy(&v45);
    return 0;
  }
  v8 = 47;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasthandler.cpp",
    (const char *)(unsigned int)v7,
    bIgnoreCase);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18034e440  mov     [rsp+arg_0], rbx
0x18034e445  mov     [rsp+arg_18], rsi
0x18034e44a  push    rdi
0x18034e44b  push    r12
0x18034e44d  push    r15
0x18034e44f  sub     rsp, 610h
0x18034e456  mov     rax, cs:__security_cookie
0x18034e45d  xor     rax, rsp
0x18034e460  mov     [rsp+628h+var_28], rax
0x18034e468  mov     rsi, r8
0x18034e46b  mov     rcx, rdx; lpString1
0x18034e46e  mov     edi, 1
0x18034e473  mov     [rsp+628h+bIgnoreCase], edi; int
0x18034e477  or      r12, 0FFFFFFFFFFFFFFFFh
0x18034e47b  mov     r9d, r12d; cchCount2
0x18034e47e  lea     r8, aWindowsSystemA; "Windows.System.AppInitiatedDownload"
0x18034e485  mov     edx, r12d; cchCount1
0x18034e488  call    cs:__imp_CompareStringOrdinal
0x18034e48f  nop     dword ptr [rax+rax+00h]
0x18034e494  cmp     eax, 2
0x18034e497  jnz     loc_18034E9CE
0x18034e49d  xor     r15d, r15d
0x18034e4a0  test    rsi, rsi
0x18034e4a3  jz      loc_18034E9CE
0x18034e4a9  cmp     [rsi], r15w
0x18034e4ad  jz      loc_18034E9CE
0x18034e4b3  lea     r8, asc_1807381CC; "$"
0x18034e4ba  mov     edx, eax; unsigned __int64
0x18034e4bc  lea     rcx, [rsp+628h+Delimiter]; unsigned __int16 *
0x18034e4c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18034e4c9  mov     ebx, eax
0x18034e4cb  test    eax, eax
0x18034e4cd  jns     short loc_18034E4F0
0x18034e4cf  lea     edx, [rdi+2Dh]; void *
0x18034e4d2  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\windows.storage\\clo"...
0x18034e4d9  mov     r9d, ebx; char *
0x18034e4dc  mov     rcx, [rsp+628h]; this
0x18034e4e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e4e9  mov     eax, ebx
0x18034e4eb  jmp     loc_18034E9D3
0x18034e4f0  mov     r8, rsi; unsigned __int16 *
0x18034e4f3  mov     edx, 200h; unsigned __int64
0x18034e4f8  lea     rcx, [rsp+628h+String]; unsigned __int16 *
0x18034e500  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18034e505  mov     ebx, eax
0x18034e507  test    eax, eax
0x18034e509  jns     short loc_18034E512
0x18034e50b  mov     edx, 2Fh ; '/'
0x18034e510  jmp     short loc_18034E4D2
0x18034e512  lea     rcx, [rsp+628h+var_5C0]; void *
0x18034e517  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UITransferBatch@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UITransferBatch@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UITransferBatch@@Uerr_returncode_policy@wil@@@wil@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,wil::com_ptr_t<ITransferBatch,wil::err_returncode_policy>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,wil::com_ptr_t<ITransferBatch,wil::err_returncode_policy>>>>>>>(std::allocator<std::pair<std::wstring const,wil::com_ptr_t<ITransferBatch,wil::err_returncode_policy>>> const &)
0x18034e51c  nop
0x18034e51d  mov     [rsp+628h+Context], r15
0x18034e522  lea     rcx, [rsp+628h+String]; String
0x18034e52a  lea     r8, [rsp+628h+Context]; Context
0x18034e52f  lea     rdx, [rsp+628h+Delimiter]; Delimiter
0x18034e537  call    cs:__imp_wcstok_s
0x18034e53e  nop     dword ptr [rax+rax+00h]
0x18034e543  mov     [rsp+628h+var_5D0], rax
0x18034e548  test    rax, rax
0x18034e54b  jz      short loc_18034E576
0x18034e54d  mov     rcx, r12
0x18034e550  inc     rcx
0x18034e553  cmp     [rax+rcx*2], r15w
0x18034e558  jnz     short loc_18034E550
0x18034e55a  mov     [rsp+628h+var_5F8], ecx
0x18034e55e  lea     r8, [rsp+628h+var_5F8]
0x18034e563  lea     rdx, [rsp+628h+var_5D0]
0x18034e568  lea     rcx, [rsp+628h+var_5C0]
0x18034e56d  call    ??$emplace_back@AEAPEAGI@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAPEAG$$QEAI@Z; std::vector<std::wstring>::emplace_back<ushort * &,uint>(ushort * &,uint &&)
0x18034e572  xor     ecx, ecx
0x18034e574  jmp     short loc_18034E52A
0x18034e576  mov     rax, [rsp+628h+var_5B8]
0x18034e57b  mov     rbx, [rsp+628h+var_5C0]
0x18034e580  sub     rax, rbx
0x18034e583  sar     rax, 5
0x18034e587  cmp     rax, 4
0x18034e58b  jnb     short loc_18034E597
0x18034e58d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "tokens.size() >= 4")
0x18034e592  mov     rbx, [rsp+628h+var_5C0]
0x18034e597  cmp     [rsp+628h+arg_20], r15d
0x18034e59f  jz      short loc_18034E5AB
0x18034e5a1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "count == 0")
0x18034e5a6  mov     rbx, [rsp+628h+var_5C0]
0x18034e5ab  lea     rsi, [rbx+60h]
0x18034e5af  cmp     qword ptr [rsi+18h], 7
0x18034e5b4  jbe     short loc_18034E5B9
0x18034e5b6  mov     rsi, [rsi]
0x18034e5b9  cmp     qword ptr [rbx+18h], 7
0x18034e5be  jbe     short loc_18034E5C3
0x18034e5c0  mov     rbx, [rbx]
0x18034e5c3  lea     rdx, aAidButtonclick; "AID_ButtonClickHandler"
0x18034e5ca  lea     rcx, [rsp+628h+var_578]; struct wil::details::IFailureCallback *
0x18034e5d2  call    ??0?$ActivityBase@VCloudFileProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CloudFileProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudFileProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18034e5d7  lea     rax, ??_7AID_ButtonClickHandler@CloudFilesTelemetry@@6B@; const CloudFilesTelemetry::AID_ButtonClickHandler::`vftable'
0x18034e5de  mov     [rsp+628h+var_578], rax
0x18034e5e6  mov     r8, rsi; unsigned __int16 *
0x18034e5e9  mov     rdx, rbx; unsigned __int16 *
0x18034e5ec  lea     rcx, [rsp+628h+var_578]; this
0x18034e5f4  call    ?StartActivity@AID_ButtonClickHandler@CloudFilesTelemetry@@QEAAXPEBG0@Z; CloudFilesTelemetry::AID_ButtonClickHandler::StartActivity(ushort const *,ushort const *)
0x18034e5f9  nop
0x18034e5fa  mov     rcx, [rsp+628h+var_5C0]
0x18034e5ff  cmp     qword ptr [rcx+18h], 7
0x18034e604  jbe     short loc_18034E609
0x18034e606  mov     rcx, [rcx]; lpString1
0x18034e609  mov     [rsp+628h+bIgnoreCase], edi; bIgnoreCase
0x18034e60d  mov     r9d, r12d; cchCount2
0x18034e610  lea     r8, aToastProgressB_0; "Toast.Progress.Button.CancelDownload"
0x18034e617  mov     edx, r12d; cchCount1
0x18034e61a  call    cs:__imp_CompareStringOrdinal
0x18034e621  nop     dword ptr [rax+rax+00h]
0x18034e626  mov     rcx, [rsp+628h+var_5C0]
0x18034e62b  cmp     eax, 2
0x18034e62e  jnz     short loc_18034E679
0x18034e630  lea     r8, [rcx+20h]
0x18034e634  cmp     qword ptr [r8+18h], 7
0x18034e639  jbe     short loc_18034E63E
0x18034e63b  mov     r8, [r8]; unsigned __int16 *
0x18034e63e  lea     rdx, [rcx+60h]
0x18034e642  cmp     qword ptr [rdx+18h], 7
0x18034e647  jbe     short loc_18034E64C
0x18034e649  mov     rdx, [rdx]; unsigned __int16 *
0x18034e64c  add     rcx, 40h ; '@'
0x18034e650  cmp     qword ptr [rcx+18h], 7
0x18034e655  jbe     short loc_18034E65A
0x18034e657  mov     rcx, [rcx]; this
0x18034e65a  call    ?MakeCloudFilesHydrationConfirmToast@ToastFactory@Toast@UI@CloudFiles@@YAJPEBG00@Z; CloudFiles::UI::Toast::ToastFactory::MakeCloudFilesHydrationConfirmToast(ushort const *,ushort const *,ushort const *)
0x18034e65f  mov     ebx, eax
0x18034e661  test    eax, eax
0x18034e663  jns     short loc_18034E66F
0x18034e665  mov     edx, 4Ah ; 'J'
0x18034e66a  jmp     loc_18034E93C
0x18034e66f  call    ?AIDToast_LaunchConfirm@CloudFilesTelemetry@@SAXXZ; CloudFilesTelemetry::AIDToast_LaunchConfirm(void)
0x18034e674  jmp     loc_18034E992
0x18034e679  cmp     qword ptr [rcx+18h], 7
0x18034e67e  jbe     short loc_18034E683
0x18034e680  mov     rcx, [rcx]; lpString1
0x18034e683  mov     [rsp+628h+bIgnoreCase], edi; int
0x18034e687  mov     r9d, r12d; cchCount2
0x18034e68a  lea     r8, aToastProgressB; "Toast.Progress.Body"
0x18034e691  mov     edx, r12d; cchCount1
0x18034e694  call    cs:__imp_CompareStringOrdinal
0x18034e69b  nop     dword ptr [rax+rax+00h]
0x18034e6a0  cmp     eax, 2
0x18034e6a3  jz      loc_18034E914
0x18034e6a9  mov     rcx, [rsp+628h+var_5C0]
0x18034e6ae  cmp     qword ptr [rcx+18h], 7
0x18034e6b3  jbe     short loc_18034E6B8
0x18034e6b5  mov     rcx, [rcx]; lpString1
0x18034e6b8  mov     [rsp+628h+bIgnoreCase], edi; bIgnoreCase
0x18034e6bc  mov     r9d, r12d; cchCount2
0x18034e6bf  lea     r8, aToastConfirmBo; "Toast.Confirm.Body"
0x18034e6c6  mov     edx, r12d; cchCount1
0x18034e6c9  call    cs:__imp_CompareStringOrdinal
0x18034e6d0  nop     dword ptr [rax+rax+00h]
0x18034e6d5  cmp     eax, 2
0x18034e6d8  jz      loc_18034E914
0x18034e6de  xorps   xmm0, xmm0
0x18034e6e1  movdqu  [rsp+628h+var_5A0], xmm0
0x18034e6ea  xorps   xmm1, xmm1
0x18034e6ed  movdqu  [rsp+628h+var_590], xmm1
0x18034e6f6  mov     rcx, [rsp+628h+var_5C0]
0x18034e6fb  cmp     qword ptr [rcx+18h], 7
0x18034e700  jbe     short loc_18034E705
0x18034e702  mov     rcx, [rcx]; lpString1
0x18034e705  mov     [rsp+628h+bIgnoreCase], edi; bIgnoreCase
0x18034e709  mov     r9d, r12d; cchCount2
0x18034e70c  lea     r8, aToastConfirmBu_0; "Toast.Confirm.Button.Cancel"
0x18034e713  mov     edx, r12d; cchCount1
0x18034e716  call    cs:__imp_CompareStringOrdinal
0x18034e71d  nop     dword ptr [rax+rax+00h]
0x18034e722  cmp     eax, 2
0x18034e725  jnz     loc_18034E821
0x18034e72b  mov     rdx, [rsp+628h+var_5C0]
0x18034e730  sub     rdx, 0FFFFFFFFFFFFFF80h
0x18034e734  cmp     qword ptr [rdx+18h], 7
0x18034e739  jbe     short loc_18034E73E
0x18034e73b  mov     rdx, [rdx]
0x18034e73e  lea     rcx, [rsp+628h+var_5F0]
0x18034e743  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18034e748  nop
0x18034e749  lea     rcx, [rsp+628h+var_5F0]; String
0x18034e74e  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x18034e753  mov     ebx, eax
0x18034e755  mov     [rsp+628h+var_5F8], eax
0x18034e759  lea     rcx, [rsp+628h+var_5F0]; void *
0x18034e75e  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@QEAA@XZ; std::pair<std::wstring,int>::~pair<std::wstring,int>(void)
0x18034e763  cmp     ebx, edi
0x18034e765  jg      loc_18034E815
0x18034e76b  mov     rax, [rsp+628h+var_5B8]
0x18034e770  mov     rcx, [rsp+628h+var_5C0]
0x18034e775  sub     rax, rcx
0x18034e778  cmp     rax, 100h
0x18034e77e  jz      short loc_18034E78A
0x18034e780  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "tokens.size() == 8")
0x18034e785  mov     rcx, [rsp+628h+var_5C0]
0x18034e78a  add     rcx, 0A0h
0x18034e791  cmp     qword ptr [rcx+18h], 7
0x18034e796  jbe     short loc_18034E79B
0x18034e798  mov     rcx, [rcx]; String
0x18034e79b  xor     r8d, r8d; Radix
0x18034e79e  xor     edx, edx; EndPtr
0x18034e7a0  call    cs:__imp__wcstoi64
0x18034e7a7  nop     dword ptr [rax+rax+00h]
0x18034e7ac  mov     qword ptr [rsp+628h+var_5A0], rax
0x18034e7b4  mov     rcx, [rsp+628h+var_5C0]
0x18034e7b9  add     rcx, 0C0h
0x18034e7c0  cmp     qword ptr [rcx+18h], 7
0x18034e7c5  jbe     short loc_18034E7CA
0x18034e7c7  mov     rcx, [rcx]; String
0x18034e7ca  xor     r8d, r8d; Radix
0x18034e7cd  xor     edx, edx; EndPtr
0x18034e7cf  call    cs:__imp__wcstoi64
0x18034e7d6  nop     dword ptr [rax+rax+00h]
0x18034e7db  mov     qword ptr [rsp+628h+var_5A0+8], rax
0x18034e7e3  mov     rcx, [rsp+628h+var_5C0]
0x18034e7e8  add     rcx, 0E0h
0x18034e7ef  cmp     qword ptr [rcx+18h], 7
0x18034e7f4  jbe     short loc_18034E7F9
0x18034e7f6  mov     rcx, [rcx]; String
0x18034e7f9  xor     r8d, r8d; Radix
0x18034e7fc  xor     edx, edx; EndPtr
0x18034e7fe  call    cs:__imp__wcstoi64
0x18034e805  nop     dword ptr [rax+rax+00h]
0x18034e80a  mov     qword ptr [rsp+628h+var_590], rax
0x18034e812  mov     edi, r15d
0x18034e815  lea     rcx, [rsp+628h+var_5F8]
0x18034e81a  call    ??$AIDToast_Canceled@AEBH@CloudFilesTelemetry@@SAXAEBH@Z; CloudFilesTelemetry::AIDToast_Canceled<int const &>(int const &)
0x18034e81f  jmp     short loc_18034E87A
0x18034e821  mov     rcx, [rsp+628h+var_5C0]
0x18034e826  cmp     qword ptr [rcx+18h], 7
0x18034e82b  jbe     short loc_18034E830
0x18034e82d  mov     rcx, [rcx]; lpString1
0x18034e830  mov     [rsp+628h+bIgnoreCase], edi; int
0x18034e834  mov     r9d, r12d; cchCount2
0x18034e837  lea     r8, aToastConfirmBu; "Toast.Confirm.Button.Block"
0x18034e83e  mov     edx, r12d; cchCount1
0x18034e841  call    cs:__imp_CompareStringOrdinal
0x18034e848  nop     dword ptr [rax+rax+00h]
0x18034e84d  cmp     eax, 2
0x18034e850  jnz     loc_18034E8EE
0x18034e856  mov     edi, eax
0x18034e858  mov     rax, [rsp+628h+var_5C0]
0x18034e85d  add     rax, 60h ; '`'
0x18034e861  cmp     qword ptr [rax+18h], 7
0x18034e866  jbe     short loc_18034E86B
0x18034e868  mov     rax, [rax]
0x18034e86b  mov     [rsp+628h+var_5D0], rax
0x18034e870  lea     rcx, [rsp+628h+var_5D0]
0x18034e875  call    ??$AIDToast_BlockApp@PEBG@CloudFilesTelemetry@@SAX$$QEAPEBG@Z; CloudFilesTelemetry::AIDToast_BlockApp<ushort const *>(ushort const * &&)
0x18034e87a  mov     rcx, [rsp+628h+var_5C0]
0x18034e87f  add     rcx, 40h ; '@'
0x18034e883  cmp     qword ptr [rcx+18h], 7
0x18034e888  jbe     short loc_18034E88D
0x18034e88a  mov     rcx, [rcx]; String
0x18034e88d  xor     r8d, r8d; Radix
0x18034e890  xor     edx, edx; EndPtr
0x18034e892  call    cs:__imp_wcstoul
0x18034e899  nop     dword ptr [rax+rax+00h]
0x18034e89e  mov     ecx, eax
0x18034e8a0  test    edi, edi
0x18034e8a2  jz      short loc_18034E8C6
0x18034e8a4  mov     r8d, edi
0x18034e8a7  xor     edx, edx
0x18034e8a9  call    cs:__imp_CfAbortOperation
0x18034e8b0  nop     dword ptr [rax+rax+00h]
0x18034e8b5  mov     ebx, eax
0x18034e8b7  test    eax, eax
0x18034e8b9  jns     loc_18034E992
0x18034e8bf  mov     edx, 82h
0x18034e8c4  jmp     short loc_18034E93C
0x18034e8c6  xor     r8d, r8d
0x18034e8c9  lea     rdx, [rsp+628h+var_5A0]
0x18034e8d1  call    cs:__imp_CfAbortOperation
0x18034e8d8  nop     dword ptr [rax+rax+00h]
0x18034e8dd  mov     ebx, eax
0x18034e8df  test    eax, eax
0x18034e8e1  jns     loc_18034E992
0x18034e8e7  mov     edx, 86h
0x18034e8ec  jmp     short loc_18034E93C
0x18034e8ee  mov     rcx, [rsp+628h]; this
0x18034e8f6  mov     r9d, 80070057h; char *
0x18034e8fc  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\windows.storage\\clo"...
0x18034e903  mov     edx, 7Ah ; 'z'; void *
0x18034e908  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e90d  mov     ebx, 80070057h
0x18034e912  jmp     short loc_18034E954
0x18034e914  mov     rcx, [rsp+628h+var_5C0]
0x18034e919  add     rcx, 40h ; '@'
0x18034e91d  cmp     qword ptr [rcx+18h], 7
0x18034e922  jbe     short loc_18034E927
0x18034e924  mov     rcx, [rcx]
0x18034e927  mov     r8d, edi
0x18034e92a  xor     edx, edx
0x18034e92c  call    ?UpdateToast@Utility@Toast@UI@CloudFiles@@YAJPEBGIW4ToastVisibility@@@Z; CloudFiles::UI::Toast::Utility::UpdateToast(ushort const *,uint,ToastVisibility)
0x18034e931  mov     ebx, eax
0x18034e933  test    eax, eax
0x18034e935  jns     short loc_18034E971
0x18034e937  mov     edx, 51h ; 'Q'; void *
0x18034e93c  mov     r9d, eax; char *
  ... truncated ...
```

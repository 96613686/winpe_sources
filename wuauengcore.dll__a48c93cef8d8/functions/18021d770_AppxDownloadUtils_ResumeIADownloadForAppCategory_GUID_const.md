# AppxDownloadUtils::ResumeIADownloadForAppCategory(_GUID const &)

- ea: `0x18021d770`
- end: `0x18021dc59`
- name: `?ResumeIADownloadForAppCategory@AppxDownloadUtils@@YAJAEBU_GUID@@@Z`
- size: `1257`
- prototype: `__int64 __fastcall(AppxDownloadUtils *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180212d00`

## callees

- `0x18000c824`
- `0x18007b8a4`
- `0x180113ae8`
- `0x18021d4b4`
- `0x18021d770`
- `0x18021f6e0`
- `0x18021f76c`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021d859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021dae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021dbeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021d859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021dae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021dbeb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18021d83f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18021d83f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18021dad9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18021dbde`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18021dad9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18021dbde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021d8b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021da68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021d8b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021da68`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18021d8ee`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18021d8ee`

## string_xrefs

- `0x18021d8aa`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall AppxDownloadUtils::ResumeIADownloadForAppCategory(
        AppxDownloadUtils *this,
        const struct _GUID *a2,
        unsigned int *a3)
{
  AppxDownloadUtils *v3; // rsi
  char v4; // r13
  __int64 v5; // rdx
  signed int UserTokens; // ebx
  unsigned int v7; // r14d
  void *v8; // rdi
  unsigned int v9; // r12d
  BOOL v10; // edi
  bool v11; // r15
  signed int LastError; // eax
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  HSTRING v16; // rbx
  void **v17; // rcx
  void **v18; // rdi
  __int64 (__fastcall *v19)(void **, GUID *, __int64 *); // rbx
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, HSTRING); // rdi
  unsigned __int64 v23; // rdx
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  __int64 v27; // rcx
  void **v28; // rcx
  __int64 v29; // rcx
  void **v30; // rcx
  bool v31; // zf
  __int64 v32; // rcx
  void **v33; // rcx
  __int64 v34; // rcx
  __int64 v36; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+28h] [rbp-D8h]
  __int64 v38; // [rsp+30h] [rbp-D0h]
  __int64 v39; // [rsp+38h] [rbp-C8h]
  __int64 v40; // [rsp+40h] [rbp-C0h]
  __int64 v41; // [rsp+48h] [rbp-B8h]
  __int64 v42; // [rsp+50h] [rbp-B0h]
  __int64 v43; // [rsp+58h] [rbp-A8h]
  __int64 v44; // [rsp+60h] [rbp-A0h]
  __int64 v45; // [rsp+68h] [rbp-98h]
  void *v46; // [rsp+70h] [rbp-90h] BYREF
  bool v47; // [rsp+78h] [rbp-88h]
  signed int v48; // [rsp+7Ch] [rbp-84h]
  unsigned int *v49; // [rsp+80h] [rbp-80h]
  HSTRING_HEADER v50; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v51; // [rsp+A0h] [rbp-60h] BYREF
  void **v52; // [rsp+A8h] [rbp-58h] BYREF
  void **v53; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-48h] BYREF
  void *lpMem[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-30h]
  HSTRING_HEADER hstringHeader; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING string; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t sourceString[40]; // [rsp+100h] [rbp+0h] BYREF

  v3 = this;
  v49 = (unsigned int *)this;
  lpMem[1] = 0;
  v56 = 0;
  lpMem[0] = &CSusArray<void *,CHandleItemOp>::`vftable';
  v46 = 0;
  LODWORD(v53) = 0;
  v4 = 0;
  UserTokens = AppxDownloadUtils::GetUserTokens((AppxDownloadUtils *)&v46, &v53, a3);
  if ( UserTokens >= 0 )
  {
    v7 = (unsigned int)v53;
    if ( !(_DWORD)v53 )
    {
      UserTokens = -2145124328;
      goto LABEL_66;
    }
    v8 = v46;
    if ( v46 )
    {
      CSusArrayList<void *,CHandleItemOp>::RemoveArraySection(lpMem, v5, 0);
      SusFree(lpMem[1]);
      lpMem[1] = v8;
      HIDWORD(v56) = v7;
      LODWORD(v56) = v7;
    }
    v9 = 0;
    if ( v7 )
    {
      while ( 1 )
      {
        UserTokens = 0;
        v10 = ImpersonateLoggedOnUser(*((HANDLE *)v8 + v9));
        v11 = v10;
        v47 = v10;
        if ( !v10 )
        {
          LastError = GetLastError();
          UserTokens = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            UserTokens = LastError;
          if ( UserTokens >= 0 )
            UserTokens = -2147418113;
        }
        v48 = UserTokens;
        v53 = 0;
        v54 = 0;
        if ( UserTokens < 0 )
        {
          v31 = !v10;
          goto LABEL_61;
        }
        memset(&hstringHeader, 0, sizeof(hstringHeader));
        string = 0;
        v13 = WindowsCreateStringReference(
                L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager",
                0x47u,
                &hstringHeader,
                &string);
        if ( v13 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
LABEL_68:
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
          __debugbreak();
        }
        v16 = string;
        v17 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*((void (__fastcall **)(void **))*v17 + 2))(v17);
        }
        v53 = 0;
        v52 = 0;
        UserTokens = RoActivateInstance(v16, &v52);
        if ( UserTokens >= 0 )
        {
          if ( *(_QWORD *)&GUID_9353e170_8441_4b45_bd72_7c2fa925beee.Data1 == *(_QWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
            && *(_QWORD *)GUID_9353e170_8441_4b45_bd72_7c2fa925beee.Data4 == *(_QWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
          {
            v18 = v52;
            v53 = v52;
            goto LABEL_22;
          }
          UserTokens = (*(__int64 (__fastcall **)(void **, GUID *, void ***))*v52)(
                         v52,
                         &GUID_9353e170_8441_4b45_bd72_7c2fa925beee,
                         &v53);
          (*((void (__fastcall **)(void **))*v52 + 2))(v52);
        }
        v18 = v53;
LABEL_22:
        if ( UserTokens < 0 )
        {
          string = 0;
          v34 = v54;
          if ( v54 )
          {
            v54 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            v18 = v53;
          }
          if ( v18 )
          {
            v53 = 0;
            (*((void (__fastcall **)(void **))*v18 + 2))(v18);
          }
LABEL_49:
          v31 = !v11;
LABEL_61:
          if ( !v31 && !RevertToSelf() )
            GetLastError();
          goto LABEL_64;
        }
        v19 = *(__int64 (__fastcall **)(void **, GUID *, __int64 *))*v18;
        v20 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        UserTokens = v19(v18, &GUID_8ae50234_8fd5_4743_9f5a_d6bb44f24f29, &v54);
        if ( UserTokens < 0 )
        {
          string = 0;
          v32 = v54;
          if ( v54 )
          {
            v54 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          }
          v33 = v53;
          if ( v53 )
          {
            v53 = 0;
            (*((void (__fastcall **)(void **))*v33 + 2))(v33);
          }
          goto LABEL_49;
        }
        LODWORD(v45) = *((unsigned __int8 *)v3 + 15);
        LODWORD(v44) = *((unsigned __int8 *)v3 + 14);
        LODWORD(v43) = *((unsigned __int8 *)v3 + 13);
        LODWORD(v42) = *((unsigned __int8 *)v3 + 12);
        LODWORD(v41) = *((unsigned __int8 *)v3 + 11);
        LODWORD(v40) = *((unsigned __int8 *)v3 + 10);
        LODWORD(v39) = *((unsigned __int8 *)v3 + 9);
        LODWORD(v38) = *((unsigned __int8 *)v3 + 8);
        LODWORD(v37) = *((unsigned __int16 *)v3 + 3);
        LODWORD(v36) = *((unsigned __int16 *)v3 + 2);
        v3 = (AppxDownloadUtils *)v49;
        UserTokens = StringCchPrintfW(
                       sourceString,
                       0x27u,
                       L"%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X",
                       *v49,
                       v36,
                       v37,
                       v38,
                       v39,
                       v40,
                       v41,
                       v42,
                       v43,
                       v44,
                       v45);
        if ( UserTokens < 0 )
        {
          string = 0;
          v29 = v54;
          if ( v54 )
          {
            v54 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          }
          v30 = v53;
          if ( v53 )
          {
            v53 = 0;
            (*((void (__fastcall **)(void **))*v30 + 2))(v30);
          }
          goto LABEL_49;
        }
        v21 = v54;
        v22 = *(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v54 + 72LL);
        v23 = -1;
        do
          ++v23;
        while ( sourceString[v23] );
        if ( v23 > 0xFFFFFFFF )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v23, 0);
          JUMPOUT(0x18021DC58LL);
        }
        if ( (int)v23 + 1 < (unsigned int)v23 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v23, 0);
          __debugbreak();
        }
        v24 = WindowsCreateStringReference(sourceString, v23, &v50, &v51);
        if ( v24 < 0 )
          goto LABEL_68;
        UserTokens = v22(v21, v51);
        if ( UserTokens >= 0 )
          v4 = 1;
        string = 0;
        v27 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v28 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*((void (__fastcall **)(void **))*v28 + 2))(v28);
        }
        if ( v11 )
        {
          if ( RevertToSelf() )
            v47 = 0;
          else
            GetLastError();
        }
        ++v9;
        v8 = v46;
        if ( v9 >= v7 )
        {
          if ( UserTokens >= 0 )
            break;
LABEL_64:
          if ( v4 )
            UserTokens = 0;
          break;
        }
      }
    }
  }
LABEL_66:
  CSusArrayList<void *,CHandleItemOp>::~CSusArrayList<void *,CHandleItemOp>(lpMem, v5, 0);
  return (unsigned int)UserTokens;
}

```

## disassembly

```asm
0x18021d770  mov     [rsp-8+arg_8], rbx
0x18021d775  mov     [rsp-8+arg_10], rsi
0x18021d77a  mov     [rsp-8+arg_18], rdi
0x18021d77f  push    rbp
0x18021d780  push    r12
0x18021d782  push    r13
0x18021d784  push    r14
0x18021d786  push    r15
0x18021d788  lea     rbp, [rsp-60h]
0x18021d78d  sub     rsp, 160h
0x18021d794  mov     rax, cs:__security_cookie
0x18021d79b  xor     rax, rsp
0x18021d79e  mov     [rbp+80h+var_30], rax
0x18021d7a2  mov     rsi, rcx
0x18021d7a5  mov     [rbp+80h+var_100], rcx
0x18021d7a9  xorps   xmm0, xmm0
0x18021d7ac  movups  xmmword ptr [rbp+80h+lpMem], xmm0
0x18021d7b0  xor     ecx, ecx
0x18021d7b2  mov     [rbp+80h+lpMem+8], rcx
0x18021d7b6  mov     [rbp+80h+var_B0], rcx
0x18021d7ba  lea     rax, ??_7?$CSusArray@PEAXVCHandleItemOp@@@@6B@; const CSusArray<void *,CHandleItemOp>::`vftable'
0x18021d7c1  mov     [rbp+80h+lpMem], rax
0x18021d7c5  mov     [rsp+180h+var_110], rcx
0x18021d7ca  mov     dword ptr [rbp+80h+var_D0], ecx
0x18021d7cd  mov     r13b, cl
0x18021d7d0  lea     rdx, [rbp+80h+var_D0]; void ***
0x18021d7d4  lea     rcx, [rsp+180h+var_110]; this
0x18021d7d9  call    ?GetUserTokens@AppxDownloadUtils@@YAJPEAPEAPEAXPEAK@Z; AppxDownloadUtils::GetUserTokens(void * * *,ulong *)
0x18021d7de  mov     ebx, eax
0x18021d7e0  xor     r8d, r8d
0x18021d7e3  test    eax, eax
0x18021d7e5  js      loc_18021DBFB
0x18021d7eb  mov     r14d, dword ptr [rbp+80h+var_D0]
0x18021d7ef  test    r14d, r14d
0x18021d7f2  jnz     short loc_18021D7FE
0x18021d7f4  mov     ebx, 80240018h
0x18021d7f9  jmp     loc_18021DBFB
0x18021d7fe  mov     rdi, [rsp+180h+var_110]
0x18021d803  test    rdi, rdi
0x18021d806  jz      short loc_18021D829
0x18021d808  lea     rcx, [rbp+80h+lpMem]
0x18021d80c  call    ?RemoveArraySection@?$CSusArrayList@PEAXVCHandleItemOp@@@@IEAAXKKH@Z; CSusArrayList<void *,CHandleItemOp>::RemoveArraySection(ulong,ulong,int)
0x18021d811  mov     rcx, [rbp+80h+lpMem+8]; lpMem
0x18021d815  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18021d81a  mov     [rbp+80h+lpMem+8], rdi
0x18021d81e  mov     dword ptr [rbp+80h+var_B0+4], r14d
0x18021d822  mov     dword ptr [rbp+80h+var_B0], r14d
0x18021d826  xor     r8d, r8d
0x18021d829  mov     r12d, r8d
0x18021d82c  test    r14d, r14d
0x18021d82f  jz      loc_18021DBFB
0x18021d835  mov     ebx, r8d
0x18021d838  mov     ecx, r12d
0x18021d83b  mov     rcx, [rdi+rcx*8]; hToken
0x18021d83f  call    cs:__imp_ImpersonateLoggedOnUser
0x18021d845  mov     edi, eax
0x18021d847  xor     r8d, r8d
0x18021d84a  test    eax, eax
0x18021d84c  setnz   r15b
0x18021d850  mov     [rsp+180h+var_108], r15b
0x18021d855  test    eax, eax
0x18021d857  jnz     short loc_18021D87A
0x18021d859  call    cs:__imp_GetLastError
0x18021d85f  movzx   ebx, ax
0x18021d862  or      ebx, 80070000h
0x18021d868  xor     r8d, r8d
0x18021d86b  test    eax, eax
0x18021d86d  cmovle  ebx, eax
0x18021d870  mov     eax, 8000FFFFh
0x18021d875  test    ebx, ebx
0x18021d877  cmovns  ebx, eax
0x18021d87a  mov     [rsp+180h+var_104], ebx
0x18021d87e  mov     [rbp+80h+var_D0], r8
0x18021d882  mov     [rbp+80h+var_C8], r8
0x18021d886  test    ebx, ebx
0x18021d888  js      loc_18021DBDA
0x18021d88e  xorps   xmm0, xmm0
0x18021d891  movups  xmmword ptr [rbp+80h+hstringHeader.Reserved], xmm0
0x18021d895  movups  xmmword ptr [rbp+80h+hstringHeader.Reserved+10h], xmm0
0x18021d899  mov     [rbp+80h+string], r8
0x18021d89d  lea     r9, [rbp+80h+string]; string
0x18021d8a1  lea     r8, [rbp+80h+hstringHeader]; hstringHeader
0x18021d8a5  mov     edx, 47h ; 'G'; length
0x18021d8aa  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QB_WB; "Windows.ApplicationModel.Store.Preview."...
0x18021d8b1  call    cs:__imp_WindowsCreateStringReference
0x18021d8b7  xor     edi, edi
0x18021d8b9  test    eax, eax
0x18021d8bb  js      loc_18021DC33
0x18021d8c1  mov     rbx, [rbp+80h+string]
0x18021d8c5  mov     rcx, [rbp+80h+var_D0]
0x18021d8c9  test    rcx, rcx
0x18021d8cc  jz      short loc_18021D8DF
0x18021d8ce  mov     [rbp+80h+var_D0], rdi
0x18021d8d2  mov     rax, [rcx]
0x18021d8d5  mov     rax, [rax+10h]
0x18021d8d9  call    _guard_dispatch_icall
0x18021d8de  nop
0x18021d8df  mov     [rbp+80h+var_D0], rdi
0x18021d8e3  mov     [rbp+80h+var_D8], rdi
0x18021d8e7  lea     rdx, [rbp+80h+var_D8]
0x18021d8eb  mov     rcx, rbx
0x18021d8ee  call    cs:__imp_RoActivateInstance
0x18021d8f4  mov     ebx, eax
0x18021d8f6  xor     r8d, r8d
0x18021d8f9  test    eax, eax
0x18021d8fb  js      short loc_18021D956
0x18021d8fd  mov     rax, qword ptr cs:_GUID_9353e170_8441_4b45_bd72_7c2fa925beee.Data1
0x18021d904  cmp     rax, qword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18021d90b  jnz     short loc_18021D927
0x18021d90d  mov     rax, qword ptr cs:_GUID_9353e170_8441_4b45_bd72_7c2fa925beee.Data4
0x18021d914  cmp     rax, qword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18021d91b  jnz     short loc_18021D927
0x18021d91d  mov     rdi, [rbp+80h+var_D8]
0x18021d921  mov     [rbp+80h+var_D0], rdi
0x18021d925  jmp     short loc_18021D95A
0x18021d927  mov     rcx, [rbp+80h+var_D8]
0x18021d92b  mov     rax, [rcx]
0x18021d92e  lea     r8, [rbp+80h+var_D0]
0x18021d932  lea     rdx, _GUID_9353e170_8441_4b45_bd72_7c2fa925beee
0x18021d939  mov     rax, [rax]
0x18021d93c  call    _guard_dispatch_icall
0x18021d941  mov     ebx, eax
0x18021d943  mov     rcx, [rbp+80h+var_D8]
0x18021d947  mov     rax, [rcx]
0x18021d94a  mov     rax, [rax+10h]
0x18021d94e  call    _guard_dispatch_icall
0x18021d953  xor     r8d, r8d
0x18021d956  mov     rdi, [rbp+80h+var_D0]
0x18021d95a  test    ebx, ebx
0x18021d95c  js      loc_18021DB96
0x18021d962  mov     rax, [rdi]
0x18021d965  mov     rbx, [rax]
0x18021d968  mov     rcx, [rbp+80h+var_C8]
0x18021d96c  test    rcx, rcx
0x18021d96f  jz      short loc_18021D982
0x18021d971  mov     [rbp+80h+var_C8], r8
0x18021d975  mov     rdx, [rcx]
0x18021d978  mov     rax, [rdx+10h]
0x18021d97c  call    _guard_dispatch_icall
0x18021d981  nop
0x18021d982  lea     r8, [rbp+80h+var_C8]
0x18021d986  lea     rdx, _GUID_8ae50234_8fd5_4743_9f5a_d6bb44f24f29
0x18021d98d  mov     rcx, rdi
0x18021d990  mov     rax, rbx
0x18021d993  call    _guard_dispatch_icall
0x18021d998  mov     ebx, eax
0x18021d99a  xor     r8d, r8d
0x18021d99d  test    eax, eax
0x18021d99f  js      loc_18021DB58
0x18021d9a5  movzx   eax, byte ptr [rsi+0Fh]
0x18021d9a9  movzx   ecx, byte ptr [rsi+0Eh]
0x18021d9ad  movzx   edx, byte ptr [rsi+0Dh]
0x18021d9b1  movzx   r8d, byte ptr [rsi+0Ch]
0x18021d9b6  movzx   r9d, byte ptr [rsi+0Bh]
0x18021d9bb  movzx   r10d, byte ptr [rsi+0Ah]
0x18021d9c0  movzx   r11d, byte ptr [rsi+9]
0x18021d9c5  movzx   ebx, byte ptr [rsi+8]
0x18021d9c9  movzx   edi, word ptr [rsi+6]
0x18021d9cd  movzx   esi, word ptr [rsi+4]
0x18021d9d1  mov     dword ptr [rsp+180h+var_118], eax
0x18021d9d5  mov     dword ptr [rsp+180h+var_120], ecx
0x18021d9d9  mov     dword ptr [rsp+180h+var_128], edx
0x18021d9dd  mov     dword ptr [rsp+180h+var_130], r8d
0x18021d9e2  mov     dword ptr [rsp+180h+var_138], r9d
0x18021d9e7  mov     dword ptr [rsp+180h+var_140], r10d
0x18021d9ec  mov     dword ptr [rsp+180h+var_148], r11d
0x18021d9f1  mov     dword ptr [rsp+180h+var_150], ebx
0x18021d9f5  mov     dword ptr [rsp+180h+var_158], edi
0x18021d9f9  mov     dword ptr [rsp+180h+var_160], esi
0x18021d9fd  mov     rsi, [rbp+80h+var_100]
0x18021da01  mov     r9d, [rsi]
0x18021da04  lea     r8, a08x04x04x02x02; "%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02"...
0x18021da0b  mov     edx, 27h ; '''; unsigned __int64
0x18021da10  lea     rcx, [rbp+80h+sourceString]; Buffer
0x18021da14  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18021da19  mov     ebx, eax
0x18021da1b  xor     r8d, r8d; unsigned int
0x18021da1e  test    eax, eax
0x18021da20  js      loc_18021DB14
0x18021da26  mov     rbx, [rbp+80h+var_C8]
0x18021da2a  mov     rax, [rbx]
0x18021da2d  mov     rdi, [rax+48h]
0x18021da31  lea     rax, [rbp+80h+sourceString]
0x18021da35  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18021da39  inc     rdx; int
0x18021da3c  cmp     [rax+rdx*2], r8w
0x18021da41  jnz     short loc_18021DA39
0x18021da43  mov     eax, 0FFFFFFFFh
0x18021da48  cmp     rdx, rax
0x18021da4b  ja      loc_18021DC4E
0x18021da51  lea     eax, [rdx+1]
0x18021da54  cmp     eax, edx
0x18021da56  jb      loc_18021DC43
0x18021da5c  lea     r9, [rbp+80h+var_E0]; string
0x18021da60  lea     r8, [rbp+80h+var_F8]; hstringHeader
0x18021da64  lea     rcx, [rbp+80h+sourceString]; sourceString
0x18021da68  call    cs:__imp_WindowsCreateStringReference
0x18021da6e  test    eax, eax
0x18021da70  js      loc_18021DC3B
0x18021da76  mov     rdx, [rbp+80h+var_E0]
0x18021da7a  mov     rcx, rbx
0x18021da7d  mov     rax, rdi
0x18021da80  call    _guard_dispatch_icall
0x18021da85  mov     ebx, eax
0x18021da87  movzx   r13d, r13b
0x18021da8b  xor     r8d, r8d
0x18021da8e  test    eax, eax
0x18021da90  lea     edi, [r8+1]
0x18021da94  cmovns  r13d, edi
0x18021da98  mov     [rbp+80h+string], r8
0x18021da9c  mov     rcx, [rbp+80h+var_C8]
0x18021daa0  test    rcx, rcx
0x18021daa3  jz      short loc_18021DAB8
0x18021daa5  mov     [rbp+80h+var_C8], r8
0x18021daa9  mov     rax, [rcx]
0x18021daac  mov     rax, [rax+10h]
0x18021dab0  call    _guard_dispatch_icall
0x18021dab5  xor     r8d, r8d
0x18021dab8  mov     rcx, [rbp+80h+var_D0]
0x18021dabc  test    rcx, rcx
0x18021dabf  jz      short loc_18021DAD4
0x18021dac1  mov     [rbp+80h+var_D0], r8
0x18021dac5  mov     rax, [rcx]
0x18021dac8  mov     rax, [rax+10h]
0x18021dacc  call    _guard_dispatch_icall
0x18021dad1  xor     r8d, r8d
0x18021dad4  test    r15b, r15b
0x18021dad7  jz      short loc_18021DAF6
0x18021dad9  call    cs:__imp_RevertToSelf
0x18021dadf  xor     r8d, r8d
0x18021dae2  test    eax, eax
0x18021dae4  jnz     short loc_18021DAF1
0x18021dae6  call    cs:__imp_GetLastError
0x18021daec  xor     r8d, r8d
0x18021daef  jmp     short loc_18021DAF6
0x18021daf1  mov     [rsp+180h+var_108], r8b
0x18021daf6  add     r12d, edi
0x18021daf9  cmp     r12d, r14d
0x18021dafc  mov     rdi, [rsp+180h+var_110]
0x18021db01  jb      loc_18021D835
0x18021db07  test    ebx, ebx
0x18021db09  jns     loc_18021DBFB
0x18021db0f  jmp     loc_18021DBF4
0x18021db14  mov     [rbp+80h+string], r8
0x18021db18  mov     rcx, [rbp+80h+var_C8]
0x18021db1c  test    rcx, rcx
0x18021db1f  jz      short loc_18021DB34
0x18021db21  mov     [rbp+80h+var_C8], r8
0x18021db25  mov     rax, [rcx]
0x18021db28  mov     rax, [rax+10h]
0x18021db2c  call    _guard_dispatch_icall
0x18021db31  xor     r8d, r8d
0x18021db34  mov     rcx, [rbp+80h+var_D0]
0x18021db38  test    rcx, rcx
0x18021db3b  jz      short loc_18021DB50
0x18021db3d  mov     [rbp+80h+var_D0], r8
0x18021db41  mov     rax, [rcx]
0x18021db44  mov     rax, [rax+10h]
0x18021db48  call    _guard_dispatch_icall
0x18021db4d  xor     r8d, r8d
0x18021db50  test    r15b, r15b
0x18021db53  jmp     loc_18021DBDC
0x18021db58  mov     [rbp+80h+string], r8
0x18021db5c  mov     rcx, [rbp+80h+var_C8]
0x18021db60  test    rcx, rcx
0x18021db63  jz      short loc_18021DB78
0x18021db65  mov     [rbp+80h+var_C8], r8
0x18021db69  mov     rax, [rcx]
0x18021db6c  mov     rax, [rax+10h]
0x18021db70  call    _guard_dispatch_icall
0x18021db75  xor     r8d, r8d
0x18021db78  mov     rcx, [rbp+80h+var_D0]
0x18021db7c  test    rcx, rcx
0x18021db7f  jz      short loc_18021DB94
0x18021db81  mov     [rbp+80h+var_D0], r8
0x18021db85  mov     rax, [rcx]
0x18021db88  mov     rax, [rax+10h]
0x18021db8c  call    _guard_dispatch_icall
0x18021db91  xor     r8d, r8d
0x18021db94  jmp     short loc_18021DB50
0x18021db96  mov     [rbp+80h+string], r8
0x18021db9a  mov     rcx, [rbp+80h+var_C8]
0x18021db9e  test    rcx, rcx
0x18021dba1  jz      short loc_18021DBBA
0x18021dba3  mov     [rbp+80h+var_C8], r8
0x18021dba7  mov     rax, [rcx]
0x18021dbaa  mov     rax, [rax+10h]
0x18021dbae  call    _guard_dispatch_icall
0x18021dbb3  mov     rdi, [rbp+80h+var_D0]
0x18021dbb7  xor     r8d, r8d
0x18021dbba  test    rdi, rdi
0x18021dbbd  jz      short loc_18021DBD5
0x18021dbbf  mov     [rbp+80h+var_D0], r8
0x18021dbc3  mov     rax, [rdi]
0x18021dbc6  mov     rcx, rdi
0x18021dbc9  mov     rax, [rax+10h]
0x18021dbcd  call    _guard_dispatch_icall
0x18021dbd2  xor     r8d, r8d
0x18021dbd5  jmp     loc_18021DB50
0x18021dbda  test    edi, edi
  ... truncated ...
```

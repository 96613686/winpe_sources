# OSDeploymentHelper::CDeploymentSessionWrapper::CreateDeploymentSessionFromLibrary(wchar_t const *,wchar_t const *,_GUID const &,ulong,tagOptionalSessionInfo6 &,void *,IDeploymentSession * *)

- ea: `0x18003c0fc`
- end: `0x18003c8ca`
- name: `?CreateDeploymentSessionFromLibrary@CDeploymentSessionWrapper@OSDeploymentHelper@@QEAAJPEB_W0AEBU_GUID@@KAEAUtagOptionalSessionInfo6@@PEAXPEAPEAUIDeploymentSession@@@Z`
- size: `1998`
- prototype: `__int64 __fastcall(OSDeploymentHelper::CDeploymentSessionWrapper *this, const wchar_t *, const wchar_t *, const struct _GUID *, unsigned int, struct tagOptionalSessionInfo6 *, void *, struct IDeploymentSession **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18003b800`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18003c0fc`
- `0x18003d0c8`
- `0x18003d148`
- `0x180041448`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c187`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c187`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c175`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c175`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c1f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c22b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c5e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c1f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c22b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c5e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c5f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c5f6`

## string_xrefs

- `0x18003c1ee`: `CreateDeploymentSessionEx`
- `0x18003c1b9`: `Failed to load the service stack dll file '%ws'`
- `0x18003c403`: `CreateDeploymentSessionEx: %ws with OptionalSessionInfo version 5.`
- `0x18003c5dd`: `CreateDeploymentSession`
- `0x18003c5b1`: `CreateDeploymentSessionEx`
- `0x18003c614`: `CreateDeploymentSession`
- `0x18003c79d`: `CreateDeploymentSession`
- `0x18003c886`: `CreateDeploymentSession`

## pseudocode

```c
__int64 __fastcall OSDeploymentHelper::CDeploymentSessionWrapper::CreateDeploymentSessionFromLibrary(
        OSDeploymentHelper::CDeploymentSessionWrapper *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const struct _GUID *a4,
        unsigned int a5,
        struct tagOptionalSessionInfo6 *a6,
        void *a7,
        struct IDeploymentSession **a8)
{
  signed int v11; // ebx
  __int64 v12; // rdx
  HMODULE Library; // rdi
  HMODULE v14; // rcx
  signed int LastError; // eax
  FARPROC v16; // rax
  int v17; // eax
  int *v18; // rax
  __int64 v19; // r8
  int v20; // ecx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  struct _GUID v24; // xmm0
  __int64 v25; // r9
  __int64 v26; // rdx
  unsigned int v27; // ecx
  int v28; // eax
  int *v29; // rax
  __int64 v30; // r8
  int v31; // ecx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rcx
  FARPROC ProcAddress; // r15
  signed int v36; // eax
  unsigned int v37; // ecx
  int v38; // eax
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  int *v41; // rax
  __int64 v42; // r9
  int v43; // edx
  __int64 v44; // rax
  __int64 v45; // r9
  __int64 v46; // rax
  struct IDeploymentSession *v47; // rax
  struct IDeploymentSession *v48; // rcx
  int v50; // [rsp+20h] [rbp-A1h]
  int v51; // [rsp+20h] [rbp-A1h]
  void *v52; // [rsp+20h] [rbp-A1h]
  int v53; // [rsp+20h] [rbp-A1h]
  int v54; // [rsp+20h] [rbp-A1h]
  struct SessionDataUtil::WUDeploymentSessionInfoWrapper *v55[2]; // [rsp+40h] [rbp-81h] BYREF
  struct _GUID v56; // [rsp+50h] [rbp-71h] BYREF
  struct _GUID v57; // [rsp+60h] [rbp-61h] BYREF
  struct IDeploymentSession **v58; // [rsp+70h] [rbp-51h]
  __int128 v59; // [rsp+78h] [rbp-49h] BYREF
  __int128 v60; // [rsp+88h] [rbp-39h]
  __int128 v61; // [rsp+98h] [rbp-29h]
  struct IDeploymentSession *v62; // [rsp+A8h] [rbp-19h] BYREF
  int v63; // [rsp+B0h] [rbp-11h] BYREF
  unsigned int v64; // [rsp+B4h] [rbp-Dh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  *(_QWORD *)&v56.Data1 = a4;
  v58 = a8;
  if ( !a8 )
  {
    v11 = -2147467261;
    v12 = 369;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
      (const char *)(unsigned int)v11,
      v50);
    return (unsigned int)v11;
  }
  Library = LoadLibraryExW(a2, 0, 0);
  v14 = (HMODULE)*((_QWORD *)this + 9);
  if ( v14 )
    FreeLibrary(v14);
  *((_QWORD *)this + 9) = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v11 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v11 = LastError;
    if ( v11 >= 0 )
      v11 = -2147418113;
    v50 = v11;
    WUTrace(0, 0, 4096, 1);
    v12 = 376;
    goto LABEL_3;
  }
  v62 = 0;
  *(_QWORD *)&v57.Data1 = GetProcAddress(Library, "CreateDeploymentSessionEx");
  if ( !*(_QWORD *)&v57.Data1 )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)this + 9), "CreateDeploymentSession");
    if ( !ProcAddress )
    {
      v36 = GetLastError();
      v11 = (unsigned __int16)v36 | 0x80070000;
      if ( v36 <= 0 )
        v11 = v36;
      if ( v11 >= 0 )
        v11 = -2147418113;
      WUTrace(0, 0, 4096, 1);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)v11,
        v11);
      goto LABEL_112;
    }
    v59 = 0;
    v60 = 0;
    v61 = 0;
    if ( a7 )
    {
      v59 = *(_OWORD *)a6;
      v60 = *((_OWORD *)a6 + 1);
      v61 = *((_OWORD *)a6 + 2);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
    {
      v57 = *a4;
      v11 = ((__int64 (__fastcall *)(__int64, const wchar_t *, struct _GUID *, __int128 *, struct IDeploymentSession **))ProcAddress)(
              1,
              a3,
              &v57,
              &v59,
              &v62);
      if ( v11 >= 0 )
        goto LABEL_105;
      v50 = v11;
      WUTrace(0, 0, 4096, 1);
      v26 = 566;
LABEL_111:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)v11,
        v50);
      goto LABEL_112;
    }
    v55[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
    v57 = *a4;
    v38 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(v37, a3, &v57, 5u, &v59, v55);
    v11 = v38;
    if ( v38 < 0 )
    {
      v39 = (unsigned int)v38;
      v40 = 540;
      goto LABEL_102;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    v41 = (int *)*((_QWORD *)v55[0] + 4);
    if ( v41 )
    {
      v42 = *((_QWORD *)v41 + 6);
      if ( v42 )
      {
        v43 = *v41;
        if ( *v41 == 1 )
        {
          v44 = *((_QWORD *)v41 + 1);
LABEL_87:
          v45 = *(_QWORD *)(v44 + 48);
LABEL_100:
          v57 = (struct _GUID)*((_OWORD *)v55[0] + 1);
          v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, struct _GUID *, __int64, struct IDeploymentSession **))ProcAddress)(
                  *(unsigned int *)v55[0],
                  *((_QWORD *)v55[0] + 1),
                  &v57,
                  v45,
                  &v62);
          if ( v11 >= 0 )
          {
            WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
            goto LABEL_105;
          }
          v54 = v11;
          WUTrace(0, 0, 4096, 1);
          v39 = (unsigned int)v11;
          v40 = 552;
LABEL_102:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v40,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
            (const char *)v39,
            v54);
          goto LABEL_103;
        }
        switch ( v43 )
        {
          case 2:
            v46 = *((_QWORD *)v41 + 2);
LABEL_90:
            v45 = *(_QWORD *)(v46 + 16);
            goto LABEL_100;
          case 3:
            v46 = *((_QWORD *)v41 + 3);
            goto LABEL_90;
          case 4:
            v46 = *((_QWORD *)v41 + 4);
            goto LABEL_90;
          case 5:
            v44 = *((_QWORD *)v41 + 5);
            goto LABEL_87;
          case 6:
            v45 = *(_QWORD *)(v42 + 16);
            goto LABEL_100;
        }
      }
    }
    v45 = 0;
    goto LABEL_100;
  }
  if ( a5 < 6 )
    goto LABEL_43;
  v16 = GetProcAddress(*((HMODULE *)this + 9), "GetSupportedSessionInitializationOptions");
  if ( !v16
    || (v63 = 0, v64 = 5, ((int (__fastcall *)(int *, unsigned int *))v16)(&v63, &v64) < 0)
    || (v63 & 1) == 0
    || v64 < 6 )
  {
    if ( (*((_BYTE *)a6 + 104) & 1) != 0 )
    {
      v11 = -2145116123;
      v26 = 457;
      goto LABEL_111;
    }
LABEL_43:
    WUTrace(0, 0, 4096, 4);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
    {
      v24 = *(struct _GUID *)*(_QWORD *)&v56.Data1;
      v52 = a7;
      v25 = 5;
      goto LABEL_67;
    }
    v55[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
    v56 = *(struct _GUID *)*(_QWORD *)&v56.Data1;
    v28 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(v27, a3, &v56, 5u, a7, v55);
    v11 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)v28,
        v53);
      goto LABEL_103;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    v29 = (int *)*((_QWORD *)v55[0] + 4);
    if ( v29 )
    {
      v30 = *((_QWORD *)v29 + 6);
      if ( v30 )
      {
        v31 = *v29;
        if ( *v29 == 1 )
        {
          v32 = *((_QWORD *)v29 + 1);
LABEL_52:
          v22 = *(_QWORD *)(v32 + 48);
          goto LABEL_65;
        }
        switch ( v31 )
        {
          case 2:
            v33 = *((_QWORD *)v29 + 2);
LABEL_55:
            v22 = *(_QWORD *)(v33 + 16);
            goto LABEL_65;
          case 3:
            v33 = *((_QWORD *)v29 + 3);
            goto LABEL_55;
          case 4:
            v33 = *((_QWORD *)v29 + 4);
            goto LABEL_55;
          case 5:
            v32 = *((_QWORD *)v29 + 5);
            goto LABEL_52;
          case 6:
            v22 = *(_QWORD *)(v30 + 16);
            goto LABEL_65;
        }
      }
    }
    v22 = 0;
    goto LABEL_65;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
  {
    v55[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
    v56 = *(struct _GUID *)*(_QWORD *)&v56.Data1;
    v17 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(
            (unsigned int)v55,
            a3,
            &v56,
            6u,
            (const void *)((unsigned __int64)a6 & -(__int64)(a7 != 0)),
            v55);
    v11 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A8,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)v17,
        v51);
LABEL_103:
      WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
      goto LABEL_112;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    v18 = (int *)*((_QWORD *)v55[0] + 4);
    if ( v18 )
    {
      v19 = *((_QWORD *)v18 + 6);
      if ( v19 )
      {
        v20 = *v18;
        if ( *v18 == 1 )
        {
          v21 = *((_QWORD *)v18 + 1);
LABEL_27:
          v22 = *(_QWORD *)(v21 + 48);
LABEL_65:
          v34 = *(unsigned int *)v55[0];
          v56 = (struct _GUID)*((_OWORD *)v55[0] + 1);
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _GUID *, _QWORD, __int64, struct IDeploymentSession **))&v57.Data1)(
                  v34,
                  *((_QWORD *)v55[0] + 1),
                  &v56,
                  (unsigned int)v34,
                  v22,
                  &v62);
          WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
          goto LABEL_68;
        }
        switch ( v20 )
        {
          case 2:
            v23 = *((_QWORD *)v18 + 2);
LABEL_30:
            v22 = *(_QWORD *)(v23 + 16);
            goto LABEL_65;
          case 3:
            v23 = *((_QWORD *)v18 + 3);
            goto LABEL_30;
          case 4:
            v23 = *((_QWORD *)v18 + 4);
            goto LABEL_30;
          case 5:
            v21 = *((_QWORD *)v18 + 5);
            goto LABEL_27;
          case 6:
            v22 = *(_QWORD *)(v19 + 16);
            goto LABEL_65;
        }
      }
    }
    v22 = 0;
    goto LABEL_65;
  }
  v24 = *(struct _GUID *)*(_QWORD *)&v56.Data1;
  v52 = (void *)((unsigned __int64)a6 & -(__int64)(a7 != 0));
  v25 = 6;
LABEL_67:
  v56 = v24;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct _GUID *, __int64, void *, struct IDeploymentSession **))&v57.Data1)(
          1,
          a3,
          &v56,
          v25,
          v52,
          &v62);
LABEL_68:
  if ( v11 >= 0 )
  {
LABEL_105:
    v47 = v62;
    v48 = 0;
    v62 = 0;
    *v58 = v47;
    v11 = 0;
    goto LABEL_106;
  }
  WUTrace(0, 0, 4096, 1);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
    (const char *)(unsigned int)v11,
    v11);
LABEL_112:
  v48 = v62;
LABEL_106:
  if ( v48 )
    (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v48 + 16LL))(v48);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003c0fc  push    rbp
0x18003c0fe  push    rbx
0x18003c0ff  push    rsi
0x18003c100  push    rdi
0x18003c101  push    r12
0x18003c103  push    r13
0x18003c105  push    r14
0x18003c107  push    r15
0x18003c109  lea     rbp, [rsp-7]
0x18003c10e  sub     rsp, 0C8h
0x18003c115  mov     rax, cs:__security_cookie
0x18003c11c  xor     rax, rsp
0x18003c11f  mov     [rbp+3Fh+var_48], rax
0x18003c123  mov     rsi, r9
0x18003c126  mov     qword ptr [rbp+3Fh+var_B0.Data1], r9
0x18003c12a  mov     r13, r8
0x18003c12d  mov     r14, rdx
0x18003c130  mov     r15, rcx
0x18003c133  mov     rbx, [rbp+3Fh+arg_28]
0x18003c137  mov     r12, [rbp+3Fh+arg_30]
0x18003c13b  mov     rax, [rbp+3Fh+arg_38]
0x18003c142  mov     [rbp+3Fh+var_90], rax
0x18003c146  test    rax, rax
0x18003c149  jnz     short loc_18003C16D
0x18003c14b  mov     ebx, 80004003h
0x18003c150  mov     edx, 171h; void *
0x18003c155  lea     r8, aCW1SSrcClientE_19; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003c15c  mov     r9d, ebx; char *
0x18003c15f  mov     rcx, [rbp+47h]; this
0x18003c163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c168  jmp     loc_18003C816
0x18003c16d  xor     r8d, r8d; dwFlags
0x18003c170  xor     edx, edx; hFile
0x18003c172  mov     rcx, r14; lpLibFileName
0x18003c175  call    cs:__imp_LoadLibraryExW
0x18003c17b  mov     rdi, rax
0x18003c17e  mov     rcx, [r15+48h]; hLibModule
0x18003c182  test    rcx, rcx
0x18003c185  jz      short loc_18003C18D
0x18003c187  call    cs:__imp_FreeLibrary
0x18003c18d  mov     [r15+48h], rdi
0x18003c191  test    rdi, rdi
0x18003c194  jnz     short loc_18003C1E6
0x18003c196  call    cs:__imp_GetLastError
0x18003c19c  movzx   ebx, ax
0x18003c19f  or      ebx, 80070000h
0x18003c1a5  test    eax, eax
0x18003c1a7  cmovle  ebx, eax
0x18003c1aa  mov     eax, 8000FFFFh
0x18003c1af  test    ebx, ebx
0x18003c1b1  cmovns  ebx, eax
0x18003c1b4  mov     [rsp+100h+var_D0], r14
0x18003c1b9  lea     rax, aFailedToLoadTh; "Failed to load the service stack dll fi"...
0x18003c1c0  mov     [rsp+100h+var_D8], rax
0x18003c1c5  mov     dword ptr [rsp+100h+var_E0], ebx
0x18003c1c9  xor     edx, edx
0x18003c1cb  xor     ecx, ecx
0x18003c1cd  lea     r9d, [rdi+1]
0x18003c1d1  mov     r8d, 1000h
0x18003c1d7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003c1dc  mov     edx, 178h
0x18003c1e1  jmp     loc_18003C155
0x18003c1e6  mov     [rbp+3Fh+var_58], 0
0x18003c1ee  lea     rdx, aCreatedeployme_0; "CreateDeploymentSessionEx"
0x18003c1f5  mov     rcx, rdi; hModule
0x18003c1f8  call    cs:__imp_GetProcAddress
0x18003c1fe  mov     qword ptr [rbp+3Fh+var_A0.Data1], rax
0x18003c202  test    rax, rax
0x18003c205  jz      loc_18003C5DD
0x18003c20b  mov     edi, 1
0x18003c210  lea     esi, [rdi+5]
0x18003c213  lea     r14d, [rdi+4]
0x18003c217  cmp     [rbp+3Fh+arg_20], esi
0x18003c21a  jb      loc_18003C3F7
0x18003c220  lea     rdx, aGetsupportedse; "GetSupportedSessionInitializationOption"...
0x18003c227  mov     rcx, [r15+48h]; hModule
0x18003c22b  call    cs:__imp_GetProcAddress
0x18003c231  test    rax, rax
0x18003c234  jz      loc_18003C3E2
0x18003c23a  mov     [rbp+3Fh+var_50], 0
0x18003c241  mov     [rbp+3Fh+var_4C], r14d
0x18003c245  lea     rdx, [rbp+3Fh+var_4C]
0x18003c249  lea     rcx, [rbp+3Fh+var_50]
0x18003c24d  call    _guard_dispatch_icall
0x18003c252  test    eax, eax
0x18003c254  js      loc_18003C3E2
0x18003c25a  test    byte ptr [rbp+3Fh+var_50], dil
0x18003c25e  jz      loc_18003C3E2
0x18003c264  cmp     [rbp+3Fh+var_4C], esi
0x18003c267  jb      loc_18003C3E2
0x18003c26d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl(void)'::`2'::impl
0x18003c274  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(void)
0x18003c279  test    al, al
0x18003c27b  jz      loc_18003C39F
0x18003c281  mov     [rsp+100h+var_C0], 0
0x18003c28a  lea     rcx, [rsp+100h+var_C0]
0x18003c28f  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x18003c294  mov     rax, qword ptr [rbp+3Fh+var_B0.Data1]
0x18003c298  movaps  xmm0, xmmword ptr [rax]
0x18003c29b  movdqa  xmmword ptr [rbp+3Fh+var_B0.Data1], xmm0
0x18003c2a0  neg     r12
0x18003c2a3  sbb     rax, rax
0x18003c2a6  and     rax, rbx
0x18003c2a9  lea     rcx, [rsp+100h+var_C0]; unsigned int
0x18003c2ae  mov     [rsp+100h+var_D8], rcx; struct SessionDataUtil::WUDeploymentSessionInfoWrapper **
0x18003c2b3  mov     [rsp+100h+var_E0], rax; int
0x18003c2b8  mov     r9d, esi; unsigned int
0x18003c2bb  lea     r8, [rbp+3Fh+var_B0]; struct _GUID
0x18003c2bf  mov     rdx, r13; wchar_t *
0x18003c2c2  call    ?CreateInstance@WUDeploymentSessionInfoWrapper@SessionDataUtil@@SAJKPEB_WU_GUID@@KPEBXPEAPEAV12@@Z; SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(ulong,wchar_t const *,_GUID,ulong,void const *,SessionDataUtil::WUDeploymentSessionInfoWrapper * *)
0x18003c2c7  mov     ebx, eax
0x18003c2c9  test    eax, eax
0x18003c2cb  jns     short loc_18003C2EB
0x18003c2cd  mov     rcx, [rbp+47h]; this
0x18003c2d1  mov     r9d, eax; char *
0x18003c2d4  lea     r8, aCW1SSrcClientE_19; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003c2db  mov     edx, 1A8h; void *
0x18003c2e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c2e5  nop
0x18003c2e6  jmp     loc_18003C7D8
0x18003c2eb  mov     rcx, [rbp+3Fh+var_58]
0x18003c2ef  test    rcx, rcx
0x18003c2f2  jz      short loc_18003C308
0x18003c2f4  mov     rax, [rcx]
0x18003c2f7  mov     rax, [rax+10h]
0x18003c2fb  call    _guard_dispatch_icall
0x18003c300  mov     [rbp+3Fh+var_58], 0
0x18003c308  mov     rdx, [rsp+100h+var_C0]
0x18003c30d  mov     rax, [rdx+20h]
0x18003c311  test    rax, rax
0x18003c314  jz      short loc_18003C369
0x18003c316  mov     r8, [rax+30h]
0x18003c31a  test    r8, r8
0x18003c31d  jz      short loc_18003C369
0x18003c31f  mov     ecx, [rax]
0x18003c321  cmp     ecx, edi
0x18003c323  jnz     short loc_18003C32F
0x18003c325  mov     rax, [rax+8]
0x18003c329  mov     rax, [rax+30h]
0x18003c32d  jmp     short loc_18003C36B
0x18003c32f  cmp     ecx, 2
0x18003c332  jnz     short loc_18003C33E
0x18003c334  mov     rax, [rax+10h]
0x18003c338  mov     rax, [rax+10h]
0x18003c33c  jmp     short loc_18003C36B
0x18003c33e  cmp     ecx, 3
0x18003c341  jnz     short loc_18003C349
0x18003c343  mov     rax, [rax+18h]
0x18003c347  jmp     short loc_18003C338
0x18003c349  cmp     ecx, 4
0x18003c34c  jnz     short loc_18003C354
0x18003c34e  mov     rax, [rax+20h]
0x18003c352  jmp     short loc_18003C338
0x18003c354  cmp     ecx, r14d
0x18003c357  jnz     short loc_18003C35F
0x18003c359  mov     rax, [rax+28h]
0x18003c35d  jmp     short loc_18003C329
0x18003c35f  cmp     ecx, esi
0x18003c361  jnz     short loc_18003C369
0x18003c363  mov     rax, [r8+10h]
0x18003c367  jmp     short loc_18003C36B
0x18003c369  xor     eax, eax
0x18003c36b  mov     ecx, [rdx]
0x18003c36d  movups  xmm0, xmmword ptr [rdx+10h]
0x18003c371  movdqu  xmmword ptr [rbp+3Fh+var_B0.Data1], xmm0
0x18003c376  lea     r8, [rbp+3Fh+var_58]
0x18003c37a  mov     [rsp+100h+var_D8], r8
0x18003c37f  mov     [rsp+100h+var_E0], rax
0x18003c384  mov     r9d, ecx
0x18003c387  lea     r8, [rbp+3Fh+var_B0]
0x18003c38b  mov     rdx, [rdx+8]
0x18003c38f  mov     rax, qword ptr [rbp+3Fh+var_A0.Data1]
0x18003c393  call    _guard_dispatch_icall
0x18003c398  mov     ebx, eax
0x18003c39a  jmp     loc_18003C54F
0x18003c39f  mov     rcx, [rbp+3Fh+var_58]
0x18003c3a3  test    rcx, rcx
0x18003c3a6  jz      short loc_18003C3BC
0x18003c3a8  mov     rax, [rcx]
0x18003c3ab  mov     rax, [rax+10h]
0x18003c3af  call    _guard_dispatch_icall
0x18003c3b4  mov     [rbp+3Fh+var_58], 0
0x18003c3bc  mov     rax, qword ptr [rbp+3Fh+var_B0.Data1]
0x18003c3c0  movaps  xmm0, xmmword ptr [rax]
0x18003c3c3  neg     r12
0x18003c3c6  sbb     rax, rax
0x18003c3c9  and     rax, rbx
0x18003c3cc  lea     rcx, [rbp+3Fh+var_58]
0x18003c3d0  mov     [rsp+100h+var_D8], rcx
0x18003c3d5  mov     [rsp+100h+var_E0], rax
0x18003c3da  mov     r9d, esi
0x18003c3dd  jmp     loc_18003C590
0x18003c3e2  test    [rbx+68h], dil
0x18003c3e6  jz      short loc_18003C3F7
0x18003c3e8  mov     ebx, 80242025h
0x18003c3ed  mov     edx, 1C9h
0x18003c3f2  jmp     loc_18003C8AD
0x18003c3f7  lea     rax, aFallbacking; "Fallbacking"
0x18003c3fe  mov     [rsp+100h+var_D0], rax
0x18003c403  lea     rax, aCreatedeployme; "CreateDeploymentSessionEx: %ws with Opt"...
0x18003c40a  mov     [rsp+100h+var_D8], rax
0x18003c40f  mov     [rsp+100h+var_E0], 0
0x18003c418  xor     edx, edx
0x18003c41a  xor     ecx, ecx
0x18003c41c  lea     r9d, [rdx+4]
0x18003c420  mov     r8d, 1000h
0x18003c426  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003c42b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl(void)'::`2'::impl
0x18003c432  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(void)
0x18003c437  test    al, al
0x18003c439  jz      loc_18003C55B
0x18003c43f  mov     [rsp+100h+var_C0], 0
0x18003c448  lea     rcx, [rsp+100h+var_C0]
0x18003c44d  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x18003c452  mov     rax, qword ptr [rbp+3Fh+var_B0.Data1]
0x18003c456  movaps  xmm0, xmmword ptr [rax]
0x18003c459  movdqa  xmmword ptr [rbp+3Fh+var_B0.Data1], xmm0
0x18003c45e  lea     rax, [rsp+100h+var_C0]
0x18003c463  mov     [rsp+100h+var_D8], rax; struct SessionDataUtil::WUDeploymentSessionInfoWrapper **
0x18003c468  mov     [rsp+100h+var_E0], r12; int
0x18003c46d  mov     r9d, r14d; unsigned int
0x18003c470  lea     r8, [rbp+3Fh+var_B0]; struct _GUID
0x18003c474  mov     rdx, r13; wchar_t *
0x18003c477  call    ?CreateInstance@WUDeploymentSessionInfoWrapper@SessionDataUtil@@SAJKPEB_WU_GUID@@KPEBXPEAPEAV12@@Z; SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(ulong,wchar_t const *,_GUID,ulong,void const *,SessionDataUtil::WUDeploymentSessionInfoWrapper * *)
0x18003c47c  mov     ebx, eax
0x18003c47e  test    eax, eax
0x18003c480  jns     short loc_18003C4A0
0x18003c482  mov     rcx, [rbp+47h]; this
0x18003c486  mov     r9d, eax; char *
0x18003c489  lea     r8, aCW1SSrcClientE_19; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003c490  mov     edx, 1DEh; void *
0x18003c495  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c49a  nop
0x18003c49b  jmp     loc_18003C7D8
0x18003c4a0  mov     rcx, [rbp+3Fh+var_58]
0x18003c4a4  test    rcx, rcx
0x18003c4a7  jz      short loc_18003C4BD
0x18003c4a9  mov     rax, [rcx]
0x18003c4ac  mov     rax, [rax+10h]
0x18003c4b0  call    _guard_dispatch_icall
0x18003c4b5  mov     [rbp+3Fh+var_58], 0
0x18003c4bd  mov     rdx, [rsp+100h+var_C0]
0x18003c4c2  mov     rax, [rdx+20h]
0x18003c4c6  test    rax, rax
0x18003c4c9  jz      short loc_18003C51E
0x18003c4cb  mov     r8, [rax+30h]
0x18003c4cf  test    r8, r8
0x18003c4d2  jz      short loc_18003C51E
0x18003c4d4  mov     ecx, [rax]
0x18003c4d6  cmp     ecx, edi
0x18003c4d8  jnz     short loc_18003C4E4
0x18003c4da  mov     rax, [rax+8]
0x18003c4de  mov     rax, [rax+30h]
0x18003c4e2  jmp     short loc_18003C520
0x18003c4e4  cmp     ecx, 2
0x18003c4e7  jnz     short loc_18003C4F3
0x18003c4e9  mov     rax, [rax+10h]
0x18003c4ed  mov     rax, [rax+10h]
0x18003c4f1  jmp     short loc_18003C520
0x18003c4f3  cmp     ecx, 3
0x18003c4f6  jnz     short loc_18003C4FE
0x18003c4f8  mov     rax, [rax+18h]
0x18003c4fc  jmp     short loc_18003C4ED
0x18003c4fe  cmp     ecx, 4
0x18003c501  jnz     short loc_18003C509
0x18003c503  mov     rax, [rax+20h]
0x18003c507  jmp     short loc_18003C4ED
0x18003c509  cmp     ecx, r14d
0x18003c50c  jnz     short loc_18003C514
0x18003c50e  mov     rax, [rax+28h]
0x18003c512  jmp     short loc_18003C4DE
0x18003c514  cmp     ecx, esi
0x18003c516  jnz     short loc_18003C51E
0x18003c518  mov     rax, [r8+10h]
0x18003c51c  jmp     short loc_18003C520
0x18003c51e  xor     eax, eax
0x18003c520  mov     ecx, [rdx]
0x18003c522  movups  xmm0, xmmword ptr [rdx+10h]
0x18003c526  movdqu  xmmword ptr [rbp+3Fh+var_B0.Data1], xmm0
0x18003c52b  lea     r8, [rbp+3Fh+var_58]
0x18003c52f  mov     [rsp+100h+var_D8], r8
0x18003c534  mov     [rsp+100h+var_E0], rax
0x18003c539  mov     r9d, ecx
0x18003c53c  lea     r8, [rbp+3Fh+var_B0]
0x18003c540  mov     rdx, [rdx+8]
0x18003c544  mov     rax, qword ptr [rbp+3Fh+var_A0.Data1]
0x18003c548  call    _guard_dispatch_icall
0x18003c54d  mov     ebx, eax
0x18003c54f  lea     rcx, [rsp+100h+var_C0]
0x18003c554  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x18003c559  jmp     short loc_18003C5A9
0x18003c55b  mov     rcx, [rbp+3Fh+var_58]
0x18003c55f  test    rcx, rcx
0x18003c562  jz      short loc_18003C578
0x18003c564  mov     rax, [rcx]
0x18003c567  mov     rax, [rax+10h]
0x18003c56b  call    _guard_dispatch_icall
0x18003c570  mov     [rbp+3Fh+var_58], 0
0x18003c578  mov     rax, qword ptr [rbp+3Fh+var_B0.Data1]
0x18003c57c  movaps  xmm0, xmmword ptr [rax]
  ... truncated ...
```

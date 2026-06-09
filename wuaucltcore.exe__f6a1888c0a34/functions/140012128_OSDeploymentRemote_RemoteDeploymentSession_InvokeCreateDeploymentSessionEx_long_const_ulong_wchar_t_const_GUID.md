# OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSessionEx(long (*const &)(ulong,wchar_t const *,_GUID,ulong,void *,IDeploymentSession * *),wchar_t const *,ulong,tagOptionalSessionInfo6 *)

- ea: `0x140012128`
- end: `0x1400126b0`
- name: `?InvokeCreateDeploymentSessionEx@RemoteDeploymentSession@OSDeploymentRemote@@AEAAJAEBQ6AJKPEB_WU_GUID@@KPEAXPEAPEAUIDeploymentSession@@@Z0KPEAUtagOptionalSessionInfo6@@@Z`
- size: `1416`
- prototype: `__int64 __fastcall(OSDeploymentRemote::RemoteDeploymentSession *this, __int64 (__fastcall **)(__int64, const wchar_t *, struct _GUID *, __int64, int *, char *, const wchar_t *), const wchar_t *, unsigned int, struct tagOptionalSessionInfo6 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140011f2c`

## callees

- `0x140002ac0`
- `0x14000d2ac`
- `0x14000fd28`
- `0x140012128`
- `0x140013600`
- `0x140013728`
- `0x140017db0`
- `0x14001aa60`
- `0x1400206e0`
- `0x140020760`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400121d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400121d0`

## string_xrefs

- `0x140012641`: `CreateDeploymentSessionEx`
- `0x14001218b`: `Remote: InvokeCreateDeploymentSessionEx()`
- `0x14001246a`: `Remote: CreateDeploymentSessionEx: %ws with OptionalSessionInfo version 5.`

## pseudocode

```c
__int64 __fastcall OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSessionEx(
        OSDeploymentRemote::RemoteDeploymentSession *this,
        __int64 (__fastcall **a2)(__int64, const wchar_t *, struct _GUID *, __int64, int *, char *, const wchar_t *),
        const wchar_t *a3,
        unsigned int a4,
        struct tagOptionalSessionInfo6 *a5)
{
  unsigned int v9; // ebx
  FARPROC ProcAddress; // rax
  unsigned int v11; // ecx
  int v12; // eax
  __int64 (__fastcall *v13)(__int64, const wchar_t *, struct _GUID *, __int64, int *, char *, const wchar_t *); // rbx
  __int64 v14; // rcx
  int *v15; // rax
  __int64 v16; // r8
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 (__fastcall *v22)(__int64, const wchar_t *, struct _GUID *, __int64, int *, char *, const wchar_t *); // rsi
  __int64 v23; // r9
  __int64 (__fastcall *v24)(__int64, const wchar_t *, struct _GUID *, __int64, int *, char *, const wchar_t *); // rax
  unsigned int v25; // ecx
  int v26; // eax
  __int64 (__fastcall *v27)(__int64, const wchar_t *, struct _GUID *, __int64, int *, char *, const wchar_t *); // rbx
  __int64 v28; // rcx
  int *v29; // rax
  __int64 v30; // r8
  int v31; // ecx
  __int64 v32; // rax
  int *v33; // rax
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 (__fastcall *v36)(__int64, const wchar_t *, struct _GUID *, __int64, int *, char *, const wchar_t *); // rbx
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int *v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  struct SessionDataUtil::WUDeploymentSessionInfoWrapper **v44; // [rsp+28h] [rbp-D8h]
  const wchar_t *v45; // [rsp+30h] [rbp-D0h]
  struct SessionDataUtil::WUDeploymentSessionInfoWrapper *v46[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v47; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v48[104]; // [rsp+60h] [rbp-A0h] BYREF
  char v49[8]; // [rsp+C8h] [rbp-38h] BYREF
  int v50; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v51[3]; // [rsp+D4h] [rbp-2Ch] BYREF
  int v52[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v53; // [rsp+F0h] [rbp-10h]
  __int128 v54; // [rsp+100h] [rbp+0h]
  __int128 v55; // [rsp+110h] [rbp+10h]
  __int128 v56; // [rsp+120h] [rbp+20h]
  __int128 v57; // [rsp+130h] [rbp+30h]
  __int64 v58; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  if ( !a5 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)0x80070057LL,
      v40);
    return v9;
  }
  WUTrace(0, 0, 4096, 4);
  *(_QWORD *)v49 = 0;
  if ( a4 < 6 )
    goto LABEL_34;
  ProcAddress = GetProcAddress(*((HMODULE *)this + 3), "GetSupportedSessionInitializationOptions");
  if ( !ProcAddress
    || (v50 = 0, v51[0] = 5, ((int (__fastcall *)(int *, unsigned int *))ProcAddress)(&v50, v51) < 0)
    || (v50 & 1) == 0
    || v51[0] < 6 )
  {
    if ( (*((_BYTE *)a5 + 104) & 1) != 0 )
    {
      v9 = -2145116123;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
        (const char *)0x80242025LL,
        0);
LABEL_65:
      v38 = *(_QWORD *)v49;
      goto LABEL_67;
    }
LABEL_34:
    memset(v48, 0, sizeof(v48));
    *(_OWORD *)v48 = *(_OWORD *)a5;
    *(_OWORD *)&v48[16] = *((_OWORD *)a5 + 1);
    *(_OWORD *)&v48[32] = *((_OWORD *)a5 + 2);
    *(_OWORD *)&v48[48] = *((_OWORD *)a5 + 3);
    *(_DWORD *)&v48[64] = *((_DWORD *)a5 + 16);
    *(_OWORD *)&v48[68] = *(_OWORD *)((char *)a5 + 68);
    *(_OWORD *)&v48[84] = *(_OWORD *)((char *)a5 + 84);
    *(_DWORD *)&v48[100] = *((_DWORD *)a5 + 25);
    *(_OWORD *)v52 = *(_OWORD *)v48;
    v53 = *(_OWORD *)&v48[16];
    v54 = *(_OWORD *)&v48[32];
    v55 = *(_OWORD *)&v48[48];
    v56 = *(_OWORD *)&v48[64];
    v57 = *(_OWORD *)&v48[80];
    v58 = *(_QWORD *)&v48[96];
    v45 = L"Fallbacking";
    WUTrace(0, 0, 4096, 4);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
    {
      v36 = *a2;
      v37 = *(_QWORD *)v49;
      *(_QWORD *)v49 = 0;
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      v42 = v52;
      v23 = 5;
      v24 = v36;
      goto LABEL_62;
    }
    v46[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v46);
    v47 = (struct _GUID)*((_OWORD *)this + 3);
    v26 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(v25, a3, &v47, 5u, v52, v46);
    v9 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
        (const char *)(unsigned int)v26,
        v43);
      goto LABEL_37;
    }
    v27 = *a2;
    v28 = *(_QWORD *)v49;
    *(_QWORD *)v49 = 0;
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v29 = (int *)*((_QWORD *)v46[0] + 4);
    if ( v29 )
    {
      v30 = *((_QWORD *)v29 + 6);
      if ( v30 )
      {
        v31 = *v29;
        if ( *v29 == 1 )
        {
          v32 = *((_QWORD *)v29 + 1);
LABEL_44:
          v33 = *(int **)(v32 + 48);
LABEL_57:
          v35 = *(unsigned int *)v46[0];
          v47 = (struct _GUID)*((_OWORD *)v46[0] + 1);
          v9 = v27(v35, *((const wchar_t **)v46[0] + 1), &v47, (unsigned int)v35, v33, v49, L"Fallbacking");
          goto LABEL_58;
        }
        switch ( v31 )
        {
          case 2:
            v34 = *((_QWORD *)v29 + 2);
LABEL_47:
            v33 = *(int **)(v34 + 16);
            goto LABEL_57;
          case 3:
            v34 = *((_QWORD *)v29 + 3);
            goto LABEL_47;
          case 4:
            v34 = *((_QWORD *)v29 + 4);
            goto LABEL_47;
          case 5:
            v32 = *((_QWORD *)v29 + 5);
            goto LABEL_44;
          case 6:
            v33 = *(int **)(v30 + 16);
            goto LABEL_57;
        }
      }
    }
    v33 = 0;
    goto LABEL_57;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
  {
    v46[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v46);
    v47 = (struct _GUID)*((_OWORD *)this + 3);
    v12 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(v11, a3, &v47, 6u, a5, v46);
    v9 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
        (const char *)(unsigned int)v12,
        v41);
LABEL_37:
      WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v46);
      goto LABEL_65;
    }
    v13 = *a2;
    v14 = *(_QWORD *)v49;
    *(_QWORD *)v49 = 0;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v15 = (int *)*((_QWORD *)v46[0] + 4);
    if ( v15 )
    {
      v16 = *((_QWORD *)v15 + 6);
      if ( v16 )
      {
        v17 = *v15;
        if ( *v15 == 1 )
        {
          v18 = *((_QWORD *)v15 + 1);
LABEL_17:
          v19 = *(_QWORD *)(v18 + 48);
LABEL_30:
          v21 = *(unsigned int *)v46[0];
          v47 = (struct _GUID)*((_OWORD *)v46[0] + 1);
          v9 = ((__int64 (__fastcall *)(__int64, _QWORD, struct _GUID *, _QWORD, __int64, char *))v13)(
                 v21,
                 *((_QWORD *)v46[0] + 1),
                 &v47,
                 (unsigned int)v21,
                 v19,
                 v49);
LABEL_58:
          WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v46);
          goto LABEL_63;
        }
        switch ( v17 )
        {
          case 2:
            v20 = *((_QWORD *)v15 + 2);
LABEL_20:
            v19 = *(_QWORD *)(v20 + 16);
            goto LABEL_30;
          case 3:
            v20 = *((_QWORD *)v15 + 3);
            goto LABEL_20;
          case 4:
            v20 = *((_QWORD *)v15 + 4);
            goto LABEL_20;
          case 5:
            v18 = *((_QWORD *)v15 + 5);
            goto LABEL_17;
          case 6:
            v19 = *(_QWORD *)(v16 + 16);
            goto LABEL_30;
        }
      }
    }
    v19 = 0;
    goto LABEL_30;
  }
  v22 = *a2;
  *(_QWORD *)v49 = 0;
  v42 = (int *)a5;
  v23 = 6;
  v24 = v22;
LABEL_62:
  v47 = (struct _GUID)*((_OWORD *)this + 3);
  v9 = v24(1, a3, &v47, v23, v42, v49, v45);
LABEL_63:
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xEE,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)v9,
      (int)"CreateDeploymentSessionEx",
      (const char *)v44);
    goto LABEL_65;
  }
  v38 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = *(_QWORD *)v49;
  *(_QWORD *)v49 = v38;
  v9 = 0;
LABEL_67:
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  return v9;
}

```

## disassembly

```asm
0x140012128  mov     [rsp-8+arg_18], rbx
0x14001212d  push    rbp
0x14001212e  push    rsi
0x14001212f  push    rdi
0x140012130  push    r14
0x140012132  push    r15
0x140012134  lea     rbp, [rsp-60h]
0x140012139  sub     rsp, 160h
0x140012140  mov     rax, cs:__security_cookie
0x140012147  xor     rax, rsp
0x14001214a  mov     [rbp+80h+var_30], rax
0x14001214e  mov     r15d, r9d
0x140012151  mov     r14, r8
0x140012154  mov     rsi, rdx
0x140012157  mov     rdi, rcx
0x14001215a  mov     rbx, [rbp+80h+arg_20]
0x140012161  test    rbx, rbx
0x140012164  jnz     short loc_14001218B
0x140012166  mov     rcx, [rbp+88h]; this
0x14001216d  mov     ebx, 80070057h
0x140012172  mov     r9d, ebx; char *
0x140012175  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x14001217c  mov     edx, 7Bh ; '{'; void *
0x140012181  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012186  jmp     loc_14001268B
0x14001218b  lea     rax, aRemoteInvokecr; "Remote: InvokeCreateDeploymentSessionEx"...
0x140012192  mov     [rsp+180h+var_158], rax
0x140012197  mov     [rsp+180h+var_160], 0; int
0x1400121a0  xor     edx, edx
0x1400121a2  xor     ecx, ecx
0x1400121a4  lea     r9d, [rdx+4]
0x1400121a8  mov     r8d, 1000h
0x1400121ae  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400121b3  mov     qword ptr [rbp+80h+var_B8], 0
0x1400121bb  cmp     r15d, 6
0x1400121bf  jb      loc_1400123B3
0x1400121c5  lea     rdx, aGetsupportedse; "GetSupportedSessionInitializationOption"...
0x1400121cc  mov     rcx, [rdi+18h]; hModule
0x1400121d0  call    cs:__imp_GetProcAddress
0x1400121d6  test    rax, rax
0x1400121d9  jz      loc_140012388
0x1400121df  mov     [rbp+80h+var_B0], 0
0x1400121e6  mov     [rbp+80h+var_AC], 5
0x1400121ed  lea     rdx, [rbp+80h+var_AC]
0x1400121f1  lea     rcx, [rbp+80h+var_B0]
0x1400121f5  call    _guard_dispatch_icall
0x1400121fa  test    eax, eax
0x1400121fc  js      loc_140012388
0x140012202  test    byte ptr [rbp+80h+var_B0], 1
0x140012206  jz      loc_140012388
0x14001220c  mov     r15d, 6
0x140012212  cmp     [rbp+80h+var_AC], r15d
0x140012216  jb      loc_140012388
0x14001221c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl(void)'::`2'::impl
0x140012223  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(void)
0x140012228  test    al, al
0x14001222a  jz      loc_14001234E
0x140012230  mov     [rsp+180h+var_140], 0
0x140012239  lea     rcx, [rsp+180h+var_140]
0x14001223e  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x140012243  movups  xmm0, xmmword ptr [rdi+30h]
0x140012247  movdqu  xmmword ptr [rsp+180h+var_130.Data1], xmm0
0x14001224d  lea     rax, [rsp+180h+var_140]
0x140012252  mov     [rsp+180h+var_158], rax; struct SessionDataUtil::WUDeploymentSessionInfoWrapper **
0x140012257  mov     [rsp+180h+var_160], rbx; int
0x14001225c  mov     r9d, r15d; unsigned int
0x14001225f  lea     r8, [rsp+180h+var_130]; struct _GUID
0x140012264  mov     rdx, r14; wchar_t *
0x140012267  call    ?CreateInstance@WUDeploymentSessionInfoWrapper@SessionDataUtil@@SAJKPEB_WU_GUID@@KPEBXPEAPEAV12@@Z; SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(ulong,wchar_t const *,_GUID,ulong,void const *,SessionDataUtil::WUDeploymentSessionInfoWrapper * *)
0x14001226c  mov     ebx, eax
0x14001226e  test    eax, eax
0x140012270  jns     short loc_140012293
0x140012272  mov     rcx, [rbp+88h]; this
0x140012279  mov     r9d, eax; char *
0x14001227c  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012283  mov     edx, 0A3h; void *
0x140012288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001228d  nop
0x14001228e  jmp     loc_14001250B
0x140012293  mov     rbx, [rsi]
0x140012296  mov     rcx, qword ptr [rbp+80h+var_B8]
0x14001229a  mov     qword ptr [rbp+80h+var_B8], 0
0x1400122a2  test    rcx, rcx
0x1400122a5  jz      short loc_1400122B4
0x1400122a7  mov     rax, [rcx]
0x1400122aa  mov     rax, [rax+10h]
0x1400122ae  call    _guard_dispatch_icall
0x1400122b3  nop
0x1400122b4  mov     rdx, [rsp+180h+var_140]
0x1400122b9  mov     rax, [rdx+20h]
0x1400122bd  test    rax, rax
0x1400122c0  jz      short loc_140012317
0x1400122c2  mov     r8, [rax+30h]
0x1400122c6  test    r8, r8
0x1400122c9  jz      short loc_140012317
0x1400122cb  mov     ecx, [rax]
0x1400122cd  cmp     ecx, 1
0x1400122d0  jnz     short loc_1400122DC
0x1400122d2  mov     rax, [rax+8]
0x1400122d6  mov     rax, [rax+30h]
0x1400122da  jmp     short loc_140012319
0x1400122dc  cmp     ecx, 2
0x1400122df  jnz     short loc_1400122EB
0x1400122e1  mov     rax, [rax+10h]
0x1400122e5  mov     rax, [rax+10h]
0x1400122e9  jmp     short loc_140012319
0x1400122eb  cmp     ecx, 3
0x1400122ee  jnz     short loc_1400122F6
0x1400122f0  mov     rax, [rax+18h]
0x1400122f4  jmp     short loc_1400122E5
0x1400122f6  cmp     ecx, 4
0x1400122f9  jnz     short loc_140012301
0x1400122fb  mov     rax, [rax+20h]
0x1400122ff  jmp     short loc_1400122E5
0x140012301  cmp     ecx, 5
0x140012304  jnz     short loc_14001230C
0x140012306  mov     rax, [rax+28h]
0x14001230a  jmp     short loc_1400122D6
0x14001230c  cmp     ecx, r15d
0x14001230f  jnz     short loc_140012317
0x140012311  mov     rax, [r8+10h]
0x140012315  jmp     short loc_140012319
0x140012317  xor     eax, eax
0x140012319  mov     ecx, [rdx]
0x14001231b  movups  xmm0, xmmword ptr [rdx+10h]
0x14001231f  movdqu  xmmword ptr [rsp+180h+var_130.Data1], xmm0
0x140012325  lea     r8, [rbp+80h+var_B8]
0x140012329  mov     [rsp+180h+var_158], r8
0x14001232e  mov     [rsp+180h+var_160], rax
0x140012333  mov     r9d, ecx
0x140012336  lea     r8, [rsp+180h+var_130]
0x14001233b  mov     rdx, [rdx+8]
0x14001233f  mov     rax, rbx
0x140012342  call    _guard_dispatch_icall
0x140012347  mov     ebx, eax
0x140012349  jmp     loc_1400125D0
0x14001234e  mov     rsi, [rsi]
0x140012351  mov     rcx, qword ptr [rbp+80h+var_B8]
0x140012355  mov     qword ptr [rbp+80h+var_B8], 0
0x14001235d  test    rcx, rcx
0x140012360  jz      short loc_14001236F
0x140012362  mov     rax, [rcx]
0x140012365  mov     rax, [rax+10h]
0x140012369  call    _guard_dispatch_icall
0x14001236e  nop
0x14001236f  lea     rax, [rbp+80h+var_B8]
0x140012373  mov     [rsp+180h+var_158], rax
0x140012378  mov     [rsp+180h+var_160], rbx
0x14001237d  mov     r9d, r15d
0x140012380  mov     rax, rsi
0x140012383  jmp     loc_140012618
0x140012388  test    byte ptr [rbx+68h], 1
0x14001238c  jz      short loc_1400123B3
0x14001238e  mov     rcx, [rbp+88h]; this
0x140012395  mov     ebx, 80242025h
0x14001239a  mov     r9d, ebx; char *
0x14001239d  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1400123a4  mov     edx, 0C3h; void *
0x1400123a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400123ae  jmp     loc_140012661
0x1400123b3  xor     edx, edx; Val
0x1400123b5  lea     r8d, [rdx+68h]; Size
0x1400123b9  lea     rcx, [rsp+180h+var_120]; void *
0x1400123be  call    memset
0x1400123c3  mov     rax, [rbx]
0x1400123c6  mov     qword ptr [rsp+180h+var_120], rax
0x1400123cb  mov     rax, [rbx+8]
0x1400123cf  mov     qword ptr [rsp+180h+var_120+8], rax
0x1400123d4  mov     rax, [rbx+10h]
0x1400123d8  mov     qword ptr [rsp+180h+var_110], rax
0x1400123dd  mov     rax, [rbx+18h]
0x1400123e1  mov     qword ptr [rsp+180h+var_110+8], rax
0x1400123e6  mov     rax, [rbx+20h]
0x1400123ea  mov     qword ptr [rbp+80h+var_100], rax
0x1400123ee  mov     rax, [rbx+28h]
0x1400123f2  mov     qword ptr [rbp+80h+var_100+8], rax
0x1400123f6  mov     rax, [rbx+30h]
0x1400123fa  mov     qword ptr [rbp+80h+var_F0], rax
0x1400123fe  mov     rax, [rbx+38h]
0x140012402  mov     qword ptr [rbp+80h+var_F0+8], rax
0x140012406  mov     eax, [rbx+40h]
0x140012409  mov     dword ptr [rbp+80h+var_E0], eax
0x14001240c  movups  xmm0, xmmword ptr [rbx+44h]
0x140012410  movups  [rbp+80h+var_E0+4], xmm0
0x140012414  movups  xmm1, xmmword ptr [rbx+54h]
0x140012418  movups  [rbp+80h+var_CC], xmm1
0x14001241c  mov     eax, [rbx+64h]
0x14001241f  mov     [rbp+80h+var_BC], eax
0x140012422  movups  xmm0, [rsp+180h+var_120]
0x140012427  movaps  xmmword ptr [rbp+80h+var_A0], xmm0
0x14001242b  movups  xmm1, [rsp+180h+var_110]
0x140012430  movaps  [rbp+80h+var_90], xmm1
0x140012434  movups  xmm0, [rbp+80h+var_100]
0x140012438  movaps  [rbp+80h+var_80], xmm0
0x14001243c  movups  xmm1, [rbp+80h+var_F0]
0x140012440  movaps  [rbp+80h+var_70], xmm1
0x140012444  movups  xmm0, [rbp+80h+var_E0]
0x140012448  movaps  [rbp+80h+var_60], xmm0
0x14001244c  movups  xmm1, xmmword ptr [rbp-50h]
0x140012450  movaps  [rbp+80h+var_50], xmm1
0x140012454  movsd   xmm0, qword ptr [rbp+80h+var_CC+0Ch]
0x140012459  movsd   [rbp+80h+var_40], xmm0
0x14001245e  lea     rax, aFallbacking; "Fallbacking"
0x140012465  mov     [rsp+180h+var_150], rax
0x14001246a  lea     rax, aRemoteCreatede; "Remote: CreateDeploymentSessionEx: %ws "...
0x140012471  mov     [rsp+180h+var_158], rax
0x140012476  mov     [rsp+180h+var_160], 0
0x14001247f  xor     edx, edx
0x140012481  xor     ecx, ecx
0x140012483  lea     r9d, [rdx+4]
0x140012487  mov     r8d, 1000h
0x14001248d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140012492  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl(void)'::`2'::impl
0x140012499  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(void)
0x14001249e  test    al, al
0x1400124a0  jz      loc_1400125DC
0x1400124a6  mov     [rsp+180h+var_140], 0
0x1400124af  lea     rcx, [rsp+180h+var_140]
0x1400124b4  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x1400124b9  movups  xmm0, xmmword ptr [rdi+30h]
0x1400124bd  movdqu  xmmword ptr [rsp+180h+var_130.Data1], xmm0
0x1400124c3  lea     rax, [rsp+180h+var_140]
0x1400124c8  mov     [rsp+180h+var_158], rax; struct SessionDataUtil::WUDeploymentSessionInfoWrapper **
0x1400124cd  lea     rax, [rbp+80h+var_A0]
0x1400124d1  mov     [rsp+180h+var_160], rax; int
0x1400124d6  mov     r9d, 5; unsigned int
0x1400124dc  lea     r8, [rsp+180h+var_130]; struct _GUID
0x1400124e1  mov     rdx, r14; wchar_t *
0x1400124e4  call    ?CreateInstance@WUDeploymentSessionInfoWrapper@SessionDataUtil@@SAJKPEB_WU_GUID@@KPEBXPEAPEAV12@@Z; SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(ulong,wchar_t const *,_GUID,ulong,void const *,SessionDataUtil::WUDeploymentSessionInfoWrapper * *)
0x1400124e9  mov     ebx, eax
0x1400124eb  test    eax, eax
0x1400124ed  jns     short loc_14001251A
0x1400124ef  mov     rcx, [rbp+88h]; this
0x1400124f6  mov     r9d, eax; char *
0x1400124f9  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012500  mov     edx, 0D9h; void *
0x140012505  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001250a  nop
0x14001250b  lea     rcx, [rsp+180h+var_140]
0x140012510  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x140012515  jmp     loc_140012661
0x14001251a  mov     rbx, [rsi]
0x14001251d  mov     rcx, qword ptr [rbp+80h+var_B8]
0x140012521  mov     qword ptr [rbp+80h+var_B8], 0
0x140012529  test    rcx, rcx
0x14001252c  jz      short loc_14001253B
0x14001252e  mov     rax, [rcx]
0x140012531  mov     rax, [rax+10h]
0x140012535  call    _guard_dispatch_icall
0x14001253a  nop
0x14001253b  mov     rdx, [rsp+180h+var_140]
0x140012540  mov     rax, [rdx+20h]
0x140012544  test    rax, rax
0x140012547  jz      short loc_14001259E
0x140012549  mov     r8, [rax+30h]
0x14001254d  test    r8, r8
0x140012550  jz      short loc_14001259E
0x140012552  mov     ecx, [rax]
0x140012554  cmp     ecx, 1
0x140012557  jnz     short loc_140012563
0x140012559  mov     rax, [rax+8]
0x14001255d  mov     rax, [rax+30h]
0x140012561  jmp     short loc_1400125A0
0x140012563  cmp     ecx, 2
0x140012566  jnz     short loc_140012572
0x140012568  mov     rax, [rax+10h]
0x14001256c  mov     rax, [rax+10h]
0x140012570  jmp     short loc_1400125A0
0x140012572  cmp     ecx, 3
0x140012575  jnz     short loc_14001257D
0x140012577  mov     rax, [rax+18h]
0x14001257b  jmp     short loc_14001256C
0x14001257d  cmp     ecx, 4
0x140012580  jnz     short loc_140012588
0x140012582  mov     rax, [rax+20h]
0x140012586  jmp     short loc_14001256C
0x140012588  cmp     ecx, 5
0x14001258b  jnz     short loc_140012593
0x14001258d  mov     rax, [rax+28h]
0x140012591  jmp     short loc_14001255D
0x140012593  cmp     ecx, 6
0x140012596  jnz     short loc_14001259E
0x140012598  mov     rax, [r8+10h]
0x14001259c  jmp     short loc_1400125A0
0x14001259e  xor     eax, eax
0x1400125a0  mov     ecx, [rdx]
0x1400125a2  movups  xmm0, xmmword ptr [rdx+10h]
0x1400125a6  movdqu  xmmword ptr [rsp+180h+var_130.Data1], xmm0
0x1400125ac  lea     r8, [rbp+80h+var_B8]
0x1400125b0  mov     [rsp+180h+var_158], r8
0x1400125b5  mov     [rsp+180h+var_160], rax
0x1400125ba  mov     r9d, ecx
0x1400125bd  lea     r8, [rsp+180h+var_130]
0x1400125c2  mov     rdx, [rdx+8]
0x1400125c6  mov     rax, rbx
0x1400125c9  call    _guard_dispatch_icall
0x1400125ce  mov     ebx, eax
0x1400125d0  lea     rcx, [rsp+180h+var_140]
0x1400125d5  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x1400125da  jmp     short loc_140012636
  ... truncated ...
```

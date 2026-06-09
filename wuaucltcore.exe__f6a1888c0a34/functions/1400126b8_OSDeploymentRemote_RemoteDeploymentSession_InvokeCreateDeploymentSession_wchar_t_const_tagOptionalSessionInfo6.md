# OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSession(wchar_t const *,tagOptionalSessionInfo6 *)

- ea: `0x1400126b8`
- end: `0x140012988`
- name: `?InvokeCreateDeploymentSession@RemoteDeploymentSession@OSDeploymentRemote@@AEAAJPEB_WPEAUtagOptionalSessionInfo6@@@Z`
- size: `720`
- prototype: `__int64 __fastcall(OSDeploymentRemote::RemoteDeploymentSession *__hidden this, const wchar_t *, struct tagOptionalSessionInfo6 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140011f2c`

## callees

- `0x140002ac0`
- `0x14000d2ac`
- `0x14000fd28`
- `0x1400126b8`
- `0x140013600`
- `0x140013728`
- `0x140014980`
- `0x140017db0`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012746`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012746`

## string_xrefs

- `0x140012710`: `Remote: InvokeCreateDeploymentSession()`
- `0x140012738`: `CreateDeploymentSession`

## pseudocode

```c
__int64 __fastcall OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSession(
        OSDeploymentRemote::RemoteDeploymentSession *this,
        const wchar_t *a2,
        struct tagOptionalSessionInfo6 *a3)
{
  unsigned int v6; // ebx
  FARPROC ProcAddress; // r14
  unsigned int v9; // ecx
  int v10; // eax
  __int64 *v11; // rdi
  __int64 v12; // rcx
  int *v13; // rax
  __int64 v14; // r9
  int v15; // edx
  __int64 v16; // rax
  __int64 v17; // r9
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  int v22; // [rsp+20h] [rbp-39h]
  int v23; // [rsp+20h] [rbp-39h]
  struct SessionDataUtil::WUDeploymentSessionInfoWrapper **v24; // [rsp+28h] [rbp-31h]
  struct SessionDataUtil::WUDeploymentSessionInfoWrapper **v25; // [rsp+28h] [rbp-31h]
  struct SessionDataUtil::WUDeploymentSessionInfoWrapper *v26[2]; // [rsp+30h] [rbp-29h] BYREF
  struct _GUID v27; // [rsp+40h] [rbp-19h] BYREF
  int v28[2]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v29; // [rsp+58h] [rbp-1h]
  __int64 v30; // [rsp+60h] [rbp+7h]
  __int64 v31; // [rsp+68h] [rbp+Fh]
  __int64 v32; // [rsp+70h] [rbp+17h]
  __int64 v33; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)0x80070057LL,
      v22);
    return v6;
  }
  WUTrace(0, 0, 4096, 4);
  ProcAddress = GetProcAddress(*((HMODULE *)this + 3), "CreateDeploymentSession");
  if ( !ProcAddress )
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)0xFF,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
             "CreateDeploymentSession",
             0,
             L"Remote: InvokeCreateDeploymentSession()");
  *(_QWORD *)v28 = *(_QWORD *)a3;
  v29 = *((_QWORD *)a3 + 1);
  v30 = *((_QWORD *)a3 + 2);
  v31 = *((_QWORD *)a3 + 3);
  v32 = *((_QWORD *)a3 + 4);
  v33 = *((_QWORD *)a3 + 5);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
  {
    v20 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = 0;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v27 = (struct _GUID)*((_OWORD *)this + 3);
    v21 = ((__int64 (__fastcall *)(__int64, const wchar_t *, struct _GUID *, int *, char *, const char *))ProcAddress)(
            1,
            a2,
            &v27,
            v28,
            (char *)this + 32,
            L"Remote: InvokeCreateDeploymentSession()");
    v6 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x127,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
        (const char *)(unsigned int)v21,
        (int)"CreateDeploymentSession",
        (const char *)v25);
      return v6;
    }
    return 0;
  }
  v26[0] = 0;
  WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v26);
  v27 = (struct _GUID)*((_OWORD *)this + 3);
  v10 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(v9, a2, &v27, 1u, v28, v26);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)(unsigned int)v10,
      v23);
LABEL_30:
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v26);
    return v6;
  }
  v11 = (__int64 *)((char *)this + 32);
  v12 = *v11;
  *v11 = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = (int *)*((_QWORD *)v26[0] + 4);
  if ( !v13 )
    goto LABEL_27;
  v14 = *((_QWORD *)v13 + 6);
  if ( !v14 )
    goto LABEL_27;
  v15 = *v13;
  if ( *v13 != 1 )
  {
    switch ( v15 )
    {
      case 2:
        v18 = *((_QWORD *)v13 + 2);
LABEL_18:
        v17 = *(_QWORD *)(v18 + 16);
        goto LABEL_28;
      case 3:
        v18 = *((_QWORD *)v13 + 3);
        goto LABEL_18;
      case 4:
        v18 = *((_QWORD *)v13 + 4);
        goto LABEL_18;
      case 5:
        v16 = *((_QWORD *)v13 + 5);
        goto LABEL_15;
      case 6:
        v17 = *(_QWORD *)(v14 + 16);
        goto LABEL_28;
    }
LABEL_27:
    v17 = 0;
    goto LABEL_28;
  }
  v16 = *((_QWORD *)v13 + 1);
LABEL_15:
  v17 = *(_QWORD *)(v16 + 48);
LABEL_28:
  v27 = (struct _GUID)*((_OWORD *)v26[0] + 1);
  v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, struct _GUID *, __int64, __int64 *))ProcAddress)(
          *(unsigned int *)v26[0],
          *((_QWORD *)v26[0] + 1),
          &v27,
          v17,
          v11);
  v6 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x11E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)(unsigned int)v19,
      (int)"CreateDeploymentSession",
      (const char *)v24);
    goto LABEL_30;
  }
  WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v26);
  return 0;
}

```

## disassembly

```asm
0x1400126b8  mov     [rsp-8+arg_18], rbx
0x1400126bd  push    rbp
0x1400126be  push    rsi
0x1400126bf  push    rdi
0x1400126c0  push    r12
0x1400126c2  push    r14
0x1400126c4  lea     rbp, [rsp-37h]
0x1400126c9  sub     rsp, 90h
0x1400126d0  mov     rax, cs:__security_cookie
0x1400126d7  xor     rax, rsp
0x1400126da  mov     [rbp+57h+var_30], rax
0x1400126de  mov     rbx, r8
0x1400126e1  mov     rsi, rdx
0x1400126e4  mov     rdi, rcx
0x1400126e7  test    r8, r8
0x1400126ea  jnz     short loc_140012710
0x1400126ec  mov     rcx, [rbp+5Fh]; this
0x1400126f0  mov     ebx, 80070057h
0x1400126f5  mov     r9d, ebx; char *
0x1400126f8  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1400126ff  mov     edx, 0F8h; void *
0x140012704  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012709  mov     eax, ebx
0x14001270b  jmp     loc_1400128F7
0x140012710  lea     rax, aRemoteInvokecr_0; "Remote: InvokeCreateDeploymentSession()"
0x140012717  mov     [rsp+0B0h+var_88], rax; char *
0x14001271c  mov     [rsp+0B0h+var_90], 0; char *
0x140012725  xor     edx, edx
0x140012727  xor     ecx, ecx
0x140012729  lea     r9d, [rdx+4]
0x14001272d  mov     r8d, 1000h
0x140012733  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140012738  lea     r12, aCreatedeployme_0; "CreateDeploymentSession"
0x14001273f  mov     rdx, r12; lpProcName
0x140012742  mov     rcx, [rdi+18h]; hModule
0x140012746  call    cs:__imp_GetProcAddress
0x14001274c  mov     r14, rax
0x14001274f  test    rax, rax
0x140012752  jnz     short loc_140012771
0x140012754  mov     rcx, [rbp+5Fh]; this
0x140012758  mov     r9, r12; char *
0x14001275b  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012762  mov     edx, 0FFh; void *
0x140012767  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14001276c  jmp     loc_1400128F7
0x140012771  mov     rax, [rbx]
0x140012774  mov     qword ptr [rbp+57h+var_60], rax
0x140012778  mov     rax, [rbx+8]
0x14001277c  mov     [rbp+57h+var_58], rax
0x140012780  mov     rax, [rbx+10h]
0x140012784  mov     [rbp+57h+var_50], rax
0x140012788  mov     rax, [rbx+18h]
0x14001278c  mov     [rbp+57h+var_48], rax
0x140012790  mov     rax, [rbx+20h]
0x140012794  mov     [rbp+57h+var_40], rax
0x140012798  mov     rax, [rbx+28h]
0x14001279c  mov     [rbp+57h+var_38], rax
0x1400127a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl(void)'::`2'::impl
0x1400127a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(void)
0x1400127ac  test    al, al
0x1400127ae  jz      loc_14001291A
0x1400127b4  mov     [rbp+57h+var_80], 0
0x1400127bc  lea     rcx, [rbp+57h+var_80]
0x1400127c0  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x1400127c5  movups  xmm0, xmmword ptr [rdi+30h]
0x1400127c9  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x1400127ce  lea     rax, [rbp+57h+var_80]
0x1400127d2  mov     [rsp+0B0h+var_88], rax; char *
0x1400127d7  lea     rax, [rbp+57h+var_60]
0x1400127db  mov     [rsp+0B0h+var_90], rax; int
0x1400127e0  mov     r9d, 1; unsigned int
0x1400127e6  lea     r8, [rbp+57h+var_70]; struct _GUID
0x1400127ea  mov     rdx, rsi; wchar_t *
0x1400127ed  call    ?CreateInstance@WUDeploymentSessionInfoWrapper@SessionDataUtil@@SAJKPEB_WU_GUID@@KPEBXPEAPEAV12@@Z; SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(ulong,wchar_t const *,_GUID,ulong,void const *,SessionDataUtil::WUDeploymentSessionInfoWrapper * *)
0x1400127f2  mov     ebx, eax
0x1400127f4  test    eax, eax
0x1400127f6  jns     short loc_140012815
0x1400127f8  mov     rcx, [rbp+5Fh]; this
0x1400127fc  mov     r9d, eax; char *
0x1400127ff  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012806  mov     edx, 115h; void *
0x14001280b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012810  jmp     loc_1400128DE
0x140012815  add     rdi, 20h ; ' '
0x140012819  mov     rcx, [rdi]
0x14001281c  mov     qword ptr [rdi], 0
0x140012823  test    rcx, rcx
0x140012826  jz      short loc_140012835
0x140012828  mov     rax, [rcx]
0x14001282b  mov     rax, [rax+10h]
0x14001282f  call    _guard_dispatch_icall
0x140012834  nop
0x140012835  mov     rcx, [rbp+57h+var_80]
0x140012839  mov     rax, [rcx+20h]
0x14001283d  test    rax, rax
0x140012840  jz      short loc_140012897
0x140012842  mov     r9, [rax+30h]
0x140012846  test    r9, r9
0x140012849  jz      short loc_140012897
0x14001284b  mov     edx, [rax]
0x14001284d  cmp     edx, 1
0x140012850  jnz     short loc_14001285C
0x140012852  mov     rax, [rax+8]
0x140012856  mov     r9, [rax+30h]
0x14001285a  jmp     short loc_14001289A
0x14001285c  cmp     edx, 2
0x14001285f  jnz     short loc_14001286B
0x140012861  mov     rax, [rax+10h]
0x140012865  mov     r9, [rax+10h]
0x140012869  jmp     short loc_14001289A
0x14001286b  cmp     edx, 3
0x14001286e  jnz     short loc_140012876
0x140012870  mov     rax, [rax+18h]
0x140012874  jmp     short loc_140012865
0x140012876  cmp     edx, 4
0x140012879  jnz     short loc_140012881
0x14001287b  mov     rax, [rax+20h]
0x14001287f  jmp     short loc_140012865
0x140012881  cmp     edx, 5
0x140012884  jnz     short loc_14001288C
0x140012886  mov     rax, [rax+28h]
0x14001288a  jmp     short loc_140012856
0x14001288c  cmp     edx, 6
0x14001288f  jnz     short loc_140012897
0x140012891  mov     r9, [r9+10h]
0x140012895  jmp     short loc_14001289A
0x140012897  xor     r9d, r9d
0x14001289a  movups  xmm0, xmmword ptr [rcx+10h]
0x14001289e  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x1400128a3  mov     [rsp+0B0h+var_90], rdi
0x1400128a8  lea     r8, [rbp+57h+var_70]
0x1400128ac  mov     rdx, [rcx+8]
0x1400128b0  mov     ecx, [rcx]
0x1400128b2  mov     rax, r14
0x1400128b5  call    _guard_dispatch_icall
0x1400128ba  mov     ebx, eax
0x1400128bc  test    eax, eax
0x1400128be  jns     short loc_1400128EC
0x1400128c0  mov     rcx, [rbp+5Fh]; this
0x1400128c4  mov     [rsp+0B0h+var_90], r12; int
0x1400128c9  mov     r9d, eax; char *
0x1400128cc  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1400128d3  mov     edx, 11Eh; void *
0x1400128d8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400128dd  nop
0x1400128de  lea     rcx, [rbp+57h+var_80]
0x1400128e2  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x1400128e7  jmp     loc_140012709
0x1400128ec  lea     rcx, [rbp+57h+var_80]
0x1400128f0  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x1400128f5  xor     eax, eax
0x1400128f7  mov     rcx, [rbp+57h+var_30]
0x1400128fb  xor     rcx, rsp; StackCookie
0x1400128fe  call    __security_check_cookie
0x140012903  mov     rbx, [rsp+0B0h+arg_18]
0x14001290b  add     rsp, 90h
0x140012912  pop     r14
0x140012914  pop     r12
0x140012916  pop     rdi
0x140012917  pop     rsi
0x140012918  pop     rbp
0x140012919  retn
0x14001291a  lea     rbx, [rdi+20h]
0x14001291e  mov     rcx, [rbx]
0x140012921  mov     qword ptr [rbx], 0
0x140012928  test    rcx, rcx
0x14001292b  jz      short loc_14001293A
0x14001292d  mov     rax, [rcx]
0x140012930  mov     rax, [rax+10h]
0x140012934  call    _guard_dispatch_icall
0x140012939  nop
0x14001293a  movups  xmm0, xmmword ptr [rdi+30h]
0x14001293e  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x140012943  mov     [rsp+0B0h+var_90], rbx
0x140012948  lea     r9, [rbp+57h+var_60]
0x14001294c  lea     r8, [rbp+57h+var_70]
0x140012950  mov     rdx, rsi
0x140012953  mov     ecx, 1
0x140012958  mov     rax, r14
0x14001295b  call    _guard_dispatch_icall
0x140012960  mov     ebx, eax
0x140012962  test    eax, eax
0x140012964  jns     short loc_1400128F5
0x140012966  mov     rcx, [rbp+5Fh]; this
0x14001296a  mov     [rsp+0B0h+var_90], r12; int
0x14001296f  mov     r9d, eax; char *
0x140012972  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012979  mov     edx, 127h; void *
0x14001297e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140012983  jmp     loc_140012709
```

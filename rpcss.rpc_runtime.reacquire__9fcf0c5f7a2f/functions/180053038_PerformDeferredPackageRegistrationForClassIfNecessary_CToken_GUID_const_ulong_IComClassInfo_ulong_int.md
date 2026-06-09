# PerformDeferredPackageRegistrationForClassIfNecessary(CToken *,_GUID const &,ulong,IComClassInfo *,ulong,int *)

- ea: `0x180053038`
- end: `0x1800535bb`
- name: `?PerformDeferredPackageRegistrationForClassIfNecessary@@YAJPEAVCToken@@AEBU_GUID@@KPEAUIComClassInfo@@KPEAH@Z`
- size: `1411`
- prototype: `__int64 __usercall@<rax>(struct CToken *this@<rcx>, const struct _GUID *@<rdx>, unsigned int@<r8d>, struct IComClassInfo *@<r9>, unsigned int, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008e54c`

## callees

- `0x180003194`
- `0x1800210f8`
- `0x180025950`
- `0x18002faa8`
- `0x180053038`
- `0x1800535d0`
- `0x180053644`
- `0x1800537c0`
- `0x18005382c`
- `0x180095c0c`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x180114010`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18005315e`
- `ntdll!RtlIsMultiSessionSku` at `0x18005315e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800531f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800534dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800531f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800534dc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800531cb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800531cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800532e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005341a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800532e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005341a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053283`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18005329a`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18005329a`

## string_xrefs

- `0x180053377`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800533fa`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180053458`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18005347a`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800534b1`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800534f4`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180053533`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180053558`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180053581`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`

## pseudocode

```c
__int64 __fastcall PerformDeferredPackageRegistrationForClassIfNecessary(
        struct CToken *this,
        const struct _GUID *a2,
        unsigned int a3,
        __int64 (__fastcall ***a4)(struct IComClassInfo *, GUID *, __int64 *),
        unsigned int a5,
        int *a6)
{
  bool v6; // si
  __int64 (__fastcall **v10)(struct IComClassInfo *, GUID *, __int64 *); // rax
  int UserSidForSession; // ebx
  __int64 v12; // rcx
  __int64 (__fastcall **v13)(struct IComClassInfo *, GUID *, __int64 *); // rax
  int v14; // eax
  int v15; // eax
  __int64 (__fastcall **v16)(struct IComClassInfo *, GUID *, __int64 *); // rax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  unsigned int v21; // eax
  __int64 v23; // rdx
  void (*v24)(void); // rax
  void (*v25)(void); // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  int v35; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid1; // [rsp+78h] [rbp-88h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v38; // [rsp+84h] [rbp-7Ch]
  PSID *p_pSid1; // [rsp+88h] [rbp-78h] BYREF
  void *v40; // [rsp+90h] [rbp-70h] BYREF
  char v41; // [rsp+98h] [rbp-68h]
  WCHAR packageFamilyName[72]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v6 = 0;
  v38 = a3;
  *a6 = 0;
  if ( !this )
  {
    UserSidForSession = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EC,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)0x8000FFFFLL,
      v28);
    return (unsigned int)UserSidForSession;
  }
  v10 = *a4;
  v29 = 0;
  UserSidForSession = (*v10)((struct IComClassInfo *)a4, &GUID_430be197_0244_2f7b_80fd_c7c473983ad0, &v29);
  if ( UserSidForSession < 0 )
  {
    v26 = 495;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)UserSidForSession,
      v28);
    if ( !v29 )
      return (unsigned int)UserSidForSession;
    v25 = *(void (**)(void))(*(_QWORD *)v29 + 16LL);
    goto LABEL_41;
  }
  v32 = 0;
  UserSidForSession = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 24LL))(v29, &v32);
  if ( UserSidForSession < 0 )
  {
    v26 = 498;
    goto LABEL_49;
  }
  if ( v32 != 2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v12);
    if ( v32 != 2 )
    {
      UserSidForSession = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F5,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)0x8000FFFFLL,
        v28);
LABEL_39:
      if ( !v29 )
        return (unsigned int)UserSidForSession;
      v25 = *(void (**)(void))(*(_QWORD *)v29 + 16LL);
LABEL_41:
      v25();
      return (unsigned int)UserSidForSession;
    }
  }
  v13 = *a4;
  v31 = 0;
  v14 = (*v13)((struct IComClassInfo *)a4, &GUID_000001e2_0000_0000_c000_000000000046, &v31);
  UserSidForSession = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v14,
      v28);
LABEL_62:
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v31);
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v29);
    return (unsigned int)UserSidForSession;
  }
  v30 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v31 + 48LL))(
          v31,
          &GUID_000001ed_0000_0000_c000_000000000046,
          &v30);
  UserSidForSession = v15;
  if ( v15 < 0 )
  {
    v27 = 507;
LABEL_61:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v15,
      v28);
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v30);
    goto LABEL_62;
  }
  v35 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 40LL))(v30, &v35);
  UserSidForSession = v15;
  if ( v15 < 0 )
  {
    v27 = 514;
    goto LABEL_61;
  }
  if ( v35 != 1 )
  {
    if ( (unsigned __int8)RtlIsMultiSessionSku() )
    {
      if ( a5 == CToken::GetSessionId(this) )
      {
        pSid1 = 0;
        p_pSid1 = &pSid1;
        v40 = 0;
        v41 = 1;
        UserSidForSession = GetUserSidForSession(a5, &v40);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_pSid1);
        if ( UserSidForSession < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x219,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
            (const char *)(unsigned int)UserSidForSession,
            v28);
          if ( pSid1 )
            HeapFree(g_hHeap, 0, pSid1);
          goto LABEL_35;
        }
        v6 = !EqualSid(pSid1, (char *)this + 156);
        if ( pSid1 )
          HeapFree(g_hHeap, 0, pSid1);
      }
      else
      {
        v6 = 1;
      }
    }
    v16 = *a4;
    v34 = 0;
    v17 = (*v16)((struct IComClassInfo *)a4, &GUID_0318b242_d086_4de9_b10c_2824a6ca1019, &v34);
    UserSidForSession = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x223,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)(unsigned int)v17,
        v28);
    }
    else
    {
      v18 = v34;
      string = 0;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 80LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      UserSidForSession = v19(v18, &string);
      if ( UserSidForSession < 0 )
      {
        v23 = 550;
LABEL_30:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)(unsigned int)UserSidForSession,
          v28);
        if ( string )
          WindowsDeleteString(string);
        if ( !v34 )
          goto LABEL_35;
        v24 = *(void (**)(void))(*(_QWORD *)v34 + 16LL);
        goto LABEL_34;
      }
      memset_0(packageFamilyName, 0, 0x82u);
      packageFamilyNameLength = 65;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v21 = PackageFamilyNameFromFullName(StringRawBuffer, &packageFamilyNameLength, packageFamilyName);
      if ( !v21 )
      {
        UserSidForSession = EnsurePackageFamilyIsRegisteredForSessionUserBeforeActivationOfClass(
                              this,
                              a2,
                              v38,
                              packageFamilyName,
                              a5,
                              v6,
                              a6);
        if ( UserSidForSession >= 0 )
        {
          if ( string )
            WindowsDeleteString(string);
          if ( v34 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          goto LABEL_22;
        }
        v23 = 558;
        goto LABEL_30;
      }
      UserSidForSession = wil::details::in1diag3::Return_Win32(
                            retaddr,
                            (void *)0x22B,
                            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                            (const char *)v21,
                            v28);
      if ( string )
        WindowsDeleteString(string);
    }
    if ( !v34 )
      goto LABEL_35;
    v24 = *(void (**)(void))(*(_QWORD *)v34 + 16LL);
LABEL_34:
    v24();
LABEL_35:
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    goto LABEL_39;
  }
LABEL_22:
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return 0;
}

```

## disassembly

```asm
0x180053038  push    rbp
0x18005303a  push    rbx
0x18005303b  push    rsi
0x18005303c  push    rdi
0x18005303d  push    r12
0x18005303f  push    r13
0x180053041  push    r14
0x180053043  push    r15
0x180053045  lea     rbp, [rsp-48h]
0x18005304a  sub     rsp, 148h
0x180053051  mov     rax, cs:__security_cookie
0x180053058  xor     rax, rsp
0x18005305b  mov     [rbp+80h+var_50], rax
0x18005305f  mov     r12, [rbp+80h+arg_28]
0x180053066  xor     esi, esi
0x180053068  mov     [rbp+80h+var_FC], r8d
0x18005306c  mov     rdi, r9
0x18005306f  mov     r13, rdx
0x180053072  mov     r15, rcx
0x180053075  mov     [r12], esi
0x180053079  test    rcx, rcx
0x18005307c  jz      loc_1800534ED
0x180053082  mov     rax, [r9]
0x180053085  lea     r8, [rsp+180h+var_140]
0x18005308a  lea     rdx, _GUID_430be197_0244_2f7b_80fd_c7c473983ad0
0x180053091  mov     [rsp+180h+var_140], rsi
0x180053096  mov     rcx, r9
0x180053099  mov     rax, [rax]
0x18005309c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530a1  mov     ebx, eax
0x1800530a3  test    eax, eax
0x1800530a5  js      loc_18005346E
0x1800530ab  mov     rcx, [rsp+180h+var_140]
0x1800530b0  lea     rdx, [rsp+180h+var_128]
0x1800530b5  mov     [rsp+180h+var_128], esi
0x1800530b9  mov     rax, [rcx]
0x1800530bc  mov     rax, [rax+18h]
0x1800530c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530c5  mov     ebx, eax
0x1800530c7  test    eax, eax
0x1800530c9  js      loc_1800534A3
0x1800530cf  cmp     [rsp+180h+var_128], 2
0x1800530d4  jnz     loc_18005351C
0x1800530da  mov     rax, [rdi]
0x1800530dd  lea     r8, [rsp+180h+var_130]
0x1800530e2  lea     rdx, _GUID_000001e2_0000_0000_c000_000000000046
0x1800530e9  mov     [rsp+180h+var_130], rsi
0x1800530ee  mov     rcx, rdi
0x1800530f1  mov     rax, [rax]
0x1800530f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530f9  mov     ebx, eax
0x1800530fb  test    eax, eax
0x1800530fd  js      loc_180053551
0x180053103  mov     rcx, [rsp+180h+var_130]
0x180053108  lea     r8, [rsp+180h+var_138]
0x18005310d  mov     [rsp+180h+var_138], rsi
0x180053112  lea     rdx, _GUID_000001ed_0000_0000_c000_000000000046
0x180053119  mov     rax, [rcx]
0x18005311c  mov     rax, [rax+30h]
0x180053120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053125  mov     ebx, eax
0x180053127  test    eax, eax
0x180053129  js      loc_18005356E
0x18005312f  mov     rcx, [rsp+180h+var_138]
0x180053134  lea     rdx, [rsp+180h+var_110]
0x180053139  mov     [rsp+180h+var_110], esi
0x18005313d  mov     rax, [rcx]
0x180053140  mov     rax, [rax+28h]
0x180053144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053149  mov     ebx, eax
0x18005314b  test    eax, eax
0x18005314d  js      loc_180053575
0x180053153  cmp     [rsp+180h+var_110], 1
0x180053158  jz      loc_180053306
0x18005315e  call    cs:__imp_RtlIsMultiSessionSku
0x180053165  nop     dword ptr [rax+rax+00h]
0x18005316a  mov     r14d, [rbp+80h+arg_20]
0x180053171  test    al, al
0x180053173  jz      loc_1800531FC
0x180053179  mov     rcx, r15; this
0x18005317c  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x180053181  cmp     r14d, eax
0x180053184  jnz     loc_1800535B3
0x18005318a  lea     rax, [rsp+180h+pSid1]
0x18005318f  mov     [rsp+180h+pSid1], rsi
0x180053194  lea     rdx, [rbp+80h+var_F0]; void **
0x180053198  mov     [rbp+80h+var_F8], rax
0x18005319c  mov     ecx, r14d; unsigned int
0x18005319f  mov     [rbp+80h+var_F0], rsi
0x1800531a3  mov     [rbp+80h+var_E8], 1
0x1800531a7  call    ?GetUserSidForSession@@YAJKPEAPEAX@Z; GetUserSidForSession(ulong,void * *)
0x1800531ac  lea     rcx, [rbp+80h+var_F8]
0x1800531b0  mov     ebx, eax
0x1800531b2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800531b7  test    ebx, ebx
0x1800531b9  js      loc_1800534AA
0x1800531bf  mov     rcx, [rsp+180h+pSid1]; pSid1
0x1800531c4  lea     rdx, [r15+9Ch]; pSid2
0x1800531cb  call    cs:__imp_EqualSid
0x1800531d2  nop     dword ptr [rax+rax+00h]
0x1800531d7  mov     r8, [rsp+180h+pSid1]; lpMem
0x1800531dc  test    eax, eax
0x1800531de  setz    sil
0x1800531e2  test    r8, r8
0x1800531e5  jz      short loc_1800531FC
0x1800531e7  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800531ee  xor     edx, edx; dwFlags
0x1800531f0  call    cs:__imp_HeapFree
0x1800531f7  nop     dword ptr [rax+rax+00h]
0x1800531fc  mov     rax, [rdi]
0x1800531ff  lea     r8, [rsp+180h+var_118]
0x180053204  lea     rdx, _GUID_0318b242_d086_4de9_b10c_2824a6ca1019
0x18005320b  mov     [rsp+180h+var_118], 0
0x180053214  mov     rcx, rdi
0x180053217  mov     rax, [rax]
0x18005321a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005321f  mov     ebx, eax
0x180053221  test    eax, eax
0x180053223  js      loc_180053451
0x180053229  mov     rdi, [rsp+180h+var_118]
0x18005322e  lea     rcx, [rsp+180h+string]
0x180053233  mov     [rsp+180h+string], 0
0x18005323c  xor     edx, edx
0x18005323e  mov     rax, [rdi]
0x180053241  mov     rbx, [rax+50h]
0x180053245  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005324a  lea     rdx, [rsp+180h+string]
0x18005324f  mov     rcx, rdi
0x180053252  mov     rax, rbx
0x180053255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005325a  mov     ebx, eax
0x18005325c  test    eax, eax
0x18005325e  js      loc_180053512
0x180053264  xor     edx, edx; Val
0x180053266  lea     rcx, [rbp+80h+packageFamilyName]; void *
0x18005326a  mov     r8d, 82h; Size
0x180053270  call    memset_0
0x180053275  mov     rcx, [rsp+180h+string]; string
0x18005327a  xor     edx, edx; length
0x18005327c  mov     [rbp+80h+packageFamilyNameLength], 41h ; 'A'
0x180053283  call    cs:__imp_WindowsGetStringRawBuffer
0x18005328a  nop     dword ptr [rax+rax+00h]
0x18005328f  mov     rcx, rax; packageFullName
0x180053292  lea     r8, [rbp+80h+packageFamilyName]; packageFamilyName
0x180053296  lea     rdx, [rbp+80h+packageFamilyNameLength]; packageFamilyNameLength
0x18005329a  call    cs:__imp_PackageFamilyNameFromFullName
0x1800532a1  nop     dword ptr [rax+rax+00h]
0x1800532a6  test    eax, eax
0x1800532a8  jnz     loc_1800533F3
0x1800532ae  mov     r8d, [rbp+80h+var_FC]; unsigned int
0x1800532b2  lea     r9, [rbp+80h+packageFamilyName]; unsigned __int16 *
0x1800532b6  mov     [rsp+180h+var_150], r12; int *
0x1800532bb  mov     rdx, r13; struct _GUID *
0x1800532be  mov     [rsp+180h+var_158], sil; bool
0x1800532c3  mov     rcx, r15; this
0x1800532c6  mov     [rsp+180h+var_160], r14d; int
0x1800532cb  call    ?EnsurePackageFamilyIsRegisteredForSessionUserBeforeActivationOfClass@@YAJPEAVCToken@@AEBU_GUID@@KPEBGK_NPEAH@Z; EnsurePackageFamilyIsRegisteredForSessionUserBeforeActivationOfClass(CToken *,_GUID const &,ulong,ushort const *,ulong,bool,int *)
0x1800532d0  mov     ebx, eax
0x1800532d2  test    eax, eax
0x1800532d4  js      loc_18005336B
0x1800532da  mov     rcx, [rsp+180h+string]; string
0x1800532df  test    rcx, rcx
0x1800532e2  jz      short loc_1800532F0
0x1800532e4  call    cs:__imp_WindowsDeleteString
0x1800532eb  nop     dword ptr [rax+rax+00h]
0x1800532f0  mov     rcx, [rsp+180h+var_118]
0x1800532f5  test    rcx, rcx
0x1800532f8  jz      short loc_180053306
0x1800532fa  mov     rax, [rcx]
0x1800532fd  mov     rax, [rax+10h]
0x180053301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053306  mov     rcx, [rsp+180h+var_138]
0x18005330b  test    rcx, rcx
0x18005330e  jz      short loc_18005331C
0x180053310  mov     rax, [rcx]
0x180053313  mov     rax, [rax+10h]
0x180053317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005331c  mov     rcx, [rsp+180h+var_130]
0x180053321  test    rcx, rcx
0x180053324  jz      short loc_180053332
0x180053326  mov     rax, [rcx]
0x180053329  mov     rax, [rax+10h]
0x18005332d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053332  mov     rcx, [rsp+180h+var_140]
0x180053337  test    rcx, rcx
0x18005333a  jz      short loc_180053348
0x18005333c  mov     rax, [rcx]
0x18005333f  mov     rax, [rax+10h]
0x180053343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053348  xor     eax, eax
0x18005334a  mov     rcx, [rbp+80h+var_50]
0x18005334e  xor     rcx, rsp; StackCookie
0x180053351  call    __security_check_cookie
0x180053356  add     rsp, 148h
0x18005335d  pop     r15
0x18005335f  pop     r14
0x180053361  pop     r13
0x180053363  pop     r12
0x180053365  pop     rdi
0x180053366  pop     rsi
0x180053367  pop     rbx
0x180053368  pop     rbp
0x180053369  retn
0x18005336b  mov     edx, 22Eh; void *
0x180053370  mov     rcx, [rbp+88h]; this
0x180053377  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18005337e  mov     r9d, ebx; char *
0x180053381  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053386  mov     rcx, [rsp+180h+string]; string
0x18005338b  test    rcx, rcx
0x18005338e  jnz     loc_180053440
0x180053394  mov     rcx, [rsp+180h+var_118]
0x180053399  test    rcx, rcx
0x18005339c  jz      short loc_1800533AA
0x18005339e  mov     rax, [rcx]
0x1800533a1  mov     rax, [rax+10h]
0x1800533a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533aa  mov     rcx, [rsp+180h+var_138]
0x1800533af  test    rcx, rcx
0x1800533b2  jz      short loc_1800533C0
0x1800533b4  mov     rax, [rcx]
0x1800533b7  mov     rax, [rax+10h]
0x1800533bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533c0  mov     rcx, [rsp+180h+var_130]
0x1800533c5  test    rcx, rcx
0x1800533c8  jz      short loc_1800533D6
0x1800533ca  mov     rax, [rcx]
0x1800533cd  mov     rax, [rax+10h]
0x1800533d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533d6  mov     rcx, [rsp+180h+var_140]
0x1800533db  test    rcx, rcx
0x1800533de  jz      short loc_1800533EC
0x1800533e0  mov     rax, [rcx]
0x1800533e3  mov     rax, [rax+10h]
0x1800533e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533ec  mov     eax, ebx
0x1800533ee  jmp     loc_18005334A
0x1800533f3  mov     rcx, [rbp+88h]; this
0x1800533fa  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x180053401  mov     r9d, eax; char *
0x180053404  mov     edx, 22Bh; void *
0x180053409  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005340e  mov     rcx, [rsp+180h+string]; string
0x180053413  mov     ebx, eax
0x180053415  test    rcx, rcx
0x180053418  jz      short loc_180053426
0x18005341a  call    cs:__imp_WindowsDeleteString
0x180053421  nop     dword ptr [rax+rax+00h]
0x180053426  mov     rcx, [rsp+180h+var_118]
0x18005342b  test    rcx, rcx
0x18005342e  jz      loc_1800533AA
0x180053434  mov     rdx, [rcx]
0x180053437  mov     rax, [rdx+10h]
0x18005343b  jmp     loc_1800533A5
0x180053440  call    cs:__imp_WindowsDeleteString
0x180053447  nop     dword ptr [rax+rax+00h]
0x18005344c  jmp     loc_180053394
0x180053451  mov     rcx, [rbp+88h]; this
0x180053458  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18005345f  mov     r9d, ebx; char *
0x180053462  mov     edx, 223h; void *
0x180053467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005346c  jmp     short loc_180053426
0x18005346e  mov     edx, 1EFh; void *
0x180053473  mov     rcx, [rbp+88h]; this
0x18005347a  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x180053481  mov     r9d, ebx; char *
0x180053484  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053489  mov     rcx, [rsp+180h+var_140]
0x18005348e  test    rcx, rcx
0x180053491  jz      loc_1800533EC
0x180053497  mov     rdx, [rcx]
0x18005349a  mov     rax, [rdx+10h]
0x18005349e  jmp     loc_1800533E7
0x1800534a3  mov     edx, 1F2h
0x1800534a8  jmp     short loc_180053473
0x1800534aa  mov     rcx, [rbp+88h]; this
0x1800534b1  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x1800534b8  mov     r9d, ebx; char *
0x1800534bb  mov     edx, 219h; void *
0x1800534c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800534c5  mov     r8, [rsp+180h+pSid1]; lpMem
0x1800534ca  test    r8, r8
0x1800534cd  jz      loc_1800533AA
0x1800534d3  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800534da  xor     edx, edx; dwFlags
0x1800534dc  call    cs:__imp_HeapFree
0x1800534e3  nop     dword ptr [rax+rax+00h]
0x1800534e8  jmp     loc_1800533AA
0x1800534ed  mov     rcx, [rbp+88h]; this
0x1800534f4  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x1800534fb  mov     ebx, 8000FFFFh
0x180053500  mov     edx, 1ECh; void *
0x180053505  mov     r9d, ebx; char *
0x180053508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005350d  jmp     loc_1800533EC
0x180053512  mov     edx, 226h
0x180053517  jmp     loc_180053370
0x18005351c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180053521  cmp     [rsp+180h+var_128], 2
  ... truncated ...
```

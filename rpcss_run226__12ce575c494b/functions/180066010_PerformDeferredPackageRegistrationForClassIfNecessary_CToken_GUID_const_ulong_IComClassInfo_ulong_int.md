# PerformDeferredPackageRegistrationForClassIfNecessary(CToken *,_GUID const &,ulong,IComClassInfo *,ulong,int *)

- ea: `0x180066010`
- end: `0x1800665dd`
- name: `?PerformDeferredPackageRegistrationForClassIfNecessary@@YAJPEAVCToken@@AEBU_GUID@@KPEAUIComClassInfo@@KPEAH@Z`
- size: `1485`
- prototype: `__int64 __usercall@<rax>(struct CToken *this@<rcx>, const struct _GUID *@<rdx>, unsigned int@<r8d>, struct IComClassInfo *@<r9>, unsigned int, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800899b0`

## callees

- `0x180003064`
- `0x180025730`
- `0x18002ba28`
- `0x18002f8cc`
- `0x180066010`
- `0x1800665e4`
- `0x180066748`
- `0x1800667b0`
- `0x18008e98c`
- `0x1800b27e0`
- `0x1800b3128`
- `0x18010b010`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x180066137`
- `ntdll!RtlIsMultiSessionSku` at `0x180066137`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800661bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800664ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800661bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800664ca`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006619f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006619f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006628a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800663cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800663da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006651f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006628a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800663cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800663da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006651f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066238`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x180066249`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x180066249`

## string_xrefs

- `0x180066311`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180066399`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800663e9`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180066468`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18006649f`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800664dc`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180066501`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x180066556`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x18006657b`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`
- `0x1800665a4`: `onecore\com\combase\rpcss\olescm\dscmif.cxx`

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
  __int64 (__fastcall **v10)(struct IComClassInfo *, GUID *, __int64 *); // rax
  unsigned int UserSidForSession; // ebx
  __int64 v12; // rcx
  __int64 (__fastcall **v13)(struct IComClassInfo *, GUID *, __int64 *); // rax
  int v14; // eax
  int v15; // eax
  bool v16; // bl
  __int64 (__fastcall **v17)(struct IComClassInfo *, GUID *, __int64 *); // rax
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  const WCHAR *StringRawBuffer; // rax
  unsigned int v22; // eax
  int IsRegisteredForSessionUserBeforeActivationOfClass; // eax
  void (*v25)(void); // rax
  void (*v26)(void); // rax
  void (*v27)(void); // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  unsigned int v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  int v38; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid1; // [rsp+78h] [rbp-88h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+80h] [rbp-80h] BYREF
  PSID *p_pSid1; // [rsp+88h] [rbp-78h] BYREF
  void *v42; // [rsp+90h] [rbp-70h] BYREF
  char v43; // [rsp+98h] [rbp-68h]
  WCHAR packageFamilyName[72]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  *a6 = 0;
  if ( !this )
  {
    UserSidForSession = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EC,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)0x8000FFFFLL,
      v30);
    return UserSidForSession;
  }
  v10 = *a4;
  v32 = 0;
  UserSidForSession = (*v10)((struct IComClassInfo *)a4, &GUID_430be197_0244_2f7b_80fd_c7c473983ad0, &v32);
  if ( (UserSidForSession & 0x80000000) != 0 )
  {
    v28 = 495;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)UserSidForSession,
      v30);
    if ( !v32 )
      return UserSidForSession;
    v26 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
    goto LABEL_40;
  }
  v35 = 0;
  UserSidForSession = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 24LL))(v32, &v35);
  if ( (UserSidForSession & 0x80000000) != 0 )
  {
    v28 = 498;
    goto LABEL_57;
  }
  if ( v35 != 2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v12);
    if ( v35 != 2 )
    {
      UserSidForSession = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F5,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
        (const char *)0x8000FFFFLL,
        v30);
LABEL_38:
      if ( !v32 )
        return UserSidForSession;
      v26 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
LABEL_40:
      v26();
      return UserSidForSession;
    }
  }
  v13 = *a4;
  v34 = 0;
  v14 = (*v13)((struct IComClassInfo *)a4, &GUID_000001e2_0000_0000_c000_000000000046, &v34);
  UserSidForSession = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v14,
      v30);
LABEL_73:
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v34);
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v32);
    return UserSidForSession;
  }
  v33 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v34 + 48LL))(
          v34,
          &GUID_000001ed_0000_0000_c000_000000000046,
          &v33);
  UserSidForSession = v15;
  if ( v15 < 0 )
  {
    v29 = 507;
LABEL_72:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v15,
      v30);
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v33);
    goto LABEL_73;
  }
  v38 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 40LL))(v33, &v38);
  UserSidForSession = v15;
  if ( v15 < 0 )
  {
    v29 = 514;
    goto LABEL_72;
  }
  if ( v38 == 1 )
  {
LABEL_22:
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    return 0;
  }
  v16 = 0;
  if ( (unsigned __int8)RtlIsMultiSessionSku() )
  {
    if ( a5 == CToken::GetSessionId(this) )
    {
      pSid1 = 0;
      p_pSid1 = &pSid1;
      v42 = 0;
      v43 = 1;
      UserSidForSession = GetUserSidForSession(a5, &v42);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_pSid1);
      if ( (UserSidForSession & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x219,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)UserSidForSession,
          v30);
        if ( pSid1 )
          HeapFree(g_hHeap, 0, pSid1);
        goto LABEL_34;
      }
      v16 = !EqualSid(pSid1, (char *)this + 156);
      if ( pSid1 )
        HeapFree(g_hHeap, 0, pSid1);
    }
    else
    {
      v16 = 1;
    }
  }
  v17 = *a4;
  v36 = 0;
  v18 = (*v17)((struct IComClassInfo *)a4, &GUID_0318b242_d086_4de9_b10c_2824a6ca1019, &v36);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v18,
      v30);
    if ( v36 )
    {
      v27 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
LABEL_48:
      v27();
    }
  }
  else
  {
    string = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 80LL))(v36, &string);
    v19 = v20;
    if ( v20 >= 0 )
    {
      memset_0(packageFamilyName, 0, 0x82u);
      packageFamilyNameLength = 65;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v22 = PackageFamilyNameFromFullName(StringRawBuffer, &packageFamilyNameLength, packageFamilyName);
      if ( v22 )
      {
        UserSidForSession = wil::details::in1diag3::Return_Win32(
                              retaddr,
                              (void *)0x22B,
                              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
                              (const char *)v22,
                              v30);
        if ( string )
          WindowsDeleteString(string);
        if ( !v36 )
          goto LABEL_34;
        v25 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
      }
      else
      {
        IsRegisteredForSessionUserBeforeActivationOfClass = EnsurePackageFamilyIsRegisteredForSessionUserBeforeActivationOfClass(
                                                              this,
                                                              a2,
                                                              a3,
                                                              packageFamilyName,
                                                              a5,
                                                              v16,
                                                              a6);
        UserSidForSession = IsRegisteredForSessionUserBeforeActivationOfClass;
        if ( IsRegisteredForSessionUserBeforeActivationOfClass >= 0 )
        {
          if ( string )
            WindowsDeleteString(string);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          goto LABEL_22;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22E,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
          (const char *)(unsigned int)IsRegisteredForSessionUserBeforeActivationOfClass,
          v31);
        if ( string )
          WindowsDeleteString(string);
        if ( !v36 )
        {
LABEL_34:
          if ( v33 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          if ( v34 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          goto LABEL_38;
        }
        v25 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
      }
      v25();
      goto LABEL_34;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x226,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\dscmif.cxx",
      (const char *)(unsigned int)v20,
      v30);
    if ( string )
      WindowsDeleteString(string);
    if ( v36 )
    {
      v27 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
      goto LABEL_48;
    }
  }
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  return v19;
}

```

## disassembly

```asm
0x180066010  push    rbp
0x180066012  push    rbx
0x180066013  push    rsi
0x180066014  push    rdi
0x180066015  push    r12
0x180066017  push    r13
0x180066019  push    r14
0x18006601b  push    r15
0x18006601d  lea     rbp, [rsp-48h]
0x180066022  sub     rsp, 148h
0x180066029  mov     rax, cs:__security_cookie
0x180066030  xor     rax, rsp
0x180066033  mov     [rbp+80h+var_50], rax
0x180066037  mov     r15, [rbp+80h+arg_28]
0x18006603e  xor     esi, esi
0x180066040  mov     rdi, r9
0x180066043  mov     r13d, r8d
0x180066046  mov     r12, rdx
0x180066049  mov     r14, rcx
0x18006604c  mov     [r15], esi
0x18006604f  test    rcx, rcx
0x180066052  jz      loc_1800664D5
0x180066058  mov     rax, [r9]
0x18006605b  lea     r8, [rsp+180h+var_140]
0x180066060  lea     rdx, _GUID_430be197_0244_2f7b_80fd_c7c473983ad0
0x180066067  mov     [rsp+180h+var_140], rsi
0x18006606c  mov     rcx, r9
0x18006606f  mov     rax, [rax]
0x180066072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066077  mov     ebx, eax
0x180066079  test    eax, eax
0x18006607b  js      loc_18006645C
0x180066081  mov     rcx, [rsp+180h+var_140]
0x180066086  lea     rdx, [rsp+180h+var_128]
0x18006608b  mov     [rsp+180h+var_128], esi
0x18006608f  mov     rax, [rcx]
0x180066092  mov     rax, [rax+18h]
0x180066096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006609b  mov     ebx, eax
0x18006609d  test    eax, eax
0x18006609f  js      loc_180066491
0x1800660a5  cmp     [rsp+180h+var_128], 2
0x1800660aa  jnz     loc_18006653F
0x1800660b0  mov     rax, [rdi]
0x1800660b3  lea     r8, [rsp+180h+var_130]
0x1800660b8  lea     rdx, _GUID_000001e2_0000_0000_c000_000000000046
0x1800660bf  mov     [rsp+180h+var_130], rsi
0x1800660c4  mov     rcx, rdi
0x1800660c7  mov     rax, [rax]
0x1800660ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660cf  mov     ebx, eax
0x1800660d1  test    eax, eax
0x1800660d3  js      loc_180066574
0x1800660d9  mov     rcx, [rsp+180h+var_130]
0x1800660de  lea     r8, [rsp+180h+var_138]
0x1800660e3  mov     [rsp+180h+var_138], rsi
0x1800660e8  lea     rdx, _GUID_000001ed_0000_0000_c000_000000000046
0x1800660ef  mov     rax, [rcx]
0x1800660f2  mov     rax, [rax+30h]
0x1800660f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660fb  mov     ebx, eax
0x1800660fd  test    eax, eax
0x1800660ff  js      loc_180066591
0x180066105  mov     rcx, [rsp+180h+var_138]
0x18006610a  lea     rdx, [rsp+180h+var_110]
0x18006610f  mov     [rsp+180h+var_110], esi
0x180066113  mov     rax, [rcx]
0x180066116  mov     rax, [rax+28h]
0x18006611a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006611f  mov     ebx, eax
0x180066121  test    eax, eax
0x180066123  js      loc_180066598
0x180066129  cmp     [rsp+180h+var_110], 1
0x18006612e  jz      loc_1800662A6
0x180066134  mov     bl, sil
0x180066137  call    cs:__imp_RtlIsMultiSessionSku
0x18006613d  mov     esi, [rbp+80h+arg_20]
0x180066143  test    al, al
0x180066145  jz      short loc_1800661C3
0x180066147  mov     rcx, r14; this
0x18006614a  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x18006614f  cmp     esi, eax
0x180066151  jnz     loc_1800665D6
0x180066157  lea     rax, [rsp+180h+pSid1]
0x18006615c  mov     [rsp+180h+pSid1], 0
0x180066165  lea     rdx, [rbp+80h+var_F0]; void **
0x180066169  mov     [rbp+80h+var_F8], rax
0x18006616d  mov     ecx, esi; unsigned int
0x18006616f  mov     [rbp+80h+var_F0], 0
0x180066177  mov     [rbp+80h+var_E8], 1
0x18006617b  call    ?GetUserSidForSession@@YAJKPEAPEAX@Z; GetUserSidForSession(ulong,void * *)
0x180066180  lea     rcx, [rbp+80h+var_F8]
0x180066184  mov     ebx, eax
0x180066186  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18006618b  test    ebx, ebx
0x18006618d  js      loc_180066498
0x180066193  mov     rcx, [rsp+180h+pSid1]; pSid1
0x180066198  lea     rdx, [r14+9Ch]; pSid2
0x18006619f  call    cs:__imp_EqualSid
0x1800661a5  mov     r8, [rsp+180h+pSid1]; lpMem
0x1800661aa  test    eax, eax
0x1800661ac  setz    bl
0x1800661af  test    r8, r8
0x1800661b2  jz      short loc_1800661C3
0x1800661b4  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800661bb  xor     edx, edx; dwFlags
0x1800661bd  call    cs:__imp_HeapFree
0x1800661c3  mov     rax, [rdi]
0x1800661c6  lea     r8, [rsp+180h+var_120]
0x1800661cb  lea     rdx, _GUID_0318b242_d086_4de9_b10c_2824a6ca1019
0x1800661d2  mov     [rsp+180h+var_120], 0
0x1800661db  mov     rcx, rdi
0x1800661de  mov     rax, [rax]
0x1800661e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661e6  mov     edi, eax
0x1800661e8  test    eax, eax
0x1800661ea  js      loc_1800663E2
0x1800661f0  mov     rcx, [rsp+180h+var_120]
0x1800661f5  lea     rdx, [rsp+180h+string]
0x1800661fa  mov     [rsp+180h+string], 0
0x180066203  mov     rax, [rcx]
0x180066206  mov     rax, [rax+50h]
0x18006620a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006620f  mov     edi, eax
0x180066211  test    eax, eax
0x180066213  js      loc_1800664FA
0x180066219  xor     edx, edx; Val
0x18006621b  lea     rcx, [rbp+80h+packageFamilyName]; void *
0x18006621f  mov     r8d, 82h; Size
0x180066225  call    memset_0
0x18006622a  mov     rcx, [rsp+180h+string]; string
0x18006622f  xor     edx, edx; length
0x180066231  mov     [rbp+80h+packageFamilyNameLength], 41h ; 'A'
0x180066238  call    cs:__imp_WindowsGetStringRawBuffer
0x18006623e  mov     rcx, rax; packageFullName
0x180066241  lea     r8, [rbp+80h+packageFamilyName]; packageFamilyName
0x180066245  lea     rdx, [rbp+80h+packageFamilyNameLength]; packageFamilyNameLength
0x180066249  call    cs:__imp_PackageFamilyNameFromFullName
0x18006624f  test    eax, eax
0x180066251  jnz     loc_180066392
0x180066257  mov     [rsp+180h+var_150], r15; int *
0x18006625c  lea     r9, [rbp+80h+packageFamilyName]; unsigned __int16 *
0x180066260  mov     [rsp+180h+var_158], bl; bool
0x180066264  mov     r8d, r13d; unsigned int
0x180066267  mov     rdx, r12; struct _GUID *
0x18006626a  mov     [rsp+180h+var_160], esi; int
0x18006626e  mov     rcx, r14; this
0x180066271  call    ?EnsurePackageFamilyIsRegisteredForSessionUserBeforeActivationOfClass@@YAJPEAVCToken@@AEBU_GUID@@KPEBGK_NPEAH@Z; EnsurePackageFamilyIsRegisteredForSessionUserBeforeActivationOfClass(CToken *,_GUID const &,ulong,ushort const *,ulong,bool,int *)
0x180066276  mov     ebx, eax
0x180066278  test    eax, eax
0x18006627a  js      loc_18006630A
0x180066280  mov     rcx, [rsp+180h+string]; string
0x180066285  test    rcx, rcx
0x180066288  jz      short loc_180066290
0x18006628a  call    cs:__imp_WindowsDeleteString
0x180066290  mov     rcx, [rsp+180h+var_120]
0x180066295  test    rcx, rcx
0x180066298  jz      short loc_1800662A6
0x18006629a  mov     rax, [rcx]
0x18006629d  mov     rax, [rax+10h]
0x1800662a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662a6  mov     rcx, [rsp+180h+var_138]
0x1800662ab  test    rcx, rcx
0x1800662ae  jz      short loc_1800662BC
0x1800662b0  mov     rax, [rcx]
0x1800662b3  mov     rax, [rax+10h]
0x1800662b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662bc  mov     rcx, [rsp+180h+var_130]
0x1800662c1  test    rcx, rcx
0x1800662c4  jz      short loc_1800662D2
0x1800662c6  mov     rax, [rcx]
0x1800662c9  mov     rax, [rax+10h]
0x1800662cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662d2  mov     rcx, [rsp+180h+var_140]
0x1800662d7  test    rcx, rcx
0x1800662da  jz      short loc_1800662E8
0x1800662dc  mov     rax, [rcx]
0x1800662df  mov     rax, [rax+10h]
0x1800662e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662e8  xor     eax, eax
0x1800662ea  mov     rcx, [rbp+80h+var_50]
0x1800662ee  xor     rcx, rsp; StackCookie
0x1800662f1  call    __security_check_cookie
0x1800662f6  add     rsp, 148h
0x1800662fd  pop     r15
0x1800662ff  pop     r14
0x180066301  pop     r13
0x180066303  pop     r12
0x180066305  pop     rdi
0x180066306  pop     rsi
0x180066307  pop     rbx
0x180066308  pop     rbp
0x180066309  retn
0x18006630a  mov     rcx, [rbp+88h]; this
0x180066311  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x180066318  mov     r9d, ebx; char *
0x18006631b  mov     edx, 22Eh; void *
0x180066320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066325  mov     rcx, [rsp+180h+string]; string
0x18006632a  test    rcx, rcx
0x18006632d  jnz     loc_1800663CF
0x180066333  mov     rcx, [rsp+180h+var_120]
0x180066338  test    rcx, rcx
0x18006633b  jz      short loc_180066349
0x18006633d  mov     rax, [rcx]
0x180066340  mov     rax, [rax+10h]
0x180066344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066349  mov     rcx, [rsp+180h+var_138]
0x18006634e  test    rcx, rcx
0x180066351  jz      short loc_18006635F
0x180066353  mov     rax, [rcx]
0x180066356  mov     rax, [rax+10h]
0x18006635a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006635f  mov     rcx, [rsp+180h+var_130]
0x180066364  test    rcx, rcx
0x180066367  jz      short loc_180066375
0x180066369  mov     rax, [rcx]
0x18006636c  mov     rax, [rax+10h]
0x180066370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066375  mov     rcx, [rsp+180h+var_140]
0x18006637a  test    rcx, rcx
0x18006637d  jz      short loc_18006638B
0x18006637f  mov     rax, [rcx]
0x180066382  mov     rax, [rax+10h]
0x180066386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006638b  mov     eax, ebx
0x18006638d  jmp     loc_1800662EA
0x180066392  mov     rcx, [rbp+88h]; this
0x180066399  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x1800663a0  mov     r9d, eax; char *
0x1800663a3  mov     edx, 22Bh; void *
0x1800663a8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800663ad  mov     rcx, [rsp+180h+string]; string
0x1800663b2  mov     ebx, eax
0x1800663b4  test    rcx, rcx
0x1800663b7  jnz     short loc_1800663DA
0x1800663b9  mov     rcx, [rsp+180h+var_120]
0x1800663be  test    rcx, rcx
0x1800663c1  jz      short loc_180066349
0x1800663c3  mov     rdx, [rcx]
0x1800663c6  mov     rax, [rdx+10h]
0x1800663ca  jmp     loc_180066344
0x1800663cf  call    cs:__imp_WindowsDeleteString
0x1800663d5  jmp     loc_180066333
0x1800663da  call    cs:__imp_WindowsDeleteString
0x1800663e0  jmp     short loc_1800663B9
0x1800663e2  mov     rcx, [rbp+88h]; this
0x1800663e9  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x1800663f0  mov     r9d, edi; char *
0x1800663f3  mov     edx, 223h; void *
0x1800663f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800663fd  mov     rcx, [rsp+180h+var_120]
0x180066402  test    rcx, rcx
0x180066405  jz      short loc_180066413
0x180066407  mov     rdx, [rcx]
0x18006640a  mov     rax, [rdx+10h]
0x18006640e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066413  mov     rcx, [rsp+180h+var_138]
0x180066418  test    rcx, rcx
0x18006641b  jz      short loc_180066429
0x18006641d  mov     rax, [rcx]
0x180066420  mov     rax, [rax+10h]
0x180066424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066429  mov     rcx, [rsp+180h+var_130]
0x18006642e  test    rcx, rcx
0x180066431  jz      short loc_18006643F
0x180066433  mov     rax, [rcx]
0x180066436  mov     rax, [rax+10h]
0x18006643a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006643f  mov     rcx, [rsp+180h+var_140]
0x180066444  test    rcx, rcx
0x180066447  jz      short loc_180066455
0x180066449  mov     rax, [rcx]
0x18006644c  mov     rax, [rax+10h]
0x180066450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066455  mov     eax, edi
0x180066457  jmp     loc_1800662EA
0x18006645c  mov     edx, 1EFh; void *
0x180066461  mov     rcx, [rbp+88h]; this
0x180066468  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x18006646f  mov     r9d, ebx; char *
0x180066472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066477  mov     rcx, [rsp+180h+var_140]
0x18006647c  test    rcx, rcx
0x18006647f  jz      loc_18006638B
0x180066485  mov     rdx, [rcx]
0x180066488  mov     rax, [rdx+10h]
0x18006648c  jmp     loc_180066386
0x180066491  mov     edx, 1F2h
0x180066496  jmp     short loc_180066461
0x180066498  mov     rcx, [rbp+88h]; this
0x18006649f  lea     r8, aOnecoreComComb_17; "onecore\\com\\combase\\rpcss\\olescm\\d"...
0x1800664a6  mov     r9d, ebx; char *
0x1800664a9  mov     edx, 219h; void *
0x1800664ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800664b3  mov     r8, [rsp+180h+pSid1]; lpMem
0x1800664b8  test    r8, r8
0x1800664bb  jz      loc_180066349
0x1800664c1  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800664c8  xor     edx, edx; dwFlags
  ... truncated ...
```

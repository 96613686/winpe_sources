# AppEndpoint::UpdateContainerSidIfApplicable(INotificationHandler *)

- ea: `0x1800186a4`
- end: `0x1800189f2`
- name: `?UpdateContainerSidIfApplicable@AppEndpoint@@AEAAXPEAUINotificationHandler@@@Z`
- size: `846`
- prototype: `void __fastcall(AppEndpoint *__hidden this, struct INotificationHandler *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004d8c4`
- `0x180052620`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x180011618`
- `0x180013360`
- `0x180017a6c`
- `0x180018238`
- `0x180018380`
- `0x1800186a4`
- `0x1800189f8`
- `0x1800276d8`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187fb`
- `msvcp_win!_Cnd_signal` at `0x180018985`
- `msvcp_win!_Cnd_signal` at `0x180018985`
- `msvcp_win!_Mtx_unlock` at `0x180018976`
- `msvcp_win!_Mtx_unlock` at `0x180018976`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall AppEndpoint::UpdateContainerSidIfApplicable(AppEndpoint *this, struct INotificationHandler *a2)
{
  int v4; // eax
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rax
  size_t v8; // r8
  const wchar_t *v9; // rcx
  unsigned __int64 v10; // rdx
  __int64 v11; // rbx
  int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // [rsp+20h] [rbp-50h] BYREF
  __int64 v19; // [rsp+28h] [rbp-48h] BYREF
  wchar_t *S2; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-38h] BYREF
  wchar_t *S1[2]; // [rsp+48h] [rbp-28h] BYREF
  size_t N; // [rsp+58h] [rbp-18h]
  unsigned __int64 v24; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  pv[0] = 0;
  v4 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 24LL))(a2, pv);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFE8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
      (const char *)(unsigned int)v4,
      v18);
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_40049089>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_40049089>::GetImpl'::`2'::impl,
    v5);
  S2 = 0;
  v6 = (*(__int64 (__fastcall **)(struct INotificationHandler *, wchar_t **))(*(_QWORD *)a2 + 104LL))(a2, &S2);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFED,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
      (const char *)(unsigned int)v6,
      v18);
  pv[1] = this;
  if ( this )
    (*(void (__fastcall **)(AppEndpoint *))(*(_QWORD *)this + 8LL))(this);
  GetContainerUserSid(S1, this);
  v7 = -1;
  do
    ++v7;
  while ( S2[v7] );
  v8 = N;
  v9 = (const wchar_t *)S1;
  if ( v24 > 7 )
    v9 = S1[0];
  if ( N != v7 || N && wmemcmp(v9, S2, N) )
  {
    Wns::NotificationPlatformHandle::Get((char *)this + 40, &v19);
    if ( !v19 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFF7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
        (const char *)0x803E0105LL,
        v18);
    v18 = 0;
    v11 = *(_QWORD *)(v19 + 184);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    v12 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v11 + 144))(
            *(_QWORD *)(v11 + 144),
            &GUID_145e48ec_626a_4302_9000_36e8172c6d29,
            &v18);
    v13 = v18;
    if ( v12 >= 0 && !v18 )
    {
      v12 = -2143420155;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x400,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)0x803E0105LL,
        0);
      v13 = v18;
    }
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFFA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
        (const char *)(unsigned int)v12,
        v18);
    v14 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v13 + 208LL))(v13, pv[0]);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFFD,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
        (const char *)(unsigned int)v14,
        v18);
    v15 = (*(__int64 (__fastcall **)(struct INotificationHandler *))(*(_QWORD *)a2 + 112LL))(a2);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFFF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
        (const char *)(unsigned int)v15,
        v18);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    v16 = _InterlockedExchange64(&v19, 0);
    if ( v16 )
    {
      std::_Mutex_base::lock((std::_Mutex_base *)v16);
      v17 = --*(_QWORD *)(v16 + 152);
      _Mtx_unlock((_Mtx_t)v16);
      if ( !v17 )
        _Cnd_signal((_Cnd_t)(v16 + 80));
    }
  }
  v10 = v24;
  if ( v24 > 7 )
    std::_Deallocate<16>(S1[0], 2 * v24 + 2);
  N = 0;
  v24 = 7;
  LOWORD(S1[0]) = 0;
  if ( this )
    (*(void (__fastcall **)(AppEndpoint *, unsigned __int64, size_t))(*(_QWORD *)this + 16LL))(this, v10, v8);
  if ( S2 )
    CoTaskMemFree(S2);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
}

```

## disassembly

```asm
0x1800186a4  mov     [rsp-18h+arg_10], rbx
0x1800186a9  mov     [rsp-18h+arg_18], rsi
0x1800186ae  push    rbp
0x1800186af  push    rdi
0x1800186b0  push    r14
0x1800186b2  mov     rbp, rsp
0x1800186b5  sub     rsp, 70h
0x1800186b9  mov     rax, cs:__security_cookie
0x1800186c0  xor     rax, rsp
0x1800186c3  mov     [rbp+var_8], rax
0x1800186c7  mov     rdi, rdx
0x1800186ca  mov     rsi, rcx
0x1800186cd  xor     r14d, r14d
0x1800186d0  mov     [rbp+pv], r14
0x1800186d4  mov     rax, [rdx]
0x1800186d7  lea     rdx, [rbp+pv]
0x1800186db  mov     rcx, rdi
0x1800186de  mov     rax, [rax+18h]
0x1800186e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186e7  mov     rcx, [rbp+18h]; this
0x1800186eb  test    eax, eax
0x1800186ed  js      loc_1800188BC
0x1800186f3  mov     dl, 1
0x1800186f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40049089@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40049089@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40049089> `wil::Feature<__WilFeatureTraits_Feature_40049089>::GetImpl(void)'::`2'::impl
0x1800186fc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_40049089@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40049089>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180018701  nop
0x180018702  mov     [rbp+S2], r14
0x180018706  mov     rax, [rdi]
0x180018709  lea     rdx, [rbp+S2]
0x18001870d  mov     rcx, rdi
0x180018710  mov     rax, [rax+68h]
0x180018714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018719  mov     rcx, [rbp+18h]; this
0x18001871d  test    eax, eax
0x18001871f  js      loc_1800188D1
0x180018725  mov     [rbp+var_30], rsi
0x180018729  test    rsi, rsi
0x18001872c  jz      short loc_18001873E
0x18001872e  mov     rax, [rsi]
0x180018731  mov     rcx, rsi
0x180018734  mov     rax, [rax+8]
0x180018738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001873d  nop
0x18001873e  mov     rdx, rsi
0x180018741  lea     rcx, [rbp+S1]
0x180018745  call    ?GetContainerUserSid@@YA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIUnknown@@@Z; GetContainerUserSid(IUnknown *)
0x18001874a  nop
0x18001874b  mov     rdx, [rbp+S2]; S2
0x18001874f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018753  inc     rax
0x180018756  cmp     [rdx+rax*2], r14w
0x18001875b  jnz     short loc_180018753
0x18001875d  mov     r8, [rbp+N]; N
0x180018761  lea     rcx, [rbp+S1]
0x180018765  cmp     [rbp+var_10], 7
0x18001876a  cmova   rcx, [rbp+S1]; S1
0x18001876f  cmp     r8, rax
0x180018772  jnz     loc_180018811
0x180018778  test    r8, r8
0x18001877b  jnz     loc_180018804
0x180018781  mov     rdx, [rbp+var_10]
0x180018785  cmp     rdx, 7
0x180018789  jbe     short loc_18001879C
0x18001878b  lea     rdx, ds:2[rdx*2]
0x180018793  mov     rcx, [rbp+S1]
0x180018797  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001879c  mov     [rbp+N], r14
0x1800187a0  mov     [rbp+var_10], 7
0x1800187a8  mov     word ptr [rbp+S1], r14w
0x1800187ad  test    rsi, rsi
0x1800187b0  jz      short loc_1800187C2
0x1800187b2  mov     rax, [rsi]
0x1800187b5  mov     rcx, rsi
0x1800187b8  mov     rax, [rax+10h]
0x1800187bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187c1  nop
0x1800187c2  mov     rcx, [rbp+S2]; pv
0x1800187c6  test    rcx, rcx
0x1800187c9  jnz     short loc_1800187FB
0x1800187cb  mov     rcx, [rbp+pv]; pv
0x1800187cf  test    rcx, rcx
0x1800187d2  jz      short loc_1800187DA
0x1800187d4  call    cs:__imp_CoTaskMemFree
0x1800187da  mov     rcx, [rbp+var_8]
0x1800187de  xor     rcx, rsp; StackCookie
0x1800187e1  call    __security_check_cookie
0x1800187e6  lea     r11, [rsp+70h+var_s0]
0x1800187eb  mov     rbx, [r11+30h]
0x1800187ef  mov     rsi, [r11+38h]
0x1800187f3  mov     rsp, r11
0x1800187f6  pop     r14
0x1800187f8  pop     rdi
0x1800187f9  pop     rbp
0x1800187fa  retn
0x1800187fb  call    cs:__imp_CoTaskMemFree
0x180018801  nop
0x180018802  jmp     short loc_1800187CB
0x180018804  call    wmemcmp
0x180018809  test    eax, eax
0x18001880b  jz      loc_180018781
0x180018811  lea     rcx, [rsi+28h]
0x180018815  lea     rdx, [rbp+var_48]
0x180018819  call    ?Get@NotificationPlatformHandle@Wns@@QEAA?AVNotificationPlatformPtr@2@XZ; Wns::NotificationPlatformHandle::Get(void)
0x18001881e  nop
0x18001881f  mov     rax, [rbp+var_48]
0x180018823  nop
0x180018824  mov     rcx, [rbp+18h]; this
0x180018828  test    rax, rax
0x18001882b  jz      loc_1800188E6
0x180018831  mov     [rbp+var_50], r14
0x180018835  mov     rax, [rbp+var_48]
0x180018839  nop
0x18001883a  mov     rbx, [rax+0B8h]
0x180018841  lea     rcx, [rbp+var_50]
0x180018845  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001884a  nop
0x18001884b  mov     rcx, [rbx+90h]
0x180018852  mov     rax, [rcx]
0x180018855  lea     r8, [rbp+var_50]
0x180018859  lea     rdx, _GUID_145e48ec_626a_4302_9000_36e8172c6d29
0x180018860  mov     rax, [rax]
0x180018863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018868  mov     ebx, eax
0x18001886a  mov     rcx, [rbp+var_50]
0x18001886e  test    eax, eax
0x180018870  js      short loc_180018898
0x180018872  test    rcx, rcx
0x180018875  jnz     short loc_180018898
0x180018877  mov     rcx, [rbp+18h]; this
0x18001887b  mov     ebx, 803E0105h
0x180018880  mov     r9d, ebx; char *
0x180018883  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001888a  mov     edx, 400h; void *
0x18001888f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018894  mov     rcx, [rbp+var_50]
0x180018898  mov     rax, [rbp+18h]
0x18001889c  test    ebx, ebx
0x18001889e  jns     loc_1800189A6
0x1800188a4  mov     r9d, ebx; char *
0x1800188a7  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800188ae  mov     edx, 0FFAh; void *
0x1800188b3  mov     rcx, rax; this
0x1800188b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800188bc  mov     r9d, eax; char *
0x1800188bf  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800188c6  mov     edx, 0FE8h; void *
0x1800188cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800188d1  mov     r9d, eax; char *
0x1800188d4  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800188db  mov     edx, 0FEDh; void *
0x1800188e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800188e6  mov     r9d, 803E0105h; char *
0x1800188ec  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800188f3  mov     edx, 0FF7h; void *
0x1800188f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800188fe  mov     rdx, [rbp+pv]
0x180018902  mov     rax, [rax+0D0h]
0x180018909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001890e  mov     rcx, [rbp+18h]; this
0x180018912  test    eax, eax
0x180018914  jns     loc_1800189CF
0x18001891a  mov     r9d, eax; char *
0x18001891d  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180018924  mov     edx, 0FFDh; void *
0x180018929  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001892f  mov     rcx, rdi
0x180018932  mov     rax, [rax+70h]
0x180018936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001893b  mov     rcx, [rbp+18h]; this
0x18001893f  test    eax, eax
0x180018941  js      short loc_180018991
0x180018943  lea     rcx, [rbp+var_50]
0x180018947  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001894c  nop
0x18001894d  mov     rdi, r14
0x180018950  xchg    rdi, [rbp+var_48]
0x180018954  test    rdi, rdi
0x180018957  jz      loc_180018781
0x18001895d  mov     rcx, rdi; this
0x180018960  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180018965  dec     qword ptr [rdi+98h]
0x18001896c  mov     rbx, [rdi+98h]
0x180018973  mov     rcx, rdi; _Mtx_t
0x180018976  call    cs:__imp__Mtx_unlock
0x18001897c  test    rbx, rbx
0x18001897f  jnz     short loc_18001898C
0x180018981  lea     rcx, [rdi+50h]; _Cnd_t
0x180018985  call    cs:__imp__Cnd_signal
0x18001898b  nop
0x18001898c  jmp     loc_180018781
0x180018991  mov     r9d, eax; char *
0x180018994  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001899b  mov     edx, 0FFFh; void *
0x1800189a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800189a6  cmp     [rbp+N], r14
0x1800189aa  setz    bl
0x1800189ad  mov     rax, [rcx]
0x1800189b0  test    bl, bl
0x1800189b2  jnz     short loc_1800189C7
0x1800189b4  lea     r8, [rbp+S1]
0x1800189b8  cmp     [rbp+var_10], 7
0x1800189bd  cmova   r8, [rbp+S1]
0x1800189c2  jmp     loc_1800188FE
0x1800189c7  mov     r8, r14
0x1800189ca  jmp     loc_1800188FE
0x1800189cf  mov     rax, [rdi]
0x1800189d2  test    bl, bl
0x1800189d4  jnz     short loc_1800189E9
0x1800189d6  lea     rdx, [rbp+S1]
0x1800189da  cmp     [rbp+var_10], 7
0x1800189df  cmova   rdx, [rbp+S1]
0x1800189e4  jmp     loc_18001892F
0x1800189e9  mov     rdx, r14
0x1800189ec  jmp     loc_18001892F
```

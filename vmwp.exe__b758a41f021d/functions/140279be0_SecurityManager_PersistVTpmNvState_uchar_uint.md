# SecurityManager::PersistVTpmNvState(uchar *,uint)

- ea: `0x140279be0`
- end: `0x14027a09b`
- name: `?PersistVTpmNvState@SecurityManager@@UEAAJPEAEI@Z`
- size: `1211`
- prototype: `int(SecurityManager *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140053de8`
- `0x140053f10`
- `0x1400676dc`
- `0x140069004`
- `0x1400691b4`
- `0x14006d540`
- `0x14011ea40`
- `0x14012216c`
- `0x140279be0`
- `0x14027a8bc`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140279c33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140279c33`

## string_xrefs

- `0x140279e54`: `/configuration/security/policy/lkg_security_policy`
- `0x140279d66`: `/configuration/security/keys/lkg_key_protector`
- `0x140279cf0`: `/configuration/security/keys/key_protector`
- `0x140279dde`: `/configuration/security/policy/security_policy`
- `0x140279ebb`: `/configuration/security/vtpm/vtpm_engine_nvram`
- `0x140279f8a`: `/configuration/security/vtpm/vtpm_engine_nvram_hash`
- `0x140279c9e`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140279d14`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140279d8a`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140279e02`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140279e78`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140279edf`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140279f42`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140279fae`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140279ffd`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027a068`: `onecore\vm\worker\security\securitymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SecurityManager::PersistVTpmNvState(SecurityManager *this, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v3; // r14
  char *v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // [rsp+20h] [rbp-98h]
  char *v28; // [rsp+30h] [rbp-88h] BYREF
  char *v29[2]; // [rsp+38h] [rbp-80h] BYREF
  unsigned int v30; // [rsp+48h] [rbp-70h]
  unsigned __int8 v31[24]; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int8 v32[16]; // [rsp+68h] [rbp-50h] BYREF
  __int128 v33; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v3 = a3;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  if ( !a2 || !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D9,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)0x80070057LL,
      v27);
    return 2147942487LL;
  }
  v6 = (char *)this + 384;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  try
  {
    v28 = v6;
    v7 = std::vector<unsigned char>::vector<unsigned char>(v31, a2, &a2[v3]);
    std::vector<unsigned char>::operator=((char *)this + 296, v7);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v31);
    *(_OWORD *)v29 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(v29, *((_QWORD *)this + 2), 1);
    v8 = (unsigned int)v29[1];
    if ( SLODWORD(v29[1]) < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E3,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)LODWORD(v29[1]),
        v27);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      return v8;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 144LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/keys/key_protector",
            *((_QWORD *)this + 28),
            (unsigned int)(*((_DWORD *)this + 58) - *((_DWORD *)this + 56)));
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F2,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v11,
        0);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      return v12;
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**((_QWORD **)this + 2) + 144LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/keys/lkg_key_protector",
            *((_QWORD *)this + 28));
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F7,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v13,
        0);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      return v14;
    }
    if ( *((_QWORD *)this + 35) != *((_QWORD *)this + 34) )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)this + 2) + 144LL))(
              *((_QWORD *)this + 2),
              L"/configuration/security/policy/security_policy");
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5FE,
          (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
          (const char *)(unsigned int)v15,
          0);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
        return v16;
      }
      v17 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**((_QWORD **)this + 2) + 144LL))(
              *((_QWORD *)this + 2),
              L"/configuration/security/policy/lkg_security_policy",
              *((_QWORD *)this + 34));
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x602,
          (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
          (const char *)(unsigned int)v17,
          0);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
        return v18;
      }
    }
    v19 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int8 *, _QWORD))(**((_QWORD **)this + 2)
                                                                                                 + 144LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/vtpm/vtpm_engine_nvram",
            a2,
            (unsigned int)v3);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x608,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v19,
        0);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      return v20;
    }
    if ( *((_DWORD *)this + 94) < 0x802u )
      goto LABEL_22;
    v21 = SecurityManager::Sha256HashData((SecurityManager *)((char *)this - 24), a2, v3, v32);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60C,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v21,
        0);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      return v22;
    }
    v23 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int8 *, __int64))(**((_QWORD **)this + 2)
                                                                                                  + 144LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/vtpm/vtpm_engine_nvram_hash",
            v32,
            32);
    v24 = v23;
    if ( v23 >= 0 )
    {
LABEL_22:
      v25 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2));
      v26 = v25;
      if ( v25 >= 0 )
      {
        *((_BYTE *)this + 195) = 1;
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x612,
          (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
          (const char *)(unsigned int)v25,
          0);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
        result = v26;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60F,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v23,
        0);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      result = v24;
    }
  }
  catch ( ... )
  {
    v30 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x618,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            v9);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
    return v30;
  }
  return result;
}

```

## disassembly

```asm
0x140279be0  push    rbx
0x140279be2  push    rsi
0x140279be3  push    rdi
0x140279be4  push    r14
0x140279be6  push    r15
0x140279be8  sub     rsp, 90h
0x140279bef  mov     rax, cs:__security_cookie
0x140279bf6  xor     rax, rsp
0x140279bf9  mov     [rsp+0B8h+var_30], rax
0x140279c01  mov     r14d, r8d
0x140279c04  mov     rsi, rdx
0x140279c07  mov     rdi, rcx
0x140279c0a  xorps   xmm0, xmm0
0x140279c0d  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x140279c12  movups  [rsp+0B8h+var_40], xmm0
0x140279c17  test    rdx, rdx
0x140279c1a  jz      loc_14027A058
0x140279c20  test    r8d, r8d
0x140279c23  jz      loc_14027A058
0x140279c29  lea     rbx, [rcx+180h]
0x140279c30  mov     rcx, rbx; lpCriticalSection
0x140279c33  call    cs:__imp_EnterCriticalSection
0x140279c3a  nop     dword ptr [rax+rax+00h]
0x140279c3f  mov     [rsp+0B8h+var_88], rbx
0x140279c44  lea     r8, [rsi+r14]
0x140279c48  mov     rdx, rsi
0x140279c4b  lea     rcx, [rsp+0B8h+var_68]
0x140279c50  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x140279c55  lea     rcx, [rdi+128h]
0x140279c5c  mov     rdx, rax
0x140279c5f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140279c64  lea     rcx, [rsp+0B8h+var_68]
0x140279c69  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140279c6e  xorps   xmm0, xmm0
0x140279c71  movups  xmmword ptr [rsp+0B8h+var_80], xmm0
0x140279c76  mov     r8d, 1
0x140279c7c  mov     rdx, [rdi+10h]
0x140279c80  lea     rcx, [rsp+0B8h+var_80]
0x140279c85  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x140279c8a  nop
0x140279c8b  mov     ebx, dword ptr [rsp+0B8h+var_80+8]
0x140279c8f  test    ebx, ebx
0x140279c91  jns     short loc_140279CCC
0x140279c93  mov     rcx, [rsp+0B8h]; this
0x140279c9b  mov     r9d, ebx; char *
0x140279c9e  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140279ca5  mov     edx, 5E3h; void *
0x140279caa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140279caf  nop
0x140279cb0  lea     rcx, [rsp+0B8h+var_80]; this
0x140279cb5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279cba  nop
0x140279cbb  lea     rcx, [rsp+0B8h+var_88]
0x140279cc0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140279cc5  mov     eax, ebx
0x140279cc7  jmp     loc_14027A07B
0x140279ccc  mov     rcx, [rdi+10h]
0x140279cd0  mov     rax, [rcx]
0x140279cd3  mov     r9d, [rdi+0E8h]
0x140279cda  sub     r9d, [rdi+0E0h]
0x140279ce1  mov     [rsp+0B8h+var_98], 0; int
0x140279ce9  mov     r8, [rdi+0E0h]
0x140279cf0  lea     rdx, ?SECURITY_SETTING_KEY_PROTECTOR@@3QBGB; "/configuration/security/keys/key_protec"...
0x140279cf7  mov     rax, [rax+90h]
0x140279cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140279d03  mov     ebx, eax
0x140279d05  test    eax, eax
0x140279d07  jns     short loc_140279D42
0x140279d09  mov     rcx, [rsp+0B8h]; this
0x140279d11  mov     r9d, eax; char *
0x140279d14  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140279d1b  mov     edx, 5F2h; void *
0x140279d20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140279d25  nop
0x140279d26  lea     rcx, [rsp+0B8h+var_80]; this
0x140279d2b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279d30  nop
0x140279d31  lea     rcx, [rsp+0B8h+var_88]
0x140279d36  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140279d3b  mov     eax, ebx
0x140279d3d  jmp     loc_14027A07B
0x140279d42  mov     rcx, [rdi+10h]
0x140279d46  mov     rax, [rcx]
0x140279d49  mov     r9d, [rdi+0E8h]
0x140279d50  sub     r9d, [rdi+0E0h]
0x140279d57  mov     [rsp+0B8h+var_98], 0; int
0x140279d5f  mov     r8, [rdi+0E0h]
0x140279d66  lea     rdx, ?SECURITY_SETTING_LKG_KEY_PROTECTOR@@3QBGB; "/configuration/security/keys/lkg_key_pr"...
0x140279d6d  mov     rax, [rax+90h]
0x140279d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140279d79  mov     ebx, eax
0x140279d7b  test    eax, eax
0x140279d7d  jns     short loc_140279DB8
0x140279d7f  mov     rcx, [rsp+0B8h]; this
0x140279d87  mov     r9d, eax; char *
0x140279d8a  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140279d91  mov     edx, 5F7h; void *
0x140279d96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140279d9b  nop
0x140279d9c  lea     rcx, [rsp+0B8h+var_80]; this
0x140279da1  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279da6  nop
0x140279da7  lea     rcx, [rsp+0B8h+var_88]
0x140279dac  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140279db1  mov     eax, ebx
0x140279db3  jmp     loc_14027A07B
0x140279db8  mov     r8, [rdi+110h]
0x140279dbf  mov     r9, [rdi+118h]
0x140279dc6  sub     r9, r8
0x140279dc9  jz      loc_140279EA6
0x140279dcf  mov     rcx, [rdi+10h]
0x140279dd3  mov     rax, [rcx]
0x140279dd6  mov     [rsp+0B8h+var_98], 0; int
0x140279dde  lea     rdx, ?SECURITY_SETTING_POLICY@@3QBGB; "/configuration/security/policy/security"...
0x140279de5  mov     rax, [rax+90h]
0x140279dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140279df1  mov     ebx, eax
0x140279df3  test    eax, eax
0x140279df5  jns     short loc_140279E30
0x140279df7  mov     rcx, [rsp+0B8h]; this
0x140279dff  mov     r9d, eax; char *
0x140279e02  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140279e09  mov     edx, 5FEh; void *
0x140279e0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140279e13  nop
0x140279e14  lea     rcx, [rsp+0B8h+var_80]; this
0x140279e19  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279e1e  nop
0x140279e1f  lea     rcx, [rsp+0B8h+var_88]
0x140279e24  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140279e29  mov     eax, ebx
0x140279e2b  jmp     loc_14027A07B
0x140279e30  mov     rcx, [rdi+10h]
0x140279e34  mov     rax, [rcx]
0x140279e37  mov     r9d, [rdi+118h]
0x140279e3e  sub     r9d, [rdi+110h]
0x140279e45  mov     [rsp+0B8h+var_98], 0; int
0x140279e4d  mov     r8, [rdi+110h]
0x140279e54  lea     rdx, ?SECURITY_SETTING_LKG_POLICY@@3QBGB; "/configuration/security/policy/lkg_secu"...
0x140279e5b  mov     rax, [rax+90h]
0x140279e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140279e67  mov     ebx, eax
0x140279e69  test    eax, eax
0x140279e6b  jns     short loc_140279EA6
0x140279e6d  mov     rcx, [rsp+0B8h]; this
0x140279e75  mov     r9d, eax; char *
0x140279e78  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140279e7f  mov     edx, 602h; void *
0x140279e84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140279e89  nop
0x140279e8a  lea     rcx, [rsp+0B8h+var_80]; this
0x140279e8f  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279e94  nop
0x140279e95  lea     rcx, [rsp+0B8h+var_88]
0x140279e9a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140279e9f  mov     eax, ebx
0x140279ea1  jmp     loc_14027A07B
0x140279ea6  mov     rcx, [rdi+10h]
0x140279eaa  mov     rax, [rcx]
0x140279ead  mov     [rsp+0B8h+var_98], 0; int
0x140279eb5  mov     r9d, r14d
0x140279eb8  mov     r8, rsi
0x140279ebb  lea     rdx, ?SECURITY_VTPM_ENGINE_NVRAM@@3QBGB; "/configuration/security/vtpm/vtpm_engin"...
0x140279ec2  mov     rax, [rax+90h]
0x140279ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140279ece  mov     ebx, eax
0x140279ed0  test    eax, eax
0x140279ed2  jns     short loc_140279F0D
0x140279ed4  mov     rcx, [rsp+0B8h]; this
0x140279edc  mov     r9d, eax; char *
0x140279edf  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140279ee6  mov     edx, 608h; void *
0x140279eeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140279ef0  nop
0x140279ef1  lea     rcx, [rsp+0B8h+var_80]; this
0x140279ef6  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279efb  nop
0x140279efc  lea     rcx, [rsp+0B8h+var_88]
0x140279f01  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140279f06  mov     eax, ebx
0x140279f08  jmp     loc_14027A07B
0x140279f0d  cmp     dword ptr [rdi+178h], 802h
0x140279f17  jb      loc_140279FDC
0x140279f1d  lea     r9, [rsp+0B8h+var_50]; unsigned __int8 *
0x140279f22  mov     r8d, r14d; unsigned int
0x140279f25  mov     rdx, rsi; unsigned __int8 *
0x140279f28  lea     rcx, [rdi-18h]; this
0x140279f2c  call    ?Sha256HashData@SecurityManager@@AEAAJPEAEIQEAE@Z; SecurityManager::Sha256HashData(uchar *,uint,uchar * const)
0x140279f31  mov     ebx, eax
0x140279f33  test    eax, eax
0x140279f35  jns     short loc_140279F70
0x140279f37  mov     rcx, [rsp+0B8h]; this
0x140279f3f  mov     r9d, eax; char *
0x140279f42  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140279f49  mov     edx, 60Ch; void *
0x140279f4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140279f53  nop
0x140279f54  lea     rcx, [rsp+0B8h+var_80]; this
0x140279f59  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279f5e  nop
0x140279f5f  lea     rcx, [rsp+0B8h+var_88]
0x140279f64  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140279f69  mov     eax, ebx
0x140279f6b  jmp     loc_14027A07B
0x140279f70  mov     rcx, [rdi+10h]
0x140279f74  mov     rax, [rcx]
0x140279f77  mov     [rsp+0B8h+var_98], 0; int
0x140279f7f  mov     r9d, 20h ; ' '
0x140279f85  lea     r8, [rsp+0B8h+var_50]
0x140279f8a  lea     rdx, ?SECURITY_VTPM_ENGINE_NVRAM_HASH@@3QBGB; "/configuration/security/vtpm/vtpm_engin"...
0x140279f91  mov     rax, [rax+90h]
0x140279f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140279f9d  mov     ebx, eax
0x140279f9f  test    eax, eax
0x140279fa1  jns     short loc_140279FDC
0x140279fa3  mov     rcx, [rsp+0B8h]; this
0x140279fab  mov     r9d, eax; char *
0x140279fae  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140279fb5  mov     edx, 60Fh; void *
0x140279fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140279fbf  nop
0x140279fc0  lea     rcx, [rsp+0B8h+var_80]; this
0x140279fc5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279fca  nop
0x140279fcb  lea     rcx, [rsp+0B8h+var_88]
0x140279fd0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140279fd5  mov     eax, ebx
0x140279fd7  jmp     loc_14027A07B
0x140279fdc  mov     rcx, [rdi+10h]
0x140279fe0  mov     rax, [rcx]
0x140279fe3  mov     rax, [rax+38h]
0x140279fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140279fec  mov     ebx, eax
0x140279fee  test    eax, eax
0x140279ff0  jns     short loc_14027A028
0x140279ff2  mov     rcx, [rsp+0B8h]; this
0x140279ffa  mov     r9d, eax; char *
0x140279ffd  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a004  mov     edx, 612h; void *
0x14027a009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027a00e  nop
0x14027a00f  lea     rcx, [rsp+0B8h+var_80]; this
0x14027a014  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14027a019  nop
0x14027a01a  lea     rcx, [rsp+0B8h+var_88]
0x14027a01f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x14027a024  mov     eax, ebx
0x14027a026  jmp     short loc_14027A07B
0x14027a028  mov     byte ptr [rdi+0C3h], 1
0x14027a02f  lea     rcx, [rsp+0B8h+var_80]; this
0x14027a034  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14027a039  nop
0x14027a03a  lea     rcx, [rsp+0B8h+var_88]
0x14027a03f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x14027a044  xor     eax, eax
0x14027a046  jmp     short loc_14027A07B
0x14027a048  lea     rcx, [rsp+0B8h+var_88]
0x14027a04d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x14027a052  mov     eax, [rsp+0B8h+var_70]
0x14027a056  jmp     short loc_14027A07B
0x14027a058  mov     rcx, [rsp+0B8h]; this
0x14027a060  mov     ebx, 80070057h
0x14027a065  mov     r9d, ebx; char *
0x14027a068  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027a06f  mov     edx, 5D9h; void *
0x14027a074  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027a079  mov     eax, ebx
0x14027a07b  mov     rcx, [rsp+0B8h+var_30]
0x14027a083  xor     rcx, rsp; StackCookie
0x14027a086  call    __security_check_cookie
0x14027a08b  add     rsp, 90h
0x14027a092  pop     r15
0x14027a094  pop     r14
0x14027a096  pop     rdi
0x14027a097  pop     rsi
0x14027a098  pop     rbx
0x14027a099  retn
```

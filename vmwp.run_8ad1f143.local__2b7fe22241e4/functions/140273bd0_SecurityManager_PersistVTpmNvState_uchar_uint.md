# SecurityManager::PersistVTpmNvState(uchar *,uint)

- ea: `0x140273bd0`
- end: `0x14027408b`
- name: `?PersistVTpmNvState@SecurityManager@@UEAAJPEAEI@Z`
- size: `1211`
- prototype: `int(SecurityManager *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400544a8`
- `0x1400545d0`
- `0x14005e6a4`
- `0x14005e804`
- `0x1400b42d0`
- `0x1400c1814`
- `0x140132960`
- `0x14013608c`
- `0x140273bd0`
- `0x1402748ac`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140273c23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140273c23`

## string_xrefs

- `0x140273e44`: `/configuration/security/policy/lkg_security_policy`
- `0x140273d56`: `/configuration/security/keys/lkg_key_protector`
- `0x140273ce0`: `/configuration/security/keys/key_protector`
- `0x140273dce`: `/configuration/security/policy/security_policy`
- `0x140273eab`: `/configuration/security/vtpm/vtpm_engine_nvram`
- `0x140273f7a`: `/configuration/security/vtpm/vtpm_engine_nvram_hash`
- `0x140273c8e`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273d04`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273d7a`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273df2`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273e68`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273ecf`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273f32`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273f9e`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273fed`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274058`: `onecore\vm\worker\security\securitymanager.cpp`

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
0x140273bd0  push    rbx
0x140273bd2  push    rsi
0x140273bd3  push    rdi
0x140273bd4  push    r14
0x140273bd6  push    r15
0x140273bd8  sub     rsp, 90h
0x140273bdf  mov     rax, cs:__security_cookie
0x140273be6  xor     rax, rsp
0x140273be9  mov     [rsp+0B8h+var_30], rax
0x140273bf1  mov     r14d, r8d
0x140273bf4  mov     rsi, rdx
0x140273bf7  mov     rdi, rcx
0x140273bfa  xorps   xmm0, xmm0
0x140273bfd  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x140273c02  movups  [rsp+0B8h+var_40], xmm0
0x140273c07  test    rdx, rdx
0x140273c0a  jz      loc_140274048
0x140273c10  test    r8d, r8d
0x140273c13  jz      loc_140274048
0x140273c19  lea     rbx, [rcx+180h]
0x140273c20  mov     rcx, rbx; lpCriticalSection
0x140273c23  call    cs:__imp_EnterCriticalSection
0x140273c2a  nop     dword ptr [rax+rax+00h]
0x140273c2f  mov     [rsp+0B8h+var_88], rbx
0x140273c34  lea     r8, [rsi+r14]
0x140273c38  mov     rdx, rsi
0x140273c3b  lea     rcx, [rsp+0B8h+var_68]
0x140273c40  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x140273c45  lea     rcx, [rdi+128h]
0x140273c4c  mov     rdx, rax
0x140273c4f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140273c54  lea     rcx, [rsp+0B8h+var_68]
0x140273c59  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140273c5e  xorps   xmm0, xmm0
0x140273c61  movups  xmmword ptr [rsp+0B8h+var_80], xmm0
0x140273c66  mov     r8d, 1
0x140273c6c  mov     rdx, [rdi+10h]
0x140273c70  lea     rcx, [rsp+0B8h+var_80]
0x140273c75  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x140273c7a  nop
0x140273c7b  mov     ebx, dword ptr [rsp+0B8h+var_80+8]
0x140273c7f  test    ebx, ebx
0x140273c81  jns     short loc_140273CBC
0x140273c83  mov     rcx, [rsp+0B8h]; this
0x140273c8b  mov     r9d, ebx; char *
0x140273c8e  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273c95  mov     edx, 5E3h; void *
0x140273c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273c9f  nop
0x140273ca0  lea     rcx, [rsp+0B8h+var_80]; this
0x140273ca5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273caa  nop
0x140273cab  lea     rcx, [rsp+0B8h+var_88]
0x140273cb0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273cb5  mov     eax, ebx
0x140273cb7  jmp     loc_14027406B
0x140273cbc  mov     rcx, [rdi+10h]
0x140273cc0  mov     rax, [rcx]
0x140273cc3  mov     r9d, [rdi+0E8h]
0x140273cca  sub     r9d, [rdi+0E0h]
0x140273cd1  mov     [rsp+0B8h+var_98], 0; int
0x140273cd9  mov     r8, [rdi+0E0h]
0x140273ce0  lea     rdx, ?SECURITY_SETTING_KEY_PROTECTOR@@3QBGB; "/configuration/security/keys/key_protec"...
0x140273ce7  mov     rax, [rax+90h]
0x140273cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273cf3  mov     ebx, eax
0x140273cf5  test    eax, eax
0x140273cf7  jns     short loc_140273D32
0x140273cf9  mov     rcx, [rsp+0B8h]; this
0x140273d01  mov     r9d, eax; char *
0x140273d04  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273d0b  mov     edx, 5F2h; void *
0x140273d10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273d15  nop
0x140273d16  lea     rcx, [rsp+0B8h+var_80]; this
0x140273d1b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273d20  nop
0x140273d21  lea     rcx, [rsp+0B8h+var_88]
0x140273d26  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273d2b  mov     eax, ebx
0x140273d2d  jmp     loc_14027406B
0x140273d32  mov     rcx, [rdi+10h]
0x140273d36  mov     rax, [rcx]
0x140273d39  mov     r9d, [rdi+0E8h]
0x140273d40  sub     r9d, [rdi+0E0h]
0x140273d47  mov     [rsp+0B8h+var_98], 0; int
0x140273d4f  mov     r8, [rdi+0E0h]
0x140273d56  lea     rdx, ?SECURITY_SETTING_LKG_KEY_PROTECTOR@@3QBGB; "/configuration/security/keys/lkg_key_pr"...
0x140273d5d  mov     rax, [rax+90h]
0x140273d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273d69  mov     ebx, eax
0x140273d6b  test    eax, eax
0x140273d6d  jns     short loc_140273DA8
0x140273d6f  mov     rcx, [rsp+0B8h]; this
0x140273d77  mov     r9d, eax; char *
0x140273d7a  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273d81  mov     edx, 5F7h; void *
0x140273d86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273d8b  nop
0x140273d8c  lea     rcx, [rsp+0B8h+var_80]; this
0x140273d91  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273d96  nop
0x140273d97  lea     rcx, [rsp+0B8h+var_88]
0x140273d9c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273da1  mov     eax, ebx
0x140273da3  jmp     loc_14027406B
0x140273da8  mov     r8, [rdi+110h]
0x140273daf  mov     r9, [rdi+118h]
0x140273db6  sub     r9, r8
0x140273db9  jz      loc_140273E96
0x140273dbf  mov     rcx, [rdi+10h]
0x140273dc3  mov     rax, [rcx]
0x140273dc6  mov     [rsp+0B8h+var_98], 0; int
0x140273dce  lea     rdx, ?SECURITY_SETTING_POLICY@@3QBGB; "/configuration/security/policy/security"...
0x140273dd5  mov     rax, [rax+90h]
0x140273ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273de1  mov     ebx, eax
0x140273de3  test    eax, eax
0x140273de5  jns     short loc_140273E20
0x140273de7  mov     rcx, [rsp+0B8h]; this
0x140273def  mov     r9d, eax; char *
0x140273df2  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273df9  mov     edx, 5FEh; void *
0x140273dfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273e03  nop
0x140273e04  lea     rcx, [rsp+0B8h+var_80]; this
0x140273e09  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273e0e  nop
0x140273e0f  lea     rcx, [rsp+0B8h+var_88]
0x140273e14  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273e19  mov     eax, ebx
0x140273e1b  jmp     loc_14027406B
0x140273e20  mov     rcx, [rdi+10h]
0x140273e24  mov     rax, [rcx]
0x140273e27  mov     r9d, [rdi+118h]
0x140273e2e  sub     r9d, [rdi+110h]
0x140273e35  mov     [rsp+0B8h+var_98], 0; int
0x140273e3d  mov     r8, [rdi+110h]
0x140273e44  lea     rdx, ?SECURITY_SETTING_LKG_POLICY@@3QBGB; "/configuration/security/policy/lkg_secu"...
0x140273e4b  mov     rax, [rax+90h]
0x140273e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273e57  mov     ebx, eax
0x140273e59  test    eax, eax
0x140273e5b  jns     short loc_140273E96
0x140273e5d  mov     rcx, [rsp+0B8h]; this
0x140273e65  mov     r9d, eax; char *
0x140273e68  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273e6f  mov     edx, 602h; void *
0x140273e74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273e79  nop
0x140273e7a  lea     rcx, [rsp+0B8h+var_80]; this
0x140273e7f  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273e84  nop
0x140273e85  lea     rcx, [rsp+0B8h+var_88]
0x140273e8a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273e8f  mov     eax, ebx
0x140273e91  jmp     loc_14027406B
0x140273e96  mov     rcx, [rdi+10h]
0x140273e9a  mov     rax, [rcx]
0x140273e9d  mov     [rsp+0B8h+var_98], 0; int
0x140273ea5  mov     r9d, r14d
0x140273ea8  mov     r8, rsi
0x140273eab  lea     rdx, ?SECURITY_VTPM_ENGINE_NVRAM@@3QBGB; "/configuration/security/vtpm/vtpm_engin"...
0x140273eb2  mov     rax, [rax+90h]
0x140273eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273ebe  mov     ebx, eax
0x140273ec0  test    eax, eax
0x140273ec2  jns     short loc_140273EFD
0x140273ec4  mov     rcx, [rsp+0B8h]; this
0x140273ecc  mov     r9d, eax; char *
0x140273ecf  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273ed6  mov     edx, 608h; void *
0x140273edb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273ee0  nop
0x140273ee1  lea     rcx, [rsp+0B8h+var_80]; this
0x140273ee6  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273eeb  nop
0x140273eec  lea     rcx, [rsp+0B8h+var_88]
0x140273ef1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273ef6  mov     eax, ebx
0x140273ef8  jmp     loc_14027406B
0x140273efd  cmp     dword ptr [rdi+178h], 802h
0x140273f07  jb      loc_140273FCC
0x140273f0d  lea     r9, [rsp+0B8h+var_50]; unsigned __int8 *
0x140273f12  mov     r8d, r14d; unsigned int
0x140273f15  mov     rdx, rsi; unsigned __int8 *
0x140273f18  lea     rcx, [rdi-18h]; this
0x140273f1c  call    ?Sha256HashData@SecurityManager@@AEAAJPEAEIQEAE@Z; SecurityManager::Sha256HashData(uchar *,uint,uchar * const)
0x140273f21  mov     ebx, eax
0x140273f23  test    eax, eax
0x140273f25  jns     short loc_140273F60
0x140273f27  mov     rcx, [rsp+0B8h]; this
0x140273f2f  mov     r9d, eax; char *
0x140273f32  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273f39  mov     edx, 60Ch; void *
0x140273f3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273f43  nop
0x140273f44  lea     rcx, [rsp+0B8h+var_80]; this
0x140273f49  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273f4e  nop
0x140273f4f  lea     rcx, [rsp+0B8h+var_88]
0x140273f54  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273f59  mov     eax, ebx
0x140273f5b  jmp     loc_14027406B
0x140273f60  mov     rcx, [rdi+10h]
0x140273f64  mov     rax, [rcx]
0x140273f67  mov     [rsp+0B8h+var_98], 0; int
0x140273f6f  mov     r9d, 20h ; ' '
0x140273f75  lea     r8, [rsp+0B8h+var_50]
0x140273f7a  lea     rdx, ?SECURITY_VTPM_ENGINE_NVRAM_HASH@@3QBGB; "/configuration/security/vtpm/vtpm_engin"...
0x140273f81  mov     rax, [rax+90h]
0x140273f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273f8d  mov     ebx, eax
0x140273f8f  test    eax, eax
0x140273f91  jns     short loc_140273FCC
0x140273f93  mov     rcx, [rsp+0B8h]; this
0x140273f9b  mov     r9d, eax; char *
0x140273f9e  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273fa5  mov     edx, 60Fh; void *
0x140273faa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273faf  nop
0x140273fb0  lea     rcx, [rsp+0B8h+var_80]; this
0x140273fb5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273fba  nop
0x140273fbb  lea     rcx, [rsp+0B8h+var_88]
0x140273fc0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273fc5  mov     eax, ebx
0x140273fc7  jmp     loc_14027406B
0x140273fcc  mov     rcx, [rdi+10h]
0x140273fd0  mov     rax, [rcx]
0x140273fd3  mov     rax, [rax+38h]
0x140273fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273fdc  mov     ebx, eax
0x140273fde  test    eax, eax
0x140273fe0  jns     short loc_140274018
0x140273fe2  mov     rcx, [rsp+0B8h]; this
0x140273fea  mov     r9d, eax; char *
0x140273fed  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273ff4  mov     edx, 612h; void *
0x140273ff9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273ffe  nop
0x140273fff  lea     rcx, [rsp+0B8h+var_80]; this
0x140274004  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140274009  nop
0x14027400a  lea     rcx, [rsp+0B8h+var_88]
0x14027400f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140274014  mov     eax, ebx
0x140274016  jmp     short loc_14027406B
0x140274018  mov     byte ptr [rdi+0C3h], 1
0x14027401f  lea     rcx, [rsp+0B8h+var_80]; this
0x140274024  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140274029  nop
0x14027402a  lea     rcx, [rsp+0B8h+var_88]
0x14027402f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140274034  xor     eax, eax
0x140274036  jmp     short loc_14027406B
0x140274038  lea     rcx, [rsp+0B8h+var_88]
0x14027403d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140274042  mov     eax, [rsp+0B8h+var_70]
0x140274046  jmp     short loc_14027406B
0x140274048  mov     rcx, [rsp+0B8h]; this
0x140274050  mov     ebx, 80070057h
0x140274055  mov     r9d, ebx; char *
0x140274058  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027405f  mov     edx, 5D9h; void *
0x140274064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140274069  mov     eax, ebx
0x14027406b  mov     rcx, [rsp+0B8h+var_30]
0x140274073  xor     rcx, rsp; StackCookie
0x140274076  call    __security_check_cookie
0x14027407b  add     rsp, 90h
0x140274082  pop     r15
0x140274084  pop     r14
0x140274086  pop     rdi
0x140274087  pop     rsi
0x140274088  pop     rbx
0x140274089  retn
```

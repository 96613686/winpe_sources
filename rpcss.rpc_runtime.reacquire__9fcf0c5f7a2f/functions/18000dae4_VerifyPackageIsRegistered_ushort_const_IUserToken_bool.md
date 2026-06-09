# VerifyPackageIsRegistered(ushort const *,IUserToken *,bool)

- ea: `0x18000dae4`
- end: `0x18000e06d`
- name: `?VerifyPackageIsRegistered@@YAJPEBGPEAUIUserToken@@_N@Z`
- size: `1417`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUserToken *, bool)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003bf10`

## callees

- `0x18000ce5c`
- `0x18000cf64`
- `0x18000d850`
- `0x18000dae4`
- `0x18000e074`
- `0x18000e0a0`
- `0x18000e148`
- `0x18000e5c0`
- `0x18000eccc`
- `0x18000edf0`
- `0x18000f14c`
- `0x18000f7f4`
- `0x18000fb8c`
- `0x1800210f8`
- `0x1800a48d8`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x180114010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000dd62`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000dd62`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000de1d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000dea1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000dfdb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000de1d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000dea1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000dfdb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000db46`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000db46`

## string_xrefs

- `0x18000db75`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18000dc64`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18000deb7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18000db90`: `onecore\com\combase\catalog\services.cxx`
- `0x18000dcca`: `onecore\com\combase\catalog\services.cxx`
- `0x18000dedf`: `onecore\com\combase\catalog\services.cxx`
- `0x18000de84`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000df60`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000df82`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000dfa7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000dfbd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall VerifyPackageIsRegistered(const unsigned __int16 *a1, struct IUserToken *a2, char a3)
{
  int LastError; // ebx
  bool v8; // r14
  ProcessToken *v9; // rcx
  PSID v10; // rsi
  int v11; // eax
  const char *v12; // rax
  __int64 v13; // rdx
  int SelfSid; // eax
  bool v15; // si
  const char *v16; // r9
  __int64 v17; // rdi
  int v18; // eax
  __int64 v19; // r8
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  unsigned __int64 v24; // r9
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rdx
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  bool v32; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v39; // [rsp+68h] [rbp-98h]
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  char v41; // [rsp+78h] [rbp-88h]
  __int64 v42[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+90h] [rbp-70h]
  __int64 v44; // [rsp+98h] [rbp-68h]
  __int64 v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+A8h] [rbp-58h]
  __int64 v47; // [rsp+B0h] [rbp-50h]
  __int64 v48; // [rsp+B8h] [rbp-48h]
  __int128 v49; // [rsp+C0h] [rbp-40h]
  int v50; // [rsp+D0h] [rbp-30h]
  __int64 v51; // [rsp+D8h] [rbp-28h]
  __int64 v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v54[72]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v55; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  if ( !g_disableCatalogPackageRegistrationChecks )
  {
    v35 = 0;
    v39 = &v35;
    v40 = 0;
    v41 = 1;
    LastError = SRCacheManager_Open(0, &v40);
    if ( v41 )
      wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(v39, v40);
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
        (const char *)(unsigned int)LastError,
        v29);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6F,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)LastError,
        v30);
LABEL_6:
      wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v35, 0);
      return (unsigned int)LastError;
    }
    v43 = 0;
    *(_OWORD *)v42 = 0;
    v49 = 0;
    v44 = 0;
    v45 = 0;
    v8 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v32 = 0;
    Sid = 0;
    LastError = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
                  (struct StateRepository::Cache::Manager_NoThrow *)&v35,
                  a1,
                  (__int64 *)&Sid);
    if ( LastError < 0 )
    {
      v22 = 1165;
      goto LABEL_42;
    }
    v10 = Sid;
    if ( !Sid )
    {
LABEL_15:
      if ( !v8 || (v44 & 0x800000000LL) == 0 )
      {
        v12 = "Package %ls is not machine registered";
        v13 = 3449;
        goto LABEL_17;
      }
      if ( a3 )
      {
        if ( (v44 & 0x100000000000LL) != 0 || (v45 & 0x100) != 0 )
          goto LABEL_38;
        v12 = "Package %ls is not singleton or system registered";
        v13 = 3457;
        goto LABEL_17;
      }
      if ( (v45 & 0x1000) != 0 )
      {
LABEL_38:
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v42);
        LastError = 0;
        goto LABEL_6;
      }
      Sid = 0;
      if ( a2 )
      {
        v25 = *(_QWORD *)a2;
        v34 = 0;
        v26 = (*(__int64 (__fastcall **)(struct IUserToken *, PSID *, __int16 *))(v25 + 40))(a2, &Sid, &v34);
        LastError = v26;
        if ( v26 < 0 )
        {
          v24 = (unsigned int)v26;
          v23 = 3472;
          goto LABEL_44;
        }
      }
      else
      {
        SelfSid = ProcessToken::GetSelfSid(v9, &Sid);
        LastError = SelfSid;
        if ( SelfSid < 0 )
        {
          v24 = (unsigned int)SelfSid;
          v23 = 3476;
          goto LABEL_44;
        }
      }
      v53 = 0;
      memset_0(v54, 0, 0x44u);
      v55 = 0;
      v15 = 0;
      v32 = 0;
      StringSid = 0;
      if ( !ConvertSidToStringSidW(Sid, &StringSid) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xDC,
                      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
                      v16);
        if ( StringSid )
          LocalFree(StringSid);
        if ( LastError >= 0 )
          goto LABEL_35;
        goto LABEL_56;
      }
      v38 = 0;
      LastError = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
                    (struct StateRepository::Cache::Manager_NoThrow *)&v35,
                    StringSid,
                    &v38);
      if ( LastError < 0 )
      {
        v27 = 245;
LABEL_54:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
          (const char *)(unsigned int)LastError,
          v29);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
          (const char *)(unsigned int)LastError,
          v31);
        if ( StringSid )
          LocalFree(StringSid);
LABEL_56:
        v23 = 3482;
        goto LABEL_43;
      }
      v17 = v38;
      if ( v38 )
      {
        v33 = 0;
        v18 = StateRepository::Cache::Entity::User_NoThrow::Open(
                (struct StateRepository::Cache::Manager_NoThrow *)&v35,
                v38,
                (struct StateRepository::Cache::Context_NoThrow *)&v33,
                &v32);
        v15 = v32;
        LastError = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9B,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
            (const char *)(unsigned int)v18,
            v29);
LABEL_31:
          wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v33, 0);
          if ( LastError >= 0 )
            goto LABEL_32;
          v27 = 248;
          goto LABEL_54;
        }
        if ( v32 )
        {
          v20 = StateRepository::Cache::Entity::User_NoThrow::ContextToObject(
                  (StateRepository::Cache::Context_NoThrow *)&v33,
                  &v53,
                  v19,
                  v17);
          LastError = v20;
          if ( v20 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA0,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
              (const char *)(unsigned int)v20,
              v29);
          else
            LastError = 0;
          goto LABEL_31;
        }
        wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v33, 0);
      }
LABEL_32:
      if ( StringSid )
        LocalFree(StringSid);
LABEL_35:
      if ( v15 )
      {
        v32 = 0;
        v21 = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
                (struct StateRepository::Cache::Manager_NoThrow *)&v35,
                v53,
                v42[0],
                &v32);
        LastError = v21;
        if ( v21 >= 0 )
        {
          if ( v32 )
            goto LABEL_38;
          v12 = "Package %ls is not user registered";
          v13 = 3494;
          goto LABEL_17;
        }
        v24 = (unsigned int)v21;
        v23 = 3491;
LABEL_44:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
          (const char *)v24,
          v29);
        goto LABEL_18;
      }
      v12 = "Package %ls is not user registered";
      v13 = 3487;
LABEL_17:
      LastError = -2147023728;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)0x80070490LL,
        (int)v12,
        (const char *)a1);
LABEL_18:
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v42);
      goto LABEL_6;
    }
    v33 = 0;
    v11 = StateRepository::Cache::Entity::Package_NoThrow::Open(
            (struct StateRepository::Cache::Manager_NoThrow *)&v35,
            (__int64)Sid,
            (struct StateRepository::Cache::Context_NoThrow *)&v33,
            &v32);
    v8 = v32;
    LastError = v11;
    if ( v11 < 0 )
    {
      v28 = 1110;
    }
    else
    {
      if ( !v32 )
      {
        wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v33, 0);
        goto LABEL_15;
      }
      v11 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v33, v42, 0, v10);
      LastError = v11;
      if ( v11 >= 0 )
      {
        LastError = 0;
LABEL_14:
        wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v33, 0);
        if ( LastError >= 0 )
          goto LABEL_15;
        v22 = 1168;
LABEL_42:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
          (const char *)(unsigned int)LastError,
          v29);
        v23 = 3444;
LABEL_43:
        v24 = (unsigned int)LastError;
        goto LABEL_44;
      }
      v28 = 1115;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v11,
      v29);
    goto LABEL_14;
  }
  return 0;
}

```

## disassembly

```asm
0x18000dae4  mov     [rsp-8+arg_10], rbx
0x18000dae9  push    rbp
0x18000daea  push    rsi
0x18000daeb  push    rdi
0x18000daec  push    r12
0x18000daee  push    r13
0x18000daf0  push    r14
0x18000daf2  push    r15
0x18000daf4  lea     rbp, [rsp-60h]
0x18000daf9  sub     rsp, 160h
0x18000db00  mov     rax, cs:__security_cookie
0x18000db07  xor     rax, rsp
0x18000db0a  mov     [rbp+90h+var_40], rax
0x18000db0e  xor     edi, edi
0x18000db10  mov     r13b, r8b
0x18000db13  cmp     cs:?g_disableCatalogPackageRegistrationChecks@@3_NA, dil; bool g_disableCatalogPackageRegistrationChecks
0x18000db1a  mov     r15, rdx
0x18000db1d  mov     r12, rcx
0x18000db20  jnz     loc_18000DBDA
0x18000db26  lea     rax, [rsp+190h+var_148]
0x18000db2b  mov     [rsp+190h+var_148], rdi
0x18000db30  lea     rdx, [rsp+190h+var_120]
0x18000db35  mov     [rsp+190h+var_128], rax
0x18000db3a  xor     ecx, ecx
0x18000db3c  mov     [rsp+190h+var_120], rdi
0x18000db41  mov     [rsp+190h+var_118], 1
0x18000db46  call    cs:__imp_SRCacheManager_Open
0x18000db4d  nop     dword ptr [rax+rax+00h]
0x18000db52  mov     ebx, eax
0x18000db54  cmp     [rsp+190h+var_118], dil
0x18000db59  jz      short loc_18000DB6A
0x18000db5b  mov     rdx, [rsp+190h+var_120]
0x18000db60  mov     rcx, [rsp+190h+var_128]
0x18000db65  call    ?reset@?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheManager@@@Z; wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(SRCacheManager *)
0x18000db6a  test    ebx, ebx
0x18000db6c  jns     short loc_18000DBDE
0x18000db6e  mov     rcx, [rbp+98h]; this
0x18000db75  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000db7c  mov     r9d, ebx; char *
0x18000db7f  mov     edx, 0A5h; void *
0x18000db84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db89  mov     rcx, [rbp+98h]; this
0x18000db90  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18000db97  mov     r9d, ebx; char *
0x18000db9a  mov     edx, 0D6Fh; void *
0x18000db9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dba4  xor     edx, edx
0x18000dba6  lea     rcx, [rsp+190h+var_148]
0x18000dbab  call    ?reset@?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheManager@@@Z; wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(SRCacheManager *)
0x18000dbb0  mov     eax, ebx
0x18000dbb2  mov     rcx, [rbp+90h+var_40]
0x18000dbb6  xor     rcx, rsp; StackCookie
0x18000dbb9  call    __security_check_cookie
0x18000dbbe  mov     rbx, [rsp+190h+arg_10]
0x18000dbc6  add     rsp, 160h
0x18000dbcd  pop     r15
0x18000dbcf  pop     r14
0x18000dbd1  pop     r13
0x18000dbd3  pop     r12
0x18000dbd5  pop     rdi
0x18000dbd6  pop     rsi
0x18000dbd7  pop     rbp
0x18000dbd8  retn
0x18000dbda  xor     eax, eax
0x18000dbdc  jmp     short loc_18000DBB2
0x18000dbde  xorps   xmm0, xmm0
0x18000dbe1  mov     [rbp+90h+var_100], rdi
0x18000dbe5  lea     r8, [rsp+190h+Sid]; __int64 *
0x18000dbea  movdqa  xmmword ptr [rbp+90h+var_110], xmm0
0x18000dbef  mov     rdx, r12; unsigned __int16 *
0x18000dbf2  movdqa  [rbp+90h+var_D0], xmm0
0x18000dbf7  lea     rcx, [rsp+190h+var_148]; struct StateRepository::Cache::Manager_NoThrow *
0x18000dbfc  mov     [rbp+90h+var_F8], rdi
0x18000dc00  mov     [rbp+90h+var_F0], rdi
0x18000dc04  mov     r14b, dil
0x18000dc07  mov     [rbp+90h+var_E8], rdi
0x18000dc0b  mov     [rbp+90h+var_E0], rdi
0x18000dc0f  mov     [rbp+90h+var_D8], rdi
0x18000dc13  mov     [rbp+90h+var_C0], edi
0x18000dc16  mov     [rbp+90h+var_B8], rdi
0x18000dc1a  mov     [rbp+90h+var_B0], rdi
0x18000dc1e  mov     [rsp+190h+var_160], dil
0x18000dc23  mov     [rsp+190h+Sid], rdi
0x18000dc28  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18000dc2d  mov     ebx, eax
0x18000dc2f  test    eax, eax
0x18000dc31  js      loc_18000DEB2
0x18000dc37  mov     rsi, [rsp+190h+Sid]
0x18000dc3c  test    rsi, rsi
0x18000dc3f  jz      short loc_18000DCB2
0x18000dc41  lea     r9, [rsp+190h+var_160]; bool *
0x18000dc46  mov     [rsp+190h+var_158], rdi
0x18000dc4b  lea     r8, [rsp+190h+var_158]; struct StateRepository::Cache::Context_NoThrow *
0x18000dc50  mov     rdx, rsi; __int64
0x18000dc53  lea     rcx, [rsp+190h+var_148]; struct StateRepository::Cache::Manager_NoThrow *
0x18000dc58  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18000dc5d  mov     r14b, [rsp+190h+var_160]
0x18000dc62  mov     ebx, eax
0x18000dc64  lea     rdi, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000dc6b  test    eax, eax
0x18000dc6d  js      loc_18000DFF1
0x18000dc73  lea     rcx, [rsp+190h+var_158]
0x18000dc78  test    r14b, r14b
0x18000dc7b  jz      loc_18000E00D
0x18000dc81  mov     r9, rsi
0x18000dc84  lea     rdx, [rbp+90h+var_110]
0x18000dc88  xor     r8d, r8d
0x18000dc8b  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x18000dc90  mov     ebx, eax
0x18000dc92  test    eax, eax
0x18000dc94  js      loc_18000E019
0x18000dc9a  xor     ebx, ebx
0x18000dc9c  lea     rcx, [rsp+190h+var_158]
0x18000dca1  xor     edx, edx
0x18000dca3  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000dca8  test    ebx, ebx
0x18000dcaa  js      loc_18000E020
0x18000dcb0  xor     edi, edi
0x18000dcb2  test    r14b, r14b
0x18000dcb5  jnz     short loc_18000DCF6
0x18000dcb7  lea     rax, aPackageLsIsNot_1; "Package %ls is not machine registered"
0x18000dcbe  mov     edx, 0D79h; void *
0x18000dcc3  mov     rcx, [rbp+98h]; this
0x18000dcca  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18000dcd1  mov     ebx, 80070490h
0x18000dcd6  mov     [rsp+190h+var_168], r12; char *
0x18000dcdb  mov     r9d, ebx; char *
0x18000dcde  mov     qword ptr [rsp+190h+var_170], rax; int
0x18000dce3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000dce8  lea     rcx, [rbp+90h+var_110]; this
0x18000dcec  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18000dcf1  jmp     loc_18000DBA4
0x18000dcf6  test    byte ptr [rbp+90h+var_F8+4], 8
0x18000dcfa  jz      short loc_18000DCB7
0x18000dcfc  test    r13b, r13b
0x18000dcff  jnz     loc_18000DF1D
0x18000dd05  test    dword ptr [rbp+90h+var_F0], 1000h
0x18000dd0c  jnz     loc_18000DE6D
0x18000dd12  mov     [rsp+190h+Sid], rdi
0x18000dd17  lea     rdx, [rsp+190h+Sid]; void **
0x18000dd1c  test    r15, r15
0x18000dd1f  jnz     loc_18000DEF0
0x18000dd25  call    ?GetSelfSid@ProcessToken@@QEAAJPEAPEAX@Z; ProcessToken::GetSelfSid(void * *)
0x18000dd2a  mov     ebx, eax
0x18000dd2c  test    eax, eax
0x18000dd2e  js      loc_18000E02A
0x18000dd34  xor     edx, edx; Val
0x18000dd36  mov     [rbp+90h+var_A0], rdi
0x18000dd3a  lea     rcx, [rbp+90h+var_98]; void *
0x18000dd3e  lea     r8d, [rdx+44h]; Size
0x18000dd42  call    memset_0
0x18000dd47  mov     rcx, [rsp+190h+Sid]; Sid
0x18000dd4c  lea     rdx, [rsp+190h+StringSid]; StringSid
0x18000dd51  mov     [rbp+90h+var_50], rdi
0x18000dd55  mov     sil, dil
0x18000dd58  mov     [rsp+190h+var_160], dil
0x18000dd5d  mov     [rsp+190h+StringSid], rdi
0x18000dd62  call    cs:__imp_ConvertSidToStringSidW
0x18000dd69  nop     dword ptr [rax+rax+00h]
0x18000dd6e  test    eax, eax
0x18000dd70  jz      loc_18000DE7D
0x18000dd76  mov     rdx, [rsp+190h+StringSid]; unsigned __int16 *
0x18000dd7b  lea     r8, [rsp+190h+var_130]; __int64 *
0x18000dd80  lea     rcx, [rsp+190h+var_148]; struct StateRepository::Cache::Manager_NoThrow *
0x18000dd85  mov     [rsp+190h+var_130], rdi
0x18000dd8a  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18000dd8f  mov     ebx, eax
0x18000dd91  test    eax, eax
0x18000dd93  js      loc_18000DF9B
0x18000dd99  mov     rdi, [rsp+190h+var_130]
0x18000dd9e  test    rdi, rdi
0x18000dda1  jz      loc_18000E03E
0x18000dda7  lea     r9, [rsp+190h+var_160]; bool *
0x18000ddac  mov     [rsp+190h+var_158], 0
0x18000ddb5  lea     r8, [rsp+190h+var_158]; struct StateRepository::Cache::Context_NoThrow *
0x18000ddba  mov     rdx, rdi; __int64
0x18000ddbd  lea     rcx, [rsp+190h+var_148]; struct StateRepository::Cache::Manager_NoThrow *
0x18000ddc2  call    ?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18000ddc7  mov     sil, [rsp+190h+var_160]
0x18000ddcc  mov     ebx, eax
0x18000ddce  test    eax, eax
0x18000ddd0  js      loc_18000DF59
0x18000ddd6  lea     rcx, [rsp+190h+var_158]
0x18000dddb  test    sil, sil
0x18000ddde  jz      loc_18000E037
0x18000dde4  mov     r9, rdi
0x18000dde7  lea     rdx, [rbp+90h+var_A0]
0x18000ddeb  call    ?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)
0x18000ddf0  xor     edi, edi
0x18000ddf2  mov     ebx, eax
0x18000ddf4  test    eax, eax
0x18000ddf6  js      loc_18000DF7B
0x18000ddfc  mov     ebx, edi
0x18000ddfe  lea     rcx, [rsp+190h+var_158]
0x18000de03  mov     rdx, rdi
0x18000de06  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000de0b  test    ebx, ebx
0x18000de0d  js      loc_18000E045
0x18000de13  mov     rcx, [rsp+190h+StringSid]; hMem
0x18000de18  test    rcx, rcx
0x18000de1b  jz      short loc_18000DE33
0x18000de1d  call    cs:__imp_LocalFree
0x18000de24  nop     dword ptr [rax+rax+00h]
0x18000de29  jmp     short loc_18000DE33
0x18000de2b  test    ebx, ebx
0x18000de2d  js      loc_18000DFE7
0x18000de33  test    sil, sil
0x18000de36  jz      loc_18000E04F
0x18000de3c  mov     r8, [rbp+90h+var_110]; __int64
0x18000de40  lea     r9, [rsp+190h+var_160]; bool *
0x18000de45  mov     rdx, [rbp+90h+var_A0]; __int64
0x18000de49  lea     rcx, [rsp+190h+var_148]; struct StateRepository::Cache::Manager_NoThrow *
0x18000de4e  mov     [rsp+190h+var_160], dil
0x18000de53  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x18000de58  mov     ebx, eax
0x18000de5a  test    eax, eax
0x18000de5c  js      loc_18000E060
0x18000de62  cmp     [rsp+190h+var_160], dil
0x18000de67  jz      loc_18000DF48
0x18000de6d  lea     rcx, [rbp+90h+var_110]; this
0x18000de71  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18000de76  mov     ebx, edi
0x18000de78  jmp     loc_18000DBA4
0x18000de7d  mov     rcx, [rbp+98h]; this
0x18000de84  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000de8b  mov     edx, 0DCh; void *
0x18000de90  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de95  mov     rcx, [rsp+190h+StringSid]; hMem
0x18000de9a  mov     ebx, eax
0x18000de9c  test    rcx, rcx
0x18000de9f  jz      short loc_18000DE2B
0x18000dea1  call    cs:__imp_LocalFree
0x18000dea8  nop     dword ptr [rax+rax+00h]
0x18000dead  jmp     loc_18000DE2B
0x18000deb2  mov     edx, 48Dh; void *
0x18000deb7  lea     rdi, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000debe  mov     rcx, [rbp+98h]; this
0x18000dec5  mov     r9d, ebx; char *
0x18000dec8  mov     r8, rdi; unsigned int
0x18000decb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ded0  mov     edx, 0D74h; void *
0x18000ded5  mov     r9d, ebx; char *
0x18000ded8  mov     rcx, [rbp+98h]; this
0x18000dedf  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18000dee6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000deeb  jmp     loc_18000DCE8
0x18000def0  mov     rax, [r15]
0x18000def3  lea     r8, [rsp+190h+var_150]
0x18000def8  mov     rcx, r15
0x18000defb  mov     [rsp+190h+var_150], di
0x18000df00  mov     rax, [rax+28h]
0x18000df04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df09  mov     ebx, eax
0x18000df0b  test    eax, eax
0x18000df0d  jns     loc_18000DD34
0x18000df13  mov     r9d, eax
0x18000df16  mov     edx, 0D90h
0x18000df1b  jmp     short loc_18000DED8
0x18000df1d  test    dword ptr [rbp+90h+var_F8+4], 1000h
0x18000df24  jnz     loc_18000DE6D
0x18000df2a  test    dword ptr [rbp+90h+var_F0], 100h
0x18000df31  jnz     loc_18000DE6D
0x18000df37  lea     rax, aPackageLsIsNot_0; "Package %ls is not singleton or system "...
0x18000df3e  mov     edx, 0D81h
0x18000df43  jmp     loc_18000DCC3
0x18000df48  lea     rax, aPackageLsIsNot; "Package %ls is not user registered"
0x18000df4f  mov     edx, 0DA6h
0x18000df54  jmp     loc_18000DCC3
0x18000df59  mov     rcx, [rbp+98h]; this
0x18000df60  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000df67  mov     r9d, eax; char *
0x18000df6a  mov     edx, 9Bh; void *
0x18000df6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df74  xor     edi, edi
0x18000df76  jmp     loc_18000DDFE
0x18000df7b  mov     rcx, [rbp+98h]; this
0x18000df82  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000df89  mov     r9d, eax; char *
0x18000df8c  mov     edx, 0A0h; void *
0x18000df91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df96  jmp     loc_18000DDFE
0x18000df9b  mov     edx, 0F5h; void *
0x18000dfa0  mov     rcx, [rbp+98h]; this
0x18000dfa7  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000dfae  mov     r9d, ebx; char *
0x18000dfb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dfb6  mov     rcx, [rbp+98h]; this
0x18000dfbd  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000dfc4  mov     r9d, ebx; char *
0x18000dfc7  mov     edx, 0DEh; void *
0x18000dfcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dfd1  mov     rcx, [rsp+190h+StringSid]; hMem
0x18000dfd6  test    rcx, rcx
0x18000dfd9  jz      short loc_18000DFE7
0x18000dfdb  call    cs:__imp_LocalFree
0x18000dfe2  nop     dword ptr [rax+rax+00h]
0x18000dfe7  mov     edx, 0D9Ah
0x18000dfec  jmp     loc_18000DED5
0x18000dff1  mov     edx, 456h; void *
0x18000dff6  mov     rcx, [rbp+98h]; this
  ... truncated ...
```

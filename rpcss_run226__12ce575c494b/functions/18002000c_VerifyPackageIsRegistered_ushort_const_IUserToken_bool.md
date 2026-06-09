# VerifyPackageIsRegistered(ushort const *,IUserToken *,bool)

- ea: `0x18002000c`
- end: `0x180020590`
- name: `?VerifyPackageIsRegistered@@YAJPEBGPEAUIUserToken@@_N@Z`
- size: `1412`
- prototype: `__int64 __fastcall(char *, struct IUserToken *, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180047f88`

## callees

- `0x18000b428`
- `0x18001ec28`
- `0x18001ec48`
- `0x18001ef44`
- `0x18001f85c`
- `0x18001fb78`
- `0x18002000c`
- `0x180020598`
- `0x180020b3c`
- `0x180020ed0`
- `0x180021454`
- `0x18002ba28`
- `0x18009f6b8`
- `0x1800b27e0`
- `0x1800b3128`
- `0x18010b010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180020318`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180020318`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800203c1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800203f4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800204f0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800203c1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800203f4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800204f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002024a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800203ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800204aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020538`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002024a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800203ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800204aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020538`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002006f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002006f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180020093`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800200e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002016b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002029c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180020093`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800200e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002016b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002029c`

## string_xrefs

- `0x1800200c3`: `onecore\com\combase\catalog\services.cxx`
- `0x180020268`: `onecore\com\combase\catalog\services.cxx`
- `0x18002055b`: `onecore\com\combase\catalog\services.cxx`
- `0x180020404`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180020517`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800203d3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18002048c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800204bc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800204d2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800200a8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall VerifyPackageIsRegistered(char *a1, struct IUserToken *a2, char a3)
{
  int SelfSid; // ebx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v10; // rcx
  const char *v11; // rax
  __int64 v12; // rdx
  bool v13; // si
  ProcessToken *v14; // rcx
  PSID v15; // rdi
  int v16; // eax
  __int64 v17; // rcx
  bool v18; // si
  const char *v19; // r9
  __int64 v20; // rdi
  int v21; // eax
  __int64 v22; // r8
  ProcessToken *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  ProcessToken *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  ProcessToken *v31; // rcx
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  bool v35[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  ProcessToken *v37; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v41; // [rsp+60h] [rbp-A0h]
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  char v43; // [rsp+70h] [rbp-90h]
  __int64 v44[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+90h] [rbp-70h]
  __int64 v46; // [rsp+98h] [rbp-68h]
  __int64 v47; // [rsp+A0h] [rbp-60h]
  __int64 v48; // [rsp+A8h] [rbp-58h]
  __int64 v49; // [rsp+B0h] [rbp-50h]
  __int64 v50; // [rsp+B8h] [rbp-48h]
  __int128 v51; // [rsp+C0h] [rbp-40h]
  int v52; // [rsp+D0h] [rbp-30h]
  __int64 v53; // [rsp+D8h] [rbp-28h]
  __int64 v54; // [rsp+E0h] [rbp-20h]
  __int64 v55; // [rsp+F0h] [rbp-10h] BYREF
  char v56[72]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v57; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  if ( g_disableCatalogPackageRegistrationChecks )
    return 0;
  v36 = 0;
  v41 = &v36;
  v42 = 0;
  v43 = 1;
  SelfSid = SRCacheManager_Open(0, &v42);
  if ( v43 )
  {
    v7 = *v41;
    *v41 = v42;
    if ( v7 )
      SRCacheManager_Close();
  }
  if ( SelfSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)SelfSid,
      v32);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6F,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)(unsigned int)SelfSid,
      v33);
LABEL_7:
    v8 = v36;
    v36 = 0;
    if ( v8 )
      SRCacheManager_Close();
    return (unsigned int)SelfSid;
  }
  v45 = 0;
  *(_OWORD *)v44 = 0;
  v51 = 0;
  v46 = 0;
  v47 = 0;
  v13 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v35[0] = 0;
  Sid = 0;
  SelfSid = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
              (struct StateRepository::Cache::Manager_NoThrow *)&v36,
              (const unsigned __int16 *)a1,
              (__int64 *)&Sid);
  if ( SelfSid < 0 )
  {
    v24 = 1165;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)SelfSid,
      v32);
    v25 = 3444;
    goto LABEL_69;
  }
  v15 = Sid;
  if ( !Sid )
    goto LABEL_25;
  v37 = 0;
  v16 = StateRepository::Cache::Entity::Package_NoThrow::Open(
          (struct StateRepository::Cache::Manager_NoThrow *)&v36,
          (__int64)Sid,
          (struct StateRepository::Cache::Context_NoThrow *)&v37,
          v35);
  SelfSid = v16;
  if ( v16 < 0 )
  {
    v30 = 1110;
LABEL_64:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v16,
      v32);
    v31 = v37;
    v37 = 0;
    if ( v31 )
      SRCacheContext_Close();
    v24 = 1168;
    goto LABEL_48;
  }
  v13 = v35[0];
  if ( v35[0] )
  {
    v16 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v37, v44, 0, v15);
    SelfSid = v16;
    if ( v16 < 0 )
    {
      v30 = 1115;
      goto LABEL_64;
    }
  }
  v14 = v37;
  v37 = 0;
  if ( v14 )
    SRCacheContext_Close();
LABEL_25:
  if ( !v13 || (v46 & 0x800000000LL) == 0 )
  {
    v11 = "Package %ls is not machine registered";
    v12 = 3449;
    goto LABEL_27;
  }
  if ( a3 )
  {
    if ( (v46 & 0x100000000000LL) == 0 && (v47 & 0x100) == 0 )
    {
      v11 = "Package %ls is not singleton or system registered";
      v12 = 3457;
      goto LABEL_27;
    }
LABEL_14:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v44);
    v10 = v36;
    v36 = 0;
    if ( v10 )
      SRCacheManager_Close();
    return 0;
  }
  if ( (v47 & 0x1000) != 0 )
    goto LABEL_14;
  Sid = 0;
  if ( a2 )
  {
    v26 = *(_QWORD *)a2;
    *(_WORD *)v35 = 0;
    SelfSid = (*(__int64 (__fastcall **)(struct IUserToken *, PSID *, bool *))(v26 + 40))(a2, &Sid, v35);
    if ( SelfSid >= 0 )
      goto LABEL_35;
    v25 = 3472;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)(unsigned int)SelfSid,
      v32);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v44);
    goto LABEL_7;
  }
  SelfSid = ProcessToken::GetSelfSid(v14, &Sid);
  if ( SelfSid < 0 )
  {
    v25 = 3476;
    goto LABEL_69;
  }
LABEL_35:
  v55 = 0;
  memset_0(v56, 0, 0x44u);
  v57 = 0;
  v18 = 0;
  v35[0] = 0;
  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v40 = 0;
    SelfSid = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
                (struct StateRepository::Cache::Manager_NoThrow *)&v36,
                StringSid,
                &v40);
    if ( SelfSid < 0 )
    {
      v29 = 245;
    }
    else
    {
      v20 = v40;
      if ( !v40 )
      {
LABEL_43:
        if ( StringSid )
          LocalFree(StringSid);
        goto LABEL_11;
      }
      v37 = 0;
      v21 = StateRepository::Cache::Entity::User_NoThrow::Open(
              (struct StateRepository::Cache::Manager_NoThrow *)&v36,
              v40,
              (struct StateRepository::Cache::Context_NoThrow *)&v37,
              v35);
      SelfSid = v21;
      if ( v21 < 0 )
      {
        v27 = 155;
      }
      else
      {
        v18 = v35[0];
        if ( !v35[0]
          || (v21 = StateRepository::Cache::Entity::User_NoThrow::ContextToObject(&v37, &v55, v22, v20),
              SelfSid = v21,
              v21 >= 0) )
        {
          v23 = v37;
          v37 = 0;
          if ( v23 )
            SRCacheContext_Close();
          goto LABEL_43;
        }
        v27 = 160;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (const char *)(unsigned int)v21,
        v32);
      v28 = v37;
      v37 = 0;
      if ( v28 )
        SRCacheContext_Close();
      v29 = 248;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)SelfSid,
      v32);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)SelfSid,
      v34);
    if ( StringSid )
      LocalFree(StringSid);
    goto LABEL_60;
  }
  SelfSid = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xDC,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
              v19);
  if ( StringSid )
    LocalFree(StringSid);
  if ( SelfSid < 0 )
  {
LABEL_60:
    v25 = 3482;
    goto LABEL_69;
  }
LABEL_11:
  if ( !v18 )
  {
    v11 = "Package %ls is not user registered";
    v12 = 3487;
    goto LABEL_27;
  }
  v35[0] = 0;
  SelfSid = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
              (struct StateRepository::Cache::Manager_NoThrow *)&v36,
              v55,
              v44[0],
              v35);
  if ( SelfSid < 0 )
  {
    v25 = 3491;
    goto LABEL_69;
  }
  if ( v35[0] )
    goto LABEL_14;
  v11 = "Package %ls is not user registered";
  v12 = 3494;
LABEL_27:
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
    (const char *)0x80070490LL,
    (int)v11,
    a1);
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v44);
  v17 = v36;
  v36 = 0;
  if ( v17 )
    SRCacheManager_Close();
  return 2147943568LL;
}

```

## disassembly

```asm
0x18002000c  mov     [rsp-8+arg_10], rbx
0x180020011  push    rbp
0x180020012  push    rsi
0x180020013  push    rdi
0x180020014  push    r12
0x180020016  push    r13
0x180020018  push    r14
0x18002001a  push    r15
0x18002001c  lea     rbp, [rsp-60h]
0x180020021  sub     rsp, 160h
0x180020028  mov     rax, cs:__security_cookie
0x18002002f  xor     rax, rsp
0x180020032  mov     [rbp+90h+var_40], rax
0x180020036  xor     r13d, r13d
0x180020039  mov     r12b, r8b
0x18002003c  cmp     cs:?g_disableCatalogPackageRegistrationChecks@@3_NA, r13b; bool g_disableCatalogPackageRegistrationChecks
0x180020043  mov     r14, rdx
0x180020046  mov     r15, rcx
0x180020049  jnz     loc_180020171
0x18002004f  lea     rax, [rsp+190h+var_158]
0x180020054  mov     [rsp+190h+var_158], r13
0x180020059  lea     rdx, [rsp+190h+var_128]
0x18002005e  mov     [rsp+190h+var_130], rax
0x180020063  xor     ecx, ecx
0x180020065  mov     [rsp+190h+var_128], r13
0x18002006a  mov     [rsp+190h+var_120], 1
0x18002006f  call    cs:__imp_SRCacheManager_Open
0x180020075  mov     ebx, eax
0x180020077  cmp     [rsp+190h+var_120], r13b
0x18002007c  jz      short loc_180020099
0x18002007e  mov     r8, [rsp+190h+var_130]
0x180020083  mov     rdx, [rsp+190h+var_128]
0x180020088  mov     rcx, [r8]
0x18002008b  mov     [r8], rdx
0x18002008e  test    rcx, rcx
0x180020091  jz      short loc_180020099
0x180020093  call    cs:__imp_SRCacheManager_Close
0x180020099  test    ebx, ebx
0x18002009b  jns     loc_180020189
0x1800200a1  mov     rcx, [rbp+98h]; this
0x1800200a8  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800200af  mov     r9d, ebx; char *
0x1800200b2  mov     edx, 0A5h; void *
0x1800200b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800200bc  mov     rcx, [rbp+98h]; this
0x1800200c3  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x1800200ca  mov     r9d, ebx; char *
0x1800200cd  mov     edx, 0D6Fh; void *
0x1800200d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800200d7  mov     rcx, [rsp+190h+var_158]
0x1800200dc  mov     [rsp+190h+var_158], r13
0x1800200e1  test    rcx, rcx
0x1800200e4  jz      short loc_1800200EC
0x1800200e6  call    cs:__imp_SRCacheManager_Close
0x1800200ec  mov     eax, ebx
0x1800200ee  mov     rcx, [rbp+90h+var_40]
0x1800200f2  xor     rcx, rsp; StackCookie
0x1800200f5  call    __security_check_cookie
0x1800200fa  mov     rbx, [rsp+190h+arg_10]
0x180020102  add     rsp, 160h
0x180020109  pop     r15
0x18002010b  pop     r14
0x18002010d  pop     r13
0x18002010f  pop     r12
0x180020111  pop     rdi
0x180020112  pop     rsi
0x180020113  pop     rbp
0x180020114  retn
0x180020115  test    ebx, ebx
0x180020117  js      loc_1800204F6
0x18002011d  test    sil, sil
0x180020120  jz      loc_18002057F
0x180020126  mov     r8, [rbp+90h+var_110]; __int64
0x18002012a  lea     r9, [rsp+190h+var_160]; bool *
0x18002012f  mov     rdx, [rbp+90h+var_A0]; __int64
0x180020133  lea     rcx, [rsp+190h+var_158]; struct StateRepository::Cache::Manager_NoThrow *
0x180020138  mov     [rsp+190h+var_160], r13b
0x18002013d  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x180020142  mov     ebx, eax
0x180020144  test    eax, eax
0x180020146  js      loc_18002054F
0x18002014c  cmp     [rsp+190h+var_160], r13b
0x180020151  jz      short loc_180020178
0x180020153  lea     rcx, [rbp+90h+var_110]; this
0x180020157  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002015c  mov     rcx, [rsp+190h+var_158]
0x180020161  mov     [rsp+190h+var_158], r13
0x180020166  test    rcx, rcx
0x180020169  jz      short loc_180020171
0x18002016b  call    cs:__imp_SRCacheManager_Close
0x180020171  xor     eax, eax
0x180020173  jmp     loc_1800200EE
0x180020178  lea     rax, aPackageLsIsNot; "Package %ls is not user registered"
0x18002017f  mov     edx, 0DA6h
0x180020184  jmp     loc_180020261
0x180020189  xorps   xmm0, xmm0
0x18002018c  mov     [rbp+90h+var_100], r13
0x180020190  lea     r8, [rsp+190h+Sid]; __int64 *
0x180020195  movdqa  xmmword ptr [rbp+90h+var_110], xmm0
0x18002019a  mov     rdx, r15; unsigned __int16 *
0x18002019d  movdqa  [rbp+90h+var_D0], xmm0
0x1800201a2  lea     rcx, [rsp+190h+var_158]; struct StateRepository::Cache::Manager_NoThrow *
0x1800201a7  mov     [rbp+90h+var_F8], r13
0x1800201ab  mov     [rbp+90h+var_F0], r13
0x1800201af  mov     sil, r13b
0x1800201b2  mov     [rbp+90h+var_E8], r13
0x1800201b6  mov     [rbp+90h+var_E0], r13
0x1800201ba  mov     [rbp+90h+var_D8], r13
0x1800201be  mov     [rbp+90h+var_C0], r13d
0x1800201c2  mov     [rbp+90h+var_B8], r13
0x1800201c6  mov     [rbp+90h+var_B0], r13
0x1800201ca  mov     [rsp+190h+var_160], r13b
0x1800201cf  mov     [rsp+190h+Sid], r13
0x1800201d4  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x1800201d9  mov     ebx, eax
0x1800201db  test    eax, eax
0x1800201dd  js      loc_1800203FF
0x1800201e3  mov     rdi, [rsp+190h+Sid]
0x1800201e8  test    rdi, rdi
0x1800201eb  jz      short loc_180020250
0x1800201ed  lea     r9, [rsp+190h+var_160]; bool *
0x1800201f2  mov     [rsp+190h+var_150], r13
0x1800201f7  lea     r8, [rsp+190h+var_150]; struct StateRepository::Cache::Context_NoThrow *
0x1800201fc  mov     rdx, rdi; __int64
0x1800201ff  lea     rcx, [rsp+190h+var_158]; struct StateRepository::Cache::Manager_NoThrow *
0x180020204  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180020209  mov     ebx, eax
0x18002020b  test    eax, eax
0x18002020d  js      loc_18002050B
0x180020213  mov     sil, [rsp+190h+var_160]
0x180020218  test    sil, sil
0x18002021b  jz      short loc_18002023B
0x18002021d  mov     r9, rdi
0x180020220  lea     rdx, [rbp+90h+var_110]
0x180020224  xor     r8d, r8d
0x180020227  lea     rcx, [rsp+190h+var_150]
0x18002022c  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180020231  mov     ebx, eax
0x180020233  test    eax, eax
0x180020235  js      loc_180020548
0x18002023b  mov     rcx, [rsp+190h+var_150]
0x180020240  mov     [rsp+190h+var_150], r13
0x180020245  test    rcx, rcx
0x180020248  jz      short loc_180020250
0x18002024a  call    cs:__imp_SRCacheContext_Close
0x180020250  test    sil, sil
0x180020253  jnz     short loc_1800202AC
0x180020255  lea     rax, aPackageLsIsNot_1; "Package %ls is not machine registered"
0x18002025c  mov     edx, 0D79h; void *
0x180020261  mov     rcx, [rbp+98h]; this
0x180020268  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18002026f  mov     [rsp+190h+var_168], r15; char *
0x180020274  mov     r9d, 80070490h; char *
0x18002027a  mov     qword ptr [rsp+190h+var_170], rax; int
0x18002027f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020284  lea     rcx, [rbp+90h+var_110]; this
0x180020288  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002028d  mov     rcx, [rsp+190h+var_158]
0x180020292  mov     [rsp+190h+var_158], r13
0x180020297  test    rcx, rcx
0x18002029a  jz      short loc_1800202A2
0x18002029c  call    cs:__imp_SRCacheManager_Close
0x1800202a2  mov     eax, 80070490h
0x1800202a7  jmp     loc_1800200EE
0x1800202ac  test    byte ptr [rbp+90h+var_F8+4], 8
0x1800202b0  jz      short loc_180020255
0x1800202b2  test    r12b, r12b
0x1800202b5  jnz     loc_180020455
0x1800202bb  test    dword ptr [rbp+90h+var_F0], 1000h
0x1800202c2  jnz     loc_180020153
0x1800202c8  mov     [rsp+190h+Sid], r13
0x1800202cd  lea     rdx, [rsp+190h+Sid]; void **
0x1800202d2  test    r14, r14
0x1800202d5  jnz     loc_180020427
0x1800202db  call    ?GetSelfSid@ProcessToken@@QEAAJPEAPEAX@Z; ProcessToken::GetSelfSid(void * *)
0x1800202e0  mov     ebx, eax
0x1800202e2  test    eax, eax
0x1800202e4  js      loc_180020578
0x1800202ea  xor     edx, edx; Val
0x1800202ec  mov     [rbp+90h+var_A0], r13
0x1800202f0  lea     rcx, [rbp+90h+var_98]; void *
0x1800202f4  lea     r8d, [rdx+44h]; Size
0x1800202f8  call    memset_0
0x1800202fd  mov     rcx, [rsp+190h+Sid]; Sid
0x180020302  lea     rdx, [rsp+190h+StringSid]; StringSid
0x180020307  mov     [rbp+90h+var_50], r13
0x18002030b  mov     sil, r13b
0x18002030e  mov     [rsp+190h+var_160], r13b
0x180020313  mov     [rsp+190h+StringSid], r13
0x180020318  call    cs:__imp_ConvertSidToStringSidW
0x18002031e  test    eax, eax
0x180020320  jz      loc_1800203CC
0x180020326  mov     rdx, [rsp+190h+StringSid]; unsigned __int16 *
0x18002032b  lea     r8, [rsp+190h+var_138]; __int64 *
0x180020330  lea     rcx, [rsp+190h+var_158]; struct StateRepository::Cache::Manager_NoThrow *
0x180020335  mov     [rsp+190h+var_138], r13
0x18002033a  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18002033f  mov     ebx, eax
0x180020341  test    eax, eax
0x180020343  js      loc_180020504
0x180020349  mov     rdi, [rsp+190h+var_138]
0x18002034e  test    rdi, rdi
0x180020351  jz      short loc_1800203B3
0x180020353  lea     r9, [rsp+190h+var_160]; bool *
0x180020358  mov     [rsp+190h+var_150], r13
0x18002035d  lea     r8, [rsp+190h+var_150]; struct StateRepository::Cache::Context_NoThrow *
0x180020362  mov     rdx, rdi; __int64
0x180020365  lea     rcx, [rsp+190h+var_158]; struct StateRepository::Cache::Manager_NoThrow *
0x18002036a  call    ?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002036f  mov     ebx, eax
0x180020371  test    eax, eax
0x180020373  js      loc_180020480
0x180020379  mov     sil, [rsp+190h+var_160]
0x18002037e  test    sil, sil
0x180020381  jz      short loc_18002039E
0x180020383  mov     r9, rdi
0x180020386  lea     rdx, [rbp+90h+var_A0]
0x18002038a  lea     rcx, [rsp+190h+var_150]
0x18002038f  call    ?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)
0x180020394  mov     ebx, eax
0x180020396  test    eax, eax
0x180020398  js      loc_1800204FD
0x18002039e  mov     rcx, [rsp+190h+var_150]
0x1800203a3  mov     [rsp+190h+var_150], r13
0x1800203a8  test    rcx, rcx
0x1800203ab  jz      short loc_1800203B3
0x1800203ad  call    cs:__imp_SRCacheContext_Close
0x1800203b3  mov     rcx, [rsp+190h+StringSid]; hMem
0x1800203b8  test    rcx, rcx
0x1800203bb  jz      loc_18002011D
0x1800203c1  call    cs:__imp_LocalFree
0x1800203c7  jmp     loc_18002011D
0x1800203cc  mov     rcx, [rbp+98h]; this
0x1800203d3  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800203da  mov     edx, 0DCh; void *
0x1800203df  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800203e4  mov     rcx, [rsp+190h+StringSid]; hMem
0x1800203e9  mov     ebx, eax
0x1800203eb  test    rcx, rcx
0x1800203ee  jz      loc_180020115
0x1800203f4  call    cs:__imp_LocalFree
0x1800203fa  jmp     loc_180020115
0x1800203ff  mov     edx, 48Dh; void *
0x180020404  lea     rdi, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002040b  mov     rcx, [rbp+98h]; this
0x180020412  mov     r9d, ebx; char *
0x180020415  mov     r8, rdi; unsigned int
0x180020418  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002041d  mov     edx, 0D74h
0x180020422  jmp     loc_180020554
0x180020427  mov     rax, [r14]
0x18002042a  lea     r8, [rsp+190h+var_160]
0x18002042f  mov     rcx, r14
0x180020432  mov     word ptr [rsp+190h+var_160], r13w
0x180020438  mov     rax, [rax+28h]
0x18002043c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020441  mov     ebx, eax
0x180020443  test    eax, eax
0x180020445  jns     loc_1800202EA
0x18002044b  mov     edx, 0D90h
0x180020450  jmp     loc_180020554
0x180020455  test    dword ptr [rbp+90h+var_F8+4], 1000h
0x18002045c  jnz     loc_180020153
0x180020462  test    dword ptr [rbp+90h+var_F0], 100h
0x180020469  jnz     loc_180020153
0x18002046f  lea     rax, aPackageLsIsNot_0; "Package %ls is not singleton or system "...
0x180020476  mov     edx, 0D81h
0x18002047b  jmp     loc_180020261
0x180020480  mov     edx, 9Bh; void *
0x180020485  mov     rcx, [rbp+98h]; this
0x18002048c  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020493  mov     r9d, eax; char *
0x180020496  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002049b  mov     rcx, [rsp+190h+var_150]
0x1800204a0  mov     [rsp+190h+var_150], r13
0x1800204a5  test    rcx, rcx
0x1800204a8  jz      short loc_1800204B0
0x1800204aa  call    cs:__imp_SRCacheContext_Close
0x1800204b0  mov     edx, 0F8h; void *
0x1800204b5  mov     rcx, [rbp+98h]; this
0x1800204bc  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800204c3  mov     r9d, ebx; char *
0x1800204c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204cb  mov     rcx, [rbp+98h]; this
0x1800204d2  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800204d9  mov     r9d, ebx; char *
0x1800204dc  mov     edx, 0DEh; void *
0x1800204e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204e6  mov     rcx, [rsp+190h+StringSid]; hMem
0x1800204eb  test    rcx, rcx
0x1800204ee  jz      short loc_1800204F6
0x1800204f0  call    cs:__imp_LocalFree
0x1800204f6  mov     edx, 0D9Ah
0x1800204fb  jmp     short loc_180020554
0x1800204fd  mov     edx, 0A0h
0x180020502  jmp     short loc_180020485
0x180020504  mov     edx, 0F5h
0x180020509  jmp     short loc_1800204B5
0x18002050b  mov     edx, 456h; void *
0x180020510  mov     rcx, [rbp+98h]; this
  ... truncated ...
```

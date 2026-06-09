# DesktopAppXActivator::GetWorkingDirectory(HSTRING__ *)

- ea: `0x1800093ec`
- end: `0x180009914`
- name: `?GetWorkingDirectory@DesktopAppXActivator@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@@Z`
- size: `1320`
- prototype: `_QWORD *__fastcall(WCHAR *, _QWORD *, HSTRING)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006f30`

## callees

- `0x180008eb0`
- `0x1800093ec`
- `0x18000991c`
- `0x18000a38c`
- `0x18001b47c`
- `0x18001c214`
- `0x18001cc38`
- `0x18001d578`
- `0x18001d95c`
- `0x18001d97c`
- `0x18001e1c4`
- `0x18001e340`
- `0x1800258f4`
- `0x1800269a4`
- `0x18002b5b0`
- `0x180033d5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800095ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800095ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800094ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800094ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800094c3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800094c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180009439`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180009439`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000945a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800098f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000945a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800098f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180009711`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000972e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180009711`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000972e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009741`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009836`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000984a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000985d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009870`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009883`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009896`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800098a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800098bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800098cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009741`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009836`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000984a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000985d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009870`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009883`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009896`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800098a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800098bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800098cf`

## string_xrefs

- `0x1800095c8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180009611`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800094d1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180009515`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180009651`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18000946b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
_QWORD *__fastcall DesktopAppXActivator::GetWorkingDirectory(WCHAR *a1, _QWORD *a2, HSTRING a3)
{
  char v5; // r12
  int v6; // ebx
  __int64 v7; // rcx
  const char *v8; // r9
  int LastError; // ebx
  int v10; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rsi
  int v17; // eax
  __int64 v18; // rdx
  bool v19; // zf
  __int64 v20; // rcx
  int v21; // eax
  int v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  void *v33; // rcx
  __int64 v34; // rcx
  LPWSTR *p_StringSid; // [rsp+20h] [rbp-A9h]
  int v37; // [rsp+20h] [rbp-A9h]
  __int64 v38; // [rsp+30h] [rbp-99h] BYREF
  int v39; // [rsp+38h] [rbp-91h]
  __int64 v40; // [rsp+40h] [rbp-89h] BYREF
  __int64 v41; // [rsp+48h] [rbp-81h] BYREF
  void *Block; // [rsp+50h] [rbp-79h] BYREF
  __int128 v43; // [rsp+58h] [rbp-71h] BYREF
  __int64 v44[2]; // [rsp+68h] [rbp-61h]
  __int128 v45; // [rsp+78h] [rbp-51h]
  __int128 v46; // [rsp+90h] [rbp-39h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-29h]
  __int64 v48; // [rsp+A8h] [rbp-21h]
  __int128 v49; // [rsp+B0h] [rbp-19h]
  __int128 v50; // [rsp+C0h] [rbp-9h]
  __int128 v51; // [rsp+D0h] [rbp+7h]
  __int128 v52; // [rsp+E0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]
  LPWSTR StringSid; // [rsp+130h] [rbp+67h] BYREF
  _QWORD *v55; // [rsp+138h] [rbp+6Fh]
  __int64 v56; // [rsp+148h] [rbp+7Fh] BYREF

  v55 = a2;
  StringSid = a1;
  v39 = 0;
  v38 = 0;
  v43 = (unsigned __int64)&v38;
  v5 = 1;
  LOBYTE(v44[0]) = 1;
  v6 = SRCacheManager_Open(0, (char *)&v43 + 8);
  if ( LOBYTE(v44[0]) )
  {
    v7 = *(_QWORD *)v43;
    *(_QWORD *)v43 = *((_QWORD *)&v43 + 1);
    if ( v7 )
      SRCacheManager_Close();
  }
  if ( v6 >= 0 )
    v6 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v6,
      (int)p_StringSid);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v6,
      (int)p_StringSid);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block);
  v39 = 2;
  v40 = 0;
  StringSid = 0;
  if ( ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
  {
    v10 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
            (struct StateRepository::Cache::Manager_NoThrow *)&v38,
            StringSid,
            &v40);
    LastError = v10;
    if ( v10 >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      LastError = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (const char *)(unsigned int)v10,
        (int)p_StringSid);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAA,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
                  v8);
    if ( StringSid )
      LocalFree(StringSid);
  }
  if ( LastError < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E9,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)LastError,
      (int)p_StringSid);
  if ( !v40 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)0x80070490LL,
      (int)p_StringSid);
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  if ( !v40 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x573,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      (int)p_StringSid);
    goto LABEL_45;
  }
  v43 = 0;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  LOBYTE(StringSid) = 0;
  v56 = 0;
  v12 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(
          (struct StateRepository::Cache::Manager_NoThrow *)&v38,
          v40,
          StringRawBuffer,
          &v56);
  if ( v12 < 0 )
  {
    v14 = 468;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v12,
      (int)p_StringSid);
    v15 = 1400;
    goto LABEL_27;
  }
  if ( v56 )
  {
    p_StringSid = &StringSid;
    v12 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(&v38, v56, v13, &v43);
    if ( v12 < 0 )
    {
      v14 = 471;
      goto LABEL_26;
    }
  }
  if ( !(_BYTE)StringSid )
    goto LABEL_41;
  v16 = v44[1];
  if ( v44[1] )
  {
    v56 = 0;
    v17 = StateRepository::Cache::Entity::Application_NoThrow::Open(
            (struct StateRepository::Cache::Manager_NoThrow *)&v38,
            v44[1],
            (struct StateRepository::Cache::Context_NoThrow *)&v56,
            (bool *)&StringSid);
    v12 = v17;
    if ( v17 >= 0 )
    {
      if ( !(_BYTE)StringSid
        || (v17 = StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(&v56, &v46, 0, v16),
            v12 = v17,
            v17 >= 0) )
      {
        v19 = v56 == 0;
        v56 = 0;
        if ( !v19 )
          SRCacheContext_Close();
        goto LABEL_41;
      }
      v18 = 347;
    }
    else
    {
      v18 = 342;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v17,
      (int)p_StringSid);
    v19 = v56 == 0;
    v56 = 0;
    if ( !v19 )
      SRCacheContext_Close();
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      (int)p_StringSid);
    v12 = -2147024809;
  }
  v15 = 1404;
LABEL_27:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
    (const char *)(unsigned int)v12,
    v37);
LABEL_41:
  v20 = *((_QWORD *)&v45 + 1);
  *((_QWORD *)&v45 + 1) = 0;
  if ( v20 )
    SRCache_Free();
  if ( (_BYTE)StringSid )
    v5 = 0;
LABEL_45:
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)0x80070057LL,
      (int)p_StringSid);
  v41 = 0;
  *(_QWORD *)&v43 = &v38;
  v45 = 0;
  *((_QWORD *)&v43 + 1) = v40;
  v44[0] = *((_QWORD *)&v46 + 1);
  v44[1] = v46;
  v21 = StateRepository::Cache::Macros::Expand(v51, &v43, &v41);
  v22 = v21;
  if ( v21 >= 0 )
    v22 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v21,
      (int)p_StringSid);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v22,
      (int)p_StringSid);
  *a2 = 0;
  v39 = 3;
  v23 = v41;
  if ( v41 )
  {
    v24 = wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &StringSid,
            v41,
            -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a2,
      v24);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    v23 = v41;
  }
  v41 = 0;
  if ( v23 )
    SRCache_Free();
  v25 = *((_QWORD *)&v52 + 1);
  *((_QWORD *)&v52 + 1) = 0;
  if ( v25 )
    SRCache_Free();
  v26 = v52;
  *(_QWORD *)&v52 = 0;
  if ( v26 )
    SRCache_Free();
  v27 = *((_QWORD *)&v51 + 1);
  *((_QWORD *)&v51 + 1) = 0;
  if ( v27 )
    SRCache_Free();
  v28 = v51;
  *(_QWORD *)&v51 = 0;
  if ( v28 )
    SRCache_Free();
  v29 = *((_QWORD *)&v50 + 1);
  *((_QWORD *)&v50 + 1) = 0;
  if ( v29 )
    SRCache_Free();
  v30 = v50;
  *(_QWORD *)&v50 = 0;
  if ( v30 )
    SRCache_Free();
  v31 = v49;
  *(_QWORD *)&v49 = 0;
  if ( v31 )
    SRCache_Free();
  v32 = v48;
  v48 = 0;
  if ( v32 )
    SRCache_Free();
  v33 = Block;
  Block = 0;
  if ( v33 )
    operator delete(v33);
  v34 = v38;
  v38 = 0;
  if ( v34 )
    SRCacheManager_Close();
  return a2;
}

```

## disassembly

```asm
0x1800093ec  mov     [rsp-8+arg_8], rdx
0x1800093f1  mov     [rsp-8+StringSid], rcx
0x1800093f6  push    rbp
0x1800093f7  push    rbx
0x1800093f8  push    rsi
0x1800093f9  push    rdi
0x1800093fa  push    r12
0x1800093fc  push    r13
0x1800093fe  push    r15
0x180009400  lea     rbp, [rsp-27h]
0x180009405  sub     rsp, 0F0h
0x18000940c  mov     rdi, r8
0x18000940f  mov     r15, rdx
0x180009412  xor     r13d, r13d
0x180009415  mov     [rsp+120h+var_E8], r13d
0x18000941a  mov     [rsp+120h+var_F0], r13
0x18000941f  lea     rax, [rsp+120h+var_F0]
0x180009424  mov     qword ptr [rbp+57h+var_C8], rax
0x180009428  mov     qword ptr [rbp+57h+var_C8+8], r13
0x18000942c  mov     r12b, 1
0x18000942f  mov     byte ptr [rbp+57h+var_B8], r12b
0x180009433  lea     rdx, [rbp+57h+var_C8+8]
0x180009437  xor     ecx, ecx
0x180009439  call    cs:__imp_SRCacheManager_Open
0x18000943f  mov     ebx, eax
0x180009441  cmp     byte ptr [rbp+57h+var_B8], r13b
0x180009445  jz      short loc_180009460
0x180009447  mov     rdx, qword ptr [rbp+57h+var_C8]
0x18000944b  mov     rcx, [rdx]
0x18000944e  mov     rax, qword ptr [rbp+57h+var_C8+8]
0x180009452  mov     [rdx], rax
0x180009455  test    rcx, rcx
0x180009458  jz      short loc_180009460
0x18000945a  call    cs:__imp_SRCacheManager_Close
0x180009460  test    ebx, ebx
0x180009462  jns     short loc_18000947E
0x180009464  mov     rcx, [rbp+5Fh]; this
0x180009468  mov     r9d, ebx; char *
0x18000946b  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009472  mov     edx, 0A5h; void *
0x180009477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000947c  jmp     short loc_180009481
0x18000947e  mov     ebx, r13d
0x180009481  mov     rcx, [rbp+5Fh]; this
0x180009485  test    ebx, ebx
0x180009487  jns     short loc_18000949E
0x180009489  mov     r9d, ebx; char *
0x18000948c  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180009493  mov     edx, 1E5h; void *
0x180009498  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000949e  lea     rcx, [rbp+57h+Block]
0x1800094a2  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x1800094a7  mov     [rsp+120h+var_E8], 2
0x1800094af  mov     [rsp+120h+var_E0], r13
0x1800094b4  mov     [rbp+57h+StringSid], r13
0x1800094b8  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800094bc  mov     rcx, [rbp+57h+Block]
0x1800094c0  mov     rcx, [rcx]; Sid
0x1800094c3  call    cs:__imp_ConvertSidToStringSidW
0x1800094c9  test    eax, eax
0x1800094cb  jnz     short loc_1800094F5
0x1800094cd  mov     rcx, [rbp+5Fh]; this
0x1800094d1  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800094d8  mov     edx, 0AAh; void *
0x1800094dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800094e2  mov     ebx, eax
0x1800094e4  mov     rcx, [rbp+57h+StringSid]; hMem
0x1800094e8  test    rcx, rcx
0x1800094eb  jz      short loc_18000953D
0x1800094ed  call    cs:__imp_LocalFree
0x1800094f3  jmp     short loc_18000953D
0x1800094f5  lea     r8, [rsp+120h+var_E0]; __int64 *
0x1800094fa  mov     rdx, [rbp+57h+StringSid]; unsigned __int16 *
0x1800094fe  lea     rcx, [rsp+120h+var_F0]; struct StateRepository::Cache::Manager_NoThrow *
0x180009503  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180009508  mov     ebx, eax
0x18000950a  test    eax, eax
0x18000950c  jns     short loc_180009531
0x18000950e  mov     rcx, [rbp+5Fh]; this
0x180009512  mov     r9d, eax; char *
0x180009515  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000951c  mov     edx, 0ACh; void *
0x180009521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009526  lea     rcx, [rbp+57h+StringSid]
0x18000952a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000952f  jmp     short loc_18000953D
0x180009531  lea     rcx, [rbp+57h+StringSid]
0x180009535  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000953a  mov     ebx, r13d
0x18000953d  mov     rcx, [rbp+5Fh]; this
0x180009541  test    ebx, ebx
0x180009543  jns     short loc_18000955A
0x180009545  mov     r9d, ebx; char *
0x180009548  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x18000954f  mov     edx, 1E9h; void *
0x180009554  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000955a  cmp     [rsp+120h+var_E0], r13
0x18000955f  setz    al
0x180009562  mov     rcx, [rbp+5Fh]; this
0x180009566  test    al, al
0x180009568  jz      short loc_180009582
0x18000956a  mov     r9d, 80070490h; char *
0x180009570  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180009577  mov     edx, 1EAh; void *
0x18000957c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009582  xorps   xmm0, xmm0
0x180009585  movdqa  [rbp+57h+var_90], xmm0
0x18000958a  mov     [rbp+57h+var_80], r13
0x18000958e  mov     [rbp+57h+var_78], r13
0x180009592  movdqa  [rbp+57h+var_70], xmm0
0x180009597  xorps   xmm1, xmm1
0x18000959a  movdqa  [rbp+57h+var_60], xmm1
0x18000959f  movdqa  [rbp+57h+var_50], xmm0
0x1800095a4  movdqa  [rbp+57h+var_40], xmm1
0x1800095a9  xor     edx, edx; length
0x1800095ab  mov     rcx, rdi; string
0x1800095ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800095b4  mov     rdx, [rsp+120h+var_E0]; __int64
0x1800095b9  test    rdx, rdx
0x1800095bc  jnz     short loc_1800095E1
0x1800095be  mov     rcx, [rbp+5Fh]; this
0x1800095c2  mov     r9d, 80070057h; char *
0x1800095c8  lea     rdi, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800095cf  mov     r8, rdi; unsigned int
0x1800095d2  mov     edx, 573h; void *
0x1800095d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095dc  jmp     loc_180009750
0x1800095e1  xorps   xmm0, xmm0
0x1800095e4  movdqu  [rbp+57h+var_C8], xmm0
0x1800095e9  xorps   xmm1, xmm1
0x1800095ec  movdqu  xmmword ptr [rbp+57h+var_B8], xmm1
0x1800095f1  movdqu  [rbp+57h+var_A8], xmm0
0x1800095f6  mov     byte ptr [rbp+57h+StringSid], r13b
0x1800095fa  mov     [rbp+57h+arg_18], r13
0x1800095fe  lea     r9, [rbp+57h+arg_18]; __int64 *
0x180009602  mov     r8, rax; unsigned __int16 *
0x180009605  lea     rcx, [rsp+120h+var_F0]; struct StateRepository::Cache::Manager_NoThrow *
0x18000960a  call    ?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)
0x18000960f  mov     ebx, eax
0x180009611  lea     rdi, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009618  test    eax, eax
0x18000961a  jns     short loc_180009623
0x18000961c  mov     edx, 1D4h
0x180009621  jmp     short loc_18000964E
0x180009623  mov     rdx, [rbp+57h+arg_18]
0x180009627  test    rdx, rdx
0x18000962a  jz      short loc_18000967A
0x18000962c  lea     rax, [rbp+57h+StringSid]
0x180009630  mov     qword ptr [rsp+120h+var_100], rax; int
0x180009635  lea     r9, [rbp+57h+var_C8]
0x180009639  lea     rcx, [rsp+120h+var_F0]
0x18000963e  call    ?Get@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x180009643  mov     ebx, eax
0x180009645  test    eax, eax
0x180009647  jns     short loc_18000967A
0x180009649  mov     edx, 1D7h; void *
0x18000964e  mov     r9d, ebx; char *
0x180009651  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009658  mov     rcx, [rbp+5Fh]; this
0x18000965c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009661  mov     edx, 578h; void *
0x180009666  mov     r8, rdi; unsigned int
0x180009669  mov     r9d, ebx; char *
0x18000966c  mov     rcx, [rbp+5Fh]; this
0x180009670  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009675  jmp     loc_180009734
0x18000967a  cmp     byte ptr [rbp+57h+StringSid], r13b
0x18000967e  jz      loc_180009734
0x180009684  mov     rsi, [rbp+57h+var_B8+8]
0x180009688  test    rsi, rsi
0x18000968b  jnz     short loc_1800096AB
0x18000968d  mov     rcx, [rbp+5Fh]; this
0x180009691  mov     r9d, 80070057h; char *
0x180009697  mov     r8, rdi; unsigned int
0x18000969a  mov     edx, 153h; void *
0x18000969f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096a4  mov     ebx, 80070057h
0x1800096a9  jmp     short loc_180009717
0x1800096ab  mov     [rbp+57h+arg_18], r13
0x1800096af  lea     r9, [rbp+57h+StringSid]; bool *
0x1800096b3  lea     r8, [rbp+57h+arg_18]; struct StateRepository::Cache::Context_NoThrow *
0x1800096b7  mov     rdx, rsi; __int64
0x1800096ba  lea     rcx, [rsp+120h+var_F0]; struct StateRepository::Cache::Manager_NoThrow *
0x1800096bf  call    ?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800096c4  mov     ebx, eax
0x1800096c6  test    eax, eax
0x1800096c8  jns     short loc_1800096D1
0x1800096ca  mov     edx, 156h
0x1800096cf  jmp     short loc_1800096F5
0x1800096d1  cmp     byte ptr [rbp+57h+StringSid], r13b
0x1800096d5  jz      short loc_180009721
0x1800096d7  mov     r9, rsi
0x1800096da  xor     r8d, r8d
0x1800096dd  lea     rdx, [rbp+57h+var_90]
0x1800096e1  lea     rcx, [rbp+57h+arg_18]
0x1800096e5  call    ?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)
0x1800096ea  mov     ebx, eax
0x1800096ec  test    eax, eax
0x1800096ee  jns     short loc_180009721
0x1800096f0  mov     edx, 15Bh; void *
0x1800096f5  mov     r9d, eax; char *
0x1800096f8  mov     r8, rdi; unsigned int
0x1800096fb  mov     rcx, [rbp+5Fh]; this
0x1800096ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009704  mov     rcx, [rbp+57h+arg_18]
0x180009708  test    rcx, rcx
0x18000970b  mov     [rbp+57h+arg_18], r13
0x18000970f  jz      short loc_180009717
0x180009711  call    cs:__imp_SRCacheContext_Close
0x180009717  mov     edx, 57Ch
0x18000971c  jmp     loc_180009666
0x180009721  mov     rcx, [rbp+57h+arg_18]
0x180009725  test    rcx, rcx
0x180009728  mov     [rbp+57h+arg_18], r13
0x18000972c  jz      short loc_180009734
0x18000972e  call    cs:__imp_SRCacheContext_Close
0x180009734  mov     rcx, qword ptr [rbp+57h+var_A8+8]
0x180009738  mov     qword ptr [rbp+57h+var_A8+8], r13
0x18000973c  test    rcx, rcx
0x18000973f  jz      short loc_180009747
0x180009741  call    cs:__imp_SRCache_Free
0x180009747  cmp     byte ptr [rbp+57h+StringSid], r13b
0x18000974b  jz      short loc_180009750
0x18000974d  mov     r12b, r13b
0x180009750  mov     rcx, [rbp+5Fh]; this
0x180009754  test    r12b, r12b
0x180009757  jz      short loc_180009771
0x180009759  mov     r9d, 80070057h; char *
0x18000975f  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180009766  mov     edx, 1F4h; void *
0x18000976b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009771  mov     [rsp+120h+var_D8], r13
0x180009776  lea     rax, [rsp+120h+var_F0]
0x18000977b  mov     qword ptr [rbp+57h+var_C8], rax
0x18000977f  xorps   xmm0, xmm0
0x180009782  movdqu  [rbp+57h+var_A8], xmm0
0x180009787  mov     rax, [rsp+120h+var_E0]
0x18000978c  mov     qword ptr [rbp+57h+var_C8+8], rax
0x180009790  mov     rax, qword ptr [rbp+57h+var_90+8]
0x180009794  mov     [rbp+57h+var_B8], rax
0x180009798  mov     rax, qword ptr [rbp+57h+var_90]
0x18000979c  mov     [rbp+57h+var_B8+8], rax
0x1800097a0  lea     r8, [rsp+120h+var_D8]
0x1800097a5  lea     rdx, [rbp+57h+var_C8]
0x1800097a9  mov     rcx, qword ptr [rbp+57h+var_50]
0x1800097ad  call    ?Expand@Macros@Cache@StateRepository@@YAJPEBGAEAVMacroExpandData_NoThrow@123@AEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@W4SRCacheExpandMacrosFlags@@@Z; StateRepository::Cache::Macros::Expand(ushort const *,StateRepository::Cache::Macros::MacroExpandData_NoThrow &,wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>> &,SRCacheExpandMacrosFlags)
0x1800097b2  mov     ebx, eax
0x1800097b4  test    eax, eax
0x1800097b6  jns     short loc_1800097CE
0x1800097b8  mov     rcx, [rbp+5Fh]; this
0x1800097bc  mov     r9d, eax; char *
0x1800097bf  mov     r8, rdi; unsigned int
0x1800097c2  mov     edx, 5A7h; void *
0x1800097c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097cc  jmp     short loc_1800097D1
0x1800097ce  mov     ebx, r13d
0x1800097d1  mov     rcx, [rbp+5Fh]; this
0x1800097d5  test    ebx, ebx
0x1800097d7  jns     short loc_1800097EE
0x1800097d9  mov     r9d, ebx; char *
0x1800097dc  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x1800097e3  mov     edx, 1F6h; void *
0x1800097e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800097ee  mov     [r15], r13
0x1800097f1  mov     [rsp+120h+var_E8], 3
0x1800097f9  mov     rcx, [rsp+120h+var_D8]
0x1800097fe  test    rcx, rcx
0x180009801  jz      short loc_18000982C
0x180009803  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009807  mov     rdx, rcx
0x18000980a  lea     rcx, [rbp+57h+StringSid]
0x18000980e  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180009813  mov     rdx, rax
0x180009816  mov     rcx, r15
0x180009819  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000981e  lea     rcx, [rbp+57h+StringSid]
0x180009822  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180009827  mov     rcx, [rsp+120h+var_D8]
0x18000982c  mov     [rsp+120h+var_D8], r13
0x180009831  test    rcx, rcx
0x180009834  jz      short loc_18000983D
0x180009836  call    cs:__imp_SRCache_Free
0x18000983c  nop
0x18000983d  mov     rcx, qword ptr [rbp+57h+var_40+8]
0x180009841  mov     qword ptr [rbp+57h+var_40+8], r13
0x180009845  test    rcx, rcx
0x180009848  jz      short loc_180009850
0x18000984a  call    cs:__imp_SRCache_Free
0x180009850  mov     rcx, qword ptr [rbp+57h+var_40]
0x180009854  mov     qword ptr [rbp+57h+var_40], r13
0x180009858  test    rcx, rcx
0x18000985b  jz      short loc_180009863
0x18000985d  call    cs:__imp_SRCache_Free
0x180009863  mov     rcx, qword ptr [rbp+57h+var_50+8]
0x180009867  mov     qword ptr [rbp+57h+var_50+8], r13
0x18000986b  test    rcx, rcx
0x18000986e  jz      short loc_180009876
0x180009870  call    cs:__imp_SRCache_Free
0x180009876  mov     rcx, qword ptr [rbp+57h+var_50]
0x18000987a  mov     qword ptr [rbp+57h+var_50], r13
  ... truncated ...
```

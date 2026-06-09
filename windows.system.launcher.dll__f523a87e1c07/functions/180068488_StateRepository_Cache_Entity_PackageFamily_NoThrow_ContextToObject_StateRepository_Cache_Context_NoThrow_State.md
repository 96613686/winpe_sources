# StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)

- ea: `0x180068488`
- end: `0x180068667`
- name: `?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800d7aec`

## callees

- `0x18000d60c`
- `0x180010c04`
- `0x1800326f0`
- `0x18003506c`
- `0x180035100`
- `0x180067258`
- `0x180068488`
- `0x18008e5a2`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006855e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006860f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006855e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006860f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800685dd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800685dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180068598`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180068598`

## string_xrefs

- `0x1800684e1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180068539`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800685b1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18006850b`: `PackageSID`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        _QWORD *a2,
        const WCHAR *a3,
        __int64 a4)
{
  int Field; // ebx
  __int64 v8; // rdx
  LPCWSTR v10; // rcx
  LPCWSTR v11; // rcx
  BOOL v12; // ebx
  const char *v13; // r9
  PSID v14; // rbx
  DWORD LengthSid; // eax
  PSID pSid; // [rsp+20h] [rbp-28h] BYREF
  void *p_StringSid; // [rsp+28h] [rbp-20h] BYREF
  PSID Sid; // [rsp+30h] [rbp-18h] BYREF
  char v19; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  LPCWSTR StringSid; // [rsp+90h] [rbp+48h] BYREF

  StringSid = a3;
  Sid = 0;
  p_StringSid = a2 + 1;
  v19 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFamilyName", (unsigned __int16 **)&Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&p_StringSid);
  if ( Field < 0 )
  {
    v8 = 775;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)Field,
      (int)pSid);
    return (unsigned int)Field;
  }
  StringSid = 0;
  p_StringSid = &StringSid;
  Sid = 0;
  v19 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageSID", (unsigned __int16 **)&Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&p_StringSid);
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)Field,
      (int)pSid);
    goto LABEL_7;
  }
  v11 = StringSid;
  if ( StringSid )
  {
    pSid = 0;
    p_StringSid = &pSid;
    Sid = 0;
    v19 = 1;
    v12 = ConvertStringSidToSidW(StringSid, &Sid);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_StringSid);
    if ( !v12 )
    {
      Field = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x315,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
                v13);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid);
LABEL_7:
      v10 = StringSid;
      StringSid = 0;
      if ( v10 )
        SRCache_Free(v10);
      return (unsigned int)Field;
    }
    v14 = pSid;
    LengthSid = GetLengthSid(pSid);
    memcpy_0(a2 + 2, v14, LengthSid);
    a2[11] = a2 + 2;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid);
    v11 = StringSid;
  }
  else
  {
    a2[11] = 0;
  }
  StringSid = 0;
  if ( v11 )
    SRCache_Free(v11);
  Sid = 0;
  p_StringSid = a2 + 12;
  v19 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Publisher", (unsigned __int16 **)&Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&p_StringSid);
  if ( Field < 0 )
  {
    v8 = 796;
    goto LABEL_3;
  }
  *a2 = a4;
  return 0;
}

```

## disassembly

```asm
0x180068488  mov     [rsp-30h+StringSid], r8
0x18006848d  push    rbp
0x18006848e  push    rbx
0x18006848f  push    rsi
0x180068490  push    rdi
0x180068491  push    r14
0x180068493  push    r15
0x180068495  mov     rbp, rsp
0x180068498  sub     rsp, 48h
0x18006849c  lea     rax, [rdx+8]
0x1800684a0  mov     [rbp+Sid], 0
0x1800684a8  mov     rsi, rdx
0x1800684ab  mov     [rbp+var_20], rax
0x1800684af  lea     rdx, aPackagefamilyn_0; "PackageFamilyName"
0x1800684b6  mov     [rbp+var_10], 1
0x1800684ba  lea     r8, [rbp+Sid]; unsigned __int16 **
0x1800684be  mov     r15, r9
0x1800684c1  mov     r14, rcx
0x1800684c4  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800684c9  lea     rcx, [rbp+var_20]
0x1800684cd  mov     ebx, eax
0x1800684cf  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800684d4  test    ebx, ebx
0x1800684d6  jns     short loc_1800684F7
0x1800684d8  mov     edx, 307h; void *
0x1800684dd  mov     rcx, [rbp+30h]; this
0x1800684e1  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800684e8  mov     r9d, ebx; char *
0x1800684eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800684f0  mov     eax, ebx
0x1800684f2  jmp     loc_18006865A
0x1800684f7  lea     rax, [rbp+StringSid]
0x1800684fb  mov     [rbp+StringSid], 0
0x180068503  lea     r8, [rbp+Sid]; unsigned __int16 **
0x180068507  mov     [rbp+var_20], rax
0x18006850b  lea     rdx, aPackagesid; "PackageSID"
0x180068512  mov     [rbp+Sid], 0
0x18006851a  mov     rcx, r14; this
0x18006851d  mov     [rbp+var_10], 1
0x180068521  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180068526  lea     rcx, [rbp+var_20]
0x18006852a  mov     ebx, eax
0x18006852c  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180068531  test    ebx, ebx
0x180068533  jns     short loc_180068566
0x180068535  mov     rcx, [rbp+30h]; this
0x180068539  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180068540  mov     r9d, ebx; char *
0x180068543  mov     edx, 30Dh; void *
0x180068548  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006854d  mov     rcx, [rbp+StringSid]
0x180068551  mov     [rbp+StringSid], 0
0x180068559  test    rcx, rcx
0x18006855c  jz      short loc_1800684F0
0x18006855e  call    cs:__imp_SRCache_Free
0x180068564  jmp     short loc_1800684F0
0x180068566  mov     rcx, [rbp+StringSid]; StringSid
0x18006856a  test    rcx, rcx
0x18006856d  jnz     short loc_180068578
0x18006856f  mov     [rsi+58h], rcx
0x180068573  jmp     loc_180068602
0x180068578  lea     rax, [rbp+pSid]
0x18006857c  mov     [rbp+pSid], 0
0x180068584  lea     rdx, [rbp+Sid]; Sid
0x180068588  mov     [rbp+var_20], rax
0x18006858c  mov     [rbp+Sid], 0
0x180068594  mov     [rbp+var_10], 1
0x180068598  call    cs:__imp_ConvertStringSidToSidW
0x18006859e  lea     rcx, [rbp+var_20]
0x1800685a2  mov     ebx, eax
0x1800685a4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800685a9  test    ebx, ebx
0x1800685ab  jnz     short loc_1800685D2
0x1800685ad  mov     rcx, [rbp+30h]; this
0x1800685b1  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800685b8  mov     edx, 315h; void *
0x1800685bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800685c2  lea     rcx, [rbp+pSid]
0x1800685c6  mov     ebx, eax
0x1800685c8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800685cd  jmp     loc_18006854D
0x1800685d2  mov     rbx, [rbp+pSid]
0x1800685d6  lea     rdi, [rsi+10h]
0x1800685da  mov     rcx, rbx; pSid
0x1800685dd  call    cs:__imp_GetLengthSid
0x1800685e3  mov     r8d, eax; Size
0x1800685e6  mov     rdx, rbx; Src
0x1800685e9  mov     rcx, rdi; void *
0x1800685ec  call    memcpy_0
0x1800685f1  lea     rcx, [rbp+pSid]
0x1800685f5  mov     [rsi+58h], rdi
0x1800685f9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800685fe  mov     rcx, [rbp+StringSid]
0x180068602  mov     [rbp+StringSid], 0
0x18006860a  test    rcx, rcx
0x18006860d  jz      short loc_180068615
0x18006860f  call    cs:__imp_SRCache_Free
0x180068615  lea     rax, [rsi+60h]
0x180068619  mov     [rbp+Sid], 0
0x180068621  lea     r8, [rbp+Sid]; unsigned __int16 **
0x180068625  mov     [rbp+var_20], rax
0x180068629  lea     rdx, aPublisher; "Publisher"
0x180068630  mov     [rbp+var_10], 1
0x180068634  mov     rcx, r14; this
0x180068637  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18006863c  lea     rcx, [rbp+var_20]
0x180068640  mov     ebx, eax
0x180068642  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180068647  test    ebx, ebx
0x180068649  jns     short loc_180068655
0x18006864b  mov     edx, 31Ch
0x180068650  jmp     loc_1800684DD
0x180068655  mov     [rsi], r15
0x180068658  xor     eax, eax
0x18006865a  add     rsp, 48h
0x18006865e  pop     r15
0x180068660  pop     r14
0x180068662  pop     rdi
0x180068663  pop     rsi
0x180068664  pop     rbx
0x180068665  pop     rbp
0x180068666  retn
```

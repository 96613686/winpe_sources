# UpdateHandler::RemoteUHProcessHostWrapper::StartDynamicCOMServer(void)

- ea: `0x180036454`
- end: `0x18003661a`
- name: `?StartDynamicCOMServer@RemoteUHProcessHostWrapper@UpdateHandler@@AEAAJXZ`
- size: `454`
- prototype: `__int64 __fastcall(UpdateHandler::RemoteUHProcessHostWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180035a94`

## callees

- `0x180003950`
- `0x18000956c`
- `0x1800103b8`
- `0x180031078`
- `0x180036454`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180036474`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800364ed`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180036474`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800364ed`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800364b4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180036513`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800364b4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180036513`

## string_xrefs

- `0x180036569`: `Software\Classes\CLSID`
- `0x180036529`: `Registering RemoteUHProcessHostRegistrar COM server as CLSID %ws and APPID %ws`
- `0x1800365cf`: `Successfully registered RemoteUHProcessHostRegistrar COM server`

## pseudocode

```c
__int64 __fastcall UpdateHandler::RemoteUHProcessHostWrapper::StartDynamicCOMServer(
        UpdateHandler::RemoteUHProcessHostWrapper *this)
{
  HRESULT Guid; // edi
  __int64 v3; // rdx
  __int64 result; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rcx
  const wchar_t *v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Guid = CoCreateGuid((GUID *)((char *)this + 8));
  if ( Guid < 0 )
  {
    v3 = 515;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)Guid,
      (int)v8);
    return (unsigned int)Guid;
  }
  if ( !StringFromGUID2((const GUID *const)((char *)this + 8), (LPOLESTR)this + 73, 39) )
  {
    v5 = 518;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)0x8007007ALL,
      (int)v8);
    return 2147942522LL;
  }
  Guid = CoCreateGuid((GUID *)this + 14);
  if ( Guid < 0 )
  {
    v3 = 521;
    goto LABEL_3;
  }
  if ( !StringFromGUID2((const GUID *const)this + 14, (LPOLESTR)this + 120, 39) )
  {
    v5 = 523;
    goto LABEL_6;
  }
  WUTrace(0, 0, 4096, 4);
  LODWORD(v8) = (_DWORD)this + 240;
  Guid = RegSetStringValueOnVolatileKey(v6, L"Software\\Classes\\CLSID", (char *)this + 146, L"AppID");
  if ( Guid < 0 )
  {
    v3 = 536;
    goto LABEL_3;
  }
  v8 = L"nt authority\\system";
  Guid = RegSetStringValueOnVolatileKey(v7, L"Software\\Classes\\AppID", (char *)this + 240, L"RunAs");
  if ( Guid < 0 )
  {
    v3 = 544;
    goto LABEL_3;
  }
  Guid = CWuaClassFactoryBase::RegisterClassFactory(this);
  if ( Guid < 0 )
  {
    v3 = 546;
    goto LABEL_3;
  }
  WUTrace(0, 0, 4096, 4);
  result = 0;
  *((_BYTE *)this + 144) = 1;
  return result;
}

```

## disassembly

```asm
0x180036454  mov     rax, rsp
0x180036457  mov     [rax+8], rbx
0x18003645b  mov     [rax+10h], rbp
0x18003645f  mov     [rax+18h], rsi
0x180036463  mov     [rax+20h], rdi
0x180036467  push    r14
0x180036469  sub     rsp, 40h
0x18003646d  mov     rbx, rcx
0x180036470  add     rcx, 8; pguid
0x180036474  call    cs:__imp_CoCreateGuid
0x18003647a  mov     edi, eax
0x18003647c  test    eax, eax
0x18003647e  jns     short loc_1800364A0
0x180036480  mov     edx, 203h; void *
0x180036485  mov     rcx, [rsp+48h]; this
0x18003648a  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180036491  mov     r9d, edi; char *
0x180036494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036499  mov     eax, edi
0x18003649b  jmp     loc_1800365FF
0x1800364a0  lea     r14, [rbx+92h]
0x1800364a7  mov     r8d, 27h ; '''; cchMax
0x1800364ad  mov     rdx, r14; lpsz
0x1800364b0  lea     rcx, [rbx+8]; rguid
0x1800364b4  call    cs:__imp_StringFromGUID2
0x1800364ba  test    eax, eax
0x1800364bc  jnz     short loc_1800364E3
0x1800364be  mov     edx, 206h; void *
0x1800364c3  mov     rcx, [rsp+48h]; this
0x1800364c8  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800364cf  mov     ebx, 8007007Ah
0x1800364d4  mov     r9d, ebx; char *
0x1800364d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800364dc  mov     eax, ebx
0x1800364de  jmp     loc_1800365FF
0x1800364e3  lea     rbp, [rbx+0E0h]
0x1800364ea  mov     rcx, rbp; pguid
0x1800364ed  call    cs:__imp_CoCreateGuid
0x1800364f3  mov     edi, eax
0x1800364f5  test    eax, eax
0x1800364f7  jns     short loc_180036500
0x1800364f9  mov     edx, 209h
0x1800364fe  jmp     short loc_180036485
0x180036500  lea     rsi, [rbx+0F0h]
0x180036507  mov     r8d, 27h ; '''; cchMax
0x18003650d  mov     rdx, rsi; lpsz
0x180036510  mov     rcx, rbp; rguid
0x180036513  call    cs:__imp_StringFromGUID2
0x180036519  test    eax, eax
0x18003651b  jnz     short loc_180036524
0x18003651d  mov     edx, 20Bh
0x180036522  jmp     short loc_1800364C3
0x180036524  mov     [rsp+48h+var_10], rsi
0x180036529  lea     rax, aRegisteringRem; "Registering RemoteUHProcessHostRegistra"...
0x180036530  mov     [rsp+48h+var_18], r14
0x180036535  mov     ebp, 4
0x18003653a  mov     [rsp+48h+var_20], rax
0x18003653f  mov     r9d, ebp
0x180036542  xor     edx, edx
0x180036544  mov     [rsp+48h+var_28], 0
0x18003654d  xor     ecx, ecx
0x18003654f  mov     r8d, 1000h
0x180036555  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003655a  lea     r9, ?c_szAppIdValueName@@3QB_WB; "AppID"
0x180036561  mov     [rsp+48h+var_28], rsi
0x180036566  mov     r8, r14
0x180036569  lea     rdx, ?c_szDynamicCLSIDKey@@3QB_WB; "Software\\Classes\\CLSID"
0x180036570  call    ?RegSetStringValueOnVolatileKey@@YAJPEAUHKEY__@@PEB_W111W4RegistryHiveType@@@Z; RegSetStringValueOnVolatileKey(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x180036575  mov     edi, eax
0x180036577  test    eax, eax
0x180036579  jns     short loc_180036585
0x18003657b  mov     edx, 218h
0x180036580  jmp     loc_180036485
0x180036585  lea     rax, aNtAuthoritySys; "nt authority\\system"
0x18003658c  mov     r8, rsi
0x18003658f  lea     r9, aRunas; "RunAs"
0x180036596  mov     [rsp+48h+var_28], rax
0x18003659b  lea     rdx, ?c_szDynamicAppIDKey@@3QB_WB; "Software\\Classes\\AppID"
0x1800365a2  call    ?RegSetStringValueOnVolatileKey@@YAJPEAUHKEY__@@PEB_W111W4RegistryHiveType@@@Z; RegSetStringValueOnVolatileKey(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x1800365a7  mov     edi, eax
0x1800365a9  test    eax, eax
0x1800365ab  jns     short loc_1800365B7
0x1800365ad  mov     edx, 220h
0x1800365b2  jmp     loc_180036485
0x1800365b7  mov     rcx, rbx; this
0x1800365ba  call    ?RegisterClassFactory@CWuaClassFactoryBase@@QEAAJXZ; CWuaClassFactoryBase::RegisterClassFactory(void)
0x1800365bf  mov     edi, eax
0x1800365c1  test    eax, eax
0x1800365c3  jns     short loc_1800365CF
0x1800365c5  mov     edx, 222h
0x1800365ca  jmp     loc_180036485
0x1800365cf  lea     rax, aSuccessfullyRe; "Successfully registered RemoteUHProcess"...
0x1800365d6  mov     r9d, ebp
0x1800365d9  mov     [rsp+48h+var_20], rax
0x1800365de  xor     edx, edx
0x1800365e0  xor     ecx, ecx
0x1800365e2  mov     [rsp+48h+var_28], 0
0x1800365eb  mov     r8d, 1000h
0x1800365f1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800365f6  xor     eax, eax
0x1800365f8  mov     byte ptr [rbx+90h], 1
0x1800365ff  mov     rbx, [rsp+48h+arg_0]
0x180036604  mov     rbp, [rsp+48h+arg_8]
0x180036609  mov     rsi, [rsp+48h+arg_10]
0x18003660e  mov     rdi, [rsp+48h+arg_18]
0x180036613  add     rsp, 40h
0x180036617  pop     r14
0x180036619  retn
```

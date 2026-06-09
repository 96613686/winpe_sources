# OSDeploymentInformationFactory::StartJITCOMServer(void)

- ea: `0x18001c06c`
- end: `0x18001c229`
- name: `?StartJITCOMServer@OSDeploymentInformationFactory@@QEAAJXZ`
- size: `445`
- prototype: `__int64 __fastcall(OSDeploymentInformationFactory *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016c30`
- `0x18002715c`

## callees

- `0x180003950`
- `0x18000956c`
- `0x1800103b8`
- `0x18001c06c`
- `0x180031078`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001c0a3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001c11b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001c0a3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001c11b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001c0e2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001c15a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001c0e2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001c15a`

## string_xrefs

- `0x18001c170`: `Registering OSDeploymentInformationFactory COM server as CLSID %ws and APPID %ws`
- `0x18001c1b0`: `Software\Classes\CLSID`
- `0x18001c1e4`: `Successfully registered OSDeploymentInformationFactory COM server`

## pseudocode

```c
__int64 __fastcall OSDeploymentInformationFactory::StartJITCOMServer(OSDeploymentInformationFactory *this)
{
  const GUID *v1; // rdi
  HRESULT Guid; // eax
  unsigned int v4; // esi
  __int64 result; // rax
  __int64 v6; // rdx
  int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = (const GUID *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)this + 2) == *(_QWORD *)GUID_NULL.Data4 )
  {
    Guid = CoCreateGuid((GUID *)((char *)this + 8));
    v4 = Guid;
    if ( Guid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInfo"
                      "rmationFactory.cpp",
        (const char *)(unsigned int)Guid,
        v10);
      return v4;
    }
  }
  if ( !StringFromGUID2(v1, (LPOLESTR)this + 149, 39) )
  {
    v6 = 308;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInform"
                    "ationFactory.cpp",
      (const char *)0x8007007ALL,
      v10);
    return 2147942522LL;
  }
  v7 = CoCreateGuid((GUID *)((char *)this + 376));
  if ( v7 < 0 )
  {
    v8 = 311;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInform"
                    "ationFactory.cpp",
      (const char *)(unsigned int)v7,
      v10);
    return (unsigned int)v7;
  }
  if ( !StringFromGUID2((const GUID *const)((char *)this + 376), (LPOLESTR)this + 196, 39) )
  {
    v6 = 313;
    goto LABEL_7;
  }
  WUTrace(0, 0, 4096, 4);
  v7 = RegSetStringValueOnVolatileKey(
         v9,
         (__int64)L"Software\\Classes\\CLSID",
         (__int64)this + 298,
         (__int64)L"AppID",
         (__int64)this + 392);
  if ( v7 < 0 )
  {
    v8 = 326;
    goto LABEL_10;
  }
  v7 = CWuaClassFactoryBase::RegisterClassFactory((IUnknown *)this);
  if ( v7 < 0 )
  {
    v8 = 328;
    goto LABEL_10;
  }
  WUTrace(0, 0, 4096, 4);
  result = 0;
  *((_BYTE *)this + 296) = 1;
  return result;
}

```

## disassembly

```asm
0x18001c06c  mov     [rsp+arg_0], rbx
0x18001c071  mov     [rsp+arg_8], rbp
0x18001c076  mov     [rsp+arg_10], rsi
0x18001c07b  push    rdi
0x18001c07c  sub     rsp, 40h
0x18001c080  lea     rdi, [rcx+8]
0x18001c084  mov     rbx, rcx
0x18001c087  mov     rax, [rdi]
0x18001c08a  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001c091  jnz     short loc_18001C0CF
0x18001c093  mov     rax, [rdi+8]
0x18001c097  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001c09e  jnz     short loc_18001C0CF
0x18001c0a0  mov     rcx, rdi; pguid
0x18001c0a3  call    cs:__imp_CoCreateGuid
0x18001c0a9  mov     esi, eax
0x18001c0ab  test    eax, eax
0x18001c0ad  jns     short loc_18001C0CF
0x18001c0af  mov     rcx, [rsp+48h]; this
0x18001c0b4  lea     r8, aCW1SSrcClientE_11; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001c0bb  mov     r9d, eax; char *
0x18001c0be  mov     edx, 130h; void *
0x18001c0c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c0c8  mov     eax, esi
0x18001c0ca  jmp     loc_18001C214
0x18001c0cf  lea     rbp, [rbx+12Ah]
0x18001c0d6  mov     r8d, 27h ; '''; cchMax
0x18001c0dc  mov     rdx, rbp; lpsz
0x18001c0df  mov     rcx, rdi; rguid
0x18001c0e2  call    cs:__imp_StringFromGUID2
0x18001c0e8  test    eax, eax
0x18001c0ea  jnz     short loc_18001C111
0x18001c0ec  mov     edx, 134h; void *
0x18001c0f1  mov     rcx, [rsp+48h]; this
0x18001c0f6  lea     r8, aCW1SSrcClientE_11; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001c0fd  mov     ebx, 8007007Ah
0x18001c102  mov     r9d, ebx; char *
0x18001c105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c10a  mov     eax, ebx
0x18001c10c  jmp     loc_18001C214
0x18001c111  lea     rsi, [rbx+178h]
0x18001c118  mov     rcx, rsi; pguid
0x18001c11b  call    cs:__imp_CoCreateGuid
0x18001c121  mov     edi, eax
0x18001c123  test    eax, eax
0x18001c125  jns     short loc_18001C147
0x18001c127  mov     edx, 137h; void *
0x18001c12c  mov     rcx, [rsp+48h]; this
0x18001c131  lea     r8, aCW1SSrcClientE_11; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001c138  mov     r9d, edi; char *
0x18001c13b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c140  mov     eax, edi
0x18001c142  jmp     loc_18001C214
0x18001c147  lea     rdi, [rbx+188h]
0x18001c14e  mov     r8d, 27h ; '''; cchMax
0x18001c154  mov     rdx, rdi; lpsz
0x18001c157  mov     rcx, rsi; rguid
0x18001c15a  call    cs:__imp_StringFromGUID2
0x18001c160  test    eax, eax
0x18001c162  jnz     short loc_18001C16B
0x18001c164  mov     edx, 139h
0x18001c169  jmp     short loc_18001C0F1
0x18001c16b  mov     [rsp+48h+var_10], rdi
0x18001c170  lea     rax, aRegisteringOsd; "Registering OSDeploymentInformationFact"...
0x18001c177  mov     [rsp+48h+var_18], rbp
0x18001c17c  mov     esi, 4
0x18001c181  mov     [rsp+48h+var_20], rax
0x18001c186  mov     r9d, esi
0x18001c189  xor     edx, edx
0x18001c18b  mov     [rsp+48h+var_28], 0
0x18001c194  xor     ecx, ecx
0x18001c196  mov     r8d, 1000h
0x18001c19c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001c1a1  lea     r9, aAppid; "AppID"
0x18001c1a8  mov     [rsp+48h+var_28], rdi
0x18001c1ad  mov     r8, rbp
0x18001c1b0  lea     rdx, aSoftwareClasse; "Software\\Classes\\CLSID"
0x18001c1b7  call    ?RegSetStringValueOnVolatileKey@@YAJPEAUHKEY__@@PEB_W111W4RegistryHiveType@@@Z; RegSetStringValueOnVolatileKey(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x18001c1bc  mov     edi, eax
0x18001c1be  test    eax, eax
0x18001c1c0  jns     short loc_18001C1CC
0x18001c1c2  mov     edx, 146h
0x18001c1c7  jmp     loc_18001C12C
0x18001c1cc  mov     rcx, rbx; this
0x18001c1cf  call    ?RegisterClassFactory@CWuaClassFactoryBase@@QEAAJXZ; CWuaClassFactoryBase::RegisterClassFactory(void)
0x18001c1d4  mov     edi, eax
0x18001c1d6  test    eax, eax
0x18001c1d8  jns     short loc_18001C1E4
0x18001c1da  mov     edx, 148h
0x18001c1df  jmp     loc_18001C12C
0x18001c1e4  lea     rax, aSuccessfullyRe_0; "Successfully registered OSDeploymentInf"...
0x18001c1eb  mov     r9d, esi
0x18001c1ee  mov     [rsp+48h+var_20], rax
0x18001c1f3  xor     edx, edx
0x18001c1f5  xor     ecx, ecx
0x18001c1f7  mov     [rsp+48h+var_28], 0
0x18001c200  mov     r8d, 1000h
0x18001c206  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001c20b  xor     eax, eax
0x18001c20d  mov     byte ptr [rbx+128h], 1
0x18001c214  mov     rbx, [rsp+48h+arg_0]
0x18001c219  mov     rbp, [rsp+48h+arg_8]
0x18001c21e  mov     rsi, [rsp+48h+arg_10]
0x18001c223  add     rsp, 40h
0x18001c227  pop     rdi
0x18001c228  retn
```

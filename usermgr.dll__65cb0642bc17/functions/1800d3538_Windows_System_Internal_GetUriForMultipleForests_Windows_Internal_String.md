# Windows::System::Internal::_GetUriForMultipleForests(Windows::Internal::String &)

- ea: `0x1800d3538`
- end: `0x1800d378e`
- name: `?_GetUriForMultipleForests@Internal@System@Windows@@YAJAEAVString@13@@Z`
- size: `598`
- prototype: `__int64 __fastcall(Windows::System::Internal *__hidden this, struct Windows::Internal::String *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d2998`

## callees

- `0x1800088e8`
- `0x18000ce48`
- `0x1800b7570`
- `0x1800d2154`
- `0x1800d2ad0`
- `0x1800d303c`
- `0x1800d3538`
- `0x1800d3c60`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d356f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d356f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d357f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d357f`
- `SspiCli!GetUserNameExW` at `0x1800d35d2`
- `SspiCli!GetUserNameExW` at `0x1800d35d2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d3657`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d3657`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d3755`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d3755`
- `OLEAUT32!__imp_VariantInit` at `0x1800d364a`
- `OLEAUT32!__imp_VariantInit` at `0x1800d364a`
- `OLEAUT32!__imp_VariantClear` at `0x1800d374c`
- `OLEAUT32!__imp_VariantClear` at `0x1800d374c`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsOpenObject` at `0x1800d3626`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsOpenObject` at `0x1800d3626`

## string_xrefs

- `0x1800d35a6`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x1800d3568`: `activeds.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::System::Internal::_GetUriForMultipleForests(
        Windows::System::Internal *this,
        struct Windows::Internal::String *a2)
{
  signed int LastError; // eax
  int ActiveDirectory; // ebx
  OLECHAR *v5; // rdi
  const unsigned __int16 *v6; // rdx
  int riid; // [rsp+20h] [rbp-E0h]
  bool ppObject; // [rsp+28h] [rbp-D8h]
  bool v10; // [rsp+30h] [rbp-D0h]
  struct Windows::Internal::String *v11; // [rsp+40h] [rbp-C0h] BYREF
  ULONG nSize; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  HMODULE Library; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 **v15[3]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpszPathName[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v17[2]; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v18; // [rsp+A8h] [rbp-58h]
  WCHAR NameBuffer[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  Library = LoadLibraryExW(L"activeds.dll", 0, 0x800u);
  if ( Library )
  {
    nSize = 257;
    if ( GetUserNameExW((EXTENDED_NAME_FORMAT)65538, NameBuffer, &nSize)
      || (ActiveDirectory = ResultFromKnownLastError(), ActiveDirectory >= 0) )
    {
      v11 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      ActiveDirectory = ADsOpenObject(
                          L"LDAP://rootDSE",
                          0,
                          0,
                          1u,
                          &GUID_fd8256d0_fd15_11ce_abc4_02608c9e7553,
                          (void **)&v11);
      if ( ActiveDirectory >= 0 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v5 = SysAllocString(L"rootDomainNamingContext");
        ActiveDirectory = (*(__int64 (__fastcall **)(struct Windows::Internal::String *, OLECHAR *, VARIANTARG *))(*(_QWORD *)v11 + 120LL))(
                            v11,
                            v5,
                            &pvarg);
        if ( ActiveDirectory >= 0 && pvarg.vt == 8 )
        {
          memset(lpszPathName, 0, sizeof(lpszPathName));
          ActiveDirectory = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
                              lpszPathName,
                              L"LDAP://%s",
                              pvarg.llVal);
          if ( ActiveDirectory >= 0 )
          {
            memset(v15, 0, sizeof(v15));
            ActiveDirectory = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
                                v15,
                                L"(&(|(objectCategory=contact)(objectCategory=user))(|(mailNickName=%s)(mail=%s)(sAMAccoun"
                                 "tName=%s))(msRTCSIP-UserEnabled=TRUE))",
                                NameBuffer,
                                NameBuffer);
            if ( ActiveDirectory >= 0 )
            {
              *(_QWORD *)v17 = L"msRTCSIP-PrimaryUserAddress";
              v18 = L"proxyAddresses";
              ActiveDirectory = Windows::System::Internal::_QueryActiveDirectory(
                                  lpszPathName[0],
                                  v6,
                                  (unsigned int)v17,
                                  (const unsigned __int16 **)v15[0],
                                  NameBuffer,
                                  ppObject,
                                  v10,
                                  (bool *)this,
                                  v11);
            }
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(v15);
          }
          Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(lpszPathName);
        }
        VariantClear(&pvarg);
        SysFreeString(v5);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    }
  }
  else
  {
    LastError = GetLastError();
    ActiveDirectory = LastError;
    if ( LastError > 0 )
      ActiveDirectory = (unsigned __int16)LastError | 0x80070000;
    if ( ActiveDirectory < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x272,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
        (const char *)(unsigned int)ActiveDirectory,
        riid);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&Library);
  return (unsigned int)ActiveDirectory;
}

```

## disassembly

```asm
0x1800d3538  push    rbp
0x1800d353a  push    rbx
0x1800d353b  push    rsi
0x1800d353c  push    rdi
0x1800d353d  lea     rbp, [rsp-1D8h]
0x1800d3545  sub     rsp, 2D8h
0x1800d354c  mov     rax, cs:__security_cookie
0x1800d3553  xor     rax, rsp
0x1800d3556  mov     [rbp+1F0h+var_30], rax
0x1800d355d  mov     rsi, rcx
0x1800d3560  xor     edx, edx; hFile
0x1800d3562  mov     r8d, 800h; dwFlags
0x1800d3568  lea     rcx, aActivedsDll; "activeds.dll"
0x1800d356f  call    cs:__imp_LoadLibraryExW
0x1800d3575  mov     [rsp+2F0h+var_288], rax
0x1800d357a  test    rax, rax
0x1800d357d  jnz     short loc_1800D35BC
0x1800d357f  call    cs:__imp_GetLastError
0x1800d3585  mov     ebx, eax
0x1800d3587  test    eax, eax
0x1800d3589  jle     short loc_1800D3594
0x1800d358b  movzx   ebx, ax
0x1800d358e  or      ebx, 80070000h
0x1800d3594  test    ebx, ebx
0x1800d3596  jns     loc_1800D3767
0x1800d359c  mov     rcx, [rbp+1F8h]; this
0x1800d35a3  mov     r9d, ebx; char *
0x1800d35a6  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x1800d35ad  mov     edx, 272h; void *
0x1800d35b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d35b7  jmp     loc_1800D3767
0x1800d35bc  mov     [rsp+2F0h+nSize], 101h
0x1800d35c4  lea     r8, [rsp+2F0h+nSize]; nSize
0x1800d35c9  lea     rdx, [rbp+1F0h+NameBuffer]; lpNameBuffer
0x1800d35cd  mov     ecx, 10002h; NameFormat
0x1800d35d2  call    cs:__imp_GetUserNameExW
0x1800d35d8  test    al, al
0x1800d35da  jnz     short loc_1800D35EB
0x1800d35dc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d35e1  mov     ebx, eax
0x1800d35e3  test    eax, eax
0x1800d35e5  js      loc_1800D3767
0x1800d35eb  mov     [rsp+2F0h+var_2B0], 0; struct Windows::Internal::String *
0x1800d35f4  lea     rcx, [rsp+2F0h+var_2B0]
0x1800d35f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d35fe  lea     rax, [rsp+2F0h+var_2B0]
0x1800d3603  mov     [rsp+2F0h+ppObject], rax; bool
0x1800d3608  lea     rax, _GUID_fd8256d0_fd15_11ce_abc4_02608c9e7553
0x1800d360f  mov     [rsp+2F0h+riid], rax; riid
0x1800d3614  mov     r9d, 1; dwReserved
0x1800d361a  xor     r8d, r8d; lpszPassword
0x1800d361d  xor     edx, edx; lpszUserName
0x1800d361f  lea     rcx, szPathName; "LDAP://rootDSE"
0x1800d3626  call    cs:__imp_ADsOpenObject
0x1800d362c  mov     ebx, eax
0x1800d362e  test    eax, eax
0x1800d3630  js      loc_1800D375C
0x1800d3636  xorps   xmm0, xmm0
0x1800d3639  xor     eax, eax
0x1800d363b  movups  xmmword ptr [rsp+2F0h+pvarg], xmm0
0x1800d3640  mov     qword ptr [rsp+2F0h+pvarg+10h], rax
0x1800d3645  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x1800d364a  call    cs:__imp_VariantInit
0x1800d3650  lea     rcx, aRootdomainnami; "rootDomainNamingContext"
0x1800d3657  call    cs:__imp_SysAllocString
0x1800d365d  mov     rdi, rax
0x1800d3660  mov     rcx, [rsp+2F0h+var_2B0]
0x1800d3665  mov     rdx, [rcx]
0x1800d3668  mov     rax, [rdx+78h]
0x1800d366c  lea     r8, [rsp+2F0h+pvarg]
0x1800d3671  mov     rdx, rdi
0x1800d3674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3679  mov     ebx, eax
0x1800d367b  test    eax, eax
0x1800d367d  js      loc_1800D3747
0x1800d3683  cmp     word ptr [rsp+2F0h+pvarg], 8
0x1800d3689  jnz     loc_1800D3747
0x1800d368f  mov     [rbp+1F0h+lpszPathName], 0
0x1800d3697  mov     [rbp+1F0h+var_260], 0
0x1800d369f  mov     [rbp+1F0h+var_258], 0
0x1800d36a7  mov     r8, qword ptr [rsp+2F0h+pvarg+8]
0x1800d36ac  lea     rdx, aLdapS; "LDAP://%s"
0x1800d36b3  lea     rcx, [rbp+1F0h+lpszPathName]
0x1800d36b7  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800d36bc  mov     ebx, eax
0x1800d36be  test    eax, eax
0x1800d36c0  js      short loc_1800D373E
0x1800d36c2  mov     [rsp+2F0h+var_280], 0
0x1800d36cb  mov     [rsp+2F0h+var_278], 0
0x1800d36d4  mov     [rbp+1F0h+var_270], 0
0x1800d36dc  lea     rax, [rbp+1F0h+NameBuffer]
0x1800d36e0  mov     [rsp+2F0h+riid], rax; unsigned __int16 *
0x1800d36e5  lea     r9, [rbp+1F0h+NameBuffer]
0x1800d36e9  lea     r8, [rbp+1F0h+NameBuffer]
0x1800d36ed  lea     rdx, aObjectcategory; "(&(|(objectCategory=contact)(objectCate"...
0x1800d36f4  lea     rcx, [rsp+2F0h+var_280]
0x1800d36f9  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800d36fe  mov     ebx, eax
0x1800d3700  test    eax, eax
0x1800d3702  js      short loc_1800D3733
0x1800d3704  lea     rax, aMsrtcsipPrimar; "msRTCSIP-PrimaryUserAddress"
0x1800d370b  mov     qword ptr [rbp+1F0h+var_250], rax
0x1800d370f  lea     rax, aProxyaddresses; "proxyAddresses"
0x1800d3716  mov     [rbp+1F0h+var_248], rax
0x1800d371a  mov     [rsp+2F0h+var_2B8], rsi; bool *
0x1800d371f  mov     r9, [rsp+2F0h+var_280]; unsigned __int16 **
0x1800d3724  lea     r8, [rbp+1F0h+var_250]; unsigned int
0x1800d3728  mov     rcx, [rbp+1F0h+lpszPathName]; lpszPathName
0x1800d372c  call    ?_QueryActiveDirectory@Internal@System@Windows@@YAJPEBGKPEAPEBG0_N2PEA_NAEAVString@13@@Z; Windows::System::Internal::_QueryActiveDirectory(ushort const *,ulong,ushort const * *,ushort const *,bool,bool,bool *,Windows::Internal::String &)
0x1800d3731  mov     ebx, eax
0x1800d3733  lea     rcx, [rsp+2F0h+var_280]
0x1800d3738  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1800d373d  nop
0x1800d373e  lea     rcx, [rbp+1F0h+lpszPathName]
0x1800d3742  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1800d3747  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x1800d374c  call    cs:__imp_VariantClear
0x1800d3752  mov     rcx, rdi; bstrString
0x1800d3755  call    cs:__imp_SysFreeString
0x1800d375b  nop
0x1800d375c  lea     rcx, [rsp+2F0h+var_2B0]
0x1800d3761  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d3766  nop
0x1800d3767  lea     rcx, [rsp+2F0h+var_288]
0x1800d376c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800d3771  mov     eax, ebx
0x1800d3773  mov     rcx, [rbp+1F0h+var_30]
0x1800d377a  xor     rcx, rsp; StackCookie
0x1800d377d  call    __security_check_cookie
0x1800d3782  add     rsp, 2D8h
0x1800d3789  pop     rdi
0x1800d378a  pop     rsi
0x1800d378b  pop     rbx
0x1800d378c  pop     rbp
0x1800d378d  retn
```

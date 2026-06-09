# CUpdate::get_ExtendedStaticProperty(wchar_t *,tagVARIANT *)

- ea: `0x18004f600`
- end: `0x18004f8b5`
- name: `?get_ExtendedStaticProperty@CUpdate@@UEAAJPEA_WPEAUtagVARIANT@@@Z`
- size: `693`
- prototype: `int(CUpdate *__hidden this, wchar_t *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180006d4c`
- `0x180016e9c`
- `0x18004f600`
- `0x180090bc8`
- `0x1800914bc`
- `0x180091f50`
- `0x180099990`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004f6d5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004f6d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f769`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f769`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f746`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f80f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f820`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f746`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f80f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f820`
- `OLEAUT32!__imp_SysStringLen` at `0x18004f650`
- `OLEAUT32!__imp_SysStringLen` at `0x18004f650`
- `OLEAUT32!__imp_VariantInit` at `0x18004f6af`
- `OLEAUT32!__imp_VariantInit` at `0x18004f7ce`
- `OLEAUT32!__imp_VariantInit` at `0x18004f83e`
- `OLEAUT32!__imp_VariantInit` at `0x18004f6af`
- `OLEAUT32!__imp_VariantInit` at `0x18004f7ce`
- `OLEAUT32!__imp_VariantInit` at `0x18004f83e`
- `OLEAUT32!__imp_VariantClear` at `0x18004f887`
- `OLEAUT32!__imp_VariantClear` at `0x18004f887`
- `OLEAUT32!__imp_VariantCopy` at `0x18004f7db`
- `OLEAUT32!__imp_VariantCopy` at `0x18004f84b`
- `OLEAUT32!__imp_VariantCopy` at `0x18004f7db`
- `OLEAUT32!__imp_VariantCopy` at `0x18004f84b`

## string_xrefs

- `0x18004f6b7`: `ContainsUpdateBootstrapper`
- `0x18004f661`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004f68d`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004f7ee`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004f875`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004f714`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18004f77b`: `ContainsUpdateBootstrapper`

## pseudocode

```c
__int64 __fastcall CUpdate::get_ExtendedStaticProperty(CUpdate *this, wchar_t *a2, struct tagVARIANT *a3)
{
  unsigned int v6; // ebx
  HRESULT v8; // eax
  int v9; // edi
  HRESULT v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  int lpString2; // [rsp+20h] [rbp-E0h]
  PCNZWCH lpString2a; // [rsp+20h] [rbp-E0h]
  int lpString2b; // [rsp+20h] [rbp-E0h]
  _BYTE v16[80]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-68h] BYREF
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v6 = 0;
  if ( (int)WUSystemInterfaceHelper::IsCapabilitySupported(this, (unsigned int)a2) < 0 )
    return 2149842999LL;
  if ( !SysStringLen(a2) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E2,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)0x80070057LL,
      lpString2);
    return 2147942487LL;
  }
  if ( a3 )
  {
    VariantInit(&pvarg);
    if ( CompareStringW(0x7Fu, 0, a2, -1, L"ContainsUpdateBootstrapper", -1) == 2 )
    {
      if ( (unsigned int)AreTestKeysAllowed(1) )
      {
        hKey = 0;
        Trace::GuidToString::GuidToString((Trace::GuidToString *)v16, (const struct _GUID *)this + 42);
        lpString2a = L"PreDownloadOverride";
        if ( (int)StringCchPrintfW(
                    SubKey,
                    0x104u,
                    L"%ws\\%ws\\%ws",
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test") >= 0 )
        {
          if ( hKey )
            RegCloseKey(hKey);
          if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey)
            && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(hKey, 0, L"ContainsUpdateBootstrapper", 0) )
          {
            WUTrace(0, 0, 0x10000, 4, 0, L" Using Test Override: %ws");
            pvarg.iVal = -1;
            pvarg.vt = 11;
            VariantInit(a3);
            v8 = VariantCopy(a3, &pvarg);
            v9 = v8;
            if ( v8 >= 0 )
              v9 = 0;
            else
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x600,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
                (const char *)(unsigned int)v8,
                lpString2b);
            if ( hKey )
              RegCloseKey(hKey);
            goto LABEL_25;
          }
        }
        if ( hKey )
          RegCloseKey(hKey);
      }
      pvarg.vt = 11;
      pvarg.iVal = *((_WORD *)this + 311);
      VariantInit(a3);
      v10 = VariantCopy(a3, &pvarg);
      v9 = v10;
      if ( v10 >= 0 )
      {
LABEL_26:
        VariantClear(&pvarg);
        return v6;
      }
      v11 = (unsigned int)v10;
      v12 = 1551;
    }
    else
    {
      v9 = -2147024809;
      v12 = 1547;
      v11 = 2147942487LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)v11,
      (int)lpString2a);
LABEL_25:
    v6 = v9;
    goto LABEL_26;
  }
  v6 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E3,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
    (const char *)0x80004003LL,
    lpString2);
  return v6;
}

```

## disassembly

```asm
0x18004f600  mov     [rsp-8+arg_18], rbx
0x18004f605  push    rbp
0x18004f606  push    rsi
0x18004f607  push    rdi
0x18004f608  push    r14
0x18004f60a  push    r15
0x18004f60c  lea     rbp, [rsp-1D0h]
0x18004f614  sub     rsp, 2D0h
0x18004f61b  mov     rax, cs:__security_cookie
0x18004f622  xor     rax, rsp
0x18004f625  mov     [rbp+1F0h+var_30], rax
0x18004f62c  mov     rdi, r8
0x18004f62f  mov     rsi, rdx
0x18004f632  mov     r14, rcx
0x18004f635  call    ?IsCapabilitySupported@WUSystemInterfaceHelper@@YAJK@Z; WUSystemInterfaceHelper::IsCapabilitySupported(ulong)
0x18004f63a  shr     eax, 1Fh
0x18004f63d  xor     ebx, ebx
0x18004f63f  test    al, al
0x18004f641  jz      short loc_18004F64D
0x18004f643  mov     eax, 80240037h
0x18004f648  jmp     loc_18004F88F
0x18004f64d  mov     rcx, rsi; pbstr
0x18004f650  call    cs:__imp_SysStringLen
0x18004f656  test    eax, eax
0x18004f658  jnz     short loc_18004F681
0x18004f65a  mov     rcx, [rbp+1F8h]; this
0x18004f661  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004f668  mov     edi, 80070057h
0x18004f66d  mov     edx, 5E2h; void *
0x18004f672  mov     r9d, edi; char *
0x18004f675  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f67a  mov     eax, edi
0x18004f67c  jmp     loc_18004F88F
0x18004f681  test    rdi, rdi
0x18004f684  jnz     short loc_18004F6AB
0x18004f686  mov     rcx, [rbp+1F8h]; this
0x18004f68d  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004f694  mov     ebx, 80004003h
0x18004f699  mov     edx, 5E3h; void *
0x18004f69e  mov     r9d, ebx; char *
0x18004f6a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f6a6  jmp     loc_18004F88D
0x18004f6ab  lea     rcx, [rbp+1F0h+pvarg]; pvarg
0x18004f6af  call    cs:__imp_VariantInit
0x18004f6b5  xor     edx, edx; dwCmpFlags
0x18004f6b7  lea     rax, psz; "ContainsUpdateBootstrapper"
0x18004f6be  or      r15d, 0FFFFFFFFh
0x18004f6c2  mov     r8, rsi; lpString1
0x18004f6c5  mov     [rsp+2F0h+cchCount2], r15d; cchCount2
0x18004f6ca  mov     r9d, r15d; cchCount1
0x18004f6cd  mov     [rsp+2F0h+lpString2], rax; int
0x18004f6d2  lea     ecx, [rdx+7Fh]; Locale
0x18004f6d5  call    cs:__imp_CompareStringW
0x18004f6db  cmp     eax, 2
0x18004f6de  jnz     loc_18004F861
0x18004f6e4  mov     cl, 1; bool
0x18004f6e6  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18004f6eb  test    eax, eax
0x18004f6ed  jz      loc_18004F826
0x18004f6f3  lea     rdx, [r14+2A0h]; struct _GUID *
0x18004f6fa  mov     [rbp+1F0h+hKey], rbx
0x18004f6fe  lea     rcx, [rsp+2F0h+var_2B0]; this
0x18004f703  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18004f708  mov     qword ptr [rsp+2F0h+cchCount2], rax
0x18004f70d  lea     rsi, ?c_szPreDownloadOverrideKey@@3QB_WB; "PreDownloadOverride"
0x18004f714  lea     r9, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f71b  mov     [rsp+2F0h+lpString2], rsi
0x18004f720  lea     r8, aWsWsWs; "%ws\\%ws\\%ws"
0x18004f727  mov     edx, 104h; unsigned __int64
0x18004f72c  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18004f730  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18004f735  test    eax, eax
0x18004f737  js      loc_18004F817
0x18004f73d  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18004f741  test    rcx, rcx
0x18004f744  jz      short loc_18004F74C
0x18004f746  call    cs:__imp_RegCloseKey
0x18004f74c  lea     rax, [rbp+1F0h+hKey]
0x18004f750  mov     r9d, 20019h; samDesired
0x18004f756  xor     r8d, r8d; ulOptions
0x18004f759  mov     [rsp+2F0h+lpString2], rax; phkResult
0x18004f75e  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18004f762  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004f769  call    cs:__imp_RegOpenKeyExW
0x18004f76f  test    eax, eax
0x18004f771  jnz     loc_18004F817
0x18004f777  mov     rcx, [rbp+1F0h+hKey]
0x18004f77b  lea     r8, ?c_szContainsUpdateBootstrapper@@3QB_WB; "ContainsUpdateBootstrapper"
0x18004f782  xor     r9d, r9d
0x18004f785  xor     edx, edx
0x18004f787  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x18004f78c  test    eax, eax
0x18004f78e  jz      loc_18004F817
0x18004f794  xor     edx, edx
0x18004f796  mov     [rsp+2F0h+var_2C0], rsi
0x18004f79b  lea     rax, aUsingTestOverr_1; " Using Test Override: %ws"
0x18004f7a2  xor     ecx, ecx
0x18004f7a4  mov     qword ptr [rsp+2F0h+cchCount2], rax
0x18004f7a9  mov     r8d, 10000h
0x18004f7af  mov     [rsp+2F0h+lpString2], rbx; int
0x18004f7b4  lea     r9d, [rdx+4]
0x18004f7b8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18004f7bd  mov     eax, 0Bh
0x18004f7c2  mov     word ptr [rbp+1F0h+pvarg+8], r15w
0x18004f7c7  mov     rcx, rdi; pvarg
0x18004f7ca  mov     word ptr [rbp+1F0h+pvarg], ax
0x18004f7ce  call    cs:__imp_VariantInit
0x18004f7d4  lea     rdx, [rbp+1F0h+pvarg]; pvargSrc
0x18004f7d8  mov     rcx, rdi; pvargDest
0x18004f7db  call    cs:__imp_VariantCopy
0x18004f7e1  mov     edi, eax
0x18004f7e3  test    eax, eax
0x18004f7e5  jns     short loc_18004F804
0x18004f7e7  mov     rcx, [rbp+1F8h]; this
0x18004f7ee  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004f7f5  mov     r9d, eax; char *
0x18004f7f8  mov     edx, 600h; void *
0x18004f7fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f802  jmp     short loc_18004F806
0x18004f804  mov     edi, ebx
0x18004f806  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18004f80a  test    rcx, rcx
0x18004f80d  jz      short loc_18004F881
0x18004f80f  call    cs:__imp_RegCloseKey
0x18004f815  jmp     short loc_18004F881
0x18004f817  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18004f81b  test    rcx, rcx
0x18004f81e  jz      short loc_18004F826
0x18004f820  call    cs:__imp_RegCloseKey
0x18004f826  mov     eax, 0Bh
0x18004f82b  mov     rcx, rdi; pvarg
0x18004f82e  mov     word ptr [rbp+1F0h+pvarg], ax
0x18004f832  movzx   eax, word ptr [r14+26Eh]
0x18004f83a  mov     word ptr [rbp+1F0h+pvarg+8], ax
0x18004f83e  call    cs:__imp_VariantInit
0x18004f844  lea     rdx, [rbp+1F0h+pvarg]; pvargSrc
0x18004f848  mov     rcx, rdi; pvargDest
0x18004f84b  call    cs:__imp_VariantCopy
0x18004f851  mov     edi, eax
0x18004f853  test    eax, eax
0x18004f855  jns     short loc_18004F883
0x18004f857  mov     r9d, eax
0x18004f85a  mov     edx, 60Fh
0x18004f85f  jmp     short loc_18004F86E
0x18004f861  mov     edi, 80070057h
0x18004f866  mov     edx, 60Bh; void *
0x18004f86b  mov     r9d, edi; char *
0x18004f86e  mov     rcx, [rbp+1F8h]; this
0x18004f875  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004f87c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f881  mov     ebx, edi
0x18004f883  lea     rcx, [rbp+1F0h+pvarg]; pvarg
0x18004f887  call    cs:__imp_VariantClear
0x18004f88d  mov     eax, ebx
0x18004f88f  mov     rcx, [rbp+1F0h+var_30]
0x18004f896  xor     rcx, rsp; StackCookie
0x18004f899  call    __security_check_cookie
0x18004f89e  mov     rbx, [rsp+2F0h+arg_18]
0x18004f8a6  add     rsp, 2D0h
0x18004f8ad  pop     r15
0x18004f8af  pop     r14
0x18004f8b1  pop     rdi
0x18004f8b2  pop     rsi
0x18004f8b3  pop     rbp
0x18004f8b4  retn
```

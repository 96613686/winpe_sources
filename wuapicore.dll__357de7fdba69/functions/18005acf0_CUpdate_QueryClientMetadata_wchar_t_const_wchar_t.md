# CUpdate::QueryClientMetadata(wchar_t const *,wchar_t * *)

- ea: `0x18005acf0`
- end: `0x18005b0e2`
- name: `?QueryClientMetadata@CUpdate@@UEAAJPEB_WPEAPEA_W@Z`
- size: `1010`
- prototype: `int(CUpdate *__hidden this, const wchar_t *, wchar_t **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180006d4c`
- `0x180016e9c`
- `0x18005acf0`
- `0x180081a38`
- `0x180090bc8`
- `0x1800914bc`
- `0x180092084`
- `0x180096bb0`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ad8d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005adb2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005adde`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005afa7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005afd2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ad8d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005adb2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005adde`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005afa7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005afd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ae99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ae99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ae76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005af25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005af5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ae76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005af25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005af5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005aec4`
- `OLEAUT32!__imp_SysFreeString` at `0x18005afe0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b010`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b057`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b0b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005aec4`
- `OLEAUT32!__imp_SysFreeString` at `0x18005afe0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b010`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b057`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b0b0`

## string_xrefs

- `0x18005adbd`: `Update`
- `0x18005ad42`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18005b03e`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18005b080`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18005ae38`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
__int64 __fastcall CUpdate::QueryClientMetadata(CUpdate *this, const wchar_t *a2, wchar_t **a3)
{
  unsigned int v3; // r14d
  unsigned int v7; // ebx
  __int64 v8; // rdx
  OLECHAR *v9; // rdi
  void *v10; // rbx
  HKEY v11; // rcx
  const wchar_t *v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  const wchar_t *v15; // rcx
  const wchar_t *v16; // rcx
  int v17; // eax
  int v18; // ebx
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  void *lpMem; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[80]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v3 = 0;
  if ( a3 )
  {
    *a3 = 0;
    if ( a2 != L"Audience"
      && (!a2
       || CompareStringW(0x7Fu, 1u, a2, -1, L"Audience", -1) != 2
       && a2 != L"Admin"
       && CompareStringW(0x7Fu, 1u, a2, -1, L"Admin", -1) != 2
       && a2 != L"Update"
       && CompareStringW(0x7Fu, 1u, a2, -1, L"Update", -1) != 2) )
    {
      v7 = -2147024809;
      v8 = 4811;
      goto LABEL_3;
    }
    bstrString = 0;
    v9 = 0;
    if ( (unsigned int)AreTestKeysAllowed(1) )
    {
      v10 = 0;
      hKey = 0;
      lpMem = 0;
      Trace::GuidToString::GuidToString((Trace::GuidToString *)v23, (const struct _GUID *)((char *)this + 648));
      lpString2 = L"OverrideClientMetadata";
      if ( (int)StringCchPrintfW(
                  SubKey,
                  0x104u,
                  L"%ws\\%ws\\%ws\\%ws",
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test") >= 0 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
        {
          if ( (int)RegQueryStringValue(hKey, 0, a2, &lpMem) < 0 )
          {
            v10 = lpMem;
          }
          else
          {
            SysFreeString(0);
            v10 = lpMem;
            if ( SusSysAllocString((const wchar_t *)lpMem, &bstrString) >= 0 )
            {
              WUTrace(
                0,
                0,
                0x10000,
                4,
                0,
                L"Using Test Override: %ws, Level = %ws, Value = %s",
                L"OverrideClientMetadata",
                a2,
                v10);
              v11 = hKey;
              *a3 = bstrString;
              if ( v11 )
              {
                RegCloseKey(v11);
                hKey = 0;
              }
              if ( v10 )
                SusFree(v10);
              goto LABEL_42;
            }
            v9 = bstrString;
          }
        }
      }
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      if ( v10 )
        SusFree(v10);
    }
    if ( a2 != L"Audience" )
    {
      if ( !a2 )
        goto LABEL_36;
      if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Audience", -1) != 2 )
      {
        if ( a2 == L"Admin" || CompareStringW(0x7Fu, 1u, a2, -1, L"Admin", -1) == 2 )
        {
          SysFreeString(v9);
          v12 = (const wchar_t *)*((_QWORD *)this + 128);
          bstrString = 0;
          v13 = SusSysAllocString(v12, &bstrString);
          v7 = v13;
          if ( v13 < 0 )
          {
            v14 = 4859;
LABEL_38:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v14,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
              (const char *)(unsigned int)v13,
              (int)lpString2);
            v9 = bstrString;
LABEL_43:
            SysFreeString(v9);
            return v7;
          }
          goto LABEL_41;
        }
LABEL_36:
        SysFreeString(v9);
        v15 = (const wchar_t *)*((_QWORD *)this + 130);
        bstrString = 0;
        v13 = SusSysAllocString(v15, &bstrString);
        v7 = v13;
        if ( v13 < 0 )
        {
          v14 = 4863;
          goto LABEL_38;
        }
        goto LABEL_41;
      }
    }
    SysFreeString(v9);
    v16 = (const wchar_t *)*((_QWORD *)this + 129);
    bstrString = 0;
    v17 = SusSysAllocString(v16, &bstrString);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12F7,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)(unsigned int)v17,
        (int)lpString2);
      v9 = bstrString;
      v3 = v18;
LABEL_42:
      v7 = v3;
      goto LABEL_43;
    }
LABEL_41:
    v9 = 0;
    *a3 = bstrString;
    goto LABEL_42;
  }
  v7 = -2147467261;
  v8 = 4803;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
    (const char *)v7,
    (int)lpString2);
  return v7;
}

```

## disassembly

```asm
0x18005acf0  mov     [rsp-8+arg_18], rbx
0x18005acf5  push    rbp
0x18005acf6  push    rsi
0x18005acf7  push    rdi
0x18005acf8  push    r12
0x18005acfa  push    r13
0x18005acfc  push    r14
0x18005acfe  push    r15
0x18005ad00  lea     rbp, [rsp-1E0h]
0x18005ad08  sub     rsp, 2E0h
0x18005ad0f  mov     rax, cs:__security_cookie
0x18005ad16  xor     rax, rsp
0x18005ad19  mov     [rbp+210h+var_40], rax
0x18005ad20  xor     r14d, r14d
0x18005ad23  mov     r12, r8
0x18005ad26  mov     r15, rdx
0x18005ad29  mov     r13, rcx
0x18005ad2c  test    r8, r8
0x18005ad2f  jnz     short loc_18005AD56
0x18005ad31  mov     ebx, 80004003h
0x18005ad36  mov     edx, 12C3h; void *
0x18005ad3b  mov     rcx, [rbp+218h]; this
0x18005ad42  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18005ad49  mov     r9d, ebx; char *
0x18005ad4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ad51  jmp     loc_18005B0B6
0x18005ad56  lea     rax, aAudience; "Audience"
0x18005ad5d  mov     [r8], r14
0x18005ad60  or      ebx, 0FFFFFFFFh
0x18005ad63  lea     rsi, aAdmin; "Admin"
0x18005ad6a  cmp     r15, rax
0x18005ad6d  jz      loc_18005ADF8
0x18005ad73  test    r15, r15
0x18005ad76  jz      short loc_18005ADE9
0x18005ad78  lea     edx, [rbx+2]; dwCmpFlags
0x18005ad7b  mov     [rsp+310h+cchCount2], ebx; cchCount2
0x18005ad7f  lea     ecx, [rdx+7Eh]; Locale
0x18005ad82  mov     [rsp+310h+lpString2], rax; lpString2
0x18005ad87  mov     r9d, ebx; cchCount1
0x18005ad8a  mov     r8, r15; lpString1
0x18005ad8d  call    cs:__imp_CompareStringW
0x18005ad93  cmp     eax, 2
0x18005ad96  jz      short loc_18005ADF8
0x18005ad98  cmp     r15, rsi
0x18005ad9b  jz      short loc_18005ADF8
0x18005ad9d  lea     edx, [rbx+2]; dwCmpFlags
0x18005ada0  mov     [rsp+310h+cchCount2], ebx; cchCount2
0x18005ada4  lea     ecx, [rdx+7Eh]; Locale
0x18005ada7  mov     [rsp+310h+lpString2], rsi; lpString2
0x18005adac  mov     r9d, ebx; cchCount1
0x18005adaf  mov     r8, r15; lpString1
0x18005adb2  call    cs:__imp_CompareStringW
0x18005adb8  cmp     eax, 2
0x18005adbb  jz      short loc_18005ADF8
0x18005adbd  lea     rax, aUpdate; "Update"
0x18005adc4  cmp     r15, rax
0x18005adc7  jz      short loc_18005ADF8
0x18005adc9  lea     edx, [rbx+2]; dwCmpFlags
0x18005adcc  mov     [rsp+310h+cchCount2], ebx; cchCount2
0x18005add0  lea     ecx, [rdx+7Eh]; Locale
0x18005add3  mov     [rsp+310h+lpString2], rax; lpString2
0x18005add8  mov     r9d, ebx; cchCount1
0x18005addb  mov     r8, r15; lpString1
0x18005adde  call    cs:__imp_CompareStringW
0x18005ade4  cmp     eax, 2
0x18005ade7  jz      short loc_18005ADF8
0x18005ade9  mov     ebx, 80070057h
0x18005adee  mov     edx, 12CBh
0x18005adf3  jmp     loc_18005AD3B
0x18005adf8  mov     cl, 1; bool
0x18005adfa  mov     [rsp+310h+bstrString], r14
0x18005adff  mov     rdi, r14
0x18005ae02  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18005ae07  test    eax, eax
0x18005ae09  jz      loc_18005AF7B
0x18005ae0f  mov     rsi, [r13+3B0h]
0x18005ae16  lea     rdx, [r13+288h]; struct _GUID *
0x18005ae1d  mov     rbx, r14
0x18005ae20  mov     [rbp+210h+hKey], r14
0x18005ae24  lea     rcx, [rsp+310h+var_2B0]; this
0x18005ae29  mov     [rsp+310h+lpMem], rbx
0x18005ae2e  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18005ae33  mov     [rsp+310h+var_2E0], rsi
0x18005ae38  lea     r9, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005ae3f  mov     qword ptr [rsp+310h+cchCount2], rax
0x18005ae44  lea     rsi, aOverrideclient; "OverrideClientMetadata"
0x18005ae4b  lea     r8, aWsWsWsWs; "%ws\\%ws\\%ws\\%ws"
0x18005ae52  mov     [rsp+310h+lpString2], rsi
0x18005ae57  mov     edx, 104h; unsigned __int64
0x18005ae5c  lea     rcx, [rbp+210h+SubKey]; Buffer
0x18005ae60  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18005ae65  test    eax, eax
0x18005ae67  js      loc_18005AF51
0x18005ae6d  mov     rcx, [rbp+210h+hKey]; hKey
0x18005ae71  test    rcx, rcx
0x18005ae74  jz      short loc_18005AE7C
0x18005ae76  call    cs:__imp_RegCloseKey
0x18005ae7c  lea     rax, [rbp+210h+hKey]
0x18005ae80  mov     r9d, 20019h; samDesired
0x18005ae86  xor     r8d, r8d; ulOptions
0x18005ae89  mov     [rsp+310h+lpString2], rax; int
0x18005ae8e  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x18005ae92  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ae99  call    cs:__imp_RegOpenKeyExW
0x18005ae9f  test    eax, eax
0x18005aea1  jnz     loc_18005AF51
0x18005aea7  mov     rcx, [rbp+210h+hKey]
0x18005aeab  lea     r9, [rsp+310h+lpMem]
0x18005aeb0  mov     r8, r15
0x18005aeb3  xor     edx, edx
0x18005aeb5  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)
0x18005aeba  test    eax, eax
0x18005aebc  js      loc_18005AF4C
0x18005aec2  xor     ecx, ecx; bstrString
0x18005aec4  call    cs:__imp_SysFreeString
0x18005aeca  mov     rbx, [rsp+310h+lpMem]
0x18005aecf  lea     rdx, [rsp+310h+bstrString]; wchar_t **
0x18005aed4  mov     rcx, rbx; wchar_t *
0x18005aed7  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x18005aedc  test    eax, eax
0x18005aede  js      short loc_18005AF45
0x18005aee0  mov     [rsp+310h+var_2D0], rbx
0x18005aee5  lea     rax, aUsingTestOverr_0; "Using Test Override: %ws, Level = %ws, "...
0x18005aeec  mov     [rsp+310h+var_2D8], r15
0x18005aef1  xor     edx, edx
0x18005aef3  mov     [rsp+310h+var_2E0], rsi
0x18005aef8  xor     ecx, ecx
0x18005aefa  mov     qword ptr [rsp+310h+cchCount2], rax
0x18005aeff  mov     r8d, 10000h
0x18005af05  mov     [rsp+310h+lpString2], r14
0x18005af0a  lea     r9d, [rdx+4]
0x18005af0e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18005af13  mov     rcx, [rbp+210h+hKey]; hKey
0x18005af17  mov     rax, [rsp+310h+bstrString]
0x18005af1c  mov     [r12], rax
0x18005af20  test    rcx, rcx
0x18005af23  jz      short loc_18005AF2F
0x18005af25  call    cs:__imp_RegCloseKey
0x18005af2b  mov     [rbp+210h+hKey], r14
0x18005af2f  test    rbx, rbx
0x18005af32  jz      loc_18005B0AA
0x18005af38  mov     rcx, rbx; lpMem
0x18005af3b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005af40  jmp     loc_18005B0AA
0x18005af45  mov     rdi, [rsp+310h+bstrString]
0x18005af4a  jmp     short loc_18005AF51
0x18005af4c  mov     rbx, [rsp+310h+lpMem]
0x18005af51  mov     rcx, [rbp+210h+hKey]; hKey
0x18005af55  test    rcx, rcx
0x18005af58  jz      short loc_18005AF64
0x18005af5a  call    cs:__imp_RegCloseKey
0x18005af60  mov     [rbp+210h+hKey], r14
0x18005af64  test    rbx, rbx
0x18005af67  jz      short loc_18005AF71
0x18005af69  mov     rcx, rbx; lpMem
0x18005af6c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005af71  lea     rsi, aAdmin; "Admin"
0x18005af78  or      ebx, 0FFFFFFFFh
0x18005af7b  lea     rax, aAudience; "Audience"
0x18005af82  cmp     r15, rax
0x18005af85  jz      loc_18005B054
0x18005af8b  test    r15, r15
0x18005af8e  jz      short loc_18005B00D
0x18005af90  mov     edx, 1; dwCmpFlags
0x18005af95  mov     [rsp+310h+cchCount2], ebx; cchCount2
0x18005af99  mov     r9d, ebx; cchCount1
0x18005af9c  mov     [rsp+310h+lpString2], rax; lpString2
0x18005afa1  mov     r8, r15; lpString1
0x18005afa4  lea     ecx, [rdx+7Eh]; Locale
0x18005afa7  call    cs:__imp_CompareStringW
0x18005afad  cmp     eax, 2
0x18005afb0  jz      loc_18005B054
0x18005afb6  cmp     r15, rsi
0x18005afb9  jz      short loc_18005AFDD
0x18005afbb  mov     edx, 1; dwCmpFlags
0x18005afc0  mov     [rsp+310h+cchCount2], ebx; cchCount2
0x18005afc4  mov     r9d, ebx; cchCount1
0x18005afc7  mov     [rsp+310h+lpString2], rsi; lpString2
0x18005afcc  mov     r8, r15; lpString1
0x18005afcf  lea     ecx, [rdx+7Eh]; Locale
0x18005afd2  call    cs:__imp_CompareStringW
0x18005afd8  cmp     eax, 2
0x18005afdb  jnz     short loc_18005B00D
0x18005afdd  mov     rcx, rdi; bstrString
0x18005afe0  call    cs:__imp_SysFreeString
0x18005afe6  mov     rcx, [r13+400h]; wchar_t *
0x18005afed  lea     rdx, [rsp+310h+bstrString]; wchar_t **
0x18005aff2  mov     [rsp+310h+bstrString], r14
0x18005aff7  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x18005affc  mov     ebx, eax
0x18005affe  test    eax, eax
0x18005b000  jns     loc_18005B09E
0x18005b006  mov     edx, 12FBh
0x18005b00b  jmp     short loc_18005B037
0x18005b00d  mov     rcx, rdi; bstrString
0x18005b010  call    cs:__imp_SysFreeString
0x18005b016  mov     rcx, [r13+410h]; wchar_t *
0x18005b01d  lea     rdx, [rsp+310h+bstrString]; wchar_t **
0x18005b022  mov     [rsp+310h+bstrString], r14
0x18005b027  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x18005b02c  mov     ebx, eax
0x18005b02e  test    eax, eax
0x18005b030  jns     short loc_18005B09E
0x18005b032  mov     edx, 12FFh; void *
0x18005b037  mov     rcx, [rbp+218h]; this
0x18005b03e  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18005b045  mov     r9d, eax; char *
0x18005b048  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b04d  mov     rdi, [rsp+310h+bstrString]
0x18005b052  jmp     short loc_18005B0AD
0x18005b054  mov     rcx, rdi; bstrString
0x18005b057  call    cs:__imp_SysFreeString
0x18005b05d  mov     rcx, [r13+408h]; wchar_t *
0x18005b064  lea     rdx, [rsp+310h+bstrString]; wchar_t **
0x18005b069  mov     [rsp+310h+bstrString], r14
0x18005b06e  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x18005b073  mov     ebx, eax
0x18005b075  test    eax, eax
0x18005b077  jns     short loc_18005B09E
0x18005b079  mov     rcx, [rbp+218h]; this
0x18005b080  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18005b087  mov     r9d, eax; char *
0x18005b08a  mov     edx, 12F7h; void *
0x18005b08f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b094  mov     rdi, [rsp+310h+bstrString]
0x18005b099  mov     r14d, ebx
0x18005b09c  jmp     short loc_18005B0AA
0x18005b09e  mov     rax, [rsp+310h+bstrString]
0x18005b0a3  mov     rdi, r14
0x18005b0a6  mov     [r12], rax
0x18005b0aa  mov     ebx, r14d
0x18005b0ad  mov     rcx, rdi; bstrString
0x18005b0b0  call    cs:__imp_SysFreeString
0x18005b0b6  mov     eax, ebx
0x18005b0b8  mov     rcx, [rbp+210h+var_40]
0x18005b0bf  xor     rcx, rsp; StackCookie
0x18005b0c2  call    __security_check_cookie
0x18005b0c7  mov     rbx, [rsp+310h+arg_18]
0x18005b0cf  add     rsp, 2E0h
0x18005b0d6  pop     r15
0x18005b0d8  pop     r14
0x18005b0da  pop     r13
0x18005b0dc  pop     r12
0x18005b0de  pop     rdi
0x18005b0df  pop     rsi
0x18005b0e0  pop     rbp
0x18005b0e1  retn
```

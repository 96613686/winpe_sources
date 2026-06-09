# CPublishedApp::GetAppInfo(_AppInfoData *)

- ea: `0x180002ab0`
- end: `0x180002d9d`
- name: `?GetAppInfo@CPublishedApp@@UEAAJPEAU_AppInfoData@@@Z`
- size: `749`
- prototype: `__int64 __fastcall(CPublishedApp *__hidden this, struct _AppInfoData *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180003b78`
- `0x1800058bc`
- `0x180006ac4`
- `0x180090bc8`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002bf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002cc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002bf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002cc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180002bbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d64`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d72`
- `OLEAUT32!__imp_SysFreeString` at `0x180002bbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d64`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d72`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180002be7`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180002cb3`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180002be7`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180002cb3`

## string_xrefs

- `0x180002af3`: `C:\__w\1\s\src\Client\comapi\AppPublisher.cpp`
- `0x180002d09`: `C:\__w\1\s\src\Client\comapi\AppPublisher.cpp`

## pseudocode

```c
__int64 __fastcall CPublishedApp::GetAppInfo(CPublishedApp *this, struct _AppInfoData *a2)
{
  int v3; // ebx
  bool v4; // zf
  __int64 v5; // rdx
  DWORD dwMask; // esi
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, BSTR *); // rbx
  SIZE_T v9; // rbx
  WCHAR *v10; // rax
  wchar_t **v11; // r9
  wchar_t *pszDisplayName; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, BSTR *); // rbx
  UINT v15; // eax
  SIZE_T v16; // rbx
  WCHAR *v17; // rax
  wchar_t **v18; // r9
  wchar_t *pszSupportUrl; // rcx
  unsigned __int64 *v21; // [rsp+20h] [rbp-60h]
  unsigned int v22; // [rsp+28h] [rbp-58h]
  _QWORD v23[2]; // [rsp+40h] [rbp-40h] BYREF
  char v24; // [rsp+50h] [rbp-30h]
  struct _AppInfoData *v25; // [rsp+58h] [rbp-28h] BYREF
  char v26; // [rsp+60h] [rbp-20h] BYREF
  BSTR bstr; // [rsp+68h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v25 = a2;
  bstrString = 0;
  bstr = 0;
  v26 = 1;
  if ( a2 )
  {
    v4 = a2->cbSize == 152;
    v23[0] = &v26;
    v23[1] = &v25;
    v24 = 1;
    if ( v4 )
    {
      if ( *((_QWORD *)this + 10) )
      {
        dwMask = a2->dwMask;
        a2->dwMask = 0;
        a2->pszVersion = 0;
        a2->pszProductID = 0;
        a2->pszRegisteredOwner = 0;
        a2->pszRegisteredCompany = 0;
        a2->pszLanguage = 0;
        a2->pszSupportTelephone = 0;
        a2->pszHelpLink = 0;
        a2->pszInstallLocation = 0;
        a2->pszInstallSource = 0;
        a2->pszInstallDate = 0;
        a2->pszContact = 0;
        a2->pszComments = 0;
        a2->pszImage = 0;
        a2->pszReadmeUrl = 0;
        a2->pszUpdateInfoUrl = 0;
        a2->pszDisplayName = 0;
        a2->pszSupportUrl = 0;
        if ( (dwMask & 1) != 0 )
        {
          v7 = *((_QWORD *)this + 10);
          v8 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v7 + 56LL);
          SysFreeString(bstrString);
          v3 = v8(v7, &bstrString);
          if ( v3 < 0 )
          {
            v5 = 737;
            goto LABEL_23;
          }
          v9 = SysStringByteLen(bstrString) + 2;
          v10 = (WCHAR *)CoTaskMemAlloc(v9);
          v25->pszDisplayName = v10;
          pszDisplayName = v25->pszDisplayName;
          if ( !pszDisplayName )
          {
            v3 = -2147024882;
            v5 = 745;
            goto LABEL_23;
          }
          v3 = StringCbCopyExW(pszDisplayName, v9, bstrString, v11, v21, v22);
          if ( v3 < 0 )
          {
            v5 = 748;
            goto LABEL_23;
          }
          v25->dwMask |= 1u;
          WUTrace(0, 0, 0x10000, 4, 0, L"AppInfo DisplayName: %ws");
        }
        if ( (dwMask & 0x80u) != 0 )
        {
          v13 = *((_QWORD *)this + 10);
          v14 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v13 + 328LL);
          SysFreeString(bstr);
          v3 = v14(v13, &bstr);
          if ( v3 < 0 )
          {
            v5 = 762;
            goto LABEL_23;
          }
          v15 = SysStringByteLen(bstr);
          if ( v15 )
          {
            v16 = v15 + 2;
            v17 = (WCHAR *)CoTaskMemAlloc(v16);
            v25->pszSupportUrl = v17;
            pszSupportUrl = v25->pszSupportUrl;
            if ( !pszSupportUrl )
            {
              v3 = -2147024882;
              v5 = 775;
              goto LABEL_23;
            }
            v3 = StringCbCopyExW(pszSupportUrl, v16, bstr, v18, v21, v22);
            if ( v3 < 0 )
            {
              v5 = 782;
              goto LABEL_23;
            }
            v25->dwMask |= 0x80u;
          }
          WUTrace(0, 0, 0x10000, 4, 0, L"AppInfo SupportURL: %ws", bstr);
        }
        v26 = 0;
        v3 = 0;
        goto LABEL_27;
      }
      v3 = -2147467261;
      v5 = 702;
    }
    else
    {
      v3 = -2147024809;
      v5 = 699;
    }
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\AppPublisher.cpp",
      (const char *)(unsigned int)v3,
      (int)v21);
LABEL_27:
    wil::details::lambda_call__lambda_543fa54d9138ce78a3e0d8634e49346c___::_lambda_call__lambda_543fa54d9138ce78a3e0d8634e49346c___(v23);
    goto LABEL_28;
  }
  v3 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A9,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\AppPublisher.cpp",
    (const char *)0x80004003LL,
    (int)v21);
LABEL_28:
  SysFreeString(bstr);
  bstr = 0;
  SysFreeString(bstrString);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002ab0  mov     [rsp-28h+arg_10], rbx
0x180002ab5  push    rbp
0x180002ab6  push    rsi
0x180002ab7  push    rdi
0x180002ab8  push    r14
0x180002aba  push    r15
0x180002abc  mov     rbp, rsp
0x180002abf  sub     rsp, 80h
0x180002ac6  mov     rax, cs:__security_cookie
0x180002acd  xor     rax, rsp
0x180002ad0  mov     [rbp+var_8], rax
0x180002ad4  xor     r15d, r15d
0x180002ad7  mov     [rbp+var_28], rdx
0x180002adb  mov     [rbp+bstrString], r15
0x180002adf  mov     r14, rcx
0x180002ae2  mov     [rbp+bstr], r15
0x180002ae6  mov     [rbp+var_20], 1
0x180002aea  test    rdx, rdx
0x180002aed  jnz     short loc_180002B11
0x180002aef  mov     rcx, [rbp+28h]; this
0x180002af3  lea     r8, aCW1SSrcClientC_27; "C:\\__w\\1\\s\\src\\Client\\comapi\\App"...
0x180002afa  mov     ebx, 80004003h
0x180002aff  mov     edx, 2A9h; void *
0x180002b04  mov     r9d, ebx; char *
0x180002b07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002b0c  jmp     loc_180002D60
0x180002b11  cmp     dword ptr [rdx], 98h
0x180002b17  lea     rax, [rbp+var_20]
0x180002b1b  mov     [rbp+var_40], rax
0x180002b1f  lea     rax, [rbp+var_28]
0x180002b23  mov     [rbp+var_38], rax
0x180002b27  mov     [rbp+var_30], 1
0x180002b2b  jz      short loc_180002B3C
0x180002b2d  mov     ebx, 80070057h
0x180002b32  mov     edx, 2BBh
0x180002b37  jmp     loc_180002D05
0x180002b3c  cmp     [rcx+50h], r15
0x180002b40  jnz     short loc_180002B51
0x180002b42  mov     ebx, 80004003h
0x180002b47  mov     edx, 2BEh
0x180002b4c  jmp     loc_180002D05
0x180002b51  mov     esi, [rdx+4]
0x180002b54  mov     [rdx+4], r15d
0x180002b58  mov     [rdx+10h], r15
0x180002b5c  mov     [rdx+20h], r15
0x180002b60  mov     [rdx+28h], r15
0x180002b64  mov     [rdx+30h], r15
0x180002b68  mov     [rdx+38h], r15
0x180002b6c  mov     [rdx+48h], r15
0x180002b70  mov     [rdx+50h], r15
0x180002b74  mov     [rdx+58h], r15
0x180002b78  mov     [rdx+60h], r15
0x180002b7c  mov     [rdx+68h], r15
0x180002b80  mov     [rdx+70h], r15
0x180002b84  mov     [rdx+78h], r15
0x180002b88  mov     [rdx+80h], r15
0x180002b8f  mov     [rdx+88h], r15
0x180002b96  mov     [rdx+90h], r15
0x180002b9d  mov     [rdx+8], r15
0x180002ba1  mov     [rdx+40h], r15
0x180002ba5  test    sil, 1
0x180002ba9  jz      loc_180002C72
0x180002baf  mov     rdi, [rcx+50h]
0x180002bb3  mov     rcx, [rbp+bstrString]; bstrString
0x180002bb7  mov     rax, [rdi]
0x180002bba  mov     rbx, [rax+38h]
0x180002bbe  call    cs:__imp_SysFreeString
0x180002bc4  lea     rdx, [rbp+bstrString]
0x180002bc8  mov     rcx, rdi
0x180002bcb  mov     rax, rbx
0x180002bce  call    _guard_dispatch_icall
0x180002bd3  mov     ebx, eax
0x180002bd5  test    eax, eax
0x180002bd7  jns     short loc_180002BE3
0x180002bd9  mov     edx, 2E1h
0x180002bde  jmp     loc_180002D05
0x180002be3  mov     rcx, [rbp+bstrString]; bstr
0x180002be7  call    cs:__imp_SysStringByteLen
0x180002bed  add     eax, 2
0x180002bf0  mov     ecx, eax; cb
0x180002bf2  mov     ebx, eax
0x180002bf4  call    cs:__imp_CoTaskMemAlloc
0x180002bfa  mov     rcx, rax
0x180002bfd  mov     rax, [rbp+var_28]
0x180002c01  mov     [rax+8], rcx
0x180002c05  mov     rax, [rbp+var_28]
0x180002c09  mov     rcx, [rax+8]; wchar_t *
0x180002c0d  test    rcx, rcx
0x180002c10  jnz     short loc_180002C21
0x180002c12  mov     ebx, 8007000Eh
0x180002c17  mov     edx, 2E9h
0x180002c1c  jmp     loc_180002D05
0x180002c21  mov     r8, [rbp+bstrString]; wchar_t *
0x180002c25  mov     rdx, rbx; unsigned __int64
0x180002c28  call    ?StringCbCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCbCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180002c2d  mov     ebx, eax
0x180002c2f  test    eax, eax
0x180002c31  jns     short loc_180002C3D
0x180002c33  mov     edx, 2ECh
0x180002c38  jmp     loc_180002D05
0x180002c3d  mov     rax, [rbp+var_28]
0x180002c41  xor     edx, edx
0x180002c43  xor     ecx, ecx
0x180002c45  mov     r8d, 10000h
0x180002c4b  or      dword ptr [rax+4], 1
0x180002c4f  lea     r9d, [rdx+4]
0x180002c53  mov     rax, [rbp+bstrString]
0x180002c57  mov     [rsp+80h+var_50], rax
0x180002c5c  lea     rax, aAppinfoDisplay; "AppInfo DisplayName: %ws"
0x180002c63  mov     qword ptr [rsp+80h+var_58], rax; unsigned int
0x180002c68  mov     [rsp+80h+var_60], r15; int
0x180002c6d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180002c72  test    sil, sil
0x180002c75  jns     loc_180002D50
0x180002c7b  mov     rdi, [r14+50h]
0x180002c7f  mov     rcx, [rbp+bstr]; bstrString
0x180002c83  mov     rax, [rdi]
0x180002c86  mov     rbx, [rax+148h]
0x180002c8d  call    cs:__imp_SysFreeString
0x180002c93  lea     rdx, [rbp+bstr]
0x180002c97  mov     rcx, rdi
0x180002c9a  mov     rax, rbx
0x180002c9d  call    _guard_dispatch_icall
0x180002ca2  mov     ebx, eax
0x180002ca4  test    eax, eax
0x180002ca6  jns     short loc_180002CAF
0x180002ca8  mov     edx, 2FAh
0x180002cad  jmp     short loc_180002D05
0x180002caf  mov     rcx, [rbp+bstr]; bstr
0x180002cb3  call    cs:__imp_SysStringByteLen
0x180002cb9  test    eax, eax
0x180002cbb  jz      short loc_180002D23
0x180002cbd  add     eax, 2
0x180002cc0  mov     ecx, eax; cb
0x180002cc2  mov     ebx, eax
0x180002cc4  call    cs:__imp_CoTaskMemAlloc
0x180002cca  mov     rcx, rax
0x180002ccd  mov     rax, [rbp+var_28]
0x180002cd1  mov     [rax+40h], rcx
0x180002cd5  mov     rax, [rbp+var_28]
0x180002cd9  mov     rcx, [rax+40h]; wchar_t *
0x180002cdd  test    rcx, rcx
0x180002ce0  jnz     short loc_180002CEE
0x180002ce2  mov     ebx, 8007000Eh
0x180002ce7  mov     edx, 307h
0x180002cec  jmp     short loc_180002D05
0x180002cee  mov     r8, [rbp+bstr]; wchar_t *
0x180002cf2  mov     rdx, rbx; unsigned __int64
0x180002cf5  call    ?StringCbCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCbCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180002cfa  mov     ebx, eax
0x180002cfc  test    eax, eax
0x180002cfe  jns     short loc_180002D1A
0x180002d00  mov     edx, 30Eh; void *
0x180002d05  mov     rcx, [rbp+28h]; this
0x180002d09  lea     r8, aCW1SSrcClientC_27; "C:\\__w\\1\\s\\src\\Client\\comapi\\App"...
0x180002d10  mov     r9d, ebx; char *
0x180002d13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002d18  jmp     short loc_180002D57
0x180002d1a  mov     rax, [rbp+var_28]
0x180002d1e  bts     dword ptr [rax+4], 7
0x180002d23  mov     rax, [rbp+bstr]
0x180002d27  xor     edx, edx
0x180002d29  mov     [rsp+80h+var_50], rax
0x180002d2e  xor     ecx, ecx
0x180002d30  lea     rax, aAppinfoSupport; "AppInfo SupportURL: %ws"
0x180002d37  mov     r8d, 10000h
0x180002d3d  mov     qword ptr [rsp+80h+var_58], rax
0x180002d42  lea     r9d, [rdx+4]
0x180002d46  mov     [rsp+80h+var_60], r15
0x180002d4b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180002d50  mov     [rbp+var_20], r15b
0x180002d54  mov     ebx, r15d
0x180002d57  lea     rcx, [rbp+var_40]
0x180002d5b  call    wil__details__lambda_call__lambda_543fa54d9138ce78a3e0d8634e49346c______lambda_call__lambda_543fa54d9138ce78a3e0d8634e49346c___
0x180002d60  mov     rcx, [rbp+bstr]; bstrString
0x180002d64  call    cs:__imp_SysFreeString
0x180002d6a  mov     rcx, [rbp+bstrString]; bstrString
0x180002d6e  mov     [rbp+bstr], r15
0x180002d72  call    cs:__imp_SysFreeString
0x180002d78  mov     eax, ebx
0x180002d7a  mov     rcx, [rbp+var_8]
0x180002d7e  xor     rcx, rsp; StackCookie
0x180002d81  call    __security_check_cookie
0x180002d86  mov     rbx, [rsp+80h+arg_10]
0x180002d8e  add     rsp, 80h
0x180002d95  pop     r15
0x180002d97  pop     r14
0x180002d99  pop     rdi
0x180002d9a  pop     rsi
0x180002d9b  pop     rbp
0x180002d9c  retn
```

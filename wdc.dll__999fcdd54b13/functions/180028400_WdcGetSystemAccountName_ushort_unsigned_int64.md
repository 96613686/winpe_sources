# WdcGetSystemAccountName(ushort *,unsigned __int64)

- ea: `0x180028400`
- end: `0x180028575`
- name: `?WdcGetSystemAccountName@@YAJPEAG_K@Z`
- size: `373`
- prototype: `__int64 __fastcall(LPWSTR Name, unsigned __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002f114`
- `0x1800552f8`
- `0x180059adc`
- `0x180066ed8`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x180019990`
- `0x180028400`
- `0x18003a3c0`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x18002848c`
- `ADVAPI32!CreateWellKnownSid` at `0x18002848c`
- `KERNEL32!GetLastError` at `0x180028496`
- `KERNEL32!GetLastError` at `0x18002850e`
- `KERNEL32!GetLastError` at `0x180028496`
- `KERNEL32!GetLastError` at `0x18002850e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180028500`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180028500`

## pseudocode

```c
__int64 __fastcall WdcGetSystemAccountName(LPWSTR Name)
{
  int v2; // eax
  signed int v3; // ebx
  const char *v4; // rdx
  int v5; // r8d
  signed int v6; // eax
  WCHAR *v7; // rax
  WCHAR *v8; // rdi
  const char *v9; // rdx
  int v10; // r8d
  signed int LastError; // eax
  int cchReferencedDomainName; // [rsp+20h] [rbp-49h]
  LPDWORD cchReferencedDomainNamea; // [rsp+20h] [rbp-49h]
  DWORD cchName; // [rsp+30h] [rbp-39h] BYREF
  DWORD v16; // [rsp+34h] [rbp-35h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-31h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+3Ch] [rbp-2Dh] BYREF
  _BYTE pSid[80]; // [rsp+40h] [rbp-29h] BYREF

  peUse = 0;
  cbSid = 68;
  v16 = 260;
  cchName = 0;
  v2 = ULongLongToULong(0x104u, &cchName);
  v3 = v2;
  if ( v2 < 0 )
    goto LABEL_2;
  if ( cchName )
    *Name = 0;
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
  {
LABEL_11:
    v7 = (WCHAR *)WdcAlloc(2LL * v16, v4, v5);
    v8 = v7;
    if ( !v7 )
    {
      v3 = -2147024882;
      cchReferencedDomainName = -2147024882;
      goto LABEL_3;
    }
    *v7 = 0;
    if ( LookupAccountSidLocalW(pSid, Name, &cchName, v7, &v16, &peUse) )
    {
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 >= 0 )
          goto LABEL_24;
      }
      else
      {
        v3 = -2147467259;
      }
      LODWORD(cchReferencedDomainNamea) = v3;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
        "WdcGetSystemAccountName",
        0,
        L"FAILURE: 0x%08x",
        cchReferencedDomainNamea);
    }
LABEL_24:
    WdcFree(v8, v9, v10);
    return (unsigned int)v3;
  }
  v6 = GetLastError();
  v3 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    if ( v3 >= 0 )
      goto LABEL_11;
  }
  else
  {
    v3 = -2147467259;
  }
  v2 = v3;
LABEL_2:
  cchReferencedDomainName = v2;
LABEL_3:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
    "WdcGetSystemAccountName",
    0,
    L"FAILURE: 0x%08x",
    cchReferencedDomainName);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180028400  push    rbp
0x180028402  push    rbx
0x180028403  push    rsi
0x180028404  push    rdi
0x180028405  lea     rbp, [rsp-3Fh]
0x18002840a  sub     rsp, 0A8h
0x180028411  mov     rax, cs:__security_cookie
0x180028418  xor     rax, rsp
0x18002841b  mov     [rbp+57h+var_30], rax
0x18002841f  mov     rsi, rcx
0x180028422  mov     [rbp+57h+var_84], 0
0x180028429  mov     ecx, 104h; unsigned __int64
0x18002842e  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180028435  lea     rdx, [rbp+57h+cchName]; unsigned int *
0x180028439  mov     [rbp+57h+var_8C], ecx
0x18002843c  mov     [rbp+57h+cchName], 0
0x180028443  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180028448  mov     ebx, eax
0x18002844a  test    eax, eax
0x18002844c  jns     short loc_180028474
0x18002844e  mov     dword ptr [rsp+0C0h+cchReferencedDomainName], eax
0x180028452  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180028459  xor     r8d, r8d; int
0x18002845c  lea     rdx, aWdcgetsystemac; "WdcGetSystemAccountName"
0x180028463  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x18002846a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002846f  jmp     loc_18002855B
0x180028474  cmp     [rbp+57h+cchName], 0
0x180028478  jbe     short loc_18002847F
0x18002847a  xor     eax, eax
0x18002847c  mov     [rsi], ax
0x18002847f  xor     edx, edx; DomainSid
0x180028481  lea     r9, [rbp+57h+cbSid]; cbSid
0x180028485  lea     r8, [rbp+57h+pSid]; pSid
0x180028489  lea     ecx, [rdx+16h]; WellKnownSidType
0x18002848c  call    cs:__imp_CreateWellKnownSid
0x180028492  test    eax, eax
0x180028494  jnz     short loc_1800284B1
0x180028496  call    cs:__imp_GetLastError
0x18002849c  mov     ebx, eax
0x18002849e  test    eax, eax
0x1800284a0  jz      short loc_1800284CF
0x1800284a2  jle     short loc_1800284AD
0x1800284a4  movzx   ebx, ax
0x1800284a7  or      ebx, 80070000h
0x1800284ad  test    ebx, ebx
0x1800284af  js      short loc_1800284D4
0x1800284b1  mov     ecx, [rbp+57h+var_8C]
0x1800284b4  add     rcx, rcx; dwBytes
0x1800284b7  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800284bc  mov     rdi, rax
0x1800284bf  test    rax, rax
0x1800284c2  jnz     short loc_1800284DB
0x1800284c4  mov     ebx, 8007000Eh
0x1800284c9  mov     dword ptr [rsp+0C0h+cchReferencedDomainName], ebx
0x1800284cd  jmp     short loc_180028452
0x1800284cf  mov     ebx, 80004005h
0x1800284d4  mov     eax, ebx
0x1800284d6  jmp     loc_18002844E
0x1800284db  xor     eax, eax
0x1800284dd  lea     r8, [rbp+57h+cchName]; cchName
0x1800284e1  mov     [rdi], ax
0x1800284e4  lea     rcx, [rbp+57h+pSid]; Sid
0x1800284e8  lea     rax, [rbp+57h+var_84]
0x1800284ec  mov     r9, rdi; ReferencedDomainName
0x1800284ef  mov     [rsp+0C0h+peUse], rax; peUse
0x1800284f4  mov     rdx, rsi; Name
0x1800284f7  lea     rax, [rbp+57h+var_8C]
0x1800284fb  mov     [rsp+0C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180028500  call    cs:__imp_LookupAccountSidLocalW
0x180028506  test    eax, eax
0x180028508  jz      short loc_18002850E
0x18002850a  xor     ebx, ebx
0x18002850c  jmp     short loc_180028553
0x18002850e  call    cs:__imp_GetLastError
0x180028514  mov     ebx, eax
0x180028516  test    eax, eax
0x180028518  jz      short loc_18002852B
0x18002851a  jle     short loc_180028525
0x18002851c  movzx   ebx, ax
0x18002851f  or      ebx, 80070000h
0x180028525  test    ebx, ebx
0x180028527  jns     short loc_180028553
0x180028529  jmp     short loc_180028530
0x18002852b  mov     ebx, 80004005h
0x180028530  mov     eax, ebx
0x180028532  mov     dword ptr [rsp+0C0h+cchReferencedDomainName], ebx
0x180028536  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002853d  xor     r8d, r8d; int
0x180028540  lea     rdx, aWdcgetsystemac; "WdcGetSystemAccountName"
0x180028547  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x18002854e  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180028553  mov     rcx, rdi; void *
0x180028556  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18002855b  mov     eax, ebx
0x18002855d  mov     rcx, [rbp+57h+var_30]
0x180028561  xor     rcx, rsp; StackCookie
0x180028564  call    __security_check_cookie
0x180028569  add     rsp, 0A8h
0x180028570  pop     rdi
0x180028571  pop     rsi
0x180028572  pop     rbx
0x180028573  pop     rbp
0x180028574  retn
```

# RegOpenCachedConnectionKey(ushort *,HKEY__ * *)

- ea: `0x140072c7c`
- end: `0x140072f16`
- name: `?RegOpenCachedConnectionKey@@YAKPEAGPEAPEAUHKEY__@@@Z`
- size: `666`
- prototype: `unsigned int __fastcall(unsigned __int16 *, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400727d8`

## callees

- `0x140004790`
- `0x14000d9f0`
- `0x140010c4c`
- `0x140015290`
- `0x140016d7c`
- `0x14002d0a0`
- `0x14002dd20`
- `0x140072c7c`
- `0x1400782d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140072eab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140072eab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072db5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072db5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072eb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140072e8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140072e8c`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140072d92`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140072d92`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x140072d68`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x140072d68`

## string_xrefs

- `0x140072e0a`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Print\Providers\Client Side Rendering Print Provider\`
- `0x140072d78`: `Retrieving SID failed in RegOpenCachedConnectionKey.`
- `0x140072da9`: `Converting SID to stringSid failed in RegOpenCachedConnectionKey.`
- `0x140072ec9`: `Invalid input parameter in RegOpenCachedConnectionKey.Unable to fetch Devmode from the Registry.`
- `0x140072d7f`: `RegOpenCachedConnectionKey`
- `0x140072d9e`: `RegOpenCachedConnectionKey`
- `0x140072ed5`: `RegOpenCachedConnectionKey`
- `0x140072dca`: `Successfully obtained the SID, the stringSid is %ws`

## pseudocode

```c
__int64 __fastcall RegOpenCachedConnectionKey(unsigned __int16 *a1, PHKEY phkResult)
{
  WCHAR *v4; // rbx
  struct NCoreLibrary::TString *v5; // rdx
  __int64 v6; // r14
  unsigned __int64 v7; // rax
  DWORD LastError; // edi
  int v9; // eax
  NCoreLibrary::TString *v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // edi
  unsigned __int16 *v13; // rax
  WCHAR *v14; // rsi
  int v15; // eax
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpAccountName; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE Sid[80]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+B0h] [rbp-50h] BYREF

  cbSid = 68;
  peUse = SidTypeUser;
  v4 = &NCoreLibrary::TString::gszNullState;
  lpAccountName = &NCoreLibrary::TString::gszNullState;
  StringSid = 0;
  memset_0(ReferencedDomainName, 0, 0x208u);
  cchReferencedDomainName = 260;
  if ( !a1 )
    goto LABEL_26;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  if ( v7 >= 0x21B )
  {
LABEL_26:
    LastError = 87;
    PrvSpoolssTelemetry::WriteDbgTraceInfo(
      "RegOpenCachedConnectionKey",
      L"Invalid input parameter in RegOpenCachedConnectionKey.Unable to fetch Devmode from the Registry.");
    goto LABEL_27;
  }
  LastError = 0;
  v9 = NUtilityLibrary::UserName((NUtilityLibrary *)&lpAccountName, v5);
  if ( v9 < 0 )
  {
    LastError = (unsigned __int16)v9;
    if ( (_WORD)v9 )
    {
      v4 = (WCHAR *)lpAccountName;
      goto LABEL_27;
    }
  }
  v4 = (WCHAR *)lpAccountName;
  if ( !LookupAccountNameW(0, lpAccountName, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    PrvSpoolssTelemetry::WriteDbgTraceInfo(
      "RegOpenCachedConnectionKey",
      L"Retrieving SID failed in RegOpenCachedConnectionKey.");
LABEL_12:
    LastError = GetLastError();
    goto LABEL_14;
  }
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    PrvSpoolssTelemetry::WriteDbgTraceInfo(
      "RegOpenCachedConnectionKey",
      L"Converting SID to stringSid failed in RegOpenCachedConnectionKey.");
    goto LABEL_12;
  }
  PrvSpoolssTelemetry::WriteDbgTraceInfo(
    "RegOpenCachedConnectionKey",
    L"Successfully obtained the SID, the stringSid is %ws",
    StringSid);
LABEL_14:
  if ( !LastError )
  {
    v11 = -1;
    do
      ++v11;
    while ( StringSid[v11] );
    v12 = v11 + 660;
    v13 = (unsigned __int16 *)DllAllocSplMem((unsigned int)(2 * (v11 + 660)));
    v14 = v13;
    if ( v13 )
    {
      v15 = StringCchCatW(
              v13,
              v12,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print\\Providers\\Client Side Rendering Print Provider\\");
      if ( v15 < 0
        || (v15 = StringCchCatW(v14, v12, StringSid), v15 < 0)
        || (v15 = StringCchCatW(v14, v12, L"\\Printers\\Connections\\"), v15 < 0) )
      {
        LastError = (unsigned __int16)v15;
      }
      else
      {
        do
          ++v6;
        while ( StringSid[v6] );
        FormatPrinterForRegistryKey(a1, &v14[v6 + 120], v12 - (unsigned int)v6 - 120);
        LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 0x20019u, phkResult);
      }
      HeapFree(g_hSpoolssHeap, 0, v14);
    }
    else
    {
      LastError = GetLastError();
    }
  }
LABEL_27:
  NCoreLibrary::TString::vFree(v10, v4);
  return LastError;
}

```

## disassembly

```asm
0x140072c7c  mov     [rsp-8+arg_10], rbx
0x140072c81  push    rbp
0x140072c82  push    rsi
0x140072c83  push    rdi
0x140072c84  push    r12
0x140072c86  push    r13
0x140072c88  push    r14
0x140072c8a  push    r15
0x140072c8c  lea     rbp, [rsp-1D0h]
0x140072c94  sub     rsp, 2D0h
0x140072c9b  mov     rax, cs:__security_cookie
0x140072ca2  xor     rax, rsp
0x140072ca5  mov     [rbp+200h+var_40], rax
0x140072cac  mov     r13, rdx
0x140072caf  mov     [rsp+300h+cbSid], 44h ; 'D'
0x140072cb7  mov     r12, rcx
0x140072cba  mov     [rsp+300h+var_2B8], 1
0x140072cc2  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x140072cc9  xor     r15d, r15d
0x140072ccc  xor     edx, edx; Val
0x140072cce  mov     [rsp+300h+lpAccountName], rbx
0x140072cd3  lea     rcx, [rbp+200h+var_250]; void *
0x140072cd7  mov     [rsp+300h+StringSid], r15
0x140072cdc  mov     r8d, 208h; Size
0x140072ce2  call    memset_0
0x140072ce7  mov     [rsp+300h+var_2B4], 104h
0x140072cef  test    r12, r12
0x140072cf2  jz      loc_140072EC9
0x140072cf8  or      r14, 0FFFFFFFFFFFFFFFFh
0x140072cfc  mov     rax, r14
0x140072cff  inc     rax
0x140072d02  cmp     [r12+rax*2], r15w
0x140072d07  jnz     short loc_140072CFF
0x140072d09  cmp     rax, 21Bh
0x140072d0f  jnb     loc_140072EC9
0x140072d15  lea     rcx, [rsp+300h+lpAccountName]; this
0x140072d1a  mov     edi, r15d
0x140072d1d  call    ?UserName@NUtilityLibrary@@YAJAEAVTString@NCoreLibrary@@@Z; NUtilityLibrary::UserName(NCoreLibrary::TString &)
0x140072d22  test    eax, eax
0x140072d24  jns     short loc_140072D37
0x140072d26  movzx   edi, ax
0x140072d29  test    edi, edi
0x140072d2b  jz      short loc_140072D37
0x140072d2d  mov     rbx, [rsp+300h+lpAccountName]
0x140072d32  jmp     loc_140072EE1
0x140072d37  mov     rbx, [rsp+300h+lpAccountName]
0x140072d3c  lea     rax, [rsp+300h+var_2B8]
0x140072d41  mov     [rsp+300h+peUse], rax; peUse
0x140072d46  lea     r9, [rsp+300h+cbSid]; cbSid
0x140072d4b  lea     rax, [rsp+300h+var_2B4]
0x140072d50  mov     rdx, rbx; lpAccountName
0x140072d53  mov     [rsp+300h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140072d58  lea     r8, [rsp+300h+Sid]; Sid
0x140072d5d  lea     rax, [rbp+200h+var_250]
0x140072d61  xor     ecx, ecx; lpSystemName
0x140072d63  mov     [rsp+300h+ReferencedDomainName], rax; ReferencedDomainName
0x140072d68  call    cs:__imp_LookupAccountNameW
0x140072d6f  nop     dword ptr [rax+rax+00h]
0x140072d74  test    eax, eax
0x140072d76  jnz     short loc_140072D88
0x140072d78  lea     rdx, aRetrievingSidF; "Retrieving SID failed in RegOpenCachedC"...
0x140072d7f  lea     rcx, aRegopencachedc; "RegOpenCachedConnectionKey"
0x140072d86  jmp     short loc_140072DB0
0x140072d88  lea     rdx, [rsp+300h+StringSid]; StringSid
0x140072d8d  lea     rcx, [rsp+300h+Sid]; Sid
0x140072d92  call    cs:__imp_ConvertSidToStringSidW
0x140072d99  nop     dword ptr [rax+rax+00h]
0x140072d9e  lea     rcx, aRegopencachedc; "RegOpenCachedConnectionKey"
0x140072da5  test    eax, eax
0x140072da7  jnz     short loc_140072DC5
0x140072da9  lea     rdx, aConvertingSidT; "Converting SID to stringSid failed in R"...
0x140072db0  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140072db5  call    cs:__imp_GetLastError
0x140072dbc  nop     dword ptr [rax+rax+00h]
0x140072dc1  mov     edi, eax
0x140072dc3  jmp     short loc_140072DD6
0x140072dc5  mov     r8, [rsp+300h+StringSid]
0x140072dca  lea     rdx, aSuccessfullyOb; "Successfully obtained the SID, the stri"...
0x140072dd1  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140072dd6  test    edi, edi
0x140072dd8  jnz     loc_140072EE1
0x140072dde  mov     rcx, [rsp+300h+StringSid]
0x140072de3  mov     rax, r14
0x140072de6  inc     rax
0x140072de9  cmp     [rcx+rax*2], r15w
0x140072dee  jnz     short loc_140072DE6
0x140072df0  lea     edi, [rax+294h]
0x140072df6  lea     ecx, [rdi+rdi]; dwBytes
0x140072df9  call    DllAllocSplMem
0x140072dfe  mov     rsi, rax
0x140072e01  test    rax, rax
0x140072e04  jz      loc_140072EB9
0x140072e0a  lea     r8, gszClientSideRenderingPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140072e11  mov     edx, edi; unsigned __int64
0x140072e13  mov     rcx, rax; unsigned __int16 *
0x140072e16  mov     r15d, edi
0x140072e19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140072e1e  test    eax, eax
0x140072e20  js      short loc_140072E9C
0x140072e22  mov     r8, [rsp+300h+StringSid]; unsigned __int16 *
0x140072e27  mov     edx, r15d; unsigned __int64
0x140072e2a  mov     rcx, rsi; unsigned __int16 *
0x140072e2d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140072e32  test    eax, eax
0x140072e34  js      short loc_140072E9C
0x140072e36  lea     r8, gszPrinterConnectionsPath; "\\Printers\\Connections\\"
0x140072e3d  mov     edx, r15d; unsigned __int64
0x140072e40  mov     rcx, rsi; unsigned __int16 *
0x140072e43  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140072e48  xor     ecx, ecx
0x140072e4a  test    eax, eax
0x140072e4c  js      short loc_140072E9C
0x140072e4e  mov     rax, [rsp+300h+StringSid]
0x140072e53  inc     r14
0x140072e56  cmp     [rax+r14*2], cx
0x140072e5b  jnz     short loc_140072E53
0x140072e5d  sub     edi, r14d
0x140072e60  lea     rdx, [r14+78h]
0x140072e64  lea     rdx, [rsi+rdx*2]; unsigned __int16 *
0x140072e68  mov     rcx, r12; unsigned __int16 *
0x140072e6b  lea     r8d, [rdi-78h]; unsigned __int64
0x140072e6f  call    FormatPrinterForRegistryKey
0x140072e74  mov     r9d, 20019h; samDesired
0x140072e7a  mov     [rsp+300h+ReferencedDomainName], r13; phkResult
0x140072e7f  xor     r8d, r8d; ulOptions
0x140072e82  mov     rdx, rsi; lpSubKey
0x140072e85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140072e8c  call    cs:__imp_RegOpenKeyExW
0x140072e93  nop     dword ptr [rax+rax+00h]
0x140072e98  mov     edi, eax
0x140072e9a  jmp     short loc_140072E9F
0x140072e9c  movzx   edi, ax
0x140072e9f  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140072ea6  mov     r8, rsi; lpMem
0x140072ea9  xor     edx, edx; dwFlags
0x140072eab  call    cs:__imp_HeapFree
0x140072eb2  nop     dword ptr [rax+rax+00h]
0x140072eb7  jmp     short loc_140072EE1
0x140072eb9  call    cs:__imp_GetLastError
0x140072ec0  nop     dword ptr [rax+rax+00h]
0x140072ec5  mov     edi, eax
0x140072ec7  jmp     short loc_140072EE1
0x140072ec9  lea     rdx, aInvalidInputPa; "Invalid input parameter in RegOpenCache"...
0x140072ed0  mov     edi, 57h ; 'W'
0x140072ed5  lea     rcx, aRegopencachedc; "RegOpenCachedConnectionKey"
0x140072edc  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140072ee1  mov     rdx, rbx; void *
0x140072ee4  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x140072ee9  mov     eax, edi
0x140072eeb  mov     rcx, [rbp+200h+var_40]
0x140072ef2  xor     rcx, rsp; StackCookie
0x140072ef5  call    __security_check_cookie
0x140072efa  mov     rbx, [rsp+300h+arg_10]
0x140072f02  add     rsp, 2D0h
0x140072f09  pop     r15
0x140072f0b  pop     r14
0x140072f0d  pop     r13
0x140072f0f  pop     r12
0x140072f11  pop     rdi
0x140072f12  pop     rsi
0x140072f13  pop     rbp
0x140072f14  retn
```

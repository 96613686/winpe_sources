# RegOpenCachedConnectionKey(ushort *,HKEY__ * *)

- ea: `0x14006c004`
- end: `0x14006c279`
- name: `?RegOpenCachedConnectionKey@@YAKPEAGPEAPEAUHKEY__@@@Z`
- size: `629`
- prototype: `unsigned int __fastcall(unsigned __int16 *, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006bbc8`

## callees

- `0x1400041c0`
- `0x14000c8b0`
- `0x14000fa4c`
- `0x140013fe8`
- `0x140015538`
- `0x14002abc0`
- `0x14002b810`
- `0x14006c004`
- `0x140071328`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006c21b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006c21b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c223`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006c202`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006c202`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14006c114`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14006c114`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14006c0f0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14006c0f0`

## string_xrefs

- `0x14006c180`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Print\Providers\Client Side Rendering Print Provider\`
- `0x14006c22d`: `Invalid input parameter in RegOpenCachedConnectionKey.Unable to fetch Devmode from the Registry.`
- `0x14006c101`: `RegOpenCachedConnectionKey`
- `0x14006c11a`: `RegOpenCachedConnectionKey`
- `0x14006c239`: `RegOpenCachedConnectionKey`
- `0x14006c140`: `Successfully obtained the SID, the stringSid is %ws`
- `0x14006c0fa`: `Retrieving SID failed in RegOpenCachedConnectionKey.`
- `0x14006c125`: `Converting SID to stringSid failed in RegOpenCachedConnectionKey.`

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
0x14006c004  mov     [rsp-8+arg_10], rbx
0x14006c009  push    rbp
0x14006c00a  push    rsi
0x14006c00b  push    rdi
0x14006c00c  push    r12
0x14006c00e  push    r13
0x14006c010  push    r14
0x14006c012  push    r15
0x14006c014  lea     rbp, [rsp-1D0h]
0x14006c01c  sub     rsp, 2D0h
0x14006c023  mov     rax, cs:__security_cookie
0x14006c02a  xor     rax, rsp
0x14006c02d  mov     [rbp+200h+var_40], rax
0x14006c034  mov     r13, rdx
0x14006c037  mov     [rsp+300h+cbSid], 44h ; 'D'
0x14006c03f  mov     r12, rcx
0x14006c042  mov     [rsp+300h+var_2B8], 1
0x14006c04a  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14006c051  xor     r15d, r15d
0x14006c054  xor     edx, edx; Val
0x14006c056  mov     [rsp+300h+lpAccountName], rbx
0x14006c05b  lea     rcx, [rbp+200h+var_250]; void *
0x14006c05f  mov     [rsp+300h+StringSid], r15
0x14006c064  mov     r8d, 208h; Size
0x14006c06a  call    memset_0
0x14006c06f  mov     [rsp+300h+var_2B4], 104h
0x14006c077  test    r12, r12
0x14006c07a  jz      loc_14006C22D
0x14006c080  or      r14, 0FFFFFFFFFFFFFFFFh
0x14006c084  mov     rax, r14
0x14006c087  inc     rax
0x14006c08a  cmp     [r12+rax*2], r15w
0x14006c08f  jnz     short loc_14006C087
0x14006c091  cmp     rax, 21Bh
0x14006c097  jnb     loc_14006C22D
0x14006c09d  lea     rcx, [rsp+300h+lpAccountName]; this
0x14006c0a2  mov     edi, r15d
0x14006c0a5  call    ?UserName@NUtilityLibrary@@YAJAEAVTString@NCoreLibrary@@@Z; NUtilityLibrary::UserName(NCoreLibrary::TString &)
0x14006c0aa  test    eax, eax
0x14006c0ac  jns     short loc_14006C0BF
0x14006c0ae  movzx   edi, ax
0x14006c0b1  test    edi, edi
0x14006c0b3  jz      short loc_14006C0BF
0x14006c0b5  mov     rbx, [rsp+300h+lpAccountName]
0x14006c0ba  jmp     loc_14006C245
0x14006c0bf  mov     rbx, [rsp+300h+lpAccountName]
0x14006c0c4  lea     rax, [rsp+300h+var_2B8]
0x14006c0c9  mov     [rsp+300h+peUse], rax; peUse
0x14006c0ce  lea     r9, [rsp+300h+cbSid]; cbSid
0x14006c0d3  lea     rax, [rsp+300h+var_2B4]
0x14006c0d8  mov     rdx, rbx; lpAccountName
0x14006c0db  mov     [rsp+300h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14006c0e0  lea     r8, [rsp+300h+Sid]; Sid
0x14006c0e5  lea     rax, [rbp+200h+var_250]
0x14006c0e9  xor     ecx, ecx; lpSystemName
0x14006c0eb  mov     [rsp+300h+ReferencedDomainName], rax; ReferencedDomainName
0x14006c0f0  call    cs:__imp_LookupAccountNameW
0x14006c0f6  test    eax, eax
0x14006c0f8  jnz     short loc_14006C10A
0x14006c0fa  lea     rdx, aRetrievingSidF; "Retrieving SID failed in RegOpenCachedC"...
0x14006c101  lea     rcx, aRegopencachedc; "RegOpenCachedConnectionKey"
0x14006c108  jmp     short loc_14006C12C
0x14006c10a  lea     rdx, [rsp+300h+StringSid]; StringSid
0x14006c10f  lea     rcx, [rsp+300h+Sid]; Sid
0x14006c114  call    cs:__imp_ConvertSidToStringSidW
0x14006c11a  lea     rcx, aRegopencachedc; "RegOpenCachedConnectionKey"
0x14006c121  test    eax, eax
0x14006c123  jnz     short loc_14006C13B
0x14006c125  lea     rdx, aConvertingSidT; "Converting SID to stringSid failed in R"...
0x14006c12c  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006c131  call    cs:__imp_GetLastError
0x14006c137  mov     edi, eax
0x14006c139  jmp     short loc_14006C14C
0x14006c13b  mov     r8, [rsp+300h+StringSid]
0x14006c140  lea     rdx, aSuccessfullyOb; "Successfully obtained the SID, the stri"...
0x14006c147  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006c14c  test    edi, edi
0x14006c14e  jnz     loc_14006C245
0x14006c154  mov     rcx, [rsp+300h+StringSid]
0x14006c159  mov     rax, r14
0x14006c15c  inc     rax
0x14006c15f  cmp     [rcx+rax*2], r15w
0x14006c164  jnz     short loc_14006C15C
0x14006c166  lea     edi, [rax+294h]
0x14006c16c  lea     ecx, [rdi+rdi]; dwBytes
0x14006c16f  call    DllAllocSplMem
0x14006c174  mov     rsi, rax
0x14006c177  test    rax, rax
0x14006c17a  jz      loc_14006C223
0x14006c180  lea     r8, gszClientSideRenderingPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14006c187  mov     edx, edi; unsigned __int64
0x14006c189  mov     rcx, rax; unsigned __int16 *
0x14006c18c  mov     r15d, edi
0x14006c18f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006c194  test    eax, eax
0x14006c196  js      short loc_14006C20C
0x14006c198  mov     r8, [rsp+300h+StringSid]; unsigned __int16 *
0x14006c19d  mov     edx, r15d; unsigned __int64
0x14006c1a0  mov     rcx, rsi; unsigned __int16 *
0x14006c1a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006c1a8  test    eax, eax
0x14006c1aa  js      short loc_14006C20C
0x14006c1ac  lea     r8, gszPrinterConnectionsPath; "\\Printers\\Connections\\"
0x14006c1b3  mov     edx, r15d; unsigned __int64
0x14006c1b6  mov     rcx, rsi; unsigned __int16 *
0x14006c1b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006c1be  xor     ecx, ecx
0x14006c1c0  test    eax, eax
0x14006c1c2  js      short loc_14006C20C
0x14006c1c4  mov     rax, [rsp+300h+StringSid]
0x14006c1c9  inc     r14
0x14006c1cc  cmp     [rax+r14*2], cx
0x14006c1d1  jnz     short loc_14006C1C9
0x14006c1d3  sub     edi, r14d
0x14006c1d6  lea     rdx, [r14+78h]
0x14006c1da  lea     rdx, [rsi+rdx*2]; unsigned __int16 *
0x14006c1de  mov     rcx, r12; unsigned __int16 *
0x14006c1e1  lea     r8d, [rdi-78h]; unsigned __int64
0x14006c1e5  call    FormatPrinterForRegistryKey
0x14006c1ea  mov     r9d, 20019h; samDesired
0x14006c1f0  mov     [rsp+300h+ReferencedDomainName], r13; phkResult
0x14006c1f5  xor     r8d, r8d; ulOptions
0x14006c1f8  mov     rdx, rsi; lpSubKey
0x14006c1fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006c202  call    cs:__imp_RegOpenKeyExW
0x14006c208  mov     edi, eax
0x14006c20a  jmp     short loc_14006C20F
0x14006c20c  movzx   edi, ax
0x14006c20f  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006c216  mov     r8, rsi; lpMem
0x14006c219  xor     edx, edx; dwFlags
0x14006c21b  call    cs:__imp_HeapFree
0x14006c221  jmp     short loc_14006C245
0x14006c223  call    cs:__imp_GetLastError
0x14006c229  mov     edi, eax
0x14006c22b  jmp     short loc_14006C245
0x14006c22d  lea     rdx, aInvalidInputPa; "Invalid input parameter in RegOpenCache"...
0x14006c234  mov     edi, 57h ; 'W'
0x14006c239  lea     rcx, aRegopencachedc; "RegOpenCachedConnectionKey"
0x14006c240  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006c245  mov     rdx, rbx; void *
0x14006c248  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x14006c24d  mov     eax, edi
0x14006c24f  mov     rcx, [rbp+200h+var_40]
0x14006c256  xor     rcx, rsp; StackCookie
0x14006c259  call    __security_check_cookie
0x14006c25e  mov     rbx, [rsp+300h+arg_10]
0x14006c266  add     rsp, 2D0h
0x14006c26d  pop     r15
0x14006c26f  pop     r14
0x14006c271  pop     r13
0x14006c273  pop     r12
0x14006c275  pop     rdi
0x14006c276  pop     rsi
0x14006c277  pop     rbp
0x14006c278  retn
```

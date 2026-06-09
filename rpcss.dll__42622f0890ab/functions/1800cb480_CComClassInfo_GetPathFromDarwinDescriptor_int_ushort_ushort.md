# CComClassInfo::GetPathFromDarwinDescriptor(int,ushort *,ushort * *)

- ea: `0x1800cb480`
- end: `0x1800cb7f1`
- name: `?GetPathFromDarwinDescriptor@CComClassInfo@@AEAAJHPEAGPEAPEAG@Z`
- size: `881`
- prototype: `int(CComClassInfo *__hidden this, int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005fde4`
- `0x1800cb334`

## callees

- `0x18000b310`
- `0x180018344`
- `0x180034540`
- `0x18007ced0`
- `0x1800b27e0`
- `0x1800b3acc`
- `0x1800b3e9c`
- `0x1800cb480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cb503`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cb6ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cb503`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cb6ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cb787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cb7aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cb787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cb7aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cb5c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cb758`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cb5c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cb758`
- `ext-ms-win-advapi32-msi-l1-1-0!CommandLineFromMsiDescriptor` at `0x1800cb599`
- `ext-ms-win-advapi32-msi-l1-1-0!CommandLineFromMsiDescriptor` at `0x1800cb5dc`
- `ext-ms-win-advapi32-msi-l1-1-0!CommandLineFromMsiDescriptor` at `0x1800cb599`
- `ext-ms-win-advapi32-msi-l1-1-0!CommandLineFromMsiDescriptor` at `0x1800cb5dc`
- `ext-ms-win-msiltcfg-msi-l1-1-0!MsiSetInternalUI` at `0x1800cb50e`
- `ext-ms-win-msiltcfg-msi-l1-1-0!MsiSetInternalUI` at `0x1800cb6b8`
- `ext-ms-win-msiltcfg-msi-l1-1-0!MsiSetInternalUI` at `0x1800cb50e`
- `ext-ms-win-msiltcfg-msi-l1-1-0!MsiSetInternalUI` at `0x1800cb6b8`

## string_xrefs

- `0x1800cb56b`: `onecore\com\combase\catalog\class.cxx`
- `0x1800cb668`: `onecore\com\combase\catalog\class.cxx`
- `0x1800cb727`: `onecore\com\combase\catalog\class.cxx`
- `0x1800cb55f`: `CComClassInfo::GetPathFromDarwinDescriptor`
- `0x1800cb65c`: `CComClassInfo::GetPathFromDarwinDescriptor`
- `0x1800cb712`: `CComClassInfo::GetPathFromDarwinDescriptor`
- `0x1800cb572`: `CLSID:%ws DarwinID:%ws %!HRESULT!`
- `0x1800cb706`: `CLSID:%ws DarwinID:%ws %!HRESULT!`
- `0x1800cb67a`: `CLSID:%ws DarwinID:%ws %!HRESULT! MSIStatus:%!WINERROR!`

## pseudocode

```c
__int64 __fastcall CComClassInfo::GetPathFromDarwinDescriptor(
        CComClassInfo *this,
        int a2,
        unsigned __int16 *a3,
        LPVOID *a4)
{
  INSTALLUILEVEL v9; // r12d
  WCHAR *v10; // rsi
  signed int LastError; // eax
  int v12; // r8d
  signed int v13; // eax
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  __int64 i; // r9
  SIZE_T v17; // rax
  WCHAR *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r8
  signed int v21; // ebx
  signed int v22; // eax
  int v23; // r9d
  SIZE_T v24; // rax
  unsigned __int16 *v25; // rax
  int v26; // [rsp+20h] [rbp-E0h]
  const wchar_t *v27; // [rsp+28h] [rbp-D8h]
  int v28; // [rsp+40h] [rbp-C0h]
  int v29; // [rsp+48h] [rbp-B8h]
  DWORD CommandLineLength[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR CommandLine[264]; // [rsp+60h] [rbp-A0h] BYREF

  CommandLineLength[0] = 0;
  if ( !(unsigned __int8)IsCommandLineFromMsiDescriptorPresent() )
    return 2147500033LL;
  *a4 = 0;
  v9 = INSTALLUILEVEL_NONE;
  CommandLineLength[0] = 260;
  v10 = CommandLine;
  if ( a2 && (unsigned __int8)((__int64 (*)(void))IsMsiSetInternalUIPresent)() )
  {
    SetLastError(0);
    v9 = MsiSetInternalUI(INSTALLUILEVEL_NONE, 0);
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 < 0 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
      ComTraceMessageT<unsigned short *,unsigned short *,long>(
        (__int64)"onecore\\com\\combase\\catalog\\class.cxx",
        (__int64)"CComClassInfo::GetPathFromDarwinDescriptor",
        0x13Cu,
        0,
        (__int64)L"CLSID:%ws DarwinID:%ws %!HRESULT!",
        (__int64)this + 112,
        (__int64)a3,
        v12);
  }
  v13 = CommandLineFromMsiDescriptor(a3, CommandLine, CommandLineLength);
  v15 = CommandLineLength[0] + 1;
  for ( i = -1; ; i = -1 )
  {
    CommandLineLength[0] = v15;
    v20 = (unsigned int)v13;
    if ( v13 != 234 )
      break;
    v17 = 2 * v15;
    if ( !is_mul_ok(v15, 2u) )
      v17 = -1;
    v18 = (WCHAR *)HeapAlloc(g_hHeap, 0, v17);
    v10 = v18;
    if ( !v18 )
    {
      v21 = -2147024882;
      goto LABEL_28;
    }
    v13 = CommandLineFromMsiDescriptor(a3, v18, CommandLineLength);
    v15 = CommandLineLength[0] + 1;
  }
  if ( v13 > 0 )
    v21 = (unsigned __int16)v13 | 0x80070000;
  else
    v21 = v13;
  v19 = 0x80000000LL;
  if ( (int)(v21 + 0x80000000) >= 0 && v21 != -2147024882 )
  {
    v21 = -2147467229;
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v29 = v20;
      v28 = -2147467229;
      v27 = L"CLSID:%ws DarwinID:%ws %!HRESULT! MSIStatus:%!WINERROR!";
      v26 = 0;
      ComTraceMessage(
        2147500067LL,
        "onecore\\com\\combase\\catalog\\class.cxx",
        "CComClassInfo::GetPathFromDarwinDescriptor",
        349);
    }
  }
LABEL_28:
  if ( a2 && (unsigned __int8)IsMsiSetInternalUIPresent(v19, v14, v20, i, v26, v27) )
  {
    SetLastError(0);
    MsiSetInternalUI(v9, 0);
    v22 = GetLastError();
    v23 = v22;
    if ( v22 > 0 )
      v23 = (unsigned __int16)v22 | 0x80070000;
    if ( v23 < 0 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
      ComTraceMessageT<unsigned short *,unsigned short *,long>(
        (__int64)"onecore\\com\\combase\\catalog\\class.cxx",
        (__int64)"CComClassInfo::GetPathFromDarwinDescriptor",
        0x16Bu,
        0,
        (__int64)L"CLSID:%ws DarwinID:%ws %!HRESULT!",
        (__int64)this + 112,
        (__int64)a3,
        v23,
        v28,
        v29);
  }
  if ( !v21 )
  {
    v24 = 2LL * CommandLineLength[0];
    if ( !is_mul_ok(CommandLineLength[0], 2u) )
      v24 = -1;
    v25 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v24);
    *a4 = v25;
    if ( v25 )
    {
      v21 = StringCchCopyW(v25, CommandLineLength[0], v10);
      if ( v21 < 0 )
      {
        HeapFree(g_hHeap, 0, *a4);
        *a4 = 0;
      }
    }
  }
  if ( v10 != CommandLine )
    HeapFree(g_hHeap, 0, v10);
  if ( v21 )
    return (unsigned int)v21;
  else
    return *a4 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1800cb480  mov     [rsp-8+arg_8], rbx
0x1800cb485  push    rbp
0x1800cb486  push    rsi
0x1800cb487  push    rdi
0x1800cb488  push    r12
0x1800cb48a  push    r13
0x1800cb48c  push    r14
0x1800cb48e  push    r15
0x1800cb490  lea     rbp, [rsp-180h]
0x1800cb498  sub     rsp, 280h
0x1800cb49f  mov     rax, cs:__security_cookie
0x1800cb4a6  xor     rax, rsp
0x1800cb4a9  mov     [rbp+1B0h+var_40], rax
0x1800cb4b0  xor     ebx, ebx
0x1800cb4b2  mov     rdi, r9
0x1800cb4b5  mov     [rsp+2B0h+CommandLineLength], ebx
0x1800cb4b9  mov     r14, r8
0x1800cb4bc  mov     r15d, edx
0x1800cb4bf  mov     r13, rcx
0x1800cb4c2  call    IsCommandLineFromMsiDescriptorPresent
0x1800cb4c7  test    al, al
0x1800cb4c9  jnz     short loc_1800CB4D5
0x1800cb4cb  mov     eax, 80004001h
0x1800cb4d0  jmp     loc_1800CB7C7
0x1800cb4d5  mov     [rdi], rbx
0x1800cb4d8  mov     r12d, 2
0x1800cb4de  mov     [rsp+2B0h+CommandLineLength], 104h
0x1800cb4e6  lea     rsi, [rsp+2B0h+CommandLine]
0x1800cb4eb  test    r15d, r15d
0x1800cb4ee  jz      loc_1800CB58C
0x1800cb4f4  call    IsMsiSetInternalUIPresent
0x1800cb4f9  test    al, al
0x1800cb4fb  jz      loc_1800CB58C
0x1800cb501  xor     ecx, ecx; dwErrCode
0x1800cb503  call    cs:__imp_SetLastError
0x1800cb509  xor     edx, edx; phWnd
0x1800cb50b  mov     ecx, r12d; dwUILevel
0x1800cb50e  call    cs:__imp_MsiSetInternalUI
0x1800cb514  mov     r12d, eax
0x1800cb517  call    cs:__imp_GetLastError
0x1800cb51d  mov     r8d, eax
0x1800cb520  test    eax, eax
0x1800cb522  jle     short loc_1800CB52F
0x1800cb524  movzx   r8d, ax
0x1800cb528  or      r8d, 80070000h
0x1800cb52f  test    r8d, r8d
0x1800cb532  jns     short loc_1800CB58C
0x1800cb534  mov     eax, cs:dword_18014E4B8
0x1800cb53a  test    eax, eax
0x1800cb53c  jnz     short loc_1800CB551
0x1800cb53e  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800cb544  jz      short loc_1800CB58C
0x1800cb546  xor     ecx, ecx
0x1800cb548  call    IsWppLevelEnabled
0x1800cb54d  test    al, al
0x1800cb54f  jz      short loc_1800CB58C
0x1800cb551  mov     dword ptr [rsp+2B0h+var_278], r8d
0x1800cb556  lea     rax, [r13+70h]
0x1800cb55a  mov     [rsp+2B0h+var_280], r14
0x1800cb55f  lea     rdx, aCcomclassinfoG_1; "CComClassInfo::GetPathFromDarwinDescrip"...
0x1800cb566  mov     [rsp+2B0h+var_288], rax
0x1800cb56b  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x1800cb572  lea     rax, aClsidWsDarwini; "CLSID:%ws DarwinID:%ws %!HRESULT!"
0x1800cb579  xor     r9d, r9d
0x1800cb57c  mov     r8d, 13Ch
0x1800cb582  mov     [rsp+2B0h+var_290], rax
0x1800cb587  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x1800cb58c  lea     r8, [rsp+2B0h+CommandLineLength]; CommandLineLength
0x1800cb591  mov     rcx, r14; Descriptor
0x1800cb594  lea     rdx, [rsp+2B0h+CommandLine]; CommandLine
0x1800cb599  call    cs:__imp_CommandLineFromMsiDescriptor
0x1800cb59f  mov     ecx, [rsp+2B0h+CommandLineLength]
0x1800cb5a3  inc     ecx
0x1800cb5a5  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800cb5a9  jmp     short loc_1800CB5EF
0x1800cb5ab  mov     eax, 2
0x1800cb5b0  mul     rcx
0x1800cb5b3  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800cb5ba  cmovb   rax, r9
0x1800cb5be  xor     edx, edx; dwFlags
0x1800cb5c0  mov     r8, rax; dwBytes
0x1800cb5c3  call    cs:__imp_HeapAlloc
0x1800cb5c9  mov     rsi, rax
0x1800cb5cc  test    rax, rax
0x1800cb5cf  jz      short loc_1800CB605
0x1800cb5d1  lea     r8, [rsp+2B0h+CommandLineLength]; CommandLineLength
0x1800cb5d6  mov     rdx, rax; CommandLine
0x1800cb5d9  mov     rcx, r14; Descriptor
0x1800cb5dc  call    cs:__imp_CommandLineFromMsiDescriptor
0x1800cb5e2  mov     ecx, [rsp+2B0h+CommandLineLength]
0x1800cb5e6  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800cb5ed  inc     ecx
0x1800cb5ef  mov     [rsp+2B0h+CommandLineLength], ecx
0x1800cb5f3  mov     r8d, eax
0x1800cb5f6  cmp     eax, 0EAh
0x1800cb5fb  jz      short loc_1800CB5AB
0x1800cb5fd  test    eax, eax
0x1800cb5ff  jg      short loc_1800CB60F
0x1800cb601  mov     ebx, eax
0x1800cb603  jmp     short loc_1800CB619
0x1800cb605  mov     ebx, 8007000Eh
0x1800cb60a  jmp     loc_1800CB695
0x1800cb60f  movzx   ebx, r8w
0x1800cb613  or      ebx, 80070000h
0x1800cb619  mov     ecx, 80000000h
0x1800cb61e  lea     eax, [rbx+rcx]
0x1800cb621  test    ecx, eax
0x1800cb623  jnz     short loc_1800CB695
0x1800cb625  cmp     ebx, 8007000Eh
0x1800cb62b  jz      short loc_1800CB695
0x1800cb62d  mov     eax, cs:dword_18014E4B8
0x1800cb633  mov     ebx, 80004023h
0x1800cb638  test    eax, eax
0x1800cb63a  jnz     short loc_1800CB64F
0x1800cb63c  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800cb642  jz      short loc_1800CB695
0x1800cb644  xor     ecx, ecx
0x1800cb646  call    IsWppLevelEnabled
0x1800cb64b  test    al, al
0x1800cb64d  jz      short loc_1800CB695
0x1800cb64f  mov     [rsp+2B0h+var_268], r8d
0x1800cb654  lea     rax, [r13+70h]
0x1800cb658  mov     [rsp+2B0h+var_270], ebx
0x1800cb65c  lea     r8, aCcomclassinfoG_1; "CComClassInfo::GetPathFromDarwinDescrip"...
0x1800cb663  mov     [rsp+2B0h+var_278], r14
0x1800cb668  lea     rdx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x1800cb66f  mov     [rsp+2B0h+var_280], rax
0x1800cb674  mov     r9d, 15Dh
0x1800cb67a  lea     rax, aClsidWsDarwini_0; "CLSID:%ws DarwinID:%ws %!HRESULT! MSISt"...
0x1800cb681  mov     ecx, ebx
0x1800cb683  mov     [rsp+2B0h+var_288], rax
0x1800cb688  mov     dword ptr [rsp+2B0h+var_290], 0
0x1800cb690  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800cb695  test    r15d, r15d
0x1800cb698  jz      loc_1800CB733
0x1800cb69e  call    IsMsiSetInternalUIPresent
0x1800cb6a3  test    al, al
0x1800cb6a5  jz      loc_1800CB733
0x1800cb6ab  xor     ecx, ecx; dwErrCode
0x1800cb6ad  call    cs:__imp_SetLastError
0x1800cb6b3  xor     edx, edx; phWnd
0x1800cb6b5  mov     ecx, r12d; dwUILevel
0x1800cb6b8  call    cs:__imp_MsiSetInternalUI
0x1800cb6be  call    cs:__imp_GetLastError
0x1800cb6c4  mov     r9d, eax
0x1800cb6c7  test    eax, eax
0x1800cb6c9  jle     short loc_1800CB6D6
0x1800cb6cb  movzx   r9d, ax
0x1800cb6cf  or      r9d, 80070000h
0x1800cb6d6  test    r9d, r9d
0x1800cb6d9  jns     short loc_1800CB733
0x1800cb6db  mov     eax, cs:dword_18014E4B8
0x1800cb6e1  test    eax, eax
0x1800cb6e3  jnz     short loc_1800CB6F8
0x1800cb6e5  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800cb6eb  jz      short loc_1800CB733
0x1800cb6ed  xor     ecx, ecx
0x1800cb6ef  call    IsWppLevelEnabled
0x1800cb6f4  test    al, al
0x1800cb6f6  jz      short loc_1800CB733
0x1800cb6f8  mov     dword ptr [rsp+2B0h+var_278], r9d
0x1800cb6fd  lea     r8, [r13+70h]
0x1800cb701  mov     [rsp+2B0h+var_280], r14
0x1800cb706  lea     rax, aClsidWsDarwini; "CLSID:%ws DarwinID:%ws %!HRESULT!"
0x1800cb70d  mov     [rsp+2B0h+var_288], r8
0x1800cb712  lea     rdx, aCcomclassinfoG_1; "CComClassInfo::GetPathFromDarwinDescrip"...
0x1800cb719  mov     r8d, 16Bh
0x1800cb71f  mov     [rsp+2B0h+var_290], rax
0x1800cb724  xor     r9d, r9d
0x1800cb727  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x1800cb72e  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x1800cb733  test    ebx, ebx
0x1800cb735  jnz     short loc_1800CB794
0x1800cb737  mov     ecx, [rsp+2B0h+CommandLineLength]
0x1800cb73b  lea     eax, [rbx+2]
0x1800cb73e  mul     rcx
0x1800cb741  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800cb748  cmovb   rax, rcx
0x1800cb74c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800cb753  mov     r8, rax; dwBytes
0x1800cb756  xor     edx, edx; dwFlags
0x1800cb758  call    cs:__imp_HeapAlloc
0x1800cb75e  mov     [rdi], rax
0x1800cb761  test    rax, rax
0x1800cb764  jz      short loc_1800CB794
0x1800cb766  mov     edx, [rsp+2B0h+CommandLineLength]; unsigned __int64
0x1800cb76a  mov     r8, rsi; unsigned __int16 *
0x1800cb76d  mov     rcx, rax; unsigned __int16 *
0x1800cb770  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800cb775  mov     ebx, eax
0x1800cb777  test    eax, eax
0x1800cb779  jns     short loc_1800CB794
0x1800cb77b  mov     r8, [rdi]; lpMem
0x1800cb77e  xor     edx, edx; dwFlags
0x1800cb780  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800cb787  call    cs:__imp_HeapFree
0x1800cb78d  mov     qword ptr [rdi], 0
0x1800cb794  lea     rax, [rsp+2B0h+CommandLine]
0x1800cb799  cmp     rsi, rax
0x1800cb79c  jz      short loc_1800CB7B0
0x1800cb79e  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800cb7a5  mov     r8, rsi; lpMem
0x1800cb7a8  xor     edx, edx; dwFlags
0x1800cb7aa  call    cs:__imp_HeapFree
0x1800cb7b0  test    ebx, ebx
0x1800cb7b2  jz      short loc_1800CB7B8
0x1800cb7b4  mov     eax, ebx
0x1800cb7b6  jmp     short loc_1800CB7C7
0x1800cb7b8  mov     rax, [rdi]
0x1800cb7bb  neg     rax
0x1800cb7be  sbb     eax, eax
0x1800cb7c0  not     eax
0x1800cb7c2  and     eax, 8007000Eh
0x1800cb7c7  mov     rcx, [rbp+1B0h+var_40]
0x1800cb7ce  xor     rcx, rsp; StackCookie
0x1800cb7d1  call    __security_check_cookie
0x1800cb7d6  mov     rbx, [rsp+2B0h+arg_8]
0x1800cb7de  add     rsp, 280h
0x1800cb7e5  pop     r15
0x1800cb7e7  pop     r14
0x1800cb7e9  pop     r13
0x1800cb7eb  pop     r12
0x1800cb7ed  pop     rdi
0x1800cb7ee  pop     rsi
0x1800cb7ef  pop     rbp
0x1800cb7f0  retn
```

# CComClassInfo::GetPathFromDarwinDescriptor(int,ushort *,ushort * *)

- ea: `0x1800d15d4`
- end: `0x1800d198e`
- name: `?GetPathFromDarwinDescriptor@CComClassInfo@@AEAAJHPEAGPEAPEAG@Z`
- size: `954`
- prototype: `int(CComClassInfo *__hidden this, int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180064f44`
- `0x1800d1474`

## callees

- `0x180011db0`
- `0x18001c624`
- `0x180034260`
- `0x180081158`
- `0x1800b7ac0`
- `0x1800b8dcc`
- `0x1800b919c`
- `0x1800d15d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d1657`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d1825`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d1657`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d1825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1842`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d1917`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d1940`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d1917`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d1940`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d172f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d18e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d172f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d18e2`
- `ext-ms-win-advapi32-msi-l1-1-0!CommandLineFromMsiDescriptor` at `0x1800d16ff`
- `ext-ms-win-advapi32-msi-l1-1-0!CommandLineFromMsiDescriptor` at `0x1800d174e`
- `ext-ms-win-advapi32-msi-l1-1-0!CommandLineFromMsiDescriptor` at `0x1800d16ff`
- `ext-ms-win-advapi32-msi-l1-1-0!CommandLineFromMsiDescriptor` at `0x1800d174e`
- `ext-ms-win-msiltcfg-msi-l1-1-0!MsiSetInternalUI` at `0x1800d1668`
- `ext-ms-win-msiltcfg-msi-l1-1-0!MsiSetInternalUI` at `0x1800d1836`
- `ext-ms-win-msiltcfg-msi-l1-1-0!MsiSetInternalUI` at `0x1800d1668`
- `ext-ms-win-msiltcfg-msi-l1-1-0!MsiSetInternalUI` at `0x1800d1836`

## string_xrefs

- `0x1800d16d1`: `onecore\com\combase\catalog\class.cxx`
- `0x1800d17e0`: `onecore\com\combase\catalog\class.cxx`
- `0x1800d18b1`: `onecore\com\combase\catalog\class.cxx`
- `0x1800d16d8`: `CLSID:%ws DarwinID:%ws %!HRESULT!`
- `0x1800d1890`: `CLSID:%ws DarwinID:%ws %!HRESULT!`
- `0x1800d16c5`: `CComClassInfo::GetPathFromDarwinDescriptor`
- `0x1800d17d4`: `CComClassInfo::GetPathFromDarwinDescriptor`
- `0x1800d189c`: `CComClassInfo::GetPathFromDarwinDescriptor`
- `0x1800d17f2`: `CLSID:%ws DarwinID:%ws %!HRESULT! MSIStatus:%!WINERROR!`

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
  signed int v12; // r8d
  signed int v13; // eax
  unsigned __int64 i; // rcx
  SIZE_T v15; // rax
  WCHAR *v16; // rax
  signed int v17; // r8d
  signed int v18; // ebx
  signed int v19; // eax
  signed int v20; // r9d
  SIZE_T v21; // rax
  unsigned __int16 *v22; // rax
  __int64 v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD CommandLineLength[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR CommandLine[264]; // [rsp+60h] [rbp-A0h] BYREF

  CommandLineLength[0] = 0;
  if ( !(unsigned __int8)IsCommandLineFromMsiDescriptorPresent() )
    return 2147500033LL;
  *a4 = 0;
  v9 = INSTALLUILEVEL_NONE;
  CommandLineLength[0] = 260;
  v10 = CommandLine;
  if ( a2 && (unsigned __int8)IsMsiSetInternalUIPresent() )
  {
    SetLastError(0);
    v9 = MsiSetInternalUI(INSTALLUILEVEL_NONE, 0);
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 < 0 && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
      ComTraceMessageT<unsigned short *,unsigned short *,long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
        (unsigned int)"CComClassInfo::GetPathFromDarwinDescriptor",
        316,
        0,
        (__int64)L"CLSID:%ws DarwinID:%ws %!HRESULT!",
        (char *)this + 112,
        a3,
        v12);
  }
  v13 = CommandLineFromMsiDescriptor(a3, CommandLine, CommandLineLength);
  for ( i = CommandLineLength[0] + 1; ; i = CommandLineLength[0] + 1 )
  {
    CommandLineLength[0] = i;
    v17 = v13;
    if ( v13 != 234 )
      break;
    v15 = 2 * i;
    if ( !is_mul_ok(i, 2u) )
      v15 = -1;
    v16 = (WCHAR *)HeapAlloc(g_hHeap, 0, v15);
    v10 = v16;
    if ( !v16 )
    {
      v18 = -2147024882;
      goto LABEL_28;
    }
    v13 = CommandLineFromMsiDescriptor(a3, v16, CommandLineLength);
  }
  if ( v13 > 0 )
    v18 = (unsigned __int16)v13 | 0x80070000;
  else
    v18 = v13;
  if ( (int)(v18 + 0x80000000) >= 0 && v18 != -2147024882 )
  {
    v18 = -2147467229;
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      LODWORD(v23) = 0;
      ComTraceMessage(
        2147500067LL,
        "onecore\\com\\combase\\catalog\\class.cxx",
        "CComClassInfo::GetPathFromDarwinDescriptor",
        349,
        v23,
        L"CLSID:%ws DarwinID:%ws %!HRESULT! MSIStatus:%!WINERROR!",
        (char *)this + 112,
        a3,
        -2147467229,
        v17);
    }
  }
LABEL_28:
  if ( a2 && (unsigned __int8)IsMsiSetInternalUIPresent() )
  {
    SetLastError(0);
    MsiSetInternalUI(v9, 0);
    v19 = GetLastError();
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v20 < 0 && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
    {
      LODWORD(v24) = v20;
      ComTraceMessageT<unsigned short *,unsigned short *,long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
        (unsigned int)"CComClassInfo::GetPathFromDarwinDescriptor",
        363,
        0,
        (__int64)L"CLSID:%ws DarwinID:%ws %!HRESULT!",
        (char *)this + 112,
        a3,
        v24);
    }
  }
  if ( !v18 )
  {
    v21 = 2LL * CommandLineLength[0];
    if ( !is_mul_ok(CommandLineLength[0], 2u) )
      v21 = -1;
    v22 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v21);
    *a4 = v22;
    if ( v22 )
    {
      v18 = StringCchCopyW(v22, CommandLineLength[0], v10);
      if ( v18 < 0 )
      {
        HeapFree(g_hHeap, 0, *a4);
        *a4 = 0;
      }
    }
  }
  if ( v10 != CommandLine )
    HeapFree(g_hHeap, 0, v10);
  if ( v18 )
    return (unsigned int)v18;
  else
    return *a4 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1800d15d4  mov     [rsp-8+arg_8], rbx
0x1800d15d9  push    rbp
0x1800d15da  push    rsi
0x1800d15db  push    rdi
0x1800d15dc  push    r12
0x1800d15de  push    r13
0x1800d15e0  push    r14
0x1800d15e2  push    r15
0x1800d15e4  lea     rbp, [rsp-180h]
0x1800d15ec  sub     rsp, 280h
0x1800d15f3  mov     rax, cs:__security_cookie
0x1800d15fa  xor     rax, rsp
0x1800d15fd  mov     [rbp+1B0h+var_40], rax
0x1800d1604  xor     ebx, ebx
0x1800d1606  mov     rdi, r9
0x1800d1609  mov     [rsp+2B0h+CommandLineLength], ebx
0x1800d160d  mov     r14, r8
0x1800d1610  mov     r15d, edx
0x1800d1613  mov     r13, rcx
0x1800d1616  call    IsCommandLineFromMsiDescriptorPresent
0x1800d161b  test    al, al
0x1800d161d  jnz     short loc_1800D1629
0x1800d161f  mov     eax, 80004001h
0x1800d1624  jmp     loc_1800D1963
0x1800d1629  mov     [rdi], rbx
0x1800d162c  mov     r12d, 2
0x1800d1632  mov     [rsp+2B0h+CommandLineLength], 104h
0x1800d163a  lea     rsi, [rsp+2B0h+CommandLine]
0x1800d163f  test    r15d, r15d
0x1800d1642  jz      loc_1800D16F2
0x1800d1648  call    IsMsiSetInternalUIPresent
0x1800d164d  test    al, al
0x1800d164f  jz      loc_1800D16F2
0x1800d1655  xor     ecx, ecx; dwErrCode
0x1800d1657  call    cs:__imp_SetLastError
0x1800d165e  nop     dword ptr [rax+rax+00h]
0x1800d1663  xor     edx, edx; phWnd
0x1800d1665  mov     ecx, r12d; dwUILevel
0x1800d1668  call    cs:__imp_MsiSetInternalUI
0x1800d166f  nop     dword ptr [rax+rax+00h]
0x1800d1674  mov     r12d, eax
0x1800d1677  call    cs:__imp_GetLastError
0x1800d167e  nop     dword ptr [rax+rax+00h]
0x1800d1683  mov     r8d, eax
0x1800d1686  test    eax, eax
0x1800d1688  jle     short loc_1800D1695
0x1800d168a  movzx   r8d, ax
0x1800d168e  or      r8d, 80070000h
0x1800d1695  test    r8d, r8d
0x1800d1698  jns     short loc_1800D16F2
0x1800d169a  mov     eax, cs:dword_1801574B8
0x1800d16a0  test    eax, eax
0x1800d16a2  jnz     short loc_1800D16B7
0x1800d16a4  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800d16aa  jz      short loc_1800D16F2
0x1800d16ac  xor     ecx, ecx
0x1800d16ae  call    IsWppLevelEnabled
0x1800d16b3  test    al, al
0x1800d16b5  jz      short loc_1800D16F2
0x1800d16b7  mov     dword ptr [rsp+2B0h+var_278], r8d
0x1800d16bc  lea     rax, [r13+70h]
0x1800d16c0  mov     [rsp+2B0h+var_280], r14
0x1800d16c5  lea     rdx, aCcomclassinfoG_1; "CComClassInfo::GetPathFromDarwinDescrip"...
0x1800d16cc  mov     [rsp+2B0h+var_288], rax
0x1800d16d1  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x1800d16d8  lea     rax, aClsidWsDarwini; "CLSID:%ws DarwinID:%ws %!HRESULT!"
0x1800d16df  xor     r9d, r9d
0x1800d16e2  mov     r8d, 13Ch
0x1800d16e8  mov     [rsp+2B0h+var_290], rax
0x1800d16ed  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x1800d16f2  lea     r8, [rsp+2B0h+CommandLineLength]; CommandLineLength
0x1800d16f7  mov     rcx, r14; Descriptor
0x1800d16fa  lea     rdx, [rsp+2B0h+CommandLine]; CommandLine
0x1800d16ff  call    cs:__imp_CommandLineFromMsiDescriptor
0x1800d1706  nop     dword ptr [rax+rax+00h]
0x1800d170b  mov     ecx, [rsp+2B0h+CommandLineLength]
0x1800d170f  inc     ecx
0x1800d1711  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800d1715  jmp     short loc_1800D1767
0x1800d1717  mov     eax, 2
0x1800d171c  mul     rcx
0x1800d171f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d1726  cmovb   rax, r9
0x1800d172a  xor     edx, edx; dwFlags
0x1800d172c  mov     r8, rax; dwBytes
0x1800d172f  call    cs:__imp_HeapAlloc
0x1800d1736  nop     dword ptr [rax+rax+00h]
0x1800d173b  mov     rsi, rax
0x1800d173e  test    rax, rax
0x1800d1741  jz      short loc_1800D177D
0x1800d1743  lea     r8, [rsp+2B0h+CommandLineLength]; CommandLineLength
0x1800d1748  mov     rdx, rax; CommandLine
0x1800d174b  mov     rcx, r14; Descriptor
0x1800d174e  call    cs:__imp_CommandLineFromMsiDescriptor
0x1800d1755  nop     dword ptr [rax+rax+00h]
0x1800d175a  mov     ecx, [rsp+2B0h+CommandLineLength]
0x1800d175e  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800d1765  inc     ecx
0x1800d1767  mov     [rsp+2B0h+CommandLineLength], ecx
0x1800d176b  mov     r8d, eax
0x1800d176e  cmp     eax, 0EAh
0x1800d1773  jz      short loc_1800D1717
0x1800d1775  test    eax, eax
0x1800d1777  jg      short loc_1800D1787
0x1800d1779  mov     ebx, eax
0x1800d177b  jmp     short loc_1800D1791
0x1800d177d  mov     ebx, 8007000Eh
0x1800d1782  jmp     loc_1800D180D
0x1800d1787  movzx   ebx, r8w
0x1800d178b  or      ebx, 80070000h
0x1800d1791  mov     ecx, 80000000h
0x1800d1796  lea     eax, [rbx+rcx]
0x1800d1799  test    ecx, eax
0x1800d179b  jnz     short loc_1800D180D
0x1800d179d  cmp     ebx, 8007000Eh
0x1800d17a3  jz      short loc_1800D180D
0x1800d17a5  mov     eax, cs:dword_1801574B8
0x1800d17ab  mov     ebx, 80004023h
0x1800d17b0  test    eax, eax
0x1800d17b2  jnz     short loc_1800D17C7
0x1800d17b4  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800d17ba  jz      short loc_1800D180D
0x1800d17bc  xor     ecx, ecx
0x1800d17be  call    IsWppLevelEnabled
0x1800d17c3  test    al, al
0x1800d17c5  jz      short loc_1800D180D
0x1800d17c7  mov     [rsp+2B0h+var_268], r8d
0x1800d17cc  lea     rax, [r13+70h]
0x1800d17d0  mov     [rsp+2B0h+var_270], ebx
0x1800d17d4  lea     r8, aCcomclassinfoG_1; "CComClassInfo::GetPathFromDarwinDescrip"...
0x1800d17db  mov     [rsp+2B0h+var_278], r14
0x1800d17e0  lea     rdx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x1800d17e7  mov     [rsp+2B0h+var_280], rax
0x1800d17ec  mov     r9d, 15Dh
0x1800d17f2  lea     rax, aClsidWsDarwini_0; "CLSID:%ws DarwinID:%ws %!HRESULT! MSISt"...
0x1800d17f9  mov     ecx, ebx
0x1800d17fb  mov     [rsp+2B0h+var_288], rax
0x1800d1800  mov     dword ptr [rsp+2B0h+var_290], 0
0x1800d1808  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800d180d  test    r15d, r15d
0x1800d1810  jz      loc_1800D18BD
0x1800d1816  call    IsMsiSetInternalUIPresent
0x1800d181b  test    al, al
0x1800d181d  jz      loc_1800D18BD
0x1800d1823  xor     ecx, ecx; dwErrCode
0x1800d1825  call    cs:__imp_SetLastError
0x1800d182c  nop     dword ptr [rax+rax+00h]
0x1800d1831  xor     edx, edx; phWnd
0x1800d1833  mov     ecx, r12d; dwUILevel
0x1800d1836  call    cs:__imp_MsiSetInternalUI
0x1800d183d  nop     dword ptr [rax+rax+00h]
0x1800d1842  call    cs:__imp_GetLastError
0x1800d1849  nop     dword ptr [rax+rax+00h]
0x1800d184e  mov     r9d, eax
0x1800d1851  test    eax, eax
0x1800d1853  jle     short loc_1800D1860
0x1800d1855  movzx   r9d, ax
0x1800d1859  or      r9d, 80070000h
0x1800d1860  test    r9d, r9d
0x1800d1863  jns     short loc_1800D18BD
0x1800d1865  mov     eax, cs:dword_1801574B8
0x1800d186b  test    eax, eax
0x1800d186d  jnz     short loc_1800D1882
0x1800d186f  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800d1875  jz      short loc_1800D18BD
0x1800d1877  xor     ecx, ecx
0x1800d1879  call    IsWppLevelEnabled
0x1800d187e  test    al, al
0x1800d1880  jz      short loc_1800D18BD
0x1800d1882  mov     dword ptr [rsp+2B0h+var_278], r9d
0x1800d1887  lea     r8, [r13+70h]
0x1800d188b  mov     [rsp+2B0h+var_280], r14
0x1800d1890  lea     rax, aClsidWsDarwini; "CLSID:%ws DarwinID:%ws %!HRESULT!"
0x1800d1897  mov     [rsp+2B0h+var_288], r8
0x1800d189c  lea     rdx, aCcomclassinfoG_1; "CComClassInfo::GetPathFromDarwinDescrip"...
0x1800d18a3  mov     r8d, 16Bh
0x1800d18a9  mov     [rsp+2B0h+var_290], rax
0x1800d18ae  xor     r9d, r9d
0x1800d18b1  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x1800d18b8  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x1800d18bd  test    ebx, ebx
0x1800d18bf  jnz     short loc_1800D192A
0x1800d18c1  mov     ecx, [rsp+2B0h+CommandLineLength]
0x1800d18c5  lea     eax, [rbx+2]
0x1800d18c8  mul     rcx
0x1800d18cb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d18d2  cmovb   rax, rcx
0x1800d18d6  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d18dd  mov     r8, rax; dwBytes
0x1800d18e0  xor     edx, edx; dwFlags
0x1800d18e2  call    cs:__imp_HeapAlloc
0x1800d18e9  nop     dword ptr [rax+rax+00h]
0x1800d18ee  mov     [rdi], rax
0x1800d18f1  test    rax, rax
0x1800d18f4  jz      short loc_1800D192A
0x1800d18f6  mov     edx, [rsp+2B0h+CommandLineLength]; unsigned __int64
0x1800d18fa  mov     r8, rsi; unsigned __int16 *
0x1800d18fd  mov     rcx, rax; unsigned __int16 *
0x1800d1900  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d1905  mov     ebx, eax
0x1800d1907  test    eax, eax
0x1800d1909  jns     short loc_1800D192A
0x1800d190b  mov     r8, [rdi]; lpMem
0x1800d190e  xor     edx, edx; dwFlags
0x1800d1910  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d1917  call    cs:__imp_HeapFree
0x1800d191e  nop     dword ptr [rax+rax+00h]
0x1800d1923  mov     qword ptr [rdi], 0
0x1800d192a  lea     rax, [rsp+2B0h+CommandLine]
0x1800d192f  cmp     rsi, rax
0x1800d1932  jz      short loc_1800D194C
0x1800d1934  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800d193b  mov     r8, rsi; lpMem
0x1800d193e  xor     edx, edx; dwFlags
0x1800d1940  call    cs:__imp_HeapFree
0x1800d1947  nop     dword ptr [rax+rax+00h]
0x1800d194c  test    ebx, ebx
0x1800d194e  jz      short loc_1800D1954
0x1800d1950  mov     eax, ebx
0x1800d1952  jmp     short loc_1800D1963
0x1800d1954  mov     rax, [rdi]
0x1800d1957  neg     rax
0x1800d195a  sbb     eax, eax
0x1800d195c  not     eax
0x1800d195e  and     eax, 8007000Eh
0x1800d1963  mov     rcx, [rbp+1B0h+var_40]
0x1800d196a  xor     rcx, rsp; StackCookie
0x1800d196d  call    __security_check_cookie
0x1800d1972  mov     rbx, [rsp+2B0h+arg_8]
0x1800d197a  add     rsp, 280h
0x1800d1981  pop     r15
0x1800d1983  pop     r14
0x1800d1985  pop     r13
0x1800d1987  pop     r12
0x1800d1989  pop     rdi
0x1800d198a  pop     rsi
0x1800d198b  pop     rbp
0x1800d198c  retn
```

# BlbCopyMetadataFilesMatchingPattern(ushort const *,ushort const *,ushort const *,CBlbImpersonationHelper *,uchar)

- ea: `0x1400f16ac`
- end: `0x1400f1a3e`
- name: `?BlbCopyMetadataFilesMatchingPattern@@YAJPEBG00PEAVCBlbImpersonationHelper@@E@Z`
- size: `914`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, struct CBlbImpersonationHelper *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task`

## callers

- `0x140076c6c`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x140014448`
- `0x14008d84c`
- `0x14008e440`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f16ac`
- `0x1400f1a44`
- `0x1400f2a28`
- `0x1400f2d74`

## import_xrefs

- `KERNEL32!FindClose` at `0x1400f19a1`
- `KERNEL32!FindClose` at `0x1400f19a1`
- `ole32!CoTaskMemFree` at `0x1400f18df`
- `ole32!CoTaskMemFree` at `0x1400f18f5`
- `ole32!CoTaskMemFree` at `0x1400f190e`
- `ole32!CoTaskMemFree` at `0x1400f1922`
- `ole32!CoTaskMemFree` at `0x1400f19af`
- `ole32!CoTaskMemFree` at `0x1400f19bd`
- `ole32!CoTaskMemFree` at `0x1400f19cb`
- `ole32!CoTaskMemFree` at `0x1400f19d9`
- `ole32!CoTaskMemFree` at `0x1400f19ea`
- `ole32!CoTaskMemFree` at `0x1400f18df`
- `ole32!CoTaskMemFree` at `0x1400f18f5`
- `ole32!CoTaskMemFree` at `0x1400f190e`
- `ole32!CoTaskMemFree` at `0x1400f1922`
- `ole32!CoTaskMemFree` at `0x1400f19af`
- `ole32!CoTaskMemFree` at `0x1400f19bd`
- `ole32!CoTaskMemFree` at `0x1400f19cb`
- `ole32!CoTaskMemFree` at `0x1400f19d9`
- `ole32!CoTaskMemFree` at `0x1400f19ea`

## string_xrefs

- `0x1400f171b`: `wszSrcPath`
- `0x1400f173b`: `wszDstPath`

## pseudocode

```c
__int64 __fastcall BlbCopyMetadataFilesMatchingPattern(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct CBlbImpersonationHelper *this)
{
  PVOID *v8; // rcx
  unsigned __int16 *v9; // r15
  unsigned __int16 *v10; // rsi
  unsigned __int16 *v11; // r14
  int Path; // edi
  HANDLE v13; // r13
  unsigned __int16 *v14; // rbx
  int v15; // eax
  int v16; // eax
  unsigned __int16 *v18; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v20; // [rsp+40h] [rbp-10h] BYREF
  HANDLE hFindFile; // [rsp+48h] [rbp-8h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int16 *v23; // [rsp+98h] [rbp+48h]
  unsigned __int16 *v24; // [rsp+A0h] [rbp+50h] BYREF

  v23 = a2;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbfsutils.cpp", 0x9C3u, "wszSrcPath");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbfsutils.cpp", 0x9C4u, "wszDstPath");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbfsutils.cpp", 0x9C5u, "wszFilePattern");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = 0;
  pv = 0;
  v10 = 0;
  v19 = 0;
  v11 = 0;
  v18 = 0;
  v20 = 0;
  v24 = 0;
  hFindFile = (HANDLE)-1LL;
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_SSS((TRACEHANDLE)v8[2], (__int64)a2, (__int64)a3);
  Path = BlbutilGetPath(a1, a3, &v18);
  if ( Path >= 0 )
  {
    if ( !this || (Path = CBlbImpersonationHelper::ImpersonateCaller(this, 0), Path >= 0) )
    {
      Path = BlbFindFirstFile(v18, &pv, &hFindFile, 0);
      if ( this )
        CBlbImpersonationHelper::Revert(this);
      v13 = hFindFile;
      if ( Path >= 0 )
      {
        while ( 1 )
        {
          v14 = (unsigned __int16 *)pv;
          if ( !pv )
            break;
          v15 = BlbutilSplitFilePath((unsigned __int16 *)pv, &v24, &v20);
          v11 = v20;
          Path = v15;
          if ( v15 < 0
            || (v16 = BlbutilGetPath(v23, v20, &v19), v9 = v19, Path = v16, v16 < 0)
            || (Path = BlbCopySmallFile(v14, v19, this, 1u), Path < 0) )
          {
            v10 = v24;
            break;
          }
          CoTaskMemFree(v14);
          pv = 0;
          if ( v9 )
          {
            CoTaskMemFree(v9);
            v9 = 0;
            v19 = 0;
          }
          v10 = v24;
          if ( v24 )
          {
            CoTaskMemFree(v24);
            v10 = 0;
            v24 = 0;
          }
          if ( v11 )
          {
            CoTaskMemFree(v11);
            v11 = 0;
            v20 = 0;
          }
          Path = BlbFindNextFile(v18, v13, &pv, 0);
          if ( Path < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids);
            }
            goto LABEL_25;
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
            (_DWORD)v18,
            Path);
        }
LABEL_25:
        v14 = (unsigned __int16 *)pv;
      }
      if ( v13 != (HANDLE)-1LL )
        FindClose(v13);
      if ( v14 )
        CoTaskMemFree(v14);
      if ( v9 )
        CoTaskMemFree(v9);
      if ( v10 )
        CoTaskMemFree(v10);
      if ( v11 )
        CoTaskMemFree(v11);
    }
  }
  if ( v18 )
    CoTaskMemFree(v18);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids);
  }
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x1400f16ac  mov     [rsp-38h+arg_18], rbx
0x1400f16b1  mov     [rsp-38h+arg_8], rdx
0x1400f16b6  push    rbp
0x1400f16b7  push    rsi
0x1400f16b8  push    rdi
0x1400f16b9  push    r12
0x1400f16bb  push    r13
0x1400f16bd  push    r14
0x1400f16bf  push    r15
0x1400f16c1  mov     rbp, rsp
0x1400f16c4  sub     rsp, 50h
0x1400f16c8  mov     r12, r9
0x1400f16cb  mov     rbx, r8
0x1400f16ce  mov     r13, rdx
0x1400f16d1  mov     rdi, rcx
0x1400f16d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f16db  lea     rax, WPP_GLOBAL_Control
0x1400f16e2  cmp     rcx, rax
0x1400f16e5  jz      short loc_1400F170F
0x1400f16e7  test    byte ptr [rcx+1Ch], 1
0x1400f16eb  jz      short loc_1400F170F
0x1400f16ed  cmp     byte ptr [rcx+19h], 4
0x1400f16f1  jb      short loc_1400F170F
0x1400f16f3  mov     rcx, [rcx+10h]
0x1400f16f7  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f16fe  mov     edx, 68h ; 'h'
0x1400f1703  call    WPP_SF_
0x1400f1708  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f170f  lea     rsi, aBaseStorBlbEng; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400f1716  test    rdi, rdi
0x1400f1719  jnz     short loc_1400F1736
0x1400f171b  lea     r8, aWszsrcpath; "wszSrcPath"
0x1400f1722  mov     edx, 9C3h; unsigned int
0x1400f1727  mov     rcx, rsi; char *
0x1400f172a  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f172f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f1736  test    r13, r13
0x1400f1739  jnz     short loc_1400F1756
0x1400f173b  lea     r8, aWszdstpath; "wszDstPath"
0x1400f1742  mov     edx, 9C4h; unsigned int
0x1400f1747  mov     rcx, rsi; char *
0x1400f174a  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f174f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f1756  test    rbx, rbx
0x1400f1759  jnz     short loc_1400F1776
0x1400f175b  lea     r8, aWszfilepattern; "wszFilePattern"
0x1400f1762  mov     edx, 9C5h; unsigned int
0x1400f1767  mov     rcx, rsi; char *
0x1400f176a  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f176f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f1776  xor     r15d, r15d
0x1400f1779  mov     [rbp+pv], 0
0x1400f1781  xor     esi, esi
0x1400f1783  mov     [rbp+var_18], r15
0x1400f1787  xor     r14d, r14d
0x1400f178a  mov     [rbp+var_20], r15
0x1400f178e  mov     [rbp+var_10], r14
0x1400f1792  mov     [rbp+arg_10], rsi
0x1400f1796  mov     [rbp+hFindFile], 0FFFFFFFFFFFFFFFFh
0x1400f179e  lea     rax, WPP_GLOBAL_Control
0x1400f17a5  cmp     rcx, rax
0x1400f17a8  jz      short loc_1400F17D6
0x1400f17aa  test    byte ptr [rcx+1Ch], 1
0x1400f17ae  jz      short loc_1400F17D6
0x1400f17b0  cmp     byte ptr [rcx+19h], 5
0x1400f17b4  jb      short loc_1400F17D6
0x1400f17b6  mov     rcx, [rcx+10h]; LoggerHandle
0x1400f17ba  lea     edx, [rsi+69h]
0x1400f17bd  mov     [rsp+50h+var_28], rbx; __int64
0x1400f17c2  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f17c9  mov     r9, rdi
0x1400f17cc  mov     [rsp+50h+var_30], r13; __int64
0x1400f17d1  call    WPP_SF_SSS
0x1400f17d6  lea     r8, [rbp+var_20]; unsigned __int16 **
0x1400f17da  mov     rdx, rbx; unsigned __int16 *
0x1400f17dd  mov     rcx, rdi; unsigned __int16 *
0x1400f17e0  call    ?BlbutilGetPath@@YAJPEBG0PEAPEAG@Z; BlbutilGetPath(ushort const *,ushort const *,ushort * *)
0x1400f17e5  mov     edi, eax
0x1400f17e7  test    eax, eax
0x1400f17e9  js      loc_1400F19DF
0x1400f17ef  test    r12, r12
0x1400f17f2  jz      short loc_1400F1808
0x1400f17f4  xor     edx, edx; unsigned __int8
0x1400f17f6  mov     rcx, r12; this
0x1400f17f9  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x1400f17fe  mov     edi, eax
0x1400f1800  test    eax, eax
0x1400f1802  js      loc_1400F19DF
0x1400f1808  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x1400f180c  lea     r8, [rbp+hFindFile]; void **
0x1400f1810  xor     r9d, r9d; struct _WIN32_FIND_DATAW **
0x1400f1813  lea     rdx, [rbp+pv]; unsigned __int16 **
0x1400f1817  call    ?BlbFindFirstFile@@YAJPEAGPEAPEAGPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindFirstFile(ushort *,ushort * *,void * *,_WIN32_FIND_DATAW * *)
0x1400f181c  mov     edi, eax
0x1400f181e  test    r12, r12
0x1400f1821  jz      short loc_1400F182B
0x1400f1823  mov     rcx, r12; this
0x1400f1826  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x1400f182b  mov     r13, [rbp+hFindFile]
0x1400f182f  test    edi, edi
0x1400f1831  jns     short loc_1400F1878
0x1400f1833  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f183a  lea     rax, WPP_GLOBAL_Control
0x1400f1841  cmp     rcx, rax
0x1400f1844  jz      short loc_1400F186F
0x1400f1846  test    byte ptr [rcx+1Ch], 1
0x1400f184a  jz      short loc_1400F186F
0x1400f184c  cmp     byte ptr [rcx+19h], 2
0x1400f1850  jb      short loc_1400F186F
0x1400f1852  mov     r9, [rbp+var_20]
0x1400f1856  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f185d  mov     rcx, [rcx+10h]
0x1400f1861  mov     edx, 6Ah ; 'j'
0x1400f1866  mov     dword ptr [rsp+50h+var_30], edi
0x1400f186a  call    WPP_SF_Sd
0x1400f186f  mov     rbx, [rbp+pv]
0x1400f1873  jmp     loc_1400F1998
0x1400f1878  mov     rbx, [rbp+pv]
0x1400f187c  test    rbx, rbx
0x1400f187f  jz      loc_1400F1998
0x1400f1885  lea     r8, [rbp+var_10]; unsigned __int16 **
0x1400f1889  mov     rcx, rbx; unsigned __int16 *
0x1400f188c  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x1400f1890  call    ?BlbutilSplitFilePath@@YAJPEAGPEAPEAG1@Z; BlbutilSplitFilePath(ushort *,ushort * *,ushort * *)
0x1400f1895  mov     r14, [rbp+var_10]
0x1400f1899  mov     edi, eax
0x1400f189b  test    eax, eax
0x1400f189d  js      loc_1400F1994
0x1400f18a3  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x1400f18a7  lea     r8, [rbp+var_18]; unsigned __int16 **
0x1400f18ab  mov     rdx, r14; unsigned __int16 *
0x1400f18ae  call    ?BlbutilGetPath@@YAJPEBG0PEAPEAG@Z; BlbutilGetPath(ushort const *,ushort const *,ushort * *)
0x1400f18b3  mov     r15, [rbp+var_18]
0x1400f18b7  mov     edi, eax
0x1400f18b9  test    eax, eax
0x1400f18bb  js      loc_1400F1994
0x1400f18c1  mov     r9b, 1; unsigned __int8
0x1400f18c4  mov     r8, r12; this
0x1400f18c7  mov     rdx, r15; unsigned __int16 *
0x1400f18ca  mov     rcx, rbx; unsigned __int16 *
0x1400f18cd  call    ?BlbCopySmallFile@@YAJPEBG0PEAVCBlbImpersonationHelper@@E@Z; BlbCopySmallFile(ushort const *,ushort const *,CBlbImpersonationHelper *,uchar)
0x1400f18d2  mov     edi, eax
0x1400f18d4  test    eax, eax
0x1400f18d6  js      loc_1400F1994
0x1400f18dc  mov     rcx, rbx; pv
0x1400f18df  call    cs:__imp_CoTaskMemFree
0x1400f18e5  mov     [rbp+pv], 0
0x1400f18ed  test    r15, r15
0x1400f18f0  jz      short loc_1400F1902
0x1400f18f2  mov     rcx, r15; pv
0x1400f18f5  call    cs:__imp_CoTaskMemFree
0x1400f18fb  xor     r15d, r15d
0x1400f18fe  mov     [rbp+var_18], r15
0x1400f1902  mov     rsi, [rbp+arg_10]
0x1400f1906  test    rsi, rsi
0x1400f1909  jz      short loc_1400F191A
0x1400f190b  mov     rcx, rsi; pv
0x1400f190e  call    cs:__imp_CoTaskMemFree
0x1400f1914  xor     esi, esi
0x1400f1916  mov     [rbp+arg_10], rsi
0x1400f191a  test    r14, r14
0x1400f191d  jz      short loc_1400F192F
0x1400f191f  mov     rcx, r14; pv
0x1400f1922  call    cs:__imp_CoTaskMemFree
0x1400f1928  xor     r14d, r14d
0x1400f192b  mov     [rbp+var_10], r14
0x1400f192f  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x1400f1933  lea     r8, [rbp+pv]; unsigned __int16 **
0x1400f1937  xor     r9d, r9d; struct _WIN32_FIND_DATAW **
0x1400f193a  mov     rdx, r13; hFindFile
0x1400f193d  call    ?BlbFindNextFile@@YAJPEAGPEAXPEAPEAGPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindNextFile(ushort *,void *,ushort * *,_WIN32_FIND_DATAW * *)
0x1400f1942  mov     edi, eax
0x1400f1944  test    eax, eax
0x1400f1946  jns     loc_1400F1878
0x1400f194c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f1953  lea     rax, WPP_GLOBAL_Control
0x1400f195a  cmp     rcx, rax
0x1400f195d  jz      loc_1400F186F
0x1400f1963  test    byte ptr [rcx+1Ch], 1
0x1400f1967  jz      loc_1400F186F
0x1400f196d  cmp     byte ptr [rcx+19h], 2
0x1400f1971  jb      loc_1400F186F
0x1400f1977  mov     rcx, [rcx+10h]
0x1400f197b  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f1982  mov     edx, 6Bh ; 'k'
0x1400f1987  mov     r9d, edi
0x1400f198a  call    WPP_SF_d
0x1400f198f  jmp     loc_1400F186F
0x1400f1994  mov     rsi, [rbp+arg_10]
0x1400f1998  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1400f199c  jz      short loc_1400F19A7
0x1400f199e  mov     rcx, r13; hFindFile
0x1400f19a1  call    cs:__imp_FindClose
0x1400f19a7  test    rbx, rbx
0x1400f19aa  jz      short loc_1400F19B5
0x1400f19ac  mov     rcx, rbx; pv
0x1400f19af  call    cs:__imp_CoTaskMemFree
0x1400f19b5  test    r15, r15
0x1400f19b8  jz      short loc_1400F19C3
0x1400f19ba  mov     rcx, r15; pv
0x1400f19bd  call    cs:__imp_CoTaskMemFree
0x1400f19c3  test    rsi, rsi
0x1400f19c6  jz      short loc_1400F19D1
0x1400f19c8  mov     rcx, rsi; pv
0x1400f19cb  call    cs:__imp_CoTaskMemFree
0x1400f19d1  test    r14, r14
0x1400f19d4  jz      short loc_1400F19DF
0x1400f19d6  mov     rcx, r14; pv
0x1400f19d9  call    cs:__imp_CoTaskMemFree
0x1400f19df  cmp     [rbp+var_20], 0
0x1400f19e4  jz      short loc_1400F19F0
0x1400f19e6  mov     rcx, [rbp+var_20]; pv
0x1400f19ea  call    cs:__imp_CoTaskMemFree
0x1400f19f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f19f7  lea     rax, WPP_GLOBAL_Control
0x1400f19fe  cmp     rcx, rax
0x1400f1a01  jz      short loc_1400F1A24
0x1400f1a03  test    byte ptr [rcx+1Ch], 1
0x1400f1a07  jz      short loc_1400F1A24
0x1400f1a09  cmp     byte ptr [rcx+19h], 4
0x1400f1a0d  jb      short loc_1400F1A24
0x1400f1a0f  mov     rcx, [rcx+10h]
0x1400f1a13  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f1a1a  mov     edx, 6Ch ; 'l'
0x1400f1a1f  call    WPP_SF_
0x1400f1a24  mov     rbx, [rsp+50h+arg_18]
0x1400f1a2c  mov     eax, edi
0x1400f1a2e  add     rsp, 50h
0x1400f1a32  pop     r15
0x1400f1a34  pop     r14
0x1400f1a36  pop     r13
0x1400f1a38  pop     r12
0x1400f1a3a  pop     rdi
0x1400f1a3b  pop     rsi
0x1400f1a3c  pop     rbp
0x1400f1a3d  retn
```

# SrmGetCanonicalPath(ushort const *,CSrmAutoPWSZ &,ushort * *)

- ea: `0x18007cfe0`
- end: `0x18007d233`
- name: `?SrmGetCanonicalPath@@YAJPEBGAEAVCSrmAutoPWSZ@@PEAPEAG@Z`
- size: `595`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CSrmAutoPWSZ *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a3e34`

## callees

- `0x180006a1c`
- `0x18000ad14`
- `0x18000af40`
- `0x180017fd8`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074a04`
- `0x18007cfe0`
- `0x18007f760`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007d163`
- `ole32!CoTaskMemFree` at `0x18007d178`
- `ole32!CoTaskMemFree` at `0x18007d163`
- `ole32!CoTaskMemFree` at `0x18007d178`

## string_xrefs

- `0x18007d01c`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007d038`: `SRMPATHC`
- `0x18007d202`: `SRMPATHC`
- `0x18007d02a`: `SrmGetCanonicalPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SrmGetCanonicalPath(const unsigned __int16 *a1, struct CSrmAutoPWSZ *a2, unsigned __int16 **a3)
{
  __int64 v6; // rcx
  unsigned __int16 *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rax
  unsigned int v12; // ebx
  unsigned int Hr; // ebx
  __int64 v15; // rax
  unsigned __int16 *v16; // [rsp+40h] [rbp-248h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-240h] BYREF
  unsigned __int16 *v18; // [rsp+50h] [rbp-238h] BYREF
  int v19; // [rsp+58h] [rbp-230h] BYREF
  _com_error *v20; // [rsp+60h] [rbp-228h] BYREF
  const exception *v21; // [rsp+68h] [rbp-220h] BYREF
  _BYTE v22[144]; // [rsp+70h] [rbp-218h] BYREF
  void **v23; // [rsp+100h] [rbp-188h] BYREF
  int v24; // [rsp+108h] [rbp-180h]
  unsigned int v25; // [rsp+12Ch] [rbp-15Ch]
  WCHAR szVolumeName[4]; // [rsp+1B0h] [rbp-D8h] BYREF
  const unsigned __int16 *v27; // [rsp+1B8h] [rbp-D0h]
  const unsigned __int16 *v28; // [rsp+1C0h] [rbp-C8h]
  __int64 v29; // [rsp+1C8h] [rbp-C0h]
  int v30; // [rsp+1D0h] [rbp-B8h]
  _DWORD v31[26]; // [rsp+1D8h] [rbp-B0h] BYREF

  v18 = szVolumeName;
  *(_QWORD *)szVolumeName = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v27 = L"SrmGetCanonicalPath";
  v28 = L"SRMPATHC";
  v29 = 783;
  v30 = 255;
  v31[24] = 0x1000000;
  memset_0(v31, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v23, (const struct CSrmDebugInfo *)szVolumeName, 0);
  try
  {
    v18 = 0;
    SrmGetVolumeNameForPathName(a1, szVolumeName, 0x32u, 1, &v18);
    v16 = 0;
    v8 = -1;
    v6 = -1;
    do
      ++v6;
    while ( szVolumeName[v6] );
    v7 = v18;
    do
      ++v8;
    while ( v18[v8] );
    v9 = v6 + v8;
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&v16, v6 + v8);
    v24 = StringCchPrintfW(v16, v9 + 1, L"%s%s", szVolumeName, v7);
    if ( v24 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v23);
      v18 = (unsigned __int16 *)v22;
      v15 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v22,
              (__int64)L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
              (__int64)L"SRMPATHC",
              (__int64)L"SrmGetCanonicalPath",
              812,
              17);
      CSrmFunctionTracer::TranslateGenericError(&v23, v15, Hr, L"StringCchPrintf failed");
    }
    v10 = v16;
    v16 = 0;
    *(_QWORD *)a2 = v10;
    if ( a3 )
    {
      pv = 0;
      CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&pv, szVolumeName);
      v11 = (unsigned __int16 *)pv;
      pv = 0;
      *a3 = v11;
      CoTaskMemFree(pv);
      pv = 0;
    }
    CoTaskMemFree(v16);
    v16 = 0;
  }
  catch ( long v19 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v23,
      v19,
      L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
      L"SRMPATHC",
      L"SrmGetCanonicalPath",
      0x338u,
      v25);
  }
  catch ( _com_error *v20 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v23,
      v20,
      L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
      L"SRMPATHC",
      L"SrmGetCanonicalPath",
      0x338u,
      v25);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v23,
      L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
      L"SRMPATHC",
      L"SrmGetCanonicalPath",
      0x338u,
      v25);
  }
  catch ( const exception *v21 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v23,
      v21,
      L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
      L"SRMPATHC",
      L"SrmGetCanonicalPath",
      0x338u,
      v25);
  }
  v12 = v24;
  v23 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v23);
  return v12;
}

```

## disassembly

```asm
0x18007cfe0  mov     r11, rsp
0x18007cfe3  push    rbx
0x18007cfe4  push    rsi
0x18007cfe5  push    rdi
0x18007cfe6  push    r12
0x18007cfe8  push    r13
0x18007cfea  push    r14
0x18007cfec  push    r15
0x18007cfee  sub     rsp, 250h
0x18007cff5  mov     rax, cs:__security_cookie
0x18007cffc  xor     rax, rsp
0x18007cfff  mov     [rsp+288h+var_48], rax
0x18007d007  mov     rsi, r8
0x18007d00a  mov     r14, rdx
0x18007d00d  mov     rbx, rcx
0x18007d010  lea     rax, [r11-0D8h]
0x18007d017  mov     [rsp+288h+var_238], rax
0x18007d01c  lea     r12, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007d023  mov     [r11-0D8h], r12
0x18007d02a  lea     r13, aSrmgetcanonica; "SrmGetCanonicalPath"
0x18007d031  mov     [r11-0D0h], r13
0x18007d038  lea     rax, aSrmpathc; "SRMPATHC"
0x18007d03f  mov     [r11-0C8h], rax
0x18007d046  mov     qword ptr [r11-0C0h], 30Fh
0x18007d051  xor     r15d, r15d
0x18007d054  mov     [rsp+288h+var_B8], 0FFh
0x18007d05f  mov     dword ptr [r11-50h], 1000000h
0x18007d067  xor     edx, edx; Val
0x18007d069  lea     r8d, [r15+60h]; Size
0x18007d06d  lea     rcx, [r11-0B0h]; void *
0x18007d074  call    memset_0
0x18007d079  nop
0x18007d07a  xor     r8d, r8d
0x18007d07d  lea     rdx, [rsp+288h+szVolumeName]
0x18007d085  lea     rcx, [rsp+288h+var_188]
0x18007d08d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007d092  nop
0x18007d093  mov     [rsp+288h+var_238], r15
0x18007d098  lea     rax, [rsp+288h+var_238]
0x18007d09d  mov     [rsp+288h+var_268], rax; unsigned __int16 **
0x18007d0a2  mov     r9b, 1; bool
0x18007d0a5  lea     r8d, [r15+32h]; unsigned int
0x18007d0a9  lea     rdx, [rsp+288h+szVolumeName]; lpszVolumeName
0x18007d0b1  mov     rcx, rbx; lpszFileName
0x18007d0b4  call    ?SrmGetVolumeNameForPathName@@YAXPEBGPEAGK_NPEAPEAG@Z; SrmGetVolumeNameForPathName(ushort const *,ushort *,ulong,bool,ushort * *)
0x18007d0b9  mov     [rsp+288h+var_248], r15
0x18007d0be  lea     rdx, [rsp+288h+szVolumeName]
0x18007d0c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007d0ca  mov     rcx, rax
0x18007d0cd  inc     rcx
0x18007d0d0  cmp     [rdx+rcx*2], r15w
0x18007d0d5  jnz     short loc_18007D0CD
0x18007d0d7  mov     rdi, [rsp+288h+var_238]
0x18007d0dc  inc     rax
0x18007d0df  cmp     [rdi+rax*2], r15w
0x18007d0e4  jnz     short loc_18007D0DC
0x18007d0e6  lea     rbx, [rcx+rax]
0x18007d0ea  mov     rdx, rbx; unsigned __int64
0x18007d0ed  lea     rcx, [rsp+288h+var_248]; this
0x18007d0f2  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007d0f7  lea     rdx, [rbx+1]; unsigned __int64
0x18007d0fb  mov     [rsp+288h+var_268], rdi
0x18007d100  lea     r9, [rsp+288h+szVolumeName]
0x18007d108  lea     r8, aSS_0; "%s%s"
0x18007d10f  mov     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18007d114  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007d119  mov     [rsp+288h+var_180], eax
0x18007d120  test    eax, eax
0x18007d122  js      loc_18007D1D6
0x18007d128  mov     rax, [rsp+288h+var_248]
0x18007d12d  mov     [rsp+288h+var_248], r15
0x18007d132  mov     [r14], rax
0x18007d135  test    rsi, rsi
0x18007d138  jz      short loc_18007D173
0x18007d13a  mov     [rsp+288h+pv], r15
0x18007d13f  lea     rdx, [rsp+288h+szVolumeName]; unsigned __int16 *
0x18007d147  lea     rcx, [rsp+288h+pv]; this
0x18007d14c  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007d151  mov     rax, [rsp+288h+pv]
0x18007d156  mov     [rsp+288h+pv], r15
0x18007d15b  mov     [rsi], rax
0x18007d15e  mov     rcx, [rsp+288h+pv]; pv
0x18007d163  call    cs:__imp_CoTaskMemFree
0x18007d169  mov     [rsp+288h+pv], r15
0x18007d16e  mov     [rsp+288h+pv], r15
0x18007d173  mov     rcx, [rsp+288h+var_248]; pv
0x18007d178  call    cs:__imp_CoTaskMemFree
0x18007d17e  mov     [rsp+288h+var_248], r15
0x18007d183  mov     [rsp+288h+var_248], r15
0x18007d188  mov     ebx, [rsp+288h+var_180]
0x18007d18f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007d196  mov     [rsp+288h+var_188], rax
0x18007d19e  lea     rcx, [rsp+288h+var_188]; this
0x18007d1a6  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007d1ab  mov     eax, ebx
0x18007d1ad  mov     rcx, [rsp+288h+var_48]
0x18007d1b5  xor     rcx, rsp; StackCookie
0x18007d1b8  call    __security_check_cookie
0x18007d1bd  add     rsp, 250h
0x18007d1c4  pop     r15
0x18007d1c6  pop     r14
0x18007d1c8  pop     r13
0x18007d1ca  pop     r12
0x18007d1cc  pop     rdi
0x18007d1cd  pop     rsi
0x18007d1ce  pop     rbx
0x18007d1cf  retn
0x18007d1d0  jmp     short loc_18007D188
0x18007d1d2  jmp     short loc_18007D188
0x18007d1d4  jmp     short loc_18007D188
0x18007d1d6  lea     rcx, [rsp+288h+var_188]; this
0x18007d1de  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007d1e3  mov     ebx, eax
0x18007d1e5  lea     rax, [rsp+288h+var_218]
0x18007d1ea  mov     [rsp+288h+var_238], rax
0x18007d1ef  mov     [rsp+288h+var_260], 11h
0x18007d1f7  mov     dword ptr [rsp+288h+var_268], 32Ch
0x18007d1ff  mov     r9, r13
0x18007d202  lea     r8, aSrmpathc; "SRMPATHC"
0x18007d209  mov     rdx, r12
0x18007d20c  lea     rcx, [rsp+288h+var_218]
0x18007d211  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007d216  nop
0x18007d217  lea     r9, aStringcchprint; "StringCchPrintf failed"
0x18007d21e  mov     r8d, ebx
0x18007d221  mov     rdx, rax
0x18007d224  lea     rcx, [rsp+288h+var_188]
0x18007d22c  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```

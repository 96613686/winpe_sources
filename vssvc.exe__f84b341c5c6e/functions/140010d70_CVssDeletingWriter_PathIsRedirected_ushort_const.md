# CVssDeletingWriter::PathIsRedirected(ushort const *)

- ea: `0x140010d70`
- end: `0x14001143a`
- name: `?PathIsRedirected@CVssDeletingWriter@@IEAA_NPEBG@Z`
- size: `1738`
- prototype: `bool __fastcall(CVssDeletingWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x140010200`

## callees

- `0x14000e640`
- `0x140010d70`
- `0x140011a90`
- `0x1400137c0`
- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x14003a8f0`
- `0x140091560`
- `0x1400916f0`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001101e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001101e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400110b5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400110b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001103e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400112a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001103e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400112a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011162`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001133b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011162`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001133b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140010f03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140010f03`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x140010fab`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x140010fab`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001102f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001102f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140010e1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400111a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140010e1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400111a1`
- `VssTrace!__imp_VssTraceMessage` at `0x140011393`
- `VssTrace!__imp_VssTraceMessage` at `0x140011393`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001125c`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001128c`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001125c`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001128c`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140010e56`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140010e56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400110cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001116d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001117b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011197`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400110cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001116d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001117b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011197`

## string_xrefs

- `0x140010da0`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x140010dab`: `CVssDeletingWriter::PathIsRedirected`
- `0x14001111f`: `reparse point found: %s`
- `0x1400112f8`: `GetVolumePathName(%s) failed with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CVssDeletingWriter::PathIsRedirected(CVssDeletingWriter *this, WCHAR *a2)
{
  __int64 v3; // rax
  unsigned int v4; // r14d
  unsigned int v5; // edi
  __int64 i; // rdi
  void *v7; // rcx
  __int64 v8; // rdi
  unsigned __int64 v9; // rdi
  WCHAR *v10; // rax
  WCHAR *v11; // rsi
  __int64 v12; // rcx
  WCHAR *v13; // rdx
  WCHAR v14; // ax
  WCHAR *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  wchar_t *v21; // rax
  DWORD v22; // esi
  DWORD v24; // ebx
  bool v25; // bl
  unsigned __int64 v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-E0h]
  __int64 v28; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+28h] [rbp-D8h]
  __int64 v30; // [rsp+30h] [rbp-D0h]
  __int64 v31; // [rsp+38h] [rbp-C8h]
  __int64 v32; // [rsp+40h] [rbp-C0h]
  _QWORD pExceptionObject[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v36; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v37; // [rsp+78h] [rbp-88h]
  unsigned int v38; // [rsp+80h] [rbp-80h]
  unsigned int v39; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v40; // [rsp+88h] [rbp-78h]
  unsigned int v41; // [rsp+90h] [rbp-70h]
  DWORD TickCount; // [rsp+94h] [rbp-6Ch]
  unsigned int v43; // [rsp+98h] [rbp-68h]
  LPVOID v44[2]; // [rsp+A0h] [rbp-60h]
  LPVOID v45[2]; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v47; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v48; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v49; // [rsp+E0h] [rbp-20h]
  int v50; // [rsp+E8h] [rbp-18h]
  int v51; // [rsp+ECh] [rbp-14h]
  int v52; // [rsp+F0h] [rbp-10h]
  LPVOID pv[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v54; // [rsp+108h] [rbp+8h]
  __int128 v55; // [rsp+118h] [rbp+18h]
  __int128 v56; // [rsp+128h] [rbp+28h]
  __int128 v57; // [rsp+138h] [rbp+38h]
  __int128 v58; // [rsp+148h] [rbp+48h]
  __int128 v59; // [rsp+158h] [rbp+58h]
  __int64 v60; // [rsp+168h] [rbp+68h]
  int v61; // [rsp+170h] [rbp+70h]
  void **v62; // [rsp+178h] [rbp+78h] BYREF
  WCHAR *v63; // [rsp+180h] [rbp+80h]
  WCHAR szVolumePathName[264]; // [rsp+190h] [rbp+90h] BYREF

  v47 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v48 = L"CVssDeletingWriter::PathIsRedirected";
  v49 = L"WRTDELET";
  v50 = 1559;
  v51 = 4;
  v52 = 255;
  v61 = 0x1000000;
  memset_0(pv, 0, 0x78u);
  v35 = 0;
  v40 = L"CVssDeletingWriter::PathIsRedirected";
  v36 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v37 = L"WRTDELET";
  v38 = 1559;
  v39 = 4;
  TickCount = GetTickCount();
  v43 = 255;
  v34 = 0xFFFFFFFF00000000uLL;
  v46 = 0;
  *(_OWORD *)v44 = 0;
  *(_OWORD *)v45 = 0;
  pExceptionObject[0] = 0;
  if ( (int)VssGetTracingContextPerThread(pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(&v34) < 0 )
  {
    v3 = v46;
  }
  else
  {
    v3 = pExceptionObject[0];
    v46 = pExceptionObject[0];
  }
  if ( v3 )
    v41 = *(_DWORD *)(v3 + 48) + 1;
  else
    v41 = 0;
  v4 = 160;
  v5 = 160;
  if ( v43 != 255 )
    v5 = v43;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v34, v39) )
    VssTraceMessage(v36, v37, v38, v41, v39, v40, L"ENTER", v5, 0);
  if ( HIBYTE(v61) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v7 = pv[i];
      if ( v7 )
      {
        CoTaskMemFree(v7);
        pv[i] = 0;
      }
    }
  }
  v63 = 0;
  v62 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  if ( !*a2 )
  {
    v25 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v34, 0);
    CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v62);
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v34);
    return v25;
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = v8 + 1;
  v10 = (WCHAR *)LocalAlloc(0, 2 * v9);
  v11 = v10;
  v63 = v10;
  if ( !v10 )
  {
    LODWORD(pExceptionObject[0]) = -2147024882;
    throw (long *)pExceptionObject;
  }
  if ( !v9 )
    goto LABEL_55;
  if ( v9 > 0x7FFFFFFF )
  {
    *v10 = 0;
    goto LABEL_55;
  }
  v12 = 2147483646;
  v13 = v10;
  do
  {
    if ( !v12 )
      break;
    v14 = *a2;
    if ( !*a2 )
      break;
    ++a2;
    *v13++ = v14;
    --v12;
    --v9;
  }
  while ( v9 );
  v15 = v13 - 1;
  if ( v9 )
    v15 = v13;
  *v15 = 0;
  if ( !v9 )
  {
LABEL_55:
    CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v62);
    LODWORD(pExceptionObject[0]) = -2147418113;
    throw (long *)pExceptionObject;
  }
  v16 = -1;
  do
    ++v16;
  while ( v11[v16] );
  if ( v11[v16 - 1] == 92 )
    v11[v16 - 1] = 0;
  if ( GetVolumePathNameW(v11, szVolumePathName, 0x104u) )
  {
    v17 = -1;
    do
      ++v17;
    while ( szVolumePathName[v17] );
    if ( szVolumePathName[v17 - 1] == 92 )
    {
      v26 = 2 * v17 - 2;
      if ( v26 >= 0x208 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)szVolumePathName + v26) = 0;
    }
    while ( 1 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v11[v18] );
      if ( v18 < 3 || !(unsigned int)_o__wcsicmp(szVolumePathName, v11) )
        break;
      FileAttributesW = GetFileAttributesW(v11);
      if ( FileAttributesW == -1 )
      {
        LastError = GetLastError();
        v47 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v48 = L"CVssDeletingWriter::PathIsRedirected";
        v49 = L"WRTDELET";
        v50 = 1621;
        v51 = 4;
        v52 = 255;
        v61 = 0x1000000;
        *(_OWORD *)pv = 0;
        v54 = 0;
        v55 = 0;
        v56 = 0;
        v57 = 0;
        v58 = 0;
        v59 = 0;
        v60 = 0;
        LODWORD(v27) = LastError;
        CVssFunctionTracer::Trace(&v34, &v47, L"GetFileAttributes(%s) failed with %d", v11, v27);
      }
      else if ( (FileAttributesW & 0x400) != 0 )
      {
        v47 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
        v48 = L"CVssDeletingWriter::PathIsRedirected";
        v49 = L"WRTDELET";
        v50 = 1628;
        v51 = 4;
        v52 = 255;
        v61 = 0x1000000;
        memset_0(pv, 0, 0x78u);
        CVssFunctionTracer::Trace(&v34, &v47, L"reparse point found: %s", v11);
        CVssFunctionTracer::TraceInternalWithFormat(
          (CVssFunctionTracer *)&v34,
          L"RETURN",
          0xAAu,
          L"Returning BOOL: %s",
          L"TRUE");
        LocalFree(v11);
        CoTaskMemFree(v44[0]);
        v44[0] = 0;
        CoTaskMemFree(v44[1]);
        v44[1] = 0;
        CoTaskMemFree(v45[0]);
        v45[0] = 0;
        CoTaskMemFree(v45[1]);
        v45[1] = 0;
        v22 = GetTickCount() - TickCount;
        if ( v43 != 255 )
          v4 = v43;
        LODWORD(v32) = v22;
        LODWORD(v31) = v22 % 0x3E8;
        LODWORD(v30) = v22 / 0x3E8 % 0x3C;
        LODWORD(v29) = v22 / 0xEA60 % 0x3C;
        LODWORD(v28) = v22 / 0x36EE80 % 0x3C;
        CVssFunctionTracer::TraceInternalWithFormat(
          (CVssFunctionTracer *)&v34,
          L"EXIT",
          v4,
          L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
          v28,
          v29,
          v30,
          v31,
          v32,
          v35);
        VssSetTracingContextPerThread(v46);
        return 1;
      }
      v21 = wcsrchr(v11, 0x5Cu);
      if ( !v21 )
        break;
      *v21 = 0;
    }
  }
  else
  {
    v24 = GetLastError();
    v47 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
    v48 = L"CVssDeletingWriter::PathIsRedirected";
    v49 = L"WRTDELET";
    v50 = 1582;
    v51 = 4;
    v52 = 255;
    v61 = 0x1000000;
    memset_0(pv, 0, 0x78u);
    LODWORD(v27) = v24;
    CVssFunctionTracer::Trace(&v34, &v47, L"GetVolumePathName(%s) failed with %d", v11, v27);
  }
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)&v34,
    L"RETURN",
    0xAAu,
    L"Returning BOOL: %s",
    L"FALSE");
  LocalFree(v11);
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v34);
  return 0;
}

```

## disassembly

```asm
0x140010d70  push    rbp
0x140010d72  push    rbx
0x140010d73  push    rsi
0x140010d74  push    rdi
0x140010d75  push    r12
0x140010d77  push    r13
0x140010d79  push    r14
0x140010d7b  push    r15
0x140010d7d  lea     rbp, [rsp-2B8h]
0x140010d85  sub     rsp, 3B8h
0x140010d8c  mov     rax, cs:__security_cookie
0x140010d93  xor     rax, rsp
0x140010d96  mov     [rbp+2F0h+var_50], rax
0x140010d9d  mov     rbx, rdx
0x140010da0  lea     r12, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x140010da7  mov     [rbp+2F0h+var_320], r12
0x140010dab  lea     r13, aCvssdeletingwr_4; "CVssDeletingWriter::PathIsRedirected"
0x140010db2  mov     [rbp+2F0h+var_318], r13
0x140010db6  lea     rax, aWrtdelet; "WRTDELET"
0x140010dbd  mov     [rbp+2F0h+var_310], rax
0x140010dc1  mov     [rbp+2F0h+var_308], 617h
0x140010dc8  mov     [rbp+2F0h+var_304], 4
0x140010dcf  mov     [rbp+2F0h+var_300], 0FFh
0x140010dd6  xor     r15d, r15d
0x140010dd9  mov     [rbp+2F0h+var_280], 1000000h
0x140010de0  xor     edx, edx; Val
0x140010de2  mov     r8d, 78h ; 'x'; Size
0x140010de8  lea     rcx, [rbp+2F0h+pv]; void *
0x140010dec  call    memset_0
0x140010df1  mov     [rsp+3F0h+var_388], r15d
0x140010df6  mov     rax, [rbp+2F0h+var_318]
0x140010dfa  mov     [rbp+2F0h+var_368], rax
0x140010dfe  mov     rax, [rbp+2F0h+var_320]
0x140010e02  mov     [rsp+3F0h+var_380], rax
0x140010e07  mov     rax, [rbp+2F0h+var_310]
0x140010e0b  mov     [rsp+3F0h+var_378], rax
0x140010e10  mov     eax, [rbp+2F0h+var_308]
0x140010e13  mov     [rbp+2F0h+var_370], eax
0x140010e16  mov     eax, [rbp+2F0h+var_304]
0x140010e19  mov     [rbp+2F0h+var_36C], eax
0x140010e1c  call    cs:__imp_GetTickCount
0x140010e22  mov     [rbp+2F0h+var_35C], eax
0x140010e25  mov     [rsp+3F0h+var_38C], 0FFFFFFFFh
0x140010e2d  mov     eax, [rbp+2F0h+var_300]
0x140010e30  mov     [rbp+2F0h+var_358], eax
0x140010e33  mov     [rsp+3F0h+var_390], r15d
0x140010e38  mov     [rbp+2F0h+var_330], r15
0x140010e3c  xorps   xmm0, xmm0
0x140010e3f  movdqa  xmmword ptr [rbp+2F0h+var_350], xmm0
0x140010e44  xorps   xmm1, xmm1
0x140010e47  movdqa  xmmword ptr [rbp+2F0h+var_340], xmm1
0x140010e4c  mov     [rsp+3F0h+pExceptionObject], r15
0x140010e51  lea     rcx, [rsp+3F0h+pExceptionObject]
0x140010e56  call    cs:__imp_VssGetTracingContextPerThread
0x140010e5c  test    eax, eax
0x140010e5e  jns     loc_140011287
0x140010e64  mov     rax, [rbp+2F0h+var_330]
0x140010e68  test    rax, rax
0x140010e6b  jz      loc_140011353
0x140010e71  mov     eax, [rax+30h]
0x140010e74  inc     eax
0x140010e76  mov     [rbp+2F0h+var_360], eax
0x140010e79  mov     r14d, 0A0h
0x140010e7f  mov     edi, r14d
0x140010e82  cmp     [rbp+2F0h+var_358], 0FFh
0x140010e89  cmovnz  edi, [rbp+2F0h+var_358]
0x140010e8d  mov     edx, [rbp+2F0h+var_36C]; unsigned int
0x140010e90  lea     rcx, [rsp+3F0h+var_390]; this
0x140010e95  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140010e9a  test    eax, eax
0x140010e9c  jnz     loc_14001135C
0x140010ea2  cmp     byte ptr [rbp+2F0h+var_280+3], r15b
0x140010ea6  jz      short loc_140010EC7
0x140010ea8  mov     rdi, r15
0x140010eab  nop     dword ptr [rax+rax+00h]
0x140010eb0  mov     rcx, [rbp+rdi*8+2F0h+pv]; pv
0x140010eb5  test    rcx, rcx
0x140010eb8  jnz     loc_1400110CD
0x140010ebe  inc     rdi
0x140010ec1  cmp     rdi, 0Fh
0x140010ec5  jnz     short loc_140010EB0
0x140010ec7  mov     [rbp+2F0h+var_270], r15
0x140010ece  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140010ed5  mov     [rbp+2F0h+var_278], rax
0x140010ed9  cmp     word ptr [rbx], 0
0x140010edd  jz      loc_14001139E
0x140010ee3  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x140010eea  nop     word ptr [rax+rax+00h]
0x140010ef0  inc     rdi
0x140010ef3  cmp     word ptr [rbx+rdi*2], 0
0x140010ef8  jnz     short loc_140010EF0
0x140010efa  inc     rdi
0x140010efd  lea     rdx, [rdi+rdi]; uBytes
0x140010f01  xor     ecx, ecx; uFlags
0x140010f03  call    cs:__imp_LocalAlloc
0x140010f09  mov     rsi, rax
0x140010f0c  mov     [rbp+2F0h+var_270], rax
0x140010f13  test    rax, rax
0x140010f16  jz      loc_1400113C9
0x140010f1c  test    rdi, rdi
0x140010f1f  jz      loc_1400113E7
0x140010f25  cmp     rdi, 7FFFFFFFh
0x140010f2c  ja      loc_1400113E3
0x140010f32  mov     ecx, 7FFFFFFEh
0x140010f37  mov     rdx, rax
0x140010f3a  nop     word ptr [rax+rax+00h]
0x140010f40  test    rcx, rcx
0x140010f43  jz      short loc_140010F61
0x140010f45  movzx   eax, word ptr [rbx]
0x140010f48  test    ax, ax
0x140010f4b  jz      short loc_140010F61
0x140010f4d  add     rbx, 2
0x140010f51  mov     [rdx], ax
0x140010f54  add     rdx, 2
0x140010f58  dec     rcx
0x140010f5b  sub     rdi, 1
0x140010f5f  jnz     short loc_140010F40
0x140010f61  lea     rcx, [rdx-2]
0x140010f65  test    rdi, rdi
0x140010f68  cmovnz  rcx, rdx
0x140010f6c  mov     [rcx], r15w
0x140010f70  jz      loc_1400113E7
0x140010f76  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140010f7d  nop     dword ptr [rax]
0x140010f80  lea     rax, [rax+1]
0x140010f84  cmp     word ptr [rsi+rax*2], 0
0x140010f89  jnz     short loc_140010F80
0x140010f8b  lea     rcx, [rax+rax]
0x140010f8f  cmp     word ptr [rcx+rsi-2], 5Ch ; '\'
0x140010f95  jz      loc_14001140A
0x140010f9b  mov     r8d, 104h; cchBufferLength
0x140010fa1  lea     rdx, [rbp+2F0h+szVolumePathName]; lpszVolumePathName
0x140010fa8  mov     rcx, rsi; lpszFileName
0x140010fab  call    cs:__imp_GetVolumePathNameW
0x140010fb1  test    eax, eax
0x140010fb3  jz      loc_1400112A8
0x140010fb9  lea     rcx, [rbp+2F0h+szVolumePathName]
0x140010fc0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140010fc7  nop     word ptr [rax+rax+00000000h]
0x140010fd0  lea     rax, [rax+1]
0x140010fd4  cmp     word ptr [rcx+rax*2], 0
0x140010fd9  jnz     short loc_140010FD0
0x140010fdb  cmp     [rbp+rax*2+2F0h+var_262], 5Ch ; '\'
0x140010fe4  jz      loc_140011415
0x140010fea  lea     rdi, aWrtdelet; "WRTDELET"
0x140010ff1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140010ff8  nop     dword ptr [rax+rax+00000000h]
0x140011000  inc     rax
0x140011003  cmp     word ptr [rsi+rax*2], 0
0x140011008  jnz     short loc_140011000
0x14001100a  cmp     rax, 3
0x14001100e  jb      loc_14001130D
0x140011014  mov     rdx, rsi
0x140011017  lea     rcx, [rbp+2F0h+szVolumePathName]
0x14001101e  call    cs:__imp__o__wcsicmp
0x140011024  test    eax, eax
0x140011026  jz      loc_14001130D
0x14001102c  mov     rcx, rsi; lpFileName
0x14001102f  call    cs:__imp_GetFileAttributesW
0x140011035  cmp     eax, 0FFFFFFFFh
0x140011038  jnz     loc_1400110DD
0x14001103e  call    cs:__imp_GetLastError
0x140011044  mov     [rbp+2F0h+var_320], r12
0x140011048  mov     [rbp+2F0h+var_318], r13
0x14001104c  mov     [rbp+2F0h+var_310], rdi
0x140011050  mov     [rbp+2F0h+var_308], 655h
0x140011057  mov     [rbp+2F0h+var_304], 4
0x14001105e  mov     [rbp+2F0h+var_300], 0FFh
0x140011065  mov     [rbp+2F0h+var_280], 1000000h
0x14001106c  xorps   xmm0, xmm0
0x14001106f  xor     ecx, ecx
0x140011071  movups  xmmword ptr [rbp+2F0h+pv], xmm0
0x140011075  movups  [rbp+2F0h+var_2E8], xmm0
0x140011079  movups  [rbp+2F0h+var_2D8], xmm0
0x14001107d  movups  [rbp+2F0h+var_2C8], xmm0
0x140011081  movups  [rbp+2F0h+var_2B8], xmm0
0x140011085  movups  [rbp+2F0h+var_2A8], xmm0
0x140011089  movups  [rbp+2F0h+var_298], xmm0
0x14001108d  mov     [rbp+2F0h+var_288], rcx
0x140011091  mov     dword ptr [rsp+3F0h+var_3D0], eax
0x140011095  mov     r9, rsi
0x140011098  lea     r8, aGetfileattribu; "GetFileAttributes(%s) failed with %d"
0x14001109f  lea     rdx, [rbp+2F0h+var_320]
0x1400110a3  lea     rcx, [rsp+3F0h+var_390]
0x1400110a8  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400110ad  mov     edx, 5Ch ; '\'; Ch
0x1400110b2  mov     rcx, rsi; Str
0x1400110b5  call    cs:__imp_wcsrchr
0x1400110bb  test    rax, rax
0x1400110be  jz      loc_14001130D
0x1400110c4  mov     [rax], r15w
0x1400110c8  jmp     loc_140010FF1
0x1400110cd  call    cs:__imp_CoTaskMemFree
0x1400110d3  mov     [rbp+rdi*8+2F0h+pv], r15
0x1400110d8  jmp     loc_140010EBE
0x1400110dd  bt      eax, 0Ah
0x1400110e1  jnb     short loc_1400110AD
0x1400110e3  mov     [rbp+2F0h+var_320], r12
0x1400110e7  mov     [rbp+2F0h+var_318], r13
0x1400110eb  mov     [rbp+2F0h+var_310], rdi
0x1400110ef  mov     [rbp+2F0h+var_308], 65Ch
0x1400110f6  mov     [rbp+2F0h+var_304], 4
0x1400110fd  mov     [rbp+2F0h+var_300], 0FFh
0x140011104  mov     [rbp+2F0h+var_280], 1000000h
0x14001110b  xor     edx, edx; Val
0x14001110d  mov     r8d, 78h ; 'x'; Size
0x140011113  lea     rcx, [rbp+2F0h+pv]; void *
0x140011117  call    memset_0
0x14001111c  mov     r9, rsi
0x14001111f  lea     r8, aReparsePointFo; "reparse point found: %s"
0x140011126  lea     rdx, [rbp+2F0h+var_320]
0x14001112a  lea     rcx, [rsp+3F0h+var_390]
0x14001112f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140011134  lea     rax, aTrue; "TRUE"
0x14001113b  mov     [rsp+3F0h+var_3D0], rax
0x140011140  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x140011147  mov     r8d, 0AAh; unsigned int
0x14001114d  lea     rdx, aReturn; "RETURN"
0x140011154  lea     rcx, [rsp+3F0h+var_390]; this
0x140011159  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14001115e  nop
0x14001115f  mov     rcx, rsi; hMem
0x140011162  call    cs:__imp_LocalFree
0x140011168  nop
0x140011169  mov     rcx, [rbp+2F0h+var_350]; pv
0x14001116d  call    cs:__imp_CoTaskMemFree
0x140011173  mov     [rbp+2F0h+var_350], r15
0x140011177  mov     rcx, [rbp+2F0h+var_350+8]; pv
0x14001117b  call    cs:__imp_CoTaskMemFree
0x140011181  mov     [rbp+2F0h+var_350+8], r15
0x140011185  mov     rcx, [rbp+2F0h+var_340]; pv
0x140011189  call    cs:__imp_CoTaskMemFree
0x14001118f  mov     [rbp+2F0h+var_340], r15
0x140011193  mov     rcx, [rbp+2F0h+var_340+8]; pv
0x140011197  call    cs:__imp_CoTaskMemFree
0x14001119d  mov     [rbp+2F0h+var_340+8], r15
0x1400111a1  call    cs:__imp_GetTickCount
0x1400111a7  mov     esi, eax
0x1400111a9  sub     esi, [rbp+2F0h+var_35C]
0x1400111ac  mov     eax, 10624DD3h
0x1400111b1  mul     esi
0x1400111b3  mov     edi, edx
0x1400111b5  shr     edi, 6
0x1400111b8  mov     eax, 88888889h
0x1400111bd  mul     edi
0x1400111bf  shr     edx, 5
0x1400111c2  imul    ecx, edx, 3Ch ; '<'
0x1400111c5  mov     ebx, edi
0x1400111c7  sub     ebx, ecx
0x1400111c9  mov     eax, 45E7B273h
0x1400111ce  mul     esi
0x1400111d0  mov     r11d, edx
0x1400111d3  shr     r11d, 0Eh
0x1400111d7  mov     eax, 88888889h
0x1400111dc  mul     r11d
0x1400111df  shr     edx, 5
0x1400111e2  imul    ecx, edx, 3Ch ; '<'
0x1400111e5  sub     r11d, ecx
0x1400111e8  mov     eax, 95217CB1h
0x1400111ed  mul     esi
0x1400111ef  mov     r10d, edx
0x1400111f2  shr     r10d, 15h
0x1400111f6  mov     eax, 88888889h
0x1400111fb  mul     r10d
0x1400111fe  shr     edx, 5
0x140011201  imul    eax, edx, 3Ch ; '<'
0x140011204  sub     r10d, eax
0x140011207  mov     r9d, [rsp+3F0h+var_388]
0x14001120c  cmp     [rbp+2F0h+var_358], 0FFh
0x140011213  cmovnz  r14d, [rbp+2F0h+var_358]
0x140011218  imul    eax, edi, 3E8h
0x14001121e  mov     ecx, esi
0x140011220  sub     ecx, eax
0x140011222  mov     [rsp+3F0h+var_3A8], r9d
0x140011227  mov     dword ptr [rsp+3F0h+var_3B0], esi
0x14001122b  mov     dword ptr [rsp+3F0h+var_3B8], ecx
0x14001122f  mov     dword ptr [rsp+3F0h+var_3C0], ebx
0x140011233  mov     dword ptr [rsp+3F0h+var_3C8], r11d
0x140011238  mov     dword ptr [rsp+3F0h+var_3D0], r10d
0x14001123d  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140011244  mov     r8d, r14d; unsigned int
0x140011247  lea     rdx, aExit; "EXIT"
0x14001124e  lea     rcx, [rsp+3F0h+var_390]; this
0x140011253  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140011258  mov     rcx, [rbp+2F0h+var_330]
0x14001125c  call    cs:__imp_VssSetTracingContextPerThread
0x140011262  mov     al, 1
0x140011264  mov     rcx, [rbp+2F0h+var_50]
0x14001126b  xor     rcx, rsp; StackCookie
0x14001126e  call    __security_check_cookie
0x140011273  add     rsp, 3B8h
0x14001127a  pop     r15
0x14001127c  pop     r14
0x14001127e  pop     r13
0x140011280  pop     r12
0x140011282  pop     rdi
0x140011283  pop     rsi
0x140011284  pop     rbx
0x140011285  pop     rbp
0x140011286  retn
  ... truncated ...
```

# CVssRegistryValueIterator::GetCurrentValueContent(ushort * &,ulong &)

- ea: `0x14000c2a0`
- end: `0x14000c843`
- name: `?GetCurrentValueContent@CVssRegistryValueIterator@@QEAAXAEAPEAGAEAK@Z`
- size: `1443`
- prototype: `void __fastcall(CVssRegistryValueIterator *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c84c`

## callees

- `0x14000c2a0`
- `0x14000dcd0`
- `0x1400138e0`
- `0x140013c60`
- `0x140049ec4`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000c47f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000c47f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c425`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c425`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000c344`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000c767`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000c344`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000c767`
- `VssTrace!__imp_VssTraceMessage` at `0x14000c5a3`
- `VssTrace!__imp_VssTraceMessage` at `0x14000c5a3`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000c547`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000c822`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000c547`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000c822`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000c37e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000c37e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c74f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c75d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c74f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c75d`

## string_xrefs

- `0x14000c2d3`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000c4c3`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000c5b2`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000c636`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000c6bb`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x14000c2c8`: `base\stor\vss\modules\registry\registry.cxx`
- `0x14000c4b8`: `base\stor\vss\modules\registry\registry.cxx`
- `0x14000c62b`: `base\stor\vss\modules\registry\registry.cxx`
- `0x14000c6b0`: `base\stor\vss\modules\registry\registry.cxx`
- `0x14000c5f5`: `Unexpected error: attempting to read a value of the wrong type`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVssRegistryValueIterator::GetCurrentValueContent(
        CVssRegistryValueIterator *this,
        unsigned __int16 **a2,
        unsigned int *a3)
{
  __int64 v6; // rax
  unsigned int v7; // r14d
  unsigned int v8; // ebx
  __int64 i; // rbx
  void *v10; // rcx
  BYTE *v11; // rax
  unsigned __int16 *v12; // rsi
  LSTATUS v13; // eax
  unsigned int v14; // ebx
  DWORD v15; // esi
  __int64 v16; // r14
  int v17; // r15d
  __int64 v18; // rdi
  int v19; // ebx
  DWORD v20; // edi
  DWORD v21; // esi
  LPDWORD lpReserved; // [rsp+20h] [rbp-E0h]
  LPDWORD lpType; // [rsp+28h] [rbp-D8h]
  LPBYTE lpData; // [rsp+30h] [rbp-D0h]
  LPDWORD lpcbData; // [rsp+38h] [rbp-C8h]
  __int64 v26; // [rsp+40h] [rbp-C0h]
  __int64 pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v31; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v32; // [rsp+78h] [rbp-88h]
  unsigned int v33; // [rsp+80h] [rbp-80h]
  unsigned int v34; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v35; // [rsp+88h] [rbp-78h]
  unsigned int v36; // [rsp+90h] [rbp-70h]
  DWORD TickCount; // [rsp+94h] [rbp-6Ch]
  unsigned int v38; // [rsp+98h] [rbp-68h]
  LPVOID v39[2]; // [rsp+A0h] [rbp-60h]
  LPVOID v40[2]; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v42; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v43; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v44; // [rsp+E0h] [rbp-20h]
  int v45; // [rsp+E8h] [rbp-18h]
  int v46; // [rsp+ECh] [rbp-14h]
  int v47; // [rsp+F0h] [rbp-10h]
  LPVOID pv[15]; // [rsp+F8h] [rbp-8h] BYREF
  int v49; // [rsp+170h] [rbp+70h]
  void **v50; // [rsp+178h] [rbp+78h]
  BYTE *v51; // [rsp+180h] [rbp+80h]
  DWORD cchValueName; // [rsp+1D0h] [rbp+D0h] BYREF
  DWORD Type; // [rsp+1E8h] [rbp+E8h] BYREF

  v42 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v43 = L"CVssRegistryValueIterator::GetCurrentValueContent";
  v44 = L"REGREGSC";
  v45 = 1066;
  v46 = 11;
  v47 = 255;
  v49 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v30 = 0;
  v35 = L"CVssRegistryValueIterator::GetCurrentValueContent";
  v31 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v32 = L"REGREGSC";
  v33 = 1066;
  v34 = 11;
  TickCount = GetTickCount();
  v29[1] = -1;
  v38 = 255;
  v29[0] = 0;
  v41 = 0;
  *(_OWORD *)v39 = 0;
  *(_OWORD *)v40 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(v29) < 0 )
  {
    v6 = v41;
  }
  else
  {
    v6 = pExceptionObject;
    v41 = pExceptionObject;
  }
  if ( v6 )
    v36 = *(_DWORD *)(v6 + 48) + 1;
  else
    v36 = 0;
  v7 = 160;
  v8 = 160;
  if ( v38 != 255 )
    v8 = v38;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v29, v34) )
    VssTraceMessage(v31, v32, v33, v36, v34, v35, L"ENTER", v8, 0);
  if ( HIBYTE(v49) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v10 = pv[i];
      if ( v10 )
      {
        CoTaskMemFree(v10);
        pv[i] = 0;
      }
    }
  }
  CVssRegistryValueIterator::ReadCurrentValueDetails(this);
  if ( *((_DWORD *)this + 4) != 7 )
  {
    v42 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v43 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v44 = L"REGREGSC";
    v45 = 1073;
    v46 = 11;
    v47 = 255;
    v49 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::TranslateGenericError(
      v29,
      &v42,
      2147549183LL,
      L"Unexpected error: attempting to read a value of the wrong type");
  }
  cbData = *((_DWORD *)this + 11);
  v50 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v11 = (BYTE *)LocalAlloc(0, (cbData & 0xFFFFFFFE) + 2LL);
  v12 = (unsigned __int16 *)v11;
  v51 = v11;
  if ( !v11 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  cchValueName = *((_DWORD *)this + 10);
  Type = 0;
  v13 = RegEnumValueW(
          *(HKEY *)this,
          *((_DWORD *)this + 3),
          *((LPWSTR *)this + 4),
          &cchValueName,
          0,
          &Type,
          v11,
          &cbData);
  v14 = v13;
  if ( v13 )
  {
    if ( v13 != 259 )
    {
      v15 = cchValueName;
      v16 = *((_QWORD *)this + 4);
      v17 = *((_DWORD *)this + 3);
      v18 = *(_QWORD *)this;
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
      v42 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v43 = L"CVssRegistryValueIterator::GetCurrentValueContent";
      v44 = L"REGREGSC";
      v45 = 1106;
      v46 = 11;
      v47 = 255;
      v49 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      LODWORD(lpcbData) = v15;
      LODWORD(lpType) = v17;
      CVssFunctionTracer::TranslateGenericError(
        v29,
        &v42,
        v14,
        L"RegEnumValue(%p,%lu,%p,%lu ...)",
        v18,
        lpType,
        v16,
        lpcbData);
    }
    v42 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v43 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v44 = L"REGREGSC";
    v45 = 1104;
    v46 = 11;
    v47 = 255;
    v49 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    LODWORD(lpType) = *((_DWORD *)this + 2);
    LODWORD(lpReserved) = *((_DWORD *)this + 3);
    CVssFunctionTracer::TranslateGenericError(
      v29,
      &v42,
      2147549183LL,
      L"Unexpected error: dwIndex out of scope %lu %lu",
      lpReserved,
      lpType);
  }
  v19 = *((_DWORD *)this + 4);
  v20 = Type;
  if ( Type != v19 )
  {
    v42 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v43 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v44 = L"REGREGSC";
    v45 = 1098;
    v46 = 11;
    v47 = 255;
    v49 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    LODWORD(lpType) = v19;
    LODWORD(lpReserved) = v20;
    CVssFunctionTracer::TranslateGenericError(
      v29,
      &v42,
      2147549183LL,
      L"Unexpected error: current value type changed in the meantime %lu %lu",
      lpReserved,
      lpType);
  }
  *a2 = v12;
  *a3 = cbData >> 1;
  CoTaskMemFree(v39[0]);
  v39[0] = 0;
  CoTaskMemFree(v39[1]);
  v39[1] = 0;
  CoTaskMemFree(v40[0]);
  v40[0] = 0;
  CoTaskMemFree(v40[1]);
  v40[1] = 0;
  v21 = GetTickCount() - TickCount;
  if ( v38 != 255 )
    v7 = v38;
  LODWORD(v26) = v21;
  LODWORD(lpcbData) = v21 % 0x3E8;
  LODWORD(lpData) = v21 / 0x3E8 % 0x3C;
  LODWORD(lpType) = v21 / 0xEA60 % 0x3C;
  LODWORD(lpReserved) = v21 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v29,
    L"EXIT",
    v7,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    lpReserved,
    lpType,
    lpData,
    lpcbData,
    v26,
    v30);
  VssSetTracingContextPerThread(v41);
}

```

## disassembly

```asm
0x14000c2a0  mov     [rsp-8+arg_8], rbx
0x14000c2a5  push    rbp
0x14000c2a6  push    rsi
0x14000c2a7  push    rdi
0x14000c2a8  push    r12
0x14000c2aa  push    r13
0x14000c2ac  push    r14
0x14000c2ae  push    r15
0x14000c2b0  lea     rbp, [rsp-90h]
0x14000c2b8  sub     rsp, 190h
0x14000c2bf  mov     r15, r8
0x14000c2c2  mov     r12, rdx
0x14000c2c5  mov     rdi, rcx
0x14000c2c8  lea     rsi, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000c2cf  mov     [rbp+0C0h+var_F0], rsi
0x14000c2d3  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000c2da  mov     [rbp+0C0h+var_E8], rax
0x14000c2de  lea     rax, aRegregsc; "REGREGSC"
0x14000c2e5  mov     [rbp+0C0h+var_E0], rax
0x14000c2e9  mov     [rbp+0C0h+var_D8], 42Ah
0x14000c2f0  mov     [rbp+0C0h+var_D4], 0Bh
0x14000c2f7  mov     [rbp+0C0h+var_D0], 0FFh
0x14000c2fe  xor     r13d, r13d
0x14000c301  mov     [rbp+0C0h+var_50], 1000000h
0x14000c308  xor     edx, edx; Val
0x14000c30a  mov     r8d, 78h ; 'x'; Size
0x14000c310  lea     rcx, [rbp+0C0h+pv]; void *
0x14000c314  call    memset_0
0x14000c319  mov     [rsp+1C0h+var_158], r13d
0x14000c31e  mov     rax, [rbp+0C0h+var_E8]
0x14000c322  mov     [rbp+0C0h+var_138], rax
0x14000c326  mov     rax, [rbp+0C0h+var_F0]
0x14000c32a  mov     [rsp+1C0h+var_150], rax
0x14000c32f  mov     rax, [rbp+0C0h+var_E0]
0x14000c333  mov     [rsp+1C0h+var_148], rax
0x14000c338  mov     eax, [rbp+0C0h+var_D8]
0x14000c33b  mov     [rbp+0C0h+var_140], eax
0x14000c33e  mov     eax, [rbp+0C0h+var_D4]
0x14000c341  mov     [rbp+0C0h+var_13C], eax
0x14000c344  call    cs:__imp_GetTickCount
0x14000c34a  mov     [rbp+0C0h+var_12C], eax
0x14000c34d  mov     [rsp+1C0h+var_15C], 0FFFFFFFFh
0x14000c355  mov     eax, [rbp+0C0h+var_D0]
0x14000c358  mov     [rbp+0C0h+var_128], eax
0x14000c35b  mov     [rsp+1C0h+var_160], r13d
0x14000c360  mov     [rbp+0C0h+var_100], r13
0x14000c364  xorps   xmm0, xmm0
0x14000c367  movdqa  xmmword ptr [rbp+0C0h+var_120], xmm0
0x14000c36c  xorps   xmm1, xmm1
0x14000c36f  movdqa  xmmword ptr [rbp+0C0h+var_110], xmm1
0x14000c374  mov     [rsp+1C0h+pExceptionObject], r13
0x14000c379  lea     rcx, [rsp+1C0h+pExceptionObject]
0x14000c37e  call    cs:__imp_VssGetTracingContextPerThread
0x14000c384  test    eax, eax
0x14000c386  jns     loc_14000C542
0x14000c38c  mov     rax, [rbp+0C0h+var_100]
0x14000c390  test    rax, rax
0x14000c393  jz      loc_14000C563
0x14000c399  mov     eax, [rax+30h]
0x14000c39c  inc     eax
0x14000c39e  mov     [rbp+0C0h+var_130], eax
0x14000c3a1  mov     r14d, 0A0h
0x14000c3a7  mov     ebx, r14d
0x14000c3aa  cmp     [rbp+0C0h+var_128], 0FFh
0x14000c3b1  cmovnz  ebx, [rbp+0C0h+var_128]
0x14000c3b5  mov     edx, [rbp+0C0h+var_13C]; unsigned int
0x14000c3b8  lea     rcx, [rsp+1C0h+var_160]; this
0x14000c3bd  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14000c3c2  test    eax, eax
0x14000c3c4  jnz     loc_14000C56C
0x14000c3ca  cmp     byte ptr [rbp+0C0h+var_50+3], r13b
0x14000c3ce  jz      short loc_14000C3F7
0x14000c3d0  mov     rbx, r13
0x14000c3d3  nop     dword ptr [rax+00h]
0x14000c3d7  nop     word ptr [rax+rax+00000000h]
0x14000c3e0  mov     rcx, [rbp+rbx*8+0C0h+pv]; pv
0x14000c3e5  test    rcx, rcx
0x14000c3e8  jnz     loc_14000C532
0x14000c3ee  inc     rbx
0x14000c3f1  cmp     rbx, 0Fh
0x14000c3f5  jnz     short loc_14000C3E0
0x14000c3f7  mov     rcx, rdi; this
0x14000c3fa  call    ?ReadCurrentValueDetails@CVssRegistryValueIterator@@AEAAXXZ; CVssRegistryValueIterator::ReadCurrentValueDetails(void)
0x14000c3ff  cmp     dword ptr [rdi+10h], 7
0x14000c403  jnz     loc_14000C5AE
0x14000c409  mov     edx, [rdi+2Ch]
0x14000c40c  mov     [rsp+1C0h+cbData], edx
0x14000c410  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14000c417  mov     [rbp+0C0h+var_48], rax
0x14000c41b  and     rdx, 0FFFFFFFFFFFFFFFEh
0x14000c41f  add     rdx, 2; uBytes
0x14000c423  xor     ecx, ecx; uFlags
0x14000c425  call    cs:__imp_LocalAlloc
0x14000c42b  mov     rsi, rax
0x14000c42e  mov     [rbp+0C0h+var_40], rax
0x14000c435  test    rax, rax
0x14000c438  jz      loc_14000C611
0x14000c43e  mov     eax, [rdi+28h]
0x14000c441  mov     [rbp+0C0h+cchValueName], eax
0x14000c447  mov     [rbp+0C0h+Type], r13d
0x14000c44e  lea     rax, [rsp+1C0h+cbData]
0x14000c453  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x14000c458  mov     [rsp+1C0h+lpData], rsi; lpData
0x14000c45d  lea     rax, [rbp+0C0h+Type]
0x14000c464  mov     [rsp+1C0h+lpType], rax; lpType
0x14000c469  mov     [rsp+1C0h+lpReserved], r13; lpReserved
0x14000c46e  lea     r9, [rbp+0C0h+cchValueName]; lpcchValueName
0x14000c475  mov     r8, [rdi+20h]; lpValueName
0x14000c479  mov     edx, [rdi+0Ch]; dwIndex
0x14000c47c  mov     rcx, [rdi]; hKey
0x14000c47f  call    cs:__imp_RegEnumValueW
0x14000c485  mov     ebx, eax
0x14000c487  test    eax, eax
0x14000c489  jz      loc_14000C6A3
0x14000c48f  cmp     eax, 103h
0x14000c494  jz      loc_14000C62B
0x14000c49a  mov     esi, [rbp+0C0h+cchValueName]
0x14000c4a0  mov     r14, [rdi+20h]
0x14000c4a4  mov     r15d, [rdi+0Ch]
0x14000c4a8  mov     rdi, [rdi]
0x14000c4ab  test    eax, eax
0x14000c4ad  jle     short loc_14000C4B8
0x14000c4af  movzx   ebx, ax
0x14000c4b2  or      ebx, 80070000h
0x14000c4b8  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000c4bf  mov     [rbp+0C0h+var_F0], rax
0x14000c4c3  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000c4ca  mov     [rbp+0C0h+var_E8], rax
0x14000c4ce  lea     rax, aRegregsc; "REGREGSC"
0x14000c4d5  mov     [rbp+0C0h+var_E0], rax
0x14000c4d9  mov     [rbp+0C0h+var_D8], 452h
0x14000c4e0  mov     [rbp+0C0h+var_D4], 0Bh
0x14000c4e7  mov     [rbp+0C0h+var_D0], 0FFh
0x14000c4ee  mov     [rbp+0C0h+var_50], 1000000h
0x14000c4f5  xor     edx, edx; Val
0x14000c4f7  mov     r8d, 78h ; 'x'; Size
0x14000c4fd  lea     rcx, [rbp+0C0h+pv]; void *
0x14000c501  call    memset_0
0x14000c506  mov     dword ptr [rsp+1C0h+lpcbData], esi
0x14000c50a  mov     [rsp+1C0h+lpData], r14
0x14000c50f  mov     dword ptr [rsp+1C0h+lpType], r15d
0x14000c514  mov     [rsp+1C0h+lpReserved], rdi
0x14000c519  lea     r9, aRegenumvaluePL; "RegEnumValue(%p,%lu,%p,%lu ...)"
0x14000c520  mov     r8d, ebx
0x14000c523  lea     rdx, [rbp+0C0h+var_F0]
0x14000c527  lea     rcx, [rsp+1C0h+var_160]
0x14000c52c  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000c532  call    cs:__imp_CoTaskMemFree
0x14000c538  mov     [rbp+rbx*8+0C0h+pv], r13
0x14000c53d  jmp     loc_14000C3EE
0x14000c542  lea     rcx, [rsp+1C0h+var_160]
0x14000c547  call    cs:__imp_VssSetTracingContextPerThread
0x14000c54d  test    eax, eax
0x14000c54f  js      loc_14000C38C
0x14000c555  mov     rax, [rsp+1C0h+pExceptionObject]
0x14000c55a  mov     [rbp+0C0h+var_100], rax
0x14000c55e  jmp     loc_14000C390
0x14000c563  mov     [rbp+0C0h+var_130], r13d
0x14000c567  jmp     loc_14000C3A1
0x14000c56c  mov     [rsp+1C0h+var_180], r13
0x14000c571  mov     dword ptr [rsp+1C0h+lpcbData], ebx
0x14000c575  lea     rax, aEnter; "ENTER"
0x14000c57c  mov     [rsp+1C0h+lpData], rax
0x14000c581  mov     rax, [rbp+0C0h+var_138]
0x14000c585  mov     [rsp+1C0h+lpType], rax
0x14000c58a  mov     eax, [rbp+0C0h+var_13C]
0x14000c58d  mov     dword ptr [rsp+1C0h+lpReserved], eax
0x14000c591  mov     r9d, [rbp+0C0h+var_130]
0x14000c595  mov     r8d, [rbp+0C0h+var_140]
0x14000c599  mov     rdx, [rsp+1C0h+var_148]
0x14000c59e  mov     rcx, [rsp+1C0h+var_150]
0x14000c5a3  call    cs:__imp_VssTraceMessage
0x14000c5a9  jmp     loc_14000C3CA
0x14000c5ae  mov     [rbp+0C0h+var_F0], rsi
0x14000c5b2  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000c5b9  mov     [rbp+0C0h+var_E8], rax
0x14000c5bd  lea     rax, aRegregsc; "REGREGSC"
0x14000c5c4  mov     [rbp+0C0h+var_E0], rax
0x14000c5c8  mov     [rbp+0C0h+var_D8], 431h
0x14000c5cf  mov     [rbp+0C0h+var_D4], 0Bh
0x14000c5d6  mov     [rbp+0C0h+var_D0], 0FFh
0x14000c5dd  mov     [rbp+0C0h+var_50], 1000000h
0x14000c5e4  xor     edx, edx; Val
0x14000c5e6  mov     r8d, 78h ; 'x'; Size
0x14000c5ec  lea     rcx, [rbp+0C0h+pv]; void *
0x14000c5f0  call    memset_0
0x14000c5f5  lea     r9, aUnexpectedErro_6; "Unexpected error: attempting to read a "...
0x14000c5fc  mov     r8d, 8000FFFFh
0x14000c602  lea     rdx, [rbp+0C0h+var_F0]
0x14000c606  lea     rcx, [rsp+1C0h+var_160]
0x14000c60b  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000c611  mov     dword ptr [rsp+1C0h+pExceptionObject], 8007000Eh
0x14000c619  lea     rdx, _TI1J; pThrowInfo
0x14000c620  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x14000c625  call    _CxxThrowException_0
0x14000c62b  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000c632  mov     [rbp+0C0h+var_F0], rax
0x14000c636  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000c63d  mov     [rbp+0C0h+var_E8], rax
0x14000c641  lea     rax, aRegregsc; "REGREGSC"
0x14000c648  mov     [rbp+0C0h+var_E0], rax
0x14000c64c  mov     [rbp+0C0h+var_D8], 450h
0x14000c653  mov     [rbp+0C0h+var_D4], 0Bh
0x14000c65a  mov     [rbp+0C0h+var_D0], 0FFh
0x14000c661  mov     [rbp+0C0h+var_50], 1000000h
0x14000c668  xor     edx, edx; Val
0x14000c66a  mov     r8d, 78h ; 'x'; Size
0x14000c670  lea     rcx, [rbp+0C0h+pv]; void *
0x14000c674  call    memset_0
0x14000c679  mov     eax, [rdi+8]
0x14000c67c  mov     dword ptr [rsp+1C0h+lpType], eax
0x14000c680  mov     eax, [rdi+0Ch]
0x14000c683  mov     dword ptr [rsp+1C0h+lpReserved], eax
0x14000c687  lea     r9, aUnexpectedErro_11; "Unexpected error: dwIndex out of scope "...
0x14000c68e  mov     r8d, 8000FFFFh
0x14000c694  lea     rdx, [rbp+0C0h+var_F0]
0x14000c698  lea     rcx, [rsp+1C0h+var_160]
0x14000c69d  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000c6a3  mov     ebx, [rdi+10h]
0x14000c6a6  mov     edi, [rbp+0C0h+Type]
0x14000c6ac  cmp     edi, ebx
0x14000c6ae  jz      short loc_14000C722
0x14000c6b0  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000c6b7  mov     [rbp+0C0h+var_F0], rax
0x14000c6bb  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000c6c2  mov     [rbp+0C0h+var_E8], rax
0x14000c6c6  lea     rax, aRegregsc; "REGREGSC"
0x14000c6cd  mov     [rbp+0C0h+var_E0], rax
0x14000c6d1  mov     [rbp+0C0h+var_D8], 44Ah
0x14000c6d8  mov     [rbp+0C0h+var_D4], 0Bh
0x14000c6df  mov     [rbp+0C0h+var_D0], 0FFh
0x14000c6e6  mov     [rbp+0C0h+var_50], 1000000h
0x14000c6ed  xor     edx, edx; Val
0x14000c6ef  mov     r8d, 78h ; 'x'; Size
0x14000c6f5  lea     rcx, [rbp+0C0h+pv]; void *
0x14000c6f9  call    memset_0
0x14000c6fe  mov     dword ptr [rsp+1C0h+lpType], ebx
0x14000c702  mov     dword ptr [rsp+1C0h+lpReserved], edi
0x14000c706  lea     r9, aUnexpectedErro_2; "Unexpected error: current value type ch"...
0x14000c70d  mov     r8d, 8000FFFFh
0x14000c713  lea     rdx, [rbp+0C0h+var_F0]
0x14000c717  lea     rcx, [rsp+1C0h+var_160]
0x14000c71c  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000c722  mov     [r12], rsi
0x14000c726  mov     eax, [rsp+1C0h+cbData]
0x14000c72a  shr     eax, 1
0x14000c72c  mov     [r15], eax
0x14000c72f  mov     rcx, [rbp+0C0h+var_120]; pv
0x14000c733  call    cs:__imp_CoTaskMemFree
0x14000c739  mov     [rbp+0C0h+var_120], r13
0x14000c73d  mov     rcx, [rbp+0C0h+var_120+8]; pv
0x14000c741  call    cs:__imp_CoTaskMemFree
0x14000c747  mov     [rbp+0C0h+var_120+8], r13
0x14000c74b  mov     rcx, [rbp+0C0h+var_110]; pv
0x14000c74f  call    cs:__imp_CoTaskMemFree
0x14000c755  mov     [rbp+0C0h+var_110], r13
0x14000c759  mov     rcx, [rbp+0C0h+var_110+8]; pv
0x14000c75d  call    cs:__imp_CoTaskMemFree
0x14000c763  mov     [rbp+0C0h+var_110+8], r13
0x14000c767  call    cs:__imp_GetTickCount
0x14000c76d  mov     esi, eax
0x14000c76f  sub     esi, [rbp+0C0h+var_12C]
0x14000c772  mov     eax, 10624DD3h
0x14000c777  mul     esi
0x14000c779  mov     edi, edx
0x14000c77b  shr     edi, 6
0x14000c77e  mov     eax, 88888889h
0x14000c783  mul     edi
0x14000c785  shr     edx, 5
0x14000c788  imul    ecx, edx, 3Ch ; '<'
0x14000c78b  mov     ebx, edi
0x14000c78d  sub     ebx, ecx
0x14000c78f  mov     eax, 45E7B273h
0x14000c794  mul     esi
0x14000c796  mov     r11d, edx
0x14000c799  shr     r11d, 0Eh
0x14000c79d  mov     eax, 88888889h
0x14000c7a2  mul     r11d
0x14000c7a5  shr     edx, 5
0x14000c7a8  imul    ecx, edx, 3Ch ; '<'
0x14000c7ab  sub     r11d, ecx
0x14000c7ae  mov     eax, 95217CB1h
0x14000c7b3  mul     esi
0x14000c7b5  mov     r10d, edx
0x14000c7b8  shr     r10d, 15h
0x14000c7bc  mov     eax, 88888889h
0x14000c7c1  mul     r10d
0x14000c7c4  shr     edx, 5
0x14000c7c7  imul    eax, edx, 3Ch ; '<'
0x14000c7ca  sub     r10d, eax
0x14000c7cd  mov     r9d, [rsp+1C0h+var_158]
0x14000c7d2  cmp     [rbp+0C0h+var_128], 0FFh
0x14000c7d9  cmovnz  r14d, [rbp+0C0h+var_128]
0x14000c7de  imul    eax, edi, 3E8h
0x14000c7e4  mov     ecx, esi
0x14000c7e6  sub     ecx, eax
0x14000c7e8  mov     [rsp+1C0h+var_178], r9d
0x14000c7ed  mov     dword ptr [rsp+1C0h+var_180], esi
0x14000c7f1  mov     dword ptr [rsp+1C0h+lpcbData], ecx
0x14000c7f5  mov     dword ptr [rsp+1C0h+lpData], ebx
  ... truncated ...
```

# CVssRegistryKey::GetValue(ushort const *,ushort * &,bool)

- ea: `0x140027690`
- end: `0x140027ca9`
- name: `?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAPEAG_N@Z`
- size: `1561`
- prototype: `bool(CVssRegistryKey *__hidden this, const unsigned __int16 *, unsigned __int16 **, bool)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140015fb0`
- `0x140027cb0`
- `0x14009b4ac`

## callees

- `0x1400137c0`
- `0x1400138e0`
- `0x140013c60`
- `0x140027690`
- `0x140049ec4`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002781a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140027a1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002781a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140027a1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140027739`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002788e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140027739`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002788e`
- `VssTrace!__imp_VssTraceMessage` at `0x140027bed`
- `VssTrace!__imp_VssTraceMessage` at `0x140027bed`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140027949`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140027981`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140027949`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140027981`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140027773`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140027773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400279d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400279d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002785a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027876`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027884`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002796c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002785a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027876`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027884`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002796c`

## string_xrefs

- `0x1400276bd`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140027a9a`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140027b38`: `base\stor\vss\modules\registry\registry.cxx`
- `0x1400276c8`: `CVssRegistryKey::GetValue`
- `0x140027aa5`: `CVssRegistryKey::GetValue`
- `0x140027b43`: `CVssRegistryKey::GetValue`
- `0x140027c15`: `CVssRegistryKey::GetValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CVssRegistryKey::GetValue(HKEY *this, const unsigned __int16 *a2, BYTE **a3, char a4)
{
  __int64 v7; // rax
  unsigned int v8; // r14d
  unsigned int v9; // ebx
  __int64 i; // rbx
  void *v11; // rcx
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  DWORD v14; // esi
  DWORD v16; // ebx
  __int64 v17; // r14
  BYTE *v18; // rbx
  LSTATUS v19; // eax
  unsigned int v20; // r12d
  DWORD v21; // edi
  DWORD v22; // r14d
  HKEY v23; // r12
  HKEY v24; // rsi
  DWORD v25; // ebx
  DWORD v26; // edi
  HKEY v27; // r14
  HKEY v28; // rsi
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPBYTE lpDataa; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  __int64 v32; // [rsp+30h] [rbp-D0h]
  __int64 v33; // [rsp+38h] [rbp-C8h]
  __int64 v34; // [rsp+40h] [rbp-C0h]
  __int64 pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v36; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v39; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v40; // [rsp+78h] [rbp-88h]
  unsigned int v41; // [rsp+80h] [rbp-80h]
  unsigned int v42; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v43; // [rsp+88h] [rbp-78h]
  unsigned int v44; // [rsp+90h] [rbp-70h]
  DWORD TickCount; // [rsp+94h] [rbp-6Ch]
  unsigned int v46; // [rsp+98h] [rbp-68h]
  LPVOID pv[2]; // [rsp+A0h] [rbp-60h]
  LPVOID v48[2]; // [rsp+B0h] [rbp-50h]
  __int64 v49; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v50; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v51; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v52; // [rsp+E0h] [rbp-20h]
  int v53; // [rsp+E8h] [rbp-18h]
  int v54; // [rsp+ECh] [rbp-14h]
  int v55; // [rsp+F0h] [rbp-10h]
  LPVOID v56[15]; // [rsp+F8h] [rbp-8h] BYREF
  int v57; // [rsp+170h] [rbp+70h]
  void **v58; // [rsp+178h] [rbp+78h]
  BYTE *v59; // [rsp+180h] [rbp+80h]
  DWORD cbData; // [rsp+1D0h] [rbp+D0h] BYREF
  DWORD v61; // [rsp+1E0h] [rbp+E0h] BYREF
  DWORD Type; // [rsp+1E8h] [rbp+E8h] BYREF

  LOBYTE(Type) = a4;
  v50 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v51 = L"CVssRegistryKey::GetValue";
  v52 = L"REGREGSC";
  v53 = 394;
  v54 = 11;
  v55 = 255;
  v57 = 0x1000000;
  memset_0(v56, 0, sizeof(v56));
  v38 = 0;
  v43 = L"CVssRegistryKey::GetValue";
  v39 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v40 = L"REGREGSC";
  v41 = 394;
  v42 = 11;
  TickCount = GetTickCount();
  v46 = 255;
  v37 = 0xFFFFFFFF00000000uLL;
  v49 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v48 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(&v37) < 0 )
  {
    v7 = v49;
  }
  else
  {
    v7 = pExceptionObject;
    v49 = pExceptionObject;
  }
  if ( v7 )
    v44 = *(_DWORD *)(v7 + 48) + 1;
  else
    v44 = 0;
  v8 = 160;
  v9 = 160;
  if ( v46 != 255 )
    v9 = v46;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v37, v42) )
    VssTraceMessage(v39, v40, v41, v44, v42, v43, L"ENTER", v9, 0);
  if ( HIBYTE(v57) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v11 = v56[i];
      if ( v11 )
      {
        CoTaskMemFree(v11);
        v56[i] = 0;
      }
    }
  }
  *a3 = 0;
  Type = 0;
  cbData = 0;
  v12 = RegQueryValueExW(this[1], a2, 0, &Type, 0, &cbData);
  v13 = v12;
  if ( v12 == 2 )
  {
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v37,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
    CoTaskMemFree(v48[0]);
    v48[0] = 0;
    CoTaskMemFree(v48[1]);
    v48[1] = 0;
    v14 = GetTickCount() - TickCount;
    if ( v46 != 255 )
      v8 = v46;
    LODWORD(v34) = v14;
    LODWORD(v33) = v14 % 0x3E8;
    LODWORD(v32) = v14 / 0x3E8 % 0x3C;
    LODWORD(lpcbData) = v14 / 0xEA60 % 0x3C;
    LODWORD(lpDataa) = v14 / 0x36EE80 % 0x3C;
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v37,
      L"EXIT",
      v8,
      L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
      lpDataa,
      lpcbData,
      v32,
      v33,
      v34,
      v38);
    VssSetTracingContextPerThread(v49);
    return 0;
  }
  else
  {
    if ( v12 && v12 != 234 )
    {
      v21 = cbData;
      v22 = Type;
      v23 = this[3];
      v24 = this[1];
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
      v50 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v51 = L"CVssRegistryKey::GetValue";
      v52 = L"REGREGSC";
      v53 = 426;
      v54 = 11;
      v55 = 255;
      v57 = 0x1000000;
      memset_0(v56, 0, sizeof(v56));
      LODWORD(v34) = v21;
      LODWORD(v33) = v22;
      CVssFunctionTracer::TranslateGenericError(
        &v37,
        &v50,
        v13,
        L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
        v24,
        v23,
        a2,
        v33,
        v34);
    }
    v16 = Type;
    if ( Type != 1 && Type != 2 )
    {
      v50 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v51 = L"CVssRegistryKey::GetValue";
      v52 = L"REGREGSC";
      v53 = 432;
      v54 = 11;
      v55 = 255;
      v57 = 0x1000000;
      memset_0(v56, 0, sizeof(v56));
      LODWORD(lpData) = v16;
      CVssFunctionTracer::TranslateGenericError(
        &v37,
        &v50,
        2147549183LL,
        L"Unexpected type %lu for a string value 0x%08lx(%s),%s",
        lpData,
        this[1],
        this[3],
        a2);
    }
    v58 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    v17 = cbData >> 1;
    v18 = (BYTE *)CoTaskMemAlloc(2 * v17 + 2);
    v59 = v18;
    if ( !v18 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v36 = 0;
    v61 = 2 * v17;
    v19 = RegQueryValueExW(this[1], a2, 0, &v36, v18, &v61);
    v20 = v19;
    if ( v19 )
    {
      v25 = v61;
      v26 = v36;
      v27 = this[3];
      v28 = this[1];
      if ( v19 > 0 )
        v20 = (unsigned __int16)v19 | 0x80070000;
      v50 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v51 = L"CVssRegistryKey::GetValue";
      v52 = L"REGREGSC";
      v53 = 453;
      v54 = 11;
      v55 = 255;
      v57 = 0x1000000;
      memset_0(v56, 0, sizeof(v56));
      LODWORD(v34) = v25;
      LODWORD(v33) = v26;
      CVssFunctionTracer::TranslateGenericError(
        &v37,
        &v50,
        v20,
        L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
        v28,
        v27,
        a2,
        v33,
        v34);
    }
    *(_WORD *)&v18[2 * v17] = 0;
    *a3 = v18;
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v37,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v37);
    return 1;
  }
}

```

## disassembly

```asm
0x140027690  mov     [rsp-8+arg_8], rbx
0x140027695  mov     byte ptr [rsp-8+Type], r9b
0x14002769a  push    rbp
0x14002769b  push    rsi
0x14002769c  push    rdi
0x14002769d  push    r12
0x14002769f  push    r13
0x1400276a1  push    r14
0x1400276a3  push    r15
0x1400276a5  lea     rbp, [rsp-90h]
0x1400276ad  sub     rsp, 190h
0x1400276b4  mov     rdi, r8
0x1400276b7  mov     r15, rdx
0x1400276ba  mov     rsi, rcx
0x1400276bd  lea     r12, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x1400276c4  mov     [rbp+0C0h+var_F0], r12
0x1400276c8  lea     rax, aCvssregistryke_5; "CVssRegistryKey::GetValue"
0x1400276cf  mov     [rbp+0C0h+var_E8], rax
0x1400276d3  lea     rax, aRegregsc; "REGREGSC"
0x1400276da  mov     [rbp+0C0h+var_E0], rax
0x1400276de  mov     [rbp+0C0h+var_D8], 18Ah
0x1400276e5  mov     [rbp+0C0h+var_D4], 0Bh
0x1400276ec  mov     [rbp+0C0h+var_D0], 0FFh
0x1400276f3  xor     r13d, r13d
0x1400276f6  mov     [rbp+0C0h+var_50], 1000000h
0x1400276fd  xor     edx, edx; Val
0x1400276ff  mov     r8d, 78h ; 'x'; Size
0x140027705  lea     rcx, [rbp+0C0h+var_C8]; void *
0x140027709  call    memset_0
0x14002770e  mov     [rsp+1C0h+var_158], r13d
0x140027713  mov     rax, [rbp+0C0h+var_E8]
0x140027717  mov     [rbp+0C0h+var_138], rax
0x14002771b  mov     rax, [rbp+0C0h+var_F0]
0x14002771f  mov     [rsp+1C0h+var_150], rax
0x140027724  mov     rax, [rbp+0C0h+var_E0]
0x140027728  mov     [rsp+1C0h+var_148], rax
0x14002772d  mov     eax, [rbp+0C0h+var_D8]
0x140027730  mov     [rbp+0C0h+var_140], eax
0x140027733  mov     eax, [rbp+0C0h+var_D4]
0x140027736  mov     [rbp+0C0h+var_13C], eax
0x140027739  call    cs:__imp_GetTickCount
0x14002773f  mov     [rbp+0C0h+var_12C], eax
0x140027742  mov     [rsp+1C0h+var_15C], 0FFFFFFFFh
0x14002774a  mov     eax, [rbp+0C0h+var_D0]
0x14002774d  mov     [rbp+0C0h+var_128], eax
0x140027750  mov     [rsp+1C0h+var_160], r13d
0x140027755  mov     [rbp+0C0h+var_100], r13
0x140027759  xorps   xmm0, xmm0
0x14002775c  movdqa  xmmword ptr [rbp+0C0h+pv], xmm0
0x140027761  xorps   xmm1, xmm1
0x140027764  movdqa  xmmword ptr [rbp+0C0h+var_110], xmm1
0x140027769  mov     [rsp+1C0h+pExceptionObject], r13
0x14002776e  lea     rcx, [rsp+1C0h+pExceptionObject]
0x140027773  call    cs:__imp_VssGetTracingContextPerThread
0x140027779  test    eax, eax
0x14002777b  jns     loc_14002797C
0x140027781  mov     rax, [rbp+0C0h+var_100]
0x140027785  test    rax, rax
0x140027788  jz      loc_140027A6F
0x14002778e  mov     eax, [rax+30h]
0x140027791  inc     eax
0x140027793  mov     [rbp+0C0h+var_130], eax
0x140027796  mov     r14d, 0A0h
0x14002779c  mov     ebx, r14d
0x14002779f  cmp     [rbp+0C0h+var_128], 0FFh
0x1400277a6  cmovnz  ebx, [rbp+0C0h+var_128]
0x1400277aa  mov     edx, [rbp+0C0h+var_13C]; unsigned int
0x1400277ad  lea     rcx, [rsp+1C0h+var_160]; this
0x1400277b2  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x1400277b7  test    eax, eax
0x1400277b9  jnz     loc_140027BB6
0x1400277bf  cmp     byte ptr [rbp+0C0h+var_50+3], r13b
0x1400277c3  jz      short loc_1400277E7
0x1400277c5  mov     rbx, r13
0x1400277c8  nop     dword ptr [rax+rax+00000000h]
0x1400277d0  mov     rcx, [rbp+rbx*8+0C0h+var_C8]; pv
0x1400277d5  test    rcx, rcx
0x1400277d8  jnz     loc_14002796C
0x1400277de  inc     rbx
0x1400277e1  cmp     rbx, 0Fh
0x1400277e5  jnz     short loc_1400277D0
0x1400277e7  mov     [rdi], r13
0x1400277ea  mov     [rbp+0C0h+Type], r13d
0x1400277f1  mov     [rbp+0C0h+cbData], r13d
0x1400277f8  lea     rax, [rbp+0C0h+cbData]
0x1400277ff  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x140027804  mov     [rsp+1C0h+lpData], r13; lpData
0x140027809  lea     r9, [rbp+0C0h+Type]; lpType
0x140027810  xor     r8d, r8d; lpReserved
0x140027813  mov     rdx, r15; lpValueName
0x140027816  mov     rcx, [rsi+8]; hKey
0x14002781a  call    cs:__imp_RegQueryValueExW
0x140027820  mov     ebx, eax
0x140027822  cmp     eax, 2
0x140027825  jnz     loc_14002799D
0x14002782b  lea     rax, aFalse; "FALSE"
0x140027832  mov     [rsp+1C0h+lpData], rax
0x140027837  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x14002783e  mov     r8d, 0AAh; unsigned int
0x140027844  lea     rdx, aReturn; "RETURN"
0x14002784b  lea     rcx, [rsp+1C0h+var_160]; this
0x140027850  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140027855  nop
0x140027856  mov     rcx, [rbp+0C0h+pv]; pv
0x14002785a  call    cs:__imp_CoTaskMemFree
0x140027860  mov     [rbp+0C0h+pv], r13
0x140027864  mov     rcx, [rbp+0C0h+pv+8]; pv
0x140027868  call    cs:__imp_CoTaskMemFree
0x14002786e  mov     [rbp+0C0h+pv+8], r13
0x140027872  mov     rcx, [rbp+0C0h+var_110]; pv
0x140027876  call    cs:__imp_CoTaskMemFree
0x14002787c  mov     [rbp+0C0h+var_110], r13
0x140027880  mov     rcx, [rbp+0C0h+var_110+8]; pv
0x140027884  call    cs:__imp_CoTaskMemFree
0x14002788a  mov     [rbp+0C0h+var_110+8], r13
0x14002788e  call    cs:__imp_GetTickCount
0x140027894  mov     esi, eax
0x140027896  sub     esi, [rbp+0C0h+var_12C]
0x140027899  mov     eax, 10624DD3h
0x14002789e  mul     esi
0x1400278a0  mov     edi, edx
0x1400278a2  shr     edi, 6
0x1400278a5  mov     eax, 88888889h
0x1400278aa  mul     edi
0x1400278ac  shr     edx, 5
0x1400278af  imul    ecx, edx, 3Ch ; '<'
0x1400278b2  mov     ebx, edi
0x1400278b4  sub     ebx, ecx
0x1400278b6  mov     eax, 45E7B273h
0x1400278bb  mul     esi
0x1400278bd  mov     r11d, edx
0x1400278c0  shr     r11d, 0Eh
0x1400278c4  mov     eax, 88888889h
0x1400278c9  mul     r11d
0x1400278cc  shr     edx, 5
0x1400278cf  imul    ecx, edx, 3Ch ; '<'
0x1400278d2  sub     r11d, ecx
0x1400278d5  mov     eax, 95217CB1h
0x1400278da  mul     esi
0x1400278dc  mov     r10d, edx
0x1400278df  shr     r10d, 15h
0x1400278e3  mov     eax, 88888889h
0x1400278e8  mul     r10d
0x1400278eb  shr     edx, 5
0x1400278ee  imul    eax, edx, 3Ch ; '<'
0x1400278f1  sub     r10d, eax
0x1400278f4  mov     r9d, [rsp+1C0h+var_158]
0x1400278f9  cmp     [rbp+0C0h+var_128], 0FFh
0x140027900  cmovnz  r14d, [rbp+0C0h+var_128]
0x140027905  imul    eax, edi, 3E8h
0x14002790b  mov     ecx, esi
0x14002790d  sub     ecx, eax
0x14002790f  mov     [rsp+1C0h+var_178], r9d
0x140027914  mov     dword ptr [rsp+1C0h+var_180], esi
0x140027918  mov     dword ptr [rsp+1C0h+var_188], ecx
0x14002791c  mov     dword ptr [rsp+1C0h+var_190], ebx
0x140027920  mov     dword ptr [rsp+1C0h+lpcbData], r11d
0x140027925  mov     dword ptr [rsp+1C0h+lpData], r10d
0x14002792a  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140027931  mov     r8d, r14d; unsigned int
0x140027934  lea     rdx, aExit; "EXIT"
0x14002793b  lea     rcx, [rsp+1C0h+var_160]; this
0x140027940  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140027945  mov     rcx, [rbp+0C0h+var_100]
0x140027949  call    cs:__imp_VssSetTracingContextPerThread
0x14002794f  xor     al, al
0x140027951  mov     rbx, [rsp+1C0h+arg_8]
0x140027959  add     rsp, 190h
0x140027960  pop     r15
0x140027962  pop     r14
0x140027964  pop     r13
0x140027966  pop     r12
0x140027968  pop     rdi
0x140027969  pop     rsi
0x14002796a  pop     rbp
0x14002796b  retn
0x14002796c  call    cs:__imp_CoTaskMemFree
0x140027972  mov     [rbp+rbx*8+0C0h+var_C8], r13
0x140027977  jmp     loc_1400277DE
0x14002797c  lea     rcx, [rsp+1C0h+var_160]
0x140027981  call    cs:__imp_VssSetTracingContextPerThread
0x140027987  test    eax, eax
0x140027989  js      loc_140027781
0x14002798f  mov     rax, [rsp+1C0h+pExceptionObject]
0x140027994  mov     [rbp+0C0h+var_100], rax
0x140027998  jmp     loc_140027785
0x14002799d  test    eax, eax
0x14002799f  jnz     loc_140027BF8
0x1400279a5  mov     ebx, [rbp+0C0h+Type]
0x1400279ab  cmp     ebx, 1
0x1400279ae  jnz     loc_140027C08
0x1400279b4  lea     rax, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x1400279bb  mov     [rbp+0C0h+var_48], rax
0x1400279bf  mov     eax, [rbp+0C0h+cbData]
0x1400279c5  shr     eax, 1
0x1400279c7  mov     r14d, eax
0x1400279ca  lea     rcx, ds:2[rax*2]; cb
0x1400279d2  call    cs:__imp_CoTaskMemAlloc
0x1400279d8  mov     rbx, rax
0x1400279db  mov     [rbp+0C0h+var_40], rax
0x1400279e2  test    rax, rax
0x1400279e5  jz      loc_140027C8F
0x1400279eb  mov     [rsp+1C0h+var_168], r13d
0x1400279f0  lea     eax, [r14+r14]
0x1400279f4  mov     [rbp+0C0h+arg_10], eax
0x1400279fa  lea     rax, [rbp+0C0h+arg_10]
0x140027a01  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x140027a06  mov     [rsp+1C0h+lpData], rbx; lpData
0x140027a0b  lea     r9, [rsp+1C0h+var_168]; lpType
0x140027a10  xor     r8d, r8d; lpReserved
0x140027a13  mov     rdx, r15; lpValueName
0x140027a16  mov     rcx, [rsi+8]; hKey
0x140027a1a  call    cs:__imp_RegQueryValueExW
0x140027a20  mov     r12d, eax
0x140027a23  test    eax, eax
0x140027a25  jnz     loc_140027B19
0x140027a2b  mov     [rbx+r14*2], r13w
0x140027a30  mov     [rdi], rbx
0x140027a33  lea     rax, aTrue; "TRUE"
0x140027a3a  mov     [rsp+1C0h+lpData], rax
0x140027a3f  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x140027a46  mov     r8d, 0AAh; unsigned int
0x140027a4c  lea     rdx, aReturn; "RETURN"
0x140027a53  lea     rcx, [rsp+1C0h+var_160]; this
0x140027a58  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140027a5d  nop
0x140027a5e  lea     rcx, [rsp+1C0h+var_160]; this
0x140027a63  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140027a68  mov     al, 1
0x140027a6a  jmp     loc_140027951
0x140027a6f  mov     [rbp+0C0h+var_130], r13d
0x140027a73  jmp     loc_140027796
0x140027a78  mov     edi, [rbp+0C0h+cbData]
0x140027a7e  mov     r14d, [rbp+0C0h+Type]
0x140027a85  mov     r12, [rsi+18h]
0x140027a89  mov     rsi, [rsi+8]
0x140027a8d  test    eax, eax
0x140027a8f  jle     short loc_140027A9A
0x140027a91  movzx   ebx, ax
0x140027a94  or      ebx, 80070000h
0x140027a9a  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x140027aa1  mov     [rbp+0C0h+var_F0], rax
0x140027aa5  lea     rax, aCvssregistryke_5; "CVssRegistryKey::GetValue"
0x140027aac  mov     [rbp+0C0h+var_E8], rax
0x140027ab0  lea     rax, aRegregsc; "REGREGSC"
0x140027ab7  mov     [rbp+0C0h+var_E0], rax
0x140027abb  mov     [rbp+0C0h+var_D8], 1AAh
0x140027ac2  mov     [rbp+0C0h+var_D4], 0Bh
0x140027ac9  mov     [rbp+0C0h+var_D0], 0FFh
0x140027ad0  mov     [rbp+0C0h+var_50], 1000000h
0x140027ad7  xor     edx, edx; Val
0x140027ad9  mov     r8d, 78h ; 'x'; Size
0x140027adf  lea     rcx, [rbp+0C0h+var_C8]; void *
0x140027ae3  call    memset_0
0x140027ae8  mov     dword ptr [rsp+1C0h+var_180], edi
0x140027aec  mov     dword ptr [rsp+1C0h+var_188], r14d
0x140027af1  mov     [rsp+1C0h+var_190], r15
0x140027af6  mov     [rsp+1C0h+lpcbData], r12
0x140027afb  mov     [rsp+1C0h+lpData], rsi
0x140027b00  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x140027b07  mov     r8d, ebx
0x140027b0a  lea     rdx, [rbp+0C0h+var_F0]
0x140027b0e  lea     rcx, [rsp+1C0h+var_160]
0x140027b13  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140027b19  mov     ebx, [rbp+0C0h+arg_10]
0x140027b1f  mov     edi, [rsp+1C0h+var_168]
0x140027b23  mov     r14, [rsi+18h]
0x140027b27  mov     rsi, [rsi+8]
0x140027b2b  jle     short loc_140027B38
0x140027b2d  movzx   r12d, ax
0x140027b31  or      r12d, 80070000h
0x140027b38  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x140027b3f  mov     [rbp+0C0h+var_F0], rax
0x140027b43  lea     rax, aCvssregistryke_5; "CVssRegistryKey::GetValue"
0x140027b4a  mov     [rbp+0C0h+var_E8], rax
0x140027b4e  lea     rax, aRegregsc; "REGREGSC"
0x140027b55  mov     [rbp+0C0h+var_E0], rax
0x140027b59  mov     [rbp+0C0h+var_D8], 1C5h
0x140027b60  mov     [rbp+0C0h+var_D4], 0Bh
0x140027b67  mov     [rbp+0C0h+var_D0], 0FFh
0x140027b6e  mov     [rbp+0C0h+var_50], 1000000h
0x140027b75  xor     edx, edx; Val
0x140027b77  mov     r8d, 78h ; 'x'; Size
0x140027b7d  lea     rcx, [rbp+0C0h+var_C8]; void *
0x140027b81  call    memset_0
0x140027b86  mov     dword ptr [rsp+1C0h+var_180], ebx
0x140027b8a  mov     dword ptr [rsp+1C0h+var_188], edi
0x140027b8e  mov     [rsp+1C0h+var_190], r15
0x140027b93  mov     [rsp+1C0h+lpcbData], r14
0x140027b98  mov     [rsp+1C0h+lpData], rsi
0x140027b9d  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x140027ba4  mov     r8d, r12d
0x140027ba7  lea     rdx, [rbp+0C0h+var_F0]
0x140027bab  lea     rcx, [rsp+1C0h+var_160]
0x140027bb0  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140027bb6  mov     [rsp+1C0h+var_180], r13
0x140027bbb  mov     dword ptr [rsp+1C0h+var_188], ebx
0x140027bbf  lea     rax, aEnter; "ENTER"
0x140027bc6  mov     [rsp+1C0h+var_190], rax
0x140027bcb  mov     rax, [rbp+0C0h+var_138]
  ... truncated ...
```

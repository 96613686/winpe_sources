# CVssRegistryKey::GetValue(ushort const *,ulong &,bool)

- ea: `0x14003a3fc`
- end: `0x14003a8e3`
- name: `?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAK_N@Z`
- size: `1255`
- prototype: `bool(CVssRegistryKey *__hidden this, const unsigned __int16 *, unsigned int *, bool)`
- caller_count: `8`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000fba0`
- `0x140028d60`
- `0x140042688`
- `0x140055bec`
- `0x1400965c0`
- `0x1400a57d4`
- `0x1400b7c08`
- `0x1400bf05c`

## callees

- `0x140011a90`
- `0x1400137c0`
- `0x1400138e0`
- `0x140013cb0`
- `0x14003a3fc`
- `0x140049ec4`
- `0x1400921dc`
- `0x1400cda78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003a5c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003a7f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003a5c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003a7f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003a4aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003a4aa`
- `VssTrace!__imp_VssTraceMessage` at `0x14003a569`
- `VssTrace!__imp_VssTraceMessage` at `0x14003a569`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003a4eb`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003a4eb`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003a4dd`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003a4dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003a582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003a582`

## string_xrefs

- `0x14003a426`: `base\stor\vss\modules\registry\registry.cxx`
- `0x14003a63d`: `base\stor\vss\modules\registry\registry.cxx`
- `0x14003a826`: `base\stor\vss\modules\registry\registry.cxx`
- `0x14003a432`: `CVssRegistryKey::GetValue`
- `0x14003a649`: `CVssRegistryKey::GetValue`
- `0x14003a6ce`: `CVssRegistryKey::GetValue`
- `0x14003a745`: `CVssRegistryKey::GetValue`
- `0x14003a832`: `CVssRegistryKey::GetValue`
- `0x14003a719`: `Expected REG_DWORD type for registry key %s value name %s. The present value has been ignored`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CVssRegistryKey::GetValue(HKEY *this, const unsigned __int16 *a2, unsigned int *a3, char a4)
{
  int v7; // eax
  __int64 v8; // rcx
  int v9; // ebx
  __int64 i; // rbx
  void *v11; // rcx
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  bool v14; // bl
  DWORD v15; // r14d
  DWORD v16; // r15d
  HKEY v17; // r12
  HKEY v18; // rdi
  bool v19; // dl
  DWORD v20; // ebx
  LSTATUS v21; // eax
  unsigned int v22; // ebx
  DWORD v23; // r14d
  DWORD v24; // r15d
  HKEY v25; // r12
  HKEY v26; // rdi
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+38h] [rbp-C8h]
  __int64 v30; // [rsp+40h] [rbp-C0h]
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v32; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  const unsigned __int16 *v34; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v35; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v36; // [rsp+70h] [rbp-90h]
  int v37; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+7Ch] [rbp-84h]
  int v39; // [rsp+80h] [rbp-80h]
  LPVOID pv[15]; // [rsp+88h] [rbp-78h] BYREF
  int v41; // [rsp+100h] [rbp+0h]
  unsigned __int64 v42; // [rsp+110h] [rbp+10h] BYREF
  int v43; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v44; // [rsp+120h] [rbp+20h]
  const unsigned __int16 *v45; // [rsp+128h] [rbp+28h]
  unsigned int v46; // [rsp+130h] [rbp+30h]
  int v47; // [rsp+134h] [rbp+34h]
  const wchar_t *v48; // [rsp+138h] [rbp+38h]
  unsigned int v49; // [rsp+140h] [rbp+40h]
  DWORD TickCount; // [rsp+144h] [rbp+44h]
  int v51; // [rsp+148h] [rbp+48h]
  __int128 v52; // [rsp+150h] [rbp+50h]
  __int128 v53; // [rsp+160h] [rbp+60h]
  __int64 v54; // [rsp+170h] [rbp+70h]
  DWORD cbData; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD lpcbData; // [rsp+1D0h] [rbp+D0h] BYREF
  DWORD Type; // [rsp+1D8h] [rbp+D8h] BYREF

  LOBYTE(Type) = a4;
  v34 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v35 = L"CVssRegistryKey::GetValue";
  v36 = L"REGREGSC";
  v37 = 504;
  v38 = 11;
  v39 = 255;
  v41 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v43 = 0;
  v48 = L"CVssRegistryKey::GetValue";
  v44 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v45 = L"REGREGSC";
  v46 = 504;
  v47 = 11;
  TickCount = GetTickCount();
  v51 = 255;
  v42 = 0xFFFFFFFF00000000uLL;
  v54 = 0;
  v52 = 0;
  v53 = 0;
  v31 = 0;
  if ( (int)VssGetTracingContextPerThread(&v31) < 0 )
  {
    v8 = v54;
  }
  else
  {
    v7 = VssSetTracingContextPerThread(&v42);
    v8 = v54;
    if ( v7 >= 0 )
      v8 = v31;
    v54 = v8;
  }
  if ( v8 )
    v49 = *(_DWORD *)(v8 + 48) + 1;
  else
    v49 = 0;
  v9 = 160;
  if ( v51 != 255 )
    v9 = v51;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v42) )
    VssTraceMessage(v44, v45, v46, v49, v47, v48, L"ENTER", v9, 0);
  if ( HIBYTE(v41) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v11 = pv[i];
      if ( v11 )
      {
        CoTaskMemFree(v11);
        pv[i] = 0;
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
      (CVssFunctionTracer *)&v42,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    v14 = 0;
  }
  else
  {
    if ( v12 && v12 != 234 )
    {
      v15 = cbData;
      v16 = Type;
      v17 = this[3];
      v18 = this[1];
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
      v34 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v35 = L"CVssRegistryKey::GetValue";
      v36 = L"REGREGSC";
      v37 = 535;
      v38 = 11;
      v39 = 255;
      v41 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      LODWORD(v30) = v15;
      LODWORD(v29) = v16;
      CVssFunctionTracer::TranslateGenericError(
        &v42,
        &v34,
        v13,
        L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
        v18,
        v17,
        a2,
        v29,
        v30);
    }
    if ( Type == 4 )
    {
      v20 = cbData;
      if ( cbData != 4 )
      {
        v34 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
        v35 = L"CVssRegistryKey::GetValue";
        v36 = L"REGREGSC";
        v37 = 555;
        v38 = 11;
        v39 = 255;
        v41 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        LODWORD(lpData) = v20;
        CVssFunctionTracer::TranslateGenericError(
          &v42,
          &v34,
          2147549183LL,
          L"Unexpected size %lu for a DWORD value 0x%08lx(%s),%s",
          lpData,
          this[1],
          this[3],
          a2);
      }
      v32 = 0;
      lpcbData = 4;
      *(_DWORD *)Data = 0;
      v21 = RegQueryValueExW(this[1], a2, 0, &v32, Data, &lpcbData);
      v22 = v21;
      if ( v21 )
      {
        v23 = lpcbData;
        v24 = v32;
        v25 = this[3];
        v26 = this[1];
        if ( v21 > 0 )
          v22 = (unsigned __int16)v21 | 0x80070000;
        v34 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
        v35 = L"CVssRegistryKey::GetValue";
        v36 = L"REGREGSC";
        v37 = 570;
        v38 = 11;
        v39 = 255;
        v41 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        LODWORD(v30) = v23;
        LODWORD(v29) = v24;
        CVssFunctionTracer::TranslateGenericError(
          &v42,
          &v34,
          v22,
          L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
          v26,
          v25,
          a2,
          v29,
          v30);
      }
      *a3 = *(_DWORD *)Data;
      v19 = 1;
    }
    else
    {
      v34 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v35 = L"CVssRegistryKey::GetValue";
      v36 = L"REGREGSC";
      v37 = 542;
      v38 = 11;
      v39 = 255;
      v41 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      CVssFunctionTracer::LogGenericWarning(
        &v42,
        &v34,
        L"Expected REG_DWORD type for registry key %s value name %s. The present value has been ignored",
        this[3],
        a2);
      v19 = 0;
    }
    v14 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v42, v19);
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v42);
  return v14;
}

```

## disassembly

```asm
0x14003a3fc  mov     [rsp-8+arg_8], rbx
0x14003a401  mov     byte ptr [rsp-8+Type], r9b
0x14003a406  push    rbp
0x14003a407  push    rsi
0x14003a408  push    rdi
0x14003a409  push    r12
0x14003a40b  push    r13
0x14003a40d  push    r14
0x14003a40f  push    r15
0x14003a411  lea     rbp, [rsp-80h]
0x14003a416  sub     rsp, 180h
0x14003a41d  mov     r14, r8
0x14003a420  mov     rsi, rdx
0x14003a423  mov     rdi, rcx
0x14003a426  lea     r12, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14003a42d  mov     [rsp+1B0h+var_150], r12
0x14003a432  lea     rax, aCvssregistryke_5; "CVssRegistryKey::GetValue"
0x14003a439  mov     [rsp+1B0h+var_148], rax
0x14003a43e  lea     rax, aRegregsc; "REGREGSC"
0x14003a445  mov     [rsp+1B0h+var_140], rax
0x14003a44a  mov     [rsp+1B0h+var_138], 1F8h
0x14003a452  mov     [rsp+1B0h+var_134], 0Bh
0x14003a45a  mov     r15d, 0FFh
0x14003a460  mov     [rbp+0B0h+var_130], r15d
0x14003a464  xor     r13d, r13d
0x14003a467  mov     [rbp+0B0h+var_B0], 1000000h
0x14003a46e  xor     edx, edx; Val
0x14003a470  lea     r8d, [r13+78h]; Size
0x14003a474  lea     rcx, [rbp+0B0h+pv]; void *
0x14003a478  call    memset_0
0x14003a47d  mov     [rbp+0B0h+var_98], r13d
0x14003a481  mov     rax, [rsp+1B0h+var_148]
0x14003a486  mov     [rbp+0B0h+var_78], rax
0x14003a48a  mov     rax, [rsp+1B0h+var_150]
0x14003a48f  mov     [rbp+0B0h+var_90], rax
0x14003a493  mov     rax, [rsp+1B0h+var_140]
0x14003a498  mov     [rbp+0B0h+var_88], rax
0x14003a49c  mov     eax, [rsp+1B0h+var_138]
0x14003a4a0  mov     [rbp+0B0h+var_80], eax
0x14003a4a3  mov     eax, [rsp+1B0h+var_134]
0x14003a4a7  mov     [rbp+0B0h+var_7C], eax
0x14003a4aa  call    cs:__imp_GetTickCount
0x14003a4b0  mov     [rbp+0B0h+var_6C], eax
0x14003a4b3  mov     [rbp+0B0h+var_9C], 0FFFFFFFFh
0x14003a4ba  mov     eax, [rbp+0B0h+var_130]
0x14003a4bd  mov     [rbp+0B0h+var_68], eax
0x14003a4c0  mov     [rbp+0B0h+var_A0], r13d
0x14003a4c4  mov     [rbp+0B0h+var_40], r13
0x14003a4c8  xorps   xmm0, xmm0
0x14003a4cb  movups  [rbp+0B0h+var_60], xmm0
0x14003a4cf  movups  [rbp+0B0h+var_50], xmm0
0x14003a4d3  mov     [rsp+1B0h+var_160], r13
0x14003a4d8  lea     rcx, [rsp+1B0h+var_160]
0x14003a4dd  call    cs:__imp_VssGetTracingContextPerThread
0x14003a4e3  test    eax, eax
0x14003a4e5  js      short loc_14003A503
0x14003a4e7  lea     rcx, [rbp+0B0h+var_A0]
0x14003a4eb  call    cs:__imp_VssSetTracingContextPerThread
0x14003a4f1  mov     rcx, [rbp+0B0h+var_40]
0x14003a4f5  test    eax, eax
0x14003a4f7  cmovns  rcx, [rsp+1B0h+var_160]
0x14003a4fd  mov     [rbp+0B0h+var_40], rcx
0x14003a501  jmp     short loc_14003A507
0x14003a503  mov     rcx, [rbp+0B0h+var_40]
0x14003a507  test    rcx, rcx
0x14003a50a  jz      short loc_14003A516
0x14003a50c  mov     eax, [rcx+30h]
0x14003a50f  inc     eax
0x14003a511  mov     [rbp+0B0h+var_70], eax
0x14003a514  jmp     short loc_14003A51A
0x14003a516  mov     [rbp+0B0h+var_70], r13d
0x14003a51a  mov     ebx, 0A0h
0x14003a51f  cmp     [rbp+0B0h+var_68], r15d
0x14003a523  cmovnz  ebx, [rbp+0B0h+var_68]
0x14003a527  lea     rcx, [rbp+0B0h+var_A0]; this
0x14003a52b  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003a530  test    eax, eax
0x14003a532  jz      short loc_14003A56F
0x14003a534  mov     [rsp+1B0h+var_170], r13
0x14003a539  mov     dword ptr [rsp+1B0h+var_178], ebx
0x14003a53d  lea     rax, aEnter; "ENTER"
0x14003a544  mov     [rsp+1B0h+var_180], rax
0x14003a549  mov     rax, [rbp+0B0h+var_78]
0x14003a54d  mov     [rsp+1B0h+lpcbData], rax
0x14003a552  mov     eax, [rbp+0B0h+var_7C]
0x14003a555  mov     dword ptr [rsp+1B0h+lpData], eax
0x14003a559  mov     r9d, [rbp+0B0h+var_70]
0x14003a55d  mov     r8d, [rbp+0B0h+var_80]
0x14003a561  mov     rdx, [rbp+0B0h+var_88]
0x14003a565  mov     rcx, [rbp+0B0h+var_90]
0x14003a569  call    cs:__imp_VssTraceMessage
0x14003a56f  cmp     byte ptr [rbp+0B0h+var_B0+3], r13b
0x14003a573  jz      short loc_14003A596
0x14003a575  mov     rbx, r13
0x14003a578  mov     rcx, [rbp+rbx*8+0B0h+pv]; pv
0x14003a57d  test    rcx, rcx
0x14003a580  jz      short loc_14003A58D
0x14003a582  call    cs:__imp_CoTaskMemFree
0x14003a588  mov     [rbp+rbx*8+0B0h+pv], r13
0x14003a58d  inc     rbx
0x14003a590  cmp     rbx, 0Fh
0x14003a594  jnz     short loc_14003A578
0x14003a596  mov     [r14], r13d
0x14003a599  mov     [rbp+0B0h+Type], r13d
0x14003a5a0  mov     [rbp+0B0h+cbData], r13d
0x14003a5a7  lea     rax, [rbp+0B0h+cbData]
0x14003a5ae  mov     [rsp+1B0h+lpcbData], rax; lpcbData
0x14003a5b3  mov     [rsp+1B0h+lpData], r13; lpData
0x14003a5b8  lea     r9, [rbp+0B0h+Type]; lpType
0x14003a5bf  xor     r8d, r8d; lpReserved
0x14003a5c2  mov     rdx, rsi; lpValueName
0x14003a5c5  mov     rcx, [rdi+8]; hKey
0x14003a5c9  call    cs:__imp_RegQueryValueExW
0x14003a5cf  mov     ebx, eax
0x14003a5d1  cmp     eax, 2
0x14003a5d4  jnz     short loc_14003A607
0x14003a5d6  lea     rax, aFalse; "FALSE"
0x14003a5dd  mov     [rsp+1B0h+lpData], rax
0x14003a5e2  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x14003a5e9  mov     r8d, 0AAh; unsigned int
0x14003a5ef  lea     rdx, aReturn; "RETURN"
0x14003a5f6  lea     rcx, [rbp+0B0h+var_A0]; this
0x14003a5fa  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14003a5ff  mov     bl, r13b
0x14003a602  jmp     loc_14003A8BD
0x14003a607  test    eax, eax
0x14003a609  jz      loc_14003A6C0
0x14003a60f  cmp     eax, 0EAh
0x14003a614  jz      loc_14003A6C0
0x14003a61a  mov     r14d, [rbp+0B0h+cbData]
0x14003a621  mov     r15d, [rbp+0B0h+Type]
0x14003a628  mov     r12, [rdi+18h]
0x14003a62c  mov     rdi, [rdi+8]
0x14003a630  test    eax, eax
0x14003a632  jle     short loc_14003A63D
0x14003a634  movzx   ebx, ax
0x14003a637  or      ebx, 80070000h
0x14003a63d  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14003a644  mov     [rsp+1B0h+var_150], rax
0x14003a649  lea     rax, aCvssregistryke_5; "CVssRegistryKey::GetValue"
0x14003a650  mov     [rsp+1B0h+var_148], rax
0x14003a655  lea     rax, aRegregsc; "REGREGSC"
0x14003a65c  mov     [rsp+1B0h+var_140], rax
0x14003a661  mov     [rsp+1B0h+var_138], 217h
0x14003a669  mov     [rsp+1B0h+var_134], 0Bh
0x14003a671  mov     [rbp+0B0h+var_130], 0FFh
0x14003a678  mov     [rbp+0B0h+var_B0], 1000000h
0x14003a67f  xor     edx, edx; Val
0x14003a681  lea     r8d, [rdx+78h]; Size
0x14003a685  lea     rcx, [rbp+0B0h+pv]; void *
0x14003a689  call    memset_0
0x14003a68e  mov     dword ptr [rsp+1B0h+var_170], r14d
0x14003a693  mov     dword ptr [rsp+1B0h+var_178], r15d
0x14003a698  mov     [rsp+1B0h+var_180], rsi
0x14003a69d  mov     [rsp+1B0h+lpcbData], r12
0x14003a6a2  mov     [rsp+1B0h+lpData], rdi
0x14003a6a7  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x14003a6ae  mov     r8d, ebx
0x14003a6b1  lea     rdx, [rsp+1B0h+var_150]
0x14003a6b6  lea     rcx, [rbp+0B0h+var_A0]
0x14003a6ba  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14003a6c0  cmp     [rbp+0B0h+Type], 4
0x14003a6c7  jz      short loc_14003A735
0x14003a6c9  mov     [rsp+1B0h+var_150], r12
0x14003a6ce  lea     rax, aCvssregistryke_5; "CVssRegistryKey::GetValue"
0x14003a6d5  mov     [rsp+1B0h+var_148], rax
0x14003a6da  lea     rax, aRegregsc; "REGREGSC"
0x14003a6e1  mov     [rsp+1B0h+var_140], rax
0x14003a6e6  mov     [rsp+1B0h+var_138], 21Eh
0x14003a6ee  mov     [rsp+1B0h+var_134], 0Bh
0x14003a6f6  mov     [rbp+0B0h+var_130], r15d
0x14003a6fa  mov     [rbp+0B0h+var_B0], 1000000h
0x14003a701  xor     edx, edx; Val
0x14003a703  lea     r8d, [rdx+78h]; Size
0x14003a707  lea     rcx, [rbp+0B0h+pv]; void *
0x14003a70b  call    memset_0
0x14003a710  mov     [rsp+1B0h+lpData], rsi
0x14003a715  mov     r9, [rdi+18h]
0x14003a719  lea     r8, aExpectedRegDwo; "Expected REG_DWORD type for registry ke"...
0x14003a720  lea     rdx, [rsp+1B0h+var_150]
0x14003a725  lea     rcx, [rbp+0B0h+var_A0]
0x14003a729  call    ?LogGenericWarning@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::LogGenericWarning(CVssDebugInfo,ushort const *,...)
0x14003a72e  xor     edx, edx
0x14003a730  jmp     loc_14003A8B2
0x14003a735  mov     ebx, [rbp+0B0h+cbData]
0x14003a73b  cmp     ebx, 4
0x14003a73e  jz      short loc_14003A7BE
0x14003a740  mov     [rsp+1B0h+var_150], r12
0x14003a745  lea     rax, aCvssregistryke_5; "CVssRegistryKey::GetValue"
0x14003a74c  mov     [rsp+1B0h+var_148], rax
0x14003a751  lea     rax, aRegregsc; "REGREGSC"
0x14003a758  mov     [rsp+1B0h+var_140], rax
0x14003a75d  mov     [rsp+1B0h+var_138], 22Bh
0x14003a765  mov     [rsp+1B0h+var_134], 0Bh
0x14003a76d  mov     [rbp+0B0h+var_130], r15d
0x14003a771  mov     [rbp+0B0h+var_B0], 1000000h
0x14003a778  xor     edx, edx; Val
0x14003a77a  lea     r8d, [rdx+78h]; Size
0x14003a77e  lea     rcx, [rbp+0B0h+pv]; void *
0x14003a782  call    memset_0
0x14003a787  mov     [rsp+1B0h+var_178], rsi
0x14003a78c  mov     rax, [rdi+18h]
0x14003a790  mov     [rsp+1B0h+var_180], rax
0x14003a795  mov     rax, [rdi+8]
0x14003a799  mov     [rsp+1B0h+lpcbData], rax
0x14003a79e  mov     dword ptr [rsp+1B0h+lpData], ebx
0x14003a7a2  lea     r9, aUnexpectedSize; "Unexpected size %lu for a DWORD value 0"...
0x14003a7a9  mov     r8d, 8000FFFFh
0x14003a7af  lea     rdx, [rsp+1B0h+var_150]
0x14003a7b4  lea     rcx, [rbp+0B0h+var_A0]
0x14003a7b8  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14003a7be  mov     [rsp+1B0h+var_158], r13d
0x14003a7c3  mov     [rbp+0B0h+arg_10], 4
0x14003a7cd  mov     dword ptr [rsp+1B0h+Data], r13d
0x14003a7d2  lea     rax, [rbp+0B0h+arg_10]
0x14003a7d9  mov     [rsp+1B0h+lpcbData], rax; lpcbData
0x14003a7de  lea     rax, [rsp+1B0h+Data]
0x14003a7e3  mov     [rsp+1B0h+lpData], rax; lpData
0x14003a7e8  lea     r9, [rsp+1B0h+var_158]; lpType
0x14003a7ed  xor     r8d, r8d; lpReserved
0x14003a7f0  mov     rdx, rsi; lpValueName
0x14003a7f3  mov     rcx, [rdi+8]; hKey
0x14003a7f7  call    cs:__imp_RegQueryValueExW
0x14003a7fd  mov     ebx, eax
0x14003a7ff  test    eax, eax
0x14003a801  jz      loc_14003A8A9
0x14003a807  mov     r14d, [rbp+0B0h+arg_10]
0x14003a80e  mov     r15d, [rsp+1B0h+var_158]
0x14003a813  mov     r12, [rdi+18h]
0x14003a817  mov     rdi, [rdi+8]
0x14003a81b  jle     short loc_14003A826
0x14003a81d  movzx   ebx, ax
0x14003a820  or      ebx, 80070000h
0x14003a826  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14003a82d  mov     [rsp+1B0h+var_150], rax
0x14003a832  lea     rax, aCvssregistryke_5; "CVssRegistryKey::GetValue"
0x14003a839  mov     [rsp+1B0h+var_148], rax
0x14003a83e  lea     rax, aRegregsc; "REGREGSC"
0x14003a845  mov     [rsp+1B0h+var_140], rax
0x14003a84a  mov     [rsp+1B0h+var_138], 23Ah
0x14003a852  mov     [rsp+1B0h+var_134], 0Bh
0x14003a85a  mov     [rbp+0B0h+var_130], 0FFh
0x14003a861  mov     [rbp+0B0h+var_B0], 1000000h
0x14003a868  xor     edx, edx; Val
0x14003a86a  lea     r8d, [rdx+78h]; Size
0x14003a86e  lea     rcx, [rbp+0B0h+pv]; void *
0x14003a872  call    memset_0
0x14003a877  mov     dword ptr [rsp+1B0h+var_170], r14d
0x14003a87c  mov     dword ptr [rsp+1B0h+var_178], r15d
0x14003a881  mov     [rsp+1B0h+var_180], rsi
0x14003a886  mov     [rsp+1B0h+lpcbData], r12
0x14003a88b  mov     [rsp+1B0h+lpData], rdi
0x14003a890  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x14003a897  mov     r8d, ebx
0x14003a89a  lea     rdx, [rsp+1B0h+var_150]
0x14003a89f  lea     rcx, [rbp+0B0h+var_A0]
0x14003a8a3  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14003a8a9  mov     eax, dword ptr [rsp+1B0h+Data]
0x14003a8ad  mov     [r14], eax
0x14003a8b0  mov     dl, 1; bool
0x14003a8b2  lea     rcx, [rbp+0B0h+var_A0]; this
0x14003a8b6  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x14003a8bb  mov     bl, al
0x14003a8bd  lea     rcx, [rbp+0B0h+var_A0]; this
0x14003a8c1  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003a8c6  mov     al, bl
0x14003a8c8  mov     rbx, [rsp+1B0h+arg_8]
0x14003a8d0  add     rsp, 180h
0x14003a8d7  pop     r15
0x14003a8d9  pop     r14
0x14003a8db  pop     r13
0x14003a8dd  pop     r12
0x14003a8df  pop     rdi
0x14003a8e0  pop     rsi
0x14003a8e1  pop     rbp
0x14003a8e2  retn
```

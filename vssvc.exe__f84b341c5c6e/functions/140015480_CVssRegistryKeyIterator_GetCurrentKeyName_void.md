# CVssRegistryKeyIterator::GetCurrentKeyName(void)

- ea: `0x140015480`
- end: `0x140015949`
- name: `?GetCurrentKeyName@CVssRegistryKeyIterator@@QEAAPEAGXZ`
- size: `1225`
- prototype: `unsigned __int16 *__fastcall(CVssRegistryKeyIterator *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140015fb0`

## callees

- `0x1400138e0`
- `0x140013c60`
- `0x140015480`
- `0x140015e38`
- `0x140049ec4`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400156a5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400156a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140015528`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400156f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140015528`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400156f1`
- `VssTrace!__imp_VssTraceMessage` at `0x1400158c7`
- `VssTrace!__imp_VssTraceMessage` at `0x1400158c7`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400157ac`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400157d5`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400157ac`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400157d5`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140015567`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140015567`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001565b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400156bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400156cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400156d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400156e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001565b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400156bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400156cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400156d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400156e7`

## string_xrefs

- `0x1400154aa`: `CVssRegistryKeyIterator::GetCurrentKeyName`
- `0x14001581e`: `CVssRegistryKeyIterator::GetCurrentKeyName`
- `0x14001549f`: `base\stor\vss\modules\registry\registry.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall CVssRegistryKeyIterator::GetCurrentKeyName(CVssRegistryKeyIterator *this)
{
  __int64 v2; // rax
  unsigned int v3; // r15d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  WCHAR *v7; // r8
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r14
  DWORD v11; // esi
  DWORD v13; // edi
  __int64 v14; // rsi
  int v15; // r15d
  __int64 v16; // r14
  LPDWORD lpReserved; // [rsp+20h] [rbp-E0h]
  LPWSTR lpClass; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcchClass; // [rsp+30h] [rbp-D0h]
  PFILETIME lpftLastWriteTime; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  _DWORD v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v24; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v25; // [rsp+68h] [rbp-98h]
  unsigned int v26; // [rsp+70h] [rbp-90h]
  unsigned int v27; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v28; // [rsp+78h] [rbp-88h]
  unsigned int v29; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v31; // [rsp+88h] [rbp-78h]
  LPVOID v32[2]; // [rsp+90h] [rbp-70h]
  LPVOID v33[2]; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v35; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v36; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v37; // [rsp+D0h] [rbp-30h]
  int v38; // [rsp+D8h] [rbp-28h]
  int v39; // [rsp+DCh] [rbp-24h]
  int v40; // [rsp+E0h] [rbp-20h]
  LPVOID pv[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v42; // [rsp+F8h] [rbp-8h]
  __int128 v43; // [rsp+108h] [rbp+8h]
  __int128 v44; // [rsp+118h] [rbp+18h]
  __int128 v45; // [rsp+128h] [rbp+28h]
  __int128 v46; // [rsp+138h] [rbp+38h]
  __int128 v47; // [rsp+148h] [rbp+48h]
  __int64 v48; // [rsp+158h] [rbp+58h]
  int v49; // [rsp+160h] [rbp+60h]
  DWORD cchName; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v51; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+1C0h] [rbp+C0h] BYREF

  v35 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v36 = L"CVssRegistryKeyIterator::GetCurrentKeyName";
  v37 = L"REGREGSC";
  v38 = 719;
  v39 = 11;
  v40 = 255;
  v49 = 0x1000000;
  *(_OWORD *)pv = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v23 = 0;
  v28 = L"CVssRegistryKeyIterator::GetCurrentKeyName";
  v24 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v25 = L"REGREGSC";
  v26 = 719;
  v27 = 11;
  TickCount = GetTickCount();
  v22[1] = -1;
  v31 = 255;
  v22[0] = 0;
  v34 = 0;
  *(_OWORD *)v32 = 0;
  *(_OWORD *)v33 = 0;
  v51 = 0;
  if ( (int)VssGetTracingContextPerThread(&v51) < 0 || (int)VssSetTracingContextPerThread(v22) < 0 )
  {
    v2 = v34;
  }
  else
  {
    v2 = v51;
    v34 = v51;
  }
  if ( v2 )
    v29 = *(_DWORD *)(v2 + 48) + 1;
  else
    v29 = 0;
  v3 = 160;
  v4 = 160;
  if ( v31 != 255 )
    v4 = v31;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v22, v27) )
    VssTraceMessage(v24, v25, v26, v29, v27, v28, L"ENTER", v4, 0);
  for ( i = 0; i != 15; ++i )
  {
    v6 = pv[i];
    if ( v6 )
    {
      CoTaskMemFree(v6);
      pv[i] = 0;
    }
  }
  if ( !*((_BYTE *)this + 40) || (v7 = (WCHAR *)*((_QWORD *)this + 4)) == 0 )
  {
    v35 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v36 = L"CVssRegistryKeyIterator::GetCurrentKeyName";
    v37 = L"REGREGSC";
    v38 = 723;
    v39 = 11;
    v40 = 255;
    v49 = 0x1000000;
    *(_OWORD *)pv = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    CVssFunctionTracer::Throw(v22, &v35, 2147549183LL, L"Unexpected error: noninitialized iterator");
  }
  ftLastWriteTime = 0;
  cchName = *((_DWORD *)this + 4);
  v8 = RegEnumKeyExW(*(HKEY *)this, *((_DWORD *)this + 3), v7, &cchName, 0, 0, 0, &ftLastWriteTime);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 == 259 )
    {
      v35 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v36 = L"CVssRegistryKeyIterator::GetCurrentKeyName";
      v37 = L"REGREGSC";
      v38 = 748;
      v39 = 11;
      v40 = 255;
      v49 = 0x1000000;
      memset_0(pv, 0, 0x78u);
      LODWORD(lpClass) = *((_DWORD *)this + 2);
      LODWORD(lpReserved) = *((_DWORD *)this + 3);
      CVssFunctionTracer::TranslateGenericError(
        v22,
        &v35,
        2147549183LL,
        L"Unexpected error: dwIndex out of scope %lu %lu",
        lpReserved,
        lpClass);
    }
    v13 = cchName;
    v14 = *((_QWORD *)this + 4);
    v15 = *((_DWORD *)this + 3);
    v16 = *(_QWORD *)this;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    v35 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v36 = L"CVssRegistryKeyIterator::GetCurrentKeyName";
    v37 = L"REGREGSC";
    v38 = 744;
    v39 = 11;
    v40 = 255;
    v49 = 0x1000000;
    memset_0(pv, 0, 0x78u);
    LODWORD(lpftLastWriteTime) = v13;
    LODWORD(lpClass) = v15;
    CVssFunctionTracer::TranslateGenericError(
      v22,
      &v35,
      v9,
      L"RegEnumKeyExW(%p,%lu,%p,%lu ...)",
      v16,
      lpClass,
      v14,
      lpftLastWriteTime);
  }
  v10 = *((_QWORD *)this + 4);
  CoTaskMemFree(v32[0]);
  v32[0] = 0;
  CoTaskMemFree(v32[1]);
  v32[1] = 0;
  CoTaskMemFree(v33[0]);
  v33[0] = 0;
  CoTaskMemFree(v33[1]);
  v33[1] = 0;
  v11 = GetTickCount() - TickCount;
  if ( v31 != 255 )
    v3 = v31;
  LODWORD(v21) = v11;
  LODWORD(lpftLastWriteTime) = v11 % 0x3E8;
  LODWORD(lpcchClass) = v11 / 0x3E8 % 0x3C;
  LODWORD(lpClass) = v11 / 0xEA60 % 0x3C;
  LODWORD(lpReserved) = v11 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v22,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    lpReserved,
    lpClass,
    lpcchClass,
    lpftLastWriteTime,
    v21,
    v23);
  VssSetTracingContextPerThread(v34);
  return (unsigned __int16 *)v10;
}

```

## disassembly

```asm
0x140015480  mov     [rsp-8+arg_18], rbx
0x140015485  push    rbp
0x140015486  push    rsi
0x140015487  push    rdi
0x140015488  push    r12
0x14001548a  push    r13
0x14001548c  push    r14
0x14001548e  push    r15
0x140015490  lea     rbp, [rsp-70h]
0x140015495  sub     rsp, 170h
0x14001549c  mov     r14, rcx
0x14001549f  lea     r13, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x1400154a6  mov     [rbp+0A0h+var_E0], r13
0x1400154aa  lea     rsi, aCvssregistryke_4; "CVssRegistryKeyIterator::GetCurrentKeyN"...
0x1400154b1  mov     [rbp+0A0h+var_D8], rsi
0x1400154b5  lea     rcx, aRegregsc; "REGREGSC"
0x1400154bc  mov     [rbp+0A0h+var_D0], rcx
0x1400154c0  mov     [rbp+0A0h+var_C8], 2CFh
0x1400154c7  mov     [rbp+0A0h+var_C4], 0Bh
0x1400154ce  mov     [rbp+0A0h+var_C0], 0FFh
0x1400154d5  xor     r12d, r12d
0x1400154d8  mov     [rbp+0A0h+var_40], 1000000h
0x1400154df  xorps   xmm0, xmm0
0x1400154e2  xor     eax, eax
0x1400154e4  movups  xmmword ptr [rbp+0A0h+pv], xmm0
0x1400154e8  movups  [rbp+0A0h+var_A8], xmm0
0x1400154ec  movups  [rbp+0A0h+var_98], xmm0
0x1400154f0  movups  [rbp+0A0h+var_88], xmm0
0x1400154f4  movups  [rbp+0A0h+var_78], xmm0
0x1400154f8  movups  [rbp+0A0h+var_68], xmm0
0x1400154fc  movups  [rbp+0A0h+var_58], xmm0
0x140015500  mov     [rbp+0A0h+var_48], rax
0x140015504  mov     [rsp+1A0h+var_148], r12d
0x140015509  mov     [rsp+1A0h+var_128], rsi
0x14001550e  mov     [rsp+1A0h+var_140], r13
0x140015513  mov     [rsp+1A0h+var_138], rcx
0x140015518  mov     [rsp+1A0h+var_130], 2CFh
0x140015520  mov     [rsp+1A0h+var_12C], 0Bh
0x140015528  call    cs:__imp_GetTickCount
0x14001552e  mov     [rbp+0A0h+var_11C], eax
0x140015531  mov     [rsp+1A0h+var_14C], 0FFFFFFFFh
0x140015539  mov     [rbp+0A0h+var_118], 0FFh
0x140015540  mov     [rsp+1A0h+var_150], r12d
0x140015545  mov     [rbp+0A0h+var_F0], r12
0x140015549  xorps   xmm0, xmm0
0x14001554c  movdqa  xmmword ptr [rbp+0A0h+var_110], xmm0
0x140015551  xorps   xmm1, xmm1
0x140015554  movdqa  xmmword ptr [rbp+0A0h+var_100], xmm1
0x140015559  mov     [rbp+0A0h+arg_8], r12
0x140015560  lea     rcx, [rbp+0A0h+arg_8]
0x140015567  call    cs:__imp_VssGetTracingContextPerThread
0x14001556d  test    eax, eax
0x14001556f  jns     loc_1400157D0
0x140015575  mov     rax, [rbp+0A0h+var_F0]
0x140015579  test    rax, rax
0x14001557c  jz      loc_1400157F3
0x140015582  mov     eax, [rax+30h]
0x140015585  inc     eax
0x140015587  mov     [rbp+0A0h+var_120], eax
0x14001558a  mov     r15d, 0A0h
0x140015590  mov     ebx, r15d
0x140015593  cmp     [rbp+0A0h+var_118], 0FFh
0x14001559a  cmovnz  ebx, [rbp+0A0h+var_118]
0x14001559e  mov     edx, [rsp+1A0h+var_12C]; unsigned int
0x1400155a2  lea     rcx, [rsp+1A0h+var_150]; this
0x1400155a7  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x1400155ac  test    eax, eax
0x1400155ae  jnz     loc_14001588D
0x1400155b4  mov     rbx, r12
0x1400155b7  nop     word ptr [rax+rax+00000000h]
0x1400155c0  mov     rcx, [rbp+rbx*8+0A0h+pv]; pv
0x1400155c5  test    rcx, rcx
0x1400155c8  jnz     loc_14001565B
0x1400155ce  inc     rbx
0x1400155d1  cmp     rbx, 0Fh
0x1400155d5  jnz     short loc_1400155C0
0x1400155d7  cmp     byte ptr [r14+28h], 0
0x1400155dc  jz      short loc_1400155EB
0x1400155de  mov     r8, [r14+20h]; lpName
0x1400155e2  test    r8, r8
0x1400155e5  jnz     loc_14001566B
0x1400155eb  mov     [rbp+0A0h+var_E0], r13
0x1400155ef  mov     [rbp+0A0h+var_D8], rsi
0x1400155f3  lea     rax, aRegregsc; "REGREGSC"
0x1400155fa  mov     [rbp+0A0h+var_D0], rax
0x1400155fe  mov     [rbp+0A0h+var_C8], 2D3h
0x140015605  mov     [rbp+0A0h+var_C4], 0Bh
0x14001560c  mov     [rbp+0A0h+var_C0], 0FFh
0x140015613  mov     [rbp+0A0h+var_40], 1000000h
0x14001561a  xorps   xmm0, xmm0
0x14001561d  xor     eax, eax
0x14001561f  movups  xmmword ptr [rbp+0A0h+pv], xmm0
0x140015623  movups  [rbp+0A0h+var_A8], xmm0
0x140015627  movups  [rbp+0A0h+var_98], xmm0
0x14001562b  movups  [rbp+0A0h+var_88], xmm0
0x14001562f  movups  [rbp+0A0h+var_78], xmm0
0x140015633  movups  [rbp+0A0h+var_68], xmm0
0x140015637  movups  [rbp+0A0h+var_58], xmm0
0x14001563b  mov     [rbp+0A0h+var_48], rax
0x14001563f  lea     r9, aUnexpectedErro_10; "Unexpected error: noninitialized iterat"...
0x140015646  mov     r8d, 8000FFFFh
0x14001564c  lea     rdx, [rbp+0A0h+var_E0]
0x140015650  lea     rcx, [rsp+1A0h+var_150]
0x140015655  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14001565b  call    cs:__imp_CoTaskMemFree
0x140015661  mov     [rbp+rbx*8+0A0h+pv], r12
0x140015666  jmp     loc_1400155CE
0x14001566b  mov     qword ptr [rbp+0A0h+ftLastWriteTime.dwLowDateTime], r12
0x140015672  mov     eax, [r14+10h]
0x140015676  mov     [rbp+0A0h+cchName], eax
0x14001567c  lea     rax, [rbp+0A0h+ftLastWriteTime]
0x140015683  mov     [rsp+1A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140015688  mov     [rsp+1A0h+lpcchClass], r12; lpcchClass
0x14001568d  mov     [rsp+1A0h+lpClass], r12; lpClass
0x140015692  mov     [rsp+1A0h+lpReserved], r12; lpReserved
0x140015697  lea     r9, [rbp+0A0h+cchName]; lpcchName
0x14001569e  mov     edx, [r14+0Ch]; dwIndex
0x1400156a2  mov     rcx, [r14]; hKey
0x1400156a5  call    cs:__imp_RegEnumKeyExW
0x1400156ab  mov     ebx, eax
0x1400156ad  test    eax, eax
0x1400156af  jnz     loc_1400158D2
0x1400156b5  mov     r14, [r14+20h]
0x1400156b9  mov     rcx, [rbp+0A0h+var_110]; pv
0x1400156bd  call    cs:__imp_CoTaskMemFree
0x1400156c3  mov     [rbp+0A0h+var_110], r12
0x1400156c7  mov     rcx, [rbp+0A0h+var_110+8]; pv
0x1400156cb  call    cs:__imp_CoTaskMemFree
0x1400156d1  mov     [rbp+0A0h+var_110+8], r12
0x1400156d5  mov     rcx, [rbp+0A0h+var_100]; pv
0x1400156d9  call    cs:__imp_CoTaskMemFree
0x1400156df  mov     [rbp+0A0h+var_100], r12
0x1400156e3  mov     rcx, [rbp+0A0h+var_100+8]; pv
0x1400156e7  call    cs:__imp_CoTaskMemFree
0x1400156ed  mov     [rbp+0A0h+var_100+8], r12
0x1400156f1  call    cs:__imp_GetTickCount
0x1400156f7  mov     esi, eax
0x1400156f9  sub     esi, [rbp+0A0h+var_11C]
0x1400156fc  mov     eax, 10624DD3h
0x140015701  mul     esi
0x140015703  mov     edi, edx
0x140015705  shr     edi, 6
0x140015708  mov     eax, 88888889h
0x14001570d  mul     edi
0x14001570f  shr     edx, 5
0x140015712  imul    ecx, edx, 3Ch ; '<'
0x140015715  mov     ebx, edi
0x140015717  sub     ebx, ecx
0x140015719  mov     eax, 45E7B273h
0x14001571e  mul     esi
0x140015720  mov     r11d, edx
0x140015723  shr     r11d, 0Eh
0x140015727  mov     eax, 88888889h
0x14001572c  mul     r11d
0x14001572f  shr     edx, 5
0x140015732  imul    ecx, edx, 3Ch ; '<'
0x140015735  sub     r11d, ecx
0x140015738  mov     eax, 95217CB1h
0x14001573d  mul     esi
0x14001573f  mov     r10d, edx
0x140015742  shr     r10d, 15h
0x140015746  mov     eax, 88888889h
0x14001574b  mul     r10d
0x14001574e  shr     edx, 5
0x140015751  imul    eax, edx, 3Ch ; '<'
0x140015754  sub     r10d, eax
0x140015757  mov     r9d, [rsp+1A0h+var_148]
0x14001575c  cmp     [rbp+0A0h+var_118], 0FFh
0x140015763  cmovnz  r15d, [rbp+0A0h+var_118]
0x140015768  imul    ecx, edi, 3E8h
0x14001576e  mov     edx, esi
0x140015770  sub     edx, ecx
0x140015772  mov     [rsp+1A0h+var_158], r9d
0x140015777  mov     dword ptr [rsp+1A0h+var_160], esi
0x14001577b  mov     dword ptr [rsp+1A0h+lpftLastWriteTime], edx
0x14001577f  mov     dword ptr [rsp+1A0h+lpcchClass], ebx
0x140015783  mov     dword ptr [rsp+1A0h+lpClass], r11d
0x140015788  mov     dword ptr [rsp+1A0h+lpReserved], r10d
0x14001578d  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140015794  mov     r8d, r15d; unsigned int
0x140015797  lea     rdx, aExit; "EXIT"
0x14001579e  lea     rcx, [rsp+1A0h+var_150]; this
0x1400157a3  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400157a8  mov     rcx, [rbp+0A0h+var_F0]
0x1400157ac  call    cs:__imp_VssSetTracingContextPerThread
0x1400157b2  mov     rax, r14
0x1400157b5  mov     rbx, [rsp+1A0h+arg_18]
0x1400157bd  add     rsp, 170h
0x1400157c4  pop     r15
0x1400157c6  pop     r14
0x1400157c8  pop     r13
0x1400157ca  pop     r12
0x1400157cc  pop     rdi
0x1400157cd  pop     rsi
0x1400157ce  pop     rbp
0x1400157cf  retn
0x1400157d0  lea     rcx, [rsp+1A0h+var_150]
0x1400157d5  call    cs:__imp_VssSetTracingContextPerThread
0x1400157db  test    eax, eax
0x1400157dd  js      loc_140015575
0x1400157e3  mov     rax, [rbp+0A0h+arg_8]
0x1400157ea  mov     [rbp+0A0h+var_F0], rax
0x1400157ee  jmp     loc_140015579
0x1400157f3  mov     [rbp+0A0h+var_120], r12d
0x1400157f7  jmp     loc_14001558A
0x1400157fc  mov     edi, [rbp+0A0h+cchName]
0x140015802  mov     rsi, [r14+20h]
0x140015806  mov     r15d, [r14+0Ch]
0x14001580a  mov     r14, [r14]
0x14001580d  test    eax, eax
0x14001580f  jle     short loc_14001581A
0x140015811  movzx   ebx, ax
0x140015814  or      ebx, 80070000h
0x14001581a  mov     [rbp+0A0h+var_E0], r13
0x14001581e  lea     rax, aCvssregistryke_4; "CVssRegistryKeyIterator::GetCurrentKeyN"...
0x140015825  mov     [rbp+0A0h+var_D8], rax
0x140015829  lea     rax, aRegregsc; "REGREGSC"
0x140015830  mov     [rbp+0A0h+var_D0], rax
0x140015834  mov     [rbp+0A0h+var_C8], 2E8h
0x14001583b  mov     [rbp+0A0h+var_C4], 0Bh
0x140015842  mov     [rbp+0A0h+var_C0], 0FFh
0x140015849  mov     [rbp+0A0h+var_40], 1000000h
0x140015850  xor     edx, edx; Val
0x140015852  mov     r8d, 78h ; 'x'; Size
0x140015858  lea     rcx, [rbp+0A0h+pv]; void *
0x14001585c  call    memset_0
0x140015861  mov     dword ptr [rsp+1A0h+lpftLastWriteTime], edi
0x140015865  mov     [rsp+1A0h+lpcchClass], rsi
0x14001586a  mov     dword ptr [rsp+1A0h+lpClass], r15d
0x14001586f  mov     [rsp+1A0h+lpReserved], r14
0x140015874  lea     r9, aRegenumkeyexwP; "RegEnumKeyExW(%p,%lu,%p,%lu ...)"
0x14001587b  mov     r8d, ebx
0x14001587e  lea     rdx, [rbp+0A0h+var_E0]
0x140015882  lea     rcx, [rsp+1A0h+var_150]
0x140015887  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14001588d  mov     [rsp+1A0h+var_160], r12
0x140015892  mov     dword ptr [rsp+1A0h+lpftLastWriteTime], ebx
0x140015896  lea     rax, aEnter; "ENTER"
0x14001589d  mov     [rsp+1A0h+lpcchClass], rax
0x1400158a2  mov     rax, [rsp+1A0h+var_128]
0x1400158a7  mov     [rsp+1A0h+lpClass], rax
0x1400158ac  mov     eax, [rsp+1A0h+var_12C]
0x1400158b0  mov     dword ptr [rsp+1A0h+lpReserved], eax
0x1400158b4  mov     r9d, [rbp+0A0h+var_120]
0x1400158b8  mov     r8d, [rsp+1A0h+var_130]
0x1400158bd  mov     rdx, [rsp+1A0h+var_138]
0x1400158c2  mov     rcx, [rsp+1A0h+var_140]
0x1400158c7  call    cs:__imp_VssTraceMessage
0x1400158cd  jmp     loc_1400155B4
0x1400158d2  cmp     eax, 103h
0x1400158d7  jnz     loc_1400157FC
0x1400158dd  mov     [rbp+0A0h+var_E0], r13
0x1400158e1  mov     [rbp+0A0h+var_D8], rsi
0x1400158e5  lea     rax, aRegregsc; "REGREGSC"
0x1400158ec  mov     [rbp+0A0h+var_D0], rax
0x1400158f0  mov     [rbp+0A0h+var_C8], 2ECh
0x1400158f7  mov     [rbp+0A0h+var_C4], 0Bh
0x1400158fe  mov     [rbp+0A0h+var_C0], 0FFh
0x140015905  mov     [rbp+0A0h+var_40], 1000000h
0x14001590c  xor     edx, edx; Val
0x14001590e  mov     r8d, 78h ; 'x'; Size
0x140015914  lea     rcx, [rbp+0A0h+pv]; void *
0x140015918  call    memset_0
0x14001591d  mov     eax, [r14+8]
0x140015921  mov     dword ptr [rsp+1A0h+lpClass], eax
0x140015925  mov     eax, [r14+0Ch]
0x140015929  mov     dword ptr [rsp+1A0h+lpReserved], eax
0x14001592d  lea     r9, aUnexpectedErro_11; "Unexpected error: dwIndex out of scope "...
0x140015934  mov     r8d, 8000FFFFh
0x14001593a  lea     rdx, [rbp+0A0h+var_E0]
0x14001593e  lea     rcx, [rsp+1A0h+var_150]
0x140015943  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```

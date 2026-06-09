# CVssRegistryValueIterator::ReadCurrentValueDetails(void)

- ea: `0x14000dcd0`
- end: `0x14000e182`
- name: `?ReadCurrentValueDetails@CVssRegistryValueIterator@@AEAAXXZ`
- size: `1202`
- prototype: `void __fastcall(CVssRegistryValueIterator *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000bc1c`
- `0x14000c0a0`
- `0x14000c2a0`
- `0x14000d9e0`
- `0x14003af90`

## callees

- `0x14000dcd0`
- `0x1400137c0`
- `0x1400138e0`
- `0x140013c60`
- `0x140049ec4`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000deda`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000deda`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000dd78`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000df26`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000dd78`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000df26`
- `VssTrace!__imp_VssTraceMessage` at `0x14000e102`
- `VssTrace!__imp_VssTraceMessage` at `0x14000e102`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000dfe1`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000e007`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000dfe1`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000e007`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000ddb7`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000ddb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000de8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000def2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000df00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000df0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000df1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000de8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000def2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000df00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000df0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000df1c`

## string_xrefs

- `0x14000dcfa`: `CVssRegistryValueIterator::ReadCurrentValueDetails`
- `0x14000e059`: `CVssRegistryValueIterator::ReadCurrentValueDetails`
- `0x14000dcef`: `base\stor\vss\modules\registry\registry.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssRegistryValueIterator::ReadCurrentValueDetails(CVssRegistryValueIterator *this)
{
  __int64 v2; // rax
  unsigned int v3; // r14d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  WCHAR *v7; // r8
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  DWORD v10; // esi
  DWORD v11; // r14d
  __int64 v12; // r15
  __int64 v13; // rdi
  int v14; // esi
  LPDWORD lpReserved; // [rsp+20h] [rbp-E0h]
  LPDWORD lpType; // [rsp+28h] [rbp-D8h]
  LPBYTE lpData; // [rsp+30h] [rbp-D0h]
  LPDWORD lpcbData; // [rsp+38h] [rbp-C8h]
  __int64 v19; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v22; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v23; // [rsp+68h] [rbp-98h]
  unsigned int v24; // [rsp+70h] [rbp-90h]
  unsigned int v25; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v26; // [rsp+78h] [rbp-88h]
  unsigned int v27; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v29; // [rsp+88h] [rbp-78h]
  LPVOID v30[2]; // [rsp+90h] [rbp-70h]
  LPVOID v31[2]; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v33; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v34; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v35; // [rsp+D0h] [rbp-30h]
  int v36; // [rsp+D8h] [rbp-28h]
  int v37; // [rsp+DCh] [rbp-24h]
  int v38; // [rsp+E0h] [rbp-20h]
  LPVOID pv[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v40; // [rsp+F8h] [rbp-8h]
  __int128 v41; // [rsp+108h] [rbp+8h]
  __int128 v42; // [rsp+118h] [rbp+18h]
  __int128 v43; // [rsp+128h] [rbp+28h]
  __int128 v44; // [rsp+138h] [rbp+38h]
  __int128 v45; // [rsp+148h] [rbp+48h]
  __int64 v46; // [rsp+158h] [rbp+58h]
  int v47; // [rsp+160h] [rbp+60h]
  DWORD cchValueName; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v49; // [rsp+1B8h] [rbp+B8h] BYREF

  v33 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v34 = L"CVssRegistryValueIterator::ReadCurrentValueDetails";
  v35 = L"REGREGSC";
  v36 = 1118;
  v37 = 11;
  v38 = 255;
  v47 = 0x1000000;
  *(_OWORD *)pv = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v21 = 0;
  v26 = L"CVssRegistryValueIterator::ReadCurrentValueDetails";
  v22 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v23 = L"REGREGSC";
  v24 = 1118;
  v25 = 11;
  TickCount = GetTickCount();
  v29 = 255;
  v20 = 0xFFFFFFFF00000000uLL;
  v32 = 0;
  *(_OWORD *)v30 = 0;
  *(_OWORD *)v31 = 0;
  v49 = 0;
  if ( (int)VssGetTracingContextPerThread(&v49) < 0 || (int)VssSetTracingContextPerThread(&v20) < 0 )
  {
    v2 = v32;
  }
  else
  {
    v2 = v49;
    v32 = v49;
  }
  if ( v2 )
    v27 = *(_DWORD *)(v2 + 48) + 1;
  else
    v27 = 0;
  v3 = 160;
  v4 = 160;
  if ( v29 != 255 )
    v4 = v29;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v20, v25) )
    VssTraceMessage(v22, v23, v24, v27, v25, v26, L"ENTER", v4, 0);
  for ( i = 0; i != 15; ++i )
  {
    v6 = pv[i];
    if ( v6 )
    {
      CoTaskMemFree(v6);
      pv[i] = 0;
    }
  }
  if ( !*((_BYTE *)this + 49) || (v7 = (WCHAR *)*((_QWORD *)this + 4)) == 0 )
  {
    v33 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v34 = L"CVssRegistryValueIterator::ReadCurrentValueDetails";
    v35 = L"REGREGSC";
    v36 = 1122;
    v37 = 11;
    v38 = 255;
    v47 = 0x1000000;
    memset_0(pv, 0, 0x78u);
    CVssFunctionTracer::TranslateGenericError(&v20, &v33, 2147549183LL, L"Unexpected error: noninitialized iterator");
  }
  if ( *((_BYTE *)this + 48) )
  {
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v20);
  }
  else
  {
    cchValueName = *((_DWORD *)this + 10);
    v8 = RegEnumValueW(
           *(HKEY *)this,
           *((_DWORD *)this + 3),
           v7,
           &cchValueName,
           0,
           (LPDWORD)this + 4,
           0,
           (LPDWORD)this + 11);
    v9 = v8;
    if ( v8 )
    {
      v14 = *((_DWORD *)this + 3);
      if ( v8 == 259 )
      {
        v33 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
        v34 = L"CVssRegistryValueIterator::ReadCurrentValueDetails";
        v35 = L"REGREGSC";
        v36 = 1150;
        v37 = 11;
        v38 = 255;
        v47 = 0x1000000;
        memset_0(pv, 0, 0x78u);
        LODWORD(lpType) = *((_DWORD *)this + 2);
        LODWORD(lpReserved) = v14;
        CVssFunctionTracer::TranslateGenericError(
          &v20,
          &v33,
          2147549183LL,
          L"Unexpected error: dwIndex out of scope %lu %lu",
          lpReserved,
          lpType);
      }
      v11 = cchValueName;
      v12 = *((_QWORD *)this + 4);
      v13 = *(_QWORD *)this;
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      v33 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v34 = L"CVssRegistryValueIterator::ReadCurrentValueDetails";
      v35 = L"REGREGSC";
      v36 = 1146;
      v37 = 11;
      v38 = 255;
      v47 = 0x1000000;
      memset_0(pv, 0, 0x78u);
      LODWORD(lpcbData) = v11;
      LODWORD(lpType) = v14;
      CVssFunctionTracer::TranslateGenericError(
        &v20,
        &v33,
        v9,
        L"RegEnumValue(%p,%lu,%p,%lu ...)",
        v13,
        lpType,
        v12,
        lpcbData);
    }
    *((_BYTE *)this + 48) = 1;
    CoTaskMemFree(v30[0]);
    v30[0] = 0;
    CoTaskMemFree(v30[1]);
    v30[1] = 0;
    CoTaskMemFree(v31[0]);
    v31[0] = 0;
    CoTaskMemFree(v31[1]);
    v31[1] = 0;
    v10 = GetTickCount() - TickCount;
    if ( v29 != 255 )
      v3 = v29;
    LODWORD(v19) = v10;
    LODWORD(lpcbData) = v10 % 0x3E8;
    LODWORD(lpData) = v10 / 0x3E8 % 0x3C;
    LODWORD(lpType) = v10 / 0xEA60 % 0x3C;
    LODWORD(lpReserved) = v10 / 0x36EE80 % 0x3C;
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v20,
      L"EXIT",
      v3,
      L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
      lpReserved,
      lpType,
      lpData,
      lpcbData,
      v19,
      v21);
    VssSetTracingContextPerThread(v32);
  }
}

```

## disassembly

```asm
0x14000dcd0  mov     [rsp-8+arg_10], rbx
0x14000dcd5  push    rbp
0x14000dcd6  push    rsi
0x14000dcd7  push    rdi
0x14000dcd8  push    r12
0x14000dcda  push    r13
0x14000dcdc  push    r14
0x14000dcde  push    r15
0x14000dce0  lea     rbp, [rsp-70h]
0x14000dce5  sub     rsp, 170h
0x14000dcec  mov     rdi, rcx
0x14000dcef  lea     r13, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000dcf6  mov     [rbp+0A0h+var_E0], r13
0x14000dcfa  lea     r15, aCvssregistryva; "CVssRegistryValueIterator::ReadCurrentV"...
0x14000dd01  mov     [rbp+0A0h+var_D8], r15
0x14000dd05  lea     rcx, aRegregsc; "REGREGSC"
0x14000dd0c  mov     [rbp+0A0h+var_D0], rcx
0x14000dd10  mov     [rbp+0A0h+var_C8], 45Eh
0x14000dd17  mov     [rbp+0A0h+var_C4], 0Bh
0x14000dd1e  mov     [rbp+0A0h+var_C0], 0FFh
0x14000dd25  xor     r12d, r12d
0x14000dd28  mov     [rbp+0A0h+var_40], 1000000h
0x14000dd2f  xorps   xmm0, xmm0
0x14000dd32  xor     eax, eax
0x14000dd34  movups  xmmword ptr [rbp+0A0h+pv], xmm0
0x14000dd38  movups  [rbp+0A0h+var_A8], xmm0
0x14000dd3c  movups  [rbp+0A0h+var_98], xmm0
0x14000dd40  movups  [rbp+0A0h+var_88], xmm0
0x14000dd44  movups  [rbp+0A0h+var_78], xmm0
0x14000dd48  movups  [rbp+0A0h+var_68], xmm0
0x14000dd4c  movups  [rbp+0A0h+var_58], xmm0
0x14000dd50  mov     [rbp+0A0h+var_48], rax
0x14000dd54  mov     [rsp+1A0h+var_148], r12d
0x14000dd59  mov     [rsp+1A0h+var_128], r15
0x14000dd5e  mov     [rsp+1A0h+var_140], r13
0x14000dd63  mov     [rsp+1A0h+var_138], rcx
0x14000dd68  mov     [rsp+1A0h+var_130], 45Eh
0x14000dd70  mov     [rsp+1A0h+var_12C], 0Bh
0x14000dd78  call    cs:__imp_GetTickCount
0x14000dd7e  mov     [rbp+0A0h+var_11C], eax
0x14000dd81  mov     [rsp+1A0h+var_14C], 0FFFFFFFFh
0x14000dd89  mov     [rbp+0A0h+var_118], 0FFh
0x14000dd90  mov     [rsp+1A0h+var_150], r12d
0x14000dd95  mov     [rbp+0A0h+var_F0], r12
0x14000dd99  xorps   xmm0, xmm0
0x14000dd9c  movdqa  xmmword ptr [rbp+0A0h+var_110], xmm0
0x14000dda1  xorps   xmm1, xmm1
0x14000dda4  movdqa  xmmword ptr [rbp+0A0h+var_100], xmm1
0x14000dda9  mov     [rbp+0A0h+arg_8], r12
0x14000ddb0  lea     rcx, [rbp+0A0h+arg_8]
0x14000ddb7  call    cs:__imp_VssGetTracingContextPerThread
0x14000ddbd  test    eax, eax
0x14000ddbf  jns     loc_14000E002
0x14000ddc5  mov     rax, [rbp+0A0h+var_F0]
0x14000ddc9  test    rax, rax
0x14000ddcc  jz      loc_14000E031
0x14000ddd2  mov     eax, [rax+30h]
0x14000ddd5  inc     eax
0x14000ddd7  mov     [rbp+0A0h+var_120], eax
0x14000ddda  mov     r14d, 0A0h
0x14000dde0  mov     ebx, r14d
0x14000dde3  cmp     [rbp+0A0h+var_118], 0FFh
0x14000ddea  cmovnz  ebx, [rbp+0A0h+var_118]
0x14000ddee  mov     edx, [rsp+1A0h+var_12C]; unsigned int
0x14000ddf2  lea     rcx, [rsp+1A0h+var_150]; this
0x14000ddf7  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14000ddfc  test    eax, eax
0x14000ddfe  jnz     loc_14000E0C8
0x14000de04  mov     rbx, r12
0x14000de07  nop     word ptr [rax+rax+00000000h]
0x14000de10  mov     rcx, [rbp+rbx*8+0A0h+pv]; pv
0x14000de15  test    rcx, rcx
0x14000de18  jnz     short loc_14000DE8E
0x14000de1a  inc     rbx
0x14000de1d  cmp     rbx, 0Fh
0x14000de21  jnz     short loc_14000DE10
0x14000de23  cmp     byte ptr [rdi+31h], 0
0x14000de27  jz      short loc_14000DE32
0x14000de29  mov     r8, [rdi+20h]; lpValueName
0x14000de2d  test    r8, r8
0x14000de30  jnz     short loc_14000DE9E
0x14000de32  mov     [rbp+0A0h+var_E0], r13
0x14000de36  mov     [rbp+0A0h+var_D8], r15
0x14000de3a  lea     rax, aRegregsc; "REGREGSC"
0x14000de41  mov     [rbp+0A0h+var_D0], rax
0x14000de45  mov     [rbp+0A0h+var_C8], 462h
0x14000de4c  mov     [rbp+0A0h+var_C4], 0Bh
0x14000de53  mov     [rbp+0A0h+var_C0], 0FFh
0x14000de5a  mov     [rbp+0A0h+var_40], 1000000h
0x14000de61  xor     edx, edx; Val
0x14000de63  mov     r8d, 78h ; 'x'; Size
0x14000de69  lea     rcx, [rbp+0A0h+pv]; void *
0x14000de6d  call    memset_0
0x14000de72  lea     r9, aUnexpectedErro_10; "Unexpected error: noninitialized iterat"...
0x14000de79  mov     r8d, 8000FFFFh
0x14000de7f  lea     rdx, [rbp+0A0h+var_E0]
0x14000de83  lea     rcx, [rsp+1A0h+var_150]
0x14000de88  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000de8e  call    cs:__imp_CoTaskMemFree
0x14000de94  mov     [rbp+rbx*8+0A0h+pv], r12
0x14000de99  jmp     loc_14000DE1A
0x14000de9e  cmp     byte ptr [rdi+30h], 0
0x14000dea2  jnz     loc_14000E025
0x14000dea8  mov     eax, [rdi+28h]
0x14000deab  mov     [rbp+0A0h+cchValueName], eax
0x14000deb1  lea     rax, [rdi+2Ch]
0x14000deb5  lea     rcx, [rdi+10h]
0x14000deb9  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x14000debe  mov     [rsp+1A0h+lpData], r12; lpData
0x14000dec3  mov     [rsp+1A0h+lpType], rcx; lpType
0x14000dec8  mov     [rsp+1A0h+lpReserved], r12; lpReserved
0x14000decd  lea     r9, [rbp+0A0h+cchValueName]; lpcchValueName
0x14000ded4  mov     edx, [rdi+0Ch]; dwIndex
0x14000ded7  mov     rcx, [rdi]; hKey
0x14000deda  call    cs:__imp_RegEnumValueW
0x14000dee0  mov     ebx, eax
0x14000dee2  test    eax, eax
0x14000dee4  jnz     loc_14000E10D
0x14000deea  mov     byte ptr [rdi+30h], 1
0x14000deee  mov     rcx, [rbp+0A0h+var_110]; pv
0x14000def2  call    cs:__imp_CoTaskMemFree
0x14000def8  mov     [rbp+0A0h+var_110], r12
0x14000defc  mov     rcx, [rbp+0A0h+var_110+8]; pv
0x14000df00  call    cs:__imp_CoTaskMemFree
0x14000df06  mov     [rbp+0A0h+var_110+8], r12
0x14000df0a  mov     rcx, [rbp+0A0h+var_100]; pv
0x14000df0e  call    cs:__imp_CoTaskMemFree
0x14000df14  mov     [rbp+0A0h+var_100], r12
0x14000df18  mov     rcx, [rbp+0A0h+var_100+8]; pv
0x14000df1c  call    cs:__imp_CoTaskMemFree
0x14000df22  mov     [rbp+0A0h+var_100+8], r12
0x14000df26  call    cs:__imp_GetTickCount
0x14000df2c  mov     esi, eax
0x14000df2e  sub     esi, [rbp+0A0h+var_11C]
0x14000df31  mov     eax, 10624DD3h
0x14000df36  mul     esi
0x14000df38  mov     edi, edx
0x14000df3a  shr     edi, 6
0x14000df3d  mov     eax, 88888889h
0x14000df42  mul     edi
0x14000df44  shr     edx, 5
0x14000df47  imul    ecx, edx, 3Ch ; '<'
0x14000df4a  mov     ebx, edi
0x14000df4c  sub     ebx, ecx
0x14000df4e  mov     eax, 45E7B273h
0x14000df53  mul     esi
0x14000df55  mov     r11d, edx
0x14000df58  shr     r11d, 0Eh
0x14000df5c  mov     eax, 88888889h
0x14000df61  mul     r11d
0x14000df64  shr     edx, 5
0x14000df67  imul    ecx, edx, 3Ch ; '<'
0x14000df6a  sub     r11d, ecx
0x14000df6d  mov     eax, 95217CB1h
0x14000df72  mul     esi
0x14000df74  mov     r10d, edx
0x14000df77  shr     r10d, 15h
0x14000df7b  mov     eax, 88888889h
0x14000df80  mul     r10d
0x14000df83  shr     edx, 5
0x14000df86  imul    eax, edx, 3Ch ; '<'
0x14000df89  sub     r10d, eax
0x14000df8c  mov     r9d, [rsp+1A0h+var_148]
0x14000df91  cmp     [rbp+0A0h+var_118], 0FFh
0x14000df98  cmovnz  r14d, [rbp+0A0h+var_118]
0x14000df9d  imul    eax, edi, 3E8h
0x14000dfa3  mov     ecx, esi
0x14000dfa5  sub     ecx, eax
0x14000dfa7  mov     [rsp+1A0h+var_158], r9d
0x14000dfac  mov     dword ptr [rsp+1A0h+var_160], esi
0x14000dfb0  mov     dword ptr [rsp+1A0h+lpcbData], ecx
0x14000dfb4  mov     dword ptr [rsp+1A0h+lpData], ebx
0x14000dfb8  mov     dword ptr [rsp+1A0h+lpType], r11d
0x14000dfbd  mov     dword ptr [rsp+1A0h+lpReserved], r10d
0x14000dfc2  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x14000dfc9  mov     r8d, r14d; unsigned int
0x14000dfcc  lea     rdx, aExit; "EXIT"
0x14000dfd3  lea     rcx, [rsp+1A0h+var_150]; this
0x14000dfd8  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14000dfdd  mov     rcx, [rbp+0A0h+var_F0]
0x14000dfe1  call    cs:__imp_VssSetTracingContextPerThread
0x14000dfe7  mov     rbx, [rsp+1A0h+arg_10]
0x14000dfef  add     rsp, 170h
0x14000dff6  pop     r15
0x14000dff8  pop     r14
0x14000dffa  pop     r13
0x14000dffc  pop     r12
0x14000dffe  pop     rdi
0x14000dfff  pop     rsi
0x14000e000  pop     rbp
0x14000e001  retn
0x14000e002  lea     rcx, [rsp+1A0h+var_150]
0x14000e007  call    cs:__imp_VssSetTracingContextPerThread
0x14000e00d  test    eax, eax
0x14000e00f  js      loc_14000DDC5
0x14000e015  mov     rax, [rbp+0A0h+arg_8]
0x14000e01c  mov     [rbp+0A0h+var_F0], rax
0x14000e020  jmp     loc_14000DDC9
0x14000e025  lea     rcx, [rsp+1A0h+var_150]; this
0x14000e02a  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14000e02f  jmp     short loc_14000DFE7
0x14000e031  mov     [rbp+0A0h+var_120], r12d
0x14000e035  jmp     loc_14000DDDA
0x14000e03a  mov     r14d, [rbp+0A0h+cchValueName]
0x14000e041  mov     r15, [rdi+20h]
0x14000e045  mov     rdi, [rdi]
0x14000e048  test    eax, eax
0x14000e04a  jle     short loc_14000E055
0x14000e04c  movzx   ebx, ax
0x14000e04f  or      ebx, 80070000h
0x14000e055  mov     [rbp+0A0h+var_E0], r13
0x14000e059  lea     rax, aCvssregistryva; "CVssRegistryValueIterator::ReadCurrentV"...
0x14000e060  mov     [rbp+0A0h+var_D8], rax
0x14000e064  lea     rax, aRegregsc; "REGREGSC"
0x14000e06b  mov     [rbp+0A0h+var_D0], rax
0x14000e06f  mov     [rbp+0A0h+var_C8], 47Ah
0x14000e076  mov     [rbp+0A0h+var_C4], 0Bh
0x14000e07d  mov     [rbp+0A0h+var_C0], 0FFh
0x14000e084  mov     [rbp+0A0h+var_40], 1000000h
0x14000e08b  xor     edx, edx; Val
0x14000e08d  mov     r8d, 78h ; 'x'; Size
0x14000e093  lea     rcx, [rbp+0A0h+pv]; void *
0x14000e097  call    memset_0
0x14000e09c  mov     dword ptr [rsp+1A0h+lpcbData], r14d
0x14000e0a1  mov     [rsp+1A0h+lpData], r15
0x14000e0a6  mov     dword ptr [rsp+1A0h+lpType], esi
0x14000e0aa  mov     [rsp+1A0h+lpReserved], rdi
0x14000e0af  lea     r9, aRegenumvaluePL; "RegEnumValue(%p,%lu,%p,%lu ...)"
0x14000e0b6  mov     r8d, ebx
0x14000e0b9  lea     rdx, [rbp+0A0h+var_E0]
0x14000e0bd  lea     rcx, [rsp+1A0h+var_150]
0x14000e0c2  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000e0c8  mov     [rsp+1A0h+var_160], r12
0x14000e0cd  mov     dword ptr [rsp+1A0h+lpcbData], ebx
0x14000e0d1  lea     rax, aEnter; "ENTER"
0x14000e0d8  mov     [rsp+1A0h+lpData], rax
0x14000e0dd  mov     rax, [rsp+1A0h+var_128]
0x14000e0e2  mov     [rsp+1A0h+lpType], rax
0x14000e0e7  mov     eax, [rsp+1A0h+var_12C]
0x14000e0eb  mov     dword ptr [rsp+1A0h+lpReserved], eax
0x14000e0ef  mov     r9d, [rbp+0A0h+var_120]
0x14000e0f3  mov     r8d, [rsp+1A0h+var_130]
0x14000e0f8  mov     rdx, [rsp+1A0h+var_138]
0x14000e0fd  mov     rcx, [rsp+1A0h+var_140]
0x14000e102  call    cs:__imp_VssTraceMessage
0x14000e108  jmp     loc_14000DE04
0x14000e10d  mov     esi, [rdi+0Ch]
0x14000e110  cmp     eax, 103h
0x14000e115  jnz     loc_14000E03A
0x14000e11b  mov     [rbp+0A0h+var_E0], r13
0x14000e11f  mov     [rbp+0A0h+var_D8], r15
0x14000e123  lea     rax, aRegregsc; "REGREGSC"
0x14000e12a  mov     [rbp+0A0h+var_D0], rax
0x14000e12e  mov     [rbp+0A0h+var_C8], 47Eh
0x14000e135  mov     [rbp+0A0h+var_C4], 0Bh
0x14000e13c  mov     [rbp+0A0h+var_C0], 0FFh
0x14000e143  mov     [rbp+0A0h+var_40], 1000000h
0x14000e14a  xor     edx, edx; Val
0x14000e14c  mov     r8d, 78h ; 'x'; Size
0x14000e152  lea     rcx, [rbp+0A0h+pv]; void *
0x14000e156  call    memset_0
0x14000e15b  mov     eax, [rdi+8]
0x14000e15e  mov     dword ptr [rsp+1A0h+lpType], eax
0x14000e162  mov     dword ptr [rsp+1A0h+lpReserved], esi
0x14000e166  lea     r9, aUnexpectedErro_11; "Unexpected error: dwIndex out of scope "...
0x14000e16d  mov     r8d, 8000FFFFh
0x14000e173  lea     rdx, [rbp+0A0h+var_E0]
0x14000e177  lea     rcx, [rsp+1A0h+var_150]
0x14000e17c  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```

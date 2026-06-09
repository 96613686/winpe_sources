# CVssSoftwareProviderWrapper::AddRef(void)

- ea: `0x1400356c0`
- end: `0x140035a1d`
- name: `?AddRef@CVssSoftwareProviderWrapper@@UEAAKXZ`
- size: `861`
- prototype: `__int64 __fastcall(CVssSoftwareProviderWrapper *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x1400356c0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140035763`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400358c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140035763`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400358c4`
- `VssTrace!__imp_VssTraceMessage` at `0x140035a12`
- `VssTrace!__imp_VssTraceMessage` at `0x140035a12`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003597f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400359b2`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003597f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400359b2`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400357a1`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400357a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035890`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003589e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400358ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400358ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003599d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035890`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003589e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400358ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400358ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003599d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssSoftwareProviderWrapper::AddRef(CVssSoftwareProviderWrapper *this)
{
  __int64 v2; // rax
  unsigned int v3; // r15d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  int v7; // ecx
  signed __int32 v8; // r14d
  DWORD v9; // esi
  __int64 v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+20h] [rbp-E0h]
  __int64 v13; // [rsp+28h] [rbp-D8h]
  __int64 v14; // [rsp+28h] [rbp-D8h]
  __int64 v15; // [rsp+30h] [rbp-D0h]
  __int64 v16; // [rsp+38h] [rbp-C8h]
  __int64 v17; // [rsp+40h] [rbp-C0h]
  _DWORD v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v20; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v21; // [rsp+68h] [rbp-98h]
  unsigned int v22; // [rsp+70h] [rbp-90h]
  unsigned int v23; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v24; // [rsp+78h] [rbp-88h]
  unsigned int v25; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v27; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  LPVOID v29[2]; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v31; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v32; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  int v35; // [rsp+E0h] [rbp-20h]
  LPVOID v36[2]; // [rsp+E8h] [rbp-18h]
  __int128 v37; // [rsp+F8h] [rbp-8h]
  __int128 v38; // [rsp+108h] [rbp+8h]
  __int128 v39; // [rsp+118h] [rbp+18h]
  __int128 v40; // [rsp+128h] [rbp+28h]
  __int128 v41; // [rsp+138h] [rbp+38h]
  __int128 v42; // [rsp+148h] [rbp+48h]
  __int64 v43; // [rsp+158h] [rbp+58h]
  int v44; // [rsp+160h] [rbp+60h]
  __int64 v45; // [rsp+1C0h] [rbp+C0h] BYREF

  v34 = 0x100000098LL;
  v35 = 255;
  v33 = L"CORSOFTC";
  v44 = 0x1000000;
  v32 = L"CVssSoftwareProviderWrapper::AddRef";
  v24 = L"CVssSoftwareProviderWrapper::AddRef";
  v31 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  *(_OWORD *)v36 = 0;
  v43 = 0;
  v37 = 0;
  v19 = 0;
  v38 = 0;
  v20 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  v39 = 0;
  v21 = L"CORSOFTC";
  v40 = 0;
  v22 = 152;
  v41 = 0;
  v23 = 1;
  v42 = 0;
  v18[1] = -1;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v29 = 0;
  TickCount = GetTickCount();
  v27 = 255;
  v18[0] = 0;
  v30 = 0;
  v45 = 0;
  if ( (int)VssGetTracingContextPerThread(&v45) < 0 || (int)VssSetTracingContextPerThread(v18) < 0 )
  {
    v2 = v30;
  }
  else
  {
    v2 = v45;
    v30 = v45;
  }
  if ( v2 )
    v25 = *(_DWORD *)(v2 + 48) + 1;
  else
    v25 = 0;
  v3 = 160;
  v4 = 160;
  if ( v27 != 255 )
    v4 = v27;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v18, v23) )
    VssTraceMessage(v20, v21, v22, v25, v23, v24, L"ENTER", v4, 0);
  for ( i = 0; i != 15; ++i )
  {
    v6 = v36[i];
    if ( v6 )
    {
      CoTaskMemFree(v6);
      v36[i] = 0;
    }
  }
  v7 = *((_DWORD *)this + 8);
  v32 = L"CVssSoftwareProviderWrapper::AddRef";
  v31 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  v33 = L"CORSOFTC";
  v34 = 0x100000099LL;
  v43 = 0;
  LODWORD(v13) = v7 + 1;
  LODWORD(v11) = v7;
  v35 = 255;
  v44 = 0x1000000;
  *(_OWORD *)v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  CVssFunctionTracer::Trace(v18, &v31, L"Provider Wrapper AddRef(%p) %lu --> %lu", this, v11, v13);
  v8 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 8, 1u);
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v29[0]);
  v29[0] = 0;
  CoTaskMemFree(v29[1]);
  v29[1] = 0;
  v9 = GetTickCount() - TickCount;
  LODWORD(v17) = v9;
  if ( v27 != 255 )
    v3 = v27;
  LODWORD(v16) = v9 % 0x3E8;
  LODWORD(v15) = v9 / 0x3E8 % 0x3C;
  LODWORD(v14) = v9 / 0xEA60 % 0x3C;
  LODWORD(v12) = v9 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v18,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v12,
    v14,
    v15,
    v16,
    v17,
    v19);
  VssSetTracingContextPerThread(v30);
  return (unsigned int)(v8 + 1);
}

```

## disassembly

```asm
0x1400356c0  push    rbp
0x1400356c2  push    rbx
0x1400356c3  push    rsi
0x1400356c4  push    rdi
0x1400356c5  push    r12
0x1400356c7  push    r13
0x1400356c9  push    r14
0x1400356cb  push    r15
0x1400356cd  lea     rbp, [rsp-78h]
0x1400356d2  sub     rsp, 178h
0x1400356d9  xorps   xmm0, xmm0
0x1400356dc  mov     dword ptr [rbp+0B0h+var_D8], 98h
0x1400356e3  lea     rdx, aCorsoftc; "CORSOFTC"
0x1400356ea  mov     [rbp+0B0h+var_D0], 0FFh
0x1400356f1  mov     rdi, rcx
0x1400356f4  mov     [rbp+0B0h+var_E0], rdx
0x1400356f8  lea     rcx, aCvsssoftwarepr_5; "CVssSoftwareProviderWrapper::AddRef"
0x1400356ff  mov     [rbp+0B0h+var_50], 1000000h
0x140035706  lea     r13, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x14003570d  mov     [rbp+0B0h+var_E8], rcx
0x140035711  mov     r14d, 1
0x140035717  mov     [rsp+1B0h+var_138], rcx
0x14003571c  xor     eax, eax
0x14003571e  mov     [rbp+0B0h+var_F0], r13
0x140035722  xor     esi, esi
0x140035724  mov     dword ptr [rbp+0B0h+var_D8+4], r14d
0x140035728  movups  xmmword ptr [rbp+0B0h+var_C8], xmm0
0x14003572c  mov     [rbp+0B0h+var_58], rax
0x140035730  movups  [rbp+0B0h+var_B8], xmm0
0x140035734  mov     [rsp+1B0h+var_158], esi
0x140035738  movups  [rbp+0B0h+var_A8], xmm0
0x14003573c  mov     [rsp+1B0h+var_150], r13
0x140035741  movups  [rbp+0B0h+var_98], xmm0
0x140035745  mov     [rsp+1B0h+var_148], rdx
0x14003574a  movups  [rbp+0B0h+var_88], xmm0
0x14003574e  mov     [rsp+1B0h+var_140], 98h
0x140035756  movups  [rbp+0B0h+var_78], xmm0
0x14003575a  mov     [rsp+1B0h+var_13C], r14d
0x14003575f  movups  [rbp+0B0h+var_68], xmm0
0x140035763  call    cs:__imp_GetTickCount
0x140035769  xorps   xmm0, xmm0
0x14003576c  mov     [rsp+1B0h+var_15C], 0FFFFFFFFh
0x140035774  xorps   xmm1, xmm1
0x140035777  movdqa  xmmword ptr [rbp+0B0h+pv], xmm0
0x14003577c  lea     rcx, [rbp+0B0h+arg_0]
0x140035783  movdqa  xmmword ptr [rbp+0B0h+var_110], xmm1
0x140035788  mov     [rbp+0B0h+var_12C], eax
0x14003578b  mov     [rbp+0B0h+var_128], 0FFh
0x140035792  mov     [rsp+1B0h+var_160], esi
0x140035796  mov     [rbp+0B0h+var_100], rsi
0x14003579a  mov     [rbp+0B0h+arg_0], rsi
0x1400357a1  call    cs:__imp_VssGetTracingContextPerThread
0x1400357a7  test    eax, eax
0x1400357a9  jns     loc_1400359AD
0x1400357af  mov     rax, [rbp+0B0h+var_100]
0x1400357b3  test    rax, rax
0x1400357b6  jz      loc_1400359D0
0x1400357bc  mov     eax, [rax+30h]
0x1400357bf  inc     eax
0x1400357c1  mov     [rbp+0B0h+var_130], eax
0x1400357c4  cmp     [rbp+0B0h+var_128], 0FFh
0x1400357cb  lea     rcx, [rsp+1B0h+var_160]; this
0x1400357d0  mov     edx, [rsp+1B0h+var_13C]; unsigned int
0x1400357d4  mov     r15d, 0A0h
0x1400357da  mov     ebx, r15d
0x1400357dd  cmovnz  ebx, [rbp+0B0h+var_128]
0x1400357e1  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x1400357e6  test    eax, eax
0x1400357e8  jnz     loc_1400359D8
0x1400357ee  mov     rbx, rsi
0x1400357f1  mov     rcx, [rbp+rbx*8+0B0h+var_C8]; pv
0x1400357f6  test    rcx, rcx
0x1400357f9  jnz     loc_14003599D
0x1400357ff  inc     rbx
0x140035802  cmp     rbx, 0Fh
0x140035806  jnz     short loc_1400357F1
0x140035808  mov     ecx, [rdi+20h]
0x14003580b  lea     rax, aCvsssoftwarepr_5; "CVssSoftwareProviderWrapper::AddRef"
0x140035812  xorps   xmm0, xmm0
0x140035815  mov     [rbp+0B0h+var_E8], rax
0x140035819  lea     rax, aCorsoftc; "CORSOFTC"
0x140035820  mov     [rbp+0B0h+var_F0], r13
0x140035824  mov     [rbp+0B0h+var_E0], rax
0x140035828  lea     r8, aProviderWrappe_0; "Provider Wrapper AddRef(%p) %lu --> %lu"
0x14003582f  xor     eax, eax
0x140035831  mov     dword ptr [rbp+0B0h+var_D8], 99h
0x140035838  mov     [rbp+0B0h+var_58], rax
0x14003583c  lea     rdx, [rbp+0B0h+var_F0]
0x140035840  lea     eax, [rcx+1]
0x140035843  mov     dword ptr [rbp+0B0h+var_D8+4], r14d
0x140035847  mov     dword ptr [rsp+1B0h+var_188], eax
0x14003584b  mov     r9, rdi
0x14003584e  mov     dword ptr [rsp+1B0h+var_190], ecx
0x140035852  lea     rcx, [rsp+1B0h+var_160]
0x140035857  mov     [rbp+0B0h+var_D0], 0FFh
0x14003585e  mov     [rbp+0B0h+var_50], 1000000h
0x140035865  movups  xmmword ptr [rbp+0B0h+var_C8], xmm0
0x140035869  movups  [rbp+0B0h+var_B8], xmm0
0x14003586d  movups  [rbp+0B0h+var_A8], xmm0
0x140035871  movups  [rbp+0B0h+var_98], xmm0
0x140035875  movups  [rbp+0B0h+var_88], xmm0
0x140035879  movups  [rbp+0B0h+var_78], xmm0
0x14003587d  movups  [rbp+0B0h+var_68], xmm0
0x140035881  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140035886  lock xadd [rdi+20h], r14d
0x14003588c  mov     rcx, [rbp+0B0h+pv]; pv
0x140035890  call    cs:__imp_CoTaskMemFree
0x140035896  mov     rcx, [rbp+0B0h+pv+8]; pv
0x14003589a  mov     [rbp+0B0h+pv], rsi
0x14003589e  call    cs:__imp_CoTaskMemFree
0x1400358a4  mov     rcx, [rbp+0B0h+var_110]; pv
0x1400358a8  mov     [rbp+0B0h+pv+8], rsi
0x1400358ac  call    cs:__imp_CoTaskMemFree
0x1400358b2  mov     rcx, [rbp+0B0h+var_110+8]; pv
0x1400358b6  mov     [rbp+0B0h+var_110], rsi
0x1400358ba  call    cs:__imp_CoTaskMemFree
0x1400358c0  mov     [rbp+0B0h+var_110+8], rsi
0x1400358c4  call    cs:__imp_GetTickCount
0x1400358ca  mov     r9d, [rsp+1B0h+var_158]
0x1400358cf  mov     esi, eax
0x1400358d1  sub     esi, [rbp+0B0h+var_12C]
0x1400358d4  mov     eax, 10624DD3h
0x1400358d9  mul     esi
0x1400358db  mov     [rsp+1B0h+var_168], r9d
0x1400358e0  mov     eax, 88888889h
0x1400358e5  mov     edi, edx
0x1400358e7  mov     dword ptr [rsp+1B0h+var_170], esi
0x1400358eb  shr     edi, 6
0x1400358ee  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x1400358f5  mul     edi
0x1400358f7  mov     eax, 45E7B273h
0x1400358fc  mov     ebx, edi
0x1400358fe  shr     edx, 5
0x140035901  imul    ecx, edx, 3Ch ; '<'
0x140035904  mul     esi
0x140035906  sub     ebx, ecx
0x140035908  mov     eax, 88888889h
0x14003590d  mov     r11d, edx
0x140035910  shr     r11d, 0Eh
0x140035914  mul     r11d
0x140035917  mov     eax, 95217CB1h
0x14003591c  shr     edx, 5
0x14003591f  imul    ecx, edx, 3Ch ; '<'
0x140035922  mul     esi
0x140035924  sub     r11d, ecx
0x140035927  mov     eax, 88888889h
0x14003592c  mov     r10d, edx
0x14003592f  shr     r10d, 15h
0x140035933  mul     r10d
0x140035936  shr     edx, 5
0x140035939  imul    eax, edx, 3Ch ; '<'
0x14003593c  mov     edx, esi
0x14003593e  sub     r10d, eax
0x140035941  cmp     [rbp+0B0h+var_128], 0FFh
0x140035948  cmovnz  r15d, [rbp+0B0h+var_128]
0x14003594d  imul    ecx, edi, 3E8h
0x140035953  mov     r8d, r15d; unsigned int
0x140035956  sub     edx, ecx
0x140035958  lea     rcx, [rsp+1B0h+var_160]; this
0x14003595d  mov     dword ptr [rsp+1B0h+var_178], edx
0x140035961  lea     rdx, aExit; "EXIT"
0x140035968  mov     dword ptr [rsp+1B0h+var_180], ebx
0x14003596c  mov     dword ptr [rsp+1B0h+var_188], r11d
0x140035971  mov     dword ptr [rsp+1B0h+var_190], r10d
0x140035976  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14003597b  mov     rcx, [rbp+0B0h+var_100]
0x14003597f  call    cs:__imp_VssSetTracingContextPerThread
0x140035985  lea     eax, [r14+1]
0x140035989  add     rsp, 178h
0x140035990  pop     r15
0x140035992  pop     r14
0x140035994  pop     r13
0x140035996  pop     r12
0x140035998  pop     rdi
0x140035999  pop     rsi
0x14003599a  pop     rbx
0x14003599b  pop     rbp
0x14003599c  retn
0x14003599d  call    cs:__imp_CoTaskMemFree
0x1400359a3  mov     [rbp+rbx*8+0B0h+var_C8], rsi
0x1400359a8  jmp     loc_1400357FF
0x1400359ad  lea     rcx, [rsp+1B0h+var_160]
0x1400359b2  call    cs:__imp_VssSetTracingContextPerThread
0x1400359b8  test    eax, eax
0x1400359ba  js      loc_1400357AF
0x1400359c0  mov     rax, [rbp+0B0h+arg_0]
0x1400359c7  mov     [rbp+0B0h+var_100], rax
0x1400359cb  jmp     loc_1400357B3
0x1400359d0  mov     [rbp+0B0h+var_130], esi
0x1400359d3  jmp     loc_1400357C4
0x1400359d8  mov     r9d, [rbp+0B0h+var_130]
0x1400359dc  lea     rax, aEnter; "ENTER"
0x1400359e3  mov     r8d, [rsp+1B0h+var_140]
0x1400359e8  mov     rdx, [rsp+1B0h+var_148]
0x1400359ed  mov     rcx, [rsp+1B0h+var_150]
0x1400359f2  mov     [rsp+1B0h+var_170], rsi
0x1400359f7  mov     dword ptr [rsp+1B0h+var_178], ebx
0x1400359fb  mov     [rsp+1B0h+var_180], rax
0x140035a00  mov     rax, [rsp+1B0h+var_138]
0x140035a05  mov     [rsp+1B0h+var_188], rax
0x140035a0a  mov     eax, [rsp+1B0h+var_13C]
0x140035a0e  mov     dword ptr [rsp+1B0h+var_190], eax
0x140035a12  call    cs:__imp_VssTraceMessage
0x140035a18  jmp     loc_1400357EE
```

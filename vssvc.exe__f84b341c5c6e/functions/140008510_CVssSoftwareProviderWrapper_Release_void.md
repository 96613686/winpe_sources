# CVssSoftwareProviderWrapper::Release(void)

- ea: `0x140008510`
- end: `0x140008896`
- name: `?Release@CVssSoftwareProviderWrapper@@UEAAKXZ`
- size: `902`
- prototype: `unsigned int __fastcall(CVssSoftwareProviderWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140008510`
- `0x14000889c`
- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140091584`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400085b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008724`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400085b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008724`
- `VssTrace!__imp_VssTraceMessage` at `0x14000888b`
- `VssTrace!__imp_VssTraceMessage` at `0x14000888b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400087df`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140008811`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400087df`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140008811`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400085f1`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400085f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400086f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400086fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000870c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000871a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400087fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400086f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400086fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000870c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000871a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400087fc`

## pseudocode

```c
__int64 __fastcall CVssSoftwareProviderWrapper::Release(CVssSoftwareProviderWrapper *this)
{
  unsigned int v2; // r15d
  __int64 v3; // rax
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  int v7; // ecx
  unsigned __int32 v8; // r14d
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
  int v34; // [rsp+D8h] [rbp-28h]
  int v35; // [rsp+DCh] [rbp-24h]
  int v36; // [rsp+E0h] [rbp-20h]
  LPVOID v37[2]; // [rsp+E8h] [rbp-18h]
  __int128 v38; // [rsp+F8h] [rbp-8h]
  __int128 v39; // [rsp+108h] [rbp+8h]
  __int128 v40; // [rsp+118h] [rbp+18h]
  __int128 v41; // [rsp+128h] [rbp+28h]
  __int128 v42; // [rsp+138h] [rbp+38h]
  __int128 v43; // [rsp+148h] [rbp+48h]
  __int64 v44; // [rsp+158h] [rbp+58h]
  int v45; // [rsp+160h] [rbp+60h]
  __int64 v46; // [rsp+1C0h] [rbp+C0h] BYREF

  v35 = 1;
  v36 = 255;
  v45 = 0x1000000;
  v33 = L"CORSOFTC";
  v21 = L"CORSOFTC";
  v2 = 160;
  v31 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  v32 = L"CVssSoftwareProviderWrapper::Release";
  v34 = 160;
  *(_OWORD *)v37 = 0;
  v44 = 0;
  v38 = 0;
  v19 = 0;
  v39 = 0;
  v24 = L"CVssSoftwareProviderWrapper::Release";
  v40 = 0;
  v20 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  v41 = 0;
  v22 = 160;
  v42 = 0;
  v23 = 1;
  v43 = 0;
  v18[1] = -1;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v29 = 0;
  TickCount = GetTickCount();
  v27 = 255;
  v18[0] = 0;
  v30 = 0;
  v46 = 0;
  if ( (int)VssGetTracingContextPerThread(&v46) < 0 || (int)VssSetTracingContextPerThread(v18) < 0 )
  {
    v3 = v30;
  }
  else
  {
    v3 = v46;
    v30 = v46;
  }
  if ( v3 )
    v25 = *(_DWORD *)(v3 + 48) + 1;
  else
    v25 = 0;
  v4 = 160;
  if ( v27 != 255 )
    v4 = v27;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v18, v23) )
    VssTraceMessage(v20, v21, v22, v25, v23, v24, L"ENTER", v4, 0);
  for ( i = 0; i != 15; ++i )
  {
    v6 = v37[i];
    if ( v6 )
    {
      CoTaskMemFree(v6);
      v37[i] = 0;
    }
  }
  v7 = *((_DWORD *)this + 8);
  v33 = L"CORSOFTC";
  v31 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  v44 = 0;
  v32 = L"CVssSoftwareProviderWrapper::Release";
  LODWORD(v13) = v7 - 1;
  LODWORD(v11) = v7;
  v34 = 161;
  v35 = 1;
  v36 = 255;
  v45 = 0x1000000;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  CVssFunctionTracer::Trace(v18, &v31, L"Provider Wrapper Release(%p) %lu --> %lu", this, v11, v13);
  v8 = _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( !v8 && this )
  {
    CVssFileShareProviderWrapper::~CVssFileShareProviderWrapper(this);
    operator delete(this);
  }
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
    v2 = v27;
  LODWORD(v16) = v9 % 0x3E8;
  LODWORD(v15) = v9 / 0x3E8 % 0x3C;
  LODWORD(v14) = v9 / 0xEA60 % 0x3C;
  LODWORD(v12) = v9 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v18,
    L"EXIT",
    v2,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v12,
    v14,
    v15,
    v16,
    v17,
    v19);
  VssSetTracingContextPerThread(v30);
  return v8;
}

```

## disassembly

```asm
0x140008510  push    rbp
0x140008512  push    rbx
0x140008513  push    rsi
0x140008514  push    rdi
0x140008515  push    r12
0x140008517  push    r13
0x140008519  push    r14
0x14000851b  push    r15
0x14000851d  lea     rbp, [rsp-78h]
0x140008522  sub     rsp, 178h
0x140008529  xorps   xmm0, xmm0
0x14000852c  mov     [rbp+0B0h+var_D4], 1
0x140008533  mov     rdi, rcx
0x140008536  mov     [rbp+0B0h+var_D0], 0FFh
0x14000853d  lea     rcx, aCorsoftc; "CORSOFTC"
0x140008544  mov     [rbp+0B0h+var_50], 1000000h
0x14000854b  lea     r12, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x140008552  mov     [rbp+0B0h+var_E0], rcx
0x140008556  lea     r13, aCvsssoftwarepr_1; "CVssSoftwareProviderWrapper::Release"
0x14000855d  mov     [rsp+1B0h+var_148], rcx
0x140008562  mov     r15d, 0A0h
0x140008568  mov     [rbp+0B0h+var_F0], r12
0x14000856c  xor     eax, eax
0x14000856e  mov     [rbp+0B0h+var_E8], r13
0x140008572  xor     esi, esi
0x140008574  mov     [rbp+0B0h+var_D8], r15d
0x140008578  movups  xmmword ptr [rbp+0B0h+var_C8], xmm0
0x14000857c  mov     [rbp+0B0h+var_58], rax
0x140008580  movups  [rbp+0B0h+var_B8], xmm0
0x140008584  mov     [rsp+1B0h+var_158], esi
0x140008588  movups  [rbp+0B0h+var_A8], xmm0
0x14000858c  mov     [rsp+1B0h+var_138], r13
0x140008591  movups  [rbp+0B0h+var_98], xmm0
0x140008595  mov     [rsp+1B0h+var_150], r12
0x14000859a  movups  [rbp+0B0h+var_88], xmm0
0x14000859e  mov     [rsp+1B0h+var_140], r15d
0x1400085a3  movups  [rbp+0B0h+var_78], xmm0
0x1400085a7  mov     [rsp+1B0h+var_13C], 1
0x1400085af  movups  [rbp+0B0h+var_68], xmm0
0x1400085b3  call    cs:__imp_GetTickCount
0x1400085b9  xorps   xmm0, xmm0
0x1400085bc  mov     [rsp+1B0h+var_15C], 0FFFFFFFFh
0x1400085c4  xorps   xmm1, xmm1
0x1400085c7  movdqa  xmmword ptr [rbp+0B0h+pv], xmm0
0x1400085cc  lea     rcx, [rbp+0B0h+arg_0]
0x1400085d3  movdqa  xmmword ptr [rbp+0B0h+var_110], xmm1
0x1400085d8  mov     [rbp+0B0h+var_12C], eax
0x1400085db  mov     [rbp+0B0h+var_128], 0FFh
0x1400085e2  mov     [rsp+1B0h+var_160], esi
0x1400085e6  mov     [rbp+0B0h+var_100], rsi
0x1400085ea  mov     [rbp+0B0h+arg_0], rsi
0x1400085f1  call    cs:__imp_VssGetTracingContextPerThread
0x1400085f7  test    eax, eax
0x1400085f9  jns     loc_14000880C
0x1400085ff  mov     rax, [rbp+0B0h+var_100]
0x140008603  test    rax, rax
0x140008606  jz      loc_140008849
0x14000860c  mov     eax, [rax+30h]
0x14000860f  inc     eax
0x140008611  mov     [rbp+0B0h+var_130], eax
0x140008614  cmp     [rbp+0B0h+var_128], 0FFh
0x14000861b  lea     rcx, [rsp+1B0h+var_160]; this
0x140008620  mov     edx, [rsp+1B0h+var_13C]; unsigned int
0x140008624  mov     ebx, r15d
0x140008627  cmovnz  ebx, [rbp+0B0h+var_128]
0x14000862b  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140008630  test    eax, eax
0x140008632  jnz     loc_140008851
0x140008638  mov     rbx, rsi
0x14000863b  nop     dword ptr [rax+rax+00h]
0x140008640  mov     rcx, [rbp+rbx*8+0B0h+var_C8]; pv
0x140008645  test    rcx, rcx
0x140008648  jnz     loc_1400087FC
0x14000864e  inc     rbx
0x140008651  cmp     rbx, 0Fh
0x140008655  jnz     short loc_140008640
0x140008657  mov     ecx, [rdi+20h]
0x14000865a  lea     rax, aCorsoftc; "CORSOFTC"
0x140008661  xorps   xmm0, xmm0
0x140008664  mov     [rbp+0B0h+var_E0], rax
0x140008668  xor     eax, eax
0x14000866a  mov     [rbp+0B0h+var_F0], r12
0x14000866e  mov     [rbp+0B0h+var_58], rax
0x140008672  lea     r8, aProviderWrappe; "Provider Wrapper Release(%p) %lu --> %l"...
0x140008679  lea     eax, [rcx-1]
0x14000867c  mov     [rbp+0B0h+var_E8], r13
0x140008680  mov     dword ptr [rsp+1B0h+var_188], eax
0x140008684  lea     rdx, [rbp+0B0h+var_F0]
0x140008688  mov     dword ptr [rsp+1B0h+var_190], ecx
0x14000868c  mov     r9, rdi
0x14000868f  lea     rcx, [rsp+1B0h+var_160]
0x140008694  mov     [rbp+0B0h+var_D8], 0A1h
0x14000869b  mov     [rbp+0B0h+var_D4], 1
0x1400086a2  mov     [rbp+0B0h+var_D0], 0FFh
0x1400086a9  mov     [rbp+0B0h+var_50], 1000000h
0x1400086b0  movups  xmmword ptr [rbp+0B0h+var_C8], xmm0
0x1400086b4  movups  [rbp+0B0h+var_B8], xmm0
0x1400086b8  movups  [rbp+0B0h+var_A8], xmm0
0x1400086bc  movups  [rbp+0B0h+var_98], xmm0
0x1400086c0  movups  [rbp+0B0h+var_88], xmm0
0x1400086c4  movups  [rbp+0B0h+var_78], xmm0
0x1400086c8  movups  [rbp+0B0h+var_68], xmm0
0x1400086cc  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400086d1  mov     r14d, 0FFFFFFFFh
0x1400086d7  lock xadd [rdi+20h], r14d
0x1400086dd  sub     r14d, 1
0x1400086e1  jnz     short loc_1400086EC
0x1400086e3  test    rdi, rdi
0x1400086e6  jnz     loc_14000882F
0x1400086ec  mov     rcx, [rbp+0B0h+pv]; pv
0x1400086f0  call    cs:__imp_CoTaskMemFree
0x1400086f6  mov     rcx, [rbp+0B0h+pv+8]; pv
0x1400086fa  mov     [rbp+0B0h+pv], rsi
0x1400086fe  call    cs:__imp_CoTaskMemFree
0x140008704  mov     rcx, [rbp+0B0h+var_110]; pv
0x140008708  mov     [rbp+0B0h+pv+8], rsi
0x14000870c  call    cs:__imp_CoTaskMemFree
0x140008712  mov     rcx, [rbp+0B0h+var_110+8]; pv
0x140008716  mov     [rbp+0B0h+var_110], rsi
0x14000871a  call    cs:__imp_CoTaskMemFree
0x140008720  mov     [rbp+0B0h+var_110+8], rsi
0x140008724  call    cs:__imp_GetTickCount
0x14000872a  mov     r9d, [rsp+1B0h+var_158]
0x14000872f  mov     esi, eax
0x140008731  sub     esi, [rbp+0B0h+var_12C]
0x140008734  mov     eax, 10624DD3h
0x140008739  mul     esi
0x14000873b  mov     [rsp+1B0h+var_168], r9d
0x140008740  mov     eax, 88888889h
0x140008745  mov     edi, edx
0x140008747  mov     dword ptr [rsp+1B0h+var_170], esi
0x14000874b  shr     edi, 6
0x14000874e  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140008755  mul     edi
0x140008757  mov     eax, 45E7B273h
0x14000875c  mov     ebx, edi
0x14000875e  shr     edx, 5
0x140008761  imul    ecx, edx, 3Ch ; '<'
0x140008764  mul     esi
0x140008766  sub     ebx, ecx
0x140008768  mov     eax, 88888889h
0x14000876d  mov     r11d, edx
0x140008770  shr     r11d, 0Eh
0x140008774  mul     r11d
0x140008777  mov     eax, 95217CB1h
0x14000877c  shr     edx, 5
0x14000877f  imul    ecx, edx, 3Ch ; '<'
0x140008782  mul     esi
0x140008784  sub     r11d, ecx
0x140008787  mov     eax, 88888889h
0x14000878c  mov     r10d, edx
0x14000878f  shr     r10d, 15h
0x140008793  mul     r10d
0x140008796  shr     edx, 5
0x140008799  imul    eax, edx, 3Ch ; '<'
0x14000879c  mov     edx, esi
0x14000879e  sub     r10d, eax
0x1400087a1  cmp     [rbp+0B0h+var_128], 0FFh
0x1400087a8  cmovnz  r15d, [rbp+0B0h+var_128]
0x1400087ad  imul    ecx, edi, 3E8h
0x1400087b3  mov     r8d, r15d; unsigned int
0x1400087b6  sub     edx, ecx
0x1400087b8  lea     rcx, [rsp+1B0h+var_160]; this
0x1400087bd  mov     dword ptr [rsp+1B0h+var_178], edx
0x1400087c1  lea     rdx, aExit; "EXIT"
0x1400087c8  mov     dword ptr [rsp+1B0h+var_180], ebx
0x1400087cc  mov     dword ptr [rsp+1B0h+var_188], r11d
0x1400087d1  mov     dword ptr [rsp+1B0h+var_190], r10d
0x1400087d6  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400087db  mov     rcx, [rbp+0B0h+var_100]
0x1400087df  call    cs:__imp_VssSetTracingContextPerThread
0x1400087e5  mov     eax, r14d
0x1400087e8  add     rsp, 178h
0x1400087ef  pop     r15
0x1400087f1  pop     r14
0x1400087f3  pop     r13
0x1400087f5  pop     r12
0x1400087f7  pop     rdi
0x1400087f8  pop     rsi
0x1400087f9  pop     rbx
0x1400087fa  pop     rbp
0x1400087fb  retn
0x1400087fc  call    cs:__imp_CoTaskMemFree
0x140008802  mov     [rbp+rbx*8+0B0h+var_C8], rsi
0x140008807  jmp     loc_14000864E
0x14000880c  lea     rcx, [rsp+1B0h+var_160]
0x140008811  call    cs:__imp_VssSetTracingContextPerThread
0x140008817  test    eax, eax
0x140008819  js      loc_1400085FF
0x14000881f  mov     rax, [rbp+0B0h+arg_0]
0x140008826  mov     [rbp+0B0h+var_100], rax
0x14000882a  jmp     loc_140008603
0x14000882f  mov     rcx, rdi; this
0x140008832  call    ??1CVssFileShareProviderWrapper@@QEAA@XZ; CVssFileShareProviderWrapper::~CVssFileShareProviderWrapper(void)
0x140008837  mov     edx, 378h
0x14000883c  mov     rcx, rdi; Block
0x14000883f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140008844  jmp     loc_1400086EC
0x140008849  mov     [rbp+0B0h+var_130], esi
0x14000884c  jmp     loc_140008614
0x140008851  mov     r9d, [rbp+0B0h+var_130]
0x140008855  lea     rax, aEnter; "ENTER"
0x14000885c  mov     r8d, [rsp+1B0h+var_140]
0x140008861  mov     rdx, [rsp+1B0h+var_148]
0x140008866  mov     rcx, [rsp+1B0h+var_150]
0x14000886b  mov     [rsp+1B0h+var_170], rsi
0x140008870  mov     dword ptr [rsp+1B0h+var_178], ebx
0x140008874  mov     [rsp+1B0h+var_180], rax
0x140008879  mov     rax, [rsp+1B0h+var_138]
0x14000887e  mov     [rsp+1B0h+var_188], rax
0x140008883  mov     eax, [rsp+1B0h+var_13C]
0x140008887  mov     dword ptr [rsp+1B0h+var_190], eax
0x14000888b  call    cs:__imp_VssTraceMessage
0x140008891  jmp     loc_140008638
```

# CVssSoftwareProviderWrapper::QueryInternalInterface(_GUID const &,void * *)

- ea: `0x14003b830`
- end: `0x14003baac`
- name: `?QueryInternalInterface@CVssSoftwareProviderWrapper@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `636`
- prototype: `__int64 __fastcall(CVssSoftwareProviderWrapper *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x14003b830`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003b8d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003b8d0`
- `VssTrace!__imp_VssTraceMessage` at `0x14003baa1`
- `VssTrace!__imp_VssTraceMessage` at `0x14003baa1`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003b9cd`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003b9cd`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003b914`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003b914`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003b9b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003b9b7`

## pseudocode

```c
__int64 __fastcall CVssSoftwareProviderWrapper::QueryInternalInterface(
        CVssSoftwareProviderWrapper *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v6; // rcx
  int v7; // ebx
  __int64 i; // rbx
  void *v9; // rcx
  unsigned int v10; // ebx
  int v12; // eax
  unsigned __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v15; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v16; // [rsp+68h] [rbp-98h]
  unsigned int v17; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v19; // [rsp+78h] [rbp-88h]
  unsigned int v20; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  int v22; // [rsp+88h] [rbp-78h]
  __int128 v23; // [rsp+90h] [rbp-70h]
  __int128 v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v26; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v27; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v28; // [rsp+D0h] [rbp-30h]
  int v29; // [rsp+D8h] [rbp-28h]
  int v30; // [rsp+DCh] [rbp-24h]
  int v31; // [rsp+E0h] [rbp-20h]
  LPVOID pv[15]; // [rsp+E8h] [rbp-18h] BYREF
  int v33; // [rsp+160h] [rbp+60h]
  __int64 v34; // [rsp+190h] [rbp+90h] BYREF

  v29 = 120;
  v26 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  v30 = 1;
  v31 = 255;
  v27 = L"CVssSoftwareProviderWrapper::QueryInternalInterface";
  v33 = 0x1000000;
  v28 = L"CORSOFTC";
  memset_0(pv, 0, sizeof(pv));
  v19 = L"CVssSoftwareProviderWrapper::QueryInternalInterface";
  v15 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  v16 = L"CORSOFTC";
  v17 = 120;
  v18 = 1;
  v14 = 0;
  TickCount = GetTickCount();
  v22 = 255;
  v13 = 0xFFFFFFFF00000000uLL;
  v25 = 0;
  v23 = 0;
  v34 = 0;
  v24 = 0;
  if ( (int)VssGetTracingContextPerThread(&v34) >= 0 )
  {
    v12 = VssSetTracingContextPerThread(&v13);
    v6 = v25;
    if ( v12 >= 0 )
      v6 = v34;
    v25 = v6;
  }
  else
  {
    v6 = v25;
  }
  if ( v6 )
    v20 = *(_DWORD *)(v6 + 48) + 1;
  else
    v20 = 0;
  v7 = 160;
  if ( v22 != 255 )
    v7 = v22;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v13) )
    VssTraceMessage(v15, v16, v17, v20, v18, v19, L"ENTER", v7, 0);
  if ( HIBYTE(v33) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v9 = pv[i];
      if ( v9 )
      {
        CoTaskMemFree(v9);
        pv[i] = 0;
      }
    }
  }
  v14 = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 1))(*((_QWORD *)this + 1), a2, a3);
  v10 = v14;
  if ( v14 < 0 )
  {
    v29 = 125;
    v26 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
    v30 = 1;
    v31 = 255;
    v27 = L"CVssSoftwareProviderWrapper::QueryInternalInterface";
    v28 = L"CORSOFTC";
    v33 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::Trace(&v13, &v26, L"Error while obtaining an interface interface 0x%08lx", v10);
    v10 = v14;
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v13);
  return v10;
}

```

## disassembly

```asm
0x14003b830  mov     [rsp-8+arg_8], rbx
0x14003b835  mov     [rsp-8+arg_10], rsi
0x14003b83a  push    rbp
0x14003b83b  push    rdi
0x14003b83c  push    r14
0x14003b83e  lea     rbp, [rsp-70h]
0x14003b843  sub     rsp, 170h
0x14003b84a  lea     rax, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x14003b851  mov     [rbp+80h+var_A8], 78h ; 'x'
0x14003b858  mov     [rbp+80h+var_C0], rax
0x14003b85c  mov     rsi, rdx
0x14003b85f  xor     edx, edx; Val
0x14003b861  mov     [rbp+80h+var_A4], 1
0x14003b868  lea     rax, aCvsssoftwarepr_3; "CVssSoftwareProviderWrapper::QueryInter"...
0x14003b86f  mov     [rbp+80h+var_A0], 0FFh
0x14003b876  mov     [rbp+80h+var_B8], rax
0x14003b87a  mov     rdi, r8
0x14003b87d  lea     rax, aCorsoftc; "CORSOFTC"
0x14003b884  mov     [rbp+80h+var_20], 1000000h
0x14003b88b  mov     r14, rcx
0x14003b88e  mov     [rbp+80h+var_B0], rax
0x14003b892  lea     r8d, [rdx+78h]; Size
0x14003b896  lea     rcx, [rbp+80h+pv]; void *
0x14003b89a  call    memset_0
0x14003b89f  mov     rax, [rbp+80h+var_B8]
0x14003b8a3  mov     [rsp+180h+var_108], rax
0x14003b8a8  mov     rax, [rbp+80h+var_C0]
0x14003b8ac  mov     [rsp+180h+var_120], rax
0x14003b8b1  mov     rax, [rbp+80h+var_B0]
0x14003b8b5  mov     [rsp+180h+var_118], rax
0x14003b8ba  mov     eax, [rbp+80h+var_A8]
0x14003b8bd  mov     [rsp+180h+var_110], eax
0x14003b8c1  mov     eax, [rbp+80h+var_A4]
0x14003b8c4  mov     [rsp+180h+var_10C], eax
0x14003b8c8  mov     [rsp+180h+var_128], 0
0x14003b8d0  call    cs:__imp_GetTickCount
0x14003b8d6  xorps   xmm0, xmm0
0x14003b8d9  mov     [rsp+180h+var_12C], 0FFFFFFFFh
0x14003b8e1  mov     [rbp+80h+var_FC], eax
0x14003b8e4  lea     rcx, [rbp+80h+arg_0]
0x14003b8eb  mov     eax, [rbp+80h+var_A0]
0x14003b8ee  mov     [rbp+80h+var_F8], eax
0x14003b8f1  mov     [rsp+180h+var_130], 0
0x14003b8f9  mov     [rbp+80h+var_D0], 0
0x14003b901  movups  [rbp+80h+var_F0], xmm0
0x14003b905  mov     [rbp+80h+arg_0], 0
0x14003b910  movups  [rbp+80h+var_E0], xmm0
0x14003b914  call    cs:__imp_VssGetTracingContextPerThread
0x14003b91a  test    eax, eax
0x14003b91c  jns     loc_14003B9C8
0x14003b922  mov     rcx, [rbp+80h+var_D0]
0x14003b926  test    rcx, rcx
0x14003b929  jz      loc_14003BA57
0x14003b92f  mov     eax, [rcx+30h]
0x14003b932  inc     eax
0x14003b934  mov     [rbp+80h+var_100], eax
0x14003b937  cmp     [rbp+80h+var_F8], 0FFh
0x14003b93e  lea     rcx, [rsp+180h+var_130]; this
0x14003b943  mov     ebx, 0A0h
0x14003b948  cmovnz  ebx, [rbp+80h+var_F8]
0x14003b94c  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003b951  test    eax, eax
0x14003b953  jnz     loc_14003BA63
0x14003b959  cmp     byte ptr [rbp+80h+var_20+3], 0
0x14003b95d  jz      short loc_14003B974
0x14003b95f  xor     ebx, ebx
0x14003b961  mov     rcx, [rbp+rbx*8+80h+pv]; pv
0x14003b966  test    rcx, rcx
0x14003b969  jnz     short loc_14003B9B7
0x14003b96b  inc     rbx
0x14003b96e  cmp     rbx, 0Fh
0x14003b972  jnz     short loc_14003B961
0x14003b974  mov     rcx, [r14+8]
0x14003b978  mov     r8, rdi
0x14003b97b  mov     rdx, rsi
0x14003b97e  mov     rax, [rcx]
0x14003b981  mov     rax, [rax]
0x14003b984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b989  mov     [rsp+180h+var_128], eax
0x14003b98d  mov     ebx, eax
0x14003b98f  test    eax, eax
0x14003b991  js      short loc_14003B9EA
0x14003b993  lea     rcx, [rsp+180h+var_130]; this
0x14003b998  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003b99d  lea     r11, [rsp+180h+var_10]
0x14003b9a5  mov     eax, ebx
0x14003b9a7  mov     rbx, [r11+28h]
0x14003b9ab  mov     rsi, [r11+30h]
0x14003b9af  mov     rsp, r11
0x14003b9b2  pop     r14
0x14003b9b4  pop     rdi
0x14003b9b5  pop     rbp
0x14003b9b6  retn
0x14003b9b7  call    cs:__imp_CoTaskMemFree
0x14003b9bd  mov     [rbp+rbx*8+80h+pv], 0
0x14003b9c6  jmp     short loc_14003B96B
0x14003b9c8  lea     rcx, [rsp+180h+var_130]
0x14003b9cd  call    cs:__imp_VssSetTracingContextPerThread
0x14003b9d3  mov     rcx, [rbp+80h+var_D0]
0x14003b9d7  test    eax, eax
0x14003b9d9  cmovns  rcx, [rbp+80h+arg_0]
0x14003b9e1  mov     [rbp+80h+var_D0], rcx
0x14003b9e5  jmp     loc_14003B926
0x14003b9ea  lea     rax, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x14003b9f1  mov     [rbp+80h+var_A8], 7Dh ; '}'
0x14003b9f8  mov     [rbp+80h+var_C0], rax
0x14003b9fc  lea     rcx, [rbp+80h+pv]; void *
0x14003ba00  xor     edx, edx; Val
0x14003ba02  mov     [rbp+80h+var_A4], 1
0x14003ba09  lea     rax, aCvsssoftwarepr_3; "CVssSoftwareProviderWrapper::QueryInter"...
0x14003ba10  mov     [rbp+80h+var_A0], 0FFh
0x14003ba17  mov     [rbp+80h+var_B8], rax
0x14003ba1b  lea     rax, aCorsoftc; "CORSOFTC"
0x14003ba22  mov     [rbp+80h+var_B0], rax
0x14003ba26  lea     r8d, [rdx+78h]; Size
0x14003ba2a  mov     [rbp+80h+var_20], 1000000h
0x14003ba31  call    memset_0
0x14003ba36  mov     r9d, ebx
0x14003ba39  lea     r8, aErrorWhileObta; "Error while obtaining an interface inte"...
0x14003ba40  lea     rdx, [rbp+80h+var_C0]
0x14003ba44  lea     rcx, [rsp+180h+var_130]
0x14003ba49  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003ba4e  mov     ebx, [rsp+180h+var_128]
0x14003ba52  jmp     loc_14003B993
0x14003ba57  mov     [rbp+80h+var_100], 0
0x14003ba5e  jmp     loc_14003B937
0x14003ba63  mov     r9d, [rbp+80h+var_100]
0x14003ba67  lea     rax, aEnter; "ENTER"
0x14003ba6e  mov     r8d, [rsp+180h+var_110]
0x14003ba73  mov     rdx, [rsp+180h+var_118]
0x14003ba78  mov     rcx, [rsp+180h+var_120]
0x14003ba7d  mov     [rsp+180h+var_140], 0
0x14003ba86  mov     [rsp+180h+var_148], ebx
0x14003ba8a  mov     [rsp+180h+var_150], rax
0x14003ba8f  mov     rax, [rsp+180h+var_108]
0x14003ba94  mov     [rsp+180h+var_158], rax
0x14003ba99  mov     eax, [rsp+180h+var_10C]
0x14003ba9d  mov     [rsp+180h+var_160], eax
0x14003baa1  call    cs:__imp_VssTraceMessage
0x14003baa7  jmp     loc_14003B959
```

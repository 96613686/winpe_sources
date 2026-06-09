# CVssCriticalSection::CVssCriticalSection(bool)

- ea: `0x140036040`
- end: `0x1400362fa`
- name: `??0CVssCriticalSection@@QEAA@_N@Z`
- size: `698`
- prototype: `CVssCriticalSection *__fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001a90`
- `0x140001ac0`
- `0x140001af0`
- `0x140035f90`
- `0x140046050`

## callees

- `0x1400138e0`
- `0x140013cb0`
- `0x140036040`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140036180`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140036180`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400360dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400361a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400360dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400361a7`
- `VssTrace!__imp_VssTraceMessage` at `0x1400362ef`
- `VssTrace!__imp_VssTraceMessage` at `0x1400362ef`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036262`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036290`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036262`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036290`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140036114`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140036114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036193`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003627b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036193`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003627b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
CVssCriticalSection *__fastcall CVssCriticalSection::CVssCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 v2; // rcx
  unsigned int v3; // r15d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  __int64 j; // rbx
  DWORD v8; // eax
  DWORD v9; // esi
  int v11; // eax
  __int64 v12; // [rsp+20h] [rbp-E0h]
  __int64 v13; // [rsp+28h] [rbp-D8h]
  __int64 v14; // [rsp+30h] [rbp-D0h]
  __int64 v15; // [rsp+38h] [rbp-C8h]
  __int64 v16; // [rsp+40h] [rbp-C0h]
  _DWORD v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v19; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v20; // [rsp+68h] [rbp-98h]
  unsigned int v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v23; // [rsp+78h] [rbp-88h]
  unsigned int v24; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v26; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  __int128 v28; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v30; // [rsp+C0h] [rbp-40h]
  const wchar_t *v31; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v32; // [rsp+D0h] [rbp-30h]
  int v33; // [rsp+D8h] [rbp-28h]
  int v34; // [rsp+DCh] [rbp-24h]
  int v35; // [rsp+E0h] [rbp-20h]
  LPVOID v36[15]; // [rsp+E8h] [rbp-18h] BYREF
  int v37; // [rsp+160h] [rbp+60h]
  __int64 v38; // [rsp+1B0h] [rbp+B0h] BYREF

  LOWORD(lpCriticalSection[1].DebugInfo) = 256;
  v30 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  HIDWORD(lpCriticalSection[1].DebugInfo) = 0;
  v31 = L"CVssCriticalSection::CVssCriticalSection";
  v33 = 174;
  v32 = L"INCTYPEH";
  v34 = 11;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(v36, 0, sizeof(v36));
  v23 = L"CVssCriticalSection::CVssCriticalSection";
  v19 = v30;
  v20 = L"INCTYPEH";
  v21 = 174;
  v22 = 11;
  v18 = 0;
  v17[1] = -1;
  TickCount = GetTickCount();
  v26 = 255;
  v17[0] = 0;
  v29 = 0;
  *(_OWORD *)pv = 0;
  v38 = 0;
  v28 = 0;
  if ( (int)VssGetTracingContextPerThread(&v38) >= 0 )
  {
    v11 = VssSetTracingContextPerThread(v17);
    v2 = v29;
    if ( v11 >= 0 )
      v2 = v38;
    v29 = v2;
  }
  else
  {
    v2 = v29;
  }
  if ( v2 )
    v24 = *(_DWORD *)(v2 + 48) + 1;
  else
    v24 = 0;
  v3 = 160;
  v4 = 160;
  if ( v26 != 255 )
    v4 = v26;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v17) )
    VssTraceMessage(v19, v20, v21, v24, v22, v23, L"ENTER", v4, 0);
  if ( HIBYTE(v37) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v6 = v36[i];
      if ( v6 )
      {
        CoTaskMemFree(v6);
        v36[i] = 0;
      }
    }
  }
  InitializeCriticalSection(lpCriticalSection);
  LOBYTE(lpCriticalSection[1].DebugInfo) = 1;
  for ( j = 0; j != 4; ++j )
  {
    CoTaskMemFree(pv[j]);
    pv[j] = 0;
  }
  v8 = GetTickCount();
  v9 = v8 - TickCount;
  if ( v26 != 255 )
    v3 = v26;
  LODWORD(v15) = (v8 - TickCount) % 0x3E8;
  LODWORD(v14) = (v8 - TickCount) / 0x3E8 % 0x3C;
  LODWORD(v13) = v9 / 0xEA60 % 0x3C;
  LODWORD(v12) = v9 / 0x36EE80 % 0x3C;
  LODWORD(v16) = v8 - TickCount;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v17,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v12,
    v13,
    v14,
    v15,
    v16,
    v18);
  VssSetTracingContextPerThread(v29);
  return (CVssCriticalSection *)lpCriticalSection;
}

```

## disassembly

```asm
0x140036040  push    rbp
0x140036042  push    rbx
0x140036043  push    rsi
0x140036044  push    rdi
0x140036045  push    r14
0x140036047  push    r15
0x140036049  lea     rbp, [rsp-78h]
0x14003604e  sub     rsp, 178h
0x140036055  lea     rax, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x14003605c  mov     word ptr [rcx+28h], 100h
0x140036062  mov     [rbp+0A0h+var_E0], rax
0x140036066  xor     edi, edi
0x140036068  lea     rax, aCvsscriticalse_2; "CVssCriticalSection::CVssCriticalSectio"...
0x14003606f  mov     [rcx+2Ch], edi
0x140036072  mov     [rbp+0A0h+var_D8], rax
0x140036076  mov     r14, rcx
0x140036079  lea     rax, aInctypeh; "INCTYPEH"
0x140036080  mov     [rbp+0A0h+var_C8], 0AEh
0x140036087  xor     edx, edx; Val
0x140036089  mov     [rbp+0A0h+var_D0], rax
0x14003608d  lea     r8d, [rdi+78h]; Size
0x140036091  mov     [rbp+0A0h+var_C4], 0Bh
0x140036098  lea     rcx, [rbp+0A0h+var_B8]; void *
0x14003609c  mov     [rbp+0A0h+var_C0], 0FFh
0x1400360a3  mov     [rbp+0A0h+var_40], 1000000h
0x1400360aa  call    memset_0
0x1400360af  mov     rax, [rbp+0A0h+var_D8]
0x1400360b3  mov     [rsp+1A0h+var_128], rax
0x1400360b8  mov     rax, [rbp+0A0h+var_E0]
0x1400360bc  mov     [rsp+1A0h+var_140], rax
0x1400360c1  mov     rax, [rbp+0A0h+var_D0]
0x1400360c5  mov     [rsp+1A0h+var_138], rax
0x1400360ca  mov     eax, [rbp+0A0h+var_C8]
0x1400360cd  mov     [rsp+1A0h+var_130], eax
0x1400360d1  mov     eax, [rbp+0A0h+var_C4]
0x1400360d4  mov     [rsp+1A0h+var_12C], eax
0x1400360d8  mov     [rsp+1A0h+var_148], edi
0x1400360dc  call    cs:__imp_GetTickCount
0x1400360e2  xorps   xmm0, xmm0
0x1400360e5  mov     [rsp+1A0h+var_14C], 0FFFFFFFFh
0x1400360ed  mov     [rbp+0A0h+var_11C], eax
0x1400360f0  lea     rcx, [rbp+0A0h+arg_0]
0x1400360f7  mov     eax, [rbp+0A0h+var_C0]
0x1400360fa  mov     [rbp+0A0h+var_118], eax
0x1400360fd  mov     [rsp+1A0h+var_150], edi
0x140036101  mov     [rbp+0A0h+var_F0], rdi
0x140036105  movups  xmmword ptr [rbp+0A0h+pv], xmm0
0x140036109  mov     [rbp+0A0h+arg_0], rdi
0x140036110  movups  [rbp+0A0h+var_100], xmm0
0x140036114  call    cs:__imp_VssGetTracingContextPerThread
0x14003611a  test    eax, eax
0x14003611c  jns     loc_14003628B
0x140036122  mov     rcx, [rbp+0A0h+var_F0]
0x140036126  test    rcx, rcx
0x140036129  jz      loc_1400362AD
0x14003612f  mov     eax, [rcx+30h]
0x140036132  inc     eax
0x140036134  mov     [rbp+0A0h+var_120], eax
0x140036137  cmp     [rbp+0A0h+var_118], 0FFh
0x14003613e  lea     rcx, [rsp+1A0h+var_150]; this
0x140036143  mov     r15d, 0A0h
0x140036149  mov     ebx, r15d
0x14003614c  cmovnz  ebx, [rbp+0A0h+var_118]
0x140036150  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140036155  test    eax, eax
0x140036157  jnz     loc_1400362B5
0x14003615d  cmp     byte ptr [rbp+0A0h+var_40+3], dil
0x140036161  jz      short loc_14003617D
0x140036163  mov     rbx, rdi
0x140036166  mov     rcx, [rbp+rbx*8+0A0h+var_B8]; pv
0x14003616b  test    rcx, rcx
0x14003616e  jnz     loc_14003627B
0x140036174  inc     rbx
0x140036177  cmp     rbx, 0Fh
0x14003617b  jnz     short loc_140036166
0x14003617d  mov     rcx, r14; lpCriticalSection
0x140036180  call    cs:__imp_InitializeCriticalSection
0x140036186  mov     byte ptr [r14+28h], 1
0x14003618b  mov     rbx, rdi
0x14003618e  mov     rcx, [rbp+rbx*8+0A0h+pv]; pv
0x140036193  call    cs:__imp_CoTaskMemFree
0x140036199  mov     [rbp+rbx*8+0A0h+pv], rdi
0x14003619e  inc     rbx
0x1400361a1  cmp     rbx, 4
0x1400361a5  jnz     short loc_14003618E
0x1400361a7  call    cs:__imp_GetTickCount
0x1400361ad  mov     r9d, [rsp+1A0h+var_148]
0x1400361b2  mov     r8d, 88888889h
0x1400361b8  mov     esi, eax
0x1400361ba  mov     [rsp+1A0h+var_158], r9d
0x1400361bf  sub     esi, [rbp+0A0h+var_11C]
0x1400361c2  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x1400361c9  mov     eax, 10624DD3h
0x1400361ce  mov     dword ptr [rsp+1A0h+var_160], esi
0x1400361d2  mul     esi
0x1400361d4  mov     eax, r8d
0x1400361d7  mov     edi, edx
0x1400361d9  shr     edi, 6
0x1400361dc  mul     edi
0x1400361de  mov     eax, 45E7B273h
0x1400361e3  mov     ebx, edi
0x1400361e5  shr     edx, 5
0x1400361e8  imul    ecx, edx, 3Ch ; '<'
0x1400361eb  mul     esi
0x1400361ed  sub     ebx, ecx
0x1400361ef  mov     eax, r8d
0x1400361f2  mov     r11d, edx
0x1400361f5  shr     r11d, 0Eh
0x1400361f9  mul     r11d
0x1400361fc  mov     eax, 95217CB1h
0x140036201  shr     edx, 5
0x140036204  imul    ecx, edx, 3Ch ; '<'
0x140036207  mul     esi
0x140036209  sub     r11d, ecx
0x14003620c  mov     eax, r8d
0x14003620f  mov     r10d, edx
0x140036212  mov     ecx, esi
0x140036214  shr     r10d, 15h
0x140036218  mul     r10d
0x14003621b  shr     edx, 5
0x14003621e  imul    eax, edx, 3Ch ; '<'
0x140036221  lea     rdx, aExit; "EXIT"
0x140036228  sub     r10d, eax
0x14003622b  cmp     [rbp+0A0h+var_118], 0FFh
0x140036232  cmovnz  r15d, [rbp+0A0h+var_118]
0x140036237  imul    eax, edi, 3E8h
0x14003623d  mov     r8d, r15d; unsigned int
0x140036240  sub     ecx, eax
0x140036242  mov     dword ptr [rsp+1A0h+var_168], ecx
0x140036246  lea     rcx, [rsp+1A0h+var_150]; this
0x14003624b  mov     dword ptr [rsp+1A0h+var_170], ebx
0x14003624f  mov     dword ptr [rsp+1A0h+var_178], r11d
0x140036254  mov     dword ptr [rsp+1A0h+var_180], r10d
0x140036259  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14003625e  mov     rcx, [rbp+0A0h+var_F0]
0x140036262  call    cs:__imp_VssSetTracingContextPerThread
0x140036268  mov     rax, r14
0x14003626b  add     rsp, 178h
0x140036272  pop     r15
0x140036274  pop     r14
0x140036276  pop     rdi
0x140036277  pop     rsi
0x140036278  pop     rbx
0x140036279  pop     rbp
0x14003627a  retn
0x14003627b  call    cs:__imp_CoTaskMemFree
0x140036281  mov     [rbp+rbx*8+0A0h+var_B8], rdi
0x140036286  jmp     loc_140036174
0x14003628b  lea     rcx, [rsp+1A0h+var_150]
0x140036290  call    cs:__imp_VssSetTracingContextPerThread
0x140036296  mov     rcx, [rbp+0A0h+var_F0]
0x14003629a  test    eax, eax
0x14003629c  cmovns  rcx, [rbp+0A0h+arg_0]
0x1400362a4  mov     [rbp+0A0h+var_F0], rcx
0x1400362a8  jmp     loc_140036126
0x1400362ad  mov     [rbp+0A0h+var_120], edi
0x1400362b0  jmp     loc_140036137
0x1400362b5  mov     r9d, [rbp+0A0h+var_120]
0x1400362b9  lea     rax, aEnter; "ENTER"
0x1400362c0  mov     r8d, [rsp+1A0h+var_130]
0x1400362c5  mov     rdx, [rsp+1A0h+var_138]
0x1400362ca  mov     rcx, [rsp+1A0h+var_140]
0x1400362cf  mov     [rsp+1A0h+var_160], rdi
0x1400362d4  mov     dword ptr [rsp+1A0h+var_168], ebx
0x1400362d8  mov     [rsp+1A0h+var_170], rax
0x1400362dd  mov     rax, [rsp+1A0h+var_128]
0x1400362e2  mov     [rsp+1A0h+var_178], rax
0x1400362e7  mov     eax, [rsp+1A0h+var_12C]
0x1400362eb  mov     dword ptr [rsp+1A0h+var_180], eax
0x1400362ef  call    cs:__imp_VssTraceMessage
0x1400362f5  jmp     loc_14003615D
```

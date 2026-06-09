# CVssQueuedVolume::OnInit(void)

- ea: `0x140035a30`
- end: `0x140035e8a`
- name: `?OnInit@CVssQueuedVolume@@MEAA_NXZ`
- size: `1114`
- prototype: `bool __fastcall(CVssQueuedVolume *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400137c0`
- `0x1400138e0`
- `0x140013c60`
- `0x140035a30`
- `0x140049ec4`
- `0x1400921dc`
- `0x1400cda78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140035d4c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140035d4c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140035ba7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140035ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035e13`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140035b81`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140035b81`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140035ad3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140035c50`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140035ad3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140035c50`
- `VssTrace!__imp_VssTraceMessage` at `0x140035e08`
- `VssTrace!__imp_VssTraceMessage` at `0x140035e08`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140035d0b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140035d2e`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140035d0b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140035d2e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140035b11`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140035b11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035bf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035c38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035c46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035bf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035c38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140035c46`

## string_xrefs

- `0x140035db5`: `CreateEvent( NULL, TRUE, FALSE, NULL )`
- `0x140035e63`: `::SetThreadPriority(%p, THREAD_PRIORITY_HIGHEST) [0x%08lx]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CVssQueuedVolume::OnInit(CVssQueuedVolume *this)
{
  __int64 v2; // rax
  unsigned int v3; // r14d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  void *v7; // rcx
  HANDLE EventW; // rax
  __int64 v9; // rax
  char v10; // r15
  DWORD v11; // esi
  signed int LastError; // eax
  unsigned int v14; // ebx
  DWORD v15; // ebx
  __int64 v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+28h] [rbp-D8h]
  __int64 v18; // [rsp+30h] [rbp-D0h]
  __int64 v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v23; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v24; // [rsp+68h] [rbp-98h]
  unsigned int v25; // [rsp+70h] [rbp-90h]
  unsigned int v26; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v27; // [rsp+78h] [rbp-88h]
  unsigned int v28; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v30; // [rsp+88h] [rbp-78h]
  LPVOID v31[2]; // [rsp+90h] [rbp-70h]
  LPVOID v32[2]; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v34; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v35; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v36; // [rsp+D0h] [rbp-30h]
  int v37; // [rsp+D8h] [rbp-28h]
  int v38; // [rsp+DCh] [rbp-24h]
  int v39; // [rsp+E0h] [rbp-20h]
  LPVOID pv[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v41; // [rsp+F8h] [rbp-8h]
  __int128 v42; // [rsp+108h] [rbp+8h]
  __int128 v43; // [rsp+118h] [rbp+18h]
  __int128 v44; // [rsp+128h] [rbp+28h]
  __int128 v45; // [rsp+138h] [rbp+38h]
  __int128 v46; // [rsp+148h] [rbp+48h]
  __int64 v47; // [rsp+158h] [rbp+58h]
  int v48; // [rsp+160h] [rbp+60h]
  __int64 v49; // [rsp+1C0h] [rbp+C0h] BYREF

  v34 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
  v35 = L"CVssQueuedVolume::OnInit";
  v36 = L"CORLOVLC";
  v37 = 197;
  v38 = 1;
  v39 = 255;
  v48 = 0x1000000;
  *(_OWORD *)pv = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v22 = 0;
  v27 = L"CVssQueuedVolume::OnInit";
  v23 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
  v24 = L"CORLOVLC";
  v25 = 197;
  v26 = 1;
  TickCount = GetTickCount();
  v30 = 255;
  v21 = 0xFFFFFFFF00000000uLL;
  v33 = 0;
  *(_OWORD *)v31 = 0;
  *(_OWORD *)v32 = 0;
  v49 = 0;
  if ( (int)VssGetTracingContextPerThread(&v49) < 0 || (int)VssSetTracingContextPerThread(&v21) < 0 )
  {
    v2 = v33;
  }
  else
  {
    v2 = v49;
    v33 = v49;
  }
  if ( v2 )
    v28 = *(_DWORD *)(v2 + 48) + 1;
  else
    v28 = 0;
  v3 = 160;
  v4 = 160;
  if ( v30 != 255 )
    v4 = v30;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v21, v26) )
    VssTraceMessage(v23, v24, v25, v28, v26, v27, L"ENTER", v4, 0);
  for ( i = 0; i != 15; ++i )
  {
    v6 = pv[i];
    if ( v6 )
    {
      CoTaskMemFree(v6);
      pv[i] = 0;
    }
  }
  if ( SetThreadPriority(*((HANDLE *)this + 2), 2) )
  {
    v7 = (void *)*((_QWORD *)this + 5);
    if ( v7 )
    {
      ResetEvent(v7);
    }
    else
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 5) = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        v34 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
        v35 = L"CVssQueuedVolume::OnInit";
        v36 = L"CORLOVLC";
        v37 = 215;
        v38 = 1;
        v39 = 255;
        v48 = 0x1000000;
        memset_0(pv, 0, 0x78u);
        CVssFunctionTracer::TranslateGenericError(&v21, &v34, v14, L"CreateEvent( NULL, TRUE, FALSE, NULL )");
      }
    }
    if ( !*((_QWORD *)this + 5) || !*((_QWORD *)this + 6) || !*((_QWORD *)this + 8) )
      goto LABEL_22;
    v9 = *((_QWORD *)this + 12) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v9 )
      v9 = *((_QWORD *)this + 13) - *(_QWORD *)GUID_NULL.Data4;
    if ( v9 && *((_DWORD *)this + 28) && *((_WORD *)this + 58) && *((_WORD *)this + 59) )
      v10 = 1;
    else
LABEL_22:
      v10 = 0;
    CoTaskMemFree(v31[0]);
    v31[0] = 0;
    CoTaskMemFree(v31[1]);
    v31[1] = 0;
    CoTaskMemFree(v32[0]);
    v32[0] = 0;
    CoTaskMemFree(v32[1]);
    v32[1] = 0;
    v11 = GetTickCount() - TickCount;
    if ( v30 != 255 )
      v3 = v30;
    LODWORD(v20) = v11;
    LODWORD(v19) = v11 % 0x3E8;
    LODWORD(v18) = v11 / 0x3E8 % 0x3C;
    LODWORD(v17) = v11 / 0xEA60 % 0x3C;
    LODWORD(v16) = v11 / 0x36EE80 % 0x3C;
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v21,
      L"EXIT",
      v3,
      L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
      v16,
      v17,
      v18,
      v19,
      v20,
      v22);
    VssSetTracingContextPerThread(v33);
    return v10;
  }
  else
  {
    v15 = GetLastError();
    v34 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
    v35 = L"CVssQueuedVolume::OnInit";
    v36 = L"CORLOVLC";
    v37 = 204;
    v38 = 1;
    v39 = 255;
    v48 = 0x1000000;
    memset_0(pv, 0, 0x78u);
    LODWORD(v16) = v15;
    CVssFunctionTracer::LogGenericWarning(
      &v21,
      &v34,
      L"::SetThreadPriority(%p, THREAD_PRIORITY_HIGHEST) [0x%08lx]",
      *((_QWORD *)this + 2),
      v16);
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v21);
    return 0;
  }
}

```

## disassembly

```asm
0x140035a30  push    rbp
0x140035a32  push    rbx
0x140035a33  push    rsi
0x140035a34  push    rdi
0x140035a35  push    r12
0x140035a37  push    r13
0x140035a39  push    r14
0x140035a3b  push    r15
0x140035a3d  lea     rbp, [rsp-78h]
0x140035a42  sub     rsp, 178h
0x140035a49  mov     rdi, rcx
0x140035a4c  lea     r12, aBaseStorVssMod_3; "base\\stor\\vss\\modules\\coord\\src\\l"...
0x140035a53  mov     [rbp+0B0h+var_F0], r12
0x140035a57  lea     r13, aCvssqueuedvolu_1; "CVssQueuedVolume::OnInit"
0x140035a5e  mov     [rbp+0B0h+var_E8], r13
0x140035a62  lea     rcx, aCorlovlc; "CORLOVLC"
0x140035a69  mov     [rbp+0B0h+var_E0], rcx
0x140035a6d  mov     [rbp+0B0h+var_D8], 0C5h
0x140035a74  mov     [rbp+0B0h+var_D4], 1
0x140035a7b  mov     [rbp+0B0h+var_D0], 0FFh
0x140035a82  xor     esi, esi
0x140035a84  mov     [rbp+0B0h+var_50], 1000000h
0x140035a8b  xorps   xmm0, xmm0
0x140035a8e  xor     eax, eax
0x140035a90  movups  xmmword ptr [rbp+0B0h+pv], xmm0
0x140035a94  movups  [rbp+0B0h+var_B8], xmm0
0x140035a98  movups  [rbp+0B0h+var_A8], xmm0
0x140035a9c  movups  [rbp+0B0h+var_98], xmm0
0x140035aa0  movups  [rbp+0B0h+var_88], xmm0
0x140035aa4  movups  [rbp+0B0h+var_78], xmm0
0x140035aa8  movups  [rbp+0B0h+var_68], xmm0
0x140035aac  mov     [rbp+0B0h+var_58], rax
0x140035ab0  mov     [rsp+1B0h+var_158], esi
0x140035ab4  mov     [rsp+1B0h+var_138], r13
0x140035ab9  mov     [rsp+1B0h+var_150], r12
0x140035abe  mov     [rsp+1B0h+var_148], rcx
0x140035ac3  mov     [rsp+1B0h+var_140], 0C5h
0x140035acb  mov     [rsp+1B0h+var_13C], 1
0x140035ad3  call    cs:__imp_GetTickCount
0x140035ad9  mov     [rbp+0B0h+var_12C], eax
0x140035adc  mov     [rsp+1B0h+var_15C], 0FFFFFFFFh
0x140035ae4  mov     [rbp+0B0h+var_128], 0FFh
0x140035aeb  mov     [rsp+1B0h+var_160], esi
0x140035aef  mov     [rbp+0B0h+var_100], rsi
0x140035af3  xorps   xmm0, xmm0
0x140035af6  movdqa  xmmword ptr [rbp+0B0h+var_120], xmm0
0x140035afb  xorps   xmm1, xmm1
0x140035afe  movdqa  xmmword ptr [rbp+0B0h+var_110], xmm1
0x140035b03  mov     [rbp+0B0h+arg_0], rsi
0x140035b0a  lea     rcx, [rbp+0B0h+arg_0]
0x140035b11  call    cs:__imp_VssGetTracingContextPerThread
0x140035b17  test    eax, eax
0x140035b19  jns     loc_140035D29
0x140035b1f  mov     rax, [rbp+0B0h+var_100]
0x140035b23  test    rax, rax
0x140035b26  jz      loc_140035D58
0x140035b2c  mov     eax, [rax+30h]
0x140035b2f  inc     eax
0x140035b31  mov     [rbp+0B0h+var_130], eax
0x140035b34  mov     r14d, 0A0h
0x140035b3a  mov     ebx, r14d
0x140035b3d  cmp     [rbp+0B0h+var_128], 0FFh
0x140035b44  cmovnz  ebx, [rbp+0B0h+var_128]
0x140035b48  mov     edx, [rsp+1B0h+var_13C]; unsigned int
0x140035b4c  lea     rcx, [rsp+1B0h+var_160]; this
0x140035b51  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140035b56  test    eax, eax
0x140035b58  jnz     loc_140035DCE
0x140035b5e  mov     rbx, rsi
0x140035b61  mov     rcx, [rbp+rbx*8+0B0h+pv]; pv
0x140035b66  test    rcx, rcx
0x140035b69  jnz     loc_140035BF1
0x140035b6f  inc     rbx
0x140035b72  cmp     rbx, 0Fh
0x140035b76  jnz     short loc_140035B61
0x140035b78  mov     edx, 2; nPriority
0x140035b7d  mov     rcx, [rdi+10h]; hThread
0x140035b81  call    cs:__imp_SetThreadPriority
0x140035b87  test    eax, eax
0x140035b89  jz      loc_140035E13
0x140035b8f  mov     rcx, [rdi+28h]; hEvent
0x140035b93  test    rcx, rcx
0x140035b96  jnz     loc_140035D4C
0x140035b9c  xor     r9d, r9d; lpName
0x140035b9f  xor     r8d, r8d; bInitialState
0x140035ba2  mov     edx, 1; bManualReset
0x140035ba7  call    cs:__imp_CreateEventW
0x140035bad  mov     [rdi+28h], rax
0x140035bb1  test    rax, rax
0x140035bb4  jz      loc_140035D60
0x140035bba  cmp     qword ptr [rdi+28h], 0
0x140035bbf  jz      short loc_140035BEC
0x140035bc1  cmp     qword ptr [rdi+30h], 0
0x140035bc6  jz      short loc_140035BEC
0x140035bc8  cmp     qword ptr [rdi+40h], 0
0x140035bcd  jz      short loc_140035BEC
0x140035bcf  mov     rax, [rdi+60h]
0x140035bd3  sub     rax, qword ptr cs:GUID_NULL.Data1
0x140035bda  jnz     short loc_140035BE7
0x140035bdc  mov     rax, [rdi+68h]
0x140035be0  sub     rax, qword ptr cs:GUID_NULL.Data4
0x140035be7  test    rax, rax
0x140035bea  jnz     short loc_140035C01
0x140035bec  xor     r15b, r15b
0x140035bef  jmp     short loc_140035C18
0x140035bf1  call    cs:__imp_CoTaskMemFree
0x140035bf7  mov     [rbp+rbx*8+0B0h+pv], rsi
0x140035bfc  jmp     loc_140035B6F
0x140035c01  cmp     dword ptr [rdi+70h], 0
0x140035c05  jz      short loc_140035BEC
0x140035c07  cmp     word ptr [rdi+74h], 0
0x140035c0c  jz      short loc_140035BEC
0x140035c0e  cmp     word ptr [rdi+76h], 0
0x140035c13  jz      short loc_140035BEC
0x140035c15  mov     r15b, 1
0x140035c18  mov     rcx, [rbp+0B0h+var_120]; pv
0x140035c1c  call    cs:__imp_CoTaskMemFree
0x140035c22  mov     [rbp+0B0h+var_120], rsi
0x140035c26  mov     rcx, [rbp+0B0h+var_120+8]; pv
0x140035c2a  call    cs:__imp_CoTaskMemFree
0x140035c30  mov     [rbp+0B0h+var_120+8], rsi
0x140035c34  mov     rcx, [rbp+0B0h+var_110]; pv
0x140035c38  call    cs:__imp_CoTaskMemFree
0x140035c3e  mov     [rbp+0B0h+var_110], rsi
0x140035c42  mov     rcx, [rbp+0B0h+var_110+8]; pv
0x140035c46  call    cs:__imp_CoTaskMemFree
0x140035c4c  mov     [rbp+0B0h+var_110+8], rsi
0x140035c50  call    cs:__imp_GetTickCount
0x140035c56  mov     esi, eax
0x140035c58  sub     esi, [rbp+0B0h+var_12C]
0x140035c5b  mov     eax, 10624DD3h
0x140035c60  mul     esi
0x140035c62  mov     edi, edx
0x140035c64  shr     edi, 6
0x140035c67  mov     eax, 88888889h
0x140035c6c  mul     edi
0x140035c6e  shr     edx, 5
0x140035c71  imul    ecx, edx, 3Ch ; '<'
0x140035c74  mov     ebx, edi
0x140035c76  sub     ebx, ecx
0x140035c78  mov     eax, 45E7B273h
0x140035c7d  mul     esi
0x140035c7f  mov     r11d, edx
0x140035c82  shr     r11d, 0Eh
0x140035c86  mov     eax, 88888889h
0x140035c8b  mul     r11d
0x140035c8e  shr     edx, 5
0x140035c91  imul    ecx, edx, 3Ch ; '<'
0x140035c94  sub     r11d, ecx
0x140035c97  mov     eax, 95217CB1h
0x140035c9c  mul     esi
0x140035c9e  mov     r10d, edx
0x140035ca1  shr     r10d, 15h
0x140035ca5  mov     eax, 88888889h
0x140035caa  mul     r10d
0x140035cad  shr     edx, 5
0x140035cb0  imul    eax, edx, 3Ch ; '<'
0x140035cb3  sub     r10d, eax
0x140035cb6  mov     r9d, [rsp+1B0h+var_158]
0x140035cbb  cmp     [rbp+0B0h+var_128], 0FFh
0x140035cc2  cmovnz  r14d, [rbp+0B0h+var_128]
0x140035cc7  imul    ecx, edi, 3E8h
0x140035ccd  mov     edx, esi
0x140035ccf  sub     edx, ecx
0x140035cd1  mov     [rsp+1B0h+var_168], r9d
0x140035cd6  mov     dword ptr [rsp+1B0h+var_170], esi
0x140035cda  mov     dword ptr [rsp+1B0h+var_178], edx
0x140035cde  mov     dword ptr [rsp+1B0h+var_180], ebx
0x140035ce2  mov     dword ptr [rsp+1B0h+var_188], r11d
0x140035ce7  mov     dword ptr [rsp+1B0h+var_190], r10d
0x140035cec  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140035cf3  mov     r8d, r14d; unsigned int
0x140035cf6  lea     rdx, aExit; "EXIT"
0x140035cfd  lea     rcx, [rsp+1B0h+var_160]; this
0x140035d02  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140035d07  mov     rcx, [rbp+0B0h+var_100]
0x140035d0b  call    cs:__imp_VssSetTracingContextPerThread
0x140035d11  movzx   eax, r15b
0x140035d15  add     rsp, 178h
0x140035d1c  pop     r15
0x140035d1e  pop     r14
0x140035d20  pop     r13
0x140035d22  pop     r12
0x140035d24  pop     rdi
0x140035d25  pop     rsi
0x140035d26  pop     rbx
0x140035d27  pop     rbp
0x140035d28  retn
0x140035d29  lea     rcx, [rsp+1B0h+var_160]
0x140035d2e  call    cs:__imp_VssSetTracingContextPerThread
0x140035d34  test    eax, eax
0x140035d36  js      loc_140035B1F
0x140035d3c  mov     rax, [rbp+0B0h+arg_0]
0x140035d43  mov     [rbp+0B0h+var_100], rax
0x140035d47  jmp     loc_140035B23
0x140035d4c  call    cs:__imp_ResetEvent
0x140035d52  nop
0x140035d53  jmp     loc_140035BBA
0x140035d58  mov     [rbp+0B0h+var_130], esi
0x140035d5b  jmp     loc_140035B34
0x140035d60  call    cs:__imp_GetLastError
0x140035d66  mov     ebx, eax
0x140035d68  test    eax, eax
0x140035d6a  jle     short loc_140035D75
0x140035d6c  movzx   ebx, ax
0x140035d6f  or      ebx, 80070000h
0x140035d75  mov     [rbp+0B0h+var_F0], r12
0x140035d79  mov     [rbp+0B0h+var_E8], r13
0x140035d7d  lea     rax, aCorlovlc; "CORLOVLC"
0x140035d84  mov     [rbp+0B0h+var_E0], rax
0x140035d88  mov     [rbp+0B0h+var_D8], 0D7h
0x140035d8f  mov     [rbp+0B0h+var_D4], 1
0x140035d96  mov     [rbp+0B0h+var_D0], 0FFh
0x140035d9d  mov     [rbp+0B0h+var_50], 1000000h
0x140035da4  xor     edx, edx; Val
0x140035da6  mov     r8d, 78h ; 'x'; Size
0x140035dac  lea     rcx, [rbp+0B0h+pv]; void *
0x140035db0  call    memset_0
0x140035db5  lea     r9, aCreateeventNul_0; "CreateEvent( NULL, TRUE, FALSE, NULL )"
0x140035dbc  mov     r8d, ebx
0x140035dbf  lea     rdx, [rbp+0B0h+var_F0]
0x140035dc3  lea     rcx, [rsp+1B0h+var_160]
0x140035dc8  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140035dce  mov     [rsp+1B0h+var_170], rsi
0x140035dd3  mov     dword ptr [rsp+1B0h+var_178], ebx
0x140035dd7  lea     rax, aEnter; "ENTER"
0x140035dde  mov     [rsp+1B0h+var_180], rax
0x140035de3  mov     rax, [rsp+1B0h+var_138]
0x140035de8  mov     [rsp+1B0h+var_188], rax
0x140035ded  mov     eax, [rsp+1B0h+var_13C]
0x140035df1  mov     dword ptr [rsp+1B0h+var_190], eax
0x140035df5  mov     r9d, [rbp+0B0h+var_130]
0x140035df9  mov     r8d, [rsp+1B0h+var_140]
0x140035dfe  mov     rdx, [rsp+1B0h+var_148]
0x140035e03  mov     rcx, [rsp+1B0h+var_150]
0x140035e08  call    cs:__imp_VssTraceMessage
0x140035e0e  jmp     loc_140035B5E
0x140035e13  call    cs:__imp_GetLastError
0x140035e19  mov     ebx, eax
0x140035e1b  mov     [rbp+0B0h+var_F0], r12
0x140035e1f  mov     [rbp+0B0h+var_E8], r13
0x140035e23  lea     rax, aCorlovlc; "CORLOVLC"
0x140035e2a  mov     [rbp+0B0h+var_E0], rax
0x140035e2e  mov     [rbp+0B0h+var_D8], 0CCh
0x140035e35  mov     [rbp+0B0h+var_D4], 1
0x140035e3c  mov     [rbp+0B0h+var_D0], 0FFh
0x140035e43  mov     [rbp+0B0h+var_50], 1000000h
0x140035e4a  xor     edx, edx; Val
0x140035e4c  mov     r8d, 78h ; 'x'; Size
0x140035e52  lea     rcx, [rbp+0B0h+pv]; void *
0x140035e56  call    memset_0
0x140035e5b  mov     dword ptr [rsp+1B0h+var_190], ebx
0x140035e5f  mov     r9, [rdi+10h]
0x140035e63  lea     r8, aSetthreadprior; "::SetThreadPriority(%p, THREAD_PRIORITY"...
0x140035e6a  lea     rdx, [rbp+0B0h+var_F0]
0x140035e6e  lea     rcx, [rsp+1B0h+var_160]
0x140035e73  call    ?LogGenericWarning@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::LogGenericWarning(CVssDebugInfo,ushort const *,...)
0x140035e78  nop
0x140035e79  lea     rcx, [rsp+1B0h+var_160]; this
0x140035e7e  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140035e83  xor     al, al
0x140035e85  jmp     loc_140035D15
```

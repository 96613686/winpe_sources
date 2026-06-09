# CVssWorkerThread::PrepareJob(void)

- ea: `0x140032990`
- end: `0x140032fc5`
- name: `?PrepareJob@CVssWorkerThread@@QEAAJXZ`
- size: `1589`
- prototype: `__int64 __fastcall(CVssWorkerThread *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x140040c48`
- `0x1400571a4`
- `0x14006b728`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140032990`
- `0x140032fcc`
- `0x1400330fc`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x140032b0d`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x140032b0d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140032b1c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140032bd1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140032e7c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140032e8b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140032f43`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140032b1c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140032bd1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140032e7c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140032e8b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140032f43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140032a32`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140032c8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140032a32`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140032c8f`
- `VssTrace!__imp_VssTraceMessage` at `0x140032e67`
- `VssTrace!__imp_VssTraceMessage` at `0x140032e67`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140032d48`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140032d9f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140032d48`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140032d9f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140032a6e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140032a6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032c5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032c77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032c85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032d8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032c5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032c77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032c85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140032d8b`

## string_xrefs

- `0x1400329bb`: `CVssWorkerThread::PrepareJob`
- `0x140032b68`: `_beginthreadex failed. errno = 0x%08lx`
- `0x140032ed7`: `_beginthreadex failed. errno = 0x%08lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssWorkerThread::PrepareJob(CVssWorkerThread *this)
{
  __int64 v2; // rax
  unsigned int v3; // r14d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  __int64 v7; // rax
  unsigned int *v8; // rbx
  struct CVssDebugInfo *v9; // rbx
  DWORD *v10; // rax
  CVssDebugInfo *v11; // rax
  __int64 j; // rbx
  void *v13; // rcx
  __int64 k; // rbx
  void *v15; // rcx
  DWORD v16; // esi
  unsigned int *v18; // rbx
  struct CVssDebugInfo *v19; // rbx
  DWORD *v20; // rax
  CVssDebugInfo *v21; // rax
  __int64 v22; // [rsp+20h] [rbp-E0h]
  __int64 v23; // [rsp+28h] [rbp-D8h]
  __int64 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  __int64 v26; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v27; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v28; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+68h] [rbp-98h]
  int v31; // [rsp+6Ch] [rbp-94h]
  int v32; // [rsp+70h] [rbp-90h]
  LPVOID v33[15]; // [rsp+78h] [rbp-88h] BYREF
  int v34; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v35; // [rsp+100h] [rbp+0h] BYREF
  int v36; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v37; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v38; // [rsp+118h] [rbp+18h]
  unsigned int v39; // [rsp+120h] [rbp+20h]
  unsigned int v40; // [rsp+124h] [rbp+24h]
  const wchar_t *v41; // [rsp+128h] [rbp+28h]
  unsigned int v42; // [rsp+130h] [rbp+30h]
  DWORD TickCount; // [rsp+134h] [rbp+34h]
  unsigned int v44; // [rsp+138h] [rbp+38h]
  LPVOID pv[2]; // [rsp+140h] [rbp+40h]
  LPVOID v46[2]; // [rsp+150h] [rbp+50h]
  __int64 v47; // [rsp+160h] [rbp+60h]
  _BYTE v48[40]; // [rsp+170h] [rbp+70h] BYREF
  LPVOID v49[15]; // [rsp+198h] [rbp+98h]
  char v50; // [rsp+213h] [rbp+113h]
  _BYTE v51[232]; // [rsp+218h] [rbp+118h] BYREF
  __int64 v52; // [rsp+310h] [rbp+210h] BYREF

  v27 = L"base\\stor\\vss\\inc\\worker.hxx";
  v28 = L"CVssWorkerThread::PrepareJob";
  v29 = L"INCWORKH";
  v30 = 290;
  v31 = 1;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  v36 = 0;
  v41 = L"CVssWorkerThread::PrepareJob";
  v37 = L"base\\stor\\vss\\inc\\worker.hxx";
  v38 = L"INCWORKH";
  v39 = 290;
  v40 = 1;
  TickCount = GetTickCount();
  v44 = 255;
  v35 = 0xFFFFFFFF00000000uLL;
  v47 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v46 = 0;
  v52 = 0;
  if ( (int)VssGetTracingContextPerThread(&v52) < 0 || (int)VssSetTracingContextPerThread(&v35) < 0 )
  {
    v2 = v47;
  }
  else
  {
    v2 = v52;
    v47 = v52;
  }
  if ( v2 )
    v42 = *(_DWORD *)(v2 + 48) + 1;
  else
    v42 = 0;
  v3 = 160;
  v4 = 160;
  if ( v44 != 255 )
    v4 = v44;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v35, v40) )
    VssTraceMessage(v37, v38, v39, v42, v40, v41, L"ENTER", v4, 0);
  if ( HIBYTE(v34) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v6 = v33[i];
      if ( v6 )
      {
        CoTaskMemFree(v6);
        v33[i] = 0;
      }
    }
  }
  if ( *((_QWORD *)this + 2) || *((_DWORD *)this + 7) != 1 )
  {
    v27 = L"base\\stor\\vss\\inc\\worker.hxx";
    v28 = L"CVssWorkerThread::PrepareJob";
    v29 = L"INCWORKH";
    v30 = 295;
    v31 = 11;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::Trace(&v35, &v27, L"Bad state %d", *((unsigned int *)this + 7));
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v35);
    return 2147549183LL;
  }
  else
  {
    v7 = _o__beginthreadex(0, 0, CVssWorkerThread::_ThreadFunction, this, 4, (char *)this + 24);
    if ( v7 )
    {
      if ( v7 == -1 )
      {
        if ( *(_DWORD *)_o__errno() != 11 )
        {
          v18 = (unsigned int *)_o__errno();
          v27 = L"base\\stor\\vss\\inc\\worker.hxx";
          v28 = L"CVssWorkerThread::PrepareJob";
          v29 = L"INCWORKH";
          v30 = 327;
          v31 = 11;
          v32 = 255;
          v34 = 0x1000000;
          memset_0(v33, 0, sizeof(v33));
          CVssFunctionTracer::Trace(&v35, &v27, L"_beginthreadex failed. errno = 0x%08lx", *v18);
          v27 = L"base\\stor\\vss\\inc\\worker.hxx";
          v28 = L"CVssWorkerThread::PrepareJob";
          v29 = L"INCWORKH";
          v30 = 328;
          v31 = 11;
          v32 = 255;
          v34 = 0x1000000;
          memset_0(v33, 0, sizeof(v33));
          v19 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v27, (CVssDebugInfo *)v48, 0xFFFFFFFF);
          v20 = (DWORD *)_o__errno();
          v21 = CVssDebugInfo::operator<<(v19, (CVssDebugInfo *)v51, *v20);
          CVssFunctionTracer::LogError(&v35, 12296, v21, 1);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v48);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v27);
        }
        CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v35);
        return 2147942414LL;
      }
      else
      {
        *((_QWORD *)this + 2) = v7;
        *((_BYTE *)this + 8) = (**(__int64 (__fastcall ***)(CVssWorkerThread *))this)(this);
        *((_DWORD *)this + 7) = 2;
        CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v35);
        return 0;
      }
    }
    else
    {
      v8 = (unsigned int *)_o__errno();
      v27 = L"base\\stor\\vss\\inc\\worker.hxx";
      v28 = L"CVssWorkerThread::PrepareJob";
      v29 = L"INCWORKH";
      v30 = 314;
      v31 = 11;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::Trace(&v35, &v27, L"_beginthreadex failed. errno = 0x%08lx", *v8);
      v27 = L"base\\stor\\vss\\inc\\worker.hxx";
      v28 = L"CVssWorkerThread::PrepareJob";
      v29 = L"INCWORKH";
      v30 = 315;
      v31 = 11;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      v9 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v27, (CVssDebugInfo *)v48, 0);
      v10 = (DWORD *)_o__errno();
      v11 = CVssDebugInfo::operator<<(v9, (CVssDebugInfo *)v51, *v10);
      CVssFunctionTracer::LogError(&v35, 12296, v11, 1);
      if ( v50 )
      {
        for ( j = 0; j != 15; ++j )
        {
          v13 = v49[j];
          if ( v13 )
          {
            CoTaskMemFree(v13);
            v49[j] = 0;
          }
        }
      }
      if ( HIBYTE(v34) )
      {
        for ( k = 0; k != 15; ++k )
        {
          v15 = v33[k];
          if ( v15 )
          {
            CoTaskMemFree(v15);
            v33[k] = 0;
          }
        }
      }
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
      CoTaskMemFree(pv[1]);
      pv[1] = 0;
      CoTaskMemFree(v46[0]);
      v46[0] = 0;
      CoTaskMemFree(v46[1]);
      v46[1] = 0;
      v16 = GetTickCount() - TickCount;
      if ( v44 != 255 )
        v3 = v44;
      LODWORD(v26) = v16;
      LODWORD(v25) = v16 % 0x3E8;
      LODWORD(v24) = v16 / 0x3E8 % 0x3C;
      LODWORD(v23) = v16 / 0xEA60 % 0x3C;
      LODWORD(v22) = v16 / 0x36EE80 % 0x3C;
      CVssFunctionTracer::TraceInternalWithFormat(
        (CVssFunctionTracer *)&v35,
        L"EXIT",
        v3,
        L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
        v22,
        v23,
        v24,
        v25,
        v26,
        v36);
      VssSetTracingContextPerThread(v47);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x140032990  push    rbp
0x140032992  push    rbx
0x140032993  push    rsi
0x140032994  push    rdi
0x140032995  push    r12
0x140032997  push    r13
0x140032999  push    r14
0x14003299b  push    r15
0x14003299d  lea     rbp, [rsp-1C8h]
0x1400329a5  sub     rsp, 2C8h
0x1400329ac  mov     rdi, rcx
0x1400329af  lea     r15, aBaseStorVssInc_0; "base\\stor\\vss\\inc\\worker.hxx"
0x1400329b6  mov     [rsp+300h+var_2B0], r15
0x1400329bb  lea     r12, aCvssworkerthre_1; "CVssWorkerThread::PrepareJob"
0x1400329c2  mov     [rsp+300h+var_2A8], r12
0x1400329c7  lea     r13, aIncworkh; "INCWORKH"
0x1400329ce  mov     [rsp+300h+var_2A0], r13
0x1400329d3  mov     [rsp+300h+var_298], 122h
0x1400329db  mov     [rsp+300h+var_294], 1
0x1400329e3  mov     [rsp+300h+var_290], 0FFh
0x1400329eb  xor     esi, esi
0x1400329ed  mov     [rbp+200h+var_210], 1000000h
0x1400329f4  xor     edx, edx; Val
0x1400329f6  mov     r8d, 78h ; 'x'; Size
0x1400329fc  lea     rcx, [rsp+300h+var_288]; void *
0x140032a01  call    memset_0
0x140032a06  mov     [rbp+200h+var_1F8], esi
0x140032a09  mov     rax, [rsp+300h+var_2A8]
0x140032a0e  mov     [rbp+200h+var_1D8], rax
0x140032a12  mov     rax, [rsp+300h+var_2B0]
0x140032a17  mov     [rbp+200h+var_1F0], rax
0x140032a1b  mov     rax, [rsp+300h+var_2A0]
0x140032a20  mov     [rbp+200h+var_1E8], rax
0x140032a24  mov     eax, [rsp+300h+var_298]
0x140032a28  mov     [rbp+200h+var_1E0], eax
0x140032a2b  mov     eax, [rsp+300h+var_294]
0x140032a2f  mov     [rbp+200h+var_1DC], eax
0x140032a32  call    cs:__imp_GetTickCount
0x140032a38  mov     [rbp+200h+var_1CC], eax
0x140032a3b  mov     [rbp+200h+var_1FC], 0FFFFFFFFh
0x140032a42  mov     eax, [rsp+300h+var_290]
0x140032a46  mov     [rbp+200h+var_1C8], eax
0x140032a49  mov     [rbp+200h+var_200], esi
0x140032a4c  mov     [rbp+200h+var_1A0], rsi
0x140032a50  xorps   xmm0, xmm0
0x140032a53  movdqa  xmmword ptr [rbp+200h+pv], xmm0
0x140032a58  xorps   xmm1, xmm1
0x140032a5b  movdqa  xmmword ptr [rbp+200h+var_1B0], xmm1
0x140032a60  mov     [rbp+200h+arg_0], rsi
0x140032a67  lea     rcx, [rbp+200h+arg_0]
0x140032a6e  call    cs:__imp_VssGetTracingContextPerThread
0x140032a74  test    eax, eax
0x140032a76  jns     loc_140032D9B
0x140032a7c  mov     rax, [rbp+200h+var_1A0]
0x140032a80  test    rax, rax
0x140032a83  jz      loc_140032DBD
0x140032a89  mov     eax, [rax+30h]
0x140032a8c  inc     eax
0x140032a8e  mov     [rbp+200h+var_1D0], eax
0x140032a91  mov     r14d, 0A0h
0x140032a97  mov     ebx, r14d
0x140032a9a  cmp     [rbp+200h+var_1C8], 0FFh
0x140032aa1  cmovnz  ebx, [rbp+200h+var_1C8]
0x140032aa5  mov     edx, [rbp+200h+var_1DC]; unsigned int
0x140032aa8  lea     rcx, [rbp+200h+var_200]; this
0x140032aac  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140032ab1  test    eax, eax
0x140032ab3  jnz     loc_140032E32
0x140032ab9  cmp     byte ptr [rbp+200h+var_210+3], sil
0x140032abd  jz      short loc_140032AD9
0x140032abf  mov     rbx, rsi
0x140032ac2  mov     rcx, [rsp+rbx*8+300h+var_288]; pv
0x140032ac7  test    rcx, rcx
0x140032aca  jnz     loc_140032D67
0x140032ad0  inc     rbx
0x140032ad3  cmp     rbx, 0Fh
0x140032ad7  jnz     short loc_140032AC2
0x140032ad9  cmp     qword ptr [rdi+10h], 0
0x140032ade  jnz     loc_140032DC5
0x140032ae4  cmp     dword ptr [rdi+1Ch], 1
0x140032ae8  jnz     loc_140032DC5
0x140032aee  lea     rax, [rdi+18h]
0x140032af2  mov     [rsp+300h+var_2D8], rax
0x140032af7  mov     dword ptr [rsp+300h+var_2E0], 4
0x140032aff  mov     r9, rdi
0x140032b02  lea     r8, ?_ThreadFunction@CVssWorkerThread@@CAIPEAPEAX@Z; CVssWorkerThread::_ThreadFunction(void * *)
0x140032b09  xor     edx, edx
0x140032b0b  xor     ecx, ecx
0x140032b0d  call    cs:__imp__o__beginthreadex
0x140032b13  test    rax, rax
0x140032b16  jnz     loc_140032E72
0x140032b1c  call    cs:__imp__o__errno
0x140032b22  mov     rbx, rax
0x140032b25  mov     [rsp+300h+var_2B0], r15
0x140032b2a  mov     [rsp+300h+var_2A8], r12
0x140032b2f  mov     [rsp+300h+var_2A0], r13
0x140032b34  mov     [rsp+300h+var_298], 13Ah
0x140032b3c  mov     [rsp+300h+var_294], 0Bh
0x140032b44  mov     [rsp+300h+var_290], 0FFh
0x140032b4c  mov     [rbp+200h+var_210], 1000000h
0x140032b53  xor     edx, edx; Val
0x140032b55  mov     r8d, 78h ; 'x'; Size
0x140032b5b  lea     rcx, [rsp+300h+var_288]; void *
0x140032b60  call    memset_0
0x140032b65  mov     r9d, [rbx]
0x140032b68  lea     r8, aBeginthreadexF; "_beginthreadex failed. errno = 0x%08lx"
0x140032b6f  lea     rdx, [rsp+300h+var_2B0]
0x140032b74  lea     rcx, [rbp+200h+var_200]
0x140032b78  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140032b7d  mov     [rsp+300h+var_2B0], r15
0x140032b82  mov     [rsp+300h+var_2A8], r12
0x140032b87  mov     [rsp+300h+var_2A0], r13
0x140032b8c  mov     [rsp+300h+var_298], 13Bh
0x140032b94  mov     [rsp+300h+var_294], 0Bh
0x140032b9c  mov     [rsp+300h+var_290], 0FFh
0x140032ba4  mov     [rbp+200h+var_210], 1000000h
0x140032bab  xor     edx, edx; Val
0x140032bad  mov     r8d, 78h ; 'x'; Size
0x140032bb3  lea     rcx, [rsp+300h+var_288]; void *
0x140032bb8  call    memset_0
0x140032bbd  xor     r8d, r8d; dwMessageId
0x140032bc0  lea     rdx, [rbp+200h+var_190]; this
0x140032bc4  lea     rcx, [rsp+300h+var_2B0]; struct CVssDebugInfo *
0x140032bc9  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x140032bce  mov     rbx, rax
0x140032bd1  call    cs:__imp__o__errno
0x140032bd7  mov     r8d, [rax]; dwMessageId
0x140032bda  lea     rdx, [rbp+200h+var_E8]; this
0x140032be1  mov     rcx, rbx; struct CVssDebugInfo *
0x140032be4  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x140032be9  mov     r9d, 1
0x140032bef  mov     r8, rax
0x140032bf2  mov     edx, 3008h
0x140032bf7  lea     rcx, [rbp+200h+var_200]
0x140032bfb  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x140032c00  cmp     [rbp+200h+var_ED], 0
0x140032c07  jz      short loc_140032C2A
0x140032c09  mov     rbx, rsi
0x140032c0c  nop     dword ptr [rax+00h]
0x140032c10  mov     rcx, [rbp+rbx*8+200h+var_168]; pv
0x140032c18  test    rcx, rcx
0x140032c1b  jnz     loc_140032D77
0x140032c21  inc     rbx
0x140032c24  cmp     rbx, 0Fh
0x140032c28  jnz     short loc_140032C10
0x140032c2a  cmp     byte ptr [rbp+200h+var_210+3], 0
0x140032c2e  jz      short loc_140032C57
0x140032c30  mov     rbx, rsi
0x140032c33  nop     dword ptr [rax+00h]
0x140032c37  nop     word ptr [rax+rax+00000000h]
0x140032c40  mov     rcx, [rsp+rbx*8+300h+var_288]; pv
0x140032c45  test    rcx, rcx
0x140032c48  jnz     loc_140032D8B
0x140032c4e  inc     rbx
0x140032c51  cmp     rbx, 0Fh
0x140032c55  jnz     short loc_140032C40
0x140032c57  mov     rcx, [rbp+200h+pv]; pv
0x140032c5b  call    cs:__imp_CoTaskMemFree
0x140032c61  mov     [rbp+200h+pv], rsi
0x140032c65  mov     rcx, [rbp+200h+pv+8]; pv
0x140032c69  call    cs:__imp_CoTaskMemFree
0x140032c6f  mov     [rbp+200h+pv+8], rsi
0x140032c73  mov     rcx, [rbp+200h+var_1B0]; pv
0x140032c77  call    cs:__imp_CoTaskMemFree
0x140032c7d  mov     [rbp+200h+var_1B0], rsi
0x140032c81  mov     rcx, [rbp+200h+var_1B0+8]; pv
0x140032c85  call    cs:__imp_CoTaskMemFree
0x140032c8b  mov     [rbp+200h+var_1B0+8], rsi
0x140032c8f  call    cs:__imp_GetTickCount
0x140032c95  mov     esi, eax
0x140032c97  sub     esi, [rbp+200h+var_1CC]
0x140032c9a  mov     eax, 10624DD3h
0x140032c9f  mul     esi
0x140032ca1  mov     edi, edx
0x140032ca3  shr     edi, 6
0x140032ca6  mov     eax, 88888889h
0x140032cab  mul     edi
0x140032cad  shr     edx, 5
0x140032cb0  imul    ecx, edx, 3Ch ; '<'
0x140032cb3  mov     ebx, edi
0x140032cb5  sub     ebx, ecx
0x140032cb7  mov     eax, 45E7B273h
0x140032cbc  mul     esi
0x140032cbe  mov     r11d, edx
0x140032cc1  shr     r11d, 0Eh
0x140032cc5  mov     eax, 88888889h
0x140032cca  mul     r11d
0x140032ccd  shr     edx, 5
0x140032cd0  imul    ecx, edx, 3Ch ; '<'
0x140032cd3  sub     r11d, ecx
0x140032cd6  mov     eax, 95217CB1h
0x140032cdb  mul     esi
0x140032cdd  mov     r10d, edx
0x140032ce0  shr     r10d, 15h
0x140032ce4  mov     eax, 88888889h
0x140032ce9  mul     r10d
0x140032cec  shr     edx, 5
0x140032cef  imul    eax, edx, 3Ch ; '<'
0x140032cf2  sub     r10d, eax
0x140032cf5  mov     r9d, [rbp+200h+var_1F8]
0x140032cf9  cmp     [rbp+200h+var_1C8], 0FFh
0x140032d00  cmovnz  r14d, [rbp+200h+var_1C8]
0x140032d05  imul    eax, edi, 3E8h
0x140032d0b  mov     ecx, esi
0x140032d0d  sub     ecx, eax
0x140032d0f  mov     [rsp+300h+var_2B8], r9d
0x140032d14  mov     dword ptr [rsp+300h+var_2C0], esi
0x140032d18  mov     dword ptr [rsp+300h+var_2C8], ecx
0x140032d1c  mov     dword ptr [rsp+300h+var_2D0], ebx
0x140032d20  mov     dword ptr [rsp+300h+var_2D8], r11d
0x140032d25  mov     dword ptr [rsp+300h+var_2E0], r10d
0x140032d2a  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140032d31  mov     r8d, r14d; unsigned int
0x140032d34  lea     rdx, aExit; "EXIT"
0x140032d3b  lea     rcx, [rbp+200h+var_200]; this
0x140032d3f  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140032d44  mov     rcx, [rbp+200h+var_1A0]
0x140032d48  call    cs:__imp_VssSetTracingContextPerThread
0x140032d4e  mov     eax, 8007000Eh
0x140032d53  add     rsp, 2C8h
0x140032d5a  pop     r15
0x140032d5c  pop     r14
0x140032d5e  pop     r13
0x140032d60  pop     r12
0x140032d62  pop     rdi
0x140032d63  pop     rsi
0x140032d64  pop     rbx
0x140032d65  pop     rbp
0x140032d66  retn
0x140032d67  call    cs:__imp_CoTaskMemFree
0x140032d6d  mov     [rsp+rbx*8+300h+var_288], rsi
0x140032d72  jmp     loc_140032AD0
0x140032d77  call    cs:__imp_CoTaskMemFree
0x140032d7d  nop
0x140032d7e  mov     [rbp+rbx*8+200h+var_168], rsi
0x140032d86  jmp     loc_140032C21
0x140032d8b  call    cs:__imp_CoTaskMemFree
0x140032d91  mov     [rsp+rbx*8+300h+var_288], rsi
0x140032d96  jmp     loc_140032C4E
0x140032d9b  lea     rcx, [rbp+200h+var_200]
0x140032d9f  call    cs:__imp_VssSetTracingContextPerThread
0x140032da5  test    eax, eax
0x140032da7  js      loc_140032A7C
0x140032dad  mov     rax, [rbp+200h+arg_0]
0x140032db4  mov     [rbp+200h+var_1A0], rax
0x140032db8  jmp     loc_140032A80
0x140032dbd  mov     [rbp+200h+var_1D0], esi
0x140032dc0  jmp     loc_140032A91
0x140032dc5  mov     [rsp+300h+var_2B0], r15
0x140032dca  mov     [rsp+300h+var_2A8], r12
0x140032dcf  mov     [rsp+300h+var_2A0], r13
0x140032dd4  mov     [rsp+300h+var_298], 127h
0x140032ddc  mov     [rsp+300h+var_294], 0Bh
0x140032de4  mov     [rsp+300h+var_290], 0FFh
0x140032dec  mov     [rbp+200h+var_210], 1000000h
0x140032df3  xor     edx, edx; Val
0x140032df5  mov     r8d, 78h ; 'x'; Size
0x140032dfb  lea     rcx, [rsp+300h+var_288]; void *
0x140032e00  call    memset_0
0x140032e05  mov     r9d, [rdi+1Ch]
0x140032e09  lea     r8, aBadStateD; "Bad state %d"
0x140032e10  lea     rdx, [rsp+300h+var_2B0]
0x140032e15  lea     rcx, [rbp+200h+var_200]
0x140032e19  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140032e1e  nop
0x140032e1f  lea     rcx, [rbp+200h+var_200]; this
0x140032e23  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140032e28  mov     eax, 8000FFFFh
0x140032e2d  jmp     loc_140032D53
0x140032e32  mov     [rsp+300h+var_2C0], rsi
0x140032e37  mov     dword ptr [rsp+300h+var_2C8], ebx
0x140032e3b  lea     rax, aEnter; "ENTER"
0x140032e42  mov     [rsp+300h+var_2D0], rax
0x140032e47  mov     rax, [rbp+200h+var_1D8]
0x140032e4b  mov     [rsp+300h+var_2D8], rax
0x140032e50  mov     eax, [rbp+200h+var_1DC]
0x140032e53  mov     dword ptr [rsp+300h+var_2E0], eax
0x140032e57  mov     r9d, [rbp+200h+var_1D0]
0x140032e5b  mov     r8d, [rbp+200h+var_1E0]
0x140032e5f  mov     rdx, [rbp+200h+var_1E8]
0x140032e63  mov     rcx, [rbp+200h+var_1F0]
0x140032e67  call    cs:__imp_VssTraceMessage
0x140032e6d  jmp     loc_140032AB9
0x140032e72  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140032e76  jnz     loc_140032F99
0x140032e7c  call    cs:__imp__o__errno
0x140032e82  cmp     dword ptr [rax], 0Bh
0x140032e85  jz      loc_140032F86
0x140032e8b  call    cs:__imp__o__errno
0x140032e91  mov     rbx, rax
0x140032e94  mov     [rsp+300h+var_2B0], r15
0x140032e99  mov     [rsp+300h+var_2A8], r12
0x140032e9e  mov     [rsp+300h+var_2A0], r13
0x140032ea3  mov     [rsp+300h+var_298], 147h
0x140032eab  mov     [rsp+300h+var_294], 0Bh
0x140032eb3  mov     [rsp+300h+var_290], 0FFh
0x140032ebb  mov     [rbp+200h+var_210], 1000000h
0x140032ec2  xor     edx, edx; Val
0x140032ec4  mov     r8d, 78h ; 'x'; Size
0x140032eca  lea     rcx, [rsp+300h+var_288]; void *
  ... truncated ...
```

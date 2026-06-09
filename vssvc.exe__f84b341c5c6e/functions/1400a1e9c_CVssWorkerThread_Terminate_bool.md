# CVssWorkerThread::Terminate(bool)

- ea: `0x1400a1e9c`
- end: `0x1400a2170`
- name: `?Terminate@CVssWorkerThread@@AEAAJ_N@Z`
- size: `724`
- prototype: `__int64 __fastcall(CVssWorkerThread *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140008f7c`

## callees

- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x1400921dc`
- `0x1400a1e9c`
- `0x1400cda78`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400a2055`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400a2055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a1f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a1fcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a2066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a20d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a1f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a1fcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a2066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a20d3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400a1f51`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400a1f51`

## string_xrefs

- `0x1400a1fb7`: `ResumeThread(%p) = -1, GetLastError() == 0x%08lx, m_eThreadState == %d`
- `0x1400a2020`: `ResumeThread failed. Error: 0x%08lx. State: %d`
- `0x1400a1ecb`: `CVssWorkerThread::Terminate`
- `0x1400a20bb`: `WaitForSingleObject(%p,INFINITE) == WAIT_FAILED, GetLastError() == 0x%08lx, m_eThreadState == %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssWorkerThread::Terminate(CVssWorkerThread *this, char a2)
{
  int v4; // edi
  DWORD LastError; // ebx
  int v6; // edi
  DWORD v7; // ebx
  int v9; // edi
  DWORD v10; // ebx
  int v11; // edi
  DWORD v12; // ebx
  unsigned int v13; // ebx
  DWORD v14; // [rsp+20h] [rbp-E0h]
  __int64 v15; // [rsp+20h] [rbp-E0h]
  DWORD v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v20; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v21; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v22; // [rsp+40h] [rbp-C0h]
  int v23; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+4Ch] [rbp-B4h]
  int v25; // [rsp+50h] [rbp-B0h]
  _BYTE v26[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+D0h] [rbp-30h]
  LPVOID v28[14]; // [rsp+E0h] [rbp-20h] BYREF

  v20 = L"base\\stor\\vss\\inc\\worker.hxx";
  v21 = L"CVssWorkerThread::Terminate";
  v22 = L"INCWORKH";
  v23 = 503;
  v24 = 1;
  v25 = 255;
  v27 = 0x1000000;
  memset_0(v26, 0, sizeof(v26));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v28, (__int64)&v20, 0);
  if ( !*((_QWORD *)this + 2) )
    goto LABEL_7;
  *((_BYTE *)this + 9) = 1;
  (*(void (__fastcall **)(CVssWorkerThread *))(*(_QWORD *)this + 24LL))(this);
  if ( a2 && ResumeThread(*((HANDLE *)this + 2)) == -1 )
  {
    v4 = *((_DWORD *)this + 7);
    LastError = GetLastError();
    v20 = L"base\\stor\\vss\\inc\\worker.hxx";
    v21 = L"CVssWorkerThread::Terminate";
    v22 = L"INCWORKH";
    v23 = 522;
    v24 = 11;
    v25 = 255;
    v27 = 0x1000000;
    memset_0(v26, 0, sizeof(v26));
    v18 = v4;
    v14 = LastError;
    CVssFunctionTracer::LogGenericWarning(
      v28,
      &v20,
      L"ResumeThread(%p) = -1, GetLastError() == 0x%08lx, m_eThreadState == %d",
      *((_QWORD *)this + 2),
      v14,
      v18);
    v6 = *((_DWORD *)this + 7);
    v7 = GetLastError();
    v20 = L"base\\stor\\vss\\inc\\worker.hxx";
    v21 = L"CVssWorkerThread::Terminate";
    v22 = L"INCWORKH";
    v23 = 525;
    v24 = 11;
    v25 = 255;
    v27 = 0x1000000;
    memset_0(v26, 0, sizeof(v26));
    LODWORD(v15) = v6;
    CVssFunctionTracer::Trace(v28, &v20, L"ResumeThread failed. Error: 0x%08lx. State: %d", v7, v15);
    *((_DWORD *)this + 7) = 5;
    CVssFunctionTracer::~CVssFunctionTracer(v28);
    return 2147549183LL;
  }
  if ( WaitForSingleObject(*((HANDLE *)this + 2), 0xFFFFFFFF) == -1 )
  {
    v9 = *((_DWORD *)this + 7);
    v10 = GetLastError();
    v20 = L"base\\stor\\vss\\inc\\worker.hxx";
    v21 = L"CVssWorkerThread::Terminate";
    v22 = L"INCWORKH";
    v23 = 537;
    v24 = 11;
    v25 = 255;
    v27 = 0x1000000;
    memset_0(v26, 0, sizeof(v26));
    v19 = v9;
    v16 = v10;
    CVssFunctionTracer::LogGenericWarning(
      v28,
      &v20,
      L"WaitForSingleObject(%p,INFINITE) == WAIT_FAILED, GetLastError() == 0x%08lx, m_eThreadState == %d",
      *((_QWORD *)this + 2),
      v16,
      v19);
    v11 = *((_DWORD *)this + 7);
    v12 = GetLastError();
    v20 = L"base\\stor\\vss\\inc\\worker.hxx";
    v21 = L"CVssWorkerThread::Terminate";
    v22 = L"INCWORKH";
    v23 = 540;
    v24 = 11;
    v25 = 255;
    v27 = 0x1000000;
    memset_0(v26, 0, sizeof(v26));
    LODWORD(v17) = v11;
    CVssFunctionTracer::Trace(v28, &v20, L"WaitForSingleObject failed. Error: 0x%08lx. State: %d", v12, v17);
    *((_DWORD *)this + 7) = 5;
    v13 = -2147418113;
  }
  else
  {
LABEL_7:
    v13 = 0;
  }
  CVssFunctionTracer::~CVssFunctionTracer(v28);
  return v13;
}

```

## disassembly

```asm
0x1400a1e9c  mov     [rsp-8+arg_8], rbx
0x1400a1ea1  mov     [rsp-8+arg_10], rsi
0x1400a1ea6  push    rbp
0x1400a1ea7  push    rdi
0x1400a1ea8  push    r12
0x1400a1eaa  push    r13
0x1400a1eac  push    r14
0x1400a1eae  lea     rbp, [rsp-50h]
0x1400a1eb3  sub     rsp, 150h
0x1400a1eba  mov     bl, dl
0x1400a1ebc  mov     rsi, rcx
0x1400a1ebf  lea     r12, aBaseStorVssInc_0; "base\\stor\\vss\\inc\\worker.hxx"
0x1400a1ec6  mov     [rsp+170h+var_140], r12
0x1400a1ecb  lea     r13, aCvssworkerthre; "CVssWorkerThread::Terminate"
0x1400a1ed2  mov     [rsp+170h+var_138], r13
0x1400a1ed7  lea     r14, aIncworkh; "INCWORKH"
0x1400a1ede  mov     [rsp+170h+var_130], r14
0x1400a1ee3  mov     [rsp+170h+var_128], 1F7h
0x1400a1eeb  mov     [rsp+170h+var_124], 1
0x1400a1ef3  mov     [rsp+170h+var_120], 0FFh
0x1400a1efb  mov     [rbp+70h+var_A0], 1000000h
0x1400a1f02  xor     edx, edx; Val
0x1400a1f04  lea     r8d, [rdx+78h]; Size
0x1400a1f08  lea     rcx, [rsp+170h+var_118]; void *
0x1400a1f0d  call    memset_0
0x1400a1f12  xor     r8d, r8d
0x1400a1f15  lea     rdx, [rsp+170h+var_140]
0x1400a1f1a  lea     rcx, [rbp+70h+var_90]
0x1400a1f1e  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400a1f23  nop
0x1400a1f24  cmp     qword ptr [rsi+10h], 0
0x1400a1f29  jz      loc_1400A2147
0x1400a1f2f  mov     byte ptr [rsi+9], 1
0x1400a1f33  mov     rax, [rsi]
0x1400a1f36  mov     rcx, rsi
0x1400a1f39  mov     rax, [rax+18h]
0x1400a1f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a1f42  or      edi, 0FFFFFFFFh
0x1400a1f45  test    bl, bl
0x1400a1f47  jz      loc_1400A204F
0x1400a1f4d  mov     rcx, [rsi+10h]; hThread
0x1400a1f51  call    cs:__imp_ResumeThread
0x1400a1f57  cmp     eax, edi
0x1400a1f59  jnz     loc_1400A204F
0x1400a1f5f  mov     edi, [rsi+1Ch]
0x1400a1f62  call    cs:__imp_GetLastError
0x1400a1f68  mov     ebx, eax
0x1400a1f6a  mov     [rsp+170h+var_140], r12
0x1400a1f6f  mov     [rsp+170h+var_138], r13
0x1400a1f74  mov     [rsp+170h+var_130], r14
0x1400a1f79  mov     [rsp+170h+var_128], 20Ah
0x1400a1f81  mov     r14d, 0Bh
0x1400a1f87  mov     [rsp+170h+var_124], r14d
0x1400a1f8c  mov     [rsp+170h+var_120], 0FFh
0x1400a1f94  mov     [rbp+70h+var_A0], 1000000h
0x1400a1f9b  xor     edx, edx; Val
0x1400a1f9d  lea     r8d, [r14+6Dh]; Size
0x1400a1fa1  lea     rcx, [rsp+170h+var_118]; void *
0x1400a1fa6  call    memset_0
0x1400a1fab  mov     [rsp+170h+var_148], edi
0x1400a1faf  mov     dword ptr [rsp+170h+var_150], ebx
0x1400a1fb3  mov     r9, [rsi+10h]
0x1400a1fb7  lea     r8, aResumethreadP1; "ResumeThread(%p) = -1, GetLastError() ="...
0x1400a1fbe  lea     rdx, [rsp+170h+var_140]
0x1400a1fc3  lea     rcx, [rbp+70h+var_90]
0x1400a1fc7  call    ?LogGenericWarning@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::LogGenericWarning(CVssDebugInfo,ushort const *,...)
0x1400a1fcc  mov     edi, [rsi+1Ch]
0x1400a1fcf  call    cs:__imp_GetLastError
0x1400a1fd5  mov     ebx, eax
0x1400a1fd7  mov     [rsp+170h+var_140], r12
0x1400a1fdc  mov     [rsp+170h+var_138], r13
0x1400a1fe1  lea     rax, aIncworkh; "INCWORKH"
0x1400a1fe8  mov     [rsp+170h+var_130], rax
0x1400a1fed  mov     [rsp+170h+var_128], 20Dh
0x1400a1ff5  mov     [rsp+170h+var_124], r14d
0x1400a1ffa  mov     [rsp+170h+var_120], 0FFh
0x1400a2002  mov     [rbp+70h+var_A0], 1000000h
0x1400a2009  xor     edx, edx; Val
0x1400a200b  lea     r8d, [r14+6Dh]; Size
0x1400a200f  lea     rcx, [rsp+170h+var_118]; void *
0x1400a2014  call    memset_0
0x1400a2019  mov     dword ptr [rsp+170h+var_150], edi
0x1400a201d  mov     r9d, ebx
0x1400a2020  lea     r8, aResumethreadFa; "ResumeThread failed. Error: 0x%08lx. St"...
0x1400a2027  lea     rdx, [rsp+170h+var_140]
0x1400a202c  lea     rcx, [rbp+70h+var_90]
0x1400a2030  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400a2035  mov     dword ptr [rsi+1Ch], 5
0x1400a203c  lea     rcx, [rbp+70h+var_90]; this
0x1400a2040  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400a2045  mov     eax, 8000FFFFh
0x1400a204a  jmp     loc_1400A2154
0x1400a204f  mov     edx, edi; dwMilliseconds
0x1400a2051  mov     rcx, [rsi+10h]; hHandle
0x1400a2055  call    cs:__imp_WaitForSingleObject
0x1400a205b  cmp     eax, edi
0x1400a205d  jnz     loc_1400A2147
0x1400a2063  mov     edi, [rsi+1Ch]
0x1400a2066  call    cs:__imp_GetLastError
0x1400a206c  mov     ebx, eax
0x1400a206e  mov     [rsp+170h+var_140], r12
0x1400a2073  mov     [rsp+170h+var_138], r13
0x1400a2078  mov     [rsp+170h+var_130], r14
0x1400a207d  mov     [rsp+170h+var_128], 219h
0x1400a2085  mov     r14d, 0Bh
0x1400a208b  mov     [rsp+170h+var_124], r14d
0x1400a2090  mov     [rsp+170h+var_120], 0FFh
0x1400a2098  mov     [rbp+70h+var_A0], 1000000h
0x1400a209f  xor     edx, edx; Val
0x1400a20a1  lea     r8d, [r14+6Dh]; Size
0x1400a20a5  lea     rcx, [rsp+170h+var_118]; void *
0x1400a20aa  call    memset_0
0x1400a20af  mov     [rsp+170h+var_148], edi
0x1400a20b3  mov     dword ptr [rsp+170h+var_150], ebx
0x1400a20b7  mov     r9, [rsi+10h]
0x1400a20bb  lea     r8, aWaitforsingleo_2; "WaitForSingleObject(%p,INFINITE) == WAI"...
0x1400a20c2  lea     rdx, [rsp+170h+var_140]
0x1400a20c7  lea     rcx, [rbp+70h+var_90]
0x1400a20cb  call    ?LogGenericWarning@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::LogGenericWarning(CVssDebugInfo,ushort const *,...)
0x1400a20d0  mov     edi, [rsi+1Ch]
0x1400a20d3  call    cs:__imp_GetLastError
0x1400a20d9  mov     ebx, eax
0x1400a20db  mov     [rsp+170h+var_140], r12
0x1400a20e0  mov     [rsp+170h+var_138], r13
0x1400a20e5  lea     rax, aIncworkh; "INCWORKH"
0x1400a20ec  mov     [rsp+170h+var_130], rax
0x1400a20f1  mov     [rsp+170h+var_128], 21Ch
0x1400a20f9  mov     [rsp+170h+var_124], r14d
0x1400a20fe  mov     [rsp+170h+var_120], 0FFh
0x1400a2106  mov     [rbp+70h+var_A0], 1000000h
0x1400a210d  xor     edx, edx; Val
0x1400a210f  lea     r8d, [r14+6Dh]; Size
0x1400a2113  lea     rcx, [rsp+170h+var_118]; void *
0x1400a2118  call    memset_0
0x1400a211d  mov     dword ptr [rsp+170h+var_150], edi
0x1400a2121  mov     r9d, ebx
0x1400a2124  lea     r8, aWaitforsingleo; "WaitForSingleObject failed. Error: 0x%0"...
0x1400a212b  lea     rdx, [rsp+170h+var_140]
0x1400a2130  lea     rcx, [rbp+70h+var_90]
0x1400a2134  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400a2139  mov     dword ptr [rsi+1Ch], 5
0x1400a2140  mov     ebx, 8000FFFFh
0x1400a2145  jmp     short loc_1400A2149
0x1400a2147  xor     ebx, ebx
0x1400a2149  lea     rcx, [rbp+70h+var_90]; this
0x1400a214d  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400a2152  mov     eax, ebx
0x1400a2154  lea     r11, [rsp+170h+var_20]
0x1400a215c  mov     rbx, [r11+38h]
0x1400a2160  mov     rsi, [r11+40h]
0x1400a2164  mov     rsp, r11
0x1400a2167  pop     r14
0x1400a2169  pop     r13
0x1400a216b  pop     r12
0x1400a216d  pop     rdi
0x1400a216e  pop     rbp
0x1400a216f  retn
```

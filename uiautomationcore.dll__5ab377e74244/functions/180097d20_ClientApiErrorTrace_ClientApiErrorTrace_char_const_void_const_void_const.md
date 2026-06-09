# ClientApiErrorTrace::ClientApiErrorTrace(char const *,void const *,void const *)

- ea: `0x180097d20`
- end: `0x1800980c8`
- name: `??0ClientApiErrorTrace@@QEAA@PEBDPEBX1@Z`
- size: `936`
- prototype: `ClientApiErrorTrace *__fastcall(ClientApiErrorTrace *__hidden this, const char *, const void *, const void *)`
- caller_count: `501`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009d30`
- `0x18000bea0`
- `0x18003c9c0`
- `0x18003db30`
- `0x18003f6a0`
- `0x1800b57e0`
- `0x1800b6380`
- `0x1800b6750`
- `0x1800b6860`
- `0x1800c2820`
- `0x1800c5d30`
- `0x1800ca010`
- `0x1800cd660`
- `0x1800cee70`
- `0x1800d0640`
- `0x1800d0b60`
- `0x18011b350`
- `0x180121728`
- `0x1801219f0`
- `0x1801222d0`
- `0x180122910`
- `0x180122cbc`
- `0x1801352e0`
- `0x1801354b0`
- `0x180135820`
- `0x18013cb40`
- `0x18013cc40`
- `0x18013cd40`
- `0x18013ce40`
- `0x18013d100`
- `0x18013d910`
- `0x18013da10`
- `0x18013db10`
- `0x18013dc10`
- `0x18013dd10`
- `0x18013de10`
- `0x18013df10`
- `0x18013e010`
- `0x18013e120`
- `0x18013e220`
- `0x180141190`
- `0x1801415d0`
- `0x180141a00`
- `0x180141d50`
- `0x180145cf0`
- `0x180149d70`
- `0x18014a020`
- `0x18014a550`
- `0x18014bf60`
- `0x18014e210`

## callees

- `0x180097d20`
- `0x180098180`
- `0x1800deac4`
- `0x1800fbdf4`
- `0x1801e9258`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180097f09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180097f74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180097f09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180097f74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097f17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097f82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097f17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097f82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097df8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097e43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097ea2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097ec0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097f33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097df8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097e43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097ea2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097ec0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097f33`

## string_xrefs

- `0x180098024`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`
- `0x180098073`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`
- `0x1800980a9`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ClientApiErrorTrace *__fastcall ClientApiErrorTrace::ClientApiErrorTrace(
        ClientApiErrorTrace *this,
        const char *a2,
        const void *a3,
        HINSTANCE a4)
{
  __int128 *v5; // rbx
  char v6; // r14
  _QWORD *v7; // rdi
  _OWORD *v8; // rbx
  _OWORD *v9; // rax
  __int64 v10; // r15
  DWORD CurrentThreadId; // ebx
  unsigned __int64 v12; // r8
  __int64 v13; // r12
  __int64 i; // rax
  _QWORD *v15; // rcx
  __int128 **v16; // rcx
  __int128 *v17; // rax
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD **v20; // rcx
  _QWORD *v21; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  char *v25; // rax
  signed __int64 v26; // rdx
  signed __int64 v27; // rax
  const struct wil::FailureInfo *v28; // rdx
  __int128 v29; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpMem[2]; // [rsp+30h] [rbp-D0h]
  __int128 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int128 *v32; // [rsp+50h] [rbp-B0h]
  int v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  char v35; // [rsp+68h] [rbp-98h]
  char v36[16]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v37; // [rsp+80h] [rbp-80h]
  char v38; // [rsp+88h] [rbp-78h]
  _QWORD v39[3]; // [rsp+90h] [rbp-70h] BYREF
  int v40; // [rsp+A8h] [rbp-58h]
  _BYTE v41[224]; // [rsp+C0h] [rbp-40h] BYREF
  void *retaddr; // [rsp+1A8h] [rbp+A8h]

  if ( a4 < g_hInstance || a4 > (HINSTANCE)((char *)g_hInstance + g_ModuleSize) )
  {
    v5 = (__int128 *)UiaImportantTraceLoggingProvider::WatchCurrentThread(v36, a2, "object=%p", a3);
    v6 = 1;
  }
  else
  {
    v29 = 0;
    *(_OWORD *)lpMem = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v5 = &v29;
    v6 = 2;
  }
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *(_DWORD *)this = *(_DWORD *)v5;
  *((_QWORD *)this + 1) = *((_QWORD *)v5 + 1);
  *((_QWORD *)this + 2) = *((_QWORD *)v5 + 2);
  *((_QWORD *)v5 + 2) = 0;
  *((_BYTE *)this + 24) = *((_BYTE *)v5 + 24);
  *((_BYTE *)v5 + 24) = 0;
  v7 = (_QWORD *)((char *)this + 32);
  v8 = v5 + 2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)v8 + 1);
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = *((_QWORD *)v8 + 4);
  *((_BYTE *)this + 72) = 0;
  if ( *((_DWORD *)v8 + 6) )
  {
    if ( *((_DWORD *)v8 + 6) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *((_DWORD *)v8 + 6) = 0;
    while ( 1 )
    {
      v9 = **(_OWORD ***)v8;
      if ( !v9 )
        break;
      if ( v9 == v8 )
      {
        **(_QWORD **)v8 = *((_QWORD *)v8 + 2);
        break;
      }
      *(_QWORD *)v8 = v9 + 1;
    }
    *(_QWORD *)v8 = 0;
    if ( *((_DWORD *)this + 14) )
    {
      memset_0(v41, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v41, v28);
    }
    v10 = wil::details::g_pThreadFailureCallbacks;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
      v13 = 8 * v12;
      for ( i = *(_QWORD *)(8 * v12 + v10); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v15 = (_QWORD *)(i + 16);
          goto LABEL_17;
        }
      }
      v25 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v12);
      v26 = (signed __int64)v25;
      if ( v25 )
      {
        *(_DWORD *)v25 = CurrentThreadId;
        *((_DWORD *)v25 + 1) = 0;
        *((_QWORD *)v25 + 1) = 0;
        v15 = v25 + 16;
        *((_QWORD *)v25 + 2) = 0;
        do
        {
          v27 = *(_QWORD *)(v13 + v10);
          *(_QWORD *)(v26 + 8) = v27;
        }
        while ( v27 != _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + v10), v26, v27) );
      }
      else
      {
        v15 = 0;
      }
LABEL_17:
      *v7 = v15;
      if ( v15 )
      {
        *((_QWORD *)this + 6) = *v15;
        *v15 = v7;
        *((_DWORD *)this + 14) = GetCurrentThreadId();
      }
    }
    else
    {
      *v7 = 0;
    }
  }
  *((_QWORD *)this + 8) = this;
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    if ( v33 )
    {
      if ( v33 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
      v33 = 0;
      v16 = (__int128 **)v31;
      while ( 1 )
      {
        v17 = *v16;
        if ( !*v16 )
          break;
        if ( v17 == &v31 )
        {
          *v16 = v32;
          break;
        }
        v16 = (__int128 **)(v17 + 1);
        *(_QWORD *)&v31 = v17 + 1;
      }
      *(_QWORD *)&v31 = 0;
    }
    if ( LOBYTE(lpMem[1]) )
    {
      v18 = lpMem[0];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      LOBYTE(lpMem[1]) = 0;
    }
    lpMem[0] = 0;
  }
  if ( (v6 & 1) != 0 )
  {
    if ( v40 )
    {
      if ( v40 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
      v40 = 0;
      v20 = (_QWORD **)v39[0];
      while ( 1 )
      {
        v21 = *v20;
        if ( !*v20 )
          break;
        if ( v21 == v39 )
        {
          *v20 = (_QWORD *)v39[2];
          break;
        }
        v20 = (_QWORD **)(v21 + 2);
        v39[0] = v21 + 2;
      }
      v39[0] = 0;
    }
    if ( v38 )
    {
      v22 = v37;
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v22);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180097d20  push    rbp
0x180097d22  push    rbx
0x180097d23  push    rsi
0x180097d24  push    rdi
0x180097d25  push    r12
0x180097d27  push    r13
0x180097d29  push    r14
0x180097d2b  push    r15
0x180097d2d  lea     rbp, [rsp-68h]
0x180097d32  sub     rsp, 168h
0x180097d39  mov     rsi, rcx
0x180097d3c  xor     r13d, r13d
0x180097d3f  mov     [rbp+0A0h+arg_0], r13d
0x180097d46  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180097d4d  cmp     r9, rcx
0x180097d50  jb      loc_180097F9F
0x180097d56  mov     eax, cs:?g_ModuleSize@@3KA; ulong g_ModuleSize
0x180097d5c  add     rax, rcx
0x180097d5f  cmp     r9, rax
0x180097d62  ja      loc_180097F9F
0x180097d68  xorps   xmm0, xmm0
0x180097d6b  movups  [rsp+1A0h+var_180], xmm0
0x180097d70  movups  xmmword ptr [rsp+1A0h+lpMem], xmm0
0x180097d75  movdqu  [rsp+1A0h+var_160], xmm0
0x180097d7b  mov     [rsp+1A0h+var_150], r13
0x180097d80  mov     [rsp+1A0h+var_148], r13d
0x180097d85  mov     [rsp+1A0h+var_140], r13
0x180097d8a  mov     [rsp+1A0h+var_138], r13b
0x180097d8f  lea     rbx, [rsp+1A0h+var_180]
0x180097d94  mov     r14d, 2
0x180097d9a  xorps   xmm0, xmm0
0x180097d9d  movups  xmmword ptr [rsi], xmm0
0x180097da0  movups  xmmword ptr [rsi+10h], xmm0
0x180097da4  mov     ecx, [rbx]
0x180097da6  mov     [rsi], ecx
0x180097da8  mov     rcx, [rbx+8]
0x180097dac  mov     [rsi+8], rcx
0x180097db0  mov     rcx, [rbx+10h]
0x180097db4  mov     [rsi+10h], rcx
0x180097db8  mov     [rbx+10h], r13
0x180097dbc  movzx   eax, byte ptr [rbx+18h]
0x180097dc0  mov     [rsi+18h], al
0x180097dc3  mov     byte ptr [rbx+18h], 0
0x180097dc7  lea     rdi, [rsi+20h]
0x180097dcb  add     rbx, 20h ; ' '
0x180097dcf  mov     [rdi], r13
0x180097dd2  mov     rax, [rbx+8]
0x180097dd6  mov     [rdi+8], rax
0x180097dda  mov     [rdi+10h], r13
0x180097dde  mov     [rdi+18h], r13d
0x180097de2  mov     rax, [rbx+20h]
0x180097de6  mov     [rdi+20h], rax
0x180097dea  mov     byte ptr [rdi+28h], 0
0x180097dee  cmp     dword ptr [rbx+18h], 0
0x180097df2  jz      loc_180097EAB
0x180097df8  call    cs:__imp_GetCurrentThreadId
0x180097dfe  cmp     [rbx+18h], eax
0x180097e01  jnz     loc_18009800D
0x180097e07  mov     [rbx+18h], r13d
0x180097e0b  mov     rcx, [rbx]
0x180097e0e  mov     rax, [rcx]
0x180097e11  test    rax, rax
0x180097e14  jz      short loc_180097E26
0x180097e16  cmp     rax, rbx
0x180097e19  jnz     loc_180098035
0x180097e1f  mov     rax, [rbx+10h]
0x180097e23  mov     [rcx], rax
0x180097e26  mov     [rbx], r13
0x180097e29  cmp     dword ptr [rdi+18h], 0
0x180097e2d  jnz     loc_180098041
0x180097e33  mov     r15, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180097e3a  test    r15, r15
0x180097e3d  jz      loc_180097FC1
0x180097e43  call    cs:__imp_GetCurrentThreadId
0x180097e49  mov     ebx, eax
0x180097e4b  mov     r8d, eax
0x180097e4e  shr     r8, 2
0x180097e52  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180097e5c  mul     r8
0x180097e5f  shr     rdx, 3
0x180097e63  lea     rcx, [rdx+rdx*4]
0x180097e67  add     rcx, rcx
0x180097e6a  sub     r8, rcx; unsigned __int64
0x180097e6d  lea     r12, ds:0[r8*8]
0x180097e75  mov     rax, [r12+r15]
0x180097e79  test    rax, rax
0x180097e7c  jz      loc_180097FC9
0x180097e82  cmp     [rax], ebx
0x180097e84  jz      short loc_180097E8C
0x180097e86  mov     rax, [rax+8]
0x180097e8a  jmp     short loc_180097E79
0x180097e8c  lea     rcx, [rax+10h]
0x180097e90  mov     [rdi], rcx
0x180097e93  test    rcx, rcx
0x180097e96  jz      short loc_180097EAB
0x180097e98  mov     rax, [rcx]
0x180097e9b  mov     [rdi+10h], rax
0x180097e9f  mov     [rcx], rdi
0x180097ea2  call    cs:__imp_GetCurrentThreadId
0x180097ea8  mov     [rdi+18h], eax
0x180097eab  mov     [rsi+40h], rsi
0x180097eaf  test    r14b, 2
0x180097eb3  jz      short loc_180097F27
0x180097eb5  and     r14d, 0FFFFFFFDh
0x180097eb9  cmp     [rsp+1A0h+var_148], 0
0x180097ebe  jz      short loc_180097EFD
0x180097ec0  call    cs:__imp_GetCurrentThreadId
0x180097ec6  cmp     [rsp+1A0h+var_148], eax
0x180097eca  jnz     loc_18009805C
0x180097ed0  mov     [rsp+1A0h+var_148], r13d
0x180097ed5  mov     rcx, qword ptr [rsp+1A0h+var_160]
0x180097eda  mov     rax, [rcx]
0x180097edd  test    rax, rax
0x180097ee0  jz      short loc_180097EF8
0x180097ee2  lea     rdx, [rsp+1A0h+var_160]
0x180097ee7  cmp     rax, rdx
0x180097eea  jnz     loc_180098084
0x180097ef0  mov     rax, [rsp+1A0h+var_150]
0x180097ef5  mov     [rcx], rax
0x180097ef8  mov     qword ptr [rsp+1A0h+var_160], r13
0x180097efd  cmp     byte ptr [rsp+1A0h+lpMem+8], 0
0x180097f02  jz      short loc_180097F22
0x180097f04  mov     rbx, [rsp+1A0h+lpMem]
0x180097f09  call    cs:__imp_GetProcessHeap
0x180097f0f  mov     r8, rbx; lpMem
0x180097f12  xor     edx, edx; dwFlags
0x180097f14  mov     rcx, rax; hHeap
0x180097f17  call    cs:__imp_HeapFree
0x180097f1d  mov     byte ptr [rsp+1A0h+lpMem+8], 0
0x180097f22  mov     [rsp+1A0h+lpMem], r13
0x180097f27  test    r14b, 1
0x180097f2b  jz      short loc_180097F88
0x180097f2d  cmp     [rbp+0A0h+var_F8], 0
0x180097f31  jz      short loc_180097F6A
0x180097f33  call    cs:__imp_GetCurrentThreadId
0x180097f39  cmp     [rbp+0A0h+var_F8], eax
0x180097f3c  jnz     loc_180098092
0x180097f42  mov     [rbp+0A0h+var_F8], r13d
0x180097f46  mov     rcx, [rbp+0A0h+var_110]
0x180097f4a  mov     rax, [rcx]
0x180097f4d  test    rax, rax
0x180097f50  jz      short loc_180097F66
0x180097f52  lea     rdx, [rbp+0A0h+var_110]
0x180097f56  cmp     rax, rdx
0x180097f59  jnz     loc_1800980BA
0x180097f5f  mov     rax, [rbp+0A0h+var_100]
0x180097f63  mov     [rcx], rax
0x180097f66  mov     [rbp+0A0h+var_110], r13
0x180097f6a  cmp     [rbp+0A0h+var_118], 0
0x180097f6e  jz      short loc_180097F88
0x180097f70  mov     rbx, [rbp+0A0h+var_120]
0x180097f74  call    cs:__imp_GetProcessHeap
0x180097f7a  mov     r8, rbx; lpMem
0x180097f7d  xor     edx, edx; dwFlags
0x180097f7f  mov     rcx, rax; hHeap
0x180097f82  call    cs:__imp_HeapFree
0x180097f88  mov     rax, rsi
0x180097f8b  add     rsp, 168h
0x180097f92  pop     r15
0x180097f94  pop     r14
0x180097f96  pop     r13
0x180097f98  pop     r12
0x180097f9a  pop     rdi
0x180097f9b  pop     rsi
0x180097f9c  pop     rbx
0x180097f9d  pop     rbp
0x180097f9e  retn
0x180097f9f  mov     r9, r8
0x180097fa2  lea     r8, aObjectP; "object=%p"
0x180097fa9  lea     rcx, [rsp+1A0h+var_130]
0x180097fae  call    ?WatchCurrentThread@UiaImportantTraceLoggingProvider@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; UiaImportantTraceLoggingProvider::WatchCurrentThread(char const *,char const *,...)
0x180097fb3  mov     rbx, rax
0x180097fb6  mov     r14d, 1
0x180097fbc  jmp     loc_180097D9A
0x180097fc1  mov     [rdi], r13
0x180097fc4  jmp     loc_180097EAB
0x180097fc9  mov     edx, 18h; dwBytes
0x180097fce  xor     ecx, ecx; dwFlags
0x180097fd0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180097fd5  mov     rdx, rax
0x180097fd8  test    rax, rax
0x180097fdb  jz      short loc_180098005
0x180097fdd  mov     [rax], ebx
0x180097fdf  xor     eax, eax
0x180097fe1  mov     [rdx+4], eax
0x180097fe4  mov     [rdx+8], r13
0x180097fe8  lea     rcx, [rdx+10h]
0x180097fec  mov     [rcx], r13
0x180097fef  mov     rax, [r12+r15]
0x180097ff3  mov     [rdx+8], rax
0x180097ff7  lock cmpxchg [r12+r15], rdx
0x180097ffd  jz      loc_180097E90
0x180098003  jmp     short loc_180097FEF
0x180098005  mov     rcx, r13
0x180098008  jmp     loc_180097E90
0x18009800d  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180098014  test    rax, rax
0x180098017  jz      loc_180097E07
0x18009801d  mov     rdx, [rbp+0A8h]
0x180098024  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18009802b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098030  jmp     loc_180097E07
0x180098035  add     rax, 10h
0x180098039  mov     [rbx], rax
0x18009803c  jmp     loc_180097E0B
0x180098041  xor     edx, edx; Val
0x180098043  mov     r8d, 98h; Size
0x180098049  lea     rcx, [rbp+0A0h+var_E0]; void *
0x18009804d  call    memset_0
0x180098052  lea     rcx, [rbp+0A0h+var_E0]; this
0x180098056  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18009805c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180098063  test    rax, rax
0x180098066  jz      loc_180097ED0
0x18009806c  mov     rdx, [rbp+0A8h]
0x180098073  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18009807a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009807f  jmp     loc_180097ED0
0x180098084  lea     rcx, [rax+10h]
0x180098088  mov     qword ptr [rsp+1A0h+var_160], rcx
0x18009808d  jmp     loc_180097EDA
0x180098092  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180098099  test    rax, rax
0x18009809c  jz      loc_180097F42
0x1800980a2  mov     rdx, [rbp+0A8h]
0x1800980a9  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800980b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800980b5  jmp     loc_180097F42
0x1800980ba  lea     rcx, [rax+10h]
0x1800980be  mov     [rbp+0A0h+var_110], rcx
0x1800980c2  jmp     loc_180097F4A
```

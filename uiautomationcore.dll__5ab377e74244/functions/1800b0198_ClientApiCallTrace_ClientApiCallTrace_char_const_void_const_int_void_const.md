# ClientApiCallTrace::ClientApiCallTrace(char const *,void const *,int,void const *)

- ea: `0x1800b0198`
- end: `0x1800b09c2`
- name: `??0ClientApiCallTrace@@QEAA@PEBDPEBXH1@Z`
- size: `2090`
- prototype: `ClientApiCallTrace *(ClientApiCallTrace *__hidden this, const char *, const void *, int, const void *)`
- caller_count: `12`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b16b0`
- `0x1800b6080`
- `0x1800ce610`
- `0x1800ce930`
- `0x1800cfb90`
- `0x1800cff20`
- `0x1800d15b0`
- `0x18015b570`
- `0x18015cb00`
- `0x18015e080`
- `0x18017bcc0`
- `0x180260e80`

## callees

- `0x18009ab54`
- `0x18009d174`
- `0x1800adb40`
- `0x1800b0198`
- `0x1800b1120`
- `0x1800fbdf4`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e9258`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b03a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b060f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0861`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b03a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b060f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0861`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b03b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b061d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b086f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b03b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b061d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b086f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b04fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b0570`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b0740`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b079b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b07b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b04fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b0570`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b0740`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b079b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b07b6`

## string_xrefs

- `0x1800b09a3`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ClientApiCallTrace *__fastcall ClientApiCallTrace::ClientApiCallTrace(
        ClientApiCallTrace *this,
        const char *a2,
        const void *a3,
        int a4,
        HINSTANCE a5)
{
  char *v7; // rdi
  char *v8; // r14
  volatile signed __int32 **v9; // r13
  volatile signed __int32 **v10; // r12
  _QWORD *v11; // rsi
  int v12; // ebx
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v14; // rcx
  DWORD CurrentThreadId; // eax
  unsigned __int64 v16; // rbx
  __int64 i; // rcx
  __int64 *v18; // rcx
  int *v19; // rcx
  void *v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rdi
  DWORD v23; // r14d
  unsigned __int64 v24; // rbx
  __int64 j; // rcx
  _QWORD *v26; // rcx
  _QWORD **v27; // rcx
  _QWORD *v28; // rax
  volatile signed __int32 *v30; // rbx
  HANDLE v31; // rax
  char *v32; // rax
  signed __int64 v33; // rdx
  signed __int64 v34; // rax
  char *v35; // rax
  signed __int64 v36; // rdx
  signed __int64 v37; // rax
  volatile signed __int32 *v38; // rbx
  int v40; // [rsp+20h] [rbp-E0h]
  _QWORD *v42; // [rsp+28h] [rbp-D8h]
  void **v43; // [rsp+30h] [rbp-D0h] BYREF
  int v44; // [rsp+38h] [rbp-C8h] BYREF
  char v45; // [rsp+3Ch] [rbp-C4h]
  __int128 v46; // [rsp+40h] [rbp-C0h]
  __int128 v47; // [rsp+50h] [rbp-B0h]
  int v48; // [rsp+60h] [rbp-A0h] BYREF
  const char *v49; // [rsp+68h] [rbp-98h]
  __int64 v50; // [rsp+70h] [rbp-90h]
  char v51; // [rsp+78h] [rbp-88h]
  int v52; // [rsp+80h] [rbp-80h]
  _OWORD v53[9]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v54; // [rsp+118h] [rbp+18h]
  __int128 v55; // [rsp+120h] [rbp+20h] BYREF
  int v56; // [rsp+130h] [rbp+30h]
  __int64 v57; // [rsp+138h] [rbp+38h]
  int *v58; // [rsp+140h] [rbp+40h]
  volatile signed __int32 *v59; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v60[2]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD *v61; // [rsp+160h] [rbp+60h]
  int v62; // [rsp+168h] [rbp+68h]
  int *v63; // [rsp+170h] [rbp+70h]
  char v64; // [rsp+178h] [rbp+78h]
  void **v65; // [rsp+180h] [rbp+80h] BYREF
  int v66; // [rsp+188h] [rbp+88h] BYREF
  char v67; // [rsp+18Ch] [rbp+8Ch]
  __int128 v68; // [rsp+190h] [rbp+90h]
  __int128 v69; // [rsp+1A0h] [rbp+A0h]
  __int128 v70; // [rsp+1B0h] [rbp+B0h]
  __int128 v71; // [rsp+1C0h] [rbp+C0h]
  int v72; // [rsp+1D0h] [rbp+D0h]
  __int128 v73; // [rsp+1D8h] [rbp+D8h]
  __int128 v74; // [rsp+1E8h] [rbp+E8h]
  __int128 v75; // [rsp+1F8h] [rbp+F8h]
  __int128 v76; // [rsp+208h] [rbp+108h]
  __int128 v77; // [rsp+218h] [rbp+118h]
  __int128 v78; // [rsp+228h] [rbp+128h]
  __int128 v79; // [rsp+238h] [rbp+138h]
  __int128 v80; // [rsp+248h] [rbp+148h]
  __int128 v81; // [rsp+258h] [rbp+158h]
  __int64 v82; // [rsp+268h] [rbp+168h]
  __int64 v83; // [rsp+270h] [rbp+170h]
  __int64 v84; // [rsp+278h] [rbp+178h]
  int v85; // [rsp+280h] [rbp+180h]
  __int64 v86; // [rsp+288h] [rbp+188h]
  int *v87; // [rsp+290h] [rbp+190h]
  volatile signed __int32 *v88; // [rsp+298h] [rbp+198h]
  _QWORD v89[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v90; // [rsp+2B0h] [rbp+1B0h]
  DWORD v91; // [rsp+2B8h] [rbp+1B8h]
  _DWORD *v92; // [rsp+2C0h] [rbp+1C0h]
  char v93; // [rsp+2C8h] [rbp+1C8h]
  void *retaddr; // [rsp+328h] [rbp+228h]

  v7 = (char *)this + 8;
  *((_DWORD *)this + 2) = 0;
  *((_BYTE *)this + 12) = 0;
  *((_BYTE *)this + 72) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = "ClientApiCallActivity";
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 20) = 0;
  v8 = (char *)this + 88;
  v9 = (volatile signed __int32 **)((char *)this + 240);
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  memset_0((char *)this + 88, 0, 0x98u);
  *((_DWORD *)v7 + 62) = 1;
  *((_QWORD *)v7 + 32) = 0;
  *((_QWORD *)this + 34) = v7;
  v10 = (volatile signed __int32 **)((char *)this + 280);
  *((_QWORD *)this + 35) = 0;
  v11 = (_QWORD *)((char *)this + 288);
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = this;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_QWORD *)this + 40) = (char *)this + 48;
  *((_BYTE *)this + 328) = 0;
  *(_QWORD *)this = &UiaProvider::ClientApiCallActivity::`vftable';
  if ( a5 < g_hInstance || a5 > (HINSTANCE)((char *)g_hInstance + g_ModuleSize) )
  {
    v44 = 0;
    v45 = 0;
    v51 = 0;
    v48 = 0;
    v49 = "ClientApiCallActivity";
    v50 = 0;
    v52 = 0;
    v55 = 0;
    memset_0(v53, 0, 0x98u);
    v56 = 1;
    v57 = 0;
    v58 = &v44;
    v59 = 0;
    v60[0] = 0;
    v60[1] = &v43;
    v61 = 0;
    v62 = 0;
    v63 = &v48;
    v64 = 0;
    v43 = &UiaProvider::ClientApiCallActivity::`vftable';
    UiaProvider::ClientApiCallActivity::StartActivity((UiaProvider::ClientApiCallActivity *)&v43, a2, a3, a4);
    v12 = *((_DWORD *)this + 78);
    v65 = &wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
    v66 = *(_DWORD *)v7;
    v67 = v7[4];
    v68 = *(_OWORD *)(v7 + 8);
    v69 = *(_OWORD *)(v7 + 24);
    *(_DWORD *)v7 = 0;
    v7[4] = 0;
    v70 = 0;
    v71 = 0;
    LODWORD(v70) = *((_DWORD *)v7 + 10);
    *((_QWORD *)&v70 + 1) = *((_QWORD *)v7 + 6);
    if ( (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, 0);
    }
    *(_QWORD *)&v71 = *((_QWORD *)v7 + 7);
    *((_QWORD *)v7 + 7) = 0;
    BYTE8(v71) = v7[64];
    v7[64] = 0;
    v72 = *((_DWORD *)v7 + 18);
    v73 = *(_OWORD *)v8;
    v74 = *((_OWORD *)v8 + 1);
    v75 = *((_OWORD *)v8 + 2);
    v76 = *((_OWORD *)v8 + 3);
    v77 = *((_OWORD *)v8 + 4);
    v78 = *((_OWORD *)v8 + 5);
    v79 = *((_OWORD *)v8 + 6);
    v80 = *((_OWORD *)v8 + 7);
    v81 = *((_OWORD *)v8 + 8);
    v82 = *((_QWORD *)v8 + 18);
    v83 = *((_QWORD *)v7 + 29);
    v84 = *((_QWORD *)v7 + 30);
    *((_QWORD *)v7 + 29) = 0;
    *((_QWORD *)v7 + 30) = 0;
    v85 = *((_DWORD *)v7 + 62);
    v86 = 0;
    v14 = *v10;
    v88 = *v10;
    *v10 = 0;
    v89[0] = 0;
    v89[1] = &v65;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    v93 = 0;
    if ( v12 )
    {
      v42 = (_QWORD *)wil::details::g_pThreadFailureCallbacks;
      if ( wil::details::g_pThreadFailureCallbacks )
      {
        CurrentThreadId = GetCurrentThreadId();
        v40 = CurrentThreadId;
        v16 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
        for ( i = v42[v16]; i; i = *(_QWORD *)(i + 8) )
        {
          if ( *(_DWORD *)i == CurrentThreadId )
          {
            v18 = (__int64 *)(i + 16);
            goto LABEL_12;
          }
        }
        v32 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, CurrentThreadId);
        v33 = (signed __int64)v32;
        if ( v32 )
        {
          *(_DWORD *)v32 = v40;
          *((_DWORD *)v32 + 1) = 0;
          *((_QWORD *)v32 + 1) = 0;
          v18 = (__int64 *)(v32 + 16);
          *((_QWORD *)v32 + 2) = 0;
          do
          {
            v34 = v42[v16];
            *(_QWORD *)(v33 + 8) = v34;
          }
          while ( v34 != _InterlockedCompareExchange64(&v42[v16], v33, v34) );
        }
        else
        {
          v18 = 0;
        }
LABEL_12:
        v89[0] = v18;
        if ( v18 )
        {
          v90 = *v18;
          *v18 = (__int64)v89;
          v91 = GetCurrentThreadId();
        }
        v14 = v88;
      }
    }
    if ( v14 )
      v19 = (int *)((unsigned __int64)(v14 + 2) & -(__int64)(v14 != 0));
    else
      v19 = &v66;
    v87 = v19;
    v92 = v19 + 10;
    *((_QWORD *)this + 34) = v7;
    if ( *((_DWORD *)this + 78) )
      wil::details::ThreadFailureCallbackHolder::StopWatching((ClientApiCallTrace *)((char *)this + 288));
    v65 = &UiaProvider::ClientApiCallActivity::`vftable';
    *(_DWORD *)v7 = v44;
    v7[4] = v45;
    *(_OWORD *)(v7 + 8) = v46;
    *(_OWORD *)(v7 + 24) = v47;
    v44 = 0;
    v45 = 0;
    *((_DWORD *)v7 + 10) = v48;
    *((_QWORD *)v7 + 6) = v49;
    if ( v7[64] )
    {
      v20 = (void *)*((_QWORD *)v7 + 7);
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v20);
    }
    *((_QWORD *)v7 + 7) = v50;
    v50 = 0;
    v7[64] = v51;
    v51 = 0;
    *((_DWORD *)v7 + 18) = v52;
    *(_OWORD *)v8 = v53[0];
    *((_OWORD *)v8 + 1) = v53[1];
    *((_OWORD *)v8 + 2) = v53[2];
    *((_OWORD *)v8 + 3) = v53[3];
    *((_OWORD *)v8 + 4) = v53[4];
    *((_OWORD *)v8 + 5) = v53[5];
    *((_OWORD *)v8 + 6) = v53[6];
    *((_OWORD *)v8 + 7) = v53[7];
    *((_OWORD *)v8 + 8) = v53[8];
    *((_QWORD *)v8 + 18) = v54;
    if ( v9 != (volatile signed __int32 **)&v55 )
    {
      if ( *v9 && _InterlockedExchangeAdd(*v9, 0xFFFFFFFF) == 1 )
      {
        v30 = *v9;
        v31 = GetProcessHeap();
        HeapFree(v31, 0, (LPVOID)v30);
      }
      *(_OWORD *)v9 = v55;
      v55 = 0;
    }
    *((_DWORD *)v7 + 62) = v56;
    if ( v10 != &v59 )
    {
      if ( *v10 )
      {
        if ( _InterlockedExchangeAdd(*v10, 0xFFFFFFFF) == 1 )
        {
          v38 = *v10;
          if ( *v10 )
          {
            wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UiaProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UiaProvider,_TlgReflectorTag_Param0IsProviderType>(v38 + 2);
            operator delete((void *)v38);
          }
        }
      }
      *v10 = v59;
      v59 = 0;
    }
    if ( *v10 )
      v7 = (char *)(*v10 + 2);
    *((_QWORD *)this + 34) = v7;
    *((_QWORD *)this + 40) = v7 + 40;
    if ( v62 )
    {
      if ( !*((_DWORD *)this + 78) )
      {
        v22 = wil::details::g_pThreadFailureCallbacks;
        if ( wil::details::g_pThreadFailureCallbacks )
        {
          v23 = GetCurrentThreadId();
          v24 = ((unsigned __int64)v23 >> 2) % 0xA;
          for ( j = *(_QWORD *)(v22 + 8 * v24); j; j = *(_QWORD *)(j + 8) )
          {
            if ( *(_DWORD *)j == v23 )
            {
              v26 = (_QWORD *)(j + 16);
              goto LABEL_37;
            }
          }
          v35 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, 0);
          v36 = (signed __int64)v35;
          if ( v35 )
          {
            *(_DWORD *)v35 = v23;
            *((_DWORD *)v35 + 1) = 0;
            *((_QWORD *)v35 + 1) = 0;
            v26 = v35 + 16;
            *((_QWORD *)v35 + 2) = 0;
            do
            {
              v37 = *(_QWORD *)(v22 + 8 * v24);
              *(_QWORD *)(v36 + 8) = v37;
            }
            while ( v37 != _InterlockedCompareExchange64((volatile signed __int64 *)(v22 + 8 * v24), v36, v37) );
          }
          else
          {
            v26 = 0;
          }
LABEL_37:
          *v11 = v26;
          if ( v26 )
          {
            *((_QWORD *)this + 38) = *v26;
            *v26 = v11;
            *((_DWORD *)this + 78) = GetCurrentThreadId();
          }
        }
        else
        {
          *v11 = 0;
        }
      }
    }
    else
    {
      if ( !*((_DWORD *)this + 78) )
      {
        v58 = &v44;
LABEL_46:
        UiaProvider::ClientApiCallActivity::~ClientApiCallActivity((UiaProvider::ClientApiCallActivity *)&v65);
        UiaProvider::ClientApiCallActivity::~ClientApiCallActivity((UiaProvider::ClientApiCallActivity *)&v43);
        return this;
      }
      wil::details::ThreadFailureCallbackHolder::StopWatching((ClientApiCallTrace *)((char *)this + 288));
    }
    v58 = &v44;
    if ( v62 )
    {
      if ( v62 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
      v62 = 0;
      v27 = (_QWORD **)v60[0];
      while ( 1 )
      {
        v28 = *v27;
        if ( !*v27 )
          break;
        if ( v28 == v60 )
        {
          *v27 = v61;
          break;
        }
        v27 = (_QWORD **)(v28 + 2);
        v60[0] = v28 + 2;
      }
      v60[0] = 0;
    }
    goto LABEL_46;
  }
  return this;
}

```

## disassembly

```asm
0x1800b0198  push    rbp
0x1800b019a  push    rbx
0x1800b019b  push    rsi
0x1800b019c  push    rdi
0x1800b019d  push    r12
0x1800b019f  push    r13
0x1800b01a1  push    r14
0x1800b01a3  push    r15
0x1800b01a5  lea     rbp, [rsp-1E8h]
0x1800b01ad  sub     rsp, 2E8h
0x1800b01b4  mov     rax, cs:__security_cookie
0x1800b01bb  xor     rax, rsp
0x1800b01be  mov     [rbp+220h+var_50], rax
0x1800b01c5  mov     [rsp+320h+var_300], r9d
0x1800b01ca  mov     [rsp+320h+var_2F8], r8
0x1800b01cf  mov     rbx, rdx
0x1800b01d2  mov     r15, rcx
0x1800b01d5  lea     rdi, [rcx+8]
0x1800b01d9  xor     eax, eax
0x1800b01db  mov     [rdi], eax
0x1800b01dd  mov     [rdi+4], al
0x1800b01e0  mov     [rdi+40h], al
0x1800b01e3  mov     [rdi+28h], eax
0x1800b01e6  lea     rcx, aClientapicalla; "ClientApiCallActivity"
0x1800b01ed  mov     [rdi+30h], rcx
0x1800b01f1  mov     [rdi+38h], rax
0x1800b01f5  mov     [rdi+48h], eax
0x1800b01f8  lea     r14, [rdi+50h]
0x1800b01fc  lea     r13, [r14+98h]
0x1800b0203  mov     [r13+0], rax
0x1800b0207  mov     [r13+8], rax
0x1800b020b  xor     edx, edx; Val
0x1800b020d  mov     r8d, 98h; Size
0x1800b0213  mov     rcx, r14; void *
0x1800b0216  call    memset_0
0x1800b021b  mov     dword ptr [rdi+0F8h], 1
0x1800b0225  xor     eax, eax
0x1800b0227  mov     [rdi+100h], rax
0x1800b022e  mov     [r15+110h], rdi
0x1800b0235  lea     r12, [r15+118h]
0x1800b023c  xor     edx, edx
0x1800b023e  mov     [r12], rdx
0x1800b0242  lea     rsi, [r15+120h]
0x1800b0249  mov     [rsi], rdx
0x1800b024c  mov     [rsi+8], r15
0x1800b0250  mov     [rsi+10h], rdx
0x1800b0254  mov     [rsi+18h], edx
0x1800b0257  lea     rax, [r15+30h]
0x1800b025b  mov     [rsi+20h], rax
0x1800b025f  mov     [rsi+28h], dl
0x1800b0262  lea     rax, ??_7ClientApiCallActivity@UiaProvider@@6B@; const UiaProvider::ClientApiCallActivity::`vftable'
0x1800b0269  mov     [r15], rax
0x1800b026c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800b0273  cmp     [rbp+220h+arg_20], rcx
0x1800b027a  jb      short loc_1800B0292
0x1800b027c  mov     eax, cs:?g_ModuleSize@@3KA; ulong g_ModuleSize
0x1800b0282  add     rax, rcx
0x1800b0285  cmp     [rbp+220h+arg_20], rax
0x1800b028c  jbe     loc_1800B080A
0x1800b0292  mov     [rsp+320h+var_2E8], edx
0x1800b0296  mov     [rsp+320h+var_2E4], dl
0x1800b029a  mov     [rsp+320h+var_2A8], dl
0x1800b029e  mov     [rsp+320h+var_2C0], edx
0x1800b02a2  lea     rax, aClientapicalla; "ClientApiCallActivity"
0x1800b02a9  mov     [rsp+320h+var_2B8], rax
0x1800b02ae  mov     [rsp+320h+var_2B0], rdx
0x1800b02b3  mov     [rbp+220h+var_2A0], edx
0x1800b02b6  xorps   xmm0, xmm0
0x1800b02b9  movdqa  [rbp+220h+var_200], xmm0
0x1800b02be  xor     edx, edx; Val
0x1800b02c0  mov     r8d, 98h; Size
0x1800b02c6  lea     rcx, [rbp+220h+var_298]; void *
0x1800b02ca  call    memset_0
0x1800b02cf  mov     [rbp+220h+var_1F0], 1
0x1800b02d6  xor     eax, eax
0x1800b02d8  mov     [rbp+220h+var_1E8], rax
0x1800b02dc  lea     rax, [rsp+320h+var_2E8]
0x1800b02e1  mov     [rbp+220h+var_1E0], rax
0x1800b02e5  xor     ecx, ecx
0x1800b02e7  mov     [rbp+220h+var_1D8], rcx
0x1800b02eb  mov     [rbp+220h+var_1D0], rcx
0x1800b02ef  lea     rax, [rsp+320h+var_2F0]
0x1800b02f4  mov     [rbp+220h+var_1C8], rax
0x1800b02f8  mov     [rbp+220h+var_1C0], rcx
0x1800b02fc  mov     [rbp+220h+var_1B8], ecx
0x1800b02ff  lea     rax, [rsp+320h+var_2C0]
0x1800b0304  mov     [rbp+220h+var_1B0], rax
0x1800b0308  mov     [rbp+220h+var_1A8], cl
0x1800b030b  lea     rax, ??_7ClientApiCallActivity@UiaProvider@@6B@; const UiaProvider::ClientApiCallActivity::`vftable'
0x1800b0312  mov     [rsp+320h+var_2F0], rax
0x1800b0317  mov     r9d, [rsp+320h+var_300]; int
0x1800b031c  mov     r8, [rsp+320h+var_2F8]; void *
0x1800b0321  mov     rdx, rbx; char *
0x1800b0324  lea     rcx, [rsp+320h+var_2F0]; this
0x1800b0329  call    ?StartActivity@ClientApiCallActivity@UiaProvider@@QEAAXPEBDPEBXH@Z; UiaProvider::ClientApiCallActivity::StartActivity(char const *,void const *,int)
0x1800b032e  nop
0x1800b032f  mov     ebx, [r15+138h]
0x1800b0336  lea     rax, ??_7?$ActivityBase@VUiaProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x1800b033d  mov     [rbp+220h+var_1A0], rax
0x1800b0344  mov     eax, [rdi]
0x1800b0346  mov     [rbp+220h+var_198], eax
0x1800b034c  mov     al, [rdi+4]
0x1800b034f  mov     [rbp+220h+var_194], al
0x1800b0355  movups  xmm0, xmmword ptr [rdi+8]
0x1800b0359  movdqu  [rbp+220h+var_190], xmm0
0x1800b0361  movups  xmm0, xmmword ptr [rdi+18h]
0x1800b0365  movdqu  [rbp+220h+var_180], xmm0
0x1800b036d  xor     r8d, r8d
0x1800b0370  mov     [rdi], r8d
0x1800b0373  mov     [rdi+4], r8b
0x1800b0377  xorps   xmm0, xmm0
0x1800b037a  movups  [rbp+220h+var_170], xmm0
0x1800b0381  movaps  [rbp+220h+var_160], xmm0
0x1800b0388  mov     eax, [rdi+28h]
0x1800b038b  mov     dword ptr [rbp+220h+var_170], eax
0x1800b0391  mov     rax, [rdi+30h]
0x1800b0395  mov     qword ptr [rbp+220h+var_170+8], rax
0x1800b039c  psrldq  xmm0, 8
0x1800b03a1  movd    eax, xmm0
0x1800b03a5  test    al, al
0x1800b03a7  jz      short loc_1800B03C0
0x1800b03a9  call    cs:__imp_GetProcessHeap
0x1800b03af  xor     r8d, r8d; lpMem
0x1800b03b2  xor     edx, edx; dwFlags
0x1800b03b4  mov     rcx, rax; hHeap
0x1800b03b7  call    cs:__imp_HeapFree
0x1800b03bd  xor     r8d, r8d
0x1800b03c0  mov     rax, [rdi+38h]
0x1800b03c4  mov     qword ptr [rbp+220h+var_160], rax
0x1800b03cb  mov     [rdi+38h], r8
0x1800b03cf  mov     al, [rdi+40h]
0x1800b03d2  mov     byte ptr [rbp+220h+var_160+8], al
0x1800b03d8  mov     [rdi+40h], r8b
0x1800b03dc  mov     eax, [rdi+48h]
0x1800b03df  mov     [rbp+220h+var_150], eax
0x1800b03e5  movups  xmm0, xmmword ptr [r14]
0x1800b03e9  movups  [rbp+220h+var_148], xmm0
0x1800b03f0  movups  xmm1, xmmword ptr [r14+10h]
0x1800b03f5  movups  [rbp+220h+var_138], xmm1
0x1800b03fc  movups  xmm0, xmmword ptr [r14+20h]
0x1800b0401  movups  [rbp+220h+var_128], xmm0
0x1800b0408  movups  xmm1, xmmword ptr [r14+30h]
0x1800b040d  movups  [rbp+220h+var_118], xmm1
0x1800b0414  movups  xmm0, xmmword ptr [r14+40h]
0x1800b0419  movups  [rbp+220h+var_108], xmm0
0x1800b0420  movups  xmm1, xmmword ptr [r14+50h]
0x1800b0425  movups  [rbp+220h+var_F8], xmm1
0x1800b042c  movups  xmm0, xmmword ptr [r14+60h]
0x1800b0431  movups  [rbp+220h+var_E8], xmm0
0x1800b0438  movups  xmm1, xmmword ptr [r14+70h]
0x1800b043d  movups  [rbp+220h+var_D8], xmm1
0x1800b0444  movups  xmm0, xmmword ptr [r14+80h]
0x1800b044c  movups  [rbp+220h+var_C8], xmm0
0x1800b0453  mov     rax, [r14+90h]
0x1800b045a  mov     [rbp+220h+var_B8], rax
0x1800b0461  mov     rax, [rdi+0E8h]
0x1800b0468  mov     [rbp+220h+var_B0], rax
0x1800b046f  mov     rax, [rdi+0F0h]
0x1800b0476  mov     [rbp+220h+var_A8], rax
0x1800b047d  mov     [rdi+0E8h], r8
0x1800b0484  mov     [rdi+0F0h], r8
0x1800b048b  mov     eax, [rdi+0F8h]
0x1800b0491  mov     [rbp+220h+var_A0], eax
0x1800b0497  xor     eax, eax
0x1800b0499  mov     [rbp+220h+var_98], rax
0x1800b04a0  mov     rcx, [r12]
0x1800b04a4  mov     [rbp+220h+var_88], rcx
0x1800b04ab  mov     [r12], r8
0x1800b04af  mov     [rbp+220h+var_80], r8
0x1800b04b6  lea     rax, [rbp+220h+var_1A0]
0x1800b04bd  mov     [rbp+220h+var_78], rax
0x1800b04c4  mov     [rbp+220h+var_70], r8
0x1800b04cb  mov     [rbp+220h+var_68], r8d
0x1800b04d2  mov     [rbp+220h+var_60], r8
0x1800b04d9  mov     [rbp+220h+var_58], r8b
0x1800b04e0  test    ebx, ebx
0x1800b04e2  jz      loc_1800B0586
0x1800b04e8  mov     rax, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800b04ef  mov     [rsp+320h+var_2F8], rax
0x1800b04f4  test    rax, rax
0x1800b04f7  jz      loc_1800B0586
0x1800b04fd  call    cs:__imp_GetCurrentThreadId
0x1800b0503  mov     r8d, eax; unsigned __int64
0x1800b0506  mov     [rsp+320h+var_300], r8d
0x1800b050b  mov     ebx, eax
0x1800b050d  shr     rbx, 2
0x1800b0511  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800b051b  mul     rbx
0x1800b051e  shr     rdx, 3
0x1800b0522  lea     rax, [rdx+rdx*4]
0x1800b0526  add     rax, rax
0x1800b0529  sub     rbx, rax
0x1800b052c  mov     rcx, [rsp+320h+var_2F8]
0x1800b0531  mov     rcx, [rcx+rbx*8]
0x1800b0535  test    rcx, rcx
0x1800b0538  jz      loc_1800B087D
0x1800b053e  cmp     [rcx], r8d
0x1800b0541  jz      short loc_1800B0549
0x1800b0543  mov     rcx, [rcx+8]
0x1800b0547  jmp     short loc_1800B0535
0x1800b0549  add     rcx, 10h
0x1800b054d  xor     r8d, r8d
0x1800b0550  mov     [rbp+220h+var_80], rcx
0x1800b0557  test    rcx, rcx
0x1800b055a  jz      short loc_1800B057F
0x1800b055c  mov     rax, [rcx]
0x1800b055f  mov     [rbp+220h+var_70], rax
0x1800b0566  lea     rax, [rbp+220h+var_80]
0x1800b056d  mov     [rcx], rax
0x1800b0570  call    cs:__imp_GetCurrentThreadId
0x1800b0576  mov     [rbp+220h+var_68], eax
0x1800b057c  xor     r8d, r8d
0x1800b057f  mov     rcx, [rbp+220h+var_88]
0x1800b0586  test    rcx, rcx
0x1800b0589  jnz     loc_1800B095D
0x1800b058f  lea     rcx, [rbp+220h+var_198]
0x1800b0596  mov     [rbp+220h+var_90], rcx
0x1800b059d  lea     rax, [rcx+28h]
0x1800b05a1  mov     [rbp+220h+var_60], rax
0x1800b05a8  mov     [r15+110h], rdi
0x1800b05af  cmp     [r15+138h], r8d
0x1800b05b6  jnz     loc_1800B096F
0x1800b05bc  lea     rax, ??_7ClientApiCallActivity@UiaProvider@@6B@; const UiaProvider::ClientApiCallActivity::`vftable'
0x1800b05c3  mov     [rbp+220h+var_1A0], rax
0x1800b05ca  mov     eax, [rsp+320h+var_2E8]
0x1800b05ce  mov     [rdi], eax
0x1800b05d0  mov     al, [rsp+320h+var_2E4]
0x1800b05d4  mov     [rdi+4], al
0x1800b05d7  movaps  xmm0, [rsp+320h+var_2E0]
0x1800b05dc  movdqu  xmmword ptr [rdi+8], xmm0
0x1800b05e1  movaps  xmm1, [rsp+320h+var_2D0]
0x1800b05e6  movdqu  xmmword ptr [rdi+18h], xmm1
0x1800b05eb  mov     [rsp+320h+var_2E8], r8d
0x1800b05f0  mov     [rsp+320h+var_2E4], r8b
0x1800b05f5  mov     eax, [rsp+320h+var_2C0]
0x1800b05f9  mov     [rdi+28h], eax
0x1800b05fc  mov     rax, [rsp+320h+var_2B8]
0x1800b0601  mov     [rdi+30h], rax
0x1800b0605  cmp     [rdi+40h], r8b
0x1800b0609  jz      short loc_1800B0626
0x1800b060b  mov     rbx, [rdi+38h]
0x1800b060f  call    cs:__imp_GetProcessHeap
0x1800b0615  mov     r8, rbx; lpMem
0x1800b0618  xor     edx, edx; dwFlags
0x1800b061a  mov     rcx, rax; hHeap
0x1800b061d  call    cs:__imp_HeapFree
0x1800b0623  xor     r8d, r8d
0x1800b0626  mov     rax, [rsp+320h+var_2B0]
0x1800b062b  mov     [rdi+38h], rax
0x1800b062f  mov     [rsp+320h+var_2B0], r8
0x1800b0634  mov     al, [rsp+320h+var_2A8]
0x1800b0638  mov     [rdi+40h], al
0x1800b063b  mov     [rsp+320h+var_2A8], r8b
0x1800b0640  mov     eax, [rbp+220h+var_2A0]
0x1800b0643  mov     [rdi+48h], eax
0x1800b0646  movups  xmm0, [rbp+220h+var_298]
0x1800b064a  movups  xmmword ptr [r14], xmm0
0x1800b064e  movups  xmm1, [rbp+220h+var_288]
0x1800b0652  movups  xmmword ptr [r14+10h], xmm1
0x1800b0657  movups  xmm0, [rbp+220h+var_278]
0x1800b065b  movups  xmmword ptr [r14+20h], xmm0
0x1800b0660  movups  xmm1, [rbp+220h+var_268]
0x1800b0664  movups  xmmword ptr [r14+30h], xmm1
0x1800b0669  movups  xmm0, [rbp+220h+var_258]
0x1800b066d  movups  xmmword ptr [r14+40h], xmm0
0x1800b0672  movups  xmm1, [rbp+220h+var_248]
0x1800b0676  movups  xmmword ptr [r14+50h], xmm1
0x1800b067b  movups  xmm0, [rbp+220h+var_238]
0x1800b067f  movups  xmmword ptr [r14+60h], xmm0
0x1800b0684  movups  xmm1, [rbp+220h+var_228]
0x1800b0688  movups  xmmword ptr [r14+70h], xmm1
0x1800b068d  movups  xmm0, [rbp+220h+var_218]
0x1800b0691  movups  xmmword ptr [r14+80h], xmm0
0x1800b0699  mov     rax, [rbp+220h+var_208]
0x1800b069d  mov     [r14+90h], rax
0x1800b06a4  lea     rax, [rbp+220h+var_200]
0x1800b06a8  or      r14d, 0FFFFFFFFh
0x1800b06ac  cmp     r13, rax
0x1800b06af  jz      short loc_1800B06D6
0x1800b06b1  mov     rcx, [r13+0]
0x1800b06b5  test    rcx, rcx
0x1800b06b8  jnz     loc_1800B084D
0x1800b06be  mov     rax, qword ptr [rbp+220h+var_200]
0x1800b06c2  mov     [r13+0], rax
0x1800b06c6  mov     rax, qword ptr [rbp+220h+var_200+8]
0x1800b06ca  mov     [r13+8], rax
0x1800b06ce  xorps   xmm0, xmm0
0x1800b06d1  movdqa  [rbp+220h+var_200], xmm0
0x1800b06d6  mov     eax, [rbp+220h+var_1F0]
0x1800b06d9  mov     [rdi+0F8h], eax
0x1800b06df  lea     rax, [rbp+220h+var_1D8]
0x1800b06e3  cmp     r12, rax
0x1800b06e6  jz      short loc_1800B0701
0x1800b06e8  mov     rcx, [r12]
0x1800b06ec  test    rcx, rcx
0x1800b06ef  jnz     loc_1800B0912
0x1800b06f5  mov     rax, [rbp+220h+var_1D8]
0x1800b06f9  mov     [r12], rax
0x1800b06fd  mov     [rbp+220h+var_1D8], r8
0x1800b0701  mov     rax, [r12]
  ... truncated ...
```

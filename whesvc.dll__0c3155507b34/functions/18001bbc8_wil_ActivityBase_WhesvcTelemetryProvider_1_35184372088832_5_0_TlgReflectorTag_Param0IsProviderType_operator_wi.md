# wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> &&)

- ea: `0x18001bbc8`
- end: `0x18001bef3`
- name: `??4?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `811`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001b290`

## callees

- `0x180003304`
- `0x1800084d0`
- `0x18000a568`
- `0x18001bbc8`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bc3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bd20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bc3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bd20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bc2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bd12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bc2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bd12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be8e`

## string_xrefs

- `0x18001be42`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`
- `0x18001beaa`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp
  __int64 v4; // r15
  __int64 v5; // rsi
  void **v6; // rdi
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  volatile signed __int32 **v9; // r12
  volatile signed __int32 **v10; // rdi
  volatile signed __int32 *v11; // rbx
  HANDLE v12; // rax
  volatile signed __int32 **v13; // r12
  volatile signed __int32 **v14; // rbx
  volatile signed __int32 *v15; // rdi
  _QWORD *v16; // rcx
  __int64 **v17; // rdi
  __int64 *Local; // rax
  int v19; // ebx
  __int64 *v20; // rcx
  __int64 v21; // rax
  __int64 **v22; // rbx
  __int64 *v23; // rcx
  __int64 v24; // rax
  void *retaddr; // [rsp+68h] [rbp+0h]

  v2 = a2;
  v4 = a2 + 8;
  v5 = a1 + 8;
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
  *(_BYTE *)(a1 + 12) = *(_BYTE *)(a2 + 12);
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(a1 + 32) = *(_OWORD *)(a2 + 32);
  *(_DWORD *)(a2 + 8) = 0;
  *(_BYTE *)(a2 + 12) = 0;
  *(_DWORD *)(a1 + 48) = *(_DWORD *)(a2 + 48);
  *(_QWORD *)(a1 + 56) = *(_QWORD *)(a2 + 56);
  v6 = (void **)(a1 + 64);
  if ( *(_BYTE *)(a1 + 72) )
  {
    v7 = *v6;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
    *(_BYTE *)(v5 + 64) = 0;
  }
  *v6 = 0;
  *v6 = *(void **)(v4 + 56);
  *(_QWORD *)(v4 + 56) = 0;
  *(_BYTE *)(v5 + 64) = *(_BYTE *)(v4 + 64);
  *(_BYTE *)(v4 + 64) = 0;
  *(_DWORD *)(a1 + 80) = *(_DWORD *)(v2 + 80);
  *(_OWORD *)(a1 + 88) = *(_OWORD *)(v2 + 88);
  *(_OWORD *)(a1 + 104) = *(_OWORD *)(v2 + 104);
  *(_OWORD *)(a1 + 120) = *(_OWORD *)(v2 + 120);
  *(_OWORD *)(a1 + 136) = *(_OWORD *)(v2 + 136);
  *(_OWORD *)(a1 + 152) = *(_OWORD *)(v2 + 152);
  *(_OWORD *)(a1 + 168) = *(_OWORD *)(v2 + 168);
  *(_OWORD *)(a1 + 184) = *(_OWORD *)(v2 + 184);
  *(_OWORD *)(a1 + 200) = *(_OWORD *)(v2 + 200);
  *(_OWORD *)(a1 + 216) = *(_OWORD *)(v2 + 216);
  *(_QWORD *)(a1 + 232) = *(_QWORD *)(v2 + 232);
  v9 = (volatile signed __int32 **)(v2 + 240);
  v10 = (volatile signed __int32 **)(a1 + 240);
  if ( a1 + 240 != v2 + 240 )
  {
    if ( *v10 )
    {
      if ( _InterlockedExchangeAdd(*v10, 0xFFFFFFFF) == 1 )
      {
        v11 = *v10;
        v12 = GetProcessHeap();
        HeapFree(v12, 0, (LPVOID)v11);
      }
      *v10 = 0;
      *(_QWORD *)(a1 + 248) = 0;
    }
    *v10 = *v9;
    *(_QWORD *)(a1 + 248) = *(_QWORD *)(v2 + 248);
    *v9 = 0;
    *(_QWORD *)(v2 + 248) = 0;
  }
  *(_DWORD *)(a1 + 256) = *(_DWORD *)(v2 + 256);
  v13 = (volatile signed __int32 **)(v2 + 280);
  v14 = (volatile signed __int32 **)(a1 + 280);
  if ( a1 + 280 == v2 + 280 )
  {
    v16 = (_QWORD *)(a1 + 280);
  }
  else
  {
    if ( *v14 )
    {
      if ( _InterlockedExchangeAdd(*v14, 0xFFFFFFFF) == 1 && (v15 = *v14) != 0 )
      {
        wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WhesvcTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WhesvcTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(v15 + 2);
        operator delete((void *)v15);
        v16 = (_QWORD *)(a1 + 280);
      }
      else
      {
        v16 = (_QWORD *)(a1 + 280);
      }
      *v14 = 0;
    }
    else
    {
      v16 = (_QWORD *)(a1 + 280);
    }
    *v14 = *v13;
    *v13 = 0;
  }
  if ( *v16 )
    v5 = *v16 + 8LL;
  *(_QWORD *)(a1 + 272) = v5;
  v17 = (__int64 **)(a1 + 288);
  *(_QWORD *)(a1 + 320) = v5 + 40;
  if ( !*(_DWORD *)(v2 + 312) )
  {
    if ( !*(_DWORD *)(a1 + 312) )
      goto LABEL_37;
    v19 = *(_DWORD *)(a1 + 312);
    if ( v19 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(a1 + 312) = 0;
    v20 = *v17;
    while ( 1 )
    {
      v21 = *v20;
      if ( !*v20 )
        goto LABEL_36;
      if ( (__int64 **)v21 == v17 )
      {
        *v20 = *(_QWORD *)(a1 + 304);
        goto LABEL_36;
      }
      v20 = (__int64 *)(v21 + 16);
      *v17 = (__int64 *)(v21 + 16);
    }
  }
  if ( *(_DWORD *)(a1 + 312) )
    goto LABEL_37;
  if ( !wil::details::g_pThreadFailureCallbacks )
  {
LABEL_36:
    *v17 = 0;
    goto LABEL_37;
  }
  LOBYTE(a2) = 1;
  Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                       v16,
                       a2);
  *v17 = Local;
  if ( Local )
  {
    *(_QWORD *)(a1 + 304) = *Local;
    *Local = (__int64)v17;
    *(_DWORD *)(a1 + 312) = GetCurrentThreadId();
  }
LABEL_37:
  *(_QWORD *)(v2 + 272) = v4;
  if ( *(_DWORD *)(v2 + 312) )
  {
    v22 = (__int64 **)(v2 + 288);
    if ( *(_DWORD *)(v2 + 312) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(v2 + 312) = 0;
    v23 = *v22;
    while ( 1 )
    {
      v24 = *v23;
      if ( !*v23 )
        break;
      if ( (__int64 **)v24 == v22 )
      {
        *v23 = *(_QWORD *)(v2 + 304);
        break;
      }
      v23 = (__int64 *)(v24 + 16);
      *v22 = (__int64 *)(v24 + 16);
    }
    *v22 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001bbc8  push    rbx
0x18001bbca  push    rbp
0x18001bbcb  push    rsi
0x18001bbcc  push    rdi
0x18001bbcd  push    r12
0x18001bbcf  push    r13
0x18001bbd1  push    r14
0x18001bbd3  push    r15
0x18001bbd5  sub     rsp, 28h
0x18001bbd9  mov     rbp, rdx
0x18001bbdc  mov     r14, rcx
0x18001bbdf  lea     r15, [rdx+8]
0x18001bbe3  lea     rsi, [rcx+8]
0x18001bbe7  mov     eax, [r15]
0x18001bbea  mov     [rsi], eax
0x18001bbec  mov     al, [r15+4]
0x18001bbf0  mov     [rsi+4], al
0x18001bbf3  movups  xmm0, xmmword ptr [r15+8]
0x18001bbf8  movdqu  xmmword ptr [rsi+8], xmm0
0x18001bbfd  movups  xmm1, xmmword ptr [r15+18h]
0x18001bc02  movdqu  xmmword ptr [rsi+18h], xmm1
0x18001bc07  xor     r13d, r13d
0x18001bc0a  mov     [r15], r13d
0x18001bc0d  mov     [r15+4], r13b
0x18001bc11  mov     eax, [r15+28h]
0x18001bc15  mov     [rsi+28h], eax
0x18001bc18  mov     rax, [r15+30h]
0x18001bc1c  mov     [rsi+30h], rax
0x18001bc20  lea     rdi, [rsi+38h]
0x18001bc24  cmp     [rsi+40h], r13b
0x18001bc28  jz      short loc_18001BC45
0x18001bc2a  mov     rbx, [rdi]
0x18001bc2d  call    cs:__imp_GetProcessHeap
0x18001bc33  mov     r8, rbx; lpMem
0x18001bc36  xor     edx, edx; dwFlags
0x18001bc38  mov     rcx, rax; hHeap
0x18001bc3b  call    cs:__imp_HeapFree
0x18001bc41  mov     [rsi+40h], r13b
0x18001bc45  mov     [rdi], r13
0x18001bc48  mov     rax, [r15+38h]
0x18001bc4c  mov     [rdi], rax
0x18001bc4f  mov     [r15+38h], r13
0x18001bc53  mov     al, [r15+40h]
0x18001bc57  mov     [rsi+40h], al
0x18001bc5a  mov     [r15+40h], r13b
0x18001bc5e  mov     eax, [rbp+50h]
0x18001bc61  mov     [r14+50h], eax
0x18001bc65  movups  xmm0, xmmword ptr [rbp+58h]
0x18001bc69  movups  xmmword ptr [r14+58h], xmm0
0x18001bc6e  movups  xmm1, xmmword ptr [rbp+68h]
0x18001bc72  movups  xmmword ptr [r14+68h], xmm1
0x18001bc77  movups  xmm0, xmmword ptr [rbp+78h]
0x18001bc7b  movups  xmmword ptr [r14+78h], xmm0
0x18001bc80  movups  xmm1, xmmword ptr [rbp+88h]
0x18001bc87  movups  xmmword ptr [r14+88h], xmm1
0x18001bc8f  movups  xmm0, xmmword ptr [rbp+98h]
0x18001bc96  movups  xmmword ptr [r14+98h], xmm0
0x18001bc9e  movups  xmm1, xmmword ptr [rbp+0A8h]
0x18001bca5  movups  xmmword ptr [r14+0A8h], xmm1
0x18001bcad  movups  xmm0, xmmword ptr [rbp+0B8h]
0x18001bcb4  movups  xmmword ptr [r14+0B8h], xmm0
0x18001bcbc  movups  xmm1, xmmword ptr [rbp+0C8h]
0x18001bcc3  movups  xmmword ptr [r14+0C8h], xmm1
0x18001bccb  movups  xmm0, xmmword ptr [rbp+0D8h]
0x18001bcd2  movups  xmmword ptr [r14+0D8h], xmm0
0x18001bcda  mov     rax, [rbp+0E8h]
0x18001bce1  mov     [r14+0E8h], rax
0x18001bce8  lea     r12, [rbp+0F0h]
0x18001bcef  lea     rdi, [r14+0F0h]
0x18001bcf6  cmp     rdi, r12
0x18001bcf9  jz      short loc_18001BD46
0x18001bcfb  mov     rcx, [rdi]
0x18001bcfe  test    rcx, rcx
0x18001bd01  jz      short loc_18001BD2D
0x18001bd03  or      eax, 0FFFFFFFFh
0x18001bd06  lock xadd [rcx], eax
0x18001bd0a  cmp     eax, 1
0x18001bd0d  jnz     short loc_18001BD26
0x18001bd0f  mov     rbx, [rdi]
0x18001bd12  call    cs:__imp_GetProcessHeap
0x18001bd18  mov     r8, rbx; lpMem
0x18001bd1b  xor     edx, edx; dwFlags
0x18001bd1d  mov     rcx, rax; hHeap
0x18001bd20  call    cs:__imp_HeapFree
0x18001bd26  mov     [rdi], r13
0x18001bd29  mov     [rdi+8], r13
0x18001bd2d  mov     rax, [r12]
0x18001bd31  mov     [rdi], rax
0x18001bd34  mov     rax, [r12+8]
0x18001bd39  mov     [rdi+8], rax
0x18001bd3d  mov     [r12], r13
0x18001bd41  mov     [r12+8], r13
0x18001bd46  mov     eax, [rbp+100h]
0x18001bd4c  mov     [r14+100h], eax
0x18001bd53  lea     r12, [rbp+118h]
0x18001bd5a  lea     rbx, [r14+118h]
0x18001bd61  cmp     rbx, r12
0x18001bd64  jz      short loc_18001BDB9
0x18001bd66  mov     rcx, [rbx]
0x18001bd69  test    rcx, rcx
0x18001bd6c  jz      short loc_18001BDA9
0x18001bd6e  or      eax, 0FFFFFFFFh
0x18001bd71  lock xadd [rcx], eax
0x18001bd75  cmp     eax, 1
0x18001bd78  jnz     short loc_18001BDA1
0x18001bd7a  mov     rdi, [rbx]
0x18001bd7d  test    rdi, rdi
0x18001bd80  jz      short loc_18001BDA1
0x18001bd82  lea     rcx, [rdi+8]
0x18001bd86  call    ??1?$ActivityData@VWhesvcTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WhesvcTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WhesvcTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001bd8b  mov     edx, 110h; unsigned __int64
0x18001bd90  mov     rcx, rdi; void *
0x18001bd93  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bd98  lea     rcx, [r14+118h]
0x18001bd9f  jmp     short loc_18001BDA4
0x18001bda1  mov     rcx, rbx
0x18001bda4  mov     [rbx], r13
0x18001bda7  jmp     short loc_18001BDAC
0x18001bda9  mov     rcx, rbx
0x18001bdac  mov     rax, [r12]
0x18001bdb0  mov     [rbx], rax
0x18001bdb3  mov     [r12], r13
0x18001bdb7  jmp     short loc_18001BDBC
0x18001bdb9  mov     rcx, rbx
0x18001bdbc  mov     rax, [rcx]
0x18001bdbf  test    rax, rax
0x18001bdc2  jz      short loc_18001BDC8
0x18001bdc4  lea     rsi, [rax+8]
0x18001bdc8  mov     [r14+110h], rsi
0x18001bdcf  lea     rdi, [r14+120h]
0x18001bdd6  lea     rax, [rsi+28h]
0x18001bdda  mov     [rdi+20h], rax
0x18001bdde  cmp     [rbp+138h], r13d
0x18001bde5  jz      short loc_18001BE1E
0x18001bde7  cmp     [rdi+18h], r13d
0x18001bdeb  jnz     loc_18001BE77
0x18001bdf1  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r13; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001bdf8  jz      short loc_18001BE74
0x18001bdfa  mov     dl, 1
0x18001bdfc  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001be01  mov     [rdi], rax
0x18001be04  test    rax, rax
0x18001be07  jz      short loc_18001BE77
0x18001be09  mov     rcx, [rax]
0x18001be0c  mov     [rdi+10h], rcx
0x18001be10  mov     [rax], rdi
0x18001be13  call    cs:__imp_GetCurrentThreadId
0x18001be19  mov     [rdi+18h], eax
0x18001be1c  jmp     short loc_18001BE77
0x18001be1e  cmp     [rdi+18h], r13d
0x18001be22  jz      short loc_18001BE77
0x18001be24  mov     ebx, [rdi+18h]
0x18001be27  call    cs:__imp_GetCurrentThreadId
0x18001be2d  cmp     ebx, eax
0x18001be2f  jz      short loc_18001BE4E
0x18001be31  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001be38  test    rax, rax
0x18001be3b  jz      short loc_18001BE4E
0x18001be3d  mov     rdx, [rsp+68h]
0x18001be42  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001be49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be4e  mov     [rdi+18h], r13d
0x18001be52  mov     rcx, [rdi]
0x18001be55  jmp     short loc_18001BE63
0x18001be57  cmp     rax, rdi
0x18001be5a  jz      short loc_18001BE6D
0x18001be5c  lea     rcx, [rax+10h]
0x18001be60  mov     [rdi], rcx
0x18001be63  mov     rax, [rcx]
0x18001be66  test    rax, rax
0x18001be69  jnz     short loc_18001BE57
0x18001be6b  jmp     short loc_18001BE74
0x18001be6d  mov     rax, [rdi+10h]
0x18001be71  mov     [rcx], rax
0x18001be74  mov     [rdi], r13
0x18001be77  mov     [rbp+110h], r15
0x18001be7e  cmp     [rbp+138h], r13d
0x18001be85  jz      short loc_18001BEDF
0x18001be87  lea     rbx, [rbp+120h]
0x18001be8e  call    cs:__imp_GetCurrentThreadId
0x18001be94  cmp     [rbx+18h], eax
0x18001be97  jz      short loc_18001BEB6
0x18001be99  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001bea0  test    rax, rax
0x18001bea3  jz      short loc_18001BEB6
0x18001bea5  mov     rdx, [rsp+68h]
0x18001beaa  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001beb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001beb6  mov     [rbx+18h], r13d
0x18001beba  mov     rcx, [rbx]
0x18001bebd  jmp     short loc_18001BECB
0x18001bebf  cmp     rax, rbx
0x18001bec2  jz      short loc_18001BED5
0x18001bec4  lea     rcx, [rax+10h]
0x18001bec8  mov     [rbx], rcx
0x18001becb  mov     rax, [rcx]
0x18001bece  test    rax, rax
0x18001bed1  jnz     short loc_18001BEBF
0x18001bed3  jmp     short loc_18001BEDC
0x18001bed5  mov     rax, [rbx+10h]
0x18001bed9  mov     [rcx], rax
0x18001bedc  mov     [rbx], r13
0x18001bedf  mov     rax, r14
0x18001bee2  add     rsp, 28h
0x18001bee6  pop     r15
0x18001bee8  pop     r14
0x18001beea  pop     r13
0x18001beec  pop     r12
0x18001beee  pop     rdi
0x18001beef  pop     rsi
0x18001bef0  pop     rbp
0x18001bef1  pop     rbx
0x18001bef2  retn
```

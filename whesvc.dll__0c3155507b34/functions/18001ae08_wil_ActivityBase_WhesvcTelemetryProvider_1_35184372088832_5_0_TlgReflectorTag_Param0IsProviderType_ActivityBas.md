# wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)

- ea: `0x18001ae08`
- end: `0x18001b07d`
- name: `??0?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b290`

## callees

- `0x1800084d0`
- `0x18001ae08`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ae9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ae9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ae8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ae8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001afd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b018`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001afd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b018`

## string_xrefs

- `0x18001b034`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2,
        char a3)
{
  __int64 v4; // rbp
  __int64 v6; // rdi
  __int64 v7; // r14
  void **v8; // r15
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v11; // rbx
  _QWORD *Local; // rax
  __int64 v13; // rax
  __int64 **v14; // rbx
  __int64 *v15; // rcx
  __int64 v16; // rax
  void *retaddr; // [rsp+68h] [rbp+0h]

  v4 = a2;
  *(_QWORD *)a1 = &wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v6 = a1 + 8;
  v7 = a2 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 12) = 0;
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
  *(_BYTE *)(a1 + 12) = *(_BYTE *)(a2 + 12);
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(a1 + 32) = *(_OWORD *)(a2 + 32);
  *(_DWORD *)(a2 + 8) = 0;
  *(_BYTE *)(a2 + 12) = 0;
  *(_OWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 48) = *(_DWORD *)(a2 + 48);
  *(_QWORD *)(a1 + 56) = *(_QWORD *)(a2 + 56);
  v8 = (void **)(a1 + 64);
  if ( *(_BYTE *)(a1 + 72) )
  {
    v9 = *v8;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
    *(_BYTE *)(v6 + 64) = 0;
  }
  *v8 = 0;
  *v8 = *(void **)(v7 + 56);
  *(_QWORD *)(v7 + 56) = 0;
  *(_BYTE *)(v6 + 64) = *(_BYTE *)(v7 + 64);
  *(_BYTE *)(v7 + 64) = 0;
  *(_DWORD *)(a1 + 80) = *(_DWORD *)(v4 + 80);
  *(_OWORD *)(a1 + 88) = *(_OWORD *)(v4 + 88);
  *(_OWORD *)(a1 + 104) = *(_OWORD *)(v4 + 104);
  *(_OWORD *)(a1 + 120) = *(_OWORD *)(v4 + 120);
  *(_OWORD *)(a1 + 136) = *(_OWORD *)(v4 + 136);
  *(_OWORD *)(a1 + 152) = *(_OWORD *)(v4 + 152);
  *(_OWORD *)(a1 + 168) = *(_OWORD *)(v4 + 168);
  *(_OWORD *)(a1 + 184) = *(_OWORD *)(v4 + 184);
  *(_OWORD *)(a1 + 200) = *(_OWORD *)(v4 + 200);
  *(_OWORD *)(a1 + 216) = *(_OWORD *)(v4 + 216);
  *(_QWORD *)(a1 + 232) = *(_QWORD *)(v4 + 232);
  *(_QWORD *)(a1 + 240) = *(_QWORD *)(v4 + 240);
  *(_QWORD *)(a1 + 248) = *(_QWORD *)(v4 + 248);
  *(_QWORD *)(v4 + 240) = 0;
  *(_QWORD *)(v4 + 248) = 0;
  *(_DWORD *)(a1 + 256) = *(_DWORD *)(v4 + 256);
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 280) = *(_QWORD *)(v4 + 280);
  *(_QWORD *)(v4 + 280) = 0;
  v11 = (_QWORD *)(a1 + 288);
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = a1;
  *(_QWORD *)(a1 + 304) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = 0;
  *(_BYTE *)(a1 + 328) = 0;
  if ( a3 )
  {
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(a2) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          a1,
                          a2);
      *v11 = Local;
      if ( Local )
      {
        *(_QWORD *)(a1 + 304) = *Local;
        *Local = v11;
        *(_DWORD *)(a1 + 312) = GetCurrentThreadId();
      }
    }
  }
  v13 = *(_QWORD *)(a1 + 280);
  if ( v13 )
    v6 = v13 + 8;
  *(_QWORD *)(a1 + 272) = v6;
  *(_QWORD *)(a1 + 320) = v6 + 40;
  *(_QWORD *)(v4 + 272) = v7;
  if ( *(_DWORD *)(v4 + 312) )
  {
    v14 = (__int64 **)(v4 + 288);
    if ( *(_DWORD *)(v4 + 312) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(v4 + 312) = 0;
    v15 = *v14;
    while ( 1 )
    {
      v16 = *v15;
      if ( !*v15 )
        break;
      if ( (__int64 **)v16 == v14 )
      {
        *v15 = *(_QWORD *)(v4 + 304);
        break;
      }
      v15 = (__int64 *)(v16 + 16);
      *v14 = (__int64 *)(v16 + 16);
    }
    *v14 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001ae08  push    rbx
0x18001ae0a  push    rbp
0x18001ae0b  push    rsi
0x18001ae0c  push    rdi
0x18001ae0d  push    r12
0x18001ae0f  push    r13
0x18001ae11  push    r14
0x18001ae13  push    r15
0x18001ae15  sub     rsp, 28h
0x18001ae19  mov     r12b, r8b
0x18001ae1c  mov     rbp, rdx
0x18001ae1f  mov     rsi, rcx
0x18001ae22  lea     rax, ??_7?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18001ae29  mov     [rcx], rax
0x18001ae2c  lea     rdi, [rcx+8]
0x18001ae30  lea     r14, [rdx+8]
0x18001ae34  xor     r13d, r13d
0x18001ae37  mov     [rdi], r13d
0x18001ae3a  mov     [rdi+4], r13b
0x18001ae3e  mov     eax, [r14]
0x18001ae41  mov     [rdi], eax
0x18001ae43  mov     al, [r14+4]
0x18001ae47  mov     [rdi+4], al
0x18001ae4a  movups  xmm0, xmmword ptr [r14+8]
0x18001ae4f  movdqu  xmmword ptr [rdi+8], xmm0
0x18001ae54  movups  xmm1, xmmword ptr [r14+18h]
0x18001ae59  movdqu  xmmword ptr [rdi+18h], xmm1
0x18001ae5e  mov     [r14], r13d
0x18001ae61  mov     [r14+4], r13b
0x18001ae65  xorps   xmm0, xmm0
0x18001ae68  movups  xmmword ptr [rdi+28h], xmm0
0x18001ae6c  movups  xmmword ptr [rdi+38h], xmm0
0x18001ae70  mov     eax, [r14+28h]
0x18001ae74  mov     [rdi+28h], eax
0x18001ae77  mov     rax, [r14+30h]
0x18001ae7b  mov     [rdi+30h], rax
0x18001ae7f  lea     r15, [rdi+38h]
0x18001ae83  cmp     [rdi+40h], r13b
0x18001ae87  jz      short loc_18001AEA4
0x18001ae89  mov     rbx, [r15]
0x18001ae8c  call    cs:__imp_GetProcessHeap
0x18001ae92  mov     r8, rbx; lpMem
0x18001ae95  xor     edx, edx; dwFlags
0x18001ae97  mov     rcx, rax; hHeap
0x18001ae9a  call    cs:__imp_HeapFree
0x18001aea0  mov     [rdi+40h], r13b
0x18001aea4  mov     [r15], r13
0x18001aea7  mov     rax, [r14+38h]
0x18001aeab  mov     [r15], rax
0x18001aeae  mov     [r14+38h], r13
0x18001aeb2  mov     al, [r14+40h]
0x18001aeb6  mov     [rdi+40h], al
0x18001aeb9  mov     [r14+40h], r13b
0x18001aebd  mov     eax, [rbp+50h]
0x18001aec0  mov     [rsi+50h], eax
0x18001aec3  movups  xmm0, xmmword ptr [rbp+58h]
0x18001aec7  movups  xmmword ptr [rsi+58h], xmm0
0x18001aecb  movups  xmm1, xmmword ptr [rbp+68h]
0x18001aecf  movups  xmmword ptr [rsi+68h], xmm1
0x18001aed3  movups  xmm0, xmmword ptr [rbp+78h]
0x18001aed7  movups  xmmword ptr [rsi+78h], xmm0
0x18001aedb  movups  xmm1, xmmword ptr [rbp+88h]
0x18001aee2  movups  xmmword ptr [rsi+88h], xmm1
0x18001aee9  movups  xmm0, xmmword ptr [rbp+98h]
0x18001aef0  movups  xmmword ptr [rsi+98h], xmm0
0x18001aef7  movups  xmm1, xmmword ptr [rbp+0A8h]
0x18001aefe  movups  xmmword ptr [rsi+0A8h], xmm1
0x18001af05  movups  xmm0, xmmword ptr [rbp+0B8h]
0x18001af0c  movups  xmmword ptr [rsi+0B8h], xmm0
0x18001af13  movups  xmm1, xmmword ptr [rbp+0C8h]
0x18001af1a  movups  xmmword ptr [rsi+0C8h], xmm1
0x18001af21  movups  xmm0, xmmword ptr [rbp+0D8h]
0x18001af28  movups  xmmword ptr [rsi+0D8h], xmm0
0x18001af2f  mov     rax, [rbp+0E8h]
0x18001af36  mov     [rsi+0E8h], rax
0x18001af3d  mov     rax, [rbp+0F0h]
0x18001af44  mov     [rsi+0F0h], rax
0x18001af4b  mov     rax, [rbp+0F8h]
0x18001af52  mov     [rsi+0F8h], rax
0x18001af59  mov     [rbp+0F0h], r13
0x18001af60  mov     [rbp+0F8h], r13
0x18001af67  mov     eax, [rbp+100h]
0x18001af6d  mov     [rsi+100h], eax
0x18001af73  xor     eax, eax
0x18001af75  mov     [rsi+108h], rax
0x18001af7c  mov     rax, [rbp+118h]
0x18001af83  mov     [rsi+118h], rax
0x18001af8a  mov     [rbp+118h], r13
0x18001af91  lea     rbx, [rsi+120h]
0x18001af98  mov     [rbx], r13
0x18001af9b  mov     [rbx+8], rsi
0x18001af9f  mov     [rbx+10h], r13
0x18001afa3  mov     [rbx+18h], r13d
0x18001afa7  mov     [rbx+20h], r13
0x18001afab  mov     [rbx+28h], r13b
0x18001afaf  test    r12b, r12b
0x18001afb2  jz      short loc_18001AFDF
0x18001afb4  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r13; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001afbb  jz      short loc_18001AFDF
0x18001afbd  mov     dl, 1
0x18001afbf  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001afc4  mov     [rbx], rax
0x18001afc7  test    rax, rax
0x18001afca  jz      short loc_18001AFDF
0x18001afcc  mov     rcx, [rax]
0x18001afcf  mov     [rbx+10h], rcx
0x18001afd3  mov     [rax], rbx
0x18001afd6  call    cs:__imp_GetCurrentThreadId
0x18001afdc  mov     [rbx+18h], eax
0x18001afdf  mov     rax, [rsi+118h]
0x18001afe6  test    rax, rax
0x18001afe9  jz      short loc_18001AFEF
0x18001afeb  lea     rdi, [rax+8]
0x18001afef  mov     [rsi+110h], rdi
0x18001aff6  lea     rax, [rdi+28h]
0x18001affa  mov     [rsi+140h], rax
0x18001b001  mov     [rbp+110h], r14
0x18001b008  cmp     [rbp+138h], r13d
0x18001b00f  jz      short loc_18001B069
0x18001b011  lea     rbx, [rbp+120h]
0x18001b018  call    cs:__imp_GetCurrentThreadId
0x18001b01e  cmp     [rbx+18h], eax
0x18001b021  jz      short loc_18001B040
0x18001b023  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001b02a  test    rax, rax
0x18001b02d  jz      short loc_18001B040
0x18001b02f  mov     rdx, [rsp+68h]
0x18001b034  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001b03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b040  mov     [rbx+18h], r13d
0x18001b044  mov     rcx, [rbx]
0x18001b047  jmp     short loc_18001B055
0x18001b049  cmp     rax, rbx
0x18001b04c  jz      short loc_18001B05F
0x18001b04e  lea     rcx, [rax+10h]
0x18001b052  mov     [rbx], rcx
0x18001b055  mov     rax, [rcx]
0x18001b058  test    rax, rax
0x18001b05b  jnz     short loc_18001B049
0x18001b05d  jmp     short loc_18001B066
0x18001b05f  mov     rax, [rbx+10h]
0x18001b063  mov     [rcx], rax
0x18001b066  mov     [rbx], r13
0x18001b069  mov     rax, rsi
0x18001b06c  add     rsp, 28h
0x18001b070  pop     r15
0x18001b072  pop     r14
0x18001b074  pop     r13
0x18001b076  pop     r12
0x18001b078  pop     rdi
0x18001b079  pop     rsi
0x18001b07a  pop     rbp
0x18001b07b  pop     rbx
0x18001b07c  retn
```

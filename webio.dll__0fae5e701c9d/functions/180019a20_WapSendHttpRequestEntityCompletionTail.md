# WapSendHttpRequestEntityCompletionTail

- ea: `0x180019a20`
- end: `0x180019efb`
- name: `WapSendHttpRequestEntityCompletionTail`
- size: `1243`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180018370`
- `0x1800194a0`
- `0x180019580`
- `0x18001f200`
- `0x180036448`
- `0x18006ab94`

## callees

- `0x180014f30`
- `0x1800180e0`
- `0x180018860`
- `0x180019a20`
- `0x18001b150`
- `0x18003cad0`
- `0x180054794`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019c7f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019ccb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019c7f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019ccb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180019c5f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180019c5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019ce9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019dca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019ce9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019dca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019afd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019bd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019eab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019afd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019bd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019eab`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019da2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019da2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180019e18`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180019e18`

## pseudocode

```c
void __fastcall WapSendHttpRequestEntityCompletionTail(char *lpMem, __int64 a2, __int64 a3)
{
  char v4; // di
  int v5; // ecx
  _DWORD *v6; // r9
  _QWORD *v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // r8
  _QWORD *v11; // rdx
  struct _RTL_CRITICAL_SECTION *v12; // r12
  __int64 v13; // rax
  _QWORD **v14; // rdi
  __int64 v15; // rax
  DWORD v16; // ecx
  _QWORD *v17; // rsi
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // rdx
  _QWORD *v21; // rcx
  __int64 v22; // r8
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rcx
  _QWORD *v26; // rax
  bool v27; // zf
  __int128 v28; // [rsp+30h] [rbp-50h] BYREF
  __int128 v29; // [rsp+40h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+50h] [rbp-30h] BYREF
  __int128 *v31; // [rsp+60h] [rbp-20h]
  __int64 v32; // [rsp+68h] [rbp-18h]

  v28 = 0;
  while ( 1 )
  {
    v4 = 0;
    if ( lpMem[1857] )
      goto LABEL_21;
    v5 = *((_DWORD *)lpMem + 76);
    if ( (v5 & 0x800) != 0 )
      goto LABEL_14;
    if ( lpMem[56] || (v6 = lpMem + 48, !*((_DWORD *)lpMem + 12)) )
    {
      v6 = lpMem + 48;
    }
    else if ( ((*((_DWORD *)lpMem + 76) & 0x104) != 4 || *((_DWORD *)lpMem + 81) == 3)
           && (*((_DWORD *)lpMem + 493) & 5) != 1 )
    {
      if ( (v5 & 0xC0) == 0x40 )
      {
        *((_DWORD *)lpMem + 76) = v5 | 0x80;
        if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
        {
          *(_QWORD *)&v29 = lpMem;
          v31 = &v29;
          v32 = 8;
          McGenEventWrite_EventWriteTransfer(
            &WEB_ETW_PROVIDER_ID_Context,
            (const EVENT_DESCRIPTOR *)RequestSendComplete,
            a3,
            2u,
            &v30);
        }
        if ( (lpMem[1972] & 0x10) != 0 )
          v4 = 1;
      }
LABEL_21:
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 8));
      if ( v4 )
        WaFinishHttpRequest(lpMem);
      return;
    }
    *((_QWORD *)&v28 + 1) = &v28;
    v7 = lpMem + 1880;
    *(_QWORD *)&v28 = &v28;
    while ( 1 )
    {
      v8 = (_QWORD *)*v7;
      if ( (_QWORD *)*v7 == v7 || !*((_BYTE *)v8 + 48) )
        break;
      v9 = *v8;
      if ( *(_QWORD **)(*v8 + 8LL) != v8 )
        goto LABEL_37;
      v10 = (_QWORD *)v8[1];
      if ( (_QWORD *)*v10 != v8 )
        goto LABEL_37;
      *v10 = v9;
      *(_QWORD *)(v9 + 8) = v10;
      v11 = (_QWORD *)*((_QWORD *)&v28 + 1);
      if ( **((__int128 ***)&v28 + 1) != &v28 )
        goto LABEL_37;
      v8[1] = *((_QWORD *)&v28 + 1);
      *v8 = &v28;
      *v11 = v8;
      *((_QWORD *)&v28 + 1) = v8;
    }
    if ( (lpMem[56] || !*v6) && v8 == v7 )
    {
      v20 = lpMem + 1864;
      while ( 1 )
      {
        v21 = (_QWORD *)*v20;
        if ( (_QWORD *)*v20 == v20 )
          break;
        *((_BYTE *)v21 + 48) = 1;
        *((_DWORD *)v21 + 30) = *((_DWORD *)lpMem + 13);
        v21[16] = 0;
        v22 = *v21;
        if ( *(_QWORD **)(*v21 + 8LL) != v21 )
          goto LABEL_37;
        v23 = (_QWORD *)v21[1];
        if ( (_QWORD *)*v23 != v21 )
          goto LABEL_37;
        *v23 = v22;
        *(_QWORD *)(v22 + 8) = v23;
        v24 = (_QWORD *)*((_QWORD *)&v28 + 1);
        if ( **((__int128 ***)&v28 + 1) != &v28 )
          goto LABEL_37;
        v21[1] = *((_QWORD *)&v28 + 1);
        *v21 = &v28;
        *v24 = v21;
        *((_QWORD *)&v28 + 1) = v21;
      }
    }
    if ( (__int128 *)v28 == &v28 )
    {
LABEL_14:
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 8));
      return;
    }
    if ( (*((_DWORD *)lpMem + 76) & 0xC0) != 0x40
      || (v27 = (lpMem[1972] & 0x10) == 0, *((_DWORD *)lpMem + 76) |= 0x80u, v27) )
    {
      lpMem[1857] = 1;
      v12 = (struct _RTL_CRITICAL_SECTION *)(lpMem + 8);
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 8));
    }
    else
    {
      lpMem[1857] = 1;
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 8));
      WaFinishHttpRequest(lpMem);
      v12 = (struct _RTL_CRITICAL_SECTION *)(lpMem + 8);
    }
    v13 = v28;
    if ( *(__int128 **)(v28 + 8) != &v28 )
      goto LABEL_37;
    v14 = (_QWORD **)(lpMem + 1952);
    *((_QWORD *)lpMem + 244) = v28;
    *((_QWORD *)lpMem + 245) = &v28;
    *(_QWORD *)(v13 + 8) = lpMem + 1952;
    *(_QWORD *)&v28 = lpMem + 1952;
    if ( *((__int128 **)lpMem + 245) != &v28 )
      goto LABEL_37;
    v15 = *((_QWORD *)&v28 + 1);
    if ( **((__int128 ***)&v28 + 1) != &v28 )
      goto LABEL_37;
    **((_QWORD **)&v28 + 1) = v14;
    *((_QWORD *)lpMem + 245) = v15;
    _InterlockedIncrement((volatile signed __int32 *)lpMem + 1);
    v16 = WaCallbackQueueTlsIndex;
    v17 = lpMem + 1904;
    *((_QWORD *)lpMem + 239) = lpMem + 1904;
    *((_QWORD *)lpMem + 238) = lpMem + 1904;
    *((_QWORD *)lpMem + 243) = WapCompleteSendTrackersCallback;
    *((_QWORD *)lpMem + 240) = -1;
    if ( TlsGetValue(v16) || !TlsSetValue(WaCallbackQueueTlsIndex, (LPVOID)1) )
      break;
    while ( 1 )
    {
      v18 = *v14;
      if ( *v14 == v14 )
        break;
      if ( (_QWORD **)v18[1] != v14 )
        goto LABEL_37;
      v19 = (_QWORD *)*v18;
      if ( *(_QWORD **)(*v18 + 8LL) != v18 )
        goto LABEL_37;
      *v14 = v19;
      v19[1] = v14;
      v18[1] = v18;
      *v18 = v18;
      WapCompleteHttpRequestSendTracker(v18 - 2);
    }
    TlsSetValue(WaCallbackQueueTlsIndex, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 1, 0xFFFFFFFF) == 1 )
      WapDestroyHttpRequest(lpMem);
    EnterCriticalSection(v12);
    lpMem[1857] = 0;
  }
  WaGetCurrentThreadToken((__int64 *)lpMem + 240);
  v29 = 0;
  if ( EventActivityIdControl(1u, (LPGUID)(lpMem + 1928)) )
    *(_OWORD *)(lpMem + 1928) = 0;
  if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
    McTemplateU0pq_EventWriteTransfer(v25, ThreadActionQueue, lpMem + 1904, 2);
  EnterCriticalSection(&WaGlobalCallbackQueueLock);
  v26 = (_QWORD *)qword_1800AEB38;
  if ( *(__int64 **)qword_1800AEB38 != &WaGlobalCallbackQueue )
LABEL_37:
    __fastfail(3u);
  *v17 = &WaGlobalCallbackQueue;
  *((_QWORD *)lpMem + 239) = v26;
  *v26 = v17;
  qword_1800AEB38 = (__int64)(lpMem + 1904);
  LeaveCriticalSection(&WaGlobalCallbackQueueLock);
  SubmitThreadpoolWork(pwk);
}

```

## disassembly

```asm
0x180019a20  mov     r11, rsp
0x180019a23  push    rbp
0x180019a24  push    rbx
0x180019a25  push    rdi
0x180019a26  push    r13
0x180019a28  push    r15
0x180019a2a  mov     rbp, rsp
0x180019a2d  sub     rsp, 80h
0x180019a34  mov     rax, cs:__security_cookie
0x180019a3b  xor     rax, rsp
0x180019a3e  mov     [rbp+var_10], rax
0x180019a42  mov     [r11+10h], rsi
0x180019a46  lea     r13, WapCompleteSendTrackersCallback
0x180019a4d  xorps   xmm0, xmm0
0x180019a50  mov     [r11+18h], r12
0x180019a54  movups  [rbp+var_50], xmm0
0x180019a58  mov     [r11+20h], r14
0x180019a5c  mov     rbx, rcx
0x180019a5f  xor     dil, dil
0x180019a62  cmp     [rbx+741h], dil
0x180019a69  jnz     loc_180019B66
0x180019a6f  mov     ecx, [rbx+130h]
0x180019a75  bt      ecx, 0Bh
0x180019a79  jb      short loc_180019AF9
0x180019a7b  cmp     [rbx+38h], dil
0x180019a7f  jnz     loc_180019D12
0x180019a85  cmp     dword ptr [rbx+30h], 0
0x180019a89  lea     r9, [rbx+30h]
0x180019a8d  jz      loc_180019D12
0x180019a93  mov     eax, ecx
0x180019a95  and     eax, 104h
0x180019a9a  cmp     eax, 4
0x180019a9d  jnz     short loc_180019AA8
0x180019a9f  cmp     dword ptr [rbx+144h], 3
0x180019aa6  jnz     short loc_180019AB8
0x180019aa8  mov     eax, [rbx+7B4h]
0x180019aae  and     al, 5
0x180019ab0  cmp     al, 1
0x180019ab2  jnz     loc_180019B5A
0x180019ab8  lea     rax, [rbp+var_50]
0x180019abc  mov     qword ptr [rbp+var_50+8], rax
0x180019ac0  lea     rcx, [rbx+758h]
0x180019ac7  lea     rax, [rbp+var_50]
0x180019acb  mov     qword ptr [rbp+var_50], rax
0x180019acf  mov     rax, [rcx]
0x180019ad2  cmp     rax, rcx
0x180019ad5  jnz     short loc_180019B0B
0x180019ad7  cmp     [rbx+38h], dil
0x180019adb  jnz     loc_180019D1B
0x180019ae1  cmp     dword ptr [r9], 0
0x180019ae5  jz      loc_180019D1B
0x180019aeb  lea     rax, [rbp+var_50]
0x180019aef  cmp     qword ptr [rbp+var_50], rax
0x180019af3  jnz     loc_180019BB3
0x180019af9  lea     rcx, [rbx+8]; lpCriticalSection
0x180019afd  call    cs:__imp_LeaveCriticalSection
0x180019b04  nop     dword ptr [rax+rax+00h]
0x180019b09  jmp     short loc_180019B7F
0x180019b0b  cmp     [rax+30h], dil
0x180019b0f  jz      short loc_180019AD7
0x180019b11  mov     rdx, [rax]
0x180019b14  cmp     [rdx+8], rax
0x180019b18  jnz     loc_180019D01
0x180019b1e  mov     r8, [rax+8]
0x180019b22  cmp     [r8], rax
0x180019b25  jnz     loc_180019D01
0x180019b2b  mov     [r8], rdx
0x180019b2e  mov     [rdx+8], r8
0x180019b32  lea     r8, [rbp+var_50]
0x180019b36  mov     rdx, qword ptr [rbp+var_50+8]
0x180019b3a  cmp     [rdx], r8
0x180019b3d  jnz     loc_180019D01
0x180019b43  mov     [rax+8], rdx
0x180019b47  lea     r8, [rbp+var_50]
0x180019b4b  mov     [rax], r8
0x180019b4e  mov     [rdx], rax
0x180019b51  mov     qword ptr [rbp+var_50+8], rax
0x180019b55  jmp     loc_180019ACF
0x180019b5a  mov     eax, ecx
0x180019b5c  and     al, 0C0h
0x180019b5e  cmp     al, 40h ; '@'
0x180019b60  jz      loc_180019E29
0x180019b66  lea     rcx, [rbx+8]; lpCriticalSection
0x180019b6a  call    cs:__imp_LeaveCriticalSection
0x180019b71  nop     dword ptr [rax+rax+00h]
0x180019b76  test    dil, dil
0x180019b79  jnz     loc_180019EEE
0x180019b7f  mov     r14, [rsp+80h+arg_18]
0x180019b87  mov     r12, [rsp+80h+arg_10]
0x180019b8f  mov     rsi, [rsp+80h+arg_8]
0x180019b97  mov     rcx, [rbp+var_10]
0x180019b9b  xor     rcx, rsp; StackCookie
0x180019b9e  call    __security_check_cookie
0x180019ba3  add     rsp, 80h
0x180019baa  pop     r15
0x180019bac  pop     r13
0x180019bae  pop     rdi
0x180019baf  pop     rbx
0x180019bb0  pop     rbp
0x180019bb1  retn
0x180019bb3  mov     ecx, [rbx+130h]
0x180019bb9  mov     eax, ecx
0x180019bbb  and     al, 0C0h
0x180019bbd  cmp     al, 40h ; '@'
0x180019bbf  jz      loc_180019E89
0x180019bc5  lea     rcx, [rbx+8]; lpCriticalSection
0x180019bc9  mov     byte ptr [rbx+741h], 1
0x180019bd0  lea     r12, [rbx+8]
0x180019bd4  call    cs:__imp_LeaveCriticalSection
0x180019bdb  nop     dword ptr [rax+rax+00h]
0x180019be0  mov     rax, qword ptr [rbp+var_50]
0x180019be4  lea     rcx, [rbp+var_50]
0x180019be8  cmp     [rax+8], rcx
0x180019bec  jnz     loc_180019D01
0x180019bf2  lea     rdi, [rbx+7A0h]
0x180019bf9  mov     [rdi], rax
0x180019bfc  lea     rcx, [rbp+var_50]
0x180019c00  mov     [rdi+8], rcx
0x180019c04  mov     [rax+8], rdi
0x180019c08  lea     rax, [rbp+var_50]
0x180019c0c  mov     qword ptr [rbp+var_50], rdi
0x180019c10  cmp     [rdi+8], rax
0x180019c14  jnz     loc_180019D01
0x180019c1a  mov     rax, qword ptr [rbp+var_50+8]
0x180019c1e  lea     rcx, [rbp+var_50]
0x180019c22  cmp     [rax], rcx
0x180019c25  jnz     loc_180019D01
0x180019c2b  mov     [rax], rdi
0x180019c2e  mov     [rdi+8], rax
0x180019c32  lock inc dword ptr [rbx+4]
0x180019c36  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x180019c3c  lea     rsi, [rbx+770h]
0x180019c43  mov     [rbx+778h], rsi
0x180019c4a  mov     [rsi], rsi
0x180019c4d  mov     [rbx+798h], r13
0x180019c54  mov     qword ptr [rbx+780h], 0FFFFFFFFFFFFFFFFh
0x180019c5f  call    cs:__imp_TlsGetValue
0x180019c66  nop     dword ptr [rax+rax+00h]
0x180019c6b  test    rax, rax
0x180019c6e  jnz     loc_180019D86
0x180019c74  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x180019c7a  mov     edx, 1; lpTlsValue
0x180019c7f  call    cs:__imp_TlsSetValue
0x180019c86  nop     dword ptr [rax+rax+00h]
0x180019c8b  test    eax, eax
0x180019c8d  jz      loc_180019D86
0x180019c93  mov     rcx, [rdi]
0x180019c96  cmp     rcx, rdi
0x180019c99  jz      short loc_180019CC3
0x180019c9b  cmp     [rcx+8], rdi
0x180019c9f  jnz     short loc_180019D01
0x180019ca1  mov     rax, [rcx]
0x180019ca4  cmp     [rax+8], rcx
0x180019ca8  jnz     short loc_180019D01
0x180019caa  mov     [rdi], rax
0x180019cad  mov     [rax+8], rdi
0x180019cb1  mov     [rcx+8], rcx
0x180019cb5  mov     [rcx], rcx
0x180019cb8  add     rcx, 0FFFFFFFFFFFFFFF0h; lpMem
0x180019cbc  call    WapCompleteHttpRequestSendTracker
0x180019cc1  jmp     short loc_180019C93
0x180019cc3  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x180019cc9  xor     edx, edx; lpTlsValue
0x180019ccb  call    cs:__imp_TlsSetValue
0x180019cd2  nop     dword ptr [rax+rax+00h]
0x180019cd7  mov     eax, 0FFFFFFFFh
0x180019cdc  lock xadd [rbx+4], eax
0x180019ce1  cmp     eax, 1
0x180019ce4  jz      short loc_180019D08
0x180019ce6  mov     rcx, r12; lpCriticalSection
0x180019ce9  call    cs:__imp_EnterCriticalSection
0x180019cf0  nop     dword ptr [rax+rax+00h]
0x180019cf5  mov     byte ptr [rbx+741h], 0
0x180019cfc  jmp     loc_180019A5F
0x180019d01  mov     ecx, 3
0x180019d06  int     29h; Win8: RtlFailFast(ecx)
0x180019d08  mov     rcx, rbx; lpMem
0x180019d0b  call    WapDestroyHttpRequest
0x180019d10  jmp     short loc_180019CE6
0x180019d12  lea     r9, [rbx+30h]
0x180019d16  jmp     loc_180019AB8
0x180019d1b  cmp     rax, rcx
0x180019d1e  jnz     loc_180019AEB
0x180019d24  lea     rdx, [rbx+748h]
0x180019d2b  mov     rcx, [rdx]
0x180019d2e  cmp     rcx, rdx
0x180019d31  jz      loc_180019AEB
0x180019d37  mov     byte ptr [rcx+30h], 1
0x180019d3b  mov     eax, [rbx+34h]
0x180019d3e  mov     [rcx+78h], eax
0x180019d41  mov     qword ptr [rcx+80h], 0
0x180019d4c  mov     r8, [rcx]
0x180019d4f  cmp     [r8+8], rcx
0x180019d53  jnz     short loc_180019D01
0x180019d55  mov     rax, [rcx+8]
0x180019d59  cmp     [rax], rcx
0x180019d5c  jnz     short loc_180019D01
0x180019d5e  mov     [rax], r8
0x180019d61  mov     [r8+8], rax
0x180019d65  lea     r8, [rbp+var_50]
0x180019d69  mov     rax, qword ptr [rbp+var_50+8]
0x180019d6d  cmp     [rax], r8
0x180019d70  jnz     short loc_180019D01
0x180019d72  mov     [rcx+8], rax
0x180019d76  lea     r8, [rbp+var_50]
0x180019d7a  mov     [rcx], r8
0x180019d7d  mov     [rax], rcx
0x180019d80  mov     qword ptr [rbp+var_50+8], rcx
0x180019d84  jmp     short loc_180019D2B
0x180019d86  lea     rcx, [rbx+780h]
0x180019d8d  call    WaGetCurrentThreadToken
0x180019d92  xorps   xmm0, xmm0
0x180019d95  lea     rdx, [rsi+18h]; ActivityId
0x180019d99  mov     ecx, 1; ControlCode
0x180019d9e  movups  [rbp+var_40], xmm0
0x180019da2  call    cs:__imp_EventActivityIdControl
0x180019da9  nop     dword ptr [rax+rax+00h]
0x180019dae  test    eax, eax
0x180019db0  jnz     loc_180019EC8
0x180019db6  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x180019dbd  jnz     loc_180019ED4
0x180019dc3  lea     rcx, WaGlobalCallbackQueueLock; lpCriticalSection
0x180019dca  call    cs:__imp_EnterCriticalSection
0x180019dd1  nop     dword ptr [rax+rax+00h]
0x180019dd6  mov     rax, cs:qword_1800AEB38
0x180019ddd  lea     rcx, WaGlobalCallbackQueue
0x180019de4  cmp     [rax], rcx
0x180019de7  jnz     loc_180019D01
0x180019ded  mov     [rsi], rcx
0x180019df0  lea     rcx, WaGlobalCallbackQueueLock; lpCriticalSection
0x180019df7  mov     [rsi+8], rax
0x180019dfb  mov     [rax], rsi
0x180019dfe  mov     cs:qword_1800AEB38, rsi
0x180019e05  call    cs:__imp_LeaveCriticalSection
0x180019e0c  nop     dword ptr [rax+rax+00h]
0x180019e11  mov     rcx, cs:pwk; pwk
0x180019e18  call    cs:__imp_SubmitThreadpoolWork
0x180019e1f  nop     dword ptr [rax+rax+00h]
0x180019e24  jmp     loc_180019B7F
0x180019e29  bts     ecx, 7
0x180019e2d  mov     [rbx+130h], ecx
0x180019e33  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 40h
0x180019e3a  jnz     short loc_180019E51
0x180019e3c  test    byte ptr [rbx+7B4h], 10h
0x180019e43  jz      loc_180019B66
0x180019e49  mov     dil, 1
0x180019e4c  jmp     loc_180019B66
0x180019e51  lea     rax, [rbp+var_40]
0x180019e55  mov     qword ptr [rbp+var_40], rbx
0x180019e59  mov     [rbp+var_20], rax
0x180019e5d  lea     rdx, RequestSendComplete
0x180019e64  lea     rax, [rbp+var_30]
0x180019e68  mov     [rbp+var_18], 8
0x180019e70  mov     r9d, 2
0x180019e76  mov     [rsp+80h+var_60], rax
0x180019e7b  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180019e82  call    McGenEventWrite_EventWriteTransfer
0x180019e87  jmp     short loc_180019E3C
0x180019e89  bts     ecx, 7
0x180019e8d  test    byte ptr [rbx+7B4h], 10h
0x180019e94  mov     [rbx+130h], ecx
0x180019e9a  jz      loc_180019BC5
0x180019ea0  lea     rcx, [rbx+8]; lpCriticalSection
0x180019ea4  mov     byte ptr [rbx+741h], 1
0x180019eab  call    cs:__imp_LeaveCriticalSection
0x180019eb2  nop     dword ptr [rax+rax+00h]
0x180019eb7  mov     rcx, rbx
0x180019eba  call    WaFinishHttpRequest
0x180019ebf  lea     r12, [rbx+8]
0x180019ec3  jmp     loc_180019BE0
0x180019ec8  xorps   xmm0, xmm0
0x180019ecb  movups  xmmword ptr [rsi+18h], xmm0
0x180019ecf  jmp     loc_180019DB6
0x180019ed4  mov     r9d, 2
0x180019eda  lea     rdx, ThreadActionQueue
0x180019ee1  mov     r8, rsi
0x180019ee4  call    McTemplateU0pq_EventWriteTransfer
0x180019ee9  jmp     loc_180019DC3
0x180019eee  mov     rcx, rbx
0x180019ef1  call    WaFinishHttpRequest
0x180019ef6  jmp     loc_180019B7F
```

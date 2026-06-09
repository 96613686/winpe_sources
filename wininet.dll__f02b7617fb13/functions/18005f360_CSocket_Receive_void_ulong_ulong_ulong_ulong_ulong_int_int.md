# CSocket::Receive(void * *,ulong *,ulong *,ulong *,ulong,ulong,int,int *)

- ea: `0x18005f360`
- end: `0x18005fa38`
- name: `?Receive@CSocket@@UEAAKPEAPEAXPEAK11KKHPEAH@Z`
- size: `1752`
- prototype: `unsigned int __fastcall(CSocket *__hidden this, void **, unsigned int *, unsigned int *, unsigned int *, unsigned int, unsigned int, int, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x18005f360`
- `0x180060650`
- `0x1800d2e04`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801e4988`
- `0x1801e6e08`
- `0x1801e7088`
- `0x1801eb11c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f48a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f625`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f48a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f3a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f3a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f6e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f755`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f6e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f896`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f90f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f933`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f896`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f90f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f933`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005f476`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005f611`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005f476`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005f611`
- `ntdll!RtlGetLastNtStatus` at `0x18005f6f2`
- `ntdll!RtlGetLastNtStatus` at `0x18005f766`
- `ntdll!RtlGetLastNtStatus` at `0x18005f6f2`
- `ntdll!RtlGetLastNtStatus` at `0x18005f766`

## pseudocode

```c
__int64 __fastcall CSocket::Receive(
        CSocket *this,
        void **a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        int *a9)
{
  unsigned int v13; // ebp
  _QWORD *v14; // rdi
  DWORD LastError; // eax
  DWORD v16; // esi
  _QWORD *Value; // rbx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  DWORD v23; // eax
  DWORD v24; // esi
  struct _INTERNET_THREAD_INFO *ThreadInfo; // rbx
  _QWORD *v26; // rcx
  __int64 v28; // rbx
  __int64 v29; // rbx
  DWORD v30; // eax
  DWORD CurrentThreadId; // eax
  DWORD v32; // eax

  if ( (xmmword_180266B60 & 8) != 0 )
    WPP_SF_qqqdqdqddDql(
      (_DWORD)a9,
      73,
      (unsigned int)WPP_bd14be58d2f038a275675270d4ce3d8e_Traceguids,
      (_DWORD)a2,
      (__int64)*a2,
      (__int64)a3,
      *a3,
      (__int64)a4,
      *a4,
      (__int64)a5,
      *a5,
      a6,
      a7,
      (__int64)a9,
      *a9);
  v13 = 12004;
  v14 = HeapAlloc(g_hWxProcessHeap, 0, 0x138u);
  if ( v14 )
  {
    memset_0(v14, 0, 0x138u);
    *v14 = &CFsm::`vftable';
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_q(1032, 13, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v14);
    v14[4] = 0;
    *((_DWORD *)v14 + 21) = -1;
    *((_DWORD *)v14 + 22) = -1;
    *((_DWORD *)v14 + 23) = -1;
    v14[12] = CFsm_SocketReceive::RunSM;
    v14[7] = 0;
    v14[8] = 0;
    v14[9] = 0;
    *((_DWORD *)v14 + 10) = 12004;
    *((_DWORD *)v14 + 20) = 12004;
    v14[13] = this;
    *((_DWORD *)v14 + 28) = 0;
    v14[15] = 0;
    *((_DWORD *)v14 + 32) = -1;
    *(_QWORD *)((char *)v14 + 132) = 0;
    *(_QWORD *)((char *)v14 + 140) = 0;
    *(_QWORD *)((char *)v14 + 148) = 0;
    *((_DWORD *)v14 + 42) = 0;
    v14[20] = 0;
    *(_QWORD *)((char *)v14 + 188) = 0;
    LastError = GetLastError();
    v16 = LastError;
    if ( qword_180269EA8
      && LastError
      && LastError != 997
      && LastError != 12150
      && LastError != 12028
      && LastError != 122 )
    {
      v28 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
      GetSystemTimeAsFileTime((LPFILETIME)(v28 + qword_180269EA8));
      *(_DWORD *)(v28 + qword_180269EA8 + 8) = v16;
      *(_DWORD *)(v28 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
    }
    Value = TlsGetValue(InternetTlsIndex);
    if ( !Value )
    {
      if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
      {
        CurrentThreadId = GetCurrentThreadId();
        WPP_SF_d(1037, 22, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, CurrentThreadId);
      }
      Value = (_QWORD *)InternetCreateThreadInfo(1);
      if ( !Value && (BYTE1(xmmword_180266B60) & 0x20) != 0 )
        WPP_SF_(1037, 23, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids);
    }
    SetLastError(v16);
    v14[6] = Value;
    if ( Value )
    {
      v14[7] = Value[5];
      v14[8] = Value[6];
      v14[9] = Value[7];
      v14[10] = *((unsigned int *)Value + 19);
      *((_DWORD *)v14 + 22) = 4;
      *((_DWORD *)v14 + 10) = 0;
      if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
        WPP_SF_qss(
          1033,
          17,
          (unsigned int)WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids,
          (_DWORD)v14,
          (__int64)qword_180222338,
          (__int64)qword_180222338);
      v18 = v14[6];
      v14[4] = *(_QWORD *)(v18 + 80);
      *(_QWORD *)(v18 + 80) = v14;
      if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
      {
        WPP_SF_q(1033, 18, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v14[4]);
        if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
        {
          v30 = GetCurrentThreadId();
          WPP_SF_qD(1033, 19, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v14, v30);
          if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
            WPP_SF_(1033, 20, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids);
        }
      }
    }
    else
    {
      *((_DWORD *)v14 + 10) = 12004;
    }
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_(1032, 14, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids);
    *v14 = &CFsm_SocketReceive::`vftable';
    if ( !*((_DWORD *)v14 + 10) )
    {
      *((_DWORD *)v14 + 58) = a6;
      *((_DWORD *)v14 + 59) = a7;
      v14[30] = a9;
      v14[25] = a2;
      v14[26] = a3;
      v14[27] = a4;
      v14[28] = a5;
      v19 = (__int64)*a2;
      v14[31] = *a2;
      v14[32] = v19;
      *((_DWORD *)v14 + 66) = *a3;
      *((_DWORD *)v14 + 67) = *a4;
      *((_DWORD *)v14 + 68) = *a5;
      v20 = v14[6];
      *(_QWORD *)((char *)v14 + 276) = 0;
      *((_DWORD *)v14 + 71) = 0;
      v14[36] = 0;
      v14[37] = 0;
      *((_DWORD *)v14 + 76) = 0;
      v21 = *(_QWORD *)(v20 + 56);
      if ( v21 )
      {
        v14[36] = *(_QWORD *)(v21 + 976);
        v22 = *(_QWORD *)(v21 + 984);
        if ( !v22 )
          v22 = *(_QWORD *)(v21 + 976);
        v14[37] = v22;
      }
    }
  }
  else
  {
    v14 = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
    WPP_SF_qs(
      1033,
      11,
      (unsigned int)WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids,
      (_DWORD)v14,
      (__int64)qword_180222338);
  v23 = GetLastError();
  v24 = v23;
  if ( qword_180269EA8 && v23 && v23 != 997 && v23 != 12150 && v23 != 12028 && v23 != 122 )
  {
    v29 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
    GetSystemTimeAsFileTime((LPFILETIME)(v29 + qword_180269EA8));
    *(_DWORD *)(v29 + qword_180269EA8 + 8) = v24;
    *(_DWORD *)(v29 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
  }
  ThreadInfo = (struct _INTERNET_THREAD_INFO *)TlsGetValue(InternetTlsIndex);
  if ( !ThreadInfo )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
    {
      v32 = GetCurrentThreadId();
      WPP_SF_d(1037, 22, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, v32);
    }
    ThreadInfo = (struct _INTERNET_THREAD_INFO *)InternetCreateThreadInfo(1);
    if ( !ThreadInfo && (BYTE1(xmmword_180266B60) & 0x20) != 0 )
      WPP_SF_(1037, 23, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids);
  }
  SetLastError(v24);
  if ( !ThreadInfo )
  {
    if ( !v14 )
      goto LABEL_29;
    v26 = v14;
    goto LABEL_46;
  }
  if ( v14 )
  {
    v13 = *((_DWORD *)v14 + 10);
    v26 = v14;
    if ( !v13 )
    {
      v13 = CFsm::Run((CFsm *)v14, ThreadInfo, 0, 0, 0);
      goto LABEL_29;
    }
LABEL_46:
    (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v26, 1);
    goto LABEL_29;
  }
  v13 = 8;
LABEL_29:
  if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
    WPP_SF_d(1033, 12, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v13);
  if ( (xmmword_180266B60 & 8) != 0 )
    WPP_SF_d(1027, 74, WPP_bd14be58d2f038a275675270d4ce3d8e_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18005f360  push    rbx
0x18005f362  push    rbp
0x18005f363  push    rsi
0x18005f364  push    rdi
0x18005f365  push    r12
0x18005f367  push    r13
0x18005f369  push    r14
0x18005f36b  push    r15
0x18005f36d  sub     rsp, 88h
0x18005f374  mov     r14, r9
0x18005f377  mov     r15, r8
0x18005f37a  mov     r12, rdx
0x18005f37d  mov     rbx, rcx
0x18005f380  test    byte ptr cs:xmmword_180266B60, 8
0x18005f387  mov     r13, [rsp+0C8h+arg_20]
0x18005f38f  jnz     loc_18005F972
0x18005f395  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18005f39c  xor     edx, edx; dwFlags
0x18005f39e  mov     r8d, 138h; dwBytes
0x18005f3a4  call    cs:__imp_HeapAlloc
0x18005f3aa  xor     esi, esi
0x18005f3ac  mov     ebp, 2EE4h
0x18005f3b1  mov     rdi, rax
0x18005f3b4  lea     rax, qword_180222338
0x18005f3bb  test    rdi, rdi
0x18005f3be  jz      loc_18005FA08
0x18005f3c4  xor     edx, edx; Val
0x18005f3c6  mov     r8d, 138h; Size
0x18005f3cc  mov     rcx, rdi; void *
0x18005f3cf  call    memset_0
0x18005f3d4  lea     rax, ??_7CFsm@@6B@; const CFsm::`vftable'
0x18005f3db  mov     [rdi], rax
0x18005f3de  test    byte ptr cs:xmmword_180266B60+1, 1
0x18005f3e5  jnz     loc_18005F9E2
0x18005f3eb  or      eax, 0FFFFFFFFh
0x18005f3ee  mov     [rdi+20h], rsi
0x18005f3f2  mov     [rdi+54h], eax
0x18005f3f5  mov     [rdi+58h], eax
0x18005f3f8  mov     [rdi+5Ch], eax
0x18005f3fb  lea     rax, ?RunSM@CFsm_SocketReceive@@SAKPEAVCFsm@@@Z; CFsm_SocketReceive::RunSM(CFsm *)
0x18005f402  mov     [rdi+60h], rax
0x18005f406  mov     [rdi+38h], rsi
0x18005f40a  mov     [rdi+40h], rsi
0x18005f40e  mov     [rdi+48h], rsi
0x18005f412  mov     [rdi+28h], ebp
0x18005f415  mov     [rdi+50h], ebp
0x18005f418  mov     [rdi+68h], rbx
0x18005f41c  mov     [rdi+70h], esi
0x18005f41f  mov     [rdi+78h], rsi
0x18005f423  mov     dword ptr [rdi+80h], 0FFFFFFFFh
0x18005f42d  mov     [rdi+84h], rsi
0x18005f434  mov     [rdi+8Ch], rsi
0x18005f43b  mov     [rdi+94h], rsi
0x18005f442  mov     [rdi+0A8h], esi
0x18005f448  mov     [rdi+0A0h], rsi
0x18005f44f  mov     [rdi+0BCh], rsi
0x18005f456  call    cs:__imp_GetLastError
0x18005f45c  cmp     cs:qword_180269EA8, 0
0x18005f464  mov     esi, eax
0x18005f466  jz      short loc_18005F470
0x18005f468  test    eax, eax
0x18005f46a  jnz     loc_18005F694
0x18005f470  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x18005f476  call    cs:__imp_TlsGetValue
0x18005f47c  mov     rbx, rax
0x18005f47f  test    rax, rax
0x18005f482  jz      loc_18005F7BB
0x18005f488  mov     ecx, esi; dwErrCode
0x18005f48a  call    cs:__imp_SetLastError
0x18005f490  xor     esi, esi
0x18005f492  mov     [rdi+30h], rbx
0x18005f496  test    rbx, rbx
0x18005f499  jz      loc_18005FA00
0x18005f49f  mov     rax, [rbx+28h]
0x18005f4a3  mov     [rdi+38h], rax
0x18005f4a7  mov     rax, [rbx+30h]
0x18005f4ab  mov     [rdi+40h], rax
0x18005f4af  mov     rax, [rbx+38h]
0x18005f4b3  mov     [rdi+48h], rax
0x18005f4b7  mov     eax, [rbx+4Ch]
0x18005f4ba  mov     [rdi+50h], eax
0x18005f4bd  mov     [rdi+54h], esi
0x18005f4c0  mov     dword ptr [rdi+58h], 4
0x18005f4c7  mov     [rdi+28h], esi
0x18005f4ca  mov     bl, 2
0x18005f4cc  test    byte ptr cs:xmmword_180266B60+1, bl
0x18005f4d2  jnz     loc_18005F8E0
0x18005f4d8  mov     rcx, [rdi+30h]
0x18005f4dc  mov     rax, [rcx+50h]
0x18005f4e0  mov     [rdi+20h], rax
0x18005f4e4  mov     [rcx+50h], rdi
0x18005f4e8  test    byte ptr cs:xmmword_180266B60+1, bl
0x18005f4ee  jnz     loc_18005F870
0x18005f4f4  test    byte ptr cs:xmmword_180266B60+1, 1
0x18005f4fb  jnz     loc_18005F957
0x18005f501  lea     rax, ??_7CFsm_SocketReceive@@6B@; const CFsm_SocketReceive::`vftable'
0x18005f508  mov     [rdi], rax
0x18005f50b  cmp     [rdi+28h], esi
0x18005f50e  jnz     loc_18005F5DD
0x18005f514  mov     eax, [rsp+0C8h+arg_28]
0x18005f51b  mov     [rdi+0E8h], eax
0x18005f521  mov     eax, [rsp+0C8h+arg_30]
0x18005f528  mov     [rdi+0ECh], eax
0x18005f52e  mov     rax, [rsp+0C8h+arg_40]
0x18005f536  mov     [rdi+0F0h], rax
0x18005f53d  mov     [rdi+0C8h], r12
0x18005f544  mov     [rdi+0D0h], r15
0x18005f54b  mov     [rdi+0D8h], r14
0x18005f552  mov     [rdi+0E0h], r13
0x18005f559  mov     rax, [r12]
0x18005f55d  mov     [rdi+0F8h], rax
0x18005f564  mov     [rdi+100h], rax
0x18005f56b  mov     eax, [r15]
0x18005f56e  mov     [rdi+108h], eax
0x18005f574  mov     eax, [r14]
0x18005f577  mov     [rdi+10Ch], eax
0x18005f57d  mov     eax, [r13+0]
0x18005f581  mov     [rdi+110h], eax
0x18005f587  mov     rax, [rdi+30h]
0x18005f58b  mov     [rdi+114h], rsi
0x18005f592  mov     [rdi+11Ch], esi
0x18005f598  mov     [rdi+120h], rsi
0x18005f59f  mov     [rdi+128h], rsi
0x18005f5a6  mov     [rdi+130h], esi
0x18005f5ac  mov     rcx, [rax+38h]
0x18005f5b0  test    rcx, rcx
0x18005f5b3  jz      short loc_18005F5DD
0x18005f5b5  mov     rax, [rcx+3D0h]
0x18005f5bc  mov     [rdi+120h], rax
0x18005f5c3  mov     rax, [rcx+3D8h]
0x18005f5ca  test    rax, rax
0x18005f5cd  jnz     short loc_18005F5D6
0x18005f5cf  mov     rax, [rcx+3D0h]
0x18005f5d6  mov     [rdi+128h], rax
0x18005f5dd  lea     rax, qword_180222338
0x18005f5e4  test    byte ptr cs:xmmword_180266B60+1, 2
0x18005f5eb  jnz     loc_18005F84D
0x18005f5f1  call    cs:__imp_GetLastError
0x18005f5f7  cmp     cs:qword_180269EA8, 0
0x18005f5ff  mov     esi, eax
0x18005f601  jz      short loc_18005F60B
0x18005f603  test    eax, eax
0x18005f605  jnz     loc_18005F708
0x18005f60b  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x18005f611  call    cs:__imp_TlsGetValue
0x18005f617  mov     rbx, rax
0x18005f61a  test    rax, rax
0x18005f61d  jz      loc_18005F804
0x18005f623  mov     ecx, esi; dwErrCode
0x18005f625  call    cs:__imp_SetLastError
0x18005f62b  test    rbx, rbx
0x18005f62e  jz      loc_18005F77C
0x18005f634  test    rdi, rdi
0x18005f637  jz      loc_18005FA10
0x18005f63d  mov     ebp, [rdi+28h]
0x18005f640  mov     rcx, rdi; this
0x18005f643  test    ebp, ebp
0x18005f645  jnz     loc_18005F788
0x18005f64b  xor     r9d, r9d; void *
0x18005f64e  mov     [rsp+0C8h+var_A8], 0; unsigned int *
0x18005f657  xor     r8d, r8d; unsigned int *
0x18005f65a  mov     rdx, rbx; struct _INTERNET_THREAD_INFO *
0x18005f65d  call    ?Run@CFsm@@QEAAKPEAU_INTERNET_THREAD_INFO@@PEAKPEAX1@Z; CFsm::Run(_INTERNET_THREAD_INFO *,ulong *,void *,ulong *)
0x18005f662  mov     ebp, eax
0x18005f664  test    byte ptr cs:xmmword_180266B60+1, 2
0x18005f66b  jnz     loc_18005F79D
0x18005f671  test    byte ptr cs:xmmword_180266B60, 8
0x18005f678  jnz     loc_18005FA1A
0x18005f67e  mov     eax, ebp
0x18005f680  add     rsp, 88h
0x18005f687  pop     r15
0x18005f689  pop     r14
0x18005f68b  pop     r13
0x18005f68d  pop     r12
0x18005f68f  pop     rdi
0x18005f690  pop     rsi
0x18005f691  pop     rbp
0x18005f692  pop     rbx
0x18005f693  retn
0x18005f694  cmp     esi, 3E5h
0x18005f69a  jz      loc_18005F470
0x18005f6a0  cmp     esi, 2F76h
0x18005f6a6  jz      loc_18005F470
0x18005f6ac  cmp     esi, 2EFCh
0x18005f6b2  jz      loc_18005F470
0x18005f6b8  cmp     esi, 7Ah ; 'z'
0x18005f6bb  jz      loc_18005F470
0x18005f6c1  mov     eax, 1
0x18005f6c6  lock xadd cs:dword_180269EA4, eax
0x18005f6ce  mov     rcx, cs:qword_180269EA8
0x18005f6d5  inc     eax
0x18005f6d7  movzx   ebx, al
0x18005f6da  shl     rbx, 4
0x18005f6de  add     rcx, rbx; lpSystemTimeAsFileTime
0x18005f6e1  call    cs:__imp_GetSystemTimeAsFileTime
0x18005f6e7  mov     rax, cs:qword_180269EA8
0x18005f6ee  mov     [rbx+rax+8], esi
0x18005f6f2  call    cs:__imp_RtlGetLastNtStatus
0x18005f6f8  mov     rcx, cs:qword_180269EA8
0x18005f6ff  mov     [rbx+rcx+0Ch], eax
0x18005f703  jmp     loc_18005F470
0x18005f708  cmp     esi, 3E5h
0x18005f70e  jz      loc_18005F60B
0x18005f714  cmp     esi, 2F76h
0x18005f71a  jz      loc_18005F60B
0x18005f720  cmp     esi, 2EFCh
0x18005f726  jz      loc_18005F60B
0x18005f72c  cmp     esi, 7Ah ; 'z'
0x18005f72f  jz      loc_18005F60B
0x18005f735  mov     eax, 1
0x18005f73a  lock xadd cs:dword_180269EA4, eax
0x18005f742  mov     rcx, cs:qword_180269EA8
0x18005f749  inc     eax
0x18005f74b  movzx   ebx, al
0x18005f74e  shl     rbx, 4
0x18005f752  add     rcx, rbx; lpSystemTimeAsFileTime
0x18005f755  call    cs:__imp_GetSystemTimeAsFileTime
0x18005f75b  mov     rax, cs:qword_180269EA8
0x18005f762  mov     [rbx+rax+8], esi
0x18005f766  call    cs:__imp_RtlGetLastNtStatus
0x18005f76c  mov     rcx, cs:qword_180269EA8
0x18005f773  mov     [rbx+rcx+0Ch], eax
0x18005f777  jmp     loc_18005F60B
0x18005f77c  test    rdi, rdi
0x18005f77f  jz      loc_18005F664
0x18005f785  mov     rcx, rdi
0x18005f788  mov     rax, [rdi]
0x18005f78b  mov     edx, 1
0x18005f790  mov     rax, [rax]
0x18005f793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f798  jmp     loc_18005F664
0x18005f79d  mov     edx, 0Ch
0x18005f7a2  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f7a9  mov     ecx, 409h
0x18005f7ae  mov     r9d, ebp
0x18005f7b1  call    WPP_SF_d
0x18005f7b6  jmp     loc_18005F671
0x18005f7bb  test    byte ptr cs:xmmword_180266B60+1, 20h
0x18005f7c2  jnz     loc_18005F90F
0x18005f7c8  mov     ecx, 1
0x18005f7cd  call    InternetCreateThreadInfo
0x18005f7d2  mov     rbx, rax
0x18005f7d5  test    rax, rax
0x18005f7d8  jnz     loc_18005F488
0x18005f7de  test    byte ptr cs:xmmword_180266B60+1, 20h
0x18005f7e5  jz      loc_18005F488
0x18005f7eb  lea     edx, [rax+17h]
0x18005f7ee  mov     ecx, 40Dh
0x18005f7f3  lea     r8, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids
0x18005f7fa  call    WPP_SF_
0x18005f7ff  jmp     loc_18005F488
0x18005f804  test    byte ptr cs:xmmword_180266B60+1, 20h
0x18005f80b  jnz     loc_18005F933
0x18005f811  mov     ecx, 1
0x18005f816  call    InternetCreateThreadInfo
0x18005f81b  mov     rbx, rax
0x18005f81e  test    rax, rax
0x18005f821  jnz     loc_18005F623
0x18005f827  test    byte ptr cs:xmmword_180266B60+1, 20h
0x18005f82e  jz      loc_18005F623
0x18005f834  lea     edx, [rax+17h]
0x18005f837  mov     ecx, 40Dh
0x18005f83c  lea     r8, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids
0x18005f843  call    WPP_SF_
0x18005f848  jmp     loc_18005F623
0x18005f84d  mov     edx, 0Bh
0x18005f852  mov     [rsp+0C8h+var_A8], rax
0x18005f857  mov     ecx, 409h
0x18005f85c  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f863  mov     r9, rdi
0x18005f866  call    WPP_SF_qs
0x18005f86b  jmp     loc_18005F5F1
0x18005f870  mov     r9, [rdi+20h]
0x18005f874  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f87b  mov     edx, 12h
0x18005f880  mov     ecx, 409h
0x18005f885  call    WPP_SF_q
0x18005f88a  test    byte ptr cs:xmmword_180266B60+1, bl
0x18005f890  jz      loc_18005F4F4
0x18005f896  call    cs:__imp_GetCurrentThreadId
0x18005f89c  mov     edx, 13h
0x18005f8a1  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f8a8  mov     ecx, 409h
0x18005f8ad  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18005f8b1  mov     r9, rdi
0x18005f8b4  call    WPP_SF_qD
0x18005f8b9  test    byte ptr cs:xmmword_180266B60+1, bl
0x18005f8bf  jz      loc_18005F4F4
0x18005f8c5  mov     edx, 14h
0x18005f8ca  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f8d1  mov     ecx, 409h
0x18005f8d6  call    WPP_SF_
0x18005f8db  jmp     loc_18005F4F4
0x18005f8e0  lea     rax, qword_180222338
0x18005f8e7  mov     edx, 11h
0x18005f8ec  mov     [rsp+0C8h+var_A0], rax
0x18005f8f1  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f8f8  mov     ecx, 409h
0x18005f8fd  mov     [rsp+0C8h+var_A8], rax
0x18005f902  mov     r9, rdi
  ... truncated ...
```

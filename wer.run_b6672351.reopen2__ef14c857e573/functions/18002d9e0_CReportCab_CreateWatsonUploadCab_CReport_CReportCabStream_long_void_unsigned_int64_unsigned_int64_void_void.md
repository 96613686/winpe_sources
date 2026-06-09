# CReportCab::CreateWatsonUploadCab(CReport *,CReportCabStream *,long (*)(void *,unsigned __int64,unsigned __int64),void *,void *)

- ea: `0x18002d9e0`
- end: `0x18002dc46`
- name: `?CreateWatsonUploadCab@CReportCab@@QEAAJPEAVCReport@@PEAVCReportCabStream@@P6AJPEAX_K3@Z22@Z`
- size: `614`
- prototype: `__int64 __usercall@<rax>(CReportCab *__hidden this@<rcx>, struct CReport *@<rdx>, struct CReportCabStream *@<r8>, int (*)(void *, unsigned __int64, unsigned __int64)@<r9>, void *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003cef0`

## callees

- `0x180004c64`
- `0x180020680`
- `0x1800268fc`
- `0x18002d9e0`
- `0x18002f680`
- `0x18004570c`
- `0x1800a22bc`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dab3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dad4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dab3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dad4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002da31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002da4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002dc18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002da31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002da4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002dc18`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002da61`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002dc2a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002da61`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002dc2a`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18002da40`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18002da40`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002da82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002da82`

## pseudocode

```c
__int64 __fastcall CReportCab::CreateWatsonUploadCab(
        CReportCab *this,
        struct CReport *a2,
        struct CReportCabStream *a3,
        int (*a4)(void *, unsigned __int64, unsigned __int64),
        void *a5,
        HANDLE hHandle)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r15d
  HANDLE v12; // rax
  int v13; // edi
  _QWORD *v14; // rbx
  CZipArchiveFile *v15; // rax
  CZipArchiveFile *v16; // rax
  CCabArchiveFile *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // r9d
  unsigned int v22; // r8d
  __int64 v23; // rdx
  HANDLE v24; // rax

  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids);
    return 2147942487LL;
  }
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  v12 = GetCurrentThread();
  SetThreadPriority(v12, -1);
  if ( hHandle )
  {
    *(_QWORD *)this = hHandle;
    if ( !WaitForSingleObject(hHandle, 0) )
    {
      v13 = -2145681407;
      v14 = (_QWORD *)((char *)this + 40);
      goto LABEL_34;
    }
  }
  if ( *((_DWORD *)a3 + 4) )
  {
    v15 = (CZipArchiveFile *)HeapAlloc(g_hWerheap, 0, 0x58u);
    if ( v15 )
    {
      v16 = CZipArchiveFile::CZipArchiveFile(v15);
      goto LABEL_15;
    }
  }
  else
  {
    v17 = (CCabArchiveFile *)HeapAlloc(g_hWerheap, 0, 0x3B0u);
    if ( v17 )
    {
      v16 = CCabArchiveFile::CCabArchiveFile(v17);
      goto LABEL_15;
    }
  }
  v16 = 0;
LABEL_15:
  v14 = (_QWORD *)((char *)this + 40);
  v18 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v16;
  if ( v18 )
    utl::default_delete<ITpCommand>::operator()();
  if ( *v14 )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD, struct CReportCabStream *, __int64 (__fastcall *)(CReportManager *__hidden, unsigned __int64, unsigned __int64), void *, HANDLE))(*(_QWORD *)*v14 + 8LL))(
            *v14,
            a3,
            CReportManager::CabCompressCallback,
            a5,
            hHandle);
    if ( v13 >= 0 )
    {
      v21 = 0;
      v22 = 0x10000;
      if ( *((_DWORD *)a2 + 12947) == 3 )
      {
        v21 = 0x1000000;
        v22 = 327680;
      }
      v13 = CReportCab::AddReportFilesToCab(this, a2, v22, v21);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 40LL))(*v14);
        if ( v13 >= 0 )
          goto LABEL_34;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_34;
        v20 = 26;
      }
      else
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_34;
        v20 = 25;
      }
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_34;
      v20 = 24;
    }
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, (unsigned int)v13);
  }
  else
  {
    v13 = -2147024882;
  }
LABEL_34:
  v23 = *v14;
  *v14 = 0;
  if ( v23 )
    utl::default_delete<ITpCommand>::operator()();
  v24 = GetCurrentThread();
  SetThreadPriority(v24, ThreadPriority);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002d9e0  push    rbx
0x18002d9e2  push    rbp
0x18002d9e3  push    rsi
0x18002d9e4  push    rdi
0x18002d9e5  push    r14
0x18002d9e7  push    r15
0x18002d9e9  sub     rsp, 38h
0x18002d9ed  mov     r14, r8
0x18002d9f0  mov     rbp, rdx
0x18002d9f3  mov     rsi, rcx
0x18002d9f6  test    rdx, rdx
0x18002d9f9  jnz     short loc_18002DA31
0x18002d9fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da02  lea     rax, WPP_GLOBAL_Control
0x18002da09  cmp     rcx, rax
0x18002da0c  jz      short loc_18002DA27
0x18002da0e  test    byte ptr [rcx+1Ch], 1
0x18002da12  jz      short loc_18002DA27
0x18002da14  mov     rcx, [rcx+10h]
0x18002da18  lea     edx, [rbp+17h]
0x18002da1b  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18002da22  call    WPP_SF_
0x18002da27  mov     eax, 80070057h
0x18002da2c  jmp     loc_18002DC38
0x18002da31  call    cs:__imp_GetCurrentThread
0x18002da38  nop     dword ptr [rax+rax+00h]
0x18002da3d  mov     rcx, rax; hThread
0x18002da40  call    cs:__imp_GetThreadPriority
0x18002da47  nop     dword ptr [rax+rax+00h]
0x18002da4c  mov     r15d, eax
0x18002da4f  call    cs:__imp_GetCurrentThread
0x18002da56  nop     dword ptr [rax+rax+00h]
0x18002da5b  mov     rcx, rax; hThread
0x18002da5e  or      edx, 0FFFFFFFFh; nPriority
0x18002da61  call    cs:__imp_SetThreadPriority
0x18002da68  nop     dword ptr [rax+rax+00h]
0x18002da6d  mov     rdi, [rsp+68h+hHandle]
0x18002da75  test    rdi, rdi
0x18002da78  jz      short loc_18002DAA0
0x18002da7a  xor     edx, edx; dwMilliseconds
0x18002da7c  mov     [rsi], rdi
0x18002da7f  mov     rcx, rdi; hHandle
0x18002da82  call    cs:__imp_WaitForSingleObject
0x18002da89  nop     dword ptr [rax+rax+00h]
0x18002da8e  test    eax, eax
0x18002da90  jnz     short loc_18002DAA0
0x18002da92  mov     edi, 801B8001h
0x18002da97  lea     rbx, [rsi+28h]
0x18002da9b  jmp     loc_18002DC04
0x18002daa0  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002daa7  xor     edx, edx; dwFlags
0x18002daa9  cmp     [r14+10h], edx
0x18002daad  jz      short loc_18002DACE
0x18002daaf  lea     r8d, [rdx+58h]; dwBytes
0x18002dab3  call    cs:__imp_HeapAlloc
0x18002daba  nop     dword ptr [rax+rax+00h]
0x18002dabf  test    rax, rax
0x18002dac2  jz      short loc_18002DAEF
0x18002dac4  mov     rcx, rax; this
0x18002dac7  call    ??0CZipArchiveFile@@QEAA@XZ; CZipArchiveFile::CZipArchiveFile(void)
0x18002dacc  jmp     short loc_18002DAF1
0x18002dace  mov     r8d, 3B0h; dwBytes
0x18002dad4  call    cs:__imp_HeapAlloc
0x18002dadb  nop     dword ptr [rax+rax+00h]
0x18002dae0  test    rax, rax
0x18002dae3  jz      short loc_18002DAEF
0x18002dae5  mov     rcx, rax; this
0x18002dae8  call    ??0CCabArchiveFile@@QEAA@XZ; CCabArchiveFile::CCabArchiveFile(void)
0x18002daed  jmp     short loc_18002DAF1
0x18002daef  xor     eax, eax
0x18002daf1  lea     rbx, [rsi+28h]
0x18002daf5  mov     rdx, [rbx]
0x18002daf8  mov     [rbx], rax
0x18002dafb  test    rdx, rdx
0x18002dafe  jz      short loc_18002DB05
0x18002db00  call    ??R?$default_delete@VITpCommand@@@utl@@QEBAXPEAVITpCommand@@@Z; utl::default_delete<ITpCommand>::operator()(ITpCommand *)
0x18002db05  mov     rcx, [rbx]
0x18002db08  test    rcx, rcx
0x18002db0b  jnz     short loc_18002DB17
0x18002db0d  mov     edi, 8007000Eh
0x18002db12  jmp     loc_18002DC04
0x18002db17  mov     rax, [rcx]
0x18002db1a  lea     r8, ?CabCompressCallback@CReportManager@@AEAAJ_K0@Z; CReportManager::CabCompressCallback(unsigned __int64,unsigned __int64)
0x18002db21  mov     r9, [rsp+68h+arg_20]
0x18002db29  mov     rdx, r14
0x18002db2c  mov     [rsp+68h+var_48], rdi
0x18002db31  mov     rax, [rax+8]
0x18002db35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db3a  mov     edi, eax
0x18002db3c  test    eax, eax
0x18002db3e  jns     short loc_18002DB6B
0x18002db40  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db47  lea     rax, WPP_GLOBAL_Control
0x18002db4e  cmp     rcx, rax
0x18002db51  jz      loc_18002DC04
0x18002db57  test    byte ptr [rcx+1Ch], 1
0x18002db5b  jz      loc_18002DC04
0x18002db61  mov     edx, 18h
0x18002db66  jmp     loc_18002DBF1
0x18002db6b  xor     r9d, r9d
0x18002db6e  mov     ecx, 1000000h
0x18002db73  cmp     dword ptr [rbp+0CA4Ch], 3
0x18002db7a  mov     r8d, 10000h
0x18002db80  mov     rdx, rbp; struct CReport *
0x18002db83  cmovz   r9d, ecx; unsigned int
0x18002db87  mov     ecx, 50000h
0x18002db8c  cmovz   r8d, ecx; unsigned int
0x18002db90  mov     rcx, rsi; this
0x18002db93  call    ?AddReportFilesToCab@CReportCab@@IEAAJPEAVCReport@@KK@Z; CReportCab::AddReportFilesToCab(CReport *,ulong,ulong)
0x18002db98  mov     edi, eax
0x18002db9a  test    eax, eax
0x18002db9c  jns     short loc_18002DBBE
0x18002db9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dba5  lea     rax, WPP_GLOBAL_Control
0x18002dbac  cmp     rcx, rax
0x18002dbaf  jz      short loc_18002DC04
0x18002dbb1  test    byte ptr [rcx+1Ch], 1
0x18002dbb5  jz      short loc_18002DC04
0x18002dbb7  mov     edx, 19h
0x18002dbbc  jmp     short loc_18002DBF1
0x18002dbbe  mov     rcx, [rbx]
0x18002dbc1  mov     rax, [rcx]
0x18002dbc4  mov     rax, [rax+28h]
0x18002dbc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbcd  mov     edi, eax
0x18002dbcf  test    eax, eax
0x18002dbd1  jns     short loc_18002DC04
0x18002dbd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbda  lea     rax, WPP_GLOBAL_Control
0x18002dbe1  cmp     rcx, rax
0x18002dbe4  jz      short loc_18002DC04
0x18002dbe6  test    byte ptr [rcx+1Ch], 1
0x18002dbea  jz      short loc_18002DC04
0x18002dbec  mov     edx, 1Ah
0x18002dbf1  mov     rcx, [rcx+10h]
0x18002dbf5  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18002dbfc  mov     r9d, edi
0x18002dbff  call    WPP_SF_d
0x18002dc04  mov     rdx, [rbx]
0x18002dc07  mov     qword ptr [rbx], 0
0x18002dc0e  test    rdx, rdx
0x18002dc11  jz      short loc_18002DC18
0x18002dc13  call    ??R?$default_delete@VITpCommand@@@utl@@QEBAXPEAVITpCommand@@@Z; utl::default_delete<ITpCommand>::operator()(ITpCommand *)
0x18002dc18  call    cs:__imp_GetCurrentThread
0x18002dc1f  nop     dword ptr [rax+rax+00h]
0x18002dc24  mov     rcx, rax; hThread
0x18002dc27  mov     edx, r15d; nPriority
0x18002dc2a  call    cs:__imp_SetThreadPriority
0x18002dc31  nop     dword ptr [rax+rax+00h]
0x18002dc36  mov     eax, edi
0x18002dc38  add     rsp, 38h
0x18002dc3c  pop     r15
0x18002dc3e  pop     r14
0x18002dc40  pop     rdi
0x18002dc41  pop     rsi
0x18002dc42  pop     rbp
0x18002dc43  pop     rbx
0x18002dc44  retn
```

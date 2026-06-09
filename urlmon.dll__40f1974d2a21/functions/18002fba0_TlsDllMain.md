# TlsDllMain

- ea: `0x18002fba0`
- end: `0x18002ffb9`
- name: `TlsDllMain`
- size: `1049`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f690`

## callees

- `0x1800150e0`
- `0x18002dcd8`
- `0x18002fba0`
- `0x180030278`
- `0x1800302c4`
- `0x18003030c`
- `0x18003064c`
- `0x180030eec`
- `0x18005d4dc`
- `0x18005d864`
- `0x18006ca70`
- `0x180081800`
- `0x180082fe0`
- `0x1800bbfc0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fc26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fc26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fbfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fc91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fbfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fc91`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002fcd9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002fcd9`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18002fe06`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18002fe06`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18002fd75`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18002fd75`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002fbed`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002fbed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002fbd2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002fd8c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002fbd2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002fd8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fd5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fd5f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002fdec`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002fdec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fe68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fed0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fe68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fed0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff8b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!UnregisterClassW` at `0x18002feaa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!UnregisterClassW` at `0x18002feaa`
- `WININET!InternetCloseHandle` at `0x18002fe8a`
- `WININET!InternetCloseHandle` at `0x18002fe8a`

## pseudocode

```c
__int64 __fastcall TlsDllMain(HINSTANCE a1, int a2, __int64 a3)
{
  int v4; // edx
  char *v6; // rbx
  _QWORD *v7; // rdx
  void *v8; // rdi
  __int64 v9; // rax
  char *v10; // rdi
  char *v11; // rdi
  void *v12; // rdi
  __int64 v13; // rcx
  NotificationWindow **v14; // rdi
  NotificationWindow *v15; // rsi
  char *v16; // rax
  NotificationWindow *v17; // rsi
  CMediaTypeHolder *v18; // rbp
  DWORD v19; // eax
  CMediaTypeHolder *v20; // rax
  unsigned int v21; // ecx
  CMediaTypeHolder *v22; // rbx
  void *v23; // rcx
  _QWORD *v24; // rsi
  int v25; // edi
  void *v26; // rdi
  CPlex *v27; // rcx
  int v28; // r14d
  LPVOID Value; // [rsp+58h] [rbp+20h] BYREF

  if ( !a2 )
  {
    CleanupAllThreadsOnProcessDetach(a3 != 0);
    InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
    if ( !byte_18015DE34 || !a3 )
    {
      if ( dword_18015E73C == 1 )
        dword_18015E73C = !UnregisterClassW(L"URL Moniker Notification Window", g_hInst);
      if ( !a3 )
      {
        v22 = g_pCMHolder;
        if ( g_pCMHolder )
        {
          CMediaTypeHolder::~CMediaTypeHolder(g_pCMHolder);
          CoTaskMemFree(v22);
          g_pCMHolder = 0;
        }
        DeleteOInetSession(v21);
        if ( g_hSession )
        {
          InternetCloseHandle(g_hSession);
          g_hSession = 0;
        }
      }
    }
    TlsFree(gTlsIndex);
    return 1;
  }
  v4 = a2 - 1;
  if ( !v4 )
  {
    v18 = 0;
    g_hInst = a1;
    g_hHeap = GetProcessHeap();
    if ( !g_hHeap )
      return 0;
    v19 = TlsAlloc();
    gTlsIndex = v19;
    if ( v19 == -1 )
      return 0;
    Value = TlsGetValue(v19);
    if ( !Value && (int)CUrlMkTls::TLSAllocData((CUrlMkTls *)&Value) < 0 )
      return 0;
    v20 = (CMediaTypeHolder *)operator new(0x18u);
    if ( v20 )
      v18 = CMediaTypeHolder::CMediaTypeHolder(v20);
    g_pCMHolder = v18;
    return 1;
  }
  if ( v4 != 2 )
    return 1;
  v6 = (char *)TlsGetValue(gTlsIndex);
  if ( !v6 )
    return 1;
  TlsSetValue(gTlsIndex, 0);
  EnterCriticalSection(&stru_18015C010);
  v7 = (_QWORD *)qword_18015DDF0;
  if ( qword_18015DDF0 )
  {
    while ( 1 )
    {
      v7 = (_QWORD *)*v7;
      if ( !v7 )
        break;
      if ( (char *)v7[2] == v6 )
      {
        CList<tagSUrlMkTlsData *,tagSUrlMkTlsData *>::RemoveAt();
        break;
      }
    }
  }
  LeaveCriticalSection(&stru_18015C010);
  *((_DWORD *)v6 + 1) |= 4u;
  v8 = (void *)*((_QWORD *)v6 + 2);
  if ( v8 )
  {
    CList<CClBinding *,CClBinding *>::RemoveAll(*((_QWORD *)v6 + 2));
    CoTaskMemFree(v8);
    *((_QWORD *)v6 + 2) = 0;
  }
  v9 = *((_QWORD *)v6 + 6);
  if ( v9 )
  {
    v24 = *(_QWORD **)v9;
    v25 = 0;
    v28 = *(_DWORD *)(v9 + 16);
    if ( v28 > 0 )
    {
      do
      {
        v23 = (void *)v24[2];
        v24 = (_QWORD *)*v24;
        if ( v23 )
          CoTaskMemFree(v23);
        ++v25;
      }
      while ( v25 < v28 );
    }
    v26 = (void *)*((_QWORD *)v6 + 6);
    if ( v26 )
    {
      v27 = (CPlex *)*((_QWORD *)v26 + 4);
      *((_DWORD *)v26 + 4) = 0;
      *((_QWORD *)v26 + 3) = 0;
      *((_QWORD *)v26 + 1) = 0;
      *(_QWORD *)v26 = 0;
      CPlex::FreeDataChain(v27);
      *((_QWORD *)v26 + 4) = 0;
      CoTaskMemFree(v26);
    }
    *((_QWORD *)v6 + 6) = 0;
  }
  v10 = (char *)*((_QWORD *)v6 + 4);
  if ( v10 )
  {
    CList<CClBinding *,CClBinding *>::RemoveAll(v10 + 8);
    CoTaskMemFree(v10);
    *((_QWORD *)v6 + 4) = 0;
  }
  v11 = (char *)*((_QWORD *)v6 + 3);
  if ( v11 )
  {
    CList<CClBinding *,CClBinding *>::RemoveAll(v11 + 8);
    CoTaskMemFree(v11);
    *((_QWORD *)v6 + 3) = 0;
  }
  v12 = (void *)*((_QWORD *)v6 + 5);
  if ( v12 )
  {
    CCDLPacketMgr::~CCDLPacketMgr(*((CCDLPacketMgr **)v6 + 5));
    CoTaskMemFree(v12);
    *((_QWORD *)v6 + 5) = 0;
  }
  v13 = *((_QWORD *)v6 + 7);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)v6 + 7) = 0;
  }
  Value = 0;
  EnterCriticalSection(&stru_18015C010);
  v14 = (NotificationWindow **)(v6 + 552);
  if ( *((_QWORD *)v6 + 69) )
  {
    Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(&Value);
    v15 = *v14;
    if ( *v14 )
      goto LABEL_28;
    v16 = (char *)operator new(0x40u);
    v15 = (NotificationWindow *)v16;
    if ( v16 )
    {
      *(_DWORD *)v16 = 1;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v16 + 24));
      *((_QWORD *)v15 + 2) = 0;
      *((_QWORD *)v15 + 1) = 0;
    }
    else
    {
      v15 = 0;
    }
    if ( *v14 )
      NotificationWindow::Release(*v14);
    *v14 = v15;
    if ( v15 )
LABEL_28:
      _InterlockedIncrement((volatile signed __int32 *)v15);
    v17 = *v14;
    Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(v6 + 552);
    LeaveCriticalSection(&stru_18015C010);
    if ( v17 )
    {
      NotificationWindow::Shutdown(v17, 1);
      NotificationWindow::Release(v17);
    }
  }
  else
  {
    LeaveCriticalSection(&stru_18015C010);
  }
  HeapFree(g_hHeap, 0, v6);
  return 1;
}

```

## disassembly

```asm
0x18002fba0  push    rbx
0x18002fba2  push    rbp
0x18002fba3  sub     rsp, 28h
0x18002fba7  mov     rbx, r8
0x18002fbaa  test    edx, edx
0x18002fbac  jz      loc_18002FDCD
0x18002fbb2  sub     edx, 1
0x18002fbb5  jz      loc_18002FD56
0x18002fbbb  cmp     edx, 2
0x18002fbbe  jz      short loc_18002FBCC
0x18002fbc0  mov     eax, 1
0x18002fbc5  add     rsp, 28h
0x18002fbc9  pop     rbp
0x18002fbca  pop     rbx
0x18002fbcb  retn
0x18002fbcc  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x18002fbd2  call    cs:__imp_TlsGetValue
0x18002fbd8  mov     rbx, rax
0x18002fbdb  test    rax, rax
0x18002fbde  jz      short loc_18002FBC0
0x18002fbe0  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x18002fbe6  xor     edx, edx; lpTlsValue
0x18002fbe8  mov     [rsp+38h+arg_8], rdi
0x18002fbed  call    cs:__imp_TlsSetValue
0x18002fbf3  lea     rcx, stru_18015C010; lpCriticalSection
0x18002fbfa  call    cs:__imp_EnterCriticalSection
0x18002fc00  mov     rdx, cs:qword_18015DDF0
0x18002fc07  test    rdx, rdx
0x18002fc0a  jz      short loc_18002FC1F
0x18002fc0c  mov     rdx, [rdx]
0x18002fc0f  test    rdx, rdx
0x18002fc12  jz      short loc_18002FC1F
0x18002fc14  cmp     [rdx+10h], rbx
0x18002fc18  jnz     short loc_18002FC0C
0x18002fc1a  call    ?RemoveAt@?$CList@PEAUtagSUrlMkTlsData@@PEAU1@@@QEAAXPEAX@Z; CList<tagSUrlMkTlsData *,tagSUrlMkTlsData *>::RemoveAt(void *)
0x18002fc1f  lea     rcx, stru_18015C010; lpCriticalSection
0x18002fc26  call    cs:__imp_LeaveCriticalSection
0x18002fc2c  or      dword ptr [rbx+4], 4
0x18002fc30  xor     ebp, ebp
0x18002fc32  mov     rdi, [rbx+10h]
0x18002fc36  test    rdi, rdi
0x18002fc39  jnz     loc_18002FF18
0x18002fc3f  mov     rax, [rbx+30h]
0x18002fc43  mov     [rsp+38h+arg_0], rsi
0x18002fc48  test    rax, rax
0x18002fc4b  jnz     loc_18002FF32
0x18002fc51  mov     rdi, [rbx+20h]
0x18002fc55  test    rdi, rdi
0x18002fc58  jnz     loc_18002FF4A
0x18002fc5e  mov     rdi, [rbx+18h]
0x18002fc62  test    rdi, rdi
0x18002fc65  jnz     loc_18002FF65
0x18002fc6b  mov     rdi, [rbx+28h]
0x18002fc6f  test    rdi, rdi
0x18002fc72  jnz     loc_18002FF80
0x18002fc78  mov     rcx, [rbx+38h]
0x18002fc7c  test    rcx, rcx
0x18002fc7f  jnz     loc_18002FF9A
0x18002fc85  lea     rcx, stru_18015C010; lpCriticalSection
0x18002fc8c  mov     [rsp+38h+arg_18], rbp
0x18002fc91  call    cs:__imp_EnterCriticalSection
0x18002fc97  lea     rdi, [rbx+228h]
0x18002fc9e  cmp     [rdi], rbp
0x18002fca1  jz      loc_18002FD47
0x18002fca7  lea     rcx, [rsp+38h+arg_18]
0x18002fcac  call    ?InternalRelease@?$ComPtr@VNotificationWindow@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(void)
0x18002fcb1  mov     rsi, [rdi]
0x18002fcb4  test    rsi, rsi
0x18002fcb7  jnz     short loc_18002FCFB
0x18002fcb9  mov     ecx, 40h ; '@'; Size
0x18002fcbe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fcc3  mov     rsi, rax
0x18002fcc6  test    rax, rax
0x18002fcc9  jz      loc_18002FEBC
0x18002fccf  lea     rcx, [rax+18h]; lpCriticalSection
0x18002fcd3  mov     dword ptr [rax], 1
0x18002fcd9  call    cs:__imp_InitializeCriticalSection
0x18002fcdf  mov     [rsi+10h], rbp
0x18002fce3  mov     [rsi+8], rbp
0x18002fce7  mov     rcx, [rdi]; this
0x18002fcea  test    rcx, rcx
0x18002fced  jnz     loc_18002FFAF
0x18002fcf3  mov     [rdi], rsi
0x18002fcf6  test    rsi, rsi
0x18002fcf9  jz      short loc_18002FCFE
0x18002fcfb  lock inc dword ptr [rsi]
0x18002fcfe  mov     rsi, [rdi]
0x18002fd01  mov     rcx, rdi
0x18002fd04  call    ?InternalRelease@?$ComPtr@VNotificationWindow@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(void)
0x18002fd09  lea     rcx, stru_18015C010; lpCriticalSection
0x18002fd10  call    cs:__imp_LeaveCriticalSection
0x18002fd16  test    rsi, rsi
0x18002fd19  jnz     loc_18002FE11
0x18002fd1f  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x18002fd26  mov     r8, rbx; lpMem
0x18002fd29  xor     edx, edx; dwFlags
0x18002fd2b  call    cs:__imp_HeapFree
0x18002fd31  mov     rdi, [rsp+38h+arg_8]
0x18002fd36  mov     eax, 1
0x18002fd3b  mov     rsi, [rsp+38h+arg_0]
0x18002fd40  add     rsp, 28h
0x18002fd44  pop     rbp
0x18002fd45  pop     rbx
0x18002fd46  retn
0x18002fd47  lea     rcx, stru_18015C010; lpCriticalSection
0x18002fd4e  call    cs:__imp_LeaveCriticalSection
0x18002fd54  jmp     short loc_18002FD1F
0x18002fd56  xor     ebp, ebp
0x18002fd58  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInst
0x18002fd5f  call    cs:__imp_GetProcessHeap
0x18002fd65  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x18002fd6c  test    rax, rax
0x18002fd6f  jz      loc_18002FE3A
0x18002fd75  call    cs:__imp_TlsAlloc
0x18002fd7b  mov     cs:?gTlsIndex@@3KA, eax; ulong gTlsIndex
0x18002fd81  cmp     eax, 0FFFFFFFFh
0x18002fd84  jz      loc_18002FE3A
0x18002fd8a  mov     ecx, eax; dwTlsIndex
0x18002fd8c  call    cs:__imp_TlsGetValue
0x18002fd92  mov     [rsp+38h+arg_18], rax
0x18002fd97  test    rax, rax
0x18002fd9a  jz      loc_18002FE28
0x18002fda0  mov     ecx, 18h; Size
0x18002fda5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fdaa  test    rax, rax
0x18002fdad  jz      short loc_18002FDBA
0x18002fdaf  mov     rcx, rax; this
0x18002fdb2  call    ??0CMediaTypeHolder@@QEAA@XZ; CMediaTypeHolder::CMediaTypeHolder(void)
0x18002fdb7  mov     rbp, rax
0x18002fdba  mov     cs:?g_pCMHolder@@3PEAVCMediaTypeHolder@@EA, rbp; CMediaTypeHolder * g_pCMHolder
0x18002fdc1  mov     eax, 1
0x18002fdc6  add     rsp, 28h
0x18002fdca  pop     rbp
0x18002fdcb  pop     rbx
0x18002fdcc  retn
0x18002fdcd  test    rbx, rbx
0x18002fdd0  setnz   cl; bool
0x18002fdd3  call    ?CleanupAllThreadsOnProcessDetach@@YAX_N@Z; CleanupAllThreadsOnProcessDetach(bool)
0x18002fdd8  xor     r9d, r9d; Context
0x18002fddb  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002fde2  xor     r8d, r8d; Parameter
0x18002fde5  lea     rcx, stru_18015EA38; InitOnce
0x18002fdec  call    cs:__imp_InitOnceExecuteOnce
0x18002fdf2  cmp     cs:byte_18015DE34, 0
0x18002fdf9  jz      short loc_18002FE41
0x18002fdfb  test    rbx, rbx
0x18002fdfe  jz      short loc_18002FE41
0x18002fe00  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x18002fe06  call    cs:__imp_TlsFree
0x18002fe0c  jmp     loc_18002FBC0
0x18002fe11  mov     dl, 1; bool
0x18002fe13  mov     rcx, rsi; this
0x18002fe16  call    ?Shutdown@NotificationWindow@@QEAAX_N@Z; NotificationWindow::Shutdown(bool)
0x18002fe1b  mov     rcx, rsi; this
0x18002fe1e  call    ?Release@NotificationWindow@@QEAAKXZ; NotificationWindow::Release(void)
0x18002fe23  jmp     loc_18002FD1F
0x18002fe28  lea     rcx, [rsp+38h+arg_18]; this
0x18002fe2d  call    ?TLSAllocData@CUrlMkTls@@AEAAJXZ; CUrlMkTls::TLSAllocData(void)
0x18002fe32  test    eax, eax
0x18002fe34  jns     loc_18002FDA0
0x18002fe3a  mov     eax, ebp
0x18002fe3c  jmp     loc_18002FBC5
0x18002fe41  xor     ebp, ebp
0x18002fe43  cmp     cs:dword_18015E73C, 1
0x18002fe4a  jz      short loc_18002FE9C
0x18002fe4c  test    rbx, rbx
0x18002fe4f  jnz     short loc_18002FE00
0x18002fe51  mov     rbx, cs:?g_pCMHolder@@3PEAVCMediaTypeHolder@@EA; CMediaTypeHolder * g_pCMHolder
0x18002fe58  test    rbx, rbx
0x18002fe5b  jz      short loc_18002FE75
0x18002fe5d  mov     rcx, rbx; this
0x18002fe60  call    ??1CMediaTypeHolder@@QEAA@XZ; CMediaTypeHolder::~CMediaTypeHolder(void)
0x18002fe65  mov     rcx, rbx; pv
0x18002fe68  call    cs:__imp_CoTaskMemFree
0x18002fe6e  mov     cs:?g_pCMHolder@@3PEAVCMediaTypeHolder@@EA, rbp; CMediaTypeHolder * g_pCMHolder
0x18002fe75  call    ?DeleteOInetSession@@YAJK@Z; DeleteOInetSession(ulong)
0x18002fe7a  mov     rcx, cs:?g_hSession@@3PEAXEA; hInternet
0x18002fe81  test    rcx, rcx
0x18002fe84  jz      loc_18002FE00
0x18002fe8a  call    cs:__imp_InternetCloseHandle
0x18002fe90  mov     cs:?g_hSession@@3PEAXEA, rbp; void * g_hSession
0x18002fe97  jmp     loc_18002FE00
0x18002fe9c  mov     rdx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18002fea3  lea     rcx, ClassName; "URL Moniker Notification Window"
0x18002feaa  call    cs:__imp_UnregisterClassW
0x18002feb0  test    eax, eax
0x18002feb2  jz      short loc_18002FE4C
0x18002feb4  mov     cs:dword_18015E73C, ebp
0x18002feba  jmp     short loc_18002FE4C
0x18002febc  mov     rsi, rbp
0x18002febf  jmp     loc_18002FCE7
0x18002fec4  mov     rcx, [rsi+10h]; pv
0x18002fec8  mov     rsi, [rsi]
0x18002fecb  test    rcx, rcx
0x18002fece  jz      short loc_18002FED6
0x18002fed0  call    cs:__imp_CoTaskMemFree
0x18002fed6  inc     edi
0x18002fed8  cmp     edi, r14d
0x18002fedb  jl      short loc_18002FEC4
0x18002fedd  mov     rdi, [rbx+30h]
0x18002fee1  mov     r14, [rsp+38h+var_18]
0x18002fee6  test    rdi, rdi
0x18002fee9  jz      short loc_18002FF0F
0x18002feeb  mov     rcx, [rdi+20h]; this
0x18002feef  mov     [rdi+10h], ebp
0x18002fef2  mov     [rdi+18h], rbp
0x18002fef6  mov     [rdi+8], rbp
0x18002fefa  mov     [rdi], rbp
0x18002fefd  call    ?FreeDataChain@CPlex@@QEAAXXZ; CPlex::FreeDataChain(void)
0x18002ff02  mov     rcx, rdi; pv
0x18002ff05  mov     [rdi+20h], rbp
0x18002ff09  call    cs:__imp_CoTaskMemFree
0x18002ff0f  mov     [rbx+30h], rbp
0x18002ff13  jmp     loc_18002FC51
0x18002ff18  mov     rcx, rdi
0x18002ff1b  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x18002ff20  mov     rcx, rdi; pv
0x18002ff23  call    cs:__imp_CoTaskMemFree
0x18002ff29  mov     [rbx+10h], rbp
0x18002ff2d  jmp     loc_18002FC3F
0x18002ff32  mov     rsi, [rax]
0x18002ff35  mov     edi, ebp
0x18002ff37  mov     [rsp+38h+var_18], r14
0x18002ff3c  mov     r14d, [rax+10h]
0x18002ff40  test    r14d, r14d
0x18002ff43  jle     short loc_18002FEDD
0x18002ff45  jmp     loc_18002FEC4
0x18002ff4a  lea     rcx, [rdi+8]
0x18002ff4e  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x18002ff53  mov     rcx, rdi; pv
0x18002ff56  call    cs:__imp_CoTaskMemFree
0x18002ff5c  mov     [rbx+20h], rbp
0x18002ff60  jmp     loc_18002FC5E
0x18002ff65  lea     rcx, [rdi+8]
0x18002ff69  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x18002ff6e  mov     rcx, rdi; pv
0x18002ff71  call    cs:__imp_CoTaskMemFree
0x18002ff77  mov     [rbx+18h], rbp
0x18002ff7b  jmp     loc_18002FC6B
0x18002ff80  mov     rcx, rdi; this
0x18002ff83  call    ??1CCDLPacketMgr@@QEAA@XZ; CCDLPacketMgr::~CCDLPacketMgr(void)
0x18002ff88  mov     rcx, rdi; pv
0x18002ff8b  call    cs:__imp_CoTaskMemFree
0x18002ff91  mov     [rbx+28h], rbp
0x18002ff95  jmp     loc_18002FC78
0x18002ff9a  mov     rax, [rcx]
0x18002ff9d  mov     rax, [rax+10h]
0x18002ffa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffa6  mov     [rbx+38h], rbp
0x18002ffaa  jmp     loc_18002FC85
0x18002ffaf  call    ?Release@NotificationWindow@@QEAAKXZ; NotificationWindow::Release(void)
0x18002ffb4  jmp     loc_18002FCF3
```

# TlsDllMain

- ea: `0x180036010`
- end: `0x18003648c`
- name: `TlsDllMain`
- size: `1148`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180035af0`

## callees

- `0x18001db50`
- `0x180033fa4`
- `0x180036010`
- `0x1800367b4`
- `0x180036808`
- `0x180036854`
- `0x180036c08`
- `0x180036cd8`
- `0x180037828`
- `0x180037874`
- `0x180037c94`
- `0x180052494`
- `0x18005294c`
- `0x180086f20`
- `0x1800c4150`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800360a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800361a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800361f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800360a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800361a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800361f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036077`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003611a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036077`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003611a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180036168`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180036168`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800362c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800362c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180036223`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180036223`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180036064`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180036064`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180036043`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180036240`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180036043`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180036240`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800361c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800361c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036207`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036207`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800362a7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800362a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003632b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003637f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800363be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800363de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036417`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036458`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003632b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003637f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800363be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800363de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036417`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036458`
- `WININET!InternetCloseHandle` at `0x180036353`
- `WININET!InternetCloseHandle` at `0x180036353`

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
    InitOnceExecuteOnce(&stru_18016BB00, InitOnceDeviceFamily, 0, 0);
    if ( !byte_18016AF34 || !a3 )
    {
      UnregisterUrlMkWndClass();
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
  EnterCriticalSection(&stru_180169110);
  v7 = (_QWORD *)qword_18016AEF0;
  if ( qword_18016AEF0 )
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
  LeaveCriticalSection(&stru_180169110);
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
  EnterCriticalSection(&stru_180169110);
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
    LeaveCriticalSection(&stru_180169110);
    if ( v17 )
    {
      NotificationWindow::Shutdown(v17, 1);
      NotificationWindow::Release(v17);
    }
  }
  else
  {
    LeaveCriticalSection(&stru_180169110);
  }
  HeapFree(g_hHeap, 0, v6);
  return 1;
}

```

## disassembly

```asm
0x180036010  push    rbx
0x180036012  push    rbp
0x180036013  sub     rsp, 28h
0x180036017  mov     rbx, r8
0x18003601a  test    edx, edx
0x18003601c  jz      loc_180036288
0x180036022  sub     edx, 1
0x180036025  jz      loc_1800361FE
0x18003602b  cmp     edx, 2
0x18003602e  jz      short loc_18003603D
0x180036030  mov     eax, 1
0x180036035  add     rsp, 28h
0x180036039  pop     rbp
0x18003603a  pop     rbx
0x18003603b  retn
0x18003603d  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x180036043  call    cs:__imp_TlsGetValue
0x18003604a  nop     dword ptr [rax+rax+00h]
0x18003604f  mov     rbx, rax
0x180036052  test    rax, rax
0x180036055  jz      short loc_180036030
0x180036057  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x18003605d  xor     edx, edx; lpTlsValue
0x18003605f  mov     [rsp+38h+arg_8], rdi
0x180036064  call    cs:__imp_TlsSetValue
0x18003606b  nop     dword ptr [rax+rax+00h]
0x180036070  lea     rcx, stru_180169110; lpCriticalSection
0x180036077  call    cs:__imp_EnterCriticalSection
0x18003607e  nop     dword ptr [rax+rax+00h]
0x180036083  mov     rdx, cs:qword_18016AEF0
0x18003608a  test    rdx, rdx
0x18003608d  jz      short loc_1800360A2
0x18003608f  mov     rdx, [rdx]
0x180036092  test    rdx, rdx
0x180036095  jz      short loc_1800360A2
0x180036097  cmp     [rdx+10h], rbx
0x18003609b  jnz     short loc_18003608F
0x18003609d  call    ?RemoveAt@?$CList@PEAUtagSUrlMkTlsData@@PEAU1@@@QEAAXPEAX@Z; CList<tagSUrlMkTlsData *,tagSUrlMkTlsData *>::RemoveAt(void *)
0x1800360a2  lea     rcx, stru_180169110; lpCriticalSection
0x1800360a9  call    cs:__imp_LeaveCriticalSection
0x1800360b0  nop     dword ptr [rax+rax+00h]
0x1800360b5  or      dword ptr [rbx+4], 4
0x1800360b9  xor     ebp, ebp
0x1800360bb  mov     rdi, [rbx+10h]
0x1800360bf  test    rdi, rdi
0x1800360c2  jnz     loc_1800363D3
0x1800360c8  mov     rax, [rbx+30h]
0x1800360cc  mov     [rsp+38h+arg_0], rsi
0x1800360d1  test    rax, rax
0x1800360d4  jnz     loc_1800363F3
0x1800360da  mov     rdi, [rbx+20h]
0x1800360de  test    rdi, rdi
0x1800360e1  jnz     loc_18003640B
0x1800360e7  mov     rdi, [rbx+18h]
0x1800360eb  test    rdi, rdi
0x1800360ee  jnz     loc_18003642C
0x1800360f4  mov     rdi, [rbx+28h]
0x1800360f8  test    rdi, rdi
0x1800360fb  jnz     loc_18003644D
0x180036101  mov     rcx, [rbx+38h]
0x180036105  test    rcx, rcx
0x180036108  jnz     loc_18003646D
0x18003610e  lea     rcx, stru_180169110; lpCriticalSection
0x180036115  mov     [rsp+38h+arg_18], rbp
0x18003611a  call    cs:__imp_EnterCriticalSection
0x180036121  nop     dword ptr [rax+rax+00h]
0x180036126  lea     rdi, [rbx+228h]
0x18003612d  cmp     [rdi], rbp
0x180036130  jz      loc_1800361E9
0x180036136  lea     rcx, [rsp+38h+arg_18]
0x18003613b  call    ?InternalRelease@?$ComPtr@VNotificationWindow@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(void)
0x180036140  mov     rsi, [rdi]
0x180036143  test    rsi, rsi
0x180036146  jnz     short loc_180036190
0x180036148  mov     ecx, 40h ; '@'; Size
0x18003614d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036152  mov     rsi, rax
0x180036155  test    rax, rax
0x180036158  jz      loc_18003636B
0x18003615e  lea     rcx, [rax+18h]; lpCriticalSection
0x180036162  mov     dword ptr [rax], 1
0x180036168  call    cs:__imp_InitializeCriticalSection
0x18003616f  nop     dword ptr [rax+rax+00h]
0x180036174  mov     [rsi+10h], rbp
0x180036178  mov     [rsi+8], rbp
0x18003617c  mov     rcx, [rdi]; this
0x18003617f  test    rcx, rcx
0x180036182  jnz     loc_180036482
0x180036188  mov     [rdi], rsi
0x18003618b  test    rsi, rsi
0x18003618e  jz      short loc_180036193
0x180036190  lock inc dword ptr [rsi]
0x180036193  mov     rsi, [rdi]
0x180036196  mov     rcx, rdi
0x180036199  call    ?InternalRelease@?$ComPtr@VNotificationWindow@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(void)
0x18003619e  lea     rcx, stru_180169110; lpCriticalSection
0x1800361a5  call    cs:__imp_LeaveCriticalSection
0x1800361ac  nop     dword ptr [rax+rax+00h]
0x1800361b1  test    rsi, rsi
0x1800361b4  jnz     loc_1800362D8
0x1800361ba  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1800361c1  mov     r8, rbx; lpMem
0x1800361c4  xor     edx, edx; dwFlags
0x1800361c6  call    cs:__imp_HeapFree
0x1800361cd  nop     dword ptr [rax+rax+00h]
0x1800361d2  mov     rdi, [rsp+38h+arg_8]
0x1800361d7  mov     eax, 1
0x1800361dc  mov     rsi, [rsp+38h+arg_0]
0x1800361e1  add     rsp, 28h
0x1800361e5  pop     rbp
0x1800361e6  pop     rbx
0x1800361e7  retn
0x1800361e9  lea     rcx, stru_180169110; lpCriticalSection
0x1800361f0  call    cs:__imp_LeaveCriticalSection
0x1800361f7  nop     dword ptr [rax+rax+00h]
0x1800361fc  jmp     short loc_1800361BA
0x1800361fe  xor     ebp, ebp
0x180036200  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInst
0x180036207  call    cs:__imp_GetProcessHeap
0x18003620e  nop     dword ptr [rax+rax+00h]
0x180036213  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x18003621a  test    rax, rax
0x18003621d  jz      loc_180036301
0x180036223  call    cs:__imp_TlsAlloc
0x18003622a  nop     dword ptr [rax+rax+00h]
0x18003622f  mov     cs:?gTlsIndex@@3KA, eax; ulong gTlsIndex
0x180036235  cmp     eax, 0FFFFFFFFh
0x180036238  jz      loc_180036301
0x18003623e  mov     ecx, eax; dwTlsIndex
0x180036240  call    cs:__imp_TlsGetValue
0x180036247  nop     dword ptr [rax+rax+00h]
0x18003624c  mov     [rsp+38h+arg_18], rax
0x180036251  test    rax, rax
0x180036254  jz      loc_1800362EF
0x18003625a  mov     ecx, 18h; Size
0x18003625f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036264  test    rax, rax
0x180036267  jz      short loc_180036274
0x180036269  mov     rcx, rax; this
0x18003626c  call    ??0CMediaTypeHolder@@QEAA@XZ; CMediaTypeHolder::CMediaTypeHolder(void)
0x180036271  mov     rbp, rax
0x180036274  mov     cs:?g_pCMHolder@@3PEAVCMediaTypeHolder@@EA, rbp; CMediaTypeHolder * g_pCMHolder
0x18003627b  mov     eax, 1
0x180036280  add     rsp, 28h
0x180036284  pop     rbp
0x180036285  pop     rbx
0x180036286  retn
0x180036288  test    rbx, rbx
0x18003628b  setnz   cl; bool
0x18003628e  call    ?CleanupAllThreadsOnProcessDetach@@YAX_N@Z; CleanupAllThreadsOnProcessDetach(bool)
0x180036293  xor     r9d, r9d; Context
0x180036296  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18003629d  xor     r8d, r8d; Parameter
0x1800362a0  lea     rcx, stru_18016BB00; InitOnce
0x1800362a7  call    cs:__imp_InitOnceExecuteOnce
0x1800362ae  nop     dword ptr [rax+rax+00h]
0x1800362b3  cmp     cs:byte_18016AF34, 0
0x1800362ba  jz      short loc_180036308
0x1800362bc  test    rbx, rbx
0x1800362bf  jz      short loc_180036308
0x1800362c1  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x1800362c7  call    cs:__imp_TlsFree
0x1800362ce  nop     dword ptr [rax+rax+00h]
0x1800362d3  jmp     loc_180036030
0x1800362d8  mov     dl, 1; bool
0x1800362da  mov     rcx, rsi; this
0x1800362dd  call    ?Shutdown@NotificationWindow@@QEAAX_N@Z; NotificationWindow::Shutdown(bool)
0x1800362e2  mov     rcx, rsi; this
0x1800362e5  call    ?Release@NotificationWindow@@QEAAKXZ; NotificationWindow::Release(void)
0x1800362ea  jmp     loc_1800361BA
0x1800362ef  lea     rcx, [rsp+38h+arg_18]; this
0x1800362f4  call    ?TLSAllocData@CUrlMkTls@@AEAAJXZ; CUrlMkTls::TLSAllocData(void)
0x1800362f9  test    eax, eax
0x1800362fb  jns     loc_18003625A
0x180036301  mov     eax, ebp
0x180036303  jmp     loc_180036035
0x180036308  call    ?UnregisterUrlMkWndClass@@YAHXZ; UnregisterUrlMkWndClass(void)
0x18003630d  test    rbx, rbx
0x180036310  jnz     short loc_1800362C1
0x180036312  mov     rbx, cs:?g_pCMHolder@@3PEAVCMediaTypeHolder@@EA; CMediaTypeHolder * g_pCMHolder
0x180036319  xor     ebp, ebp
0x18003631b  test    rbx, rbx
0x18003631e  jz      short loc_18003633E
0x180036320  mov     rcx, rbx; this
0x180036323  call    ??1CMediaTypeHolder@@QEAA@XZ; CMediaTypeHolder::~CMediaTypeHolder(void)
0x180036328  mov     rcx, rbx; pv
0x18003632b  call    cs:__imp_CoTaskMemFree
0x180036332  nop     dword ptr [rax+rax+00h]
0x180036337  mov     cs:?g_pCMHolder@@3PEAVCMediaTypeHolder@@EA, rbp; CMediaTypeHolder * g_pCMHolder
0x18003633e  call    ?DeleteOInetSession@@YAJK@Z; DeleteOInetSession(ulong)
0x180036343  mov     rcx, cs:?g_hSession@@3PEAXEA; hInternet
0x18003634a  test    rcx, rcx
0x18003634d  jz      loc_1800362C1
0x180036353  call    cs:__imp_InternetCloseHandle
0x18003635a  nop     dword ptr [rax+rax+00h]
0x18003635f  mov     cs:?g_hSession@@3PEAXEA, rbp; void * g_hSession
0x180036366  jmp     loc_1800362C1
0x18003636b  mov     rsi, rbp
0x18003636e  jmp     loc_18003617C
0x180036373  mov     rcx, [rsi+10h]; pv
0x180036377  mov     rsi, [rsi]
0x18003637a  test    rcx, rcx
0x18003637d  jz      short loc_18003638B
0x18003637f  call    cs:__imp_CoTaskMemFree
0x180036386  nop     dword ptr [rax+rax+00h]
0x18003638b  inc     edi
0x18003638d  cmp     edi, r14d
0x180036390  jl      short loc_180036373
0x180036392  mov     rdi, [rbx+30h]
0x180036396  mov     r14, [rsp+38h+var_18]
0x18003639b  test    rdi, rdi
0x18003639e  jz      short loc_1800363CA
0x1800363a0  mov     rcx, [rdi+20h]; this
0x1800363a4  mov     [rdi+10h], ebp
0x1800363a7  mov     [rdi+18h], rbp
0x1800363ab  mov     [rdi+8], rbp
0x1800363af  mov     [rdi], rbp
0x1800363b2  call    ?FreeDataChain@CPlex@@QEAAXXZ; CPlex::FreeDataChain(void)
0x1800363b7  mov     rcx, rdi; pv
0x1800363ba  mov     [rdi+20h], rbp
0x1800363be  call    cs:__imp_CoTaskMemFree
0x1800363c5  nop     dword ptr [rax+rax+00h]
0x1800363ca  mov     [rbx+30h], rbp
0x1800363ce  jmp     loc_1800360DA
0x1800363d3  mov     rcx, rdi
0x1800363d6  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x1800363db  mov     rcx, rdi; pv
0x1800363de  call    cs:__imp_CoTaskMemFree
0x1800363e5  nop     dword ptr [rax+rax+00h]
0x1800363ea  mov     [rbx+10h], rbp
0x1800363ee  jmp     loc_1800360C8
0x1800363f3  mov     rsi, [rax]
0x1800363f6  mov     edi, ebp
0x1800363f8  mov     [rsp+38h+var_18], r14
0x1800363fd  mov     r14d, [rax+10h]
0x180036401  test    r14d, r14d
0x180036404  jle     short loc_180036392
0x180036406  jmp     loc_180036373
0x18003640b  lea     rcx, [rdi+8]
0x18003640f  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x180036414  mov     rcx, rdi; pv
0x180036417  call    cs:__imp_CoTaskMemFree
0x18003641e  nop     dword ptr [rax+rax+00h]
0x180036423  mov     [rbx+20h], rbp
0x180036427  jmp     loc_1800360E7
0x18003642c  lea     rcx, [rdi+8]
0x180036430  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x180036435  mov     rcx, rdi; pv
0x180036438  call    cs:__imp_CoTaskMemFree
0x18003643f  nop     dword ptr [rax+rax+00h]
0x180036444  mov     [rbx+18h], rbp
0x180036448  jmp     loc_1800360F4
0x18003644d  mov     rcx, rdi; this
0x180036450  call    ??1CCDLPacketMgr@@QEAA@XZ; CCDLPacketMgr::~CCDLPacketMgr(void)
0x180036455  mov     rcx, rdi; pv
0x180036458  call    cs:__imp_CoTaskMemFree
0x18003645f  nop     dword ptr [rax+rax+00h]
0x180036464  mov     [rbx+28h], rbp
0x180036468  jmp     loc_180036101
0x18003646d  mov     rax, [rcx]
0x180036470  mov     rax, [rax+10h]
0x180036474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036479  mov     [rbx+38h], rbp
0x18003647d  jmp     loc_18003610E
0x180036482  call    ?Release@NotificationWindow@@QEAAKXZ; NotificationWindow::Release(void)
0x180036487  jmp     loc_180036188
```

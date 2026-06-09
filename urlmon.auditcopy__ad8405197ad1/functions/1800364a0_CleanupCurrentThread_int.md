# CleanupCurrentThread(int)

- ea: `0x1800364a0`
- end: `0x1800367ab`
- name: `?CleanupCurrentThread@@YAXH@Z`
- size: `779`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035af0`
- `0x1800a4a90`

## callees

- `0x18001db50`
- `0x1800364a0`
- `0x1800367b4`
- `0x180036808`
- `0x180036854`
- `0x180052494`
- `0x18005294c`
- `0x180086f20`
- `0x1800c4150`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036522`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003661f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036663`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036522`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003661f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036663`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800364f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036594`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800364f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036594`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800365e2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800365e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800364dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800364dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800364af`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800364af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003663c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003663c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003669c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800366dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800366fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036777`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003669c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800366dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800366fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036777`

## pseudocode

```c
void __fastcall CleanupCurrentThread(int a1)
{
  char *Value; // rbx
  __int64 v3; // rcx
  __int64 *v4; // rdx
  void *v5; // rdi
  __int64 v6; // rax
  void *v7; // rdi
  void *v8; // rdi
  void *v9; // rdi
  __int64 v10; // rcx
  NotificationWindow **v11; // rdi
  NotificationWindow *v12; // rsi
  char *v13; // rax
  NotificationWindow *v14; // rsi
  void *v15; // rcx
  _QWORD *v16; // rsi
  int v17; // edi
  void *v18; // rdi
  CPlex **v19; // rcx
  int v20; // r14d
  __int64 v21; // [rsp+48h] [rbp+10h] BYREF

  Value = (char *)TlsGetValue(gTlsIndex);
  if ( Value )
  {
    TlsSetValue(gTlsIndex, 0);
    EnterCriticalSection(&stru_180169110);
    v4 = (__int64 *)qword_18016AEF0;
    if ( qword_18016AEF0 )
    {
      while ( 1 )
      {
        v4 = (__int64 *)*v4;
        if ( !v4 )
          break;
        if ( (char *)v4[2] == Value )
        {
          CList<tagSUrlMkTlsData *,tagSUrlMkTlsData *>::RemoveAt(v3, v4);
          break;
        }
      }
    }
    LeaveCriticalSection(&stru_180169110);
    *((_DWORD *)Value + 1) |= 4u;
    v5 = (void *)*((_QWORD *)Value + 2);
    if ( v5 )
    {
      CList<CClBinding *,CClBinding *>::RemoveAll(*((_QWORD *)Value + 2));
      CoTaskMemFree(v5);
      *((_QWORD *)Value + 2) = 0;
    }
    v6 = *((_QWORD *)Value + 6);
    if ( v6 )
    {
      v16 = *(_QWORD **)v6;
      v17 = 0;
      v20 = *(_DWORD *)(v6 + 16);
      if ( v20 > 0 )
      {
        do
        {
          v15 = (void *)v16[2];
          v16 = (_QWORD *)*v16;
          if ( v15 )
            CoTaskMemFree(v15);
          ++v17;
        }
        while ( v17 < v20 );
      }
      v18 = (void *)*((_QWORD *)Value + 6);
      if ( v18 )
      {
        v19 = (CPlex **)*((_QWORD *)v18 + 4);
        *((_DWORD *)v18 + 4) = 0;
        *((_QWORD *)v18 + 3) = 0;
        *((_QWORD *)v18 + 1) = 0;
        *(_QWORD *)v18 = 0;
        CPlex::FreeDataChain(v19);
        *((_QWORD *)v18 + 4) = 0;
        CoTaskMemFree(v18);
      }
      *((_QWORD *)Value + 6) = 0;
    }
    v7 = (void *)*((_QWORD *)Value + 4);
    if ( v7 )
    {
      CList<CClBinding *,CClBinding *>::RemoveAll((__int64)v7 + 8);
      CoTaskMemFree(v7);
      *((_QWORD *)Value + 4) = 0;
    }
    v8 = (void *)*((_QWORD *)Value + 3);
    if ( v8 )
    {
      CList<CClBinding *,CClBinding *>::RemoveAll((__int64)v8 + 8);
      CoTaskMemFree(v8);
      *((_QWORD *)Value + 3) = 0;
    }
    v9 = (void *)*((_QWORD *)Value + 5);
    if ( v9 )
    {
      CCDLPacketMgr::~CCDLPacketMgr(*((UINT_PTR **)Value + 5));
      CoTaskMemFree(v9);
      *((_QWORD *)Value + 5) = 0;
    }
    v10 = *((_QWORD *)Value + 7);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)Value + 7) = 0;
    }
    v21 = 0;
    EnterCriticalSection(&stru_180169110);
    v11 = (NotificationWindow **)(Value + 552);
    if ( *((_QWORD *)Value + 69) )
    {
      Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(&v21);
      v12 = *v11;
      if ( *v11 )
        goto LABEL_24;
      v13 = (char *)operator new(0x40u);
      v12 = (NotificationWindow *)v13;
      if ( v13 )
      {
        *(_DWORD *)v13 = 1;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v13 + 24));
        *((_QWORD *)v12 + 2) = 0;
        *((_QWORD *)v12 + 1) = 0;
      }
      else
      {
        v12 = 0;
      }
      if ( *v11 )
        NotificationWindow::Release(*v11);
      *v11 = v12;
      if ( v12 )
LABEL_24:
        _InterlockedIncrement((volatile signed __int32 *)v12);
      v14 = *v11;
      Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease((__int64 *)Value + 69);
      LeaveCriticalSection(&stru_180169110);
      if ( v14 )
      {
        NotificationWindow::Shutdown(v14, a1 != 0);
        NotificationWindow::Release(v14);
      }
    }
    else
    {
      LeaveCriticalSection(&stru_180169110);
    }
    HeapFree(g_hHeap, 0, Value);
  }
}

```

## disassembly

```asm
0x1800364a0  push    rbx
0x1800364a2  push    rbp
0x1800364a3  sub     rsp, 28h
0x1800364a7  mov     ebp, ecx
0x1800364a9  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x1800364af  call    cs:__imp_TlsGetValue
0x1800364b6  nop     dword ptr [rax+rax+00h]
0x1800364bb  mov     rbx, rax
0x1800364be  test    rax, rax
0x1800364c1  jnz     short loc_1800364CB
0x1800364c3  add     rsp, 28h
0x1800364c7  pop     rbp
0x1800364c8  pop     rbx
0x1800364c9  retn
0x1800364cb  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x1800364d1  xor     edx, edx; lpTlsValue
0x1800364d3  mov     [rsp+38h+arg_10], rdi
0x1800364d8  mov     [rsp+38h+var_18], r15
0x1800364dd  call    cs:__imp_TlsSetValue
0x1800364e4  nop     dword ptr [rax+rax+00h]
0x1800364e9  lea     rcx, stru_180169110; lpCriticalSection
0x1800364f0  call    cs:__imp_EnterCriticalSection
0x1800364f7  nop     dword ptr [rax+rax+00h]
0x1800364fc  mov     rdx, cs:qword_18016AEF0
0x180036503  test    rdx, rdx
0x180036506  jz      short loc_18003651B
0x180036508  mov     rdx, [rdx]
0x18003650b  test    rdx, rdx
0x18003650e  jz      short loc_18003651B
0x180036510  cmp     [rdx+10h], rbx
0x180036514  jnz     short loc_180036508
0x180036516  call    ?RemoveAt@?$CList@PEAUtagSUrlMkTlsData@@PEAU1@@@QEAAXPEAX@Z; CList<tagSUrlMkTlsData *,tagSUrlMkTlsData *>::RemoveAt(void *)
0x18003651b  lea     rcx, stru_180169110; lpCriticalSection
0x180036522  call    cs:__imp_LeaveCriticalSection
0x180036529  nop     dword ptr [rax+rax+00h]
0x18003652e  or      dword ptr [rbx+4], 4
0x180036532  xor     r15d, r15d
0x180036535  mov     rdi, [rbx+10h]
0x180036539  test    rdi, rdi
0x18003653c  jnz     loc_1800366F1
0x180036542  mov     rax, [rbx+30h]
0x180036546  mov     [rsp+38h+arg_0], rsi
0x18003654b  test    rax, rax
0x18003654e  jnz     loc_180036711
0x180036554  mov     rdi, [rbx+20h]
0x180036558  test    rdi, rdi
0x18003655b  jnz     loc_18003672A
0x180036561  mov     rdi, [rbx+18h]
0x180036565  test    rdi, rdi
0x180036568  jnz     loc_18003674B
0x18003656e  mov     rdi, [rbx+28h]
0x180036572  test    rdi, rdi
0x180036575  jnz     loc_18003676C
0x18003657b  mov     rcx, [rbx+38h]
0x18003657f  test    rcx, rcx
0x180036582  jnz     loc_18003678C
0x180036588  lea     rcx, stru_180169110; lpCriticalSection
0x18003658f  mov     [rsp+38h+arg_8], r15
0x180036594  call    cs:__imp_EnterCriticalSection
0x18003659b  nop     dword ptr [rax+rax+00h]
0x1800365a0  lea     rdi, [rbx+228h]
0x1800365a7  cmp     [rdi], r15
0x1800365aa  jz      loc_18003665C
0x1800365b0  lea     rcx, [rsp+38h+arg_8]
0x1800365b5  call    ?InternalRelease@?$ComPtr@VNotificationWindow@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(void)
0x1800365ba  mov     rsi, [rdi]
0x1800365bd  test    rsi, rsi
0x1800365c0  jnz     short loc_18003660A
0x1800365c2  mov     ecx, 40h ; '@'; Size
0x1800365c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800365cc  mov     rsi, rax
0x1800365cf  test    rax, rax
0x1800365d2  jz      loc_180036688
0x1800365d8  lea     rcx, [rax+18h]; lpCriticalSection
0x1800365dc  mov     dword ptr [rax], 1
0x1800365e2  call    cs:__imp_InitializeCriticalSection
0x1800365e9  nop     dword ptr [rax+rax+00h]
0x1800365ee  mov     [rsi+10h], r15
0x1800365f2  mov     [rsi+8], r15
0x1800365f6  mov     rcx, [rdi]; this
0x1800365f9  test    rcx, rcx
0x1800365fc  jnz     loc_1800367A1
0x180036602  mov     [rdi], rsi
0x180036605  test    rsi, rsi
0x180036608  jz      short loc_18003660D
0x18003660a  lock inc dword ptr [rsi]
0x18003660d  mov     rsi, [rdi]
0x180036610  mov     rcx, rdi
0x180036613  call    ?InternalRelease@?$ComPtr@VNotificationWindow@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(void)
0x180036618  lea     rcx, stru_180169110; lpCriticalSection
0x18003661f  call    cs:__imp_LeaveCriticalSection
0x180036626  nop     dword ptr [rax+rax+00h]
0x18003662b  test    rsi, rsi
0x18003662e  jnz     short loc_180036671
0x180036630  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x180036637  mov     r8, rbx; lpMem
0x18003663a  xor     edx, edx; dwFlags
0x18003663c  call    cs:__imp_HeapFree
0x180036643  nop     dword ptr [rax+rax+00h]
0x180036648  mov     r15, [rsp+38h+var_18]
0x18003664d  mov     rdi, [rsp+38h+arg_10]
0x180036652  mov     rsi, [rsp+38h+arg_0]
0x180036657  jmp     loc_1800364C3
0x18003665c  lea     rcx, stru_180169110; lpCriticalSection
0x180036663  call    cs:__imp_LeaveCriticalSection
0x18003666a  nop     dword ptr [rax+rax+00h]
0x18003666f  jmp     short loc_180036630
0x180036671  test    ebp, ebp
0x180036673  mov     rcx, rsi; this
0x180036676  setnz   dl; bool
0x180036679  call    ?Shutdown@NotificationWindow@@QEAAX_N@Z; NotificationWindow::Shutdown(bool)
0x18003667e  mov     rcx, rsi; this
0x180036681  call    ?Release@NotificationWindow@@QEAAKXZ; NotificationWindow::Release(void)
0x180036686  jmp     short loc_180036630
0x180036688  mov     rsi, r15
0x18003668b  jmp     loc_1800365F6
0x180036690  mov     rcx, [rsi+10h]; pv
0x180036694  mov     rsi, [rsi]
0x180036697  test    rcx, rcx
0x18003669a  jz      short loc_1800366A8
0x18003669c  call    cs:__imp_CoTaskMemFree
0x1800366a3  nop     dword ptr [rax+rax+00h]
0x1800366a8  inc     edi
0x1800366aa  cmp     edi, r14d
0x1800366ad  jl      short loc_180036690
0x1800366af  mov     rdi, [rbx+30h]
0x1800366b3  mov     r14, [rsp+38h+arg_18]
0x1800366b8  test    rdi, rdi
0x1800366bb  jz      short loc_1800366E8
0x1800366bd  mov     rcx, [rdi+20h]; this
0x1800366c1  mov     [rdi+10h], r15d
0x1800366c5  mov     [rdi+18h], r15
0x1800366c9  mov     [rdi+8], r15
0x1800366cd  mov     [rdi], r15
0x1800366d0  call    ?FreeDataChain@CPlex@@QEAAXXZ; CPlex::FreeDataChain(void)
0x1800366d5  mov     rcx, rdi; pv
0x1800366d8  mov     [rdi+20h], r15
0x1800366dc  call    cs:__imp_CoTaskMemFree
0x1800366e3  nop     dword ptr [rax+rax+00h]
0x1800366e8  mov     [rbx+30h], r15
0x1800366ec  jmp     loc_180036554
0x1800366f1  mov     rcx, rdi
0x1800366f4  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x1800366f9  mov     rcx, rdi; pv
0x1800366fc  call    cs:__imp_CoTaskMemFree
0x180036703  nop     dword ptr [rax+rax+00h]
0x180036708  mov     [rbx+10h], r15
0x18003670c  jmp     loc_180036542
0x180036711  mov     rsi, [rax]
0x180036714  mov     edi, r15d
0x180036717  mov     [rsp+38h+arg_18], r14
0x18003671c  mov     r14d, [rax+10h]
0x180036720  test    r14d, r14d
0x180036723  jle     short loc_1800366AF
0x180036725  jmp     loc_180036690
0x18003672a  lea     rcx, [rdi+8]
0x18003672e  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x180036733  mov     rcx, rdi; pv
0x180036736  call    cs:__imp_CoTaskMemFree
0x18003673d  nop     dword ptr [rax+rax+00h]
0x180036742  mov     [rbx+20h], r15
0x180036746  jmp     loc_180036561
0x18003674b  lea     rcx, [rdi+8]
0x18003674f  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x180036754  mov     rcx, rdi; pv
0x180036757  call    cs:__imp_CoTaskMemFree
0x18003675e  nop     dword ptr [rax+rax+00h]
0x180036763  mov     [rbx+18h], r15
0x180036767  jmp     loc_18003656E
0x18003676c  mov     rcx, rdi; this
0x18003676f  call    ??1CCDLPacketMgr@@QEAA@XZ; CCDLPacketMgr::~CCDLPacketMgr(void)
0x180036774  mov     rcx, rdi; pv
0x180036777  call    cs:__imp_CoTaskMemFree
0x18003677e  nop     dword ptr [rax+rax+00h]
0x180036783  mov     [rbx+28h], r15
0x180036787  jmp     loc_18003657B
0x18003678c  mov     rax, [rcx]
0x18003678f  mov     rax, [rax+10h]
0x180036793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036798  mov     [rbx+38h], r15
0x18003679c  jmp     loc_180036588
0x1800367a1  call    ?Release@NotificationWindow@@QEAAKXZ; NotificationWindow::Release(void)
0x1800367a6  jmp     loc_180036602
```

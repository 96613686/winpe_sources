# WdsProviderInitialize(void *)

- ea: `0x180007120`
- end: `0x1800076ec`
- name: `?WdsProviderInitialize@@YAKPEAX@Z`
- size: `1484`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800015d8`
- `0x180002660`
- `0x18000272c`
- `0x180006a20`
- `0x180006cd4`
- `0x180006d48`
- `0x180007120`
- `0x180007eb4`
- `0x180007fd8`
- `0x180008f9c`
- `0x18000b370`
- `0x18000b3ac`
- `0x18000bdc4`
- `0x18000c0ec`
- `0x18000c3f8`
- `0x18000c69c`
- `0x18001548c`
- `0x180015ff9`
- `0x180016020`
- `0x180017010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180007267`
- `KERNEL32!HeapAlloc` at `0x1800073c0`
- `KERNEL32!HeapAlloc` at `0x180007267`
- `KERNEL32!HeapAlloc` at `0x1800073c0`
- `KERNEL32!GetProcessHeap` at `0x180007248`
- `KERNEL32!GetProcessHeap` at `0x1800073ab`
- `KERNEL32!GetProcessHeap` at `0x180007248`
- `KERNEL32!GetProcessHeap` at `0x1800073ab`
- `OLEAUT32!__imp_SysFreeString` at `0x180007634`
- `OLEAUT32!__imp_SysFreeString` at `0x180007634`
- `WDSSRV!WdsEndpointOpen` at `0x18000760f`
- `WDSSRV!WdsEndpointOpen` at `0x18000760f`
- `WDSSRV!WdsRegisterCallback` at `0x18000754e`
- `WDSSRV!WdsRegisterCallback` at `0x180007581`
- `WDSSRV!WdsRegisterCallback` at `0x1800075b4`
- `WDSSRV!WdsRegisterCallback` at `0x18000754e`
- `WDSSRV!WdsRegisterCallback` at `0x180007581`
- `WDSSRV!WdsRegisterCallback` at `0x1800075b4`
- `WdsCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x1800071ba`
- `WdsCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x1800074f3`
- `WdsCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x1800071ba`
- `WdsCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x1800074f3`
- `WdsCommonLib!?WriterLock@CMRSWLock@@QEAAXXZ` at `0x1800071e4`
- `WdsCommonLib!?WriterLock@CMRSWLock@@QEAAXXZ` at `0x1800071e4`
- `WdsCommonLib!?WriterRelease@CMRSWLock@@QEAAXXZ` at `0x180007699`
- `WdsCommonLib!?WriterRelease@CMRSWLock@@QEAAXXZ` at `0x180007699`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000735b`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000735b`
- `WdsCommonLib!?Initialize@CEventLog@@QEAAKPEBGG@Z` at `0x180007209`
- `WdsCommonLib!?Initialize@CEventLog@@QEAAKPEBGG@Z` at `0x180007209`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180007658`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180007679`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180007658`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180007679`
- `ualapi!UalStart` at `0x1800072cd`
- `ualapi!UalStart` at `0x1800072cd`

## pseudocode

```c
__int64 __fastcall WdsProviderInitialize(void *a1)
{
  void *v2; // rdi
  int v3; // r15d
  __int64 refreshed; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  CClientLibraryInitializer *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  HANDLE ProcessHeap; // rax
  void *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // ebx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rsi
  SIZE_T v27; // rsi
  HANDLE v28; // rax
  unsigned __int16 *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  size_t *v32; // r8
  __int64 v33; // rdx
  SIZE_T v34; // rsi
  SIZE_T v35; // rcx
  _WORD *v36; // rax
  SIZE_T v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  CMRSWLock *v40; // rax
  CMRSWLock *v41; // rbx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // r8
  size_t v53; // [rsp+28h] [rbp-E0h]
  BSTR bstrString[2]; // [rsp+38h] [rbp-D0h] BYREF
  int v55; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v56[131]; // [rsp+4Ch] [rbp-BCh]
  int v57; // [rsp+468h] [rbp+360h] BYREF
  __int128 v58; // [rsp+46Ch] [rbp+364h]
  char v59[668]; // [rsp+47Ch] [rbp+374h] BYREF

  memset_0(&v55, 0, 0x41Cu);
  g_hProvider = a1;
  bstrString[0] = 0;
  v2 = 0;
  v3 = 0;
  WdsImgTrace(0x10000u, L"-> WdsProviderInitialize");
  g_ErrLibTraceFunction = ErrLibTrace;
  g_ErrLibTraceFunctionEx = (void (*)(unsigned int, const unsigned __int16 *, ...))WdsImgTrace;
  refreshed = CMRSWLock::Initialize((CMRSWLock *)g_Lock, 0x200u);
  if ( !(unsigned int)ElValidateWin32(refreshed, v5, v6, 2873) )
  {
    CMRSWLock::WriterLock((CMRSWLock *)g_Lock);
    v3 = 1;
    refreshed = CEventLog::Initialize((CEventLog *)g_EventLog, L"WDSIMGSRV", 0x105u);
    if ( !(unsigned int)ElValidateWin32(refreshed, v7, v8, 2890) )
    {
      refreshed = CClientLibraryInitializer::Initialize(v9);
      if ( !(unsigned int)ElValidateWin32(refreshed, v10, v11, 2897) )
      {
        ProcessHeap = GetProcessHeap();
        v13 = HeapAlloc(ProcessHeap, 8u, 0x78u);
        v2 = v13;
        if ( !v13 )
        {
LABEL_5:
          LODWORD(refreshed) = 8;
          goto LABEL_39;
        }
        memset_0(v13, 0, 0x78u);
        memset_0(v59, 0, sizeof(v59));
        v57 = 688;
        v58 = SumGuid_WDS;
        v16 = (unsigned int)DelayLoadUalApi() ? UalStart(&v57) : 0;
        *((_DWORD *)v2 + 27) = (int)ElValidateHr(v16, v14, v15, 2911) >= 0;
        refreshed = pInitializeManagement((struct _IMG_SERVER_CONTEXT *)v2);
        if ( !(unsigned int)ElValidateWin32(refreshed, v17, v18, 2918) )
        {
          refreshed = pWdsImgSrvRefreshSettings((struct _IMG_SERVER_CONTEXT *)v2);
          if ( !(unsigned int)ElValidateWin32(refreshed, v19, v20, 2926) )
          {
            v21 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)v2 + 5) + 56LL))(
                    *((_QWORD *)v2 + 5),
                    bstrString);
            if ( (int)ElValidateHr(v21, v22, v23, 2929) < 0 )
            {
LABEL_12:
              LODWORD(refreshed) = WIN32_FROM_HRESULT(v21);
              goto LABEL_39;
            }
            refreshed = pGetRemInstPath(bstrString[0], (unsigned __int16 **)v2);
            if ( !(unsigned int)ElValidateWin32(refreshed, v24, v25, 2936) )
            {
              v26 = -1;
              do
                ++v26;
              while ( *(_WORD *)(*(_QWORD *)v2 + 2 * v26) );
              v27 = 2 * v26 + 18;
              v28 = GetProcessHeap();
              v29 = (unsigned __int16 *)HeapAlloc(v28, 8u, v27);
              *((_QWORD *)v2 + 1) = v29;
              if ( !v29 )
                goto LABEL_5;
              v21 = StringCbCopyW(v29, v27, *(const unsigned __int16 **)v2);
              if ( (int)ElValidateHr(v21, v30, v31, 2948) < 0 )
                goto LABEL_12;
              v33 = *((_QWORD *)v2 + 1);
              v34 = v27 >> 1;
              if ( v34 - 1 > 0x7FFFFFFE )
              {
                v21 = -2147024809;
              }
              else
              {
                v35 = v34;
                v36 = (_WORD *)*((_QWORD *)v2 + 1);
                do
                {
                  if ( !*v36 )
                    break;
                  ++v36;
                  --v35;
                }
                while ( v35 );
                v21 = v35 == 0 ? 0x80070057 : 0;
                if ( v35 )
                  v37 = v34 - v35;
                else
                  v37 = 0;
                if ( v35 )
                  v21 = StringCopyWorkerW((STRSAFE_LPWSTR)(v33 + 2 * v37), v34 - v37, v32, L"\\Images", v53);
              }
              if ( (int)ElValidateHr(v21, v33, v32, 2952) < 0 )
                goto LABEL_12;
              refreshed = pReadParameters((struct _IMG_SERVER_CONTEXT *)v2);
              if ( !(unsigned int)ElValidateWin32(refreshed, v38, v39, 2960) )
              {
                v40 = (CMRSWLock *)operator new(0x140u, (const struct std::nothrow_t *)&std::nothrow);
                v41 = v40;
                if ( v40 )
                {
                  CMRSWLock::CMRSWLock(v40);
                  *((_QWORD *)v41 + 16) = 0;
                  *((_QWORD *)v41 + 17) = 0;
                  *((_DWORD *)v41 + 39) = 0;
                  *((_QWORD *)v41 + 20) = 0;
                  *((_QWORD *)v41 + 21) = 0;
                  CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>((char *)v41 + 176);
                  CMRSWLock::Initialize(v41, 0);
                  *((_QWORD *)v41 + 15) = 0;
                  *((_DWORD *)v41 + 38) = 0;
                }
                else
                {
                  v41 = 0;
                }
                *((_QWORD *)v2 + 12) = v41;
                if ( !v41 )
                  goto LABEL_5;
                refreshed = CImageCache::Initialize(v41, *((const unsigned __int16 **)v2 + 1));
                if ( !(unsigned int)ElValidateWin32(refreshed, v42, v43, 2970) )
                {
                  refreshed = (unsigned int)WdsRegisterCallback(a1, 0, WdsProviderShutdown, v2);
                  if ( !(unsigned int)ElValidateWin32(refreshed, v44, v45, 2984) )
                  {
                    refreshed = (unsigned int)WdsRegisterCallback(a1, 1, RecvRequest, v2);
                    if ( !(unsigned int)ElValidateWin32(refreshed, v46, v47, 2994) )
                    {
                      refreshed = (unsigned int)WdsRegisterCallback(a1, 7, ServiceControl, v2);
                      if ( !(unsigned int)ElValidateWin32(refreshed, v48, v49, 3004) )
                      {
                        v55 = 1052;
                        v56[0] = 0x300000001LL;
                        *(_OWORD *)&v56[1] = xmmword_18001C1C8;
                        refreshed = (unsigned int)WdsEndpointOpen(a1, &v55, 0, 0, &g_hRpcEndpoint);
                        ElValidateWin32(refreshed, v50, v51, 3021);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_39:
  if ( bstrString[0] )
  {
    SysFreeString(bstrString[0]);
    bstrString[0] = 0;
  }
  if ( (_DWORD)refreshed )
  {
    CEventLog::Log((CEventLog *)g_EventLog, 0xC1060102, 1);
    pFreeContext((struct _IMG_SERVER_CONTEXT *)v2);
  }
  else
  {
    CEventLog::Log((CEventLog *)g_EventLog, 0x1060100u, 0);
  }
  if ( v3 )
    CMRSWLock::WriterRelease((CMRSWLock *)g_Lock);
  WdsImgTrace(0x10000u, L"<- WdsProviderInitialize=%x", (unsigned int)refreshed);
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x180007120  mov     rax, rsp
0x180007123  mov     [rax+10h], rbx
0x180007127  mov     [rax+18h], rsi
0x18000712b  mov     [rax+20h], rdi
0x18000712f  push    rbp
0x180007130  push    r12
0x180007132  push    r13
0x180007134  push    r14
0x180007136  push    r15
0x180007138  lea     rbp, [rax-648h]
0x18000713f  sub     rsp, 720h
0x180007146  mov     rax, cs:__security_cookie
0x18000714d  xor     rax, rsp
0x180007150  mov     [rbp+640h+var_30], rax
0x180007157  mov     r14, rcx
0x18000715a  xor     edx, edx; Val
0x18000715c  lea     rcx, [rsp+740h+var_700]; void *
0x180007161  mov     r8d, 41Ch; Size
0x180007167  call    memset_0
0x18000716c  xor     r12d, r12d
0x18000716f  mov     cs:?g_hProvider@@3PEAXEA, r14; void * g_hProvider
0x180007176  lea     rdx, aWdsproviderini_1; "-> WdsProviderInitialize"
0x18000717d  mov     [rsp+740h+bstrString], r12
0x180007182  mov     ecx, 10000h; unsigned int
0x180007187  mov     edi, r12d
0x18000718a  mov     r15d, r12d
0x18000718d  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180007192  lea     rax, ?ErrLibTrace@@YAXPEBGZZ; ErrLibTrace(ushort const *,...)
0x180007199  mov     edx, 200h
0x18000719e  mov     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, rax; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800071a5  lea     rcx, ?g_Lock@@3VCMRSWLock@@A; CMRSWLock g_Lock
0x1800071ac  lea     rax, ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x1800071b3  mov     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rax; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800071ba  call    cs:__imp_?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x1800071c1  nop     dword ptr [rax+rax+00h]
0x1800071c6  mov     ecx, eax
0x1800071c8  mov     r9d, 0B39h
0x1800071ce  mov     ebx, eax
0x1800071d0  call    ElValidateWin32
0x1800071d5  test    eax, eax
0x1800071d7  jnz     loc_18000762A
0x1800071dd  lea     rcx, ?g_Lock@@3VCMRSWLock@@A; CMRSWLock g_Lock
0x1800071e4  call    cs:__imp_?WriterLock@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterLock(void)
0x1800071eb  nop     dword ptr [rax+rax+00h]
0x1800071f0  mov     r8d, 105h
0x1800071f6  lea     rdx, aWdsimgsrv; "WDSIMGSRV"
0x1800071fd  lea     rcx, ?g_EventLog@@3VCEventLog@@A; CEventLog g_EventLog
0x180007204  lea     r15d, [r12+1]
0x180007209  call    cs:__imp_?Initialize@CEventLog@@QEAAKPEBGG@Z; CEventLog::Initialize(ushort const *,ushort)
0x180007210  nop     dword ptr [rax+rax+00h]
0x180007215  mov     ecx, eax
0x180007217  mov     r9d, 0B4Ah
0x18000721d  mov     ebx, eax
0x18000721f  call    ElValidateWin32
0x180007224  test    eax, eax
0x180007226  jnz     loc_18000762A
0x18000722c  call    ?Initialize@CClientLibraryInitializer@@QEAAKXZ; CClientLibraryInitializer::Initialize(void)
0x180007231  mov     r9d, 0B51h
0x180007237  mov     ecx, eax
0x180007239  mov     ebx, eax
0x18000723b  call    ElValidateWin32
0x180007240  test    eax, eax
0x180007242  jnz     loc_18000762A
0x180007248  call    cs:__imp_GetProcessHeap
0x18000724f  nop     dword ptr [rax+rax+00h]
0x180007254  lea     ebx, [r12+78h]
0x180007259  mov     rcx, rax; hHeap
0x18000725c  lea     r13d, [r12+8]
0x180007261  mov     r8d, ebx; dwBytes
0x180007264  mov     edx, r13d; dwFlags
0x180007267  call    cs:__imp_HeapAlloc
0x18000726e  nop     dword ptr [rax+rax+00h]
0x180007273  mov     rdi, rax
0x180007276  test    rax, rax
0x180007279  jnz     short loc_180007283
0x18000727b  mov     ebx, r13d
0x18000727e  jmp     loc_18000762A
0x180007283  mov     r8, rbx; Size
0x180007286  xor     edx, edx; Val
0x180007288  mov     rcx, rdi; void *
0x18000728b  call    memset_0
0x180007290  xor     edx, edx; Val
0x180007292  lea     rcx, [rbp+640h+var_2CC]; void *
0x180007299  mov     r8d, 29Ch; Size
0x18000729f  call    memset_0
0x1800072a4  movups  xmm0, cs:SumGuid_WDS
0x1800072ab  mov     [rbp+640h+var_2E0], 2B0h
0x1800072b5  movdqu  [rbp+640h+var_2DC], xmm0
0x1800072bd  call    ?DelayLoadUalApi@@YAHXZ; DelayLoadUalApi(void)
0x1800072c2  test    eax, eax
0x1800072c4  jz      short loc_1800072DB
0x1800072c6  lea     rcx, [rbp+640h+var_2E0]
0x1800072cd  call    cs:__imp_UalStart
0x1800072d4  nop     dword ptr [rax+rax+00h]
0x1800072d9  jmp     short loc_1800072DE
0x1800072db  mov     eax, r12d
0x1800072de  mov     r9d, 0B5Fh
0x1800072e4  mov     ecx, eax
0x1800072e6  call    ElValidateHr
0x1800072eb  not     eax
0x1800072ed  mov     rcx, rdi; struct _IMG_SERVER_CONTEXT *
0x1800072f0  shr     eax, 1Fh
0x1800072f3  mov     [rdi+6Ch], eax
0x1800072f6  call    ?pInitializeManagement@@YAKPEAU_IMG_SERVER_CONTEXT@@@Z; pInitializeManagement(_IMG_SERVER_CONTEXT *)
0x1800072fb  mov     r9d, 0B66h
0x180007301  mov     ecx, eax
0x180007303  mov     ebx, eax
0x180007305  call    ElValidateWin32
0x18000730a  test    eax, eax
0x18000730c  jnz     loc_18000762A
0x180007312  mov     rcx, rdi; struct _IMG_SERVER_CONTEXT *
0x180007315  call    ?pWdsImgSrvRefreshSettings@@YAKPEAU_IMG_SERVER_CONTEXT@@@Z; pWdsImgSrvRefreshSettings(_IMG_SERVER_CONTEXT *)
0x18000731a  mov     r9d, 0B6Eh
0x180007320  mov     ecx, eax
0x180007322  mov     ebx, eax
0x180007324  call    ElValidateWin32
0x180007329  test    eax, eax
0x18000732b  jnz     loc_18000762A
0x180007331  mov     rcx, [rdi+28h]
0x180007335  lea     rdx, [rsp+740h+bstrString]
0x18000733a  mov     rax, [rcx]
0x18000733d  mov     rax, [rax+38h]
0x180007341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007346  mov     r9d, 0B71h
0x18000734c  mov     ecx, eax
0x18000734e  mov     ebx, eax
0x180007350  call    ElValidateHr
0x180007355  test    eax, eax
0x180007357  jns     short loc_18000736E
0x180007359  mov     ecx, ebx
0x18000735b  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180007362  nop     dword ptr [rax+rax+00h]
0x180007367  mov     ebx, eax
0x180007369  jmp     loc_18000762A
0x18000736e  mov     rcx, [rsp+740h+bstrString]; unsigned __int16 *
0x180007373  mov     rdx, rdi; unsigned __int16 **
0x180007376  call    ?pGetRemInstPath@@YAKPEAGPEAPEAG@Z; pGetRemInstPath(ushort *,ushort * *)
0x18000737b  mov     r9d, 0B78h
0x180007381  mov     ecx, eax
0x180007383  mov     ebx, eax
0x180007385  call    ElValidateWin32
0x18000738a  test    eax, eax
0x18000738c  jnz     loc_18000762A
0x180007392  mov     rax, [rdi]
0x180007395  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007399  inc     rsi
0x18000739c  cmp     [rax+rsi*2], r12w
0x1800073a1  jnz     short loc_180007399
0x1800073a3  lea     rsi, ds:12h[rsi*2]
0x1800073ab  call    cs:__imp_GetProcessHeap
0x1800073b2  nop     dword ptr [rax+rax+00h]
0x1800073b7  mov     r8, rsi; dwBytes
0x1800073ba  mov     edx, r13d; dwFlags
0x1800073bd  mov     rcx, rax; hHeap
0x1800073c0  call    cs:__imp_HeapAlloc
0x1800073c7  nop     dword ptr [rax+rax+00h]
0x1800073cc  mov     [rdi+8], rax
0x1800073d0  test    rax, rax
0x1800073d3  jz      loc_18000727B
0x1800073d9  mov     r8, [rdi]; unsigned __int16 *
0x1800073dc  mov     rdx, rsi; unsigned __int64
0x1800073df  mov     rcx, rax; unsigned __int16 *
0x1800073e2  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800073e7  mov     r9d, 0B84h
0x1800073ed  mov     ecx, eax
0x1800073ef  mov     ebx, eax
0x1800073f1  call    ElValidateHr
0x1800073f6  test    eax, eax
0x1800073f8  js      loc_180007359
0x1800073fe  mov     rdx, [rdi+8]
0x180007402  shr     rsi, 1
0x180007405  lea     rax, [rsi-1]
0x180007409  cmp     rax, 7FFFFFFEh
0x18000740f  ja      short loc_180007465
0x180007411  mov     rcx, rsi
0x180007414  mov     rax, rdx
0x180007417  cmp     [rax], r12w
0x18000741b  jz      short loc_180007426
0x18000741d  add     rax, 2
0x180007421  sub     rcx, r15
0x180007424  jnz     short loc_180007417
0x180007426  mov     rax, rcx
0x180007429  neg     rax
0x18000742c  sbb     ebx, ebx
0x18000742e  not     ebx
0x180007430  and     ebx, 80070057h
0x180007436  test    rcx, rcx
0x180007439  jz      short loc_180007443
0x18000743b  mov     rax, rsi
0x18000743e  sub     rax, rcx
0x180007441  jmp     short loc_180007446
0x180007443  mov     rax, r12
0x180007446  test    rcx, rcx
0x180007449  jz      short loc_18000746A
0x18000744b  sub     rsi, rax
0x18000744e  lea     rcx, [rdx+rax*2]; pszDest
0x180007452  mov     rdx, rsi; cchDest
0x180007455  lea     r9, aImages; "\\Images"
0x18000745c  call    StringCopyWorkerW
0x180007461  mov     ebx, eax
0x180007463  jmp     short loc_18000746A
0x180007465  mov     ebx, 80070057h
0x18000746a  mov     r9d, 0B88h
0x180007470  mov     ecx, ebx
0x180007472  call    ElValidateHr
0x180007477  test    eax, eax
0x180007479  js      loc_180007359
0x18000747f  mov     rcx, rdi; struct _IMG_SERVER_CONTEXT *
0x180007482  call    ?pReadParameters@@YAKPEAU_IMG_SERVER_CONTEXT@@@Z; pReadParameters(_IMG_SERVER_CONTEXT *)
0x180007487  mov     r9d, 0B90h
0x18000748d  mov     ecx, eax
0x18000748f  mov     ebx, eax
0x180007491  call    ElValidateWin32
0x180007496  test    eax, eax
0x180007498  jnz     loc_18000762A
0x18000749e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800074a5  mov     ecx, 140h; unsigned __int64
0x1800074aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800074af  mov     rbx, rax
0x1800074b2  test    rax, rax
0x1800074b5  jz      short loc_18000750C
0x1800074b7  mov     rcx, rax; this
0x1800074ba  call    ??0CMRSWLock@@QEAA@XZ; CMRSWLock::CMRSWLock(void)
0x1800074bf  mov     [rbx+80h], r12
0x1800074c6  lea     rcx, [rbx+0B0h]
0x1800074cd  mov     [rbx+88h], r12
0x1800074d4  mov     [rbx+9Ch], r12d
0x1800074db  mov     [rbx+0A0h], r12
0x1800074e2  mov     [rbx+0A8h], r12
0x1800074e9  call    ??0?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@QEAA@XZ; CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>(void)
0x1800074ee  xor     edx, edx
0x1800074f0  mov     rcx, rbx
0x1800074f3  call    cs:__imp_?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x1800074fa  nop     dword ptr [rax+rax+00h]
0x1800074ff  mov     [rbx+78h], r12
0x180007503  mov     [rbx+98h], r12d
0x18000750a  jmp     short loc_18000750F
0x18000750c  mov     rbx, r12
0x18000750f  mov     [rdi+60h], rbx
0x180007513  test    rbx, rbx
0x180007516  jz      loc_18000727B
0x18000751c  mov     rdx, [rdi+8]; unsigned __int16 *
0x180007520  mov     rcx, rbx; this
0x180007523  call    ?Initialize@CImageCache@@QEAAKPEBG@Z; CImageCache::Initialize(ushort const *)
0x180007528  mov     r9d, 0B9Ah
0x18000752e  mov     ecx, eax
0x180007530  mov     ebx, eax
0x180007532  call    ElValidateWin32
0x180007537  test    eax, eax
0x180007539  jnz     loc_18000762A
0x18000753f  mov     r9, rdi
0x180007542  lea     r8, ?WdsProviderShutdown@@YAKPEAX@Z; WdsProviderShutdown(void *)
0x180007549  xor     edx, edx
0x18000754b  mov     rcx, r14
0x18000754e  call    cs:__imp_WdsRegisterCallback
0x180007555  nop     dword ptr [rax+rax+00h]
0x18000755a  mov     ecx, eax
0x18000755c  mov     r9d, 0BA8h
0x180007562  mov     ebx, eax
0x180007564  call    ElValidateWin32
0x180007569  test    eax, eax
0x18000756b  jnz     loc_18000762A
0x180007571  mov     r9, rdi
0x180007574  lea     r8, ?RecvRequest@@YAKPEAX0PEAUtagWDS_ENDPOINT@@10K@Z; RecvRequest(void *,void *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ulong)
0x18000757b  mov     edx, r15d
0x18000757e  mov     rcx, r14
0x180007581  call    cs:__imp_WdsRegisterCallback
0x180007588  nop     dword ptr [rax+rax+00h]
0x18000758d  mov     ecx, eax
0x18000758f  mov     r9d, 0BB2h
0x180007595  mov     ebx, eax
0x180007597  call    ElValidateWin32
0x18000759c  test    eax, eax
0x18000759e  jnz     loc_18000762A
0x1800075a4  mov     r9, rdi
0x1800075a7  lea     r8, ?ServiceControl@@YAXPEAXK@Z; ServiceControl(void *,ulong)
0x1800075ae  lea     edx, [rax+7]
0x1800075b1  mov     rcx, r14
0x1800075b4  call    cs:__imp_WdsRegisterCallback
0x1800075bb  nop     dword ptr [rax+rax+00h]
0x1800075c0  mov     ecx, eax
0x1800075c2  mov     r9d, 0BBCh
0x1800075c8  mov     ebx, eax
0x1800075ca  call    ElValidateWin32
0x1800075cf  test    eax, eax
0x1800075d1  jnz     short loc_18000762A
0x1800075d3  movups  xmm0, cs:xmmword_18001C1C8
0x1800075da  lea     rax, ?g_hRpcEndpoint@@3PEAXEA; void * g_hRpcEndpoint
0x1800075e1  mov     [rsp+740h+var_700], 41Ch
0x1800075e9  xor     r9d, r9d
0x1800075ec  mov     dword ptr [rsp+740h+var_6FC], r15d
0x1800075f1  xor     r8d, r8d
0x1800075f4  mov     dword ptr [rsp+740h+var_6FC+4], 3
0x1800075fc  lea     rdx, [rsp+740h+var_700]
0x180007601  mov     [rsp+740h+var_720], rax
0x180007606  mov     rcx, r14
0x180007609  movdqu  xmmword ptr [rsp+740h+var_6FC+8], xmm0
0x18000760f  call    cs:__imp_WdsEndpointOpen
0x180007616  nop     dword ptr [rax+rax+00h]
0x18000761b  mov     ecx, eax
  ... truncated ...
```

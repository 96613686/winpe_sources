# SNIInitializeEx

- ea: `0x383894440`
- end: `0x38389461d`
- name: `SNIInitializeEx`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x3838817a0`

## callees

- `0x383846430`
- `0x3838832d0`
- `0x383890e50`
- `0x383890ed0`
- `0x383891080`
- `0x383892840`
- `0x383894440`
- `0x383894630`
- `0x383894a40`
- `0x383894b20`
- `0x3838bcc20`
- `0x38391ac00`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0b20`
- `0x383ab0c30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x3838f6760`
- `KERNEL32!GetLastError` at `0x3838f67a7`
- `KERNEL32!GetLastError` at `0x3838f6877`
- `KERNEL32!GetLastError` at `0x3838f6760`
- `KERNEL32!GetLastError` at `0x3838f67a7`
- `KERNEL32!GetLastError` at `0x3838f6877`
- `KERNEL32!CloseHandle` at `0x3838f664e`
- `KERNEL32!CloseHandle` at `0x3838f664e`
- `KERNEL32!GetVersionExA` at `0x38389451f`
- `KERNEL32!GetVersionExA` at `0x38389451f`
- `KERNEL32!GetComputerNameA` at `0x383894500`
- `KERNEL32!GetComputerNameA` at `0x383894500`
- `KERNEL32!CreateIoCompletionPort` at `0x38389457f`
- `KERNEL32!CreateIoCompletionPort` at `0x38389457f`

## pseudocode

```c
__int64 __fastcall SNIInitializeEx(int a1)
{
  struct CCriticalSectionNT_SNI *v2; // rsi
  DWORD ClusterResourceLibraryIfNeeded; // ebx
  LastConnectCache *v4; // rcx
  unsigned int v5; // eax
  struct CLUSTER_API *v6; // rdx
  unsigned int v7; // edx
  const enum ProviderNum *v8; // rcx
  unsigned int v10; // eax
  char *v11; // r8
  char *v12; // rcx
  __int64 v13; // rdx
  struct SNIMemRegion *v14; // rcx
  int v15; // [rsp+20h] [rbp-38h]
  DWORD nSize; // [rsp+68h] [rbp+10h] BYREF
  __int64 v17; // [rsp+70h] [rbp+18h] BYREF

  v17 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B485B0[0] )
  {
    v15 = 0;
    bidScopeEnterA(&v17, off_383B485B0[0], 0);
  }
  v2 = g_csInitialize;
  ClusterResourceLibraryIfNeeded = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)g_csInitialize + 2) + 32LL) + 8LL))(*((_QWORD *)g_csInitialize
                                                                                                + 2) + 32LL);
  if ( _InterlockedIncrement(&gcSNIInitialized) == 1 )
  {
    g_fSandbox = a1;
    gpmo = (struct ISOSHost_MemObj *)g_pMO;
    if ( !a1 )
      LastConnectCache::Initialize(v4);
    SNIMemRegion::s_rgClientMemRegion = SNIMemRegion::Init();
    if ( SNIMemRegion::s_rgClientMemRegion )
    {
      v5 = CCriticalSectionNT_SNI::Initialize(&g_csLocalDBInitialize);
      ClusterResourceLibraryIfNeeded = v5;
      if ( v5 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_26;
        if ( off_383B461F8[0] )
          bidTraceA(off_383B43B78[0], 1315840, off_383B461F8[0], v5, v15);
        if ( (bidGblFlags & 2) == 0 || !off_383B461F0[0] )
          goto LABEL_26;
        v10 = SniErrorIdFromStringId(0xC3B4u);
        v11 = off_383B461F0[0];
        v12 = off_383B43B70[0];
        v13 = 1316864;
      }
      else
      {
        MakeNodeMask();
        nSize = 255;
        if ( GetComputerNameA(gszComputerName, &nSize) )
        {
          g_osviSNI.dwOSVersionInfoSize = 156;
          if ( GetVersionExA(&g_osviSNI) )
          {
            if ( (unsigned int)FVistaSP1orLater() )
            {
              if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B461D8[0] && bidID != -1 )
              {
                v15 = 0;
                off_383B15038();
              }
              Tcp::s_fAutoTuning = 1;
            }
            ClusterResourceLibraryIfNeeded = CCriticalSectionNT_SNI::Initialize(&g_pcsListenerList);
            if ( ClusterResourceLibraryIfNeeded )
            {
              if ( (bidGblFlags & 2) == 0 || !off_383B461D0[0] )
                goto LABEL_26;
              v10 = SniErrorIdFromStringId(0xC3B4u);
              v11 = off_383B461D0[0];
              v12 = off_383B43B50[0];
              v13 = 1378304;
            }
            else
            {
              g_fTerminate = 0;
              ghIoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
              if ( ghIoCompletionPort )
              {
                ClusterResourceLibraryIfNeeded = SNICreateWaitThread((LPTHREAD_START_ROUTINE)SNIAsyncWait, 0);
                if ( !ClusterResourceLibraryIfNeeded )
                {
                  gClusApi = 0;
                  qword_383B23DF8 = 0;
                  ClusterResourceLibraryIfNeeded = LoadClusterResourceLibraryIfNeeded(
                                                     (struct CLUSTER_API *)&gClusApi,
                                                     v6);
                  if ( !ClusterResourceLibraryIfNeeded )
                  {
                    SNI_Provider::InitProviders(v8, v7);
                    goto LABEL_17;
                  }
                }
                goto LABEL_27;
              }
              ClusterResourceLibraryIfNeeded = GetLastError();
              if ( (bidGblFlags & 2) == 0 || !off_383B461C8[0] )
              {
LABEL_26:
                SNISetLastError(9, ClusterResourceLibraryIfNeeded, 50100);
LABEL_27:
                if ( g_wszInstanceNameCopy )
                {
                  ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
                  g_wszInstanceNameCopy = 0;
                }
                if ( g_pcsListenerList )
                {
                  (**(void (__fastcall ***)(struct CCriticalSectionNT_SNI *, __int64))g_pcsListenerList)(
                    g_pcsListenerList,
                    1);
                  g_pcsListenerList = 0;
                }
                if ( g_csLocalDBInitialize )
                {
                  (**(void (__fastcall ***)(struct CCriticalSectionNT_SNI *, __int64))g_csLocalDBInitialize)(
                    g_csLocalDBInitialize,
                    1);
                  g_csLocalDBInitialize = 0;
                }
                v14 = (struct SNIMemRegion *)ghIoCompletionPort;
                if ( ghIoCompletionPort )
                {
                  CloseHandle(ghIoCompletionPort);
                  ghIoCompletionPort = 0;
                }
                if ( SNIMemRegion::s_rgClientMemRegion )
                {
                  SNIMemRegion::Terminate(v14);
                  SNIMemRegion::s_rgClientMemRegion = 0;
                }
                LastConnectCache::Shutdown(v14);
                g_NodeMask = 0;
                _InterlockedDecrement(&gcSNIInitialized);
                goto LABEL_17;
              }
              v10 = SniErrorIdFromStringId(0xC3B4u);
              v11 = off_383B461C8[0];
              v12 = off_383B43B48[0];
              v13 = 1396736;
            }
          }
          else
          {
            ClusterResourceLibraryIfNeeded = GetLastError();
            if ( (bidGblFlags & 2) == 0 || !off_383B461E0[0] )
              goto LABEL_26;
            v10 = SniErrorIdFromStringId(0xC3B4u);
            v11 = off_383B461E0[0];
            v12 = off_383B43B60[0];
            v13 = 1360896;
          }
        }
        else
        {
          ClusterResourceLibraryIfNeeded = GetLastError();
          if ( (bidGblFlags & 2) == 0 || !off_383B461E8[0] )
            goto LABEL_26;
          v10 = SniErrorIdFromStringId(0xC3B4u);
          v11 = off_383B461E8[0];
          v12 = off_383B43B68[0];
          v13 = 1346560;
        }
      }
    }
    else
    {
      ClusterResourceLibraryIfNeeded = 14;
      if ( (bidGblFlags & 2) == 0 || !off_383B46200[0] )
        goto LABEL_26;
      v10 = SniErrorIdFromStringId(0xC3B4u);
      v11 = off_383B46200[0];
      v12 = off_383B43B80[0];
      v13 = 1306624;
    }
    bidTraceA(v12, v13, v11, 9, v10);
    goto LABEL_26;
  }
LABEL_17:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v2 + 2) + 32LL) + 24LL))(*((_QWORD *)v2 + 2) + 32LL);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B461B8[0] )
    bidTraceA(off_383B43B38[0], 1502208, off_383B461B8[0], ClusterResourceLibraryIfNeeded, v15);
  if ( v17 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return ClusterResourceLibraryIfNeeded;
}

```

## disassembly

```asm
0x383894440  mov     [rsp+arg_0], rbx
0x383894445  push    rbp
0x383894446  push    rsi
0x383894447  push    rdi
0x383894448  sub     rsp, 40h
0x38389444c  mov     eax, cs:_bidGblFlags
0x383894452  xor     ebp, ebp
0x383894454  mov     edi, ecx
0x383894456  and     eax, 20004h
0x38389445b  mov     [rsp+58h+arg_10], 0FFFFFFFFFFFFFFFFh
0x383894464  cmp     eax, 20004h
0x383894469  jz      loc_3838F654D
0x38389446f  mov     rsi, cs:?g_csInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csInitialize
0x383894476  mov     ebx, ebp
0x383894478  mov     rcx, [rsi+10h]
0x38389447c  mov     rax, [rcx+20h]
0x383894480  add     rcx, 20h ; ' '
0x383894484  call    qword ptr [rax+8]
0x383894487  mov     eax, 1
0x38389448c  lock xadd cs:?gcSNIInitialized@@3JA, eax; long gcSNIInitialized
0x383894494  inc     eax
0x383894496  cmp     eax, 1
0x383894499  jnz     loc_3838945D8
0x38389449f  mov     rax, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838944a6  mov     cs:?g_fSandbox@@3HA, edi; int g_fSandbox
0x3838944ac  mov     cs:?gpmo@@3PEAUISOSHost_MemObj@@EA, rax; ISOSHost_MemObj * gpmo
0x3838944b3  test    edi, edi
0x3838944b5  jnz     short loc_3838944BC
0x3838944b7  call    ?Initialize@LastConnectCache@@YAXXZ; LastConnectCache::Initialize(void)
0x3838944bc  call    ?Init@SNIMemRegion@@SAPEAV1@XZ; SNIMemRegion::Init(void)
0x3838944c1  mov     cs:?s_rgClientMemRegion@SNIMemRegion@@2PEAV1@EA, rax; SNIMemRegion * SNIMemRegion::s_rgClientMemRegion
0x3838944c8  test    rax, rax
0x3838944cb  jz      loc_3838F658B
0x3838944d1  lea     rcx, ?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; struct CCriticalSectionNT_SNI **
0x3838944d8  call    ?Initialize@CCriticalSectionNT_SNI@@SAKPEAPEAV1@@Z; CCriticalSectionNT_SNI::Initialize(CCriticalSectionNT_SNI * *)
0x3838944dd  mov     ebx, eax
0x3838944df  test    eax, eax
0x3838944e1  jnz     loc_3838F66ED
0x3838944e7  call    ?MakeNodeMask@@YAXXZ; MakeNodeMask(void)
0x3838944ec  lea     rdx, [rsp+58h+nSize]; nSize
0x3838944f1  lea     rcx, ?gszComputerName@@3PADA; lpBuffer
0x3838944f8  mov     [rsp+58h+nSize], 0FFh
0x383894500  call    cs:__imp_GetComputerNameA
0x383894506  test    eax, eax
0x383894508  jz      loc_3838F6760
0x38389450e  lea     rcx, ?g_osviSNI@@3U_OSVERSIONINFOEXA@@A; lpVersionInformation
0x383894515  mov     cs:?g_osviSNI@@3U_OSVERSIONINFOEXA@@A.dwOSVersionInfoSize, 9Ch; _OSVERSIONINFOEXA g_osviSNI ...
0x38389451f  call    cs:__imp_GetVersionExA
0x383894525  test    eax, eax
0x383894527  jz      loc_3838F67A7
0x38389452d  call    ?FVistaSP1orLater@@YAHXZ; FVistaSP1orLater(void)
0x383894532  test    eax, eax
0x383894534  jz      short loc_383894556
0x383894536  mov     eax, cs:_bidGblFlags
0x38389453c  and     eax, 20002h
0x383894541  cmp     eax, 20002h
0x383894546  jz      loc_3838F67EE
0x38389454c  mov     cs:?s_fAutoTuning@Tcp@@2HA, 1; int Tcp::s_fAutoTuning
0x383894556  lea     rcx, ?g_pcsListenerList@@3PEAVCCriticalSectionNT_SNI@@EA; struct CCriticalSectionNT_SNI **
0x38389455d  call    ?Initialize@CCriticalSectionNT_SNI@@SAKPEAPEAV1@@Z; CCriticalSectionNT_SNI::Initialize(CCriticalSectionNT_SNI * *)
0x383894562  mov     ebx, eax
0x383894564  test    eax, eax
0x383894566  jnz     loc_3838F6838
0x38389456c  xor     r9d, r9d; NumberOfConcurrentThreads
0x38389456f  xor     r8d, r8d; CompletionKey
0x383894572  xor     edx, edx; ExistingCompletionPort
0x383894574  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x383894578  mov     cs:?g_fTerminate@@3_NA, bpl; bool g_fTerminate
0x38389457f  call    cs:__imp_CreateIoCompletionPort
0x383894585  mov     cs:?ghIoCompletionPort@@3PEAXEA, rax; void * ghIoCompletionPort
0x38389458c  test    rax, rax
0x38389458f  jz      loc_3838F6877
0x383894595  lea     rcx, ?SNIAsyncWait@@YAKPEAX@Z; lpStartAddress
0x38389459c  xor     edx, edx; lpParameter
0x38389459e  call    SNICreateWaitThread
0x3838945a3  mov     ebx, eax
0x3838945a5  test    eax, eax
0x3838945a7  jnz     loc_3838F65E5
0x3838945ad  lea     rcx, ?gClusApi@@3UCLUSTER_API@@A; struct CLUSTER_API *
0x3838945b4  mov     cs:?gClusApi@@3UCLUSTER_API@@A, rbp; CLUSTER_API gClusApi
0x3838945bb  mov     cs:qword_383B23DF8, rbp
0x3838945c2  call    ?LoadClusterResourceLibraryIfNeeded@@YAKHPEAUCLUSTER_API@@@Z; LoadClusterResourceLibraryIfNeeded(int,CLUSTER_API *)
0x3838945c7  mov     ebx, eax
0x3838945c9  test    eax, eax
0x3838945cb  jnz     loc_3838F65E5
0x3838945d1  call    ?InitProviders@SNI_Provider@@SAXPEBW4ProviderNum@@K@Z; SNI_Provider::InitProviders(ProviderNum const *,ulong)
0x3838945d6  jmp     short $+2
0x3838945d8  mov     rcx, [rsi+10h]
0x3838945dc  mov     rax, [rcx+20h]
0x3838945e0  add     rcx, 20h ; ' '
0x3838945e4  call    qword ptr [rax+18h]
0x3838945e7  mov     r11d, cs:_bidGblFlags
0x3838945ee  and     r11d, 20002h
0x3838945f5  cmp     r11d, 20002h
0x3838945fc  jz      loc_3838F6688
0x383894602  cmp     [rsp+58h+arg_10], 0FFFFFFFFFFFFFFFFh
0x383894608  jnz     loc_3838F66B9
0x38389460e  mov     eax, ebx
0x383894610  mov     rbx, [rsp+58h+arg_0]
0x383894615  add     rsp, 40h
0x383894619  pop     rdi
0x38389461a  pop     rsi
0x38389461b  pop     rbp
0x38389461c  retn
0x3838f654d  mov     rax, cs:off_383B485B0; "<SNIInitializeEx|API|SNI> pmo: %p{void*"...
0x3838f6554  test    rax, rax
0x3838f6557  jz      loc_38389446F
0x3838f655d  mov     rdx, cs:off_383B485B0; "<SNIInitializeEx|API|SNI> pmo: %p{void*"...
0x3838f6564  mov     [rsp+58h+var_20], rbp
0x3838f6569  mov     [rsp+58h+var_28], ebp
0x3838f656d  mov     [rsp+58h+var_30], ecx
0x3838f6571  lea     rcx, [rsp+58h+arg_10]
0x3838f6576  xor     r9d, r9d
0x3838f6579  xor     r8d, r8d
0x3838f657c  mov     dword ptr [rsp+58h+var_38], ebp
0x3838f6580  call    _bidScopeEnterA
0x3838f6585  nop
0x3838f6586  jmp     loc_38389446F
0x3838f658b  test    byte ptr cs:_bidGblFlags, 2
0x3838f6592  lea     ebx, [rax+0Eh]
0x3838f6595  jz      short loc_3838F65D3
0x3838f6597  mov     rax, cs:off_383B46200; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f659e  test    rax, rax
0x3838f65a1  jz      short loc_3838F65D3
0x3838f65a3  mov     ecx, 0C3B4h; unsigned int
0x3838f65a8  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f65ad  mov     r8, cs:off_383B46200; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f65b4  mov     rcx, cs:off_383B43B80; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f65bb  mov     edx, 13F000h
0x3838f65c0  mov     r9d, 9
0x3838f65c6  mov     [rsp+58h+var_30], ebx
0x3838f65ca  mov     dword ptr [rsp+58h+var_38], eax
0x3838f65ce  call    _bidTraceA
0x3838f65d3  mov     r8d, 0C3B4h
0x3838f65d9  mov     edx, ebx
0x3838f65db  mov     ecx, 9
0x3838f65e0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838f65e5  mov     rdx, cs:?g_wszInstanceNameCopy@@3PEAGEA; ushort * g_wszInstanceNameCopy
0x3838f65ec  test    rdx, rdx
0x3838f65ef  jz      short loc_3838F6608
0x3838f65f1  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838f65f8  mov     rax, [rcx]
0x3838f65fb  call    qword ptr [rax+80h]
0x3838f6601  mov     cs:?g_wszInstanceNameCopy@@3PEAGEA, rbp; ushort * g_wszInstanceNameCopy
0x3838f6608  mov     rcx, cs:?g_pcsListenerList@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_pcsListenerList
0x3838f660f  test    rcx, rcx
0x3838f6612  jz      short loc_3838F6625
0x3838f6614  mov     rax, [rcx]
0x3838f6617  mov     edx, 1
0x3838f661c  call    qword ptr [rax]
0x3838f661e  mov     cs:?g_pcsListenerList@@3PEAVCCriticalSectionNT_SNI@@EA, rbp; CCriticalSectionNT_SNI * g_pcsListenerList
0x3838f6625  mov     rcx, cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x3838f662c  test    rcx, rcx
0x3838f662f  jz      short loc_3838F6642
0x3838f6631  mov     rax, [rcx]
0x3838f6634  mov     edx, 1
0x3838f6639  call    qword ptr [rax]
0x3838f663b  mov     cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA, rbp; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x3838f6642  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; hObject
0x3838f6649  test    rcx, rcx
0x3838f664c  jz      short loc_3838F665B
0x3838f664e  call    cs:__imp_CloseHandle
0x3838f6654  mov     cs:?ghIoCompletionPort@@3PEAXEA, rbp; void * ghIoCompletionPort
0x3838f665b  cmp     cs:?s_rgClientMemRegion@SNIMemRegion@@2PEAV1@EA, rbp; SNIMemRegion * SNIMemRegion::s_rgClientMemRegion
0x3838f6662  jz      short loc_3838F6670
0x3838f6664  call    ?Terminate@SNIMemRegion@@SAXPEAV1@@Z; SNIMemRegion::Terminate(SNIMemRegion *)
0x3838f6669  mov     cs:?s_rgClientMemRegion@SNIMemRegion@@2PEAV1@EA, rbp; SNIMemRegion * SNIMemRegion::s_rgClientMemRegion
0x3838f6670  call    ?Shutdown@LastConnectCache@@YAXXZ; LastConnectCache::Shutdown(void)
0x3838f6675  mov     cs:?g_NodeMask@@3_KA, rbp; unsigned __int64 g_NodeMask
0x3838f667c  lock dec cs:?gcSNIInitialized@@3JA; long gcSNIInitialized
0x3838f6683  jmp     loc_3838945D8
0x3838f6688  mov     rax, cs:off_383B461B8; "<SNIInitializeEx|RET|SNI> %d{WINERR}\n"
0x3838f668f  test    rax, rax
0x3838f6692  jz      loc_383894602
0x3838f6698  mov     r8, cs:off_383B461B8; "<SNIInitializeEx|RET|SNI> %d{WINERR}\n"
0x3838f669f  mov     rcx, cs:off_383B43B38; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f66a6  mov     r9d, ebx
0x3838f66a9  mov     edx, 16EC00h
0x3838f66ae  call    _bidTraceA
0x3838f66b3  nop
0x3838f66b4  jmp     loc_383894602
0x3838f66b9  test    byte ptr cs:_bidGblFlags, 4
0x3838f66c0  jz      loc_38389460E
0x3838f66c6  mov     rcx, cs:_bidID
0x3838f66cd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838f66d1  jz      loc_38389460E
0x3838f66d7  lea     r9, [rsp+58h+arg_10]
0x3838f66dc  xor     r8d, r8d
0x3838f66df  xor     edx, edx
0x3838f66e1  call    cs:off_383B15058
0x3838f66e7  nop
0x3838f66e8  jmp     loc_38389460E
0x3838f66ed  test    byte ptr cs:_bidGblFlags, 2
0x3838f66f4  jz      loc_3838F65D3
0x3838f66fa  mov     rcx, cs:off_383B461F8; "<SNIInitializeEx|ERR|SNI> Initialize g_"...
0x3838f6701  test    rcx, rcx
0x3838f6704  jz      short loc_3838F6721
0x3838f6706  mov     r8, cs:off_383B461F8; "<SNIInitializeEx|ERR|SNI> Initialize g_"...
0x3838f670d  mov     rcx, cs:off_383B43B78; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f6714  mov     r9d, eax
0x3838f6717  mov     edx, 141400h
0x3838f671c  call    _bidTraceA
0x3838f6721  test    byte ptr cs:_bidGblFlags, 2
0x3838f6728  jz      loc_3838F65D3
0x3838f672e  mov     rax, cs:off_383B461F0; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f6735  test    rax, rax
0x3838f6738  jz      loc_3838F65D3
0x3838f673e  mov     ecx, 0C3B4h; unsigned int
0x3838f6743  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f6748  mov     r8, cs:off_383B461F0; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f674f  mov     rcx, cs:off_383B43B70; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f6756  mov     edx, 141800h
0x3838f675b  jmp     loc_3838F65C0
0x3838f6760  call    cs:__imp_GetLastError
0x3838f6766  test    byte ptr cs:_bidGblFlags, 2
0x3838f676d  mov     ebx, eax
0x3838f676f  jz      loc_3838F65D3
0x3838f6775  mov     rax, cs:off_383B461E8; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f677c  test    rax, rax
0x3838f677f  jz      loc_3838F65D3
0x3838f6785  mov     ecx, 0C3B4h; unsigned int
0x3838f678a  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f678f  mov     r8, cs:off_383B461E8; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f6796  mov     rcx, cs:off_383B43B68; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f679d  mov     edx, 148C00h
0x3838f67a2  jmp     loc_3838F65C0
0x3838f67a7  call    cs:__imp_GetLastError
0x3838f67ad  test    byte ptr cs:_bidGblFlags, 2
0x3838f67b4  mov     ebx, eax
0x3838f67b6  jz      loc_3838F65D3
0x3838f67bc  mov     rax, cs:off_383B461E0; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f67c3  test    rax, rax
0x3838f67c6  jz      loc_3838F65D3
0x3838f67cc  mov     ecx, 0C3B4h; unsigned int
0x3838f67d1  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f67d6  mov     r8, cs:off_383B461E0; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f67dd  mov     rcx, cs:off_383B43B60; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f67e4  mov     edx, 14C400h
0x3838f67e9  jmp     loc_3838F65C0
0x3838f67ee  mov     rax, cs:off_383B461D8; "<SNIInitializeEx|SNI> Vista versions wh"...
0x3838f67f5  test    rax, rax
0x3838f67f8  jz      loc_38389454C
0x3838f67fe  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3838f6806  jz      loc_38389454C
0x3838f680c  mov     r9, cs:off_383B461D8; "<SNIInitializeEx|SNI> Vista versions wh"...
0x3838f6813  mov     rdx, cs:off_383B43B58; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f681a  mov     rcx, cs:_bidID
0x3838f6821  mov     r8d, 14E400h
0x3838f6827  mov     [rsp+58h+var_38], rbp
0x3838f682c  call    cs:off_383B15038
0x3838f6832  nop
0x3838f6833  jmp     loc_38389454C
0x3838f6838  test    byte ptr cs:_bidGblFlags, 2
0x3838f683f  jz      loc_3838F65D3
0x3838f6845  mov     rax, cs:off_383B461D0; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f684c  test    rax, rax
0x3838f684f  jz      loc_3838F65D3
0x3838f6855  mov     ecx, 0C3B4h; unsigned int
0x3838f685a  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f685f  mov     r8, cs:off_383B461D0; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f6866  mov     rcx, cs:off_383B43B50; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f686d  mov     edx, 150800h
0x3838f6872  jmp     loc_3838F65C0
0x3838f6877  call    cs:__imp_GetLastError
0x3838f687d  test    byte ptr cs:_bidGblFlags, 2
0x3838f6884  mov     ebx, eax
0x3838f6886  jz      loc_3838F65D3
0x3838f688c  mov     rax, cs:off_383B461C8; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f6893  test    rax, rax
0x3838f6896  jz      loc_3838F65D3
0x3838f689c  mov     ecx, 0C3B4h; unsigned int
0x3838f68a1  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f68a6  mov     r8, cs:off_383B461C8; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x3838f68ad  mov     rcx, cs:off_383B43B48; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f68b4  mov     edx, 155000h
0x3838f68b9  jmp     loc_3838F65C0
```

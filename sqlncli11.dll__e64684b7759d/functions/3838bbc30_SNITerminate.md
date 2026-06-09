# SNITerminate

- ea: `0x3838bbc30`
- end: `0x3838bbe90`
- name: `SNITerminate`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x3838be0c0`

## callees

- `0x383846430`
- `0x3838bbc30`
- `0x3838bbf90`
- `0x3838bc070`
- `0x3838bc210`
- `0x3838bc730`
- `0x3838bc9f0`
- `0x3838bca90`
- `0x3838bcc20`
- `0x3838bcce0`
- `0x3838bcd60`
- `0x3838bcf50`
- `0x3838be2fc`
- `0x38391ac00`
- `0x38391ac20`
- `0x38391ac40`
- `0x38391ae80`
- `0x383ab0a80`
- `0x383ab0c30`

## import_xrefs

- `KERNEL32!Sleep` at `0x3838f692a`
- `KERNEL32!Sleep` at `0x3838f692a`
- `KERNEL32!GetLastError` at `0x3838f6a4c`
- `KERNEL32!GetLastError` at `0x3838f6a4c`
- `KERNEL32!PostQueuedCompletionStatus` at `0x3838f69e3`
- `KERNEL32!PostQueuedCompletionStatus` at `0x3838f69e3`
- `KERNEL32!CloseHandle` at `0x3838bbd28`
- `KERNEL32!CloseHandle` at `0x3838bbd54`
- `KERNEL32!CloseHandle` at `0x3838bbd28`
- `KERNEL32!CloseHandle` at `0x3838bbd54`
- `KERNEL32!InterlockedPopEntrySList` at `0x3838bbd8d`
- `KERNEL32!InterlockedPopEntrySList` at `0x3838bbd8d`

## pseudocode

```c
__int64 SNITerminate()
{
  unsigned int v0; // ebx
  struct CCriticalSectionNT_SNI *v1; // r14
  LastConnectCache *v2; // rcx
  int i; // edi
  unsigned int v4; // edi
  unsigned int v5; // esi
  HANDLE *v6; // rdi
  BOOL v7; // eax
  struct SNIMemRegion *v8; // rbp
  unsigned int j; // edi
  PSLIST_ENTRY v10; // rax
  PSLIST_ENTRY v11; // rsi

  v0 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B485A8[0] && bidID != -1 )
    off_383B15048();
  v1 = g_csInitialize;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)g_csInitialize + 2) + 32LL) + 8LL))(*((_QWORD *)g_csInitialize
                                                                                                + 2) + 32LL);
  if ( !_InterlockedDecrement(&gcSNIInitialized) )
  {
    SNI_ServiceBindings::Release();
    if ( g_wszInstanceNameCopy )
    {
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
      g_wszInstanceNameCopy = 0;
    }
    for ( i = 0; i < 10; ++i )
    {
      if ( !gnConns )
        goto LABEL_7;
      Sleep(0x3E8u);
    }
    if ( !gnConns )
    {
LABEL_7:
      LastConnectCache::Shutdown(v2);
      LocalDB::Terminate();
      if ( g_csLocalDBInitialize )
      {
        (**(void (__fastcall ***)(struct CCriticalSectionNT_SNI *, __int64))g_csLocalDBInitialize)(
          g_csLocalDBInitialize,
          1);
        g_csLocalDBInitialize = 0;
      }
      Tcp::Terminate();
      Sm::Terminate();
      Np::Terminate();
      Sspi::Terminate();
      Ssl::Terminate();
      g_fTerminate = 1;
      PostQueuedCompletionStatus(ghIoCompletionPort, 0, 0, 0);
      if ( gnWorkerThreadCount )
      {
        v4 = ThreadHandle<SNIThreadHandleAllocator>::WaitForAllThreadsToExit(gnWorkerThreadCount);
        if ( v4 )
        {
          if ( (bidGblFlags & 2) != 0 && off_383B461A8[0] )
          {
            SniErrorIdFromStringId(0xC3B4u);
            bidTraceA(off_383B43B28[0], 1670144, off_383B461A8[0], 9);
          }
          SNISetLastError(9, v4, 50100);
        }
        v5 = 0;
        if ( gnWorkerThreadCount )
        {
          v6 = (HANDLE *)rghWorkerThreads;
          do
          {
            if ( *v6 )
            {
              v7 = CloseHandle(*v6);
              *v6 = 0;
              if ( !v7 )
                GetLastError();
            }
            ++v5;
            ++v6;
          }
          while ( v5 < gnWorkerThreadCount );
        }
        gnWorkerThreadCount = 0;
      }
      CloseHandle(ghIoCompletionPort);
      v8 = SNIMemRegion::s_rgClientMemRegion;
      ghIoCompletionPort = 0;
      if ( SNIMemRegion::s_rgClientMemRegion )
      {
        for ( j = 0; j < 7; ++j )
        {
          while ( 1 )
          {
            v10 = InterlockedPopEntrySList((PSLIST_HEADER)v8 + 2 * j + 1);
            if ( !v10 )
              break;
            v11 = v10 - 5;
            if ( v10 == (PSLIST_ENTRY)80 )
              break;
            SNI_Packet::~SNI_Packet((SNI_Packet *)&v10[-5]);
            ((void (__fastcall *)(struct IMalloc *, PSLIST_ENTRY))g_pMO->lpVtbl[1].Realloc)(g_pMO, v11);
          }
        }
        if ( v8 )
        {
          `eh vector destructor iterator'(v8, 0x20u, *((_DWORD *)v8 - 4), (void (*)(void *))SNIMemRegion::~SNIMemRegion);
          if ( v8 != (struct SNIMemRegion *)16 )
            ((void (__fastcall *)(struct IMalloc *, char *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, (char *)v8 - 16);
        }
        SNIMemRegion::s_rgClientMemRegion = 0;
      }
      else if ( (bidGblFlags & 2) != 0 && off_383B461A0[0] && bidID != -1 )
      {
        off_383B15038();
      }
      g_NodeMask = 0;
      if ( g_pcsListenerList )
      {
        (**(void (__fastcall ***)(struct CCriticalSectionNT_SNI *, __int64))g_pcsListenerList)(g_pcsListenerList, 1);
        g_pcsListenerList = 0;
      }
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46198[0] )
        bidTraceA(off_383B43B18[0], 1707008, off_383B46198[0], 0);
      goto LABEL_31;
    }
    _InterlockedIncrement(&gcSNIInitialized);
    scierrlog((unsigned int)v2);
    v0 = 5023;
    if ( (bidGblFlags & 2) != 0 && off_383B461B0[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceA(off_383B43B30[0], 1632256, off_383B461B0[0], 9);
    }
    SNISetLastError(9, 5023, 50100);
  }
LABEL_31:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v1 + 2) + 32LL) + 24LL))(*((_QWORD *)v1 + 2) + 32LL);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46190[0] )
    bidTraceA(off_383B43B10[0], 1715200, off_383B46190[0], v0);
  return v0;
}

```

## disassembly

```asm
0x3838bbc30  push    rbx
0x3838bbc32  sub     rsp, 40h
0x3838bbc36  mov     eax, cs:_bidGblFlags
0x3838bbc3c  mov     [rsp+48h+var_10], rdi
0x3838bbc41  or      rdi, 0FFFFFFFFFFFFFFFFh
0x3838bbc45  and     eax, 20004h
0x3838bbc4a  xor     ebx, ebx
0x3838bbc4c  mov     [rsp+48h+var_18], r14
0x3838bbc51  mov     [rsp+48h+arg_0], rdi
0x3838bbc56  cmp     eax, 20004h
0x3838bbc5b  jz      loc_3838F68BE
0x3838bbc61  mov     r14, cs:?g_csInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csInitialize
0x3838bbc68  mov     rcx, [r14+10h]
0x3838bbc6c  mov     rax, [rcx+20h]
0x3838bbc70  add     rcx, 20h ; ' '
0x3838bbc74  call    qword ptr [rax+8]
0x3838bbc77  lock dec cs:?gcSNIInitialized@@3JA; long gcSNIInitialized
0x3838bbc7e  jnz     loc_3838BBE48
0x3838bbc84  call    ?Release@SNI_ServiceBindings@@SAXXZ; SNI_ServiceBindings::Release(void)
0x3838bbc89  mov     rdx, cs:?g_wszInstanceNameCopy@@3PEAGEA; ushort * g_wszInstanceNameCopy
0x3838bbc90  test    rdx, rdx
0x3838bbc93  jnz     loc_3838F6909
0x3838bbc99  mov     edi, ebx
0x3838bbc9b  nop     dword ptr [rax+rax+00h]
0x3838bbca0  cmp     cs:?gnConns@@3JA, ebx; long gnConns
0x3838bbca6  jz      short loc_3838BBCAD
0x3838bbca8  jmp     loc_3838F6925
0x3838bbcad  mov     [rsp+48h+arg_8], rbp
0x3838bbcb2  call    ?Shutdown@LastConnectCache@@YAXXZ; LastConnectCache::Shutdown(void)
0x3838bbcb7  call    ?Terminate@LocalDB@@SAXXZ; LocalDB::Terminate(void)
0x3838bbcbc  mov     rcx, cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x3838bbcc3  test    rcx, rcx
0x3838bbcc6  jz      short loc_3838BBCD9
0x3838bbcc8  mov     rax, [rcx]
0x3838bbccb  mov     edx, 1
0x3838bbcd0  call    qword ptr [rax]
0x3838bbcd2  mov     cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA, rbx; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x3838bbcd9  mov     [rsp+48h+arg_10], rsi
0x3838bbcde  jmp     loc_3838F69B4
0x3838bbce3  mov     r11d, cs:?gnWorkerThreadCount@@3KA; ulong gnWorkerThreadCount
0x3838bbcea  test    r11d, r11d
0x3838bbced  jz      short loc_3838BBD4D
0x3838bbcef  mov     ecx, r11d
0x3838bbcf2  call    ?WaitForAllThreadsToExit@?$ThreadHandle@USNIThreadHandleAllocator@@@@SAK_KPEAV1@PEAK@Z; ThreadHandle<SNIThreadHandleAllocator>::WaitForAllThreadsToExit(unsigned __int64,ThreadHandle<SNIThreadHandleAllocator> *,ulong *)
0x3838bbcf7  mov     edi, eax
0x3838bbcf9  test    eax, eax
0x3838bbcfb  jnz     loc_3838F69EF
0x3838bbd01  cmp     cs:?gnWorkerThreadCount@@3KA, ebx; ulong gnWorkerThreadCount
0x3838bbd07  mov     esi, ebx
0x3838bbd09  jbe     short loc_3838BBD47
0x3838bbd0b  lea     rdi, ?rghWorkerThreads@@3PAV?$ThreadHandle@USNIThreadHandleAllocator@@@@A; ThreadHandle<SNIThreadHandleAllocator> near * rghWorkerThreads
0x3838bbd12  nop     dword ptr [rax+00000000h]
0x3838bbd19  nop     dword ptr [rax+00000000h]
0x3838bbd20  mov     rcx, [rdi]; hObject
0x3838bbd23  test    rcx, rcx
0x3838bbd26  jz      short loc_3838BBD39
0x3838bbd28  call    cs:__imp_CloseHandle
0x3838bbd2e  mov     [rdi], rbx
0x3838bbd31  test    eax, eax
0x3838bbd33  jz      loc_3838F6A4C
0x3838bbd39  inc     esi
0x3838bbd3b  add     rdi, 8
0x3838bbd3f  cmp     esi, cs:?gnWorkerThreadCount@@3KA; ulong gnWorkerThreadCount
0x3838bbd45  jb      short loc_3838BBD20
0x3838bbd47  mov     cs:?gnWorkerThreadCount@@3KA, ebx; ulong gnWorkerThreadCount
0x3838bbd4d  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; hObject
0x3838bbd54  call    cs:__imp_CloseHandle
0x3838bbd5a  mov     rbp, cs:?s_rgClientMemRegion@SNIMemRegion@@2PEAV1@EA; SNIMemRegion * SNIMemRegion::s_rgClientMemRegion
0x3838bbd61  mov     cs:?ghIoCompletionPort@@3PEAXEA, rbx; void * ghIoCompletionPort
0x3838bbd68  test    rbp, rbp
0x3838bbd6b  jz      loc_3838F6A58
0x3838bbd71  mov     edi, ebx
0x3838bbd73  nop     dword ptr [rax+00000000h]
0x3838bbd7a  nop     word ptr [rax+rax+00h]
0x3838bbd80  mov     eax, edi
0x3838bbd82  lea     rcx, [rbp+10h]
0x3838bbd86  shl     rax, 5
0x3838bbd8a  add     rcx, rax; ListHead
0x3838bbd8d  call    cs:__imp_InterlockedPopEntrySList
0x3838bbd93  test    rax, rax
0x3838bbd96  jz      short loc_3838BBDBB
0x3838bbd98  lea     rsi, [rax-50h]
0x3838bbd9c  test    rsi, rsi
0x3838bbd9f  jz      short loc_3838BBDBB
0x3838bbda1  mov     rcx, rsi; this
0x3838bbda4  call    ??1SNI_Packet@@AEAA@XZ; SNI_Packet::~SNI_Packet(void)
0x3838bbda9  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838bbdb0  mov     rdx, rsi
0x3838bbdb3  mov     rax, [rcx]
0x3838bbdb6  call    qword ptr [rax+68h]
0x3838bbdb9  jmp     short loc_3838BBD80
0x3838bbdbb  inc     edi
0x3838bbdbd  cmp     edi, 7
0x3838bbdc0  jb      short loc_3838BBD80
0x3838bbdc2  test    rbp, rbp
0x3838bbdc5  jz      short loc_3838BBDFB
0x3838bbdc7  mov     r8d, [rbp-10h]; int
0x3838bbdcb  lea     rdi, [rbp-10h]
0x3838bbdcf  lea     r9, ??1SNIMemRegion@@QEAA@XZ; void (*)(void *)
0x3838bbdd6  mov     edx, 20h ; ' '; unsigned __int64
0x3838bbddb  mov     rcx, rbp; void *
0x3838bbdde  call    ??_M@YAXPEAX_KHP6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,int,void (*)(void *))
0x3838bbde3  test    rdi, rdi
0x3838bbde6  jz      short loc_3838BBDFB
0x3838bbde8  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838bbdef  mov     rdx, rdi
0x3838bbdf2  mov     rax, [rcx]
0x3838bbdf5  call    qword ptr [rax+80h]
0x3838bbdfb  mov     cs:?s_rgClientMemRegion@SNIMemRegion@@2PEAV1@EA, rbx; SNIMemRegion * SNIMemRegion::s_rgClientMemRegion
0x3838bbe02  jmp     short $+2
0x3838bbe04  mov     rcx, cs:?g_pcsListenerList@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_pcsListenerList
0x3838bbe0b  mov     rsi, [rsp+48h+arg_10]
0x3838bbe10  mov     rbp, [rsp+48h+arg_8]
0x3838bbe15  mov     cs:?g_NodeMask@@3_KA, rbx; unsigned __int64 g_NodeMask
0x3838bbe1c  test    rcx, rcx
0x3838bbe1f  jz      short loc_3838BBE32
0x3838bbe21  mov     rax, [rcx]
0x3838bbe24  mov     edx, 1
0x3838bbe29  call    qword ptr [rax]
0x3838bbe2b  mov     cs:?g_pcsListenerList@@3PEAVCCriticalSectionNT_SNI@@EA, rbx; CCriticalSectionNT_SNI * g_pcsListenerList
0x3838bbe32  mov     eax, cs:_bidGblFlags
0x3838bbe38  and     eax, 20002h
0x3838bbe3d  cmp     eax, 20002h
0x3838bbe42  jz      loc_3838F6AAF
0x3838bbe48  mov     rcx, [r14+10h]
0x3838bbe4c  mov     rax, [rcx+20h]
0x3838bbe50  add     rcx, 20h ; ' '
0x3838bbe54  call    qword ptr [rax+18h]
0x3838bbe57  mov     r11d, cs:_bidGblFlags
0x3838bbe5e  mov     r14, [rsp+48h+var_18]
0x3838bbe63  mov     rdi, [rsp+48h+var_10]
0x3838bbe68  and     r11d, 20002h
0x3838bbe6f  cmp     r11d, 20002h
0x3838bbe76  jz      loc_3838F6AE0
0x3838bbe7c  cmp     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x3838bbe82  jnz     loc_3838F6B11
0x3838bbe88  mov     eax, ebx
0x3838bbe8a  add     rsp, 40h
0x3838bbe8e  pop     rbx
0x3838bbe8f  retn
0x3838f68be  mov     rax, cs:off_383B485A8; "<SNITerminate|API|SNI> \n"
0x3838f68c5  test    rax, rax
0x3838f68c8  jz      loc_3838BBC61
0x3838f68ce  cmp     cs:_bidID, rdi
0x3838f68d5  jz      loc_3838BBC61
0x3838f68db  mov     rax, cs:off_383B485A8; "<SNITerminate|API|SNI> \n"
0x3838f68e2  mov     rcx, cs:_bidID
0x3838f68e9  lea     r9, [rsp+48h+arg_0]
0x3838f68ee  xor     r8d, r8d
0x3838f68f1  xor     edx, edx
0x3838f68f3  mov     [rsp+48h+var_20], rbx
0x3838f68f8  mov     [rsp+48h+var_28], rax
0x3838f68fd  call    cs:off_383B15048
0x3838f6903  nop
0x3838f6904  jmp     loc_3838BBC61
0x3838f6909  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838f6910  mov     rax, [rcx]
0x3838f6913  call    qword ptr [rax+80h]
0x3838f6919  mov     cs:?g_wszInstanceNameCopy@@3PEAGEA, rbx; ushort * g_wszInstanceNameCopy
0x3838f6920  jmp     loc_3838BBC99
0x3838f6925  mov     ecx, 3E8h; dwMilliseconds
0x3838f692a  call    cs:__imp_Sleep
0x3838f6930  inc     edi
0x3838f6932  cmp     edi, 0Ah
0x3838f6935  jl      loc_3838BBCA0
0x3838f693b  cmp     cs:?gnConns@@3JA, ebx; long gnConns
0x3838f6941  jz      loc_3838BBCAD
0x3838f6947  lock inc cs:?gcSNIInitialized@@3JA; long gcSNIInitialized
0x3838f694e  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x3838f6953  test    byte ptr cs:_bidGblFlags, 2
0x3838f695a  mov     ebx, 139Fh
0x3838f695f  jz      short loc_3838F699D
0x3838f6961  mov     rax, cs:off_383B461B0; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x3838f6968  test    rax, rax
0x3838f696b  jz      short loc_3838F699D
0x3838f696d  mov     ecx, 0C3B4h; unsigned int
0x3838f6972  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f6977  mov     r8, cs:off_383B461B0; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x3838f697e  mov     rcx, cs:off_383B43B30; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f6985  mov     r9d, 9
0x3838f698b  mov     edx, 18E800h
0x3838f6990  mov     dword ptr [rsp+48h+var_20], ebx
0x3838f6994  mov     dword ptr [rsp+48h+var_28], eax
0x3838f6998  call    _bidTraceA
0x3838f699d  mov     edx, ebx
0x3838f699f  mov     ecx, 9
0x3838f69a4  mov     r8d, 0C3B4h
0x3838f69aa  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838f69af  jmp     loc_3838BBE48
0x3838f69b4  call    ?Terminate@Tcp@@SAKXZ; Tcp::Terminate(void)
0x3838f69b9  call    ?Terminate@Sm@@SAKXZ; Sm::Terminate(void)
0x3838f69be  call    ?Terminate@Np@@SAKXZ; Np::Terminate(void)
0x3838f69c3  call    ?Terminate@Sspi@@SAKXZ; Sspi::Terminate(void)
0x3838f69c8  call    ?Terminate@Ssl@@SAKXZ; Ssl::Terminate(void)
0x3838f69cd  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; CompletionPort
0x3838f69d4  xor     r9d, r9d; lpOverlapped
0x3838f69d7  xor     r8d, r8d; dwCompletionKey
0x3838f69da  xor     edx, edx; dwNumberOfBytesTransferred
0x3838f69dc  mov     cs:?g_fTerminate@@3_NA, 1; bool g_fTerminate
0x3838f69e3  call    cs:__imp_PostQueuedCompletionStatus
0x3838f69e9  nop
0x3838f69ea  jmp     loc_3838BBCE3
0x3838f69ef  test    byte ptr cs:_bidGblFlags, 2
0x3838f69f6  jz      short loc_3838F6A34
0x3838f69f8  mov     rax, cs:off_383B461A8; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x3838f69ff  test    rax, rax
0x3838f6a02  jz      short loc_3838F6A34
0x3838f6a04  mov     ecx, 0C3B4h; unsigned int
0x3838f6a09  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f6a0e  mov     r8, cs:off_383B461A8; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x3838f6a15  mov     rcx, cs:off_383B43B28; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f6a1c  mov     r9d, 9
0x3838f6a22  mov     edx, 197C00h
0x3838f6a27  mov     dword ptr [rsp+48h+var_20], edi
0x3838f6a2b  mov     dword ptr [rsp+48h+var_28], eax
0x3838f6a2f  call    _bidTraceA
0x3838f6a34  mov     r8d, 0C3B4h
0x3838f6a3a  mov     edx, edi
0x3838f6a3c  mov     ecx, 9
0x3838f6a41  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838f6a46  nop
0x3838f6a47  jmp     loc_3838BBD01
0x3838f6a4c  call    cs:__imp_GetLastError
0x3838f6a52  nop
0x3838f6a53  jmp     loc_3838BBD39
0x3838f6a58  test    byte ptr cs:_bidGblFlags, 2
0x3838f6a5f  jz      loc_3838BBE04
0x3838f6a65  mov     rax, cs:off_383B461A0; "<SNITerminate|ERR|SNI> SNIMemRegion::s_"...
0x3838f6a6c  test    rax, rax
0x3838f6a6f  jz      loc_3838BBE04
0x3838f6a75  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3838f6a7d  jz      loc_3838BBE04
0x3838f6a83  mov     r9, cs:off_383B461A0; "<SNITerminate|ERR|SNI> SNIMemRegion::s_"...
0x3838f6a8a  mov     rdx, cs:off_383B43B20; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f6a91  mov     rcx, cs:_bidID
0x3838f6a98  mov     r8d, 19D800h
0x3838f6a9e  mov     [rsp+48h+var_28], rbx
0x3838f6aa3  call    cs:off_383B15038
0x3838f6aa9  nop
0x3838f6aaa  jmp     loc_3838BBE04
0x3838f6aaf  mov     rax, cs:off_383B46198; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x3838f6ab6  test    rax, rax
0x3838f6ab9  jz      loc_3838BBE48
0x3838f6abf  mov     r8, cs:off_383B46198; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x3838f6ac6  mov     rcx, cs:off_383B43B18; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f6acd  xor     r9d, r9d
0x3838f6ad0  mov     edx, 1A0C00h
0x3838f6ad5  call    _bidTraceA
0x3838f6ada  nop
0x3838f6adb  jmp     loc_3838BBE48
0x3838f6ae0  mov     rax, cs:off_383B46190; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x3838f6ae7  test    rax, rax
0x3838f6aea  jz      loc_3838BBE7C
0x3838f6af0  mov     r8, cs:off_383B46190; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x3838f6af7  mov     rcx, cs:off_383B43B10; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f6afe  mov     r9d, ebx
0x3838f6b01  mov     edx, 1A2C00h
0x3838f6b06  call    _bidTraceA
0x3838f6b0b  nop
0x3838f6b0c  jmp     loc_3838BBE7C
0x3838f6b11  test    byte ptr cs:_bidGblFlags, 4
0x3838f6b18  jz      loc_3838BBE88
0x3838f6b1e  mov     rcx, cs:_bidID
0x3838f6b25  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838f6b29  jz      loc_3838BBE88
0x3838f6b2f  lea     r9, [rsp+48h+arg_0]
0x3838f6b34  xor     r8d, r8d
0x3838f6b37  xor     edx, edx
0x3838f6b39  call    cs:off_383B15058
0x3838f6b3f  nop
0x3838f6b40  jmp     loc_3838BBE88
```

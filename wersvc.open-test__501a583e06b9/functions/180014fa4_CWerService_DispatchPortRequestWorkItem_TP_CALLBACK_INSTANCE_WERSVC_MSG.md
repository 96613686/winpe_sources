# CWerService::DispatchPortRequestWorkItem(_TP_CALLBACK_INSTANCE *,_WERSVC_MSG *)

- ea: `0x180014fa4`
- end: `0x1800154dd`
- name: `?DispatchPortRequestWorkItem@CWerService@@AEAAJPEAU_TP_CALLBACK_INSTANCE@@PEAU_WERSVC_MSG@@@Z`
- size: `1337`
- prototype: `__int64 __fastcall(CWerService *__hidden this, PTP_CALLBACK_INSTANCE pci, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180018880`

## callees

- `0x1800029d0`
- `0x180011ef8`
- `0x180011f38`
- `0x180013df4`
- `0x180014c54`
- `0x180014fa4`
- `0x180017578`
- `0x180018af8`
- `0x180018c5c`
- `0x180018e90`
- `0x180019004`
- `0x180019178`
- `0x18001924c`
- `0x18001938c`
- `0x180019578`
- `0x18001965c`
- `0x180019728`
- `0x180019b34`
- `0x180019c08`
- `0x180019d10`
- `0x180019ef4`
- `0x180019fc8`
- `0x18001a324`
- `0x18001a410`
- `0x18001a4cc`
- `0x18001a5a0`
- `0x180020dc4`
- `0x180021fc0`
- `0x18002c778`
- `0x180034550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015447`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015447`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001503c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001503c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015061`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015061`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015071`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015377`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015377`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x1800154b3`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x1800154b3`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800154a0`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800154a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWerService::DispatchPortRequestWorkItem(
        CWerService *this,
        PTP_CALLBACK_INSTANCE pci,
        struct _WERSVC_MSG *a3)
{
  LSTATUS v6; // ebx
  HKEY v7; // rdx
  int v8; // eax
  int inited; // ebx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  int Lock; // eax
  int v17; // ecx
  __int64 v18; // rcx
  char *v19; // r8
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+48h] [rbp-B8h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY *p_hKey; // [rsp+58h] [rbp-A8h]
  _BYTE v25[40]; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+98h] [rbp-68h]
  int v27; // [rsp+9Ch] [rbp-64h]
  char v28; // [rsp+A0h] [rbp-60h] BYREF
  int v29; // [rsp+CCh] [rbp-34h]

  CWerService::CheckIfValidPortMessage(this, a3);
  memcpy_0(v25, a3, 0x578u);
  v26 = 1;
  v27 = -1073741823;
  phkResult = 0;
  p_hKey = &hKey;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &phkResult);
  if ( phkResult )
  {
    v7 = *p_hKey;
    *p_hKey = phkResult;
    if ( v7 )
      RegCloseKey(v7);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 && (*((_QWORD *)this + 44) == -1 || *((_QWORD *)this + 44) == 0) )
  {
    v8 = ((__int64 (*)(void))InitReportStore)();
    inited = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          103,
          WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
          (unsigned int)v8);
      goto LABEL_72;
    }
    if ( v8 )
      goto LABEL_72;
  }
  v10 = *((_DWORD *)a3 + 10);
  if ( v10 <= 0xC0000002 )
  {
    if ( v10 == -1073741822 )
    {
      Lock = CWerService::SvcReportStoreGetLock(this, a3, (struct _WERSVC_MSG *)v25);
    }
    else if ( v10 > 0x30000000 )
    {
      switch ( v10 )
      {
        case 0x50000000u:
          v26 = 1;
          v27 = -1073741823;
          inited = -2147467259;
          goto LABEL_72;
        case 0x60000000u:
          v17 = *((_DWORD *)a3 + 12);
          if ( !v17 || (inited = -2147024809, v17 == 1) )
          {
            *((_WORD *)a3 + 43) = 0;
            *((_WORD *)a3 + 83) = 0;
            inited = LiveKernelReport((const wchar_t *)a3 + 28, (const wchar_t *)a3 + 44, v17 != 0);
          }
          goto LABEL_26;
        case 0x80000000:
          Lock = CWerService::SvcLookupHKCUForIFEO(this, a3, (struct _WERSVC_MSG *)v25);
          break;
        case 0x90000000:
          Lock = CWerService::SvcNonElevatedLaunch(this, a3, (struct _WERSVC_MSG *)v25);
          break;
        case 0xB0000000:
          Lock = CWerService::SvcProcessReflectionRequest(this, a3, (struct _WERSVC_MSG *)v25);
          break;
        default:
          goto LABEL_65;
      }
    }
    else if ( v10 == 805306368 )
    {
      Lock = CWerService::SvcReportSilentProcessExit(this, a3, (struct _WERSVC_MSG *)v25);
    }
    else
    {
      v11 = v10 - 0x10000000;
      if ( v11 )
      {
        v12 = v11 - 6;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 268435449;
            if ( v14 )
            {
              v15 = v14 - 1;
              if ( v15 )
              {
                if ( v15 == 4 )
                {
                  v29 = 0;
                  if ( *((__int16 *)a3 + 2) >= 0 )
                    inited = -2147418113;
                  else
                    inited = InitTrustletDumpSupport(*((unsigned int *)a3 + 2)) | 0x10000000;
LABEL_26:
                  v27 = inited;
                  goto LABEL_72;
                }
LABEL_65:
                inited = -2147024809;
                goto LABEL_72;
              }
              Lock = CWerService::SvcReportCrashKernelMsg(this, a3, (struct _WERSVC_MSG *)v25);
            }
            else
            {
              Lock = CWerService::SvcReportCrash(this, a3, (struct _WERSVC_MSG *)v25);
            }
          }
          else
          {
            Lock = CWerService::RestoreHungThread(this, a3);
            v26 = 268435463;
            v27 = Lock;
          }
        }
        else
        {
          Lock = CWerService::SvcReportHangCancel(this, a3, (struct _WERSVC_MSG *)v25);
        }
      }
      else
      {
        Lock = CWerService::SvcReportHang(this, a3, (struct _WERSVC_MSG *)v25);
      }
    }
LABEL_71:
    inited = Lock;
    goto LABEL_72;
  }
  if ( v10 > 0xF0010002 )
  {
    switch ( v10 )
    {
      case 0xF0020002:
        Lock = CWerService::SvcMergeETWLogs((CWerService *)0xF0010002LL, a3, (struct _WERSVC_MSG *)v25);
        break;
      case 0xF0030002:
        Lock = CWerService::SvcCollectMemoryInfo((CWerService *)0xF0010002LL, a3, (struct _WERSVC_MSG *)v25);
        break;
      case 0xF0040002:
        Lock = CWerService::SvcCollectSystemInfo((CWerService *)0xF0010002LL, a3, (struct _WERSVC_MSG *)v25);
        break;
      case 0xF0050002:
        Lock = CWerService::SvcGetTerminationReason((CWerService *)0xF0010002LL, a3, (struct _WERSVC_MSG *)v25);
        break;
      case 0xF0060002:
        Lock = CWerService::SvcAddTerminationReason((CWerService *)0xF0010002LL, a3, (struct _WERSVC_MSG *)v25);
        break;
      default:
        goto LABEL_65;
    }
    goto LABEL_71;
  }
  if ( v10 == -268369918 )
  {
    Lock = CWerService::SvcCollectETWLogs(this, a3, (struct _WERSVC_MSG *)v25);
    goto LABEL_71;
  }
  if ( v10 != -1073741821 )
  {
    switch ( v10 )
    {
      case 0xC0000004:
        Lock = CWerService::SvcReportStorePruneUserStore((CWerService *)0xF0010002LL, a3, (struct _WERSVC_MSG *)v25);
        break;
      case 0xD0000002:
        Lock = CWerService::SvcElevatedDataCollectorCreate(this, a3, (struct _WERSVC_MSG *)v25);
        break;
      case 0xE0000002:
        Lock = CWerService::SvcGenericReportCreate(this, a3, (struct _WERSVC_MSG *)v25);
        break;
      case 0xF0000002:
        Lock = CWerService::SvcMachineIdCreate(this, a3, (struct _WERSVC_MSG *)v25);
        break;
      default:
        goto LABEL_65;
    }
    goto LABEL_71;
  }
  hKey = 0;
  inited = InitReportStore(&hKey);
  v27 = inited;
  v26 = (inited < 0) - 0x40000000;
  if ( (unsigned __int64)hKey + 1 > 1 )
    CloseHandle(hKey);
LABEL_72:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      104,
      WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
      *((unsigned int *)a3 + 10),
      inited);
  hKey = (HKEY)this;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v22 = 1;
  v18 = *((_QWORD *)this + 49);
  if ( !v18 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v18 = *((_QWORD *)this + 49);
  }
  v19 = v25;
  if ( ((*((_DWORD *)a3 + 10) - 536870913) & 0xFFFFFFFB) == 0 )
    v19 = &v28;
  NtAlpcSendWaitReceivePort(v18, 0x10000, v19, 0, 0, 0, 0, 0);
  _InterlockedDecrement((volatile signed __int32 *)this + 52);
  LeaveCriticalSectionWhenCallbackReturns(pci, (PCRITICAL_SECTION)this);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180014fa4  push    rbp
0x180014fa6  push    rbx
0x180014fa7  push    rsi
0x180014fa8  push    rdi
0x180014fa9  push    r13
0x180014fab  push    r14
0x180014fad  push    r15
0x180014faf  lea     rbp, [rsp-500h]
0x180014fb7  sub     rsp, 600h
0x180014fbe  mov     rax, cs:__security_cookie
0x180014fc5  xor     rax, rsp
0x180014fc8  mov     [rbp+530h+var_40], rax
0x180014fcf  mov     rdi, r8
0x180014fd2  mov     r14, rdx
0x180014fd5  mov     rsi, rcx
0x180014fd8  mov     rdx, r8; struct _WERSVC_MSG *
0x180014fdb  call    ?CheckIfValidPortMessage@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z; CWerService::CheckIfValidPortMessage(_WERSVC_MSG *)
0x180014fe0  lea     rcx, [rsp+630h+var_5C0]; void *
0x180014fe5  mov     rdx, rdi; Src
0x180014fe8  mov     r8d, 578h; Size
0x180014fee  call    memcpy_0
0x180014ff3  mov     [rbp+530h+var_598], 1
0x180014ffa  mov     r13d, 0C0000001h
0x180015000  mov     [rbp+530h+var_594], r13d
0x180015004  xor     r15d, r15d
0x180015007  mov     [rsp+630h+var_5E0], r15
0x18001500c  lea     rax, [rsp+630h+hKey]
0x180015011  mov     [rsp+630h+var_5D8], rax
0x180015016  mov     [rsp+630h+hKey], r15
0x18001501b  lea     rax, [rsp+630h+var_5E0]
0x180015020  mov     [rsp+630h+phkResult], rax; phkResult
0x180015025  mov     r9d, 20019h; samDesired
0x18001502b  xor     r8d, r8d; ulOptions
0x18001502e  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180015035  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001503c  call    cs:__imp_RegOpenKeyExW
0x180015042  mov     ebx, eax
0x180015044  mov     r8, [rsp+630h+var_5E0]
0x180015049  test    r8, r8
0x18001504c  jz      short loc_180015067
0x18001504e  mov     rcx, [rsp+630h+var_5D8]
0x180015053  mov     rdx, [rcx]
0x180015056  mov     [rcx], r8
0x180015059  test    rdx, rdx
0x18001505c  jz      short loc_180015067
0x18001505e  mov     rcx, rdx; hKey
0x180015061  call    cs:__imp_RegCloseKey
0x180015067  mov     rcx, [rsp+630h+hKey]; hKey
0x18001506c  test    rcx, rcx
0x18001506f  jz      short loc_180015077
0x180015071  call    cs:__imp_RegCloseKey
0x180015077  test    ebx, ebx
0x180015079  jz      short loc_1800150DD
0x18001507b  lea     rcx, [rsi+160h]
0x180015082  mov     rax, [rcx]
0x180015085  inc     rax
0x180015088  cmp     rax, 1
0x18001508c  ja      short loc_1800150DD
0x18001508e  call    ?InitReportStore@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; InitReportStore(tlx::unique_any<tlx::file_handle_traits> *)
0x180015093  mov     ebx, eax
0x180015095  test    eax, eax
0x180015097  jns     short loc_1800150D7
0x180015099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150a0  lea     r13, WPP_GLOBAL_Control
0x1800150a7  cmp     rcx, r13
0x1800150aa  jz      loc_180015410
0x1800150b0  test    byte ptr [rcx+1Ch], 1
0x1800150b4  jz      loc_180015410
0x1800150ba  mov     edx, 67h ; 'g'
0x1800150bf  mov     r9d, eax
0x1800150c2  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800150c9  mov     rcx, [rcx+10h]
0x1800150cd  call    WPP_SF_d
0x1800150d2  jmp     loc_180015410
0x1800150d7  jnz     loc_180015409
0x1800150dd  mov     eax, [rdi+28h]
0x1800150e0  mov     ecx, 0C0000002h
0x1800150e5  cmp     eax, ecx
0x1800150e7  ja      loc_1800152B5
0x1800150ed  jz      loc_1800152A0
0x1800150f3  mov     ecx, 30000000h
0x1800150f8  cmp     eax, ecx
0x1800150fa  ja      loc_1800151E2
0x180015100  jz      loc_1800151CD
0x180015106  mov     r13d, 10000000h
0x18001510c  sub     eax, r13d
0x18001510f  jz      loc_1800151B8
0x180015115  sub     eax, 6
0x180015118  jz      loc_1800151A3
0x18001511e  sub     eax, 1
0x180015121  jz      short loc_180015189
0x180015123  sub     eax, 0FFFFFF9h
0x180015128  jz      short loc_180015174
0x18001512a  sub     eax, 1
0x18001512d  jz      short loc_18001515F
0x18001512f  cmp     eax, 4
0x180015132  jnz     loc_1800153B7
0x180015138  mov     [rbp+530h+var_564], r15d
0x18001513c  cmp     [rdi+4], r15w
0x180015141  jge     short loc_180015152
0x180015143  mov     ecx, [rdi+8]
0x180015146  call    InitTrustletDumpSupport
0x18001514b  mov     ebx, eax
0x18001514d  or      ebx, r13d
0x180015150  jmp     short loc_180015157
0x180015152  mov     ebx, 8000FFFFh
0x180015157  mov     [rbp+530h+var_594], ebx
0x18001515a  jmp     loc_180015409
0x18001515f  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x180015164  mov     rdx, rdi; struct _WERSVC_MSG *
0x180015167  mov     rcx, rsi; this
0x18001516a  call    ?SvcReportCrashKernelMsg@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcReportCrashKernelMsg(_WERSVC_MSG *,_WERSVC_MSG *)
0x18001516f  jmp     loc_180015407
0x180015174  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x180015179  mov     rdx, rdi; struct _WERSVC_MSG *
0x18001517c  mov     rcx, rsi; this
0x18001517f  call    ?SvcReportCrash@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcReportCrash(_WERSVC_MSG *,_WERSVC_MSG *)
0x180015184  jmp     loc_180015407
0x180015189  mov     rdx, rdi; struct _WERSVC_MSG *
0x18001518c  mov     rcx, rsi; this
0x18001518f  call    ?RestoreHungThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z; CWerService::RestoreHungThread(_WERSVC_MSG *)
0x180015194  mov     [rbp+530h+var_598], 10000007h
0x18001519b  mov     [rbp+530h+var_594], eax
0x18001519e  jmp     loc_180015407
0x1800151a3  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x1800151a8  mov     rdx, rdi; struct _WERSVC_MSG *
0x1800151ab  mov     rcx, rsi; this
0x1800151ae  call    ?SvcReportHangCancel@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcReportHangCancel(_WERSVC_MSG *,_WERSVC_MSG *)
0x1800151b3  jmp     loc_180015407
0x1800151b8  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x1800151bd  mov     rdx, rdi; struct _WERSVC_MSG *
0x1800151c0  mov     rcx, rsi; this
0x1800151c3  call    ?SvcReportHang@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcReportHang(_WERSVC_MSG *,_WERSVC_MSG *)
0x1800151c8  jmp     loc_180015407
0x1800151cd  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x1800151d2  mov     rdx, rdi; struct _WERSVC_MSG *
0x1800151d5  mov     rcx, rsi; this
0x1800151d8  call    ?SvcReportSilentProcessExit@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcReportSilentProcessExit(_WERSVC_MSG *,_WERSVC_MSG *)
0x1800151dd  jmp     loc_180015407
0x1800151e2  cmp     eax, 50000000h
0x1800151e7  jz      loc_18001528B
0x1800151ed  cmp     eax, 60000000h
0x1800151f2  jz      short loc_18001524C
0x1800151f4  cmp     eax, 80000000h
0x1800151f9  jz      short loc_180015237
0x1800151fb  cmp     eax, 90000000h
0x180015200  jz      short loc_180015222
0x180015202  cmp     eax, 0B0000000h
0x180015207  jnz     loc_1800153B7
0x18001520d  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x180015212  mov     rdx, rdi; struct _WERSVC_MSG *
0x180015215  mov     rcx, rsi; this
0x180015218  call    ?SvcProcessReflectionRequest@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcProcessReflectionRequest(_WERSVC_MSG *,_WERSVC_MSG *)
0x18001521d  jmp     loc_180015407
0x180015222  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x180015227  mov     rdx, rdi; struct _WERSVC_MSG *
0x18001522a  mov     rcx, rsi; this
0x18001522d  call    ?SvcNonElevatedLaunch@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcNonElevatedLaunch(_WERSVC_MSG *,_WERSVC_MSG *)
0x180015232  jmp     loc_180015407
0x180015237  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x18001523c  mov     rdx, rdi; struct _WERSVC_MSG *
0x18001523f  mov     rcx, rsi; this
0x180015242  call    ?SvcLookupHKCUForIFEO@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcLookupHKCUForIFEO(_WERSVC_MSG *,_WERSVC_MSG *)
0x180015247  jmp     loc_180015407
0x18001524c  mov     ecx, [rdi+30h]
0x18001524f  test    ecx, ecx
0x180015251  jz      short loc_180015261
0x180015253  mov     ebx, 80070057h
0x180015258  cmp     ecx, 1
0x18001525b  jnz     loc_180015157
0x180015261  mov     [rdi+56h], r15w
0x180015266  mov     [rdi+0A6h], r15w
0x18001526e  mov     r8d, r15d
0x180015271  test    ecx, ecx
0x180015273  setnz   r8b; int
0x180015277  lea     rdx, [rdi+58h]; wchar_t *
0x18001527b  lea     rcx, [rdi+38h]; wchar_t *
0x18001527f  call    ?LiveKernelReport@@YAJPEB_W0H@Z; LiveKernelReport(wchar_t const *,wchar_t const *,int)
0x180015284  mov     ebx, eax
0x180015286  jmp     loc_180015157
0x18001528b  mov     [rbp+530h+var_598], 1
0x180015292  mov     [rbp+530h+var_594], r13d
0x180015296  mov     ebx, 80004005h
0x18001529b  jmp     loc_180015409
0x1800152a0  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x1800152a5  mov     rdx, rdi; struct _WERSVC_MSG *
0x1800152a8  mov     rcx, rsi; this
0x1800152ab  call    ?SvcReportStoreGetLock@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcReportStoreGetLock(_WERSVC_MSG *,_WERSVC_MSG *)
0x1800152b0  jmp     loc_180015407
0x1800152b5  mov     ecx, 0F0010002h; this
0x1800152ba  cmp     eax, ecx
0x1800152bc  ja      loc_180015394
0x1800152c2  jz      loc_180015382
0x1800152c8  cmp     eax, 0C0000003h
0x1800152cd  jz      short loc_180015340
0x1800152cf  cmp     eax, 0C0000004h
0x1800152d4  jz      short loc_18001532E
0x1800152d6  cmp     eax, 0D0000002h
0x1800152db  jz      short loc_180015319
0x1800152dd  cmp     eax, 0E0000002h
0x1800152e2  jz      short loc_180015304
0x1800152e4  cmp     eax, 0F0000002h
0x1800152e9  jnz     loc_1800153B7
0x1800152ef  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x1800152f4  mov     rdx, rdi; struct _WERSVC_MSG *
0x1800152f7  mov     rcx, rsi; this
0x1800152fa  call    ?SvcMachineIdCreate@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcMachineIdCreate(_WERSVC_MSG *,_WERSVC_MSG *)
0x1800152ff  jmp     loc_180015407
0x180015304  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x180015309  mov     rdx, rdi; struct _WERSVC_MSG *
0x18001530c  mov     rcx, rsi; this
0x18001530f  call    ?SvcGenericReportCreate@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcGenericReportCreate(_WERSVC_MSG *,_WERSVC_MSG *)
0x180015314  jmp     loc_180015407
0x180015319  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x18001531e  mov     rdx, rdi; struct _WERSVC_MSG *
0x180015321  mov     rcx, rsi; this
0x180015324  call    ?SvcElevatedDataCollectorCreate@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcElevatedDataCollectorCreate(_WERSVC_MSG *,_WERSVC_MSG *)
0x180015329  jmp     loc_180015407
0x18001532e  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x180015333  mov     rdx, rdi; struct _WERSVC_MSG *
0x180015336  call    ?SvcReportStorePruneUserStore@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcReportStorePruneUserStore(_WERSVC_MSG *,_WERSVC_MSG *)
0x18001533b  jmp     loc_180015407
0x180015340  mov     [rsp+630h+hKey], r15
0x180015345  lea     rcx, [rsp+630h+hKey]
0x18001534a  call    ?InitReportStore@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; InitReportStore(tlx::unique_any<tlx::file_handle_traits> *)
0x18001534f  mov     ebx, eax
0x180015351  mov     [rbp+530h+var_594], eax
0x180015354  mov     eax, r15d
0x180015357  test    ebx, ebx
0x180015359  sets    al
0x18001535c  add     eax, 0C0000000h
0x180015361  mov     [rbp+530h+var_598], eax
0x180015364  mov     rcx, [rsp+630h+hKey]; hObject
0x180015369  lea     rax, [rcx+1]
0x18001536d  cmp     rax, 1
0x180015371  jbe     loc_180015409
0x180015377  call    cs:__imp_CloseHandle
0x18001537d  jmp     loc_180015409
0x180015382  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x180015387  mov     rdx, rdi; struct _WERSVC_MSG *
0x18001538a  mov     rcx, rsi; this
0x18001538d  call    ?SvcCollectETWLogs@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcCollectETWLogs(_WERSVC_MSG *,_WERSVC_MSG *)
0x180015392  jmp     short loc_180015407
0x180015394  cmp     eax, 0F0020002h
0x180015399  jz      short loc_1800153FA
0x18001539b  cmp     eax, 0F0030002h
0x1800153a0  jz      short loc_1800153EB
0x1800153a2  cmp     eax, 0F0040002h
0x1800153a7  jz      short loc_1800153DC
0x1800153a9  cmp     eax, 0F0050002h
0x1800153ae  jz      short loc_1800153CD
0x1800153b0  cmp     eax, 0F0060002h
0x1800153b5  jz      short loc_1800153BE
0x1800153b7  mov     ebx, 80070057h
0x1800153bc  jmp     short loc_180015409
0x1800153be  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x1800153c3  mov     rdx, rdi; struct _WERSVC_MSG *
0x1800153c6  call    ?SvcAddTerminationReason@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcAddTerminationReason(_WERSVC_MSG *,_WERSVC_MSG *)
0x1800153cb  jmp     short loc_180015407
0x1800153cd  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x1800153d2  mov     rdx, rdi; struct _WERSVC_MSG *
0x1800153d5  call    ?SvcGetTerminationReason@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcGetTerminationReason(_WERSVC_MSG *,_WERSVC_MSG *)
0x1800153da  jmp     short loc_180015407
0x1800153dc  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x1800153e1  mov     rdx, rdi; struct _WERSVC_MSG *
0x1800153e4  call    ?SvcCollectSystemInfo@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcCollectSystemInfo(_WERSVC_MSG *,_WERSVC_MSG *)
0x1800153e9  jmp     short loc_180015407
0x1800153eb  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x1800153f0  mov     rdx, rdi; struct _WERSVC_MSG *
0x1800153f3  call    ?SvcCollectMemoryInfo@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcCollectMemoryInfo(_WERSVC_MSG *,_WERSVC_MSG *)
0x1800153f8  jmp     short loc_180015407
0x1800153fa  lea     r8, [rsp+630h+var_5C0]; struct _WERSVC_MSG *
0x1800153ff  mov     rdx, rdi; struct _WERSVC_MSG *
0x180015402  call    ?SvcMergeETWLogs@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z; CWerService::SvcMergeETWLogs(_WERSVC_MSG *,_WERSVC_MSG *)
0x180015407  mov     ebx, eax
0x180015409  lea     r13, WPP_GLOBAL_Control
0x180015410  mov     rcx, cs:WPP_GLOBAL_Control
0x180015417  cmp     rcx, r13
0x18001541a  jz      short loc_18001543F
0x18001541c  test    byte ptr [rcx+1Ch], 4
0x180015420  jz      short loc_18001543F
0x180015422  mov     edx, 68h ; 'h'
0x180015427  mov     dword ptr [rsp+630h+phkResult], ebx
0x18001542b  mov     r9d, [rdi+28h]
0x18001542f  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180015436  mov     rcx, [rcx+10h]
0x18001543a  call    WPP_SF_Dd
0x18001543f  mov     [rsp+630h+hKey], rsi
0x180015444  mov     rcx, rsi; lpCriticalSection
0x180015447  call    cs:__imp_EnterCriticalSection
0x18001544d  mov     [rsp+630h+var_5E8], 1
0x180015452  mov     rcx, [rsi+188h]
0x180015459  test    rcx, rcx
0x18001545c  jnz     short loc_18001546A
0x18001545e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015463  mov     rcx, [rsi+188h]
0x18001546a  mov     eax, [rdi+28h]
0x18001546d  sub     eax, 20000001h
0x180015472  test    eax, 0FFFFFFFBh
0x180015477  lea     r8, [rsp+630h+var_5C0]
  ... truncated ...
```

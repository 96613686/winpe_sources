# TLPCMgr::ProcessConnectionRequest(void *,_PORT_MESSAGE *,_ALPC_DATA_VIEW_ATTR *)

- ea: `0x140011624`
- end: `0x14001180b`
- name: `?ProcessConnectionRequest@TLPCMgr@@QEAAKPEAXPEAU_PORT_MESSAGE@@PEAU_ALPC_DATA_VIEW_ATTR@@@Z`
- size: `487`
- prototype: `unsigned int __fastcall(TLPCMgr *__hidden this, void *, struct _PORT_MESSAGE *, struct _ALPC_DATA_VIEW_ATTR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x14000fec0`

## callees

- `0x140007298`
- `0x1400085d8`
- `0x1400086e0`
- `0x140010cac`
- `0x140010d98`
- `0x140010f8c`
- `0x140011268`
- `0x140011624`
- `0x140016010`

## import_xrefs

- `ntdll!NtAlpcAcceptConnectPort` at `0x1400116ab`
- `ntdll!NtAlpcAcceptConnectPort` at `0x1400117e2`
- `ntdll!NtAlpcAcceptConnectPort` at `0x1400116ab`
- `ntdll!NtAlpcAcceptConnectPort` at `0x1400117e2`
- `ntdll!NtAlpcOpenSenderThread` at `0x140011716`
- `ntdll!NtAlpcOpenSenderThread` at `0x140011716`

## string_xrefs

- `0x1400117a6`: `Failed to create the ClientInfo object for port context.  Error %d.`

## pseudocode

```c
_BOOL8 __fastcall TLPCMgr::ProcessConnectionRequest(
        TLPCMgr *this,
        void *a2,
        struct _PORT_MESSAGE *a3,
        struct _ALPC_DATA_VIEW_ATTR *a4)
{
  struct TLPCMgr::TClientInfo *v8; // rax
  struct TLPCMgr::TClientInfo *v9; // rdi
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 appended; // rax
  __int64 v15; // rcx
  int v17; // [rsp+40h] [rbp-40h]
  _QWORD v18[4]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v19; // [rsp+70h] [rbp-10h]
  __int64 v20; // [rsp+C0h] [rbp+40h] BYREF
  unsigned __int64 UniqueProcess; // [rsp+D0h] [rbp+50h] BYREF

  v20 = 0;
  SplWow64Telemetry::WriteDbgTraceInfo("TLPCMgr::ProcessConnectionRequest", L"Processing connection request.");
  UniqueProcess = (unsigned __int64)a3->ClientId.UniqueProcess;
  v8 = TLPCMgr::TClientInfo::CreateInstance(&UniqueProcess, (TLPCMgr *)((char *)this + 88));
  v9 = v8;
  if ( !v8 )
  {
    v11 = -1073741801;
    SplWow64Telemetry::WriteDbgTraceError(
      "TLPCMgr::ProcessConnectionRequest",
      L"Failed to create the ClientInfo object for port context.  Error %d.",
      3221225495LL);
    goto LABEL_13;
  }
  v10 = NtAlpcAcceptConnectPort(&v20, a2, 0, 0, 0, v8, a3, 0, 1);
  v11 = v10;
  if ( v10 < 0 )
  {
    SplWow64Telemetry::WriteDbgTraceError(
      "TLPCMgr::ProcessConnectionRequest",
      L"Failed to accept port connection.  Error %d.",
      (unsigned int)v10);
    (**(void (__fastcall ***)(struct TLPCMgr::TClientInfo *, __int64))v9)(v9, 1);
LABEL_13:
    LOBYTE(v17) = 0;
    NtAlpcAcceptConnectPort(&v20, a2, 0, 0, 0, 0, a3, 0, v17);
    return v11 != 0;
  }
  *((_DWORD *)v9 + 20) = 24;
  *((_QWORD *)v9 + 11) = *((_QWORD *)a4 + 3);
  *((_QWORD *)v9 + 12) = *((_QWORD *)a4 + 2);
  v12 = v20;
  *((_QWORD *)v9 + 7) = v20;
  if ( v12 )
  {
    v18[0] = 48;
    memset(&v18[1], 0, 24);
    v19 = 0;
    NtAlpcOpenSenderThread((char *)v9 + 72, v12, a3, 0, 0x80000000, v18);
  }
  v13 = *((_QWORD *)this + 10);
  if ( v13 )
  {
    UniqueProcess = (unsigned __int64)a3->ClientId.UniqueProcess;
    appended = TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(v13, &UniqueProcess);
    if ( appended
      || (v15 = *((_QWORD *)this + 10),
          UniqueProcess = (unsigned __int64)a3->ClientId.UniqueProcess,
          (appended = TLstMgr<TLPCMgr::TConnectedClientsInfo,unsigned __int64>::AppendListByElem(v15, &UniqueProcess)) != 0) )
    {
      TLstMgr<TLPCMgr::TClientInfo,void *>::AppendListByElem(*(_QWORD *)(*(_QWORD *)appended + 32LL), v9);
    }
    else
    {
      v11 = -1073741801;
    }
  }
  TLoad64BitDllsMgr::IncUIRefCnt(*((TLoad64BitDllsMgr **)this + 6));
  return v11 != 0;
}

```

## disassembly

```asm
0x140011624  mov     [rsp-38h+arg_8], rbx
0x140011629  push    rbp
0x14001162a  push    rsi
0x14001162b  push    rdi
0x14001162c  push    r12
0x14001162e  push    r13
0x140011630  push    r14
0x140011632  push    r15
0x140011634  mov     rbp, rsp
0x140011637  sub     rsp, 80h
0x14001163e  mov     r12, rdx
0x140011641  mov     r14, rcx
0x140011644  xor     r13d, r13d
0x140011647  lea     rdx, aProcessingConn; "Processing connection request."
0x14001164e  lea     rcx, aTlpcmgrProcess; "TLPCMgr::ProcessConnectionRequest"
0x140011655  mov     [rbp+arg_0], r13
0x140011659  mov     r15, r9
0x14001165c  mov     rsi, r8
0x14001165f  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140011664  mov     rax, [rsi+8]
0x140011668  lea     rdx, [r14+58h]; struct TLPCMgr::TWorkCrewForUniqueProcess *
0x14001166c  lea     rcx, [rbp+arg_10]; unsigned __int64 *
0x140011670  mov     [rbp+arg_10], rax
0x140011674  call    ?CreateInstance@TClientInfo@TLPCMgr@@SAPEAV12@AEB_KAEAVTWorkCrewForUniqueProcess@2@@Z; TLPCMgr::TClientInfo::CreateInstance(unsigned __int64 const &,TLPCMgr::TWorkCrewForUniqueProcess &)
0x140011679  mov     rdi, rax
0x14001167c  test    rax, rax
0x14001167f  jz      loc_1400117A1
0x140011685  mov     byte ptr [rsp+80h+var_40], 1
0x14001168a  lea     rcx, [rbp+arg_0]
0x14001168e  mov     [rsp+80h+var_48], r13
0x140011693  xor     r9d, r9d
0x140011696  mov     [rsp+80h+var_50], rsi
0x14001169b  xor     r8d, r8d
0x14001169e  mov     [rsp+80h+var_58], rax
0x1400116a3  mov     rdx, r12
0x1400116a6  mov     [rsp+80h+var_60], r13
0x1400116ab  call    cs:__imp_NtAlpcAcceptConnectPort
0x1400116b1  mov     ebx, eax
0x1400116b3  test    eax, eax
0x1400116b5  js      loc_140011776
0x1400116bb  mov     dword ptr [rdi+50h], 18h
0x1400116c2  mov     rcx, [r15+18h]
0x1400116c6  mov     [rdi+58h], rcx
0x1400116ca  mov     rcx, [r15+10h]
0x1400116ce  mov     [rdi+60h], rcx
0x1400116d2  mov     rdx, [rbp+arg_0]
0x1400116d6  mov     [rdi+38h], rdx
0x1400116da  test    rdx, rdx
0x1400116dd  jz      short loc_14001171C
0x1400116df  lea     rax, [rbp+var_30]
0x1400116e3  mov     [rbp+var_30], 30h ; '0'
0x1400116eb  xorps   xmm0, xmm0
0x1400116ee  mov     [rsp+80h+var_58], rax
0x1400116f3  lea     rcx, [rdi+48h]
0x1400116f7  mov     dword ptr [rsp+80h+var_60], 80000000h
0x1400116ff  xor     r9d, r9d
0x140011702  mov     [rbp+var_18], r13
0x140011706  mov     r8, rsi
0x140011709  mov     [rbp+var_28], r13
0x14001170d  mov     [rbp+var_20], r13
0x140011711  movdqu  [rbp+var_10], xmm0
0x140011716  call    cs:__imp_NtAlpcOpenSenderThread
0x14001171c  mov     rcx, [r14+50h]
0x140011720  test    rcx, rcx
0x140011723  jz      short loc_14001176B
0x140011725  mov     rax, [rsi+8]
0x140011729  lea     rdx, [rbp+arg_10]
0x14001172d  mov     [rbp+arg_10], rax
0x140011731  call    ?ElementInList@?$TLstMgr@VTPrinterHandleInfo@TLPCMgr@@PEAX@@QEBAPEAV?$TLstNd@VTPrinterHandleInfo@TLPCMgr@@PEAX@@AEBQEAX@Z; TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(void * const &)
0x140011736  test    rax, rax
0x140011739  jnz     short loc_14001175C
0x14001173b  mov     rax, [rsi+8]
0x14001173f  lea     rdx, [rbp+arg_10]
0x140011743  mov     rcx, [r14+50h]
0x140011747  mov     [rbp+arg_10], rax
0x14001174b  call    ?AppendListByElem@?$TLstMgr@VTConnectedClientsInfo@TLPCMgr@@_K@@QEAAPEAV?$TLstNd@VTConnectedClientsInfo@TLPCMgr@@_K@@AEB_K@Z; TLstMgr<TLPCMgr::TConnectedClientsInfo,unsigned __int64>::AppendListByElem(unsigned __int64 const &)
0x140011750  test    rax, rax
0x140011753  jnz     short loc_14001175C
0x140011755  mov     ebx, 0C0000017h
0x14001175a  jmp     short loc_14001176B
0x14001175c  mov     rcx, [rax]
0x14001175f  mov     rdx, rdi
0x140011762  mov     rcx, [rcx+20h]
0x140011766  call    ?AppendListByElem@?$TLstMgr@VTClientInfo@TLPCMgr@@PEAX@@QEAAPEAV?$TLstNd@VTClientInfo@TLPCMgr@@PEAX@@PEAVTClientInfo@TLPCMgr@@@Z; TLstMgr<TLPCMgr::TClientInfo,void *>::AppendListByElem(TLPCMgr::TClientInfo *)
0x14001176b  mov     rcx, [r14+30h]; this
0x14001176f  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x140011774  jmp     short loc_1400117E8
0x140011776  mov     r8d, eax
0x140011779  lea     rdx, aFailedToAccept; "Failed to accept port connection.  Erro"...
0x140011780  lea     rcx, aTlpcmgrProcess; "TLPCMgr::ProcessConnectionRequest"
0x140011787  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14001178c  mov     rax, [rdi]
0x14001178f  mov     edx, 1
0x140011794  mov     rcx, rdi
0x140011797  mov     rax, [rax]
0x14001179a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001179f  jmp     short loc_1400117BC
0x1400117a1  mov     ebx, 0C0000017h
0x1400117a6  lea     rdx, aFailedToCreate_0; "Failed to create the ClientInfo object "...
0x1400117ad  mov     r8d, ebx
0x1400117b0  lea     rcx, aTlpcmgrProcess; "TLPCMgr::ProcessConnectionRequest"
0x1400117b7  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400117bc  mov     byte ptr [rsp+80h+var_40], r13b
0x1400117c1  lea     rcx, [rbp+arg_0]
0x1400117c5  mov     [rsp+80h+var_48], r13
0x1400117ca  xor     r9d, r9d
0x1400117cd  mov     [rsp+80h+var_50], rsi
0x1400117d2  xor     r8d, r8d
0x1400117d5  mov     [rsp+80h+var_58], r13
0x1400117da  mov     rdx, r12
0x1400117dd  mov     [rsp+80h+var_60], r13
0x1400117e2  call    cs:__imp_NtAlpcAcceptConnectPort
0x1400117e8  test    ebx, ebx
0x1400117ea  mov     eax, r13d
0x1400117ed  mov     rbx, [rsp+80h+arg_8]
0x1400117f5  setnz   al
0x1400117f8  add     rsp, 80h
0x1400117ff  pop     r15
0x140011801  pop     r14
0x140011803  pop     r13
0x140011805  pop     r12
0x140011807  pop     rdi
0x140011808  pop     rsi
0x140011809  pop     rbp
0x14001180a  retn
```

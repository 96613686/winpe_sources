# ThreadNotifyProcessJob(_TMSTATEVAR *,void *)

- ea: `0x14006e940`
- end: `0x14006ed99`
- name: `?ThreadNotifyProcessJob@@YAKPEAU_TMSTATEVAR@@PEAX@Z`
- size: `1113`
- prototype: `unsigned int(struct _TMSTATEVAR *, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x14000de80`
- `0x140010c7c`
- `0x14001366c`
- `0x140013a5c`
- `0x140015290`
- `0x140015378`
- `0x140018e00`
- `0x14006d350`
- `0x14006e42c`
- `0x14006e5f8`
- `0x14006e940`
- `0x14006f23c`
- `0x14006f324`
- `0x14006f800`
- `0x140078d48`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006e9e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006ed54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006ed71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006e9e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006ed54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006ed71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006e978`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006ebf0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006e978`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006ebf0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14006ebdd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14006ebdd`
- `RPCRT4!NdrClientCall3` at `0x14006eaea`
- `RPCRT4!NdrClientCall3` at `0x14006eb27`
- `RPCRT4!NdrClientCall3` at `0x14006eaea`
- `RPCRT4!NdrClientCall3` at `0x14006eb27`
- `RPCRT4!I_RpcExceptionFilter` at `0x140080c4a`
- `RPCRT4!I_RpcExceptionFilter` at `0x140080c4a`

## string_xrefs

- `0x14006ea86`: `ThreadNotifyProcessJob`
- `0x14006eba8`: `ThreadNotifyProcessJob`
- `0x14006ecef`: `ThreadNotifyProcessJob`
- `0x14006ed1f`: `ThreadNotifyProcessJob`
- `0x14006ece8`: `Delayed link added, 0x%p, refcount %d.`

## pseudocode

```c
__int64 __fastcall ThreadNotifyProcessJob(struct _TMSTATEVAR *a1, char *a2)
{
  unsigned int *v3; // r14
  int v4; // ecx
  unsigned int v5; // ebx
  char *v6; // r12
  unsigned int v7; // r13d
  unsigned int RemoteNotifyData; // eax
  unsigned int Pointer; // ebx
  unsigned int v10; // eax
  void **v11; // r15
  CLIENT_CALL_RETURN v12; // rax
  unsigned int v13; // r9d
  struct _PRINTER_NOTIFY_INFO *v14; // rcx
  struct _PRINTER_NOTIFY_INFO *v15; // r15
  struct _PRINTHANDLE *v16; // rcx
  void *v17; // rbx
  struct __MIDL_winspool_0021 **v19; // [rsp+20h] [rbp-A8h]
  unsigned int v20[2]; // [rsp+20h] [rbp-A8h]
  unsigned __int8 *v21; // [rsp+28h] [rbp-A0h]
  PPRINTER_NOTIFY_INFO pInfo; // [rsp+50h] [rbp-78h] BYREF
  int v23; // [rsp+58h] [rbp-70h]
  CLIENT_CALL_RETURN v24; // [rsp+60h] [rbp-68h]
  CLIENT_CALL_RETURN v25; // [rsp+68h] [rbp-60h]
  char *v26; // [rsp+70h] [rbp-58h]
  char *v27; // [rsp+78h] [rbp-50h]
  char *v28; // [rsp+80h] [rbp-48h]
  _BYTE *v29; // [rsp+88h] [rbp-40h]
  _DWORD *v30; // [rsp+90h] [rbp-38h]
  struct _CHANGE *v31; // [rsp+98h] [rbp-30h] BYREF
  char *v32; // [rsp+D8h] [rbp+10h] BYREF
  int v33; // [rsp+E0h] [rbp+18h] BYREF
  unsigned int v34; // [rsp+E8h] [rbp+20h]

  v32 = a2;
  v31 = (struct _CHANGE *)a2;
  pInfo = 0;
  v33 = 0;
  EnterCriticalSection(lpCriticalSection);
  v3 = (unsigned int *)(a2 + 12);
  v26 = a2 + 12;
  v4 = *((_DWORD *)a2 + 3);
  if ( (v4 & 0x100) != 0 )
    goto LABEL_39;
  v5 = *((_DWORD *)a2 + 27);
  *((_DWORD *)a2 + 27) = 0;
  v6 = a2 + 80;
  v27 = a2 + 80;
  pInfo = (PPRINTER_NOTIFY_INFO)*((_QWORD *)a2 + 10);
  *((_QWORD *)a2 + 10) = 0;
  *v3 = v4 & 0xFFFFF7FF;
  v30 = a2 + 16;
  v7 = *((_DWORD *)a2 + 4);
  v34 = v7;
  LeaveCriticalSection(lpCriticalSection);
  v29 = a2 + 128;
  if ( (a2[128] & 8) != 0 )
  {
    if ( *((_QWORD *)a2 + 19) )
    {
      v32 = 0;
      RemoteNotifyData = NRemoteNotify_Library::CreateRemoteNotifyData(
                           (NRemoteNotify_Library *)v7,
                           v5,
                           (unsigned int)pInfo,
                           (struct _RPC_V2_NOTIFY_INFO *)&v32,
                           v19);
      Pointer = StatusFromHResult(RemoteNotifyData);
      if ( !Pointer )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a2 + 19) + 32LL))(*((_QWORD *)a2 + 19), v32);
        Pointer = StatusFromHResult(v10);
        pInfo = 0;
      }
    }
    else
    {
      Pointer = 6;
    }
    v11 = (void **)(a2 + 120);
  }
  else
  {
    v11 = (void **)(a2 + 120);
    v28 = a2 + 120;
    if ( *((_QWORD *)a2 + 15) )
    {
      PrvSpoolssTelemetry::WriteDbgTraceInfo(
        "ThreadNotifyProcessJob",
        L"Remoting pChange 0x%p, hNotifyRemote 0x%p",
        a2,
        *v11);
      if ( pInfo )
      {
        v24.Simple = 0;
        v12.Pointer = NdrClientCall3(
                        (MIDL_STUBLESS_PROXY_INFO *)&RpcClientFunctions::winspool_ProxyInfo,
                        0x42u,
                        0,
                        *v11,
                        v7,
                        v5,
                        &v33,
                        0,
                        pInfo).Pointer;
        Pointer = (unsigned int)v12.Pointer;
        v24.Pointer = v12.Pointer;
      }
      else
      {
        v25.Simple = 0;
        v12.Pointer = NdrClientCall3(
                        (MIDL_STUBLESS_PROXY_INFO *)&RpcClientFunctions::winspool_ProxyInfo,
                        0x3Bu,
                        0,
                        *v11,
                        v5,
                        1,
                        &pInfo).Pointer;
        v25.Pointer = v12.Pointer;
        Pointer = (unsigned int)v12.Pointer;
      }
      v23 = (int)v12.Pointer;
    }
    else
    {
      Pointer = 6;
      PrvSpoolssTelemetry::WriteDbgTraceError("ThreadNotifyProcessJob", L"No hNotifyRemote.");
    }
  }
  if ( Pointer )
  {
    if ( (*v29 & 8) == 0 )
    {
      LODWORD(v21) = *((_DWORD *)a2 + 28);
      *(_QWORD *)v20 = *v11;
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "ThreadNotifyProcessJob",
        L"RPC error %d, pChange 0x%p, hNotifyRemote 0x%p, dwPrinterRemote 0x%x.",
        Pointer,
        a2);
      CloseReplyRemote(*v11);
      if ( OpenReplyRemote(*((RpcClientFunctions **)a2 + 3), v11, (void **)*((unsigned int *)a2 + 28), v13, v20[0], v21) )
        *v11 = 0;
    }
  }
  Sleep(*(DWORD *)&dwThreadNotifySleep);
  EnterCriticalSection(lpCriticalSection);
  if ( v7 != *v30 )
    v33 = 0;
  v14 = pInfo;
  if ( pInfo )
  {
    v15 = *(struct _PRINTER_NOTIFY_INFO **)v6;
    if ( !Pointer )
    {
      if ( (v33 & 0x10000) != 0 )
      {
        *v3 |= 0x18000u;
        v14 = pInfo;
      }
      if ( v15 )
      {
        RouterFreePrinterNotifyInfo(v14);
      }
      else
      {
        ClearPrinterNotifyInfo(v14, (struct _CHANGE *)a2);
        *(_QWORD *)v6 = pInfo;
      }
      *(_DWORD *)(*(_QWORD *)v6 + 4LL) |= v33;
      goto LABEL_35;
    }
    *(_QWORD *)v6 = pInfo;
    if ( Pointer == 1727 )
    {
      if ( v15 )
      {
        v16 = (struct _PRINTHANDLE *)*((_QWORD *)a2 + 5);
        if ( v16 )
          AppendPrinterNotifyInfo(v16, v7, v15);
        goto LABEL_28;
      }
    }
    else
    {
      ClearPrinterNotifyInfo(pInfo, (struct _CHANGE *)a2);
      SetDiscardPrinterNotifyInfo(pInfo, (struct _CHANGE *)a2);
      if ( v15 )
LABEL_28:
        RouterFreePrinterNotifyInfo(v15);
    }
  }
LABEL_35:
  *v3 &= ~0x400u;
  if ( (*v3 & 0x800) != 0 && (unsigned int)NotifyNeeded((struct _CHANGE *)a2) && (*v3 & 0x100) == 0 )
  {
    PrvSpoolssTelemetry::WriteDbgTraceInfo(
      "ThreadNotifyProcessJob",
      L"Delayed link added, 0x%p, refcount %d.",
      a2,
      *((unsigned int *)a2 + 5));
    *v3 &= ~0x800u;
    LinkChange((struct _CHANGE *)a2);
  }
LABEL_39:
  SafeDecrementReference((unsigned int *)a2 + 5);
  PrvSpoolssTelemetry::WriteDbgTraceInfo(
    "ThreadNotifyProcessJob",
    L"Done 0x%p, refcount %d.",
    a2,
    *((unsigned int *)a2 + 5));
  if ( (*v3 & 0x100) != 0 )
  {
    v17 = (void *)*((_QWORD *)a2 + 15);
    *((_QWORD *)a2 + 15) = 0;
    FreeChange(&v31);
    LeaveCriticalSection(lpCriticalSection);
    CloseReplyRemote(v17);
  }
  else
  {
    LeaveCriticalSection(lpCriticalSection);
  }
  return 0;
}

```

## disassembly

```asm
0x14006e940  mov     rax, rsp
0x14006e943  mov     [rax+8], rbx
0x14006e947  mov     [rax+10h], rdx
0x14006e94b  push    rdi
0x14006e94c  push    r12
0x14006e94e  push    r13
0x14006e950  push    r14
0x14006e952  push    r15
0x14006e954  sub     rsp, 0A0h
0x14006e95b  mov     rdi, rdx
0x14006e95e  mov     [rax-30h], rdx
0x14006e962  mov     qword ptr [rax-78h], 0
0x14006e96a  mov     dword ptr [rax+18h], 0
0x14006e971  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x14006e978  call    cs:__imp_EnterCriticalSection
0x14006e97f  nop     dword ptr [rax+rax+00h]
0x14006e984  lea     r14, [rdi+0Ch]
0x14006e988  mov     [rsp+0C8h+var_58], r14
0x14006e98d  mov     ecx, [r14]
0x14006e990  bt      ecx, 8
0x14006e994  jb      loc_14006ED08
0x14006e99a  mov     ebx, [rdi+6Ch]
0x14006e99d  mov     dword ptr [rdi+6Ch], 0
0x14006e9a4  lea     r12, [rdi+50h]
0x14006e9a8  mov     [rsp+0C8h+var_50], r12
0x14006e9ad  mov     rax, [r12]
0x14006e9b1  mov     [rsp+0C8h+pInfo], rax
0x14006e9b6  mov     qword ptr [r12], 0
0x14006e9be  btr     ecx, 0Bh
0x14006e9c2  mov     [r14], ecx
0x14006e9c5  lea     rax, [rdi+10h]
0x14006e9c9  mov     [rsp+0C8h+var_38], rax
0x14006e9d1  mov     r13d, [rax]
0x14006e9d4  mov     [rsp+0C8h+arg_18], r13d
0x14006e9dc  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x14006e9e3  call    cs:__imp_LeaveCriticalSection
0x14006e9ea  nop     dword ptr [rax+rax+00h]
0x14006e9ef  lea     rax, [rdi+80h]
0x14006e9f6  mov     [rsp+0C8h+var_40], rax
0x14006e9fe  test    byte ptr [rax], 8
0x14006ea01  jz      short loc_14006EA7A
0x14006ea03  cmp     qword ptr [rdi+98h], 0
0x14006ea0b  jz      short loc_14006EA6C
0x14006ea0d  mov     [rsp+0C8h+arg_8], 0
0x14006ea19  lea     r9, [rsp+0C8h+arg_8]; struct _RPC_V2_NOTIFY_INFO *
0x14006ea21  mov     r8, [rsp+0C8h+pInfo]; unsigned int
0x14006ea26  mov     edx, ebx; unsigned int
0x14006ea28  mov     ecx, r13d; this
0x14006ea2b  call    ?CreateRemoteNotifyData@NRemoteNotify_Library@@YAJKKPEAU_RPC_V2_NOTIFY_INFO@@PEAPEAU__MIDL_winspool_0021@@@Z; NRemoteNotify_Library::CreateRemoteNotifyData(ulong,ulong,_RPC_V2_NOTIFY_INFO *,__MIDL_winspool_0021 * *)
0x14006ea30  mov     ecx, eax
0x14006ea32  call    StatusFromHResult
0x14006ea37  mov     ebx, eax
0x14006ea39  test    eax, eax
0x14006ea3b  jnz     short loc_14006EA71
0x14006ea3d  mov     rcx, [rdi+98h]
0x14006ea44  mov     rax, [rcx]
0x14006ea47  mov     rdx, [rsp+0C8h+arg_8]
0x14006ea4f  mov     rax, [rax+20h]
0x14006ea53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ea58  mov     ecx, eax
0x14006ea5a  call    StatusFromHResult
0x14006ea5f  mov     ebx, eax
0x14006ea61  mov     [rsp+0C8h+pInfo], 0
0x14006ea6a  jmp     short loc_14006EA71
0x14006ea6c  mov     ebx, 6
0x14006ea71  lea     r15, [rdi+78h]
0x14006ea75  jmp     loc_14006EB7B
0x14006ea7a  lea     r15, [rdi+78h]
0x14006ea7e  mov     [rsp+0C8h+var_48], r15
0x14006ea86  lea     rcx, aThreadnotifypr; "ThreadNotifyProcessJob"
0x14006ea8d  cmp     qword ptr [r15], 0
0x14006ea91  jz      loc_14006EB6A
0x14006ea97  mov     r9, [r15]
0x14006ea9a  mov     r8, rdi
0x14006ea9d  lea     rdx, aRemotingPchang; "Remoting pChange 0x%p, hNotifyRemote 0x"...
0x14006eaa4  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006eaa9  nop
0x14006eaaa  mov     rax, [rsp+0C8h+pInfo]
0x14006eaaf  xor     r8d, r8d; pReturnValue
0x14006eab2  lea     rcx, ?winspool_ProxyInfo@RpcClientFunctions@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x14006eab9  test    rax, rax
0x14006eabc  jz      short loc_14006EB00
0x14006eabe  mov     [rsp+0C8h+var_68], r8
0x14006eac3  mov     [rsp+0C8h+var_88], rax
0x14006eac8  mov     [rsp+0C8h+var_90], r8d
0x14006eacd  lea     rax, [rsp+0C8h+arg_10]
0x14006ead5  mov     [rsp+0C8h+var_98], rax
0x14006eada  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x14006eade  mov     [rsp+0C8h+var_A8], r13d
0x14006eae3  mov     r9, [r15]
0x14006eae6  lea     edx, [r8+42h]; nProcNum
0x14006eaea  call    cs:__imp_NdrClientCall3
0x14006eaf1  nop     dword ptr [rax+rax+00h]
0x14006eaf6  mov     rbx, rax
0x14006eaf9  mov     [rsp+0C8h+var_68], rax
0x14006eafe  jmp     short loc_14006EB3A
0x14006eb00  mov     [rsp+0C8h+var_60], 0
0x14006eb09  lea     rax, [rsp+0C8h+pInfo]
0x14006eb0e  mov     [rsp+0C8h+var_98], rax
0x14006eb13  mov     dword ptr [rsp+0C8h+var_A0], 1
0x14006eb1b  mov     [rsp+0C8h+var_A8], ebx
0x14006eb1f  mov     r9, [r15]
0x14006eb22  mov     edx, 3Bh ; ';'; nProcNum
0x14006eb27  call    cs:__imp_NdrClientCall3
0x14006eb2e  nop     dword ptr [rax+rax+00h]
0x14006eb33  mov     [rsp+0C8h+var_60], rax
0x14006eb38  mov     ebx, eax
0x14006eb3a  mov     [rsp+0C8h+var_70], eax
0x14006eb3e  jmp     short loc_14006EB68
0x14006eb40  mov     ebx, eax
0x14006eb42  mov     [rsp+0C8h+var_70], eax
0x14006eb46  mov     rdi, [rsp+0C8h+arg_8]
0x14006eb4e  mov     r13d, [rsp+0C8h+arg_18]
0x14006eb56  mov     r14, [rsp+0C8h+var_58]
0x14006eb5b  mov     r12, [rsp+0C8h+var_50]
0x14006eb60  mov     r15, [rsp+0C8h+var_48]
0x14006eb68  jmp     short loc_14006EB7B
0x14006eb6a  mov     ebx, 6
0x14006eb6f  lea     rdx, aNoHnotifyremot; "No hNotifyRemote."
0x14006eb76  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006eb7b  test    ebx, ebx
0x14006eb7d  jz      short loc_14006EBD7
0x14006eb7f  mov     rax, [rsp+0C8h+var_40]
0x14006eb87  test    byte ptr [rax], 8
0x14006eb8a  jnz     short loc_14006EBD7
0x14006eb8c  mov     eax, [rdi+70h]
0x14006eb8f  mov     dword ptr [rsp+0C8h+var_A0], eax; unsigned __int8 *
0x14006eb93  mov     rax, [r15]
0x14006eb96  mov     qword ptr [rsp+0C8h+var_A8], rax; unsigned int
0x14006eb9b  mov     r9, rdi
0x14006eb9e  mov     r8d, ebx
0x14006eba1  lea     rdx, aRpcErrorDPchan; "RPC error %d, pChange 0x%p, hNotifyRemo"...
0x14006eba8  lea     rcx, aThreadnotifypr; "ThreadNotifyProcessJob"
0x14006ebaf  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006ebb4  mov     rcx, [r15]; void *
0x14006ebb7  call    ?CloseReplyRemote@@YAXPEAX@Z; CloseReplyRemote(void *)
0x14006ebbc  mov     r8d, [rdi+70h]; void **
0x14006ebc0  mov     rdx, r15; void **
0x14006ebc3  mov     rcx, [rdi+18h]; this
0x14006ebc7  call    ?OpenReplyRemote@@YAKPEAGPEAPEAXKKKPEAE@Z; OpenReplyRemote(ushort *,void * *,ulong,ulong,ulong,uchar *)
0x14006ebcc  test    eax, eax
0x14006ebce  jz      short loc_14006EBD7
0x14006ebd0  mov     qword ptr [r15], 0
0x14006ebd7  mov     ecx, cs:?dwThreadNotifySleep@@3KA; dwMilliseconds
0x14006ebdd  call    cs:__imp_Sleep
0x14006ebe4  nop     dword ptr [rax+rax+00h]
0x14006ebe9  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x14006ebf0  call    cs:__imp_EnterCriticalSection
0x14006ebf7  nop     dword ptr [rax+rax+00h]
0x14006ebfc  mov     rax, [rsp+0C8h+var_38]
0x14006ec04  cmp     r13d, [rax]
0x14006ec07  jz      short loc_14006EC14
0x14006ec09  mov     [rsp+0C8h+arg_10], 0
0x14006ec14  mov     rcx, [rsp+0C8h+pInfo]
0x14006ec19  test    rcx, rcx
0x14006ec1c  jz      loc_14006ECBE
0x14006ec22  mov     r15, [r12]
0x14006ec26  test    ebx, ebx
0x14006ec28  jz      short loc_14006EC7A
0x14006ec2a  mov     [r12], rcx
0x14006ec2e  cmp     ebx, 6BFh
0x14006ec34  jz      short loc_14006EC57
0x14006ec36  mov     rdx, rdi; struct _CHANGE *
0x14006ec39  mov     rcx, [rsp+0C8h+pInfo]; struct _PRINTER_NOTIFY_INFO *
0x14006ec3e  call    ?ClearPrinterNotifyInfo@@YAXPEAU_PRINTER_NOTIFY_INFO@@PEAU_CHANGE@@@Z; ClearPrinterNotifyInfo(_PRINTER_NOTIFY_INFO *,_CHANGE *)
0x14006ec43  mov     rdx, rdi; struct _CHANGE *
0x14006ec46  mov     rcx, [rsp+0C8h+pInfo]; struct _PRINTER_NOTIFY_INFO *
0x14006ec4b  call    ?SetDiscardPrinterNotifyInfo@@YAXPEAU_PRINTER_NOTIFY_INFO@@PEAU_CHANGE@@@Z; SetDiscardPrinterNotifyInfo(_PRINTER_NOTIFY_INFO *,_CHANGE *)
0x14006ec50  test    r15, r15
0x14006ec53  jz      short loc_14006ECBE
0x14006ec55  jmp     short loc_14006EC70
0x14006ec57  test    r15, r15
0x14006ec5a  jz      short loc_14006ECBE
0x14006ec5c  mov     rcx, [rdi+28h]; struct _PRINTHANDLE *
0x14006ec60  test    rcx, rcx
0x14006ec63  jz      short loc_14006EC70
0x14006ec65  mov     r8, r15; struct _PRINTER_NOTIFY_INFO *
0x14006ec68  mov     edx, r13d; unsigned int
0x14006ec6b  call    ?AppendPrinterNotifyInfo@@YAKPEAU_PRINTHANDLE@@KPEAU_PRINTER_NOTIFY_INFO@@@Z; AppendPrinterNotifyInfo(_PRINTHANDLE *,ulong,_PRINTER_NOTIFY_INFO *)
0x14006ec70  mov     rcx, r15; pInfo
0x14006ec73  call    RouterFreePrinterNotifyInfo
0x14006ec78  jmp     short loc_14006ECBE
0x14006ec7a  test    [rsp+0C8h+arg_10], 10000h
0x14006ec85  jz      short loc_14006EC93
0x14006ec87  or      dword ptr [r14], 18000h
0x14006ec8e  mov     rcx, [rsp+0C8h+pInfo]; struct _PRINTER_NOTIFY_INFO *
0x14006ec93  test    r15, r15
0x14006ec96  jnz     short loc_14006ECAB
0x14006ec98  mov     rdx, rdi; struct _CHANGE *
0x14006ec9b  call    ?ClearPrinterNotifyInfo@@YAXPEAU_PRINTER_NOTIFY_INFO@@PEAU_CHANGE@@@Z; ClearPrinterNotifyInfo(_PRINTER_NOTIFY_INFO *,_CHANGE *)
0x14006eca0  mov     rax, [rsp+0C8h+pInfo]
0x14006eca5  mov     [r12], rax
0x14006eca9  jmp     short loc_14006ECB0
0x14006ecab  call    RouterFreePrinterNotifyInfo
0x14006ecb0  mov     rcx, [r12]
0x14006ecb4  mov     eax, [rsp+0C8h+arg_10]
0x14006ecbb  or      [rcx+4], eax
0x14006ecbe  btr     dword ptr [r14], 0Ah
0x14006ecc3  test    dword ptr [r14], 800h
0x14006ecca  jz      short loc_14006ED08
0x14006eccc  mov     rcx, rdi; struct _CHANGE *
0x14006eccf  call    ?NotifyNeeded@@YAHPEAU_CHANGE@@@Z; NotifyNeeded(_CHANGE *)
0x14006ecd4  test    eax, eax
0x14006ecd6  jz      short loc_14006ED08
0x14006ecd8  test    dword ptr [r14], 100h
0x14006ecdf  jnz     short loc_14006ED08
0x14006ece1  mov     r9d, [rdi+14h]
0x14006ece5  mov     r8, rdi
0x14006ece8  lea     rdx, aDelayedLinkAdd; "Delayed link added, 0x%p, refcount %d."
0x14006ecef  lea     rcx, aThreadnotifypr; "ThreadNotifyProcessJob"
0x14006ecf6  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006ecfb  btr     dword ptr [r14], 0Bh
0x14006ed00  mov     rcx, rdi; struct _CHANGE *
0x14006ed03  call    ?LinkChange@@YAHPEAU_CHANGE@@@Z; LinkChange(_CHANGE *)
0x14006ed08  lea     rcx, [rdi+14h]; unsigned int *
0x14006ed0c  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x14006ed11  mov     r9d, [rdi+14h]
0x14006ed15  mov     r8, rdi
0x14006ed18  lea     rdx, aDone0xPRefcoun; "Done 0x%p, refcount %d."
0x14006ed1f  lea     rcx, aThreadnotifypr; "ThreadNotifyProcessJob"
0x14006ed26  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006ed2b  test    dword ptr [r14], 100h
0x14006ed32  jz      short loc_14006ED6A
0x14006ed34  mov     rbx, [rdi+78h]
0x14006ed38  mov     qword ptr [rdi+78h], 0
0x14006ed40  lea     rcx, [rsp+0C8h+var_30]; struct _CHANGE **
0x14006ed48  call    ?FreeChange@@YAHPEAPEAU_CHANGE@@@Z; FreeChange(_CHANGE * *)
0x14006ed4d  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x14006ed54  call    cs:__imp_LeaveCriticalSection
0x14006ed5b  nop     dword ptr [rax+rax+00h]
0x14006ed60  mov     rcx, rbx; void *
0x14006ed63  call    ?CloseReplyRemote@@YAXPEAX@Z; CloseReplyRemote(void *)
0x14006ed68  jmp     short loc_14006ED7D
0x14006ed6a  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x14006ed71  call    cs:__imp_LeaveCriticalSection
0x14006ed78  nop     dword ptr [rax+rax+00h]
0x14006ed7d  xor     eax, eax
0x14006ed7f  mov     rbx, [rsp+0C8h+arg_0]
0x14006ed87  add     rsp, 0A0h
0x14006ed8e  pop     r15
0x14006ed90  pop     r14
0x14006ed92  pop     r13
0x14006ed94  pop     r12
0x14006ed96  pop     rdi
0x14006ed97  retn
0x140080c3c  push    rbp
0x140080c3e  sub     rsp, 50h
0x140080c42  mov     rbp, rdx
0x140080c45  mov     rcx, [rcx]
0x140080c48  mov     ecx, [rcx]; ExceptionCode
0x140080c4a  call    cs:__imp_I_RpcExceptionFilter
0x140080c51  nop     dword ptr [rax+rax+00h]
0x140080c56  nop
0x140080c57  add     rsp, 50h
0x140080c5b  pop     rbp
0x140080c5c  retn
```

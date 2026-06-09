# ThreadNotifyProcessJob(_TMSTATEVAR *,void *)

- ea: `0x1400680c0`
- end: `0x1400684e8`
- name: `?ThreadNotifyProcessJob@@YAKPEAU_TMSTATEVAR@@PEAX@Z`
- size: `1064`
- prototype: `unsigned int(struct _TMSTATEVAR *, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x14000d640`
- `0x14000fa7c`
- `0x140012428`
- `0x14001283c`
- `0x140013fe8`
- `0x1400140cc`
- `0x140017948`
- `0x140066ca8`
- `0x140067ca0`
- `0x140067e48`
- `0x1400680c0`
- `0x140068918`
- `0x140068a00`
- `0x140068ea0`
- `0x140071d38`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006815d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400684b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400684c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006815d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400684b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400684c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400680f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140068352`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400680f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140068352`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140068345`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140068345`
- `RPCRT4!NdrClientCall3` at `0x14006825e`
- `RPCRT4!NdrClientCall3` at `0x140068295`
- `RPCRT4!NdrClientCall3` at `0x14006825e`
- `RPCRT4!NdrClientCall3` at `0x140068295`
- `RPCRT4!I_RpcExceptionFilter` at `0x140079748`
- `RPCRT4!I_RpcExceptionFilter` at `0x140079748`

## string_xrefs

- `0x1400681fa`: `ThreadNotifyProcessJob`
- `0x140068310`: `ThreadNotifyProcessJob`
- `0x14006844b`: `ThreadNotifyProcessJob`
- `0x14006847b`: `ThreadNotifyProcessJob`
- `0x140068444`: `Delayed link added, 0x%p, refcount %d.`

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
0x1400680c0  mov     rax, rsp
0x1400680c3  mov     [rax+8], rbx
0x1400680c7  mov     [rax+10h], rdx
0x1400680cb  push    rdi
0x1400680cc  push    r12
0x1400680ce  push    r13
0x1400680d0  push    r14
0x1400680d2  push    r15
0x1400680d4  sub     rsp, 0A0h
0x1400680db  mov     rdi, rdx
0x1400680de  mov     [rax-30h], rdx
0x1400680e2  mov     qword ptr [rax-78h], 0
0x1400680ea  mov     dword ptr [rax+18h], 0
0x1400680f1  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x1400680f8  call    cs:__imp_EnterCriticalSection
0x1400680fe  lea     r14, [rdi+0Ch]
0x140068102  mov     [rsp+0C8h+var_58], r14
0x140068107  mov     ecx, [r14]
0x14006810a  bt      ecx, 8
0x14006810e  jb      loc_140068464
0x140068114  mov     ebx, [rdi+6Ch]
0x140068117  mov     dword ptr [rdi+6Ch], 0
0x14006811e  lea     r12, [rdi+50h]
0x140068122  mov     [rsp+0C8h+var_50], r12
0x140068127  mov     rax, [r12]
0x14006812b  mov     [rsp+0C8h+pInfo], rax
0x140068130  mov     qword ptr [r12], 0
0x140068138  btr     ecx, 0Bh
0x14006813c  mov     [r14], ecx
0x14006813f  lea     rax, [rdi+10h]
0x140068143  mov     [rsp+0C8h+var_38], rax
0x14006814b  mov     r13d, [rax]
0x14006814e  mov     [rsp+0C8h+arg_18], r13d
0x140068156  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x14006815d  call    cs:__imp_LeaveCriticalSection
0x140068163  lea     rax, [rdi+80h]
0x14006816a  mov     [rsp+0C8h+var_40], rax
0x140068172  test    byte ptr [rax], 8
0x140068175  jz      short loc_1400681EE
0x140068177  cmp     qword ptr [rdi+98h], 0
0x14006817f  jz      short loc_1400681E0
0x140068181  mov     [rsp+0C8h+arg_8], 0
0x14006818d  lea     r9, [rsp+0C8h+arg_8]; struct _RPC_V2_NOTIFY_INFO *
0x140068195  mov     r8, [rsp+0C8h+pInfo]; unsigned int
0x14006819a  mov     edx, ebx; unsigned int
0x14006819c  mov     ecx, r13d; this
0x14006819f  call    ?CreateRemoteNotifyData@NRemoteNotify_Library@@YAJKKPEAU_RPC_V2_NOTIFY_INFO@@PEAPEAU__MIDL_winspool_0021@@@Z; NRemoteNotify_Library::CreateRemoteNotifyData(ulong,ulong,_RPC_V2_NOTIFY_INFO *,__MIDL_winspool_0021 * *)
0x1400681a4  mov     ecx, eax
0x1400681a6  call    StatusFromHResult
0x1400681ab  mov     ebx, eax
0x1400681ad  test    eax, eax
0x1400681af  jnz     short loc_1400681E5
0x1400681b1  mov     rcx, [rdi+98h]
0x1400681b8  mov     rax, [rcx]
0x1400681bb  mov     rdx, [rsp+0C8h+arg_8]
0x1400681c3  mov     rax, [rax+20h]
0x1400681c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400681cc  mov     ecx, eax
0x1400681ce  call    StatusFromHResult
0x1400681d3  mov     ebx, eax
0x1400681d5  mov     [rsp+0C8h+pInfo], 0
0x1400681de  jmp     short loc_1400681E5
0x1400681e0  mov     ebx, 6
0x1400681e5  lea     r15, [rdi+78h]
0x1400681e9  jmp     loc_1400682E3
0x1400681ee  lea     r15, [rdi+78h]
0x1400681f2  mov     [rsp+0C8h+var_48], r15
0x1400681fa  lea     rcx, aThreadnotifypr; "ThreadNotifyProcessJob"
0x140068201  cmp     qword ptr [r15], 0
0x140068205  jz      loc_1400682D2
0x14006820b  mov     r9, [r15]
0x14006820e  mov     r8, rdi
0x140068211  lea     rdx, aRemotingPchang; "Remoting pChange 0x%p, hNotifyRemote 0x"...
0x140068218  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006821d  nop
0x14006821e  mov     rax, [rsp+0C8h+pInfo]
0x140068223  xor     r8d, r8d; pReturnValue
0x140068226  lea     rcx, ?winspool_ProxyInfo@RpcClientFunctions@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x14006822d  test    rax, rax
0x140068230  jz      short loc_14006826E
0x140068232  mov     [rsp+0C8h+var_68], r8
0x140068237  mov     [rsp+0C8h+var_88], rax
0x14006823c  mov     [rsp+0C8h+var_90], r8d
0x140068241  lea     rax, [rsp+0C8h+arg_10]
0x140068249  mov     [rsp+0C8h+var_98], rax
0x14006824e  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x140068252  mov     [rsp+0C8h+var_A8], r13d
0x140068257  mov     r9, [r15]
0x14006825a  lea     edx, [r8+42h]; nProcNum
0x14006825e  call    cs:__imp_NdrClientCall3
0x140068264  mov     rbx, rax
0x140068267  mov     [rsp+0C8h+var_68], rax
0x14006826c  jmp     short loc_1400682A2
0x14006826e  mov     [rsp+0C8h+var_60], 0
0x140068277  lea     rax, [rsp+0C8h+pInfo]
0x14006827c  mov     [rsp+0C8h+var_98], rax
0x140068281  mov     dword ptr [rsp+0C8h+var_A0], 1
0x140068289  mov     [rsp+0C8h+var_A8], ebx
0x14006828d  mov     r9, [r15]
0x140068290  mov     edx, 3Bh ; ';'; nProcNum
0x140068295  call    cs:__imp_NdrClientCall3
0x14006829b  mov     [rsp+0C8h+var_60], rax
0x1400682a0  mov     ebx, eax
0x1400682a2  mov     [rsp+0C8h+var_70], eax
0x1400682a6  jmp     short loc_1400682D0
0x1400682a8  mov     ebx, eax
0x1400682aa  mov     [rsp+0C8h+var_70], eax
0x1400682ae  mov     rdi, [rsp+0C8h+arg_8]
0x1400682b6  mov     r13d, [rsp+0C8h+arg_18]
0x1400682be  mov     r14, [rsp+0C8h+var_58]
0x1400682c3  mov     r12, [rsp+0C8h+var_50]
0x1400682c8  mov     r15, [rsp+0C8h+var_48]
0x1400682d0  jmp     short loc_1400682E3
0x1400682d2  mov     ebx, 6
0x1400682d7  lea     rdx, aNoHnotifyremot; "No hNotifyRemote."
0x1400682de  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400682e3  test    ebx, ebx
0x1400682e5  jz      short loc_14006833F
0x1400682e7  mov     rax, [rsp+0C8h+var_40]
0x1400682ef  test    byte ptr [rax], 8
0x1400682f2  jnz     short loc_14006833F
0x1400682f4  mov     eax, [rdi+70h]
0x1400682f7  mov     dword ptr [rsp+0C8h+var_A0], eax; unsigned __int8 *
0x1400682fb  mov     rax, [r15]
0x1400682fe  mov     qword ptr [rsp+0C8h+var_A8], rax; unsigned int
0x140068303  mov     r9, rdi
0x140068306  mov     r8d, ebx
0x140068309  lea     rdx, aRpcErrorDPchan; "RPC error %d, pChange 0x%p, hNotifyRemo"...
0x140068310  lea     rcx, aThreadnotifypr; "ThreadNotifyProcessJob"
0x140068317  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006831c  mov     rcx, [r15]; void *
0x14006831f  call    ?CloseReplyRemote@@YAXPEAX@Z; CloseReplyRemote(void *)
0x140068324  mov     r8d, [rdi+70h]; void **
0x140068328  mov     rdx, r15; void **
0x14006832b  mov     rcx, [rdi+18h]; this
0x14006832f  call    ?OpenReplyRemote@@YAKPEAGPEAPEAXKKKPEAE@Z; OpenReplyRemote(ushort *,void * *,ulong,ulong,ulong,uchar *)
0x140068334  test    eax, eax
0x140068336  jz      short loc_14006833F
0x140068338  mov     qword ptr [r15], 0
0x14006833f  mov     ecx, cs:?dwThreadNotifySleep@@3KA; dwMilliseconds
0x140068345  call    cs:__imp_Sleep
0x14006834b  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x140068352  call    cs:__imp_EnterCriticalSection
0x140068358  mov     rax, [rsp+0C8h+var_38]
0x140068360  cmp     r13d, [rax]
0x140068363  jz      short loc_140068370
0x140068365  mov     [rsp+0C8h+arg_10], 0
0x140068370  mov     rcx, [rsp+0C8h+pInfo]
0x140068375  test    rcx, rcx
0x140068378  jz      loc_14006841A
0x14006837e  mov     r15, [r12]
0x140068382  test    ebx, ebx
0x140068384  jz      short loc_1400683D6
0x140068386  mov     [r12], rcx
0x14006838a  cmp     ebx, 6BFh
0x140068390  jz      short loc_1400683B3
0x140068392  mov     rdx, rdi; struct _CHANGE *
0x140068395  mov     rcx, [rsp+0C8h+pInfo]; struct _PRINTER_NOTIFY_INFO *
0x14006839a  call    ?ClearPrinterNotifyInfo@@YAXPEAU_PRINTER_NOTIFY_INFO@@PEAU_CHANGE@@@Z; ClearPrinterNotifyInfo(_PRINTER_NOTIFY_INFO *,_CHANGE *)
0x14006839f  mov     rdx, rdi; struct _CHANGE *
0x1400683a2  mov     rcx, [rsp+0C8h+pInfo]; struct _PRINTER_NOTIFY_INFO *
0x1400683a7  call    ?SetDiscardPrinterNotifyInfo@@YAXPEAU_PRINTER_NOTIFY_INFO@@PEAU_CHANGE@@@Z; SetDiscardPrinterNotifyInfo(_PRINTER_NOTIFY_INFO *,_CHANGE *)
0x1400683ac  test    r15, r15
0x1400683af  jz      short loc_14006841A
0x1400683b1  jmp     short loc_1400683CC
0x1400683b3  test    r15, r15
0x1400683b6  jz      short loc_14006841A
0x1400683b8  mov     rcx, [rdi+28h]; struct _PRINTHANDLE *
0x1400683bc  test    rcx, rcx
0x1400683bf  jz      short loc_1400683CC
0x1400683c1  mov     r8, r15; struct _PRINTER_NOTIFY_INFO *
0x1400683c4  mov     edx, r13d; unsigned int
0x1400683c7  call    ?AppendPrinterNotifyInfo@@YAKPEAU_PRINTHANDLE@@KPEAU_PRINTER_NOTIFY_INFO@@@Z; AppendPrinterNotifyInfo(_PRINTHANDLE *,ulong,_PRINTER_NOTIFY_INFO *)
0x1400683cc  mov     rcx, r15; pInfo
0x1400683cf  call    RouterFreePrinterNotifyInfo
0x1400683d4  jmp     short loc_14006841A
0x1400683d6  test    [rsp+0C8h+arg_10], 10000h
0x1400683e1  jz      short loc_1400683EF
0x1400683e3  or      dword ptr [r14], 18000h
0x1400683ea  mov     rcx, [rsp+0C8h+pInfo]; struct _PRINTER_NOTIFY_INFO *
0x1400683ef  test    r15, r15
0x1400683f2  jnz     short loc_140068407
0x1400683f4  mov     rdx, rdi; struct _CHANGE *
0x1400683f7  call    ?ClearPrinterNotifyInfo@@YAXPEAU_PRINTER_NOTIFY_INFO@@PEAU_CHANGE@@@Z; ClearPrinterNotifyInfo(_PRINTER_NOTIFY_INFO *,_CHANGE *)
0x1400683fc  mov     rax, [rsp+0C8h+pInfo]
0x140068401  mov     [r12], rax
0x140068405  jmp     short loc_14006840C
0x140068407  call    RouterFreePrinterNotifyInfo
0x14006840c  mov     rcx, [r12]
0x140068410  mov     eax, [rsp+0C8h+arg_10]
0x140068417  or      [rcx+4], eax
0x14006841a  btr     dword ptr [r14], 0Ah
0x14006841f  test    dword ptr [r14], 800h
0x140068426  jz      short loc_140068464
0x140068428  mov     rcx, rdi; struct _CHANGE *
0x14006842b  call    ?NotifyNeeded@@YAHPEAU_CHANGE@@@Z; NotifyNeeded(_CHANGE *)
0x140068430  test    eax, eax
0x140068432  jz      short loc_140068464
0x140068434  test    dword ptr [r14], 100h
0x14006843b  jnz     short loc_140068464
0x14006843d  mov     r9d, [rdi+14h]
0x140068441  mov     r8, rdi
0x140068444  lea     rdx, aDelayedLinkAdd; "Delayed link added, 0x%p, refcount %d."
0x14006844b  lea     rcx, aThreadnotifypr; "ThreadNotifyProcessJob"
0x140068452  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140068457  btr     dword ptr [r14], 0Bh
0x14006845c  mov     rcx, rdi; struct _CHANGE *
0x14006845f  call    ?LinkChange@@YAHPEAU_CHANGE@@@Z; LinkChange(_CHANGE *)
0x140068464  lea     rcx, [rdi+14h]; unsigned int *
0x140068468  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x14006846d  mov     r9d, [rdi+14h]
0x140068471  mov     r8, rdi
0x140068474  lea     rdx, aDone0xPRefcoun; "Done 0x%p, refcount %d."
0x14006847b  lea     rcx, aThreadnotifypr; "ThreadNotifyProcessJob"
0x140068482  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140068487  test    dword ptr [r14], 100h
0x14006848e  jz      short loc_1400684C0
0x140068490  mov     rbx, [rdi+78h]
0x140068494  mov     qword ptr [rdi+78h], 0
0x14006849c  lea     rcx, [rsp+0C8h+var_30]; struct _CHANGE **
0x1400684a4  call    ?FreeChange@@YAHPEAPEAU_CHANGE@@@Z; FreeChange(_CHANGE * *)
0x1400684a9  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x1400684b0  call    cs:__imp_LeaveCriticalSection
0x1400684b6  mov     rcx, rbx; void *
0x1400684b9  call    ?CloseReplyRemote@@YAXPEAX@Z; CloseReplyRemote(void *)
0x1400684be  jmp     short loc_1400684CD
0x1400684c0  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x1400684c7  call    cs:__imp_LeaveCriticalSection
0x1400684cd  xor     eax, eax
0x1400684cf  mov     rbx, [rsp+0C8h+arg_0]
0x1400684d7  add     rsp, 0A0h
0x1400684de  pop     r15
0x1400684e0  pop     r14
0x1400684e2  pop     r13
0x1400684e4  pop     r12
0x1400684e6  pop     rdi
0x1400684e7  retn
0x14007973a  push    rbp
0x14007973c  sub     rsp, 50h
0x140079740  mov     rbp, rdx
0x140079743  mov     rcx, [rcx]
0x140079746  mov     ecx, [rcx]; ExceptionCode
0x140079748  call    cs:__imp_I_RpcExceptionFilter
0x14007974e  nop
0x14007974f  add     rsp, 50h
0x140079753  pop     rbp
0x140079754  retn
```

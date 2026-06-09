# AutoProxyResolver::QueueAndWaitForDetections(unsigned __int64,unsigned __int64,StructStorage<tagProxySettings,ProxySettingsAllocator> *,int,ScriptHandler * *)

- ea: `0x180016da4`
- end: `0x180017519`
- name: `?QueueAndWaitForDetections@AutoProxyResolver@@AEAAJ_K0PEAV?$StructStorage@UtagProxySettings@@VProxySettingsAllocator@@@@HPEAPEAVScriptHandler@@@Z`
- size: `1909`
- prototype: `__int64 __usercall@<rax>(AutoProxyBase *this@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x180052c30`

## callees

- `0x180010f50`
- `0x180016da4`
- `0x180017520`
- `0x180054b54`
- `0x180055b30`
- `0x180055f84`
- `0x180067e28`
- `0x180090884`
- `0x1800a1d10`
- `0x1800cf58c`
- `0x1800d9b6c`
- `0x1800db704`
- `0x1800db758`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800170bf`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800170bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017147`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017147`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x180016e83`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x180016ee1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x180016f1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x18001728c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x180016e83`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x180016ee1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x180016f1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x18001728c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001721b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001724a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800172f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001721b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001724a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800172f9`

## pseudocode

```c
__int64 __fastcall AutoProxyResolver::QueueAndWaitForDetections(
        AutoProxyBase *this,
        __int64 a2,
        __int64 a3,
        volatile signed __int32 *a4,
        int a5,
        volatile signed __int32 **a6)
{
  struct RefCountContext *v6; // r12
  struct RefCountContext *v7; // r15
  __int64 v8; // r14
  struct AutoProxyTracker *v9; // rbx
  volatile signed __int32 *v10; // rdi
  volatile signed __int32 *v11; // rax
  AutoProxyBase *v12; // r13
  signed int TrackersFromSettings; // esi
  HANDLE Event; // rax
  struct RefCountContext *v15; // rdx
  int v16; // eax
  HANDLE v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  volatile signed __int32 *v23; // rsi
  void *v24; // rcx
  int v25; // edx
  int v26; // ecx
  int v27; // r8d
  struct RefCountContext *v28; // r8
  void *v29; // rcx
  unsigned int v30; // edx
  __int64 v31; // rax
  __int64 v32; // rdx
  DWORD v33; // eax
  int v34; // eax
  signed int v36; // eax
  signed int LastError; // eax
  signed int v38; // eax
  struct RefCountContext *v39; // rax
  signed int v40; // eax
  char *v41; // rdx
  HANDLE v43; // [rsp+48h] [rbp-71h]
  int v44; // [rsp+48h] [rbp-71h]
  __int64 v45; // [rsp+50h] [rbp-69h] BYREF
  struct RefCountContext *v46; // [rsp+58h] [rbp-61h]
  struct AutoProxyTracker *v47; // [rsp+60h] [rbp-59h] BYREF
  struct RefCountContext *v48; // [rsp+68h] [rbp-51h] BYREF
  void *v49; // [rsp+70h] [rbp-49h]
  volatile signed __int32 *v50; // [rsp+78h] [rbp-41h] BYREF
  volatile signed __int32 *v51; // [rsp+80h] [rbp-39h]
  __int64 v52; // [rsp+88h] [rbp-31h]
  __int64 v53; // [rsp+90h] [rbp-29h]
  void *v54; // [rsp+98h] [rbp-21h]
  volatile signed __int32 **v55; // [rsp+A0h] [rbp-19h]
  HANDLE Handles[2]; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v57; // [rsp+B8h] [rbp-1h]

  v6 = 0;
  v7 = 0;
  v53 = a3;
  v8 = 0;
  v52 = a2;
  v9 = 0;
  v55 = a6;
  v10 = 0;
  v11 = a4;
  v50 = 0;
  v51 = a4;
  v12 = this;
  v46 = 0;
  v48 = 0;
  v45 = 0;
  v47 = 0;
  *(_OWORD *)Handles = 0;
  v57 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    WPP_SF_q(1029, 14, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids);
    v11 = v51;
  }
  if ( !a6 )
  {
    TrackersFromSettings = -2147024809;
    goto LABEL_55;
  }
  *a6 = 0;
  if ( !v11 )
  {
    TrackersFromSettings = -2147024809;
    goto LABEL_55;
  }
  TrackersFromSettings = AutoProxyResolver::CreateTrackersFromSettings(v12, (__int64)&v48, (__int64)&v45);
  if ( TrackersFromSettings < 0 )
    goto LABEL_87;
  Event = CreateEventExA(0, 0, 1u, 0x100002u);
  v49 = Event;
  if ( !Event )
  {
    LastError = GetLastError();
    TrackersFromSettings = LastError;
    if ( LastError > 0 )
      TrackersFromSettings = (unsigned __int16)LastError | 0x80070000;
    v12 = this;
    if ( TrackersFromSettings >= 0 )
      TrackersFromSettings = -2147418113;
LABEL_87:
    v7 = v48;
    v6 = v46;
LABEL_88:
    v8 = v45;
    goto LABEL_55;
  }
  v6 = v46;
  v15 = v46;
  *((_QWORD *)v46 + 8) = Event;
  v16 = QueueRefCountWorkItem((int (*)(struct RefCountContext *))IpAddressWpad, v15);
  v7 = v48;
  TrackersFromSettings = v16;
  if ( v16 < 0 )
    goto LABEL_95;
  v46 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 30) + 8LL) )
  {
    v39 = (struct RefCountContext *)CreateEventExA(0, 0, 1u, 0x100002u);
    v46 = v39;
    if ( !v39 )
    {
      v40 = GetLastError();
      TrackersFromSettings = v40;
      if ( v40 > 0 )
        TrackersFromSettings = (unsigned __int16)v40 | 0x80070000;
      if ( TrackersFromSettings >= 0 )
        TrackersFromSettings = -2147418113;
      goto LABEL_95;
    }
    *((_QWORD *)v7 + 10) = v39;
    TrackersFromSettings = QueueRefCountWorkItem((int (*)(struct RefCountContext *))SwpadWpad, v7);
    if ( TrackersFromSettings < 0 )
    {
LABEL_95:
      v12 = this;
      goto LABEL_88;
    }
  }
  v17 = CreateEventExA(0, 0, 1u, 0x100002u);
  v54 = v17;
  if ( !v17 )
  {
    v36 = GetLastError();
    TrackersFromSettings = v36;
    if ( v36 > 0 )
      TrackersFromSettings = (unsigned __int16)v36 | 0x80070000;
    if ( TrackersFromSettings >= 0 )
      TrackersFromSettings = -2147418113;
    goto LABEL_95;
  }
  v8 = v45;
  *(_QWORD *)(v45 + 88) = v17;
  TrackersFromSettings = AutoProxyTracker::CreateInstance(&v47);
  if ( TrackersFromSettings < 0 )
  {
LABEL_99:
    v9 = v47;
LABEL_100:
    v12 = this;
    goto LABEL_55;
  }
  v43 = CreateEventExA(0, 0, 1u, 0x100002u);
  if ( !v43 )
  {
    v38 = GetLastError();
    TrackersFromSettings = v38;
    if ( v38 > 0 )
      TrackersFromSettings = (unsigned __int16)v38 | 0x80070000;
    if ( TrackersFromSettings >= 0 )
      TrackersFromSettings = -2147418113;
    goto LABEL_99;
  }
  v9 = v47;
  if ( v6 )
    (**(void (__fastcall ***)(struct RefCountContext *))v6)(v6);
  v18 = *((_QWORD *)v9 + 2);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  *((_QWORD *)v9 + 2) = v6;
  if ( v7 )
    (**(void (__fastcall ***)(struct RefCountContext *))v7)(v7);
  v19 = *((_QWORD *)v9 + 3);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
  *((_QWORD *)v9 + 3) = v7;
  if ( v8 )
    (**(void (__fastcall ***)(__int64))v8)(v8);
  v20 = *((_QWORD *)v9 + 4);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
  *((_QWORD *)v9 + 4) = v8;
  (*(void (__fastcall **)(AutoProxyBase *))(*(_QWORD *)this + 8LL))(this);
  v21 = *((_QWORD *)v9 + 6);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v22 = v52;
  *((_QWORD *)v9 + 6) = this;
  v23 = v51;
  *((_QWORD *)v9 + 8) = v22;
  *((_QWORD *)v9 + 9) = v53;
  _InterlockedAdd(v23, 1u);
  v24 = (void *)*((_QWORD *)v9 + 7);
  if ( v24 )
    StructStorage<tagProxySettings,ProxySettingsAllocator>::Release(v24);
  *((_QWORD *)v9 + 7) = v23;
  WxEtwGetActivityId((struct _GUID *)((char *)v9 + 84));
  *((_QWORD *)v9 + 13) = v43;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qqqqq(
      v26,
      v25,
      v27,
      (_DWORD)this,
      (__int64)v9,
      *((_QWORD *)v9 + 2),
      *((_QWORD *)v9 + 3),
      *((_QWORD *)v9 + 4));
  TrackersFromSettings = QueueRefCountWorkItem((int (*)(struct RefCountContext *))AutoProxyWpadAndResultThread, v9);
  if ( TrackersFromSettings < 0 )
    goto LABEL_100;
  TrackersFromSettings = 0;
LABEL_32:
  v28 = v46;
LABEL_33:
  v29 = v49;
  if ( v49 )
  {
    Handles[0] = v49;
    goto LABEL_35;
  }
  while ( 1 )
  {
    v49 = v29;
LABEL_35:
    LODWORD(v48) = -(v29 == 0);
    v30 = v29 != 0;
    if ( v28 )
    {
      LODWORD(v47) = v29 != 0;
      ++v30;
      Handles[v29 != 0] = v28;
    }
    else
    {
      LODWORD(v47) = -1;
    }
    v31 = v30;
    LODWORD(v45) = v30;
    v32 = v30 + 1;
    v44 = v32;
    Handles[v31] = v54;
    Handles[v32] = (HANDLE)*((_QWORD *)this + 64);
    v33 = WaitForMultipleObjectsEx(v32 + 1, Handles, 0, 0xFFFFFFFF, 0);
    if ( v33 != (_DWORD)v48 )
    {
      if ( v33 == (_DWORD)v47 )
      {
        if ( (xmmword_180107A60 & 0x20) != 0 )
          WPP_SF_qqD(1029, 17, (unsigned int)WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids, (_DWORD)this, (__int64)v9);
        v34 = *((_DWORD *)v7 + 3);
        if ( v34 == 1 )
        {
          v28 = 0;
          v46 = 0;
          goto LABEL_33;
        }
        if ( v34 < 0 )
          goto LABEL_90;
        v41 = (char *)v7 + 56;
LABEL_113:
        AutoInterface<ScriptHandler>::operator=(&v50, v41);
        v10 = v50;
        goto LABEL_53;
      }
      if ( v33 == (_DWORD)v45 )
      {
        if ( (xmmword_180107A60 & 0x20) != 0 )
          WPP_SF_qqD(1029, 18, (unsigned int)WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids, (_DWORD)this, (__int64)v9);
        if ( *(int *)(v8 + 12) < 0 )
        {
          TrackersFromSettings = *(_DWORD *)(v8 + 12);
          goto LABEL_53;
        }
        v41 = (char *)(v8 + 64);
        goto LABEL_113;
      }
      if ( v33 == v44 )
      {
        if ( (xmmword_180107A60 & 0x20) != 0 )
          WPP_SF_qq(1029, 19, (unsigned int)WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids, (_DWORD)this, (__int64)v9);
        _InterlockedExchange((volatile __int32 *)v6 + 24, 1);
        _InterlockedExchange((volatile __int32 *)(v8 + 116), 1);
        if ( v7 )
          _InterlockedExchange((volatile __int32 *)v7 + 28, 1);
        TrackersFromSettings = -2146685199;
        goto LABEL_53;
      }
      goto LABEL_32;
    }
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_qqD(1029, 16, (unsigned int)WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids, (_DWORD)this, (__int64)v9);
    v34 = *((_DWORD *)v6 + 3);
    if ( v34 != 1 )
      break;
    v28 = v46;
    v29 = 0;
  }
  if ( v34 < 0 )
  {
LABEL_90:
    TrackersFromSettings = v34;
    goto LABEL_53;
  }
  v10 = (volatile signed __int32 *)*((_QWORD *)v6 + 7);
  if ( v10 )
    _InterlockedAdd(v10, 1u);
LABEL_53:
  SetEvent(*((HANDLE *)v9 + 13));
  v12 = this;
  if ( TrackersFromSettings >= 0 )
  {
    *v55 = v10;
    v10 = 0;
  }
LABEL_55:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qD(1029, 20, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids, v12);
  if ( v10 )
    ScriptHandler::Release((ScriptHandler *)v10);
  if ( v9 )
    (*(void (__fastcall **)(struct AutoProxyTracker *))(*(_QWORD *)v9 + 8LL))(v9);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  if ( v7 )
    (*(void (__fastcall **)(struct RefCountContext *))(*(_QWORD *)v7 + 8LL))(v7);
  if ( v6 )
    (*(void (__fastcall **)(struct RefCountContext *))(*(_QWORD *)v6 + 8LL))(v6);
  return (unsigned int)TrackersFromSettings;
}

```

## disassembly

```asm
0x180016da4  mov     [rsp-8+arg_8], rbx
0x180016da9  push    rbp
0x180016daa  push    rsi
0x180016dab  push    rdi
0x180016dac  push    r12
0x180016dae  push    r13
0x180016db0  push    r14
0x180016db2  push    r15
0x180016db4  lea     rbp, [rsp-17h]
0x180016db9  sub     rsp, 0D0h
0x180016dc0  mov     rax, cs:__security_cookie
0x180016dc7  xor     rax, rsp
0x180016dca  mov     [rbp+47h+var_38], rax
0x180016dce  mov     rsi, [rbp+47h+arg_28]
0x180016dd2  xor     r12d, r12d
0x180016dd5  xor     r15d, r15d
0x180016dd8  mov     [rbp+47h+var_70], r8
0x180016ddc  xor     r14d, r14d
0x180016ddf  mov     [rbp+47h+var_78], rdx
0x180016de3  xor     ebx, ebx
0x180016de5  mov     [rbp+47h+var_C0], rcx
0x180016de9  xorps   xmm0, xmm0
0x180016dec  mov     [rbp+47h+var_60], rsi
0x180016df0  xor     edi, edi
0x180016df2  mov     [rbp+47h+var_B4], 0
0x180016df9  mov     rax, r9
0x180016dfc  mov     [rbp+47h+var_88], rdi
0x180016e00  mov     [rbp+47h+var_80], rax
0x180016e04  mov     r13, rcx
0x180016e07  mov     [rbp+47h+var_A8], r12
0x180016e0b  mov     [rbp+47h+var_98], r15
0x180016e0f  mov     [rbp+47h+var_B0], r14
0x180016e13  mov     [rbp+47h+var_A0], rbx
0x180016e17  movups  xmmword ptr [rbp+47h+Handles], xmm0
0x180016e1b  movups  [rbp+47h+var_48], xmm0
0x180016e1f  test    byte ptr cs:xmmword_180107A60, 20h
0x180016e26  jnz     loc_1800173AA
0x180016e2c  test    rsi, rsi
0x180016e2f  jz      loc_1800172C1
0x180016e35  mov     [rsi], rbx
0x180016e38  test    rax, rax
0x180016e3b  jz      loc_1800173CC
0x180016e41  mov     r8d, [rbp+47h+arg_20]
0x180016e45  lea     rcx, [rbp+47h+var_B0]
0x180016e49  mov     [rsp+100h+var_D8], rcx; __int64
0x180016e4e  lea     r9, [rbp+47h+var_A8]
0x180016e52  lea     rcx, [rbp+47h+var_98]
0x180016e56  mov     rdx, rax
0x180016e59  mov     qword ptr [rsp+100h+bAlertable], rcx; __int64
0x180016e5e  mov     rcx, r13; this
0x180016e61  call    ?CreateTrackersFromSettings@AutoProxyResolver@@AEAAJPEAV?$StructStorage@UtagProxySettings@@VProxySettingsAllocator@@@@HPEAPEAVIpAddressWpadTracker@@PEAPEAVSwpadWpadTracker@@PEAPEAVWpadDetectionTracker@@@Z; AutoProxyResolver::CreateTrackersFromSettings(StructStorage<tagProxySettings,ProxySettingsAllocator> *,int,IpAddressWpadTracker * *,SwpadWpadTracker * *,WpadDetectionTracker * *)
0x180016e66  mov     esi, eax
0x180016e68  test    eax, eax
0x180016e6a  js      loc_1800172D2
0x180016e70  mov     r13d, 1
0x180016e76  mov     r9d, 100002h; dwDesiredAccess
0x180016e7c  mov     r8d, r13d; dwFlags
0x180016e7f  xor     edx, edx; lpName
0x180016e81  xor     ecx, ecx; lpEventAttributes
0x180016e83  call    cs:__imp_CreateEventExA
0x180016e89  mov     [rbp+47h+var_90], rax
0x180016e8d  test    rax, rax
0x180016e90  jz      loc_18001721B
0x180016e96  mov     r12, [rbp+47h+var_A8]
0x180016e9a  lea     rcx, ?IpAddressWpad@@YAJPEAVRefCountContext@@@Z; int (*)(struct RefCountContext *)
0x180016ea1  mov     rdx, r12; struct RefCountContext *
0x180016ea4  mov     [r12+40h], rax
0x180016ea9  call    ?QueueRefCountWorkItem@@YAJP6AJPEAVRefCountContext@@@Z0@Z; QueueRefCountWorkItem(long (*)(RefCountContext *),RefCountContext *)
0x180016eae  mov     r15, [rbp+47h+var_98]
0x180016eb2  mov     esi, eax
0x180016eb4  test    eax, eax
0x180016eb6  js      loc_1800173DD
0x180016ebc  mov     r9, [rbp+47h+var_C0]
0x180016ec0  mov     [rbp+47h+var_A8], rbx
0x180016ec4  mov     rax, [r9+0F0h]
0x180016ecb  cmp     [rax+8], ebx
0x180016ece  jnz     loc_18001727F
0x180016ed4  mov     r9d, 100002h; dwDesiredAccess
0x180016eda  mov     r8d, r13d; dwFlags
0x180016edd  xor     edx, edx; lpName
0x180016edf  xor     ecx, ecx; lpEventAttributes
0x180016ee1  call    cs:__imp_CreateEventExA
0x180016ee7  mov     [rbp+47h+var_68], rax
0x180016eeb  test    rax, rax
0x180016eee  jz      loc_1800171F0
0x180016ef4  mov     r14, [rbp+47h+var_B0]
0x180016ef8  lea     rcx, [rbp+47h+var_A0]; struct AutoProxyTracker **
0x180016efc  mov     [r14+58h], rax
0x180016f00  call    ?CreateInstance@AutoProxyTracker@@SAJPEAPEAV1@@Z; AutoProxyTracker::CreateInstance(AutoProxyTracker * *)
0x180016f05  mov     esi, eax
0x180016f07  test    eax, eax
0x180016f09  js      loc_18001733B
0x180016f0f  mov     r9d, 100002h; dwDesiredAccess
0x180016f15  mov     r8d, r13d; dwFlags
0x180016f18  xor     edx, edx; lpName
0x180016f1a  xor     ecx, ecx; lpEventAttributes
0x180016f1c  call    cs:__imp_CreateEventExA
0x180016f22  mov     [rbp-71h], rax
0x180016f26  test    rax, rax
0x180016f29  jz      loc_18001724A
0x180016f2f  mov     rbx, [rbp+47h+var_A0]
0x180016f33  test    r12, r12
0x180016f36  jz      short loc_180016F47
0x180016f38  mov     rcx, [r12]
0x180016f3c  mov     rax, [rcx]
0x180016f3f  mov     rcx, r12
0x180016f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f47  mov     rcx, [rbx+10h]
0x180016f4b  test    rcx, rcx
0x180016f4e  jz      short loc_180016F5C
0x180016f50  mov     rax, [rcx]
0x180016f53  mov     rax, [rax+8]
0x180016f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f5c  mov     [rbx+10h], r12
0x180016f60  test    r15, r15
0x180016f63  jz      short loc_180016F73
0x180016f65  mov     rax, [r15]
0x180016f68  mov     rcx, r15
0x180016f6b  mov     rax, [rax]
0x180016f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f73  mov     rcx, [rbx+18h]
0x180016f77  test    rcx, rcx
0x180016f7a  jz      short loc_180016F88
0x180016f7c  mov     rax, [rcx]
0x180016f7f  mov     rax, [rax+8]
0x180016f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f88  mov     [rbx+18h], r15
0x180016f8c  test    r14, r14
0x180016f8f  jz      short loc_180016F9F
0x180016f91  mov     rax, [r14]
0x180016f94  mov     rcx, r14
0x180016f97  mov     rax, [rax]
0x180016f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f9f  mov     rcx, [rbx+20h]
0x180016fa3  test    rcx, rcx
0x180016fa6  jz      short loc_180016FB4
0x180016fa8  mov     rax, [rcx]
0x180016fab  mov     rax, [rax+8]
0x180016faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fb4  mov     rsi, [rbp+47h+var_C0]
0x180016fb8  mov     [rbx+20h], r14
0x180016fbc  mov     rcx, rsi
0x180016fbf  mov     rax, [rsi]
0x180016fc2  mov     rax, [rax+8]
0x180016fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fcb  mov     rcx, [rbx+30h]
0x180016fcf  test    rcx, rcx
0x180016fd2  jz      short loc_180016FE0
0x180016fd4  mov     rax, [rcx]
0x180016fd7  mov     rax, [rax+10h]
0x180016fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe0  mov     rax, [rbp+47h+var_78]
0x180016fe4  mov     [rbx+30h], rsi
0x180016fe8  mov     rsi, [rbp+47h+var_80]
0x180016fec  mov     [rbx+40h], rax
0x180016ff0  mov     rax, [rbp+47h+var_70]
0x180016ff4  mov     [rbx+48h], rax
0x180016ff8  lock add [rsi], r13d
0x180016ffc  mov     rcx, [rbx+38h]; void *
0x180017000  test    rcx, rcx
0x180017003  jnz     loc_180017275
0x180017009  lea     rcx, [rbx+54h]; struct _GUID *
0x18001700d  mov     [rbx+38h], rsi
0x180017011  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x180017016  mov     rax, [rbp-71h]
0x18001701a  mov     [rbx+68h], rax
0x18001701e  test    byte ptr cs:xmmword_180107A60, 20h
0x180017025  jnz     loc_1800173E9
0x18001702b  mov     rdx, rbx; struct RefCountContext *
0x18001702e  lea     rcx, ?AutoProxyWpadAndResultThread@@YAJPEAVRefCountContext@@@Z; int (*)(struct RefCountContext *)
0x180017035  call    ?QueueRefCountWorkItem@@YAJP6AJPEAVRefCountContext@@@Z0@Z; QueueRefCountWorkItem(long (*)(RefCountContext *),RefCountContext *)
0x18001703a  mov     esi, eax
0x18001703c  test    eax, eax
0x18001703e  js      loc_180017393
0x180017044  xor     esi, esi
0x180017046  mov     r8, [rbp+47h+var_A8]
0x18001704a  mov     rcx, [rbp+47h+var_90]
0x18001704e  mov     [rbp+47h+var_90], rcx
0x180017052  test    rcx, rcx
0x180017055  jz      loc_180017116
0x18001705b  mov     [rbp+47h+Handles], rcx
0x18001705f  mov     rax, rcx
0x180017062  neg     rax
0x180017065  sbb     eax, eax
0x180017067  xor     edx, edx
0x180017069  test    rcx, rcx
0x18001706c  not     eax
0x18001706e  mov     dword ptr [rbp+47h+var_98], eax
0x180017071  setnz   dl
0x180017074  test    r8, r8
0x180017077  jz      loc_18001734F
0x18001707d  mov     eax, edx
0x18001707f  mov     dword ptr [rbp+47h+var_A0], edx
0x180017082  inc     edx
0x180017084  mov     [rbp+rax*8+47h+Handles], r8
0x180017089  mov     rcx, [rbp+47h+var_68]
0x18001708d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180017091  mov     eax, edx
0x180017093  xor     r8d, r8d; bWaitAll
0x180017096  mov     dword ptr [rbp+47h+var_B0], edx
0x180017099  add     edx, r13d
0x18001709c  mov     [rbp+47h+var_B8], edx
0x18001709f  mov     [rsp+100h+bAlertable], esi; bAlertable
0x1800170a3  mov     [rbp+rax*8+47h+Handles], rcx
0x1800170a8  mov     rax, [rbp+47h+var_C0]
0x1800170ac  lea     ecx, [rdx+1]; nCount
0x1800170af  mov     rax, [rax+200h]
0x1800170b6  mov     [rbp+rdx*8+47h+Handles], rax
0x1800170bb  lea     rdx, [rbp+47h+Handles]; lpHandles
0x1800170bf  call    cs:__imp_WaitForMultipleObjectsEx
0x1800170c5  cmp     eax, dword ptr [rbp+47h+var_98]
0x1800170c8  jz      short loc_1800170F5
0x1800170ca  cmp     eax, dword ptr [rbp+47h+var_A0]
0x1800170cd  jnz     short loc_18001711F
0x1800170cf  test    byte ptr cs:xmmword_180107A60, 20h
0x1800170d6  jnz     loc_180017444
0x1800170dc  mov     eax, [r15+0Ch]
0x1800170e0  cmp     eax, r13d
0x1800170e3  jnz     loc_1800172EA
0x1800170e9  xor     r8d, r8d
0x1800170ec  mov     [rbp+47h+var_A8], r8
0x1800170f0  jmp     loc_18001704A
0x1800170f5  test    byte ptr cs:xmmword_180107A60, 20h
0x1800170fc  jnz     loc_180017417
0x180017102  mov     eax, [r12+0Ch]
0x180017107  cmp     eax, r13d
0x18001710a  jnz     loc_180017320
0x180017110  mov     r8, [rbp+47h+var_A8]
0x180017114  xor     ecx, ecx
0x180017116  mov     [rbp+47h+var_90], rcx
0x18001711a  jmp     loc_18001705F
0x18001711f  cmp     eax, dword ptr [rbp+47h+var_B0]
0x180017122  jnz     loc_18001735B
0x180017128  test    byte ptr cs:xmmword_180107A60, 20h
0x18001712f  jnz     loc_1800174B0
0x180017135  cmp     [r14+0Ch], esi
0x180017139  jge     loc_180017476
0x18001713f  mov     esi, [r14+0Ch]
0x180017143  mov     rcx, [rbx+68h]; hEvent
0x180017147  call    cs:__imp_SetEvent
0x18001714d  mov     r13, [rbp+47h+var_C0]
0x180017151  test    esi, esi
0x180017153  jns     loc_1800174DC
0x180017159  mov     [rbp+47h+var_B4], 218h
0x180017160  test    byte ptr cs:xmmword_180107A60, 20h
0x180017167  jnz     loc_1800174EA
0x18001716d  test    rdi, rdi
0x180017170  jnz     loc_18001750C
0x180017176  test    rbx, rbx
0x180017179  jz      short loc_18001718A
0x18001717b  mov     rax, [rbx]
0x18001717e  mov     rcx, rbx
0x180017181  mov     rax, [rax+8]
0x180017185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001718a  test    r14, r14
0x18001718d  jz      short loc_18001719E
0x18001718f  mov     rax, [r14]
0x180017192  mov     rcx, r14
0x180017195  mov     rax, [rax+8]
0x180017199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001719e  test    r15, r15
0x1800171a1  jz      short loc_1800171B2
0x1800171a3  mov     rax, [r15]
0x1800171a6  mov     rcx, r15
0x1800171a9  mov     rax, [rax+8]
0x1800171ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171b2  test    r12, r12
0x1800171b5  jz      short loc_1800171C7
0x1800171b7  mov     rdx, [r12]
0x1800171bb  mov     rcx, r12
0x1800171be  mov     rax, [rdx+8]
0x1800171c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171c7  mov     eax, esi
0x1800171c9  mov     rcx, [rbp+47h+var_38]
0x1800171cd  xor     rcx, rsp; StackCookie
0x1800171d0  call    __security_check_cookie
0x1800171d5  mov     rbx, [rsp+100h+arg_8]
0x1800171dd  add     rsp, 0D0h
0x1800171e4  pop     r15
0x1800171e6  pop     r14
0x1800171e8  pop     r13
0x1800171ea  pop     r12
0x1800171ec  pop     rdi
0x1800171ed  pop     rsi
0x1800171ee  pop     rbp
0x1800171ef  retn
0x1800171f0  call    cs:__imp_GetLastError
0x1800171f6  mov     esi, eax
0x1800171f8  test    eax, eax
0x1800171fa  jle     short loc_180017205
0x1800171fc  movzx   esi, ax
0x1800171ff  or      esi, 80070000h
0x180017205  test    esi, esi
0x180017207  mov     [rbp+47h+var_B4], 175h
0x18001720e  mov     eax, 8000FFFFh
0x180017213  cmovns  esi, eax
0x180017216  jmp     loc_18001731A
0x18001721b  call    cs:__imp_GetLastError
0x180017221  mov     esi, eax
0x180017223  test    eax, eax
  ... truncated ...
```

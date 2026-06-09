# CWcnSession::StartConnect(IWcnTransportPeer *,tagWcnTransportId,ulong,CWcnSession::tagWCN_SESSION_CONNECT_REASON)

- ea: `0x180018204`
- end: `0x1800187fe`
- name: `?StartConnect@CWcnSession@@QEAAJPEAVIWcnTransportPeer@@W4tagWcnTransportId@@KW4tagWCN_SESSION_CONNECT_REASON@1@@Z`
- size: `1530`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c2bc`
- `0x1800362c0`
- `0x1800408dc`
- `0x1800496c0`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180016118`
- `0x180016d20`
- `0x180018204`
- `0x180018c6c`
- `0x180019808`
- `0x18002ba28`
- `0x18002bce8`
- `0x180053004`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001878d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001878d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800183fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018703`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800183fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018703`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018450`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800184da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018726`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018450`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800184da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018726`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018507`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018507`

## pseudocode

```c
__int64 __fastcall CWcnSession::StartConnect(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  int v6; // r13d
  _QWORD *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  const char *v13; // rax
  __int64 v14; // r10
  int v15; // eax
  unsigned int v16; // r15d
  __int64 v17; // rax
  int updated; // ebx
  const char *v19; // rax
  __int64 v20; // r10
  unsigned int *v21; // r12
  _QWORD *v22; // rsi
  _QWORD *v23; // r14
  void (__fastcall ***v24)(_QWORD, __int64); // rcx
  void (__fastcall ***v25)(_QWORD, __int64); // rcx
  __int64 v26; // rax
  struct _TP_TIMER *v27; // rcx
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // eax
  __int64 v31; // r10
  int v32; // ebx
  char v33; // al
  unsigned int v34; // r8d
  __int64 v35; // rax
  __int64 v36; // r8
  unsigned int v37; // eax
  __int64 v38; // r10
  bool v39; // [rsp+30h] [rbp-71h] BYREF
  bool v40; // [rsp+31h] [rbp-70h] BYREF
  int v41; // [rsp+38h] [rbp-69h] BYREF
  int v42; // [rsp+40h] [rbp-61h] BYREF
  struct _FILETIME pftDueTime; // [rsp+48h] [rbp-59h] BYREF
  __int64 v44; // [rsp+50h] [rbp-51h]
  __int128 v45; // [rsp+58h] [rbp-49h] BYREF
  _BYTE v46[16]; // [rsp+70h] [rbp-31h] BYREF
  __int64 v47; // [rsp+80h] [rbp-21h]
  __int64 v48; // [rsp+88h] [rbp-19h]
  int *v49; // [rsp+90h] [rbp-11h]
  __int64 v50; // [rsp+98h] [rbp-9h]
  int *v51; // [rsp+A0h] [rbp-1h]
  __int64 v52; // [rsp+A8h] [rbp+7h]

  v44 = a2;
  v39 = 1;
  v40 = 1;
  pftDueTime = 0;
  v6 = a3;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 21, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_s(v9[2], 22, WPP_a137d119f5dc35a130051116e3170526_Traceguids, "pTransportPeer");
    return 2147500035LL;
  }
  if ( (unsigned int)(v6 - 5) <= 1 && (a4 & 0x8000) != 0 && v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 25) >= 3u )
  {
    v13 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v14 + 16), 23, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v13);
  }
  if ( (a4 & 0xB000) == 0 )
  {
    if ( v6 == 5 )
      goto LABEL_21;
    if ( v6 == 6 )
      goto LABEL_20;
    if ( !*(_BYTE *)(a1 + 432) )
    {
      a4 |= 0x8000u;
      goto LABEL_22;
    }
    if ( *(_BYTE *)(a1 + 1480) )
LABEL_20:
      a4 |= 0x1000u;
    else
LABEL_21:
      a4 |= 0x2000u;
  }
LABEL_22:
  v15 = a4 | 0x100000;
  if ( !*(_BYTE *)(a1 + 433) )
    v15 = a4;
  v16 = v15 | 0x200000;
  if ( !*(_BYTE *)(a1 + 434) )
    v16 = v15;
  v41 = v16 & 0x8000;
  if ( (v16 & 0x8000) != 0 || (v16 & 1) != 0 )
    *(_BYTE *)(a1 + 435) = 1;
  v17 = *(_QWORD *)(a1 + 32);
  v45 = 0;
  v45 = *(_OWORD *)(v17 + 152);
  if ( (Microsoft_Windows_WCN_Config_RegistrarEnableBits & 1) != 0 )
  {
    v42 = a5;
    v52 = 4;
    v47 = a1 + 1576;
    v48 = 16;
    v49 = (int *)&v45;
    v51 = &v42;
    v50 = 16;
    McGenEventWrite_EtwEventWriteTransfer(WCN_ETW_EVENT_GUID_Context, (__int64)SessionBegin, a3, 4, (__int64)v46);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 32) + 16LL));
  if ( *(_QWORD *)(*(_QWORD *)(a1 + 32) + 112LL) )
  {
    updated = -2147024713;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v20 + 16), 24, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v19);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 32) + 16LL));
    v21 = (unsigned int *)(a1 + 208);
    v22 = (_QWORD *)(a1 + 200);
    v23 = (_QWORD *)(a1 + 216);
    goto LABEL_65;
  }
  v22 = (_QWORD *)(a1 + 200);
  v24 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 200);
  if ( v24 )
  {
    (**v24)(v24, 1);
    *v22 = 0;
  }
  v23 = (_QWORD *)(a1 + 216);
  v25 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 216);
  if ( v25 )
  {
    (**v25)(v25, 1);
    *v23 = 0;
  }
  v26 = *(_QWORD *)(a1 + 32);
  *(_DWORD *)(a1 + 224) = 1;
  *(_DWORD *)(a1 + 20) = 0;
  *(_DWORD *)(a1 + 24) = -2147467259;
  *(_QWORD *)(v26 + 112) = a1;
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 32) + 16LL));
  v27 = *(struct _TP_TIMER **)(a1 + 232);
  v21 = (unsigned int *)(a1 + 208);
  *(_DWORD *)(a1 + 208) = v6;
  pftDueTime = (struct _FILETIME)-1200000000LL;
  SetThreadpoolTimer(v27, &pftDueTime, 0, 0x3E8u);
  updated = CWcnSession::UpdateSelfIdentity((CWcnSession *)a1, v16);
  if ( updated < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_65;
    v29 = 25;
LABEL_64:
    WPP_SF_d(v28[2], v29, WPP_a137d119f5dc35a130051116e3170526_Traceguids, (unsigned int)updated);
LABEL_65:
    if ( *(_BYTE *)(a1 + 436) )
    {
      CWcnTransportManager::DisableSpecialAdvertisements(*((CWcnTransportManager **)g_pWcnService + 7), *v21);
      *(_BYTE *)(a1 + 436) = 0;
    }
    if ( *v22 )
    {
      (**(void (__fastcall ***)(_QWORD, __int64))*v22)(*v22, 1);
      *v22 = 0;
    }
    if ( *v23 )
    {
      (**(void (__fastcall ***)(_QWORD, __int64))*v23)(*v23, 1);
      *v23 = 0;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 32) + 16LL));
    v35 = *(_QWORD *)(a1 + 32);
    *(_DWORD *)(a1 + 224) = 0;
    if ( *(_QWORD *)(v35 + 112) == a1 )
      *(_QWORD *)(v35 + 112) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 32) + 16LL));
    if ( (Microsoft_Windows_WCN_Config_RegistrarEnableBits & 2) != 0 )
    {
      v41 = updated;
      v47 = a1 + 1576;
      v48 = 16;
      v49 = &v41;
      v50 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        WCN_ETW_EVENT_GUID_Context,
        (__int64)SessionEndFailure,
        v36,
        3,
        (__int64)v46);
    }
    goto LABEL_76;
  }
  updated = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 32) + 120LL) + 8LL))(
              *(_QWORD *)(*(_QWORD *)(a1 + 32) + 120LL),
              a1,
              a1 + 216);
  if ( updated < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_65;
    v29 = 26;
    goto LABEL_64;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v30 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v31 + 16), 27, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v30, v16);
  }
  if ( !v41 && (v16 & 1) == 0 )
  {
    v32 = 16396;
    GetConfigMethodSetting(&v39, &v40);
    if ( v39 )
      v32 = 24588;
    v33 = IsNfcSupported();
    v34 = v32 | 0x70;
    if ( !v33 )
      v34 = v32;
    if ( !*(_BYTE *)(a1 + 433) )
      v34 = v40 ? 1664 : 640;
    CWcnTransportManager::EnableSpecialAdvertisements(
      *((CWcnTransportManager **)g_pWcnService + 7),
      *v21,
      v34,
      (struct CWcnSession *)a1);
    *(_BYTE *)(a1 + 436) = 1;
  }
  updated = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v44 + 8LL))(
              v44,
              a1,
              v16,
              a1 + 200);
  if ( updated < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_65;
    v29 = 28;
    goto LABEL_64;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 1592));
LABEL_76:
  SetEvent(*(HANDLE *)(a1 + 256));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (updated < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v37 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v38 + 16), 29, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v37, updated);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180018204  mov     [rsp-8+arg_10], rbx
0x180018209  push    rbp
0x18001820a  push    rsi
0x18001820b  push    rdi
0x18001820c  push    r12
0x18001820e  push    r13
0x180018210  push    r14
0x180018212  push    r15
0x180018214  lea     rbp, [rsp-1Fh]
0x180018219  sub     rsp, 0C0h
0x180018220  mov     rax, cs:__security_cookie
0x180018227  xor     rax, rsp
0x18001822a  mov     [rbp+4Fh+var_40], rax
0x18001822e  mov     r14d, 1
0x180018234  mov     [rbp+4Fh+var_A0], rdx
0x180018238  xor     r12d, r12d
0x18001823b  mov     [rbp+4Fh+var_C0], r14b
0x18001823f  mov     [rbp+4Fh+var_BF], r14b
0x180018243  mov     ebx, r9d
0x180018246  mov     qword ptr [rbp+4Fh+pftDueTime.dwLowDateTime], r12
0x18001824a  mov     r13d, r8d
0x18001824d  mov     rsi, rdx
0x180018250  mov     rdi, rcx
0x180018253  mov     r10, cs:WPP_GLOBAL_Control
0x18001825a  lea     rcx, WPP_GLOBAL_Control
0x180018261  cmp     r10, rcx
0x180018264  jz      short loc_18001829A
0x180018266  cmp     byte ptr [r10+19h], 6
0x18001826b  jb      short loc_18001829A
0x18001826d  mov     ecx, r14d; int
0x180018270  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018275  mov     rcx, [r10+10h]
0x180018279  lea     edx, [r14+14h]
0x18001827d  mov     r9, rax
0x180018280  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018287  call    WPP_SF_s
0x18001828c  mov     r10, cs:WPP_GLOBAL_Control
0x180018293  lea     rcx, WPP_GLOBAL_Control
0x18001829a  test    rsi, rsi
0x18001829d  jnz     short loc_1800182CF
0x18001829f  cmp     r10, rcx
0x1800182a2  jz      short loc_1800182C5
0x1800182a4  cmp     byte ptr [r10+19h], 2
0x1800182a9  jb      short loc_1800182C5
0x1800182ab  mov     rcx, [r10+10h]
0x1800182af  lea     edx, [rsi+16h]
0x1800182b2  lea     r9, aPtransportpeer; "pTransportPeer"
0x1800182b9  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800182c0  call    WPP_SF_s
0x1800182c5  mov     eax, 80004003h
0x1800182ca  jmp     loc_1800187D7
0x1800182cf  lea     eax, [r13-5]
0x1800182d3  mov     esi, 8000h
0x1800182d8  cmp     eax, r14d
0x1800182db  ja      short loc_18001830C
0x1800182dd  test    esi, ebx
0x1800182df  jz      short loc_18001830C
0x1800182e1  cmp     r10, rcx
0x1800182e4  jz      short loc_18001830C
0x1800182e6  cmp     byte ptr [r10+19h], 3
0x1800182eb  jb      short loc_18001830C
0x1800182ed  xor     ecx, ecx; int
0x1800182ef  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800182f4  mov     rcx, [r10+10h]
0x1800182f8  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800182ff  mov     edx, 17h
0x180018304  mov     r9, rax
0x180018307  call    WPP_SF_s
0x18001830c  test    ebx, 0B000h
0x180018312  jnz     short loc_180018340
0x180018314  cmp     r13d, 5
0x180018318  jz      short loc_18001833C
0x18001831a  cmp     r13d, 6
0x18001831e  jz      short loc_180018336
0x180018320  cmp     [rdi+1B0h], r12b
0x180018327  jnz     short loc_18001832D
0x180018329  or      ebx, esi
0x18001832b  jmp     short loc_180018340
0x18001832d  cmp     [rdi+5C8h], r12b
0x180018334  jz      short loc_18001833C
0x180018336  bts     ebx, 0Ch
0x18001833a  jmp     short loc_180018340
0x18001833c  bts     ebx, 0Dh
0x180018340  mov     eax, ebx
0x180018342  bts     eax, 14h
0x180018346  cmp     [rdi+1B1h], r12b
0x18001834d  cmovz   eax, ebx
0x180018350  mov     r15d, eax
0x180018353  bts     r15d, 15h
0x180018358  cmp     [rdi+1B2h], r12b
0x18001835f  cmovz   r15d, eax
0x180018363  mov     eax, r15d
0x180018366  and     eax, esi
0x180018368  mov     [rbp+4Fh+var_B8], eax
0x18001836b  jnz     short loc_180018372
0x18001836d  test    r14b, r15b
0x180018370  jz      short loc_180018379
0x180018372  mov     [rdi+1B3h], r14b
0x180018379  test    byte ptr cs:Microsoft_Windows_WCN_Config_RegistrarEnableBits, r14b
0x180018380  xorps   xmm0, xmm0
0x180018383  mov     rax, [rdi+20h]
0x180018387  mov     ecx, 4
0x18001838c  movups  [rbp+4Fh+var_98], xmm0
0x180018390  movups  xmm0, xmmword ptr [rax+98h]
0x180018397  movdqu  [rbp+4Fh+var_98], xmm0
0x18001839c  jz      short loc_1800183F2
0x18001839e  mov     eax, [rbp+4Fh+arg_20]
0x1800183a1  lea     rdx, SessionBegin
0x1800183a8  mov     [rbp+4Fh+var_B0], eax
0x1800183ab  mov     r9d, ecx
0x1800183ae  lea     rax, [rdi+628h]
0x1800183b5  mov     [rbp+4Fh+var_48], rcx
0x1800183b9  mov     [rbp+4Fh+var_70], rax
0x1800183bd  lea     rcx, WCN_ETW_EVENT_GUID_Context
0x1800183c4  lea     rax, [rbp+4Fh+var_98]
0x1800183c8  mov     [rbp+4Fh+var_68], 10h
0x1800183d0  mov     [rbp+4Fh+var_60], rax
0x1800183d4  lea     rax, [rbp+4Fh+var_B0]
0x1800183d8  mov     [rbp+4Fh+var_50], rax
0x1800183dc  lea     rax, [rbp+4Fh+var_80]
0x1800183e0  mov     [rsp+0F0h+var_D0], rax
0x1800183e5  mov     [rbp+4Fh+var_58], 10h
0x1800183ed  call    McGenEventWrite_EtwEventWriteTransfer
0x1800183f2  mov     rcx, [rdi+20h]
0x1800183f6  add     rcx, 10h; lpCriticalSection
0x1800183fa  call    cs:__imp_EnterCriticalSection
0x180018400  mov     rax, [rdi+20h]
0x180018404  cmp     [rax+70h], r12
0x180018408  jz      short loc_180018473
0x18001840a  mov     ebx, 800700B7h
0x18001840f  mov     r10, cs:WPP_GLOBAL_Control
0x180018416  lea     rax, WPP_GLOBAL_Control
0x18001841d  cmp     r10, rax
0x180018420  jz      short loc_180018448
0x180018422  cmp     byte ptr [r10+19h], 2
0x180018427  jb      short loc_180018448
0x180018429  xor     ecx, ecx; int
0x18001842b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018430  mov     rcx, [r10+10h]
0x180018434  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18001843b  mov     edx, 18h
0x180018440  mov     r9, rax
0x180018443  call    WPP_SF_s
0x180018448  mov     rcx, [rdi+20h]
0x18001844c  add     rcx, 10h; lpCriticalSection
0x180018450  call    cs:__imp_LeaveCriticalSection
0x180018456  xor     r13d, r13d
0x180018459  lea     r12, [rdi+0D0h]
0x180018460  lea     rsi, [rdi+0C8h]
0x180018467  lea     r14, [rdi+0D8h]
0x18001846e  jmp     loc_1800186A1
0x180018473  lea     rsi, [rdi+0C8h]
0x18001847a  mov     rcx, [rsi]
0x18001847d  test    rcx, rcx
0x180018480  jz      short loc_180018493
0x180018482  mov     rax, [rcx]
0x180018485  mov     edx, r14d
0x180018488  mov     rax, [rax]
0x18001848b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018490  mov     [rsi], r12
0x180018493  lea     r14, [rdi+0D8h]
0x18001849a  mov     rcx, [r14]
0x18001849d  test    rcx, rcx
0x1800184a0  jz      short loc_1800184B5
0x1800184a2  mov     rax, [rcx]
0x1800184a5  mov     edx, 1
0x1800184aa  mov     rax, [rax]
0x1800184ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184b2  mov     [r14], r12
0x1800184b5  mov     rax, [rdi+20h]
0x1800184b9  mov     dword ptr [rdi+0E0h], 1
0x1800184c3  mov     [rdi+14h], r12d
0x1800184c7  mov     dword ptr [rdi+18h], 80004005h
0x1800184ce  mov     [rax+70h], rdi
0x1800184d2  mov     rcx, [rdi+20h]
0x1800184d6  add     rcx, 10h; lpCriticalSection
0x1800184da  call    cs:__imp_LeaveCriticalSection
0x1800184e0  mov     rcx, [rdi+0E8h]; pti
0x1800184e7  lea     r12, [rdi+0D0h]
0x1800184ee  mov     r9d, 3E8h; msWindowLength
0x1800184f4  mov     [r12], r13d
0x1800184f8  xor     r8d, r8d; msPeriod
0x1800184fb  mov     qword ptr [rbp+4Fh+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x180018503  lea     rdx, [rbp+4Fh+pftDueTime]; pftDueTime
0x180018507  call    cs:__imp_SetThreadpoolTimer
0x18001850d  mov     edx, r15d; unsigned int
0x180018510  mov     rcx, rdi; this
0x180018513  call    ?UpdateSelfIdentity@CWcnSession@@QEAAJK@Z; CWcnSession::UpdateSelfIdentity(ulong)
0x180018518  xor     r13d, r13d
0x18001851b  mov     ebx, eax
0x18001851d  test    eax, eax
0x18001851f  jns     short loc_18001854B
0x180018521  mov     rcx, cs:WPP_GLOBAL_Control
0x180018528  lea     rax, WPP_GLOBAL_Control
0x18001852f  cmp     rcx, rax
0x180018532  jz      loc_1800186A1
0x180018538  cmp     byte ptr [rcx+19h], 2
0x18001853c  jb      loc_1800186A1
0x180018542  lea     edx, [r13+19h]
0x180018546  jmp     loc_18001868E
0x18001854b  mov     rax, [rdi+20h]
0x18001854f  mov     r8, r14
0x180018552  mov     rdx, rdi
0x180018555  mov     rcx, [rax+78h]
0x180018559  mov     rax, [rcx]
0x18001855c  mov     rax, [rax+8]
0x180018560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018565  mov     ebx, eax
0x180018567  test    eax, eax
0x180018569  jns     short loc_180018596
0x18001856b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018572  lea     rax, WPP_GLOBAL_Control
0x180018579  cmp     rcx, rax
0x18001857c  jz      loc_1800186A1
0x180018582  cmp     byte ptr [rcx+19h], 2
0x180018586  jb      loc_1800186A1
0x18001858c  mov     edx, 1Ah
0x180018591  jmp     loc_18001868E
0x180018596  mov     r10, cs:WPP_GLOBAL_Control
0x18001859d  lea     rax, WPP_GLOBAL_Control
0x1800185a4  cmp     r10, rax
0x1800185a7  jz      short loc_1800185D4
0x1800185a9  cmp     byte ptr [r10+19h], 5
0x1800185ae  jb      short loc_1800185D4
0x1800185b0  xor     ecx, ecx; int
0x1800185b2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800185b7  mov     rcx, [r10+10h]
0x1800185bb  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800185c2  mov     edx, 1Bh
0x1800185c7  mov     dword ptr [rsp+0F0h+var_D0], r15d
0x1800185cc  mov     r9, rax
0x1800185cf  call    WPP_SF_sd
0x1800185d4  cmp     [rbp+4Fh+var_B8], r13d
0x1800185d8  jnz     short loc_18001864D
0x1800185da  test    r15b, 1
0x1800185de  jnz     short loc_18001864D
0x1800185e0  lea     rdx, [rbp+4Fh+var_BF]; bool *
0x1800185e4  mov     ebx, 400Ch
0x1800185e9  lea     rcx, [rbp+4Fh+var_C0]; bool *
0x1800185ed  call    ?GetConfigMethodSetting@@YAXAEA_N0@Z; GetConfigMethodSetting(bool &,bool &)
0x1800185f2  cmp     [rbp+4Fh+var_C0], r13b
0x1800185f6  mov     eax, 600Ch
0x1800185fb  cmovnz  ebx, eax
0x1800185fe  call    ?IsNfcSupported@@YA_NXZ; IsNfcSupported(void)
0x180018603  mov     r8d, ebx
0x180018606  or      r8d, 70h
0x18001860a  test    al, al
0x18001860c  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x180018613  cmovz   r8d, ebx
0x180018617  mov     rcx, [rax+38h]; this
0x18001861b  cmp     [rdi+1B1h], r13b
0x180018622  jnz     short loc_18001863A
0x180018624  mov     al, [rbp+4Fh+var_BF]
0x180018627  neg     al
0x180018629  sbb     r8d, r8d
0x18001862c  and     r8d, 400h
0x180018633  add     r8d, 280h; unsigned int
0x18001863a  mov     edx, [r12]; unsigned int
0x18001863e  mov     r9, rdi; struct CWcnSession *
0x180018641  call    ?EnableSpecialAdvertisements@CWcnTransportManager@@QEAAXKIPEAVCWcnSession@@@Z; CWcnTransportManager::EnableSpecialAdvertisements(ulong,uint,CWcnSession *)
0x180018646  mov     byte ptr [rdi+1B4h], 1
0x18001864d  mov     rcx, [rbp+4Fh+var_A0]
0x180018651  mov     r9, rsi
0x180018654  mov     r8d, r15d
0x180018657  mov     rdx, rdi
0x18001865a  mov     rax, [rcx]
0x18001865d  mov     rax, [rax+8]
0x180018661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018666  mov     ebx, eax
0x180018668  test    eax, eax
0x18001866a  jns     loc_18001877F
0x180018670  mov     rcx, cs:WPP_GLOBAL_Control
0x180018677  lea     rax, WPP_GLOBAL_Control
0x18001867e  cmp     rcx, rax
0x180018681  jz      short loc_1800186A1
0x180018683  cmp     byte ptr [rcx+19h], 2
0x180018687  jb      short loc_1800186A1
0x180018689  mov     edx, 1Ch
0x18001868e  mov     rcx, [rcx+10h]
0x180018692  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018699  mov     r9d, ebx
0x18001869c  call    WPP_SF_d
0x1800186a1  cmp     [rdi+1B4h], r13b
0x1800186a8  jz      short loc_1800186C5
0x1800186aa  mov     rcx, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x1800186b1  mov     edx, [r12]; unsigned int
0x1800186b5  mov     rcx, [rcx+38h]; this
0x1800186b9  call    ?DisableSpecialAdvertisements@CWcnTransportManager@@QEAAXK@Z; CWcnTransportManager::DisableSpecialAdvertisements(ulong)
0x1800186be  mov     [rdi+1B4h], r13b
0x1800186c5  mov     rcx, [rsi]
0x1800186c8  test    rcx, rcx
0x1800186cb  jz      short loc_1800186E0
0x1800186cd  mov     rax, [rcx]
0x1800186d0  mov     edx, 1
0x1800186d5  mov     rax, [rax]
0x1800186d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186dd  mov     [rsi], r13
0x1800186e0  mov     rcx, [r14]
0x1800186e3  test    rcx, rcx
0x1800186e6  jz      short loc_1800186FB
  ... truncated ...
```

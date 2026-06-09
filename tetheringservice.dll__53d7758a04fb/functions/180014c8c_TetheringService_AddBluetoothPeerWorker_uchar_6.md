# TetheringService::AddBluetoothPeerWorker(uchar (*)[6])

- ea: `0x180014c8c`
- end: `0x180015398`
- name: `?AddBluetoothPeerWorker@TetheringService@@AEAAXPEAY05E@Z`
- size: `1804`
- prototype: `void __fastcall(TetheringService *__hidden this, unsigned __int8 (*)[6])`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800153a0`

## callees

- `0x180002590`
- `0x18000299c`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000ee14`
- `0x180012a90`
- `0x180014c8c`
- `0x180015430`
- `0x180017adc`
- `0x18001a21c`
- `0x18001c184`
- `0x18001c75c`
- `0x18001e4a4`
- `0x180021be8`
- `0x180024c38`
- `0x180026b10`
- `0x180027130`
- `0x180027288`
- `0x1800272c0`
- `0x180027394`
- `0x180027424`
- `0x1800274c0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014f2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014f2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ed3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ee3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001529f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ed3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ee3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001529f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014eec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ef9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800152b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014eec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ef9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800152b8`

## pseudocode

```c
void __fastcall TetheringService::AddBluetoothPeerWorker(TetheringService *this, unsigned __int8 (*a2)[6])
{
  char v4; // r12
  RTL_SRWLOCK *v5; // rbx
  TetheringServiceTelemetry *v6; // rcx
  int started; // r15d
  TetheringSessionTelemetry *v8; // rax
  struct TetheringSessionTelemetry *v9; // rdi
  int v10; // r8d
  TetheringServiceTelemetry *v11; // rcx
  int v12; // eax
  bool v13; // zf
  const char *v14; // rax
  int Configuration; // eax
  TetheringService *v16; // rcx
  int DefaultInterface; // esi
  TetheringServiceTelemetry *v18; // rcx
  __int64 v19; // rdx
  BOOL v20; // edi
  TetheringServiceTelemetry *v21; // rcx
  _QWORD *v22; // rax
  char v23; // di
  struct _GUID *Id; // rax
  TetheringServiceTelemetry *v25; // rcx
  TetheringService *v26; // rcx
  TetheringServiceTelemetry *v27; // rcx
  __int64 v28; // rdx
  BtPanHandler *v29; // rcx
  BOOL v30; // esi
  TetheringServiceTelemetry *v31; // rcx
  struct TetheringSessionTelemetry *v32; // [rsp+38h] [rbp-C8h] BYREF
  int v33[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v34[7]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h]
  int v36; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v37[220]; // [rsp+A4h] [rbp-5Ch] BYREF
  struct _GUID v38; // [rsp+180h] [rbp+80h] BYREF
  struct _GUID v39; // [rsp+190h] [rbp+90h] BYREF
  _DWORD v40[52]; // [rsp+1A0h] [rbp+A0h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 272, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  memset_0(v40, 0, sizeof(v40));
  v39 = 0;
  v38 = 0;
  v4 = 0;
  memset_0(v34, 0, 0x50u);
  v5 = 0;
  v32 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( !*(_QWORD *)&g_pTetheringSessionId.Data1
    || (started = TetheringServiceTelemetry::GetSession(v6, *(struct _GUID **)&g_pTetheringSessionId.Data1, &v32),
        v5 = (RTL_SRWLOCK *)v32,
        started >= 0)
    && (!v32 || !(unsigned int)TetheringSessionTelemetry::Initialized(v32))
    || started < 0 )
  {
    v8 = (TetheringSessionTelemetry *)operator new(0x220u, (const struct std::nothrow_t *)&std::nothrow);
    *(_QWORD *)v33 = v8;
    if ( v8 )
      v9 = TetheringSessionTelemetry::TetheringSessionTelemetry(v8, 8);
    else
      v9 = 0;
    if ( v5 )
      (*((void (__fastcall **)(RTL_SRWLOCK *))v5->Ptr + 2))(v5);
    v5 = (RTL_SRWLOCK *)v9;
    v32 = v9;
    started = StartGlobalTelemetrySession(v9);
    if ( started < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        if ( !v9
          || (v12 = TetheringSessionTelemetry::Initialized(v9),
              v11 = WPP_GLOBAL_Control,
              v13 = v12 == 0,
              v14 = "true",
              v13) )
        {
          v14 = "false";
        }
        WPP_SF_lsd(*((_QWORD *)v11 + 2), 273, v10, (_DWORD)v9, (__int64)v14, started);
      }
    }
    else
    {
      v4 = 1;
    }
  }
  Configuration = TetheringService::GetConfiguration(this, 0, (struct _TETHERING_CONNECTION_SETTINGS *)v40, v33);
  DefaultInterface = Configuration;
  if ( Configuration < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_76;
    }
    v19 = 274;
    goto LABEL_26;
  }
  v20 = 0;
  if ( v40[0] == 1 && *((_DWORD *)this + 56) == 2 )
    v20 = TetheringService::IsBluetoothAutoConnectionEnabled(v16) == 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( v4 )
  {
    if ( !v5 )
      ATL::AtlThrowImpl(-2147467259);
    TetheringServiceTelemetry::AcquireSessionData(v21, v5, (struct TetheringServiceTelemetry::SESSION_DATA *)v34);
    v22 = (_QWORD *)v35;
    *(_DWORD *)(v35 + 8) = v20;
    *v22 = 0;
    ReleaseSRWLockExclusive(v5 + 2);
  }
  memset_0(v37, 0, 0xD0u);
  v36 = 12;
  TetheringService::SendNotification(this, (struct _TETHERING_WNF_NOTIFICATION_MSG *)&v36);
  memset_0(v40, 0, sizeof(v40));
  Configuration = TetheringService::GetConfiguration(this, 0, (struct _TETHERING_CONNECTION_SETTINGS *)v40, v33);
  DefaultInterface = Configuration;
  if ( Configuration < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_76;
    }
    v19 = 275;
    goto LABEL_26;
  }
  if ( *((_QWORD *)this + 161) == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)this + 162) == *(_QWORD *)GUID_NULL.Data4 )
  {
    v23 = 1;
    DefaultInterface = InterfaceMgr::GetDefaultInterface(1, 2, &v38);
    if ( DefaultInterface < 0 )
      goto LABEL_77;
  }
  else
  {
    v38 = *(struct _GUID *)((char *)this + 1288);
  }
  DefaultInterface = InterfaceMgr::GetDefaultInterface(2, 4, &v39);
  if ( DefaultInterface < 0 )
    goto LABEL_76;
  if ( v4 )
  {
    memset_0(v34, 0, 0x50u);
    v34[0] = &v38;
    v34[1] = &v39;
    Id = TetheringSessionTelemetry::GetId((TetheringSessionTelemetry *)v5);
    TetheringServiceTelemetry::SetSessionData(v25, Id, (const struct TetheringServiceTelemetry::SESSION_DATA *)v34);
  }
  if ( v40[0] == 1 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 276, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
    if ( !(unsigned int)TetheringService::IsBluetoothAutoConnectionEnabled(v26) && *((_DWORD *)this + 56) == 2 )
    {
      DefaultInterface = 1;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      {
        goto LABEL_76;
      }
      v28 = 277;
      goto LABEL_54;
    }
    v40[0] = 4;
    DefaultInterface = TetheringService::SetConfiguration(this, 0, (struct _TETHERING_CONNECTION_SETTINGS *const)v40);
    if ( DefaultInterface < 0 )
      goto LABEL_76;
    *((_DWORD *)this + 414) = 1;
    if ( *((_DWORD *)this + 56) != 3 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      {
        goto LABEL_76;
      }
      v28 = 279;
LABEL_54:
      WPP_SF_(*((_QWORD *)v27 + 2), v28, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      goto LABEL_76;
    }
    Configuration = TetheringService::StartSharingInternal(this, &v38, &v39, 0, 1u, 0);
    DefaultInterface = Configuration;
    if ( Configuration >= 0 )
      goto LABEL_76;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_76;
    }
    v19 = 278;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v18 + 2), v19, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, (unsigned int)Configuration);
LABEL_76:
    v23 = 1;
    goto LABEL_77;
  }
  if ( v40[0] != 4 )
    goto LABEL_76;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 280, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  if ( *((_DWORD *)this + 56) == 3 )
  {
    Configuration = TetheringService::StartSharingInternal(this, &v38, &v39, 0, 1u, 0);
    DefaultInterface = Configuration;
    if ( Configuration >= 0 )
      goto LABEL_76;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_76;
    }
    v19 = 281;
    goto LABEL_26;
  }
  v23 = 0;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 282, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
LABEL_77:
  memset_0(v37, 0, 0xD0u);
  v36 = 13;
  TetheringService::SendNotification(this, (struct _TETHERING_WNF_NOTIFICATION_MSG *)&v36);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  if ( DefaultInterface
    || !v23
    && (EnterCriticalSection((LPCRITICAL_SECTION)this + 34),
        v30 = *((_DWORD *)this + 415) == *((_DWORD *)this + 413),
        LeaveCriticalSection((LPCRITICAL_SECTION)this + 34),
        v30) )
  {
    BtPanHandler::DisconnectBluetoothDevice(v29, a2);
  }
  else
  {
    TetheringService::AddPeer(this, a2);
  }
  if ( started >= 0 )
    goto LABEL_86;
  v31 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_90;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      283,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)started);
LABEL_86:
    v31 = WPP_GLOBAL_Control;
  }
  if ( v31 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v31 + 2), 284, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
LABEL_90:
  if ( v5 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v5->Ptr + 2))(v5);
}

```

## disassembly

```asm
0x180014c8c  mov     [rsp-8+arg_10], rbx
0x180014c91  push    rbp
0x180014c92  push    rsi
0x180014c93  push    rdi
0x180014c94  push    r12
0x180014c96  push    r13
0x180014c98  push    r14
0x180014c9a  push    r15
0x180014c9c  lea     rbp, [rsp-180h]
0x180014ca4  sub     rsp, 280h
0x180014cab  mov     rax, cs:__security_cookie
0x180014cb2  xor     rax, rsp
0x180014cb5  mov     [rbp+1B0h+var_40], rax
0x180014cbc  mov     r13, rdx
0x180014cbf  mov     r14, rcx
0x180014cc2  lea     rsi, WPP_GLOBAL_Control
0x180014cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cd0  cmp     rcx, rsi
0x180014cd3  jz      short loc_180014CF0
0x180014cd5  test    byte ptr [rcx+1Ch], 8
0x180014cd9  jz      short loc_180014CF0
0x180014cdb  mov     edx, 110h
0x180014ce0  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180014ce7  mov     rcx, [rcx+10h]
0x180014ceb  call    WPP_SF_
0x180014cf0  mov     edi, 1
0x180014cf5  mov     [rsp+2B0h+var_280], dil
0x180014cfa  xor     edx, edx; Val
0x180014cfc  mov     r8d, 0D0h; Size
0x180014d02  lea     rcx, [rbp+1B0h+var_110]; void *
0x180014d09  call    memset_0
0x180014d0e  xorps   xmm0, xmm0
0x180014d11  movups  xmmword ptr [rbp+1B0h+var_120.Data1], xmm0
0x180014d18  xorps   xmm1, xmm1
0x180014d1b  movups  xmmword ptr [rbp+1B0h+var_130.Data1], xmm1
0x180014d22  xor     r12b, r12b
0x180014d25  xor     edx, edx; Val
0x180014d27  lea     r8d, [rdi+4Fh]; Size
0x180014d2b  lea     rcx, [rsp+2B0h+var_260]; void *
0x180014d30  call    memset_0
0x180014d35  nop
0x180014d36  xor     ebx, ebx
0x180014d38  mov     [rsp+2B0h+var_278], rbx
0x180014d3d  lea     rcx, [r14+110h]; lpCriticalSection
0x180014d44  call    cs:__imp_EnterCriticalSection
0x180014d4a  lea     rcx, [r14+0E8h]; lpCriticalSection
0x180014d51  call    cs:__imp_EnterCriticalSection
0x180014d57  mov     rdx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data1; struct _GUID *
0x180014d5e  test    rdx, rdx
0x180014d61  jz      short loc_180014D93
0x180014d63  lea     r8, [rsp+2B0h+var_278]; struct TetheringSessionTelemetry **
0x180014d68  call    ?GetSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@PEAPEAVTetheringSessionTelemetry@@@Z; TetheringServiceTelemetry::GetSession(_GUID *,TetheringSessionTelemetry * *)
0x180014d6d  mov     r15d, eax
0x180014d70  mov     rbx, [rsp+2B0h+var_278]
0x180014d75  test    eax, eax
0x180014d77  js      short loc_180014D8A
0x180014d79  test    rbx, rbx
0x180014d7c  jz      short loc_180014D93
0x180014d7e  mov     rcx, rbx; this
0x180014d81  call    ?Initialized@TetheringSessionTelemetry@@QEAAHXZ; TetheringSessionTelemetry::Initialized(void)
0x180014d86  test    eax, eax
0x180014d88  jz      short loc_180014D93
0x180014d8a  test    r15d, r15d
0x180014d8d  jns     loc_180014E4F
0x180014d93  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014d9a  mov     ecx, 220h; unsigned __int64
0x180014d9f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014da4  mov     qword ptr [rsp+2B0h+var_270], rax
0x180014da9  test    rax, rax
0x180014dac  jz      short loc_180014DC0
0x180014dae  mov     edx, 8; unsigned int
0x180014db3  mov     rcx, rax; this
0x180014db6  call    ??0TetheringSessionTelemetry@@QEAA@K@Z; TetheringSessionTelemetry::TetheringSessionTelemetry(ulong)
0x180014dbb  mov     rdi, rax
0x180014dbe  jmp     short loc_180014DC2
0x180014dc0  xor     edi, edi
0x180014dc2  test    rbx, rbx
0x180014dc5  jz      short loc_180014DD6
0x180014dc7  mov     rax, [rbx]
0x180014dca  mov     rcx, rbx
0x180014dcd  mov     rax, [rax+10h]
0x180014dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dd6  mov     rbx, rdi
0x180014dd9  mov     [rsp+2B0h+var_278], rbx
0x180014dde  mov     rcx, rdi; struct TetheringSessionTelemetry *
0x180014de1  call    ?StartGlobalTelemetrySession@@YAJPEAVTetheringSessionTelemetry@@@Z; StartGlobalTelemetrySession(TetheringSessionTelemetry *)
0x180014de6  mov     r15d, eax
0x180014de9  test    eax, eax
0x180014deb  js      short loc_180014DF7
0x180014ded  mov     edi, 1
0x180014df2  mov     r12b, dil
0x180014df5  jmp     short loc_180014E4F
0x180014df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180014dfe  cmp     rcx, rsi
0x180014e01  jz      short loc_180014E4A
0x180014e03  test    byte ptr [rcx+1Ch], 8
0x180014e07  jz      short loc_180014E4A
0x180014e09  test    rdi, rdi
0x180014e0c  jz      short loc_180014E28
0x180014e0e  mov     rcx, rdi; this
0x180014e11  call    ?Initialized@TetheringSessionTelemetry@@QEAAHXZ; TetheringSessionTelemetry::Initialized(void)
0x180014e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e1d  test    eax, eax
0x180014e1f  lea     rax, aTrue_0; "true"
0x180014e26  jnz     short loc_180014E2F
0x180014e28  lea     rax, aFalse; "false"
0x180014e2f  mov     r9d, edi
0x180014e32  mov     edx, 111h
0x180014e37  mov     dword ptr [rsp+2B0h+var_288], r15d
0x180014e3c  mov     qword ptr [rsp+2B0h+var_290], rax
0x180014e41  mov     rcx, [rcx+10h]
0x180014e45  call    WPP_SF_lsd
0x180014e4a  mov     edi, 1
0x180014e4f  lea     r9, [rsp+2B0h+var_270]; int *
0x180014e54  lea     r8, [rbp+1B0h+var_110]; struct _TETHERING_CONNECTION_SETTINGS *
0x180014e5b  xor     edx, edx; struct _TETHERING_CONNECTION_SETTINGS *
0x180014e5d  mov     rcx, r14; this
0x180014e60  call    ?GetConfiguration@TetheringService@@QEAAJPEAU_TETHERING_CONNECTION_SETTINGS@@0PEAH@Z; TetheringService::GetConfiguration(_TETHERING_CONNECTION_SETTINGS *,_TETHERING_CONNECTION_SETTINGS *,int *)
0x180014e65  mov     esi, eax
0x180014e67  test    eax, eax
0x180014e69  jns     short loc_180014EA9
0x180014e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e72  lea     r12, WPP_GLOBAL_Control
0x180014e79  cmp     rcx, r12
0x180014e7c  jz      loc_180015262
0x180014e82  test    [rcx+1Ch], dil
0x180014e86  jz      loc_180015262
0x180014e8c  mov     edx, 112h
0x180014e91  mov     r9d, eax
0x180014e94  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180014e9b  mov     rcx, [rcx+10h]
0x180014e9f  call    WPP_SF_d
0x180014ea4  jmp     loc_180015262
0x180014ea9  xor     edi, edi
0x180014eab  lea     esi, [rdi+1]
0x180014eae  cmp     [rbp+1B0h+var_110], esi
0x180014eb4  jnz     short loc_180014ECC
0x180014eb6  mov     eax, [r14+0E0h]
0x180014ebd  cmp     eax, 2
0x180014ec0  jnz     short loc_180014ECC
0x180014ec2  call    ?IsBluetoothAutoConnectionEnabled@TetheringService@@AEAAHXZ; TetheringService::IsBluetoothAutoConnectionEnabled(void)
0x180014ec7  test    eax, eax
0x180014ec9  cmovz   edi, esi
0x180014ecc  lea     rcx, [r14+0E8h]; lpCriticalSection
0x180014ed3  call    cs:__imp_LeaveCriticalSection
0x180014ed9  lea     rsi, [r14+110h]
0x180014ee0  mov     rcx, rsi; lpCriticalSection
0x180014ee3  call    cs:__imp_LeaveCriticalSection
0x180014ee9  mov     rcx, rsi; lpCriticalSection
0x180014eec  call    cs:__imp_EnterCriticalSection
0x180014ef2  lea     rcx, [r14+0E8h]; lpCriticalSection
0x180014ef9  call    cs:__imp_EnterCriticalSection
0x180014eff  test    r12b, r12b
0x180014f02  jz      short loc_180014F32
0x180014f04  test    rbx, rbx
0x180014f07  jz      loc_18001538D
0x180014f0d  lea     r8, [rsp+2B0h+var_260]; struct TetheringServiceTelemetry::SESSION_DATA *
0x180014f12  mov     rdx, rbx; struct TetheringSessionTelemetry *
0x180014f15  call    ?AcquireSessionData@TetheringServiceTelemetry@@QEAAXAEAVTetheringSessionTelemetry@@AEAUSESSION_DATA@1@@Z; TetheringServiceTelemetry::AcquireSessionData(TetheringSessionTelemetry &,TetheringServiceTelemetry::SESSION_DATA &)
0x180014f1a  mov     rax, [rbp+1B0h+var_228]
0x180014f1e  mov     [rax+8], edi
0x180014f21  mov     qword ptr [rax], 0
0x180014f28  lea     rcx, [rbx+10h]; SRWLock
0x180014f2c  call    cs:__imp_ReleaseSRWLockExclusive
0x180014f32  mov     edi, 0D0h
0x180014f37  mov     r8d, edi; Size
0x180014f3a  xor     edx, edx; Val
0x180014f3c  lea     rcx, [rbp+1B0h+var_20C]; void *
0x180014f40  call    memset_0
0x180014f45  mov     [rbp+1B0h+var_210], 0Ch
0x180014f4c  lea     rdx, [rbp+1B0h+var_210]; struct _TETHERING_WNF_NOTIFICATION_MSG *
0x180014f50  mov     rcx, r14; this
0x180014f53  call    ?SendNotification@TetheringService@@AEAAXPEAU_TETHERING_WNF_NOTIFICATION_MSG@@@Z; TetheringService::SendNotification(_TETHERING_WNF_NOTIFICATION_MSG *)
0x180014f58  mov     r8d, edi; Size
0x180014f5b  xor     edx, edx; Val
0x180014f5d  lea     rcx, [rbp+1B0h+var_110]; void *
0x180014f64  call    memset_0
0x180014f69  lea     r9, [rsp+2B0h+var_270]; int *
0x180014f6e  lea     r8, [rbp+1B0h+var_110]; struct _TETHERING_CONNECTION_SETTINGS *
0x180014f75  xor     edx, edx; struct _TETHERING_CONNECTION_SETTINGS *
0x180014f77  mov     rcx, r14; this
0x180014f7a  call    ?GetConfiguration@TetheringService@@QEAAJPEAU_TETHERING_CONNECTION_SETTINGS@@0PEAH@Z; TetheringService::GetConfiguration(_TETHERING_CONNECTION_SETTINGS *,_TETHERING_CONNECTION_SETTINGS *,int *)
0x180014f7f  mov     esi, eax
0x180014f81  test    eax, eax
0x180014f83  jns     short loc_180014FAE
0x180014f85  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f8c  lea     r12, WPP_GLOBAL_Control
0x180014f93  cmp     rcx, r12
0x180014f96  jz      loc_180015262
0x180014f9c  test    byte ptr [rcx+1Ch], 1
0x180014fa0  jz      loc_180015262
0x180014fa6  lea     edx, [rdi+43h]
0x180014fa9  jmp     loc_180014E91
0x180014fae  mov     rax, [r14+508h]
0x180014fb5  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180014fbc  jnz     short loc_180014FF6
0x180014fbe  mov     rax, [r14+510h]
0x180014fc5  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180014fcc  jnz     short loc_180014FF6
0x180014fce  lea     r8, [rbp+1B0h+var_130]
0x180014fd5  mov     edx, 2
0x180014fda  lea     edi, [rdx-1]
0x180014fdd  mov     ecx, edi
0x180014fdf  call    ?GetDefaultInterface@InterfaceMgr@@SAJW4_TETHERING_INTERFACE_TYPE@@W4_TETHERING_CONNECTION_TYPE@@PEAU_GUID@@@Z; InterfaceMgr::GetDefaultInterface(_TETHERING_INTERFACE_TYPE,_TETHERING_CONNECTION_TYPE,_GUID *)
0x180014fe4  mov     esi, eax
0x180014fe6  test    eax, eax
0x180014fe8  jns     short loc_18001500B
0x180014fea  lea     r12, WPP_GLOBAL_Control
0x180014ff1  jmp     loc_180015267
0x180014ff6  movups  xmm0, xmmword ptr [r14+508h]
0x180014ffe  movdqu  xmmword ptr [rbp+1B0h+var_130.Data1], xmm0
0x180015006  mov     edi, 1
0x18001500b  lea     r8, [rbp+1B0h+var_120]
0x180015012  mov     edx, 4
0x180015017  lea     ecx, [rdx-2]
0x18001501a  call    ?GetDefaultInterface@InterfaceMgr@@SAJW4_TETHERING_INTERFACE_TYPE@@W4_TETHERING_CONNECTION_TYPE@@PEAU_GUID@@@Z; InterfaceMgr::GetDefaultInterface(_TETHERING_INTERFACE_TYPE,_TETHERING_CONNECTION_TYPE,_GUID *)
0x18001501f  mov     esi, eax
0x180015021  test    eax, eax
0x180015023  js      loc_18001525B
0x180015029  test    r12b, r12b
0x18001502c  jz      short loc_18001506B
0x18001502e  xor     edx, edx; Val
0x180015030  lea     r8d, [rdx+50h]; Size
0x180015034  lea     rcx, [rsp+2B0h+var_260]; void *
0x180015039  call    memset_0
0x18001503e  lea     rax, [rbp+1B0h+var_130]
0x180015045  mov     [rsp+2B0h+var_260], rax
0x18001504a  lea     rax, [rbp+1B0h+var_120]
0x180015051  mov     [rsp+2B0h+var_258], rax
0x180015056  mov     rcx, rbx; this
0x180015059  call    ?GetId@TetheringSessionTelemetry@@QEAAPEAU_GUID@@XZ; TetheringSessionTelemetry::GetId(void)
0x18001505e  mov     rdx, rax; struct _GUID *
0x180015061  lea     r8, [rsp+2B0h+var_260]; struct TetheringServiceTelemetry::SESSION_DATA *
0x180015066  call    ?SetSessionData@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@AEBUSESSION_DATA@1@@Z; TetheringServiceTelemetry::SetSessionData(_GUID *,TetheringServiceTelemetry::SESSION_DATA const &)
0x18001506b  cmp     [rbp+1B0h+var_110], edi
0x180015071  jnz     loc_1800151A0
0x180015077  mov     rcx, cs:WPP_GLOBAL_Control
0x18001507e  lea     r12, WPP_GLOBAL_Control
0x180015085  cmp     rcx, r12
0x180015088  jz      short loc_1800150A5
0x18001508a  test    byte ptr [rcx+1Ch], 8
0x18001508e  jz      short loc_1800150A5
0x180015090  mov     edx, 114h
0x180015095  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001509c  mov     rcx, [rcx+10h]
0x1800150a0  call    WPP_SF_
0x1800150a5  call    ?IsBluetoothAutoConnectionEnabled@TetheringService@@AEAAHXZ; TetheringService::IsBluetoothAutoConnectionEnabled(void)
0x1800150aa  test    eax, eax
0x1800150ac  jnz     short loc_1800150F0
0x1800150ae  mov     eax, [r14+0E0h]
0x1800150b5  cmp     eax, 2
0x1800150b8  jnz     short loc_1800150F0
0x1800150ba  mov     esi, edi
0x1800150bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150c3  cmp     rcx, r12
0x1800150c6  jz      loc_180015262
0x1800150cc  test    byte ptr [rcx+1Ch], 8
0x1800150d0  jz      loc_180015262
0x1800150d6  mov     edx, 115h
0x1800150db  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800150e2  mov     rcx, [rcx+10h]
0x1800150e6  call    WPP_SF_
0x1800150eb  jmp     loc_180015262
0x1800150f0  mov     [rbp+1B0h+var_110], 4
0x1800150fa  lea     r8, [rbp+1B0h+var_110]; struct _TETHERING_CONNECTION_SETTINGS *
0x180015101  xor     edx, edx; struct _TETHERING_CONNECTION_SETTINGS *
0x180015103  mov     rcx, r14; this
0x180015106  call    ?SetConfiguration@TetheringService@@QEAAJQEAU_TETHERING_CONNECTION_SETTINGS@@0@Z; TetheringService::SetConfiguration(_TETHERING_CONNECTION_SETTINGS * const,_TETHERING_CONNECTION_SETTINGS * const)
0x18001510b  mov     esi, eax
0x18001510d  test    eax, eax
0x18001510f  js      loc_180015262
0x180015115  mov     [r14+678h], edi
0x18001511c  mov     eax, [r14+0E0h]
0x180015123  cmp     eax, 3
0x180015126  jnz     short loc_18001517C
0x180015128  mov     [rsp+2B0h+var_288], 0; unsigned __int16 *
0x180015131  mov     [rsp+2B0h+var_290], edi; unsigned int
0x180015135  xor     r9d, r9d; struct _TETHERING_SESSION_CONNECTION_SETTINGS *
0x180015138  lea     r8, [rbp+1B0h+var_120]; struct _GUID *
0x18001513f  lea     rdx, [rbp+1B0h+var_130]; struct _GUID *
0x180015146  mov     rcx, r14; this
0x180015149  call    ?StartSharingInternal@TetheringService@@AEAAJPEBU_GUID@@0QEAU_TETHERING_SESSION_CONNECTION_SETTINGS@@KPEBG@Z; TetheringService::StartSharingInternal(_GUID const *,_GUID const *,_TETHERING_SESSION_CONNECTION_SETTINGS * const,ulong,ushort const *)
0x18001514e  mov     esi, eax
0x180015150  test    eax, eax
0x180015152  jns     loc_180015262
0x180015158  mov     rcx, cs:WPP_GLOBAL_Control
0x18001515f  cmp     rcx, r12
0x180015162  jz      loc_180015262
0x180015168  test    [rcx+1Ch], dil
0x18001516c  jz      loc_180015262
0x180015172  mov     edx, 116h
0x180015177  jmp     loc_180014E91
0x18001517c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015183  cmp     rcx, r12
0x180015186  jz      loc_180015262
0x18001518c  test    byte ptr [rcx+1Ch], 8
0x180015190  jz      loc_180015262
0x180015196  mov     edx, 117h
0x18001519b  jmp     loc_1800150DB
0x1800151a0  cmp     [rbp+1B0h+var_110], 4
  ... truncated ...
```

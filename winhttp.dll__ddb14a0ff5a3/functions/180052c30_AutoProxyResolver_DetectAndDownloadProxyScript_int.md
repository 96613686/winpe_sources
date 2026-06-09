# AutoProxyResolver::DetectAndDownloadProxyScript(int)

- ea: `0x180052c30`
- end: `0x1800532d2`
- name: `?DetectAndDownloadProxyScript@AutoProxyResolver@@AEAAJH@Z`
- size: `1698`
- prototype: `__int64 __fastcall(AutoProxyResolver *__hidden this, int)`
- caller_count: `4`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180063a0c`
- `0x180064fe8`
- `0x180065afc`
- `0x1800c2434`

## callees

- `0x180016da4`
- `0x1800519e0`
- `0x180052794`
- `0x180052c30`
- `0x180053804`
- `0x180053a94`
- `0x180054378`
- `0x180054938`
- `0x1800549a0`
- `0x180054af4`
- `0x180055f84`
- `0x18007a684`
- `0x180086ca8`
- `0x180088aa4`
- `0x18008c4bc`
- `0x180090884`
- `0x18009814c`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800c8d84`
- `0x1800cf008`
- `0x1800cf58c`
- `0x1800db704`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052ce5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052e25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005305d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800530a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052ce5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052e25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005305d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800530a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052d6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052e78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005308a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800530d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053134`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052d6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052e78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005308a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800530d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053134`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180052cf2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180052cf2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052d89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052d89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052cb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052cb8`

## pseudocode

```c
__int64 __fastcall AutoProxyResolver::DetectAndDownloadProxyScript(AutoProxyResolver *this, int a2)
{
  struct AutoConfigUrlTracker *v2; // rdi
  volatile signed __int32 *v3; // rbx
  _OWORD *v5; // rax
  __int64 v6; // rcx
  _OWORD *v7; // r14
  struct _RTL_CRITICAL_SECTION *v8; // r15
  __int64 v9; // rax
  int v10; // eax
  int v11; // r12d
  _QWORD *v12; // rax
  _QWORD *v13; // r12
  int v14; // r14d
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  unsigned __int64 v18; // r13
  unsigned int NextUniquePerfTrackId; // eax
  __int64 v21; // rcx
  int AutoConfigUrlTrackerFromSettings; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // [rsp+40h] [rbp-49h]
  unsigned __int64 v27; // [rsp+48h] [rbp-41h]
  __int64 v28; // [rsp+50h] [rbp-39h]
  int v29; // [rsp+58h] [rbp-31h]
  int v30; // [rsp+5Ch] [rbp-2Dh]
  unsigned int v31; // [rsp+60h] [rbp-29h]
  struct AutoConfigUrlTracker *v33; // [rsp+68h] [rbp-21h] BYREF
  void *v34; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int64 v35; // [rsp+78h] [rbp-11h]
  int v36; // [rsp+84h] [rbp-5h]
  struct ScriptHandler *v37; // [rsp+88h] [rbp-1h] BYREF

  v2 = 0;
  v33 = 0;
  v3 = 0;
  v37 = 0;
  v29 = 0;
  v31 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qD(1029, 26, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids, this);
  v30 = *((_DWORD *)this + 114);
  *((_DWORD *)this + 114) = 0;
  if ( v30 )
  {
    if ( **((_DWORD **)this + 30) )
    {
      NextUniquePerfTrackId = GetNextUniquePerfTrackId();
      v31 = NextUniquePerfTrackId;
      if ( Microsoft_Windows_WinHttpEnableBits < 0 )
        McTemplateU0q_EtwEventWriteTransfer(v21, WINHTTP_AUTOPROXY_PERFTRACK_ALL_START, NextUniquePerfTrackId);
    }
  }
  v34 = 0;
  v5 = CoTaskMemAlloc(0x70u);
  v7 = v5;
  if ( !v5 )
  {
    v14 = -2147024882;
    v17 = 0;
    v18 = 0;
    v26 = 0;
    v11 = -2147024882;
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
    goto LABEL_22;
  }
  memset_0(v5, 0, 0x70u);
  v34 = v7;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  ResetEvent(*((HANDLE *)this + 64));
  v9 = *((_QWORD *)this + 60);
  if ( v9 )
    *(_DWORD *)(v9 + 80) = 1;
  v10 = *((_DWORD *)this + 130);
  *((_DWORD *)this + 131) = v10;
  if ( v10 )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_(1029, 27, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids);
    v14 = -2146685199;
    goto LABEL_60;
  }
  v27 = *((_QWORD *)this + 66);
  v28 = *((_QWORD *)this + 40) + 1LL;
  v35 = v28 + 1;
  *((_QWORD *)this + 40) = v28 + 1;
  AutoProxyResolver::UpdateSessionStatusGeneration(this);
  v11 = CopyProxySettings<WxCoTaskAllocator>((__int128 *)this + 2, v7);
  if ( v11 < 0 )
  {
    v17 = 1;
    v26 = 1;
    v14 = v11;
    goto LABEL_18;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v26 = 0;
  v36 = 0;
  v12 = HeapAlloc(g_hWxProcessHeap, 0, 0x10u);
  v3 = (volatile signed __int32 *)v12;
  if ( !v12 )
  {
    v3 = 0;
    v36 = 252;
    v14 = -2147024882;
    v11 = -2147024882;
    v17 = 0;
    goto LABEL_21;
  }
  *v12 = 0;
  v13 = v12 + 1;
  v12[1] = 0;
  *(_DWORD *)v12 = 1;
  if ( v12[1] )
    ProxySettingsAllocator::Free((void ***)v12 + 1);
  *v13 = v7;
  v14 = 0;
  v34 = 0;
  AutoProxyBase::SetState(this, 2, 0);
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 4LL) & 8) != 0 )
  {
    v15 = AutoProxyResolver::QueueAndWaitForDetections(this, v28, v27, v3, v30, (volatile signed __int32 **)&v37);
    v14 = v15;
    if ( v15 == -2146685199 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
      AutoProxyBase::SetState(this, 2, 0);
      *((_QWORD *)this + 39) = ++*((_QWORD *)this + 40);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
      goto LABEL_55;
    }
    if ( v15 >= 0 )
    {
      v29 = 1;
      v24 = AutoProxyResolver::SetCurrentScriptHandler(this, v37, v28, 0, 0);
      v11 = v24;
      if ( v24 >= 0 )
        goto LABEL_16;
      v14 = v24;
      v17 = 0;
LABEL_18:
      if ( v14 == -2146685199 )
        goto LABEL_27;
      if ( !v3 )
        goto LABEL_21;
      goto LABEL_20;
    }
  }
  v16 = *((_QWORD *)v3 + 1);
  if ( (*(_BYTE *)(v16 + 4) & 4) == 0 || !*(_QWORD *)(v16 + 40) )
    goto LABEL_16;
  AutoConfigUrlTrackerFromSettings = AutoProxyResolver::CreateAutoConfigUrlTrackerFromSettings(
                                       (_DWORD)this,
                                       (_DWORD)v3,
                                       v28,
                                       v30,
                                       a2,
                                       v27,
                                       (__int64)&v33);
  v11 = AutoConfigUrlTrackerFromSettings;
  if ( AutoConfigUrlTrackerFromSettings < 0 )
  {
    v2 = v33;
    v14 = AutoConfigUrlTrackerFromSettings;
    goto LABEL_17;
  }
  v2 = v33;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qq(1029, 28, (unsigned int)WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids, (_DWORD)this, (__int64)v33);
  v23 = AutoProxyResolver::DownloadAutoConfigUrl(this, v27, v2, &v37);
  v14 = v23;
  if ( v23 == -2146685199 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    AutoProxyBase::SetState(this, 2, 0);
    *((_QWORD *)this + 39) = ++*((_QWORD *)this + 40);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
LABEL_55:
    v14 = -2146685199;
    goto LABEL_28;
  }
  if ( v23 >= 0 )
  {
    v28 = v35;
    v29 = 1;
    v25 = AutoProxyResolver::SetCurrentScriptHandler(this, v37, v35, 0, 0);
    v11 = v25;
    if ( v25 < 0 )
    {
      v14 = v25;
      goto LABEL_17;
    }
    AutoProxyResolver::GetAutoProxyConfigExpirationTime(this, v37);
    goto LABEL_53;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 4LL) & 8) == 0 )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_q(1029, 30, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids);
    AutoProxyResolver::CancelBackgroundDetection(this, 0);
LABEL_53:
    AutoProxyResolver::QueueBackgroundDetection(this);
    goto LABEL_16;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 29, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids);
  MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_16:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v26 = 1;
  AutoProxyResolver::CheckForTimerConfigChanges(this, *(_DWORD *)(*((_QWORD *)v3 + 1) + 72LL));
  v11 = v14;
  if ( v14 < 0 )
  {
LABEL_17:
    v17 = v26;
    goto LABEL_18;
  }
LABEL_20:
  v6 = *(unsigned int *)(*((_QWORD *)v3 + 1) + 8LL);
  v17 = v26;
  *((_DWORD *)this + 51) = v6;
LABEL_21:
  v18 = v28;
LABEL_22:
  if ( v17 )
  {
    LeaveCriticalSection(v8);
    v26 = 0;
  }
  if ( v14 < 0 && !v29 )
    AutoProxyResolver::SetCurrentScriptHandler(this, 0, v18, 0, v11);
LABEL_27:
  if ( v26 )
LABEL_60:
    LeaveCriticalSection(v8);
LABEL_28:
  if ( v30 && **((_DWORD **)this + 30) && Microsoft_Windows_WinHttpEnableBits < 0 )
    McTemplateU0q_EtwEventWriteTransfer(v6, WINHTTP_AUTOPROXY_PERFTRACK_ALL_STOP, v31);
  ProxySettingsAllocator::Free((void ***)&v34);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qD(1029, 31, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids, this);
  if ( v37 )
  {
    ScriptHandler::Release(v37);
    v37 = 0;
  }
  if ( v3 )
    StructStorage<tagProxySettings,ProxySettingsAllocator>::Release((void *)v3);
  if ( v2 )
    (*(void (__fastcall **)(struct AutoConfigUrlTracker *))(*(_QWORD *)v2 + 8LL))(v2);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180052c30  push    rbp
0x180052c32  push    rbx
0x180052c33  push    rsi
0x180052c34  push    rdi
0x180052c35  push    r12
0x180052c37  push    r13
0x180052c39  push    r14
0x180052c3b  push    r15
0x180052c3d  lea     rbp, [rsp-1Fh]
0x180052c42  sub     rsp, 0A8h
0x180052c49  mov     rax, cs:__security_cookie
0x180052c50  xor     rax, rsp
0x180052c53  mov     [rbp+57h+var_50], rax
0x180052c57  xor     r12d, r12d
0x180052c5a  mov     [rbp+57h+var_7C], edx
0x180052c5d  mov     [rbp+57h+var_94], r12d
0x180052c61  mov     edi, r12d
0x180052c64  mov     [rbp+57h+var_78], r12
0x180052c68  mov     ebx, r12d
0x180052c6b  mov     [rbp+57h+var_58], r12
0x180052c6f  mov     eax, edx
0x180052c71  mov     [rbp+57h+var_88], r12d
0x180052c75  mov     rsi, rcx
0x180052c78  mov     [rbp+57h+var_80], r12d
0x180052c7c  test    byte ptr cs:xmmword_180107A60, 20h
0x180052c83  mov     r13d, 405h
0x180052c89  jnz     loc_1800530E1
0x180052c8f  mov     eax, [rsi+1C8h]
0x180052c95  mov     [rbp+57h+var_84], eax
0x180052c98  mov     [rsi+1C8h], r12d
0x180052c9f  test    eax, eax
0x180052ca1  jnz     loc_180052F31
0x180052ca7  mov     r15d, 70h ; 'p'
0x180052cad  mov     [rbp+57h+var_8C], r12d
0x180052cb1  mov     ecx, r15d; cb
0x180052cb4  mov     [rbp+57h+var_70], r12
0x180052cb8  call    cs:__imp_CoTaskMemAlloc
0x180052cbe  mov     r14, rax
0x180052cc1  test    rax, rax
0x180052cc4  jz      loc_180052F6A
0x180052cca  mov     r8d, r15d; Size
0x180052ccd  xor     edx, edx; Val
0x180052ccf  mov     rcx, rax; void *
0x180052cd2  call    memset_0
0x180052cd7  mov     [rbp+57h+var_70], r14
0x180052cdb  lea     r15, [rsi+98h]
0x180052ce2  mov     rcx, r15; lpCriticalSection
0x180052ce5  call    cs:__imp_EnterCriticalSection
0x180052ceb  mov     rcx, [rsi+200h]; hEvent
0x180052cf2  call    cs:__imp_ResetEvent
0x180052cf8  mov     rax, [rsi+1E0h]
0x180052cff  test    rax, rax
0x180052d02  jz      short loc_180052D0B
0x180052d04  mov     dword ptr [rax+50h], 1
0x180052d0b  mov     eax, [rsi+208h]
0x180052d11  mov     [rsi+20Ch], eax
0x180052d17  test    eax, eax
0x180052d19  jnz     loc_180053101
0x180052d1f  mov     rax, [rsi+210h]
0x180052d26  mov     rcx, rsi; this
0x180052d29  mov     [rbp-41h], rax
0x180052d2d  mov     rax, [rsi+140h]
0x180052d34  inc     rax
0x180052d37  mov     [rbp-39h], rax
0x180052d3b  inc     rax
0x180052d3e  mov     [rbp+57h+var_68], rax
0x180052d42  mov     [rsi+140h], rax
0x180052d49  call    ?UpdateSessionStatusGeneration@AutoProxyResolver@@QEAAXXZ; AutoProxyResolver::UpdateSessionStatusGeneration(void)
0x180052d4e  lea     rcx, [rsi+20h]
0x180052d52  mov     rdx, r14
0x180052d55  call    ??$CopyProxySettings@VWxCoTaskAllocator@@@@YAJPEBUtagProxySettings@@PEAU0@@Z; CopyProxySettings<WxCoTaskAllocator>(tagProxySettings const *,tagProxySettings *)
0x180052d5a  mov     r12d, eax
0x180052d5d  mov     r13d, 800C2EF1h
0x180052d63  test    eax, eax
0x180052d65  js      loc_18005313F
0x180052d6b  mov     rcx, r15; lpCriticalSection
0x180052d6e  call    cs:__imp_LeaveCriticalSection
0x180052d74  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180052d7b  xor     eax, eax
0x180052d7d  xor     edx, edx; dwFlags
0x180052d7f  mov     [rbp+57h+var_A0], eax
0x180052d82  mov     [rbp+57h+var_5C], eax
0x180052d85  lea     r8d, [rax+10h]; dwBytes
0x180052d89  call    cs:__imp_HeapAlloc
0x180052d8f  mov     rbx, rax
0x180052d92  test    rax, rax
0x180052d95  jz      loc_18005325F
0x180052d9b  mov     [rax], rdi
0x180052d9e  lea     r12, [rax+8]
0x180052da2  mov     [r12], rdi
0x180052da6  mov     dword ptr [rax], 1
0x180052dac  cmp     [r12], rdi
0x180052db0  jnz     loc_180052F24
0x180052db6  mov     [r12], r14
0x180052dba  xor     r8d, r8d
0x180052dbd  xor     r14d, r14d
0x180052dc0  mov     [rbp+57h+var_70], rdi
0x180052dc4  mov     rcx, rsi
0x180052dc7  lea     edx, [r14+2]
0x180052dcb  call    ?SetState@AutoProxyBase@@IEAAXW4_AUTO_PROXY_STATE@@J@Z; AutoProxyBase::SetState(_AUTO_PROXY_STATE,long)
0x180052dd0  mov     rax, [rbx+8]
0x180052dd4  mov     r12, [rbp-39h]
0x180052dd8  test    byte ptr [rax+4], 8
0x180052ddc  jz      short loc_180052E14
0x180052dde  mov     r8, [rbp-41h]
0x180052de2  lea     rax, [rbp+57h+var_58]
0x180052de6  mov     [rsp+0E0h+var_B8], rax; __int64
0x180052deb  mov     r9, rbx
0x180052dee  mov     eax, [rbp+57h+var_84]
0x180052df1  mov     rdx, r12
0x180052df4  mov     rcx, rsi; this
0x180052df7  mov     [rsp+0E0h+var_C0], eax; int
0x180052dfb  call    ?QueueAndWaitForDetections@AutoProxyResolver@@AEAAJ_K0PEAV?$StructStorage@UtagProxySettings@@VProxySettingsAllocator@@@@HPEAPEAVScriptHandler@@@Z; AutoProxyResolver::QueueAndWaitForDetections(unsigned __int64,unsigned __int64,StructStorage<tagProxySettings,ProxySettingsAllocator> *,int,ScriptHandler * *)
0x180052e00  mov     r14d, eax
0x180052e03  cmp     eax, r13d
0x180052e06  jz      loc_1800530A2
0x180052e0c  test    eax, eax
0x180052e0e  jns     loc_180053156
0x180052e14  mov     rax, [rbx+8]
0x180052e18  test    byte ptr [rax+4], 4
0x180052e1c  jnz     loc_180052F95
0x180052e22  mov     rcx, r15; lpCriticalSection
0x180052e25  call    cs:__imp_EnterCriticalSection
0x180052e2b  mov     rdx, [rbx+8]
0x180052e2f  mov     rcx, rsi; this
0x180052e32  mov     [rbp+57h+var_A0], 1
0x180052e39  mov     edx, [rdx+48h]; unsigned int
0x180052e3c  call    ?CheckForTimerConfigChanges@AutoProxyResolver@@AEAAKK@Z; AutoProxyResolver::CheckForTimerConfigChanges(ulong)
0x180052e41  mov     r12d, r14d
0x180052e44  test    r14d, r14d
0x180052e47  jns     short loc_180052E5D
0x180052e49  mov     [rbp+57h+var_94], 39Ch
0x180052e50  mov     eax, [rbp+57h+var_A0]
0x180052e53  cmp     r14d, r13d
0x180052e56  jz      short loc_180052EA5
0x180052e58  test    rbx, rbx
0x180052e5b  jz      short loc_180052E6D
0x180052e5d  mov     rax, [rbx+8]
0x180052e61  mov     ecx, [rax+8]
0x180052e64  mov     eax, [rbp+57h+var_A0]
0x180052e67  mov     [rsi+0CCh], ecx
0x180052e6d  mov     r13, [rbp-39h]
0x180052e71  test    eax, eax
0x180052e73  jz      short loc_180052E85
0x180052e75  mov     rcx, r15; lpCriticalSection
0x180052e78  call    cs:__imp_LeaveCriticalSection
0x180052e7e  mov     [rbp+57h+var_A0], 0
0x180052e85  test    r14d, r14d
0x180052e88  jns     short loc_180052EA5
0x180052e8a  cmp     [rbp+57h+var_88], 0
0x180052e8e  jnz     short loc_180052EA5
0x180052e90  xor     r9d, r9d; int
0x180052e93  mov     [rsp+0E0h+var_C0], r12d; int
0x180052e98  mov     r8, r13; unsigned __int64
0x180052e9b  xor     edx, edx; struct ScriptHandler *
0x180052e9d  mov     rcx, rsi; this
0x180052ea0  call    ?SetCurrentScriptHandler@AutoProxyResolver@@AEAAJPEAVScriptHandler@@_KHJ@Z; AutoProxyResolver::SetCurrentScriptHandler(ScriptHandler *,unsigned __int64,int,long)
0x180052ea5  cmp     [rbp+57h+var_A0], 0
0x180052ea9  jnz     loc_180053131
0x180052eaf  xor     r15d, r15d
0x180052eb2  cmp     [rbp+57h+var_84], r15d
0x180052eb6  jz      short loc_180052EC8
0x180052eb8  mov     rax, [rsi+0F0h]
0x180052ebf  cmp     [rax], r15d
0x180052ec2  jnz     loc_18005327F
0x180052ec8  lea     rcx, [rbp+57h+var_70]; void **
0x180052ecc  call    ?Free@ProxySettingsAllocator@@SAXPEAPEAX@Z; ProxySettingsAllocator::Free(void * *)
0x180052ed1  test    byte ptr cs:xmmword_180107A60, 20h
0x180052ed8  jnz     loc_1800532A1
0x180052ede  mov     rcx, [rbp+57h+var_58]; this
0x180052ee2  test    rcx, rcx
0x180052ee5  jnz     loc_1800532C4
0x180052eeb  test    rbx, rbx
0x180052eee  jz      short loc_180052EF8
0x180052ef0  mov     rcx, rbx; void *
0x180052ef3  call    ?Release@?$StructStorage@UtagProxySettings@@VProxySettingsAllocator@@@@QEAAKXZ; StructStorage<tagProxySettings,ProxySettingsAllocator>::Release(void)
0x180052ef8  test    rdi, rdi
0x180052efb  jnz     loc_180053046
0x180052f01  mov     eax, r14d
0x180052f04  mov     rcx, [rbp+57h+var_50]
0x180052f08  xor     rcx, rsp; StackCookie
0x180052f0b  call    __security_check_cookie
0x180052f10  add     rsp, 0A8h
0x180052f17  pop     r15
0x180052f19  pop     r14
0x180052f1b  pop     r13
0x180052f1d  pop     r12
0x180052f1f  pop     rdi
0x180052f20  pop     rsi
0x180052f21  pop     rbx
0x180052f22  pop     rbp
0x180052f23  retn
0x180052f24  mov     rcx, r12; void **
0x180052f27  call    ?Free@ProxySettingsAllocator@@SAXPEAPEAX@Z; ProxySettingsAllocator::Free(void * *)
0x180052f2c  jmp     loc_180052DB6
0x180052f31  mov     rax, [rsi+0F0h]
0x180052f38  cmp     [rax], r12d
0x180052f3b  jz      loc_180052CA7
0x180052f41  call    ?GetNextUniquePerfTrackId@@YAKXZ; GetNextUniquePerfTrackId(void)
0x180052f46  cmp     cs:Microsoft_Windows_WinHttpEnableBits, r12b
0x180052f4d  mov     [rbp+57h+var_80], eax
0x180052f50  jge     loc_180052CA7
0x180052f56  mov     r8d, eax
0x180052f59  lea     rdx, WINHTTP_AUTOPROXY_PERFTRACK_ALL_START
0x180052f60  call    McTemplateU0q_EtwEventWriteTransfer
0x180052f65  jmp     loc_180052CA7
0x180052f6a  mov     r14d, 8007000Eh
0x180052f70  mov     [rbp+57h+var_8C], 4Ch ; 'L'
0x180052f77  xor     eax, eax
0x180052f79  mov     [rbp+57h+var_94], 2BBh
0x180052f80  mov     r13, r12
0x180052f83  mov     [rbp+57h+var_A0], eax
0x180052f86  mov     r12d, r14d
0x180052f89  lea     r15, [rsi+98h]
0x180052f90  jmp     loc_180052E71
0x180052f95  cmp     [rax+28h], rdi
0x180052f99  jz      loc_180052E22
0x180052f9f  mov     r14, [rbp-41h]
0x180052fa3  lea     rax, [rbp+57h+var_78]
0x180052fa7  mov     r9d, [rbp+57h+var_84]
0x180052fab  mov     r8, r12
0x180052fae  mov     [rsp+0E0h+var_B0], rax
0x180052fb3  mov     rdx, rbx
0x180052fb6  mov     eax, [rbp+57h+var_7C]
0x180052fb9  mov     rcx, rsi
0x180052fbc  mov     [rsp+0E0h+var_B8], r14
0x180052fc1  mov     [rsp+0E0h+var_C0], eax
0x180052fc5  call    ?CreateAutoConfigUrlTrackerFromSettings@AutoProxyResolver@@AEAAJPEAV?$StructStorage@UtagProxySettings@@VProxySettingsAllocator@@@@_KHH1PEAPEAVAutoConfigUrlTracker@@@Z; AutoProxyResolver::CreateAutoConfigUrlTrackerFromSettings(StructStorage<tagProxySettings,ProxySettingsAllocator> *,unsigned __int64,int,int,unsigned __int64,AutoConfigUrlTracker * *)
0x180052fca  mov     r12d, eax
0x180052fcd  test    eax, eax
0x180052fcf  js      loc_18005318F
0x180052fd5  mov     rdi, [rbp+57h+var_78]
0x180052fd9  mov     r12b, 20h ; ' '
0x180052fdc  test    byte ptr cs:xmmword_180107A60, r12b
0x180052fe3  jnz     loc_1800531A2
0x180052fe9  lea     r9, [rbp+57h+var_58]; struct ScriptHandler **
0x180052fed  mov     r8, rdi; struct AutoConfigUrlTracker *
0x180052ff0  mov     rdx, r14; unsigned __int64
0x180052ff3  mov     rcx, rsi; this
0x180052ff6  call    ?DownloadAutoConfigUrl@AutoProxyResolver@@AEAAJ_KPEAVAutoConfigUrlTracker@@PEAPEAVScriptHandler@@@Z; AutoProxyResolver::DownloadAutoConfigUrl(unsigned __int64,AutoConfigUrlTracker *,ScriptHandler * *)
0x180052ffb  mov     r14d, eax
0x180052ffe  cmp     eax, r13d
0x180053001  jz      short loc_18005305A
0x180053003  test    eax, eax
0x180053005  jns     loc_1800531C5
0x18005300b  mov     rax, [rbx+8]
0x18005300f  test    byte ptr [rax+4], 8
0x180053013  jnz     loc_180053215
0x180053019  test    byte ptr cs:xmmword_180107A60, r12b
0x180053020  jnz     loc_180053241
0x180053026  xor     edx, edx; int
0x180053028  mov     rcx, rsi; this
0x18005302b  call    ?CancelBackgroundDetection@AutoProxyResolver@@AEAAJH@Z; AutoProxyResolver::CancelBackgroundDetection(int)
0x180053030  mov     r8d, 0BB8h
0x180053036  mov     rdx, rbx
0x180053039  mov     rcx, rsi; this
0x18005303c  call    ?QueueBackgroundDetection@AutoProxyResolver@@AEAAJPEAV?$StructStorage@UtagProxySettings@@VProxySettingsAllocator@@@@K@Z; AutoProxyResolver::QueueBackgroundDetection(StructStorage<tagProxySettings,ProxySettingsAllocator> *,ulong)
0x180053041  jmp     loc_180052E22
0x180053046  mov     rcx, [rdi]
0x180053049  mov     rax, [rcx+8]
0x18005304d  mov     rcx, rdi
0x180053050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053055  jmp     loc_180052F01
0x18005305a  mov     rcx, r15; lpCriticalSection
0x18005305d  call    cs:__imp_EnterCriticalSection
0x180053063  xor     r8d, r8d
0x180053066  mov     rcx, rsi
0x180053069  lea     edx, [r8+2]
0x18005306d  call    ?SetState@AutoProxyBase@@IEAAXW4_AUTO_PROXY_STATE@@J@Z; AutoProxyBase::SetState(_AUTO_PROXY_STATE,long)
0x180053072  inc     qword ptr [rsi+140h]
0x180053079  mov     rcx, r15; lpCriticalSection
0x18005307c  mov     rax, [rsi+140h]
0x180053083  mov     [rsi+138h], rax
0x18005308a  call    cs:__imp_LeaveCriticalSection
0x180053090  mov     [rbp+57h+var_94], 34Bh
0x180053097  mov     r12d, r13d
0x18005309a  mov     r14d, r13d
0x18005309d  jmp     loc_180052EAF
0x1800530a2  mov     rcx, r15; lpCriticalSection
0x1800530a5  call    cs:__imp_EnterCriticalSection
0x1800530ab  xor     r8d, r8d
0x1800530ae  mov     rcx, rsi
0x1800530b1  lea     edx, [r8+2]
0x1800530b5  call    ?SetState@AutoProxyBase@@IEAAXW4_AUTO_PROXY_STATE@@J@Z; AutoProxyBase::SetState(_AUTO_PROXY_STATE,long)
0x1800530ba  inc     qword ptr [rsi+140h]
0x1800530c1  mov     rcx, r15; lpCriticalSection
0x1800530c4  mov     rax, [rsi+140h]
0x1800530cb  mov     [rsi+138h], rax
0x1800530d2  call    cs:__imp_LeaveCriticalSection
0x1800530d8  mov     [rbp+57h+var_94], 30Ah
0x1800530df  jmp     short loc_180053097
0x1800530e1  mov     edx, 1Ah
0x1800530e6  mov     [rsp+0E0h+var_C0], eax
0x1800530ea  mov     ecx, r13d
0x1800530ed  lea     r8, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids
0x1800530f4  mov     r9, rsi
0x1800530f7  call    WPP_SF_qD
0x1800530fc  jmp     loc_180052C8F
0x180053101  test    byte ptr cs:xmmword_180107A60, 20h
0x180053108  jz      short loc_18005311E
  ... truncated ...
```

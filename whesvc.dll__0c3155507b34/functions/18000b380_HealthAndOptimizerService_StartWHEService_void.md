# HealthAndOptimizerService::StartWHEService(void)

- ea: `0x18000b380`
- end: `0x18000b5be`
- name: `?StartWHEService@HealthAndOptimizerService@@SAXXZ`
- size: `574`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008ba8`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x180009024`
- `0x180009044`
- `0x18000a4f0`
- `0x18000a80c`
- `0x18000b1d8`
- `0x18000b380`
- `0x18000b5c4`
- `0x18000ba38`
- `0x18000f484`
- `0x1800142e0`
- `0x1800145dc`
- `0x1800153dc`
- `0x180016754`
- `0x180020ba4`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b417`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b417`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000b421`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000b421`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b411`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b411`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000b436`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000b436`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b3e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b3e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void HealthAndOptimizerService::StartWHEService(void)
{
  int ValueW; // eax
  const char *v1; // r9
  _unnamed_type_WinDiag_ *v2; // rcx
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rdx
  OrchestratorSingleton *Instance; // rdi
  int pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD pvData[3]; // [rsp+44h] [rbp-BCh] BYREF
  void **v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+58h] [rbp-A8h] BYREF
  char v12; // [rsp+5Ch] [rbp-A4h]
  int v13; // [rsp+80h] [rbp-80h] BYREF
  const char *v14; // [rsp+88h] [rbp-78h]
  __int64 v15; // [rsp+90h] [rbp-70h]
  char v16; // [rsp+98h] [rbp-68h]
  int v17; // [rsp+A0h] [rbp-60h]
  _BYTE v18[152]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v19; // [rsp+140h] [rbp+40h]
  int v20; // [rsp+150h] [rbp+50h]
  __int64 v21; // [rsp+158h] [rbp+58h]
  int *v22; // [rsp+160h] [rbp+60h]
  __int64 v23; // [rsp+168h] [rbp+68h]
  __int64 v24; // [rsp+170h] [rbp+70h]
  void ***v25; // [rsp+178h] [rbp+78h]
  __int64 v26; // [rsp+180h] [rbp+80h]
  int v27; // [rsp+188h] [rbp+88h]
  int *v28; // [rsp+190h] [rbp+90h]
  char v29; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  pvData[0] = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\whesvc",
             L"WaitForDebugger",
             0x10u,
             0,
             pvData,
             &pcbData);
  if ( ValueW > 0 )
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  if ( ValueW >= 0 && pvData[0] == 1 )
  {
    while ( !IsDebuggerPresent() )
      Sleep(0x3E8u);
    DebugBreak();
  }
  pcbData = 1;
  if ( (unsigned int)SetProcessMitigationPolicy(16, &pcbData, 4)
    || (int)wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x17,
              (unsigned int)"pcshell\\base\\whesvc\\lib\\healthandoptimizersvc.cpp",
              v1) >= 0 )
  {
    v11 = 0;
    v12 = 0;
    v16 = 0;
    v13 = 0;
    v14 = "WhesvcStartActivity";
    v15 = 0;
    v17 = 0;
    v19 = 0;
    memset_0(v18, 0, sizeof(v18));
    v20 = 1;
    v21 = 0;
    v22 = &v11;
    v23 = 0;
    v24 = 0;
    v25 = &v10;
    v26 = 0;
    v27 = 0;
    v28 = &v13;
    v29 = 0;
    v10 = &WhesvcTelemetryProvider::WhesvcStartActivity::`vftable';
    WhesvcTelemetryProvider::WhesvcStartActivity::StartActivity((WhesvcTelemetryProvider::WhesvcStartActivity *)&v10);
    if ( (int)InitializeAssetLoader() < 0 )
      goto LABEL_22;
    v3 = _unnamed_type_WinDiag_::Initialize(v2);
    v4 = v3;
    if ( v3 >= 0 )
    {
      Instance = OrchestratorSingleton::GetInstance();
      v3 = OrchestratorSingleton::Initialize(Instance);
      v4 = v3;
      if ( v3 >= 0 )
      {
        v3 = OrchestratorSingleton::RegisterOneSettingsConfigChangeWNF(Instance);
        v4 = v3;
        if ( v3 >= 0 )
        {
          v4 = 0;
LABEL_20:
          if ( v4 >= 0 )
          {
            StartWindiagModuleWithUri("builtin://scenario/init", "00000000-0000-0000-0000-000000000000", 0, 0);
            wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v10);
LABEL_23:
            v10 = &WhesvcTelemetryProvider::WhesvcStartActivity::`vftable';
            wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v10);
            wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(&v10);
            return;
          }
LABEL_22:
          HealthAndOptimizerService::StopWHEService();
          goto LABEL_23;
        }
        v5 = 729;
      }
      else
      {
        v5 = 727;
      }
    }
    else
    {
      v5 = 723;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)(unsigned int)v3,
      pdwType);
    goto LABEL_20;
  }
}

```

## disassembly

```asm
0x18000b380  push    rbp
0x18000b382  push    rbx
0x18000b383  push    rsi
0x18000b384  push    rdi
0x18000b385  push    r14
0x18000b387  lea     rbp, [rsp-0B0h]
0x18000b38f  sub     rsp, 1B0h
0x18000b396  mov     rax, cs:__security_cookie
0x18000b39d  xor     rax, rsp
0x18000b3a0  mov     [rbp+0D0h+var_30], rax
0x18000b3a7  xor     esi, esi
0x18000b3a9  mov     [rsp+1D0h+var_18C], esi
0x18000b3ad  lea     edi, [rsi+4]
0x18000b3b0  mov     [rsp+1D0h+var_190], edi
0x18000b3b4  lea     rax, [rsp+1D0h+var_190]
0x18000b3b9  mov     [rsp+1D0h+pcbData], rax; pcbData
0x18000b3be  lea     rax, [rsp+1D0h+var_18C]
0x18000b3c3  mov     [rsp+1D0h+pvData], rax; pvData
0x18000b3c8  mov     [rsp+1D0h+pdwType], rsi; pdwType
0x18000b3cd  lea     r14d, [rsi+10h]
0x18000b3d1  mov     r9d, r14d; dwFlags
0x18000b3d4  lea     r8, Value; "WaitForDebugger"
0x18000b3db  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000b3e2  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000b3e9  call    cs:__imp_RegGetValueW
0x18000b3ef  test    eax, eax
0x18000b3f1  jle     short loc_18000B3FB
0x18000b3f3  movzx   eax, ax
0x18000b3f6  or      eax, 80070000h
0x18000b3fb  mov     ebx, 1
0x18000b400  test    eax, eax
0x18000b402  js      short loc_18000B427
0x18000b404  cmp     [rsp+1D0h+var_18C], ebx
0x18000b408  jnz     short loc_18000B427
0x18000b40a  jmp     short loc_18000B417
0x18000b40c  mov     ecx, 3E8h; dwMilliseconds
0x18000b411  call    cs:__imp_Sleep
0x18000b417  call    cs:__imp_IsDebuggerPresent
0x18000b41d  test    eax, eax
0x18000b41f  jz      short loc_18000B40C
0x18000b421  call    cs:__imp_DebugBreak
0x18000b427  mov     [rsp+1D0h+var_190], ebx
0x18000b42b  mov     r8, rdi
0x18000b42e  lea     rdx, [rsp+1D0h+var_190]
0x18000b433  mov     ecx, r14d
0x18000b436  call    cs:__imp_SetProcessMitigationPolicy
0x18000b43c  test    eax, eax
0x18000b43e  jnz     short loc_18000B45E
0x18000b440  mov     rcx, [rbp+0D8h]; this
0x18000b447  lea     r8, aPcshellBaseWhe_5; "pcshell\\base\\whesvc\\lib\\healthandop"...
0x18000b44e  lea     edx, [rax+17h]; void *
0x18000b451  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b456  test    eax, eax
0x18000b458  js      loc_18000B5A1
0x18000b45e  mov     [rsp+1D0h+var_178], esi
0x18000b462  mov     [rsp+1D0h+var_174], sil
0x18000b467  mov     [rbp+0D0h+var_138], sil
0x18000b46b  mov     [rbp+0D0h+var_150], esi
0x18000b46e  lea     rax, aWhesvcstartact; "WhesvcStartActivity"
0x18000b475  mov     [rbp+0D0h+var_148], rax
0x18000b479  mov     [rbp+0D0h+var_140], rsi
0x18000b47d  mov     [rbp+0D0h+var_130], esi
0x18000b480  xorps   xmm0, xmm0
0x18000b483  movdqa  [rbp+0D0h+var_90], xmm0
0x18000b488  xor     edx, edx; Val
0x18000b48a  mov     r8d, 98h; Size
0x18000b490  lea     rcx, [rbp+0D0h+var_128]; void *
0x18000b494  call    memset_0
0x18000b499  mov     [rbp+0D0h+var_80], ebx
0x18000b49c  xor     eax, eax
0x18000b49e  mov     [rbp+0D0h+var_78], rax
0x18000b4a2  lea     rax, [rsp+1D0h+var_178]
0x18000b4a7  mov     [rbp+0D0h+var_70], rax
0x18000b4ab  mov     [rbp+0D0h+var_68], rsi
0x18000b4af  mov     [rbp+0D0h+var_60], rsi
0x18000b4b3  lea     rax, [rsp+1D0h+var_180]
0x18000b4b8  mov     [rbp+0D0h+var_58], rax
0x18000b4bc  mov     [rbp+0D0h+var_50], rsi
0x18000b4c3  mov     [rbp+0D0h+var_48], esi
0x18000b4c9  lea     rax, [rbp+0D0h+var_150]
0x18000b4cd  mov     [rbp+0D0h+var_40], rax
0x18000b4d4  mov     [rbp+0D0h+var_38], sil
0x18000b4db  lea     r14, ??_7WhesvcStartActivity@WhesvcTelemetryProvider@@6B@; const WhesvcTelemetryProvider::WhesvcStartActivity::`vftable'
0x18000b4e2  mov     [rsp+1D0h+var_180], r14
0x18000b4e7  lea     rcx, [rsp+1D0h+var_180]; this
0x18000b4ec  call    ?StartActivity@WhesvcStartActivity@WhesvcTelemetryProvider@@QEAAXXZ; WhesvcTelemetryProvider::WhesvcStartActivity::StartActivity(void)
0x18000b4f1  call    ?InitializeAssetLoader@@YAJXZ; InitializeAssetLoader(void)
0x18000b4f6  test    eax, eax
0x18000b4f8  js      loc_18000B583
0x18000b4fe  call    ?Initialize@_unnamed_type_WinDiag_@@QEAAJXZ; _unnamed_type_WinDiag_::Initialize(void)
0x18000b503  mov     ebx, eax
0x18000b505  test    eax, eax
0x18000b507  jns     short loc_18000B526
0x18000b509  mov     edx, 2D3h; void *
0x18000b50e  mov     rcx, [rbp+0D8h]; this
0x18000b515  mov     r9d, eax; char *
0x18000b518  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x18000b51f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b524  jmp     short loc_18000B55A
0x18000b526  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x18000b52b  mov     rdi, rax
0x18000b52e  mov     rcx, rax; this
0x18000b531  call    ?Initialize@OrchestratorSingleton@@QEAAJXZ; OrchestratorSingleton::Initialize(void)
0x18000b536  mov     ebx, eax
0x18000b538  test    eax, eax
0x18000b53a  jns     short loc_18000B543
0x18000b53c  mov     edx, 2D7h
0x18000b541  jmp     short loc_18000B50E
0x18000b543  mov     rcx, rdi; this
0x18000b546  call    ?RegisterOneSettingsConfigChangeWNF@OrchestratorSingleton@@QEAAJXZ; OrchestratorSingleton::RegisterOneSettingsConfigChangeWNF(void)
0x18000b54b  mov     ebx, eax
0x18000b54d  test    eax, eax
0x18000b54f  jns     short loc_18000B558
0x18000b551  mov     edx, 2D9h
0x18000b556  jmp     short loc_18000B50E
0x18000b558  mov     ebx, esi
0x18000b55a  test    ebx, ebx
0x18000b55c  js      short loc_18000B583
0x18000b55e  xor     r9d, r9d; unsigned int
0x18000b561  xor     r8d, r8d; void *
0x18000b564  lea     rdx, a00000000000000; "00000000-0000-0000-0000-000000000000"
0x18000b56b  lea     rcx, aBuiltinScenari; "builtin://scenario/init"
0x18000b572  call    ?StartWindiagModuleWithUri@@YAJPEBD0QEAXK@Z; StartWindiagModuleWithUri(char const *,char const *,void * const,ulong)
0x18000b577  lea     rcx, [rsp+1D0h+var_180]
0x18000b57c  call    ?Stop@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000b581  jmp     short loc_18000B588
0x18000b583  call    ?StopWHEService@HealthAndOptimizerService@@SAXXZ; HealthAndOptimizerService::StopWHEService(void)
0x18000b588  mov     [rsp+1D0h+var_180], r14
0x18000b58d  lea     rcx, [rsp+1D0h+var_180]
0x18000b592  call    ?Destroy@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000b597  lea     rcx, [rsp+1D0h+var_180]
0x18000b59c  call    ??1?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000b5a1  mov     rcx, [rbp+0D0h+var_30]
0x18000b5a8  xor     rcx, rsp; StackCookie
0x18000b5ab  call    __security_check_cookie
0x18000b5b0  add     rsp, 1B0h
0x18000b5b7  pop     r14
0x18000b5b9  pop     rdi
0x18000b5ba  pop     rsi
0x18000b5bb  pop     rbx
0x18000b5bc  pop     rbp
0x18000b5bd  retn
```

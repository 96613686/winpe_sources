# CBlbServiceModule::ServiceMain(ulong,ushort * *)

- ea: `0x140066458`
- end: `0x1400668f2`
- name: `?ServiceMain@CBlbServiceModule@@QEAAXKPEAPEAG@Z`
- size: `1178`
- prototype: `void __fastcall(CBlbServiceModule *this, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callers

- `0x1400687c0`

## callees

- `0x14000bb24`
- `0x14000bb4c`
- `0x140047a50`
- `0x140061784`
- `0x140066458`
- `0x1400687cc`
- `0x140069188`
- `0x140095c58`
- `0x1400d7934`
- `0x1400f3f60`
- `0x1401090f0`
- `0x14010b944`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x1400668c1`
- `ADVAPI32!UnregisterTraceGuids` at `0x1400668c1`
- `ADVAPI32!SetServiceStatus` at `0x1400665ea`
- `ADVAPI32!SetServiceStatus` at `0x1400665ea`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x1400665a0`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x1400665a0`
- `KERNEL32!HeapSetInformation` at `0x1400665fb`
- `KERNEL32!HeapSetInformation` at `0x1400665fb`
- `KERNEL32!CreateWaitableTimerW` at `0x140066795`
- `KERNEL32!CreateWaitableTimerW` at `0x140066795`
- `KERNEL32!CreateThread` at `0x14006680d`
- `KERNEL32!CreateThread` at `0x14006680d`
- `KERNEL32!CloseHandle` at `0x140066737`
- `KERNEL32!CloseHandle` at `0x140066749`
- `KERNEL32!CloseHandle` at `0x140066737`
- `KERNEL32!CloseHandle` at `0x140066749`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140066662`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140066662`
- `KERNEL32!DeleteCriticalSection` at `0x14006675b`
- `KERNEL32!DeleteCriticalSection` at `0x14006675b`
- `KERNEL32!GetLastError` at `0x1400665b2`
- `KERNEL32!GetLastError` at `0x140066605`
- `KERNEL32!GetLastError` at `0x14006660f`
- `KERNEL32!GetLastError` at `0x140066619`
- `KERNEL32!GetLastError` at `0x140066693`
- `KERNEL32!GetLastError` at `0x1400667a7`
- `KERNEL32!GetLastError` at `0x14006681b`
- `KERNEL32!GetLastError` at `0x1400665b2`
- `KERNEL32!GetLastError` at `0x140066605`
- `KERNEL32!GetLastError` at `0x14006660f`
- `KERNEL32!GetLastError` at `0x140066619`
- `KERNEL32!GetLastError` at `0x140066693`
- `KERNEL32!GetLastError` at `0x1400667a7`
- `KERNEL32!GetLastError` at `0x14006681b`

## pseudocode

```c
void __fastcall CBlbServiceModule::ServiceMain(CBlbServiceModule *this, __int64 a2, unsigned __int16 **a3)
{
  CBlbServiceModule *v3; // r14
  int started; // eax
  PVOID *v5; // rcx
  __int64 v6; // rdx
  SERVICE_STATUS_HANDLE v7; // rax
  HANDLE Thread; // rbp
  signed int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  __int64 v13; // rdx
  _QWORD *v14; // rbx
  signed int v15; // eax
  signed int v16; // eax
  int v17; // edx
  unsigned __int16 **v18; // r8
  TRACEHANDLE v19; // rcx
  DWORD LastError; // [rsp+58h] [rbp+10h] BYREF

  v3 = ATL::_pAtlModule;
  LastError = 0;
  qword_14015F5C0 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_BLB;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  qword_14015F5C8 = 1;
  WppInitUm(this, a2, a3);
  started = BlbStartTracing();
  *((_BYTE *)v3 + 668) = started == 0;
  if ( started >= 0 )
  {
    if ( started )
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_21;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        goto LABEL_17;
      v6 = 42;
    }
    else
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_21;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        goto LABEL_17;
      v6 = 41;
    }
    WPP_SF_(v5[2], v6, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
    goto LABEL_16;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_21;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
LABEL_16:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_17:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
    WPP_SF_(v5[2], 44, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
LABEL_21:
  v7 = RegisterServiceCtrlHandlerW((LPCWSTR)v3 + 52, ATL::CAtlServiceModuleT<CBlbServiceModule,102>::_Handler);
  *((_QWORD *)v3 + 77) = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    PublishServiceEvent(2, 4, &LastError);
    return;
  }
  *((_DWORD *)v3 + 157) = 2;
  Thread = 0;
  SetServiceStatus(v7, (LPSERVICE_STATUS)((char *)v3 + 624));
  if ( !HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0) )
  {
    if ( (int)GetLastError() > 0 )
      v9 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v9 = GetLastError();
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 45;
LABEL_71:
      WPP_SF_d(v10[2], v11, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
      goto LABEL_72;
    }
    goto LABEL_73;
  }
  if ( !InitializeCriticalSectionAndSpinCount(&g_csGlobal, 0xFA0u) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
    }
    v12 = GetLastError();
    v9 = v12;
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_72;
  }
  v9 = CBlbVhdHelper::Initialize();
  if ( v9 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    {
LABEL_49:
      CBlbServiceModule::FailServiceStart(v3, v9);
      PublishServiceEvent(3, 0, 0);
      goto LABEL_50;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_45:
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 2u )
        WPP_SF_d(v10[2], 51, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
      goto LABEL_49;
    }
    v13 = 47;
    goto LABEL_43;
  }
  v9 = CBlbEngine::Initialize((CBlbEngine *)&g_blbEngine);
  if ( v9 < 0 )
    goto LABEL_44;
  g_hIdleEngineTimer = CreateWaitableTimerW(0, 1, 0);
  if ( !g_hIdleEngineTimer )
  {
    v15 = GetLastError();
    v9 = v15;
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
LABEL_72:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_73;
    }
    goto LABEL_73;
  }
  Thread = CreateThread(0, 0, CBlbServiceModule::ServiceIdleCheckThreadProc, 0, 0, 0);
  if ( Thread )
  {
    v9 = BlbSetIdleShutdownTimer(0);
    if ( v9 >= 0 )
    {
      CBlbServiceModule::_ServiceMain(v3, v17, v18);
      goto LABEL_51;
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_49;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_45;
    v13 = 50;
LABEL_43:
    WPP_SF_d(v10[2], v13, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
LABEL_44:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_45;
  }
  v16 = GetLastError();
  v9 = v16;
  if ( v16 > 0 )
    v9 = (unsigned __int16)v16 | 0x80070000;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 49;
    goto LABEL_71;
  }
LABEL_73:
  if ( v9 < 0 )
    goto LABEL_45;
LABEL_50:
  if ( Thread )
LABEL_51:
    CloseHandle(Thread);
  if ( g_hIdleEngineTimer )
    CloseHandle(g_hIdleEngineTimer);
  CBlbVhdHelper::Uninitialize();
  DeleteCriticalSection(&g_csGlobal);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    while ( v14 )
    {
      v19 = v14[1];
      if ( v19 )
      {
        UnregisterTraceGuids(v19);
        v14[1] = 0;
      }
      v14 = (_QWORD *)*v14;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
}

```

## disassembly

```asm
0x140066458  mov     rax, rsp
0x14006645b  mov     [rax+8], rbx
0x14006645f  mov     [rax+18h], rbp
0x140066463  mov     [rax+10h], edx
0x140066466  push    rdi
0x140066467  push    r13
0x140066469  push    r14
0x14006646b  sub     rsp, 30h
0x14006646f  mov     r14, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140066476  mov     dword ptr [rax+10h], 0
0x14006647d  lea     rax, WPP_ThisDir_CTLGUID_BLB
0x140066484  mov     cs:qword_14015F5C0, 0
0x14006648f  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x140066496  lea     rax, WPP_MAIN_CB
0x14006649d  mov     cs:WPP_GLOBAL_Control, rax
0x1400664a4  mov     cs:WPP_MAIN_CB, 0
0x1400664af  mov     cs:qword_14015F5C8, 1
0x1400664ba  call    WppInitUm
0x1400664bf  call    ?BlbStartTracing@@YAJXZ; BlbStartTracing(void)
0x1400664c4  test    eax, eax
0x1400664c6  lea     r13, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids
0x1400664cd  mov     ebx, 4
0x1400664d2  setz    cl
0x1400664d5  mov     [r14+29Ch], cl
0x1400664dc  test    eax, eax
0x1400664de  js      short loc_14006653A
0x1400664e0  jnz     short loc_140066515
0x1400664e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400664e9  lea     rdi, WPP_GLOBAL_Control
0x1400664f0  cmp     rcx, rdi
0x1400664f3  jz      loc_140066595
0x1400664f9  test    byte ptr [rcx+1Ch], 8
0x1400664fd  jz      short loc_140066574
0x1400664ff  cmp     [rcx+19h], bl
0x140066502  jb      short loc_140066574
0x140066504  lea     edx, [rbx+25h]
0x140066507  mov     rcx, [rcx+10h]
0x14006650b  mov     r8, r13
0x14006650e  call    WPP_SF_
0x140066513  jmp     short loc_14006656D
0x140066515  mov     rcx, cs:WPP_GLOBAL_Control
0x14006651c  lea     rdi, WPP_GLOBAL_Control
0x140066523  cmp     rcx, rdi
0x140066526  jz      short loc_140066595
0x140066528  test    byte ptr [rcx+1Ch], 8
0x14006652c  jz      short loc_140066574
0x14006652e  cmp     [rcx+19h], bl
0x140066531  jb      short loc_140066574
0x140066533  mov     edx, 2Ah ; '*'
0x140066538  jmp     short loc_140066507
0x14006653a  mov     rcx, cs:WPP_GLOBAL_Control
0x140066541  lea     rdi, WPP_GLOBAL_Control
0x140066548  cmp     rcx, rdi
0x14006654b  jz      short loc_140066595
0x14006654d  test    byte ptr [rcx+1Ch], 8
0x140066551  jz      short loc_140066574
0x140066553  cmp     byte ptr [rcx+19h], 3
0x140066557  jb      short loc_140066574
0x140066559  mov     rcx, [rcx+10h]
0x14006655d  mov     edx, 2Bh ; '+'
0x140066562  mov     r9d, eax
0x140066565  mov     r8, r13
0x140066568  call    WPP_SF_d
0x14006656d  mov     rcx, cs:WPP_GLOBAL_Control
0x140066574  cmp     rcx, rdi
0x140066577  jz      short loc_140066595
0x140066579  test    byte ptr [rcx+1Ch], 1
0x14006657d  jz      short loc_140066595
0x14006657f  cmp     [rcx+19h], bl
0x140066582  jb      short loc_140066595
0x140066584  mov     rcx, [rcx+10h]
0x140066588  mov     edx, 2Ch ; ','
0x14006658d  mov     r8, r13
0x140066590  call    WPP_SF_
0x140066595  lea     rcx, [r14+68h]; lpServiceName
0x140066599  lea     rdx, ?_Handler@?$CAtlServiceModuleT@VCBlbServiceModule@@$0GG@@ATL@@KAXK@Z; lpHandlerProc
0x1400665a0  call    cs:__imp_RegisterServiceCtrlHandlerW
0x1400665a6  mov     [r14+268h], rax
0x1400665ad  test    rax, rax
0x1400665b0  jnz     short loc_1400665D3
0x1400665b2  call    cs:__imp_GetLastError
0x1400665b8  lea     r8, [rsp+48h+arg_8]
0x1400665bd  mov     rdx, rbx
0x1400665c0  mov     ecx, 2
0x1400665c5  mov     [rsp+48h+arg_8], eax
0x1400665c9  call    ?PublishServiceEvent@@YAJW4_BLB_SERVICE_EVENTS@@_KPEBX@Z; PublishServiceEvent(_BLB_SERVICE_EVENTS,unsigned __int64,void const *)
0x1400665ce  jmp     loc_1400668DE
0x1400665d3  lea     rdx, [r14+270h]; lpServiceStatus
0x1400665da  mov     dword ptr [r14+274h], 2
0x1400665e5  mov     rcx, rax; hServiceStatus
0x1400665e8  xor     ebp, ebp
0x1400665ea  call    cs:__imp_SetServiceStatus
0x1400665f0  xor     r9d, r9d; HeapInformationLength
0x1400665f3  lea     edx, [rbp+1]; HeapInformationClass
0x1400665f6  xor     r8d, r8d; HeapInformation
0x1400665f9  xor     ecx, ecx; HeapHandle
0x1400665fb  call    cs:__imp_HeapSetInformation
0x140066601  test    eax, eax
0x140066603  jnz     short loc_140066656
0x140066605  call    cs:__imp_GetLastError
0x14006660b  test    eax, eax
0x14006660d  jg      short loc_140066619
0x14006660f  call    cs:__imp_GetLastError
0x140066615  mov     ebx, eax
0x140066617  jmp     short loc_140066628
0x140066619  call    cs:__imp_GetLastError
0x14006661f  movzx   ebx, ax
0x140066622  or      ebx, 80070000h
0x140066628  mov     rcx, cs:WPP_GLOBAL_Control
0x14006662f  cmp     rcx, rdi
0x140066632  jz      loc_140066863
0x140066638  test    byte ptr [rcx+1Ch], 1
0x14006663c  jz      loc_140066863
0x140066642  cmp     byte ptr [rcx+19h], 2
0x140066646  jb      loc_140066863
0x14006664c  mov     edx, 2Dh ; '-'
0x140066651  jmp     loc_14006684D
0x140066656  mov     edx, 0FA0h; dwSpinCount
0x14006665b  lea     rcx, ?g_csGlobal@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140066662  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140066668  test    eax, eax
0x14006666a  jnz     short loc_1400666B1
0x14006666c  mov     rcx, cs:WPP_GLOBAL_Control
0x140066673  cmp     rcx, rdi
0x140066676  jz      short loc_140066693
0x140066678  test    byte ptr [rcx+1Ch], 1
0x14006667c  jz      short loc_140066693
0x14006667e  cmp     byte ptr [rcx+19h], 2
0x140066682  jb      short loc_140066693
0x140066684  mov     rcx, [rcx+10h]
0x140066688  lea     edx, [rax+2Eh]
0x14006668b  mov     r8, r13
0x14006668e  call    WPP_SF_
0x140066693  call    cs:__imp_GetLastError
0x140066699  mov     ebx, eax
0x14006669b  test    eax, eax
0x14006669d  jle     loc_14006685C
0x1400666a3  movzx   ebx, ax
0x1400666a6  or      ebx, 80070000h
0x1400666ac  jmp     loc_14006685C
0x1400666b1  call    ?Initialize@CBlbVhdHelper@@SAJXZ; CBlbVhdHelper::Initialize(void)
0x1400666b6  mov     ebx, eax
0x1400666b8  test    eax, eax
0x1400666ba  jns     loc_140066776
0x1400666c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400666c7  cmp     rcx, rdi
0x1400666ca  jz      short loc_140066718
0x1400666cc  test    byte ptr [rcx+1Ch], 1
0x1400666d0  jz      short loc_1400666F3
0x1400666d2  cmp     byte ptr [rcx+19h], 2
0x1400666d6  jb      short loc_1400666F3
0x1400666d8  mov     edx, 2Fh ; '/'
0x1400666dd  mov     rcx, [rcx+10h]
0x1400666e1  mov     r9d, eax
0x1400666e4  mov     r8, r13
0x1400666e7  call    WPP_SF_d
0x1400666ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400666f3  cmp     rcx, rdi
0x1400666f6  jz      short loc_140066718
0x1400666f8  test    byte ptr [rcx+1Ch], 1
0x1400666fc  jz      short loc_140066718
0x1400666fe  cmp     byte ptr [rcx+19h], 2
0x140066702  jb      short loc_140066718
0x140066704  mov     rcx, [rcx+10h]
0x140066708  mov     edx, 33h ; '3'
0x14006670d  mov     r9d, ebx
0x140066710  mov     r8, r13
0x140066713  call    WPP_SF_d
0x140066718  mov     edx, ebx; int
0x14006671a  mov     rcx, r14; this
0x14006671d  call    ?FailServiceStart@CBlbServiceModule@@AEAAXJ@Z; CBlbServiceModule::FailServiceStart(long)
0x140066722  xor     edx, edx
0x140066724  xor     r8d, r8d
0x140066727  lea     ecx, [rdx+3]
0x14006672a  call    ?PublishServiceEvent@@YAJW4_BLB_SERVICE_EVENTS@@_KPEBX@Z; PublishServiceEvent(_BLB_SERVICE_EVENTS,unsigned __int64,void const *)
0x14006672f  test    rbp, rbp
0x140066732  jz      short loc_14006673D
0x140066734  mov     rcx, rbp; hObject
0x140066737  call    cs:__imp_CloseHandle
0x14006673d  mov     rcx, cs:?g_hIdleEngineTimer@@3PEAXEA; hObject
0x140066744  test    rcx, rcx
0x140066747  jz      short loc_14006674F
0x140066749  call    cs:__imp_CloseHandle
0x14006674f  call    ?Uninitialize@CBlbVhdHelper@@SAJXZ; CBlbVhdHelper::Uninitialize(void)
0x140066754  lea     rcx, ?g_csGlobal@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14006675b  call    cs:__imp_DeleteCriticalSection
0x140066761  mov     rbx, cs:WPP_GLOBAL_Control
0x140066768  cmp     rbx, rdi
0x14006676b  jz      loc_1400668DE
0x140066771  jmp     loc_1400668D2
0x140066776  lea     rcx, ?g_blbEngine@@3VCBlbEngine@@A; this
0x14006677d  call    ?Initialize@CBlbEngine@@UEAAJXZ; CBlbEngine::Initialize(void)
0x140066782  mov     ebx, eax
0x140066784  test    eax, eax
0x140066786  js      loc_1400666EC
0x14006678c  xor     r8d, r8d; lpTimerName
0x14006678f  xor     ecx, ecx; lpTimerAttributes
0x140066791  lea     edx, [r8+1]; bManualReset
0x140066795  call    cs:__imp_CreateWaitableTimerW
0x14006679b  mov     cs:?g_hIdleEngineTimer@@3PEAXEA, rax; void * g_hIdleEngineTimer
0x1400667a2  test    rax, rax
0x1400667a5  jnz     short loc_1400667F6
0x1400667a7  call    cs:__imp_GetLastError
0x1400667ad  mov     ebx, eax
0x1400667af  test    eax, eax
0x1400667b1  jle     short loc_1400667BC
0x1400667b3  movzx   ebx, ax
0x1400667b6  or      ebx, 80070000h
0x1400667bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400667c3  cmp     rcx, rdi
0x1400667c6  jz      loc_140066863
0x1400667cc  test    byte ptr [rcx+1Ch], 1
0x1400667d0  jz      loc_140066863
0x1400667d6  cmp     byte ptr [rcx+19h], 2
0x1400667da  jb      loc_140066863
0x1400667e0  mov     rcx, [rcx+10h]
0x1400667e4  mov     edx, 30h ; '0'
0x1400667e9  mov     r9d, ebx
0x1400667ec  mov     r8, r13
0x1400667ef  call    WPP_SF_d
0x1400667f4  jmp     short loc_14006685C
0x1400667f6  mov     [rsp+48h+lpThreadId], rbp; lpThreadId
0x1400667fb  lea     r8, ?ServiceIdleCheckThreadProc@CBlbServiceModule@@SAKPEAX@Z; lpStartAddress
0x140066802  xor     r9d, r9d; lpParameter
0x140066805  mov     [rsp+48h+dwCreationFlags], ebp; dwCreationFlags
0x140066809  xor     edx, edx; dwStackSize
0x14006680b  xor     ecx, ecx; lpThreadAttributes
0x14006680d  call    cs:__imp_CreateThread
0x140066813  mov     rbp, rax
0x140066816  test    rax, rax
0x140066819  jnz     short loc_140066870
0x14006681b  call    cs:__imp_GetLastError
0x140066821  mov     ebx, eax
0x140066823  test    eax, eax
0x140066825  jle     short loc_140066830
0x140066827  movzx   ebx, ax
0x14006682a  or      ebx, 80070000h
0x140066830  mov     rcx, cs:WPP_GLOBAL_Control
0x140066837  cmp     rcx, rdi
0x14006683a  jz      short loc_140066863
0x14006683c  test    byte ptr [rcx+1Ch], 1
0x140066840  jz      short loc_140066863
0x140066842  cmp     byte ptr [rcx+19h], 2
0x140066846  jb      short loc_140066863
0x140066848  mov     edx, 31h ; '1'
0x14006684d  mov     rcx, [rcx+10h]
0x140066851  mov     r9d, ebx
0x140066854  mov     r8, r13
0x140066857  call    WPP_SF_d
0x14006685c  mov     rcx, cs:WPP_GLOBAL_Control
0x140066863  test    ebx, ebx
0x140066865  jns     loc_14006672F
0x14006686b  jmp     loc_1400666F3
0x140066870  xor     ecx, ecx; unsigned __int8
0x140066872  call    ?BlbSetIdleShutdownTimer@@YAJE@Z; BlbSetIdleShutdownTimer(uchar)
0x140066877  mov     ebx, eax
0x140066879  test    eax, eax
0x14006687b  jns     short loc_1400668AB
0x14006687d  mov     rcx, cs:WPP_GLOBAL_Control
0x140066884  cmp     rcx, rdi
0x140066887  jz      loc_140066718
0x14006688d  test    byte ptr [rcx+1Ch], 1
0x140066891  jz      loc_1400666F3
0x140066897  cmp     byte ptr [rcx+19h], 2
0x14006689b  jb      loc_1400666F3
0x1400668a1  mov     edx, 32h ; '2'
0x1400668a6  jmp     loc_1400666DD
0x1400668ab  mov     rcx, r14; this
0x1400668ae  call    ?_ServiceMain@CBlbServiceModule@@AEAAXKPEAPEAG@Z; CBlbServiceModule::_ServiceMain(ulong,ushort * *)
0x1400668b3  jmp     loc_140066734
0x1400668b8  mov     rcx, [rbx+8]; RegistrationHandle
0x1400668bc  test    rcx, rcx
0x1400668bf  jz      short loc_1400668CF
0x1400668c1  call    cs:__imp_UnregisterTraceGuids
0x1400668c7  mov     qword ptr [rbx+8], 0
0x1400668cf  mov     rbx, [rbx]
0x1400668d2  test    rbx, rbx
0x1400668d5  jnz     short loc_1400668B8
0x1400668d7  mov     cs:WPP_GLOBAL_Control, rdi
0x1400668de  mov     rbx, [rsp+48h+arg_0]
0x1400668e3  mov     rbp, [rsp+48h+arg_10]
0x1400668e8  add     rsp, 30h
0x1400668ec  pop     r14
0x1400668ee  pop     r13
0x1400668f0  pop     rdi
0x1400668f1  retn
```

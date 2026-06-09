# CWerCplSupportService::Start(void)

- ea: `0x18000773c`
- end: `0x180007af5`
- name: `?Start@CWerCplSupportService@@QEAAJXZ`
- size: `953`
- prototype: `__int64 __fastcall(CWerCplSupportService *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006ec0`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x1800076c8`
- `0x18000773c`
- `0x180007b9c`
- `0x180007c9c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800078c8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800078c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000791b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000791b`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180007a21`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180007a21`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007ad4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007ad4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007791`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007791`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a98`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007823`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007852`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000783f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000783f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800077a8`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800077a8`

## pseudocode

```c
__int64 __fastcall CWerCplSupportService::Start(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // r14d
  SERVICE_STATUS_HANDLE v3; // rax
  unsigned int v4; // r8d
  signed int v5; // eax
  signed int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  HANDLE EventW; // rax
  char *OwningThread; // rcx
  HANDLE v12; // r8
  signed int LastError; // eax
  HRESULT v14; // eax
  _DWORD *v15; // rax
  ULONG_PTR SpinCount; // rbp
  HRESULT v17; // eax
  unsigned int v18; // r8d
  DWORD v19; // eax
  DWORD dwRegister; // [rsp+70h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e2c3f9fb2f8c3c7f26251029e3f227c5_Traceguids);
  v2 = 0;
  ppv = 0;
  EnterCriticalSection(this);
  v3 = RegisterServiceCtrlHandlerExW(L"wercplsupport", CWerCplSupportService::StaticHandler, this);
  *(_QWORD *)&this[1].LockCount = v3;
  if ( v3 )
  {
    CWerCplSupportService::_SetServiceStatus((CWerCplSupportService *)this, 2u, v4);
    EventW = CreateEventW(0, 0, 0, 0);
    OwningThread = (char *)this[1].OwningThread;
    this[1].OwningThread = EventW;
    if ( OwningThread != (char *)-1LL && OwningThread + 1 != (char *)1 )
      CloseHandle(OwningThread);
    v12 = this[1].OwningThread;
    if ( (unsigned __int64)v12 + 1 > 1 )
    {
      (*(void (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), struct _RTL_CRITICAL_SECTION *, int))&this[2].DebugInfo[4].Type)(
        &this[1].LockSemaphore,
        L"wercplsupport",
        v12,
        CWerCplSupportService::StaticStopCallback,
        this,
        8);
      v14 = CoInitializeEx(0, 0);
      v6 = v14;
      if ( v14 >= 0 )
      {
        v2 = 1;
        v14 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
        v6 = v14;
        if ( v14 >= 0 )
        {
          v14 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
          v6 = v14;
          if ( v14 >= 0 )
          {
            CAutoImpersonate::g_bEnableImpersonate = 1;
            v15 = operator new(0x18u);
            if ( v15 )
            {
              v15[2] = 0;
              *(_QWORD *)v15 = &CErcLuaSupportClassFactory::`vftable';
              *((_QWORD *)v15 + 2) = this;
            }
            this[1].SpinCount = (ULONG_PTR)v15;
            if ( v15 )
            {
              CObjectManager::ms_instance = 1;
              dword_18001C954 = 1;
              SpinCount = this[1].SpinCount;
              dwRegister = 0;
              v17 = CoRegisterClassObject(&CLSID_ErcLuaSupport, (LPUNKNOWN)SpinCount, 4u, 1u, &dwRegister);
              v6 = v17;
              if ( v17 >= 0 )
              {
                v19 = dwRegister;
              }
              else
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    14,
                    WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids,
                    (unsigned int)v17);
                }
                v19 = 0;
                dwRegister = 0;
              }
              _InterlockedExchange((volatile __int32 *)(SpinCount + 8), v19);
              if ( v6 >= 0 )
              {
                CWerCplSupportService::_SetServiceStatus((CWerCplSupportService *)this, 4u, v18);
                v6 = 0;
              }
              else
              {
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v8 = 19;
                  goto LABEL_12;
                }
              }
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_e2c3f9fb2f8c3c7f26251029e3f227c5_Traceguids);
            }
            goto LABEL_54;
          }
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_54;
          v8 = 17;
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_54;
          v8 = 16;
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_54;
        v8 = 15;
      }
      v9 = (unsigned int)v14;
      goto LABEL_13;
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 14;
      goto LABEL_12;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 13;
LABEL_12:
      v9 = (unsigned int)v6;
LABEL_13:
      WPP_SF_d(v7[2], v8, WPP_e2c3f9fb2f8c3c7f26251029e3f227c5_Traceguids, v9);
    }
  }
LABEL_54:
  LeaveCriticalSection(this);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v6 < 0 && *(_QWORD *)&this[1].LockCount )
  {
    CWerCplSupportService::Stop((CWerCplSupportService *)this);
    CWerCplSupportService::FinalStop((CWerCplSupportService *)this);
  }
  if ( v2 )
    CoUninitialize();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000773c  mov     [rsp+arg_10], rbx
0x180007741  mov     [rsp+arg_18], rbp
0x180007746  push    rsi
0x180007747  push    rdi
0x180007748  push    r12
0x18000774a  push    r13
0x18000774c  push    r14
0x18000774e  sub     rsp, 40h
0x180007752  mov     rsi, rcx
0x180007755  mov     rcx, cs:WPP_GLOBAL_Control
0x18000775c  lea     r12, WPP_GLOBAL_Control
0x180007763  lea     r13, WPP_e2c3f9fb2f8c3c7f26251029e3f227c5_Traceguids
0x18000776a  cmp     rcx, r12
0x18000776d  jz      short loc_180007786
0x18000776f  test    byte ptr [rcx+1Ch], 4
0x180007773  jz      short loc_180007786
0x180007775  mov     rcx, [rcx+10h]
0x180007779  mov     edx, 0Ch
0x18000777e  mov     r8, r13
0x180007781  call    WPP_SF_
0x180007786  xor     r14d, r14d
0x180007789  mov     rcx, rsi; lpCriticalSection
0x18000778c  mov     [rsp+68h+arg_8], r14
0x180007791  call    cs:__imp_EnterCriticalSection
0x180007797  mov     r8, rsi; lpContext
0x18000779a  lea     rdx, ?StaticHandler@CWerCplSupportService@@CAKKKPEAX0@Z; lpHandlerProc
0x1800077a1  lea     rcx, ServiceName; "wercplsupport"
0x1800077a8  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800077ae  mov     [rsi+30h], rax
0x1800077b2  test    rax, rax
0x1800077b5  jnz     short loc_18000780C
0x1800077b7  call    cs:__imp_GetLastError
0x1800077bd  mov     ebx, eax
0x1800077bf  test    eax, eax
0x1800077c1  jle     short loc_1800077CC
0x1800077c3  movzx   ebx, ax
0x1800077c6  or      ebx, 80070000h
0x1800077cc  test    ebx, ebx
0x1800077ce  mov     eax, 80004005h
0x1800077d3  cmovns  ebx, eax
0x1800077d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077dd  cmp     rcx, r12
0x1800077e0  jz      loc_180007A95
0x1800077e6  mov     edi, 1
0x1800077eb  test    [rcx+1Ch], dil
0x1800077ef  jz      loc_180007A95
0x1800077f5  lea     edx, [rdi+0Ch]
0x1800077f8  mov     r9d, ebx
0x1800077fb  mov     rcx, [rcx+10h]
0x1800077ff  mov     r8, r13
0x180007802  call    WPP_SF_d
0x180007807  jmp     loc_180007A95
0x18000780c  mov     edx, 2; unsigned int
0x180007811  mov     rcx, rsi; this
0x180007814  call    ?_SetServiceStatus@CWerCplSupportService@@AEAAXKK@Z; CWerCplSupportService::_SetServiceStatus(ulong,ulong)
0x180007819  xor     r9d, r9d; lpName
0x18000781c  xor     r8d, r8d; bInitialState
0x18000781f  xor     edx, edx; bManualReset
0x180007821  xor     ecx, ecx; lpEventAttributes
0x180007823  call    cs:__imp_CreateEventW
0x180007829  mov     rcx, [rsi+38h]; hObject
0x18000782d  mov     edi, 1
0x180007832  mov     [rsi+38h], rax
0x180007836  lea     rax, [rcx+1]
0x18000783a  cmp     rax, rdi
0x18000783d  jbe     short loc_180007845
0x18000783f  call    cs:__imp_CloseHandle
0x180007845  mov     r8, [rsi+38h]
0x180007849  lea     rax, [r8+1]
0x18000784d  cmp     rax, rdi
0x180007850  ja      short loc_180007895
0x180007852  call    cs:__imp_GetLastError
0x180007858  mov     ebx, eax
0x18000785a  test    eax, eax
0x18000785c  jle     short loc_180007867
0x18000785e  movzx   ebx, ax
0x180007861  or      ebx, 80070000h
0x180007867  test    ebx, ebx
0x180007869  mov     eax, 80004005h
0x18000786e  cmovns  ebx, eax
0x180007871  mov     rcx, cs:WPP_GLOBAL_Control
0x180007878  cmp     rcx, r12
0x18000787b  jz      loc_180007A95
0x180007881  test    [rcx+1Ch], dil
0x180007885  jz      loc_180007A95
0x18000788b  mov     edx, 0Eh
0x180007890  jmp     loc_1800077F8
0x180007895  mov     rax, [rsi+50h]
0x180007899  lea     rcx, [rsi+40h]
0x18000789d  mov     [rsp+68h+var_40], 8
0x1800078a5  lea     r9, ?StaticStopCallback@CWerCplSupportService@@CAXPEAXE@Z; CWerCplSupportService::StaticStopCallback(void *,uchar)
0x1800078ac  lea     rdx, ServiceName; "wercplsupport"
0x1800078b3  mov     [rsp+68h+ppv], rsi
0x1800078b8  mov     rax, [rax+0C0h]
0x1800078bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c4  xor     edx, edx; dwCoInit
0x1800078c6  xor     ecx, ecx; pvReserved
0x1800078c8  call    cs:__imp_CoInitializeEx
0x1800078ce  mov     ebx, eax
0x1800078d0  test    eax, eax
0x1800078d2  jns     short loc_1800078FB
0x1800078d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078db  cmp     rcx, r12
0x1800078de  jz      loc_180007A95
0x1800078e4  test    [rcx+1Ch], dil
0x1800078e8  jz      loc_180007A95
0x1800078ee  mov     edx, 0Fh
0x1800078f3  mov     r9d, eax
0x1800078f6  jmp     loc_1800077FB
0x1800078fb  lea     rax, [rsp+68h+arg_8]
0x180007900  mov     r8d, edi; dwClsContext
0x180007903  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18000790a  mov     [rsp+68h+ppv], rax; ppv
0x18000790f  xor     edx, edx; pUnkOuter
0x180007911  lea     rcx, CLSID_GlobalOptions; rclsid
0x180007918  mov     r14d, edi
0x18000791b  call    cs:__imp_CoCreateInstance
0x180007921  mov     ebx, eax
0x180007923  test    eax, eax
0x180007925  jns     short loc_180007948
0x180007927  mov     rcx, cs:WPP_GLOBAL_Control
0x18000792e  cmp     rcx, r12
0x180007931  jz      loc_180007A95
0x180007937  test    [rcx+1Ch], dil
0x18000793b  jz      loc_180007A95
0x180007941  mov     edx, 10h
0x180007946  jmp     short loc_1800078F3
0x180007948  mov     rcx, [rsp+68h+arg_8]
0x18000794d  mov     r8, rdi
0x180007950  mov     edx, 5
0x180007955  mov     rax, [rcx]
0x180007958  mov     rax, [rax+18h]
0x18000795c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007961  mov     ebx, eax
0x180007963  test    eax, eax
0x180007965  jns     short loc_18000798B
0x180007967  mov     rcx, cs:WPP_GLOBAL_Control
0x18000796e  cmp     rcx, r12
0x180007971  jz      loc_180007A95
0x180007977  test    [rcx+1Ch], dil
0x18000797b  jz      loc_180007A95
0x180007981  mov     edx, 11h
0x180007986  jmp     loc_1800078F3
0x18000798b  mov     ecx, 18h; Size
0x180007990  mov     cs:?g_bEnableImpersonate@CAutoImpersonate@@1HA, edi; int CAutoImpersonate::g_bEnableImpersonate
0x180007996  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000799b  test    rax, rax
0x18000799e  jz      short loc_1800079B5
0x1800079a0  lea     rcx, ??_7CErcLuaSupportClassFactory@@6B@; const CErcLuaSupportClassFactory::`vftable'
0x1800079a7  mov     dword ptr [rax+8], 0
0x1800079ae  mov     [rax], rcx
0x1800079b1  mov     [rax+10h], rsi
0x1800079b5  mov     [rsi+48h], rax
0x1800079b9  test    rax, rax
0x1800079bc  jnz     short loc_1800079EC
0x1800079be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079c5  cmp     rcx, r12
0x1800079c8  jz      loc_180007A95
0x1800079ce  test    [rcx+1Ch], dil
0x1800079d2  jz      loc_180007A95
0x1800079d8  mov     rcx, [rcx+10h]
0x1800079dc  lea     edx, [rax+12h]
0x1800079df  mov     r8, r13
0x1800079e2  call    WPP_SF_
0x1800079e7  jmp     loc_180007A95
0x1800079ec  mov     cs:?ms_instance@CObjectManager@@1V1@A, edi; CObjectManager CObjectManager::ms_instance
0x1800079f2  lea     rax, [rsp+68h+dwRegister]
0x1800079f7  mov     cs:dword_18001C954, edi
0x1800079fd  lea     rcx, CLSID_ErcLuaSupport; rclsid
0x180007a04  mov     rbp, [rsi+48h]
0x180007a08  mov     r9d, edi; flags
0x180007a0b  mov     rdx, rbp; pUnk
0x180007a0e  mov     [rsp+68h+dwRegister], 0
0x180007a16  mov     r8d, 4; dwClsContext
0x180007a1c  mov     [rsp+68h+ppv], rax; lpdwRegister
0x180007a21  call    cs:__imp_CoRegisterClassObject
0x180007a27  mov     ebx, eax
0x180007a29  test    eax, eax
0x180007a2b  jns     short loc_180007A5F
0x180007a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a34  cmp     rcx, r12
0x180007a37  jz      short loc_180007A57
0x180007a39  test    [rcx+1Ch], dil
0x180007a3d  jz      short loc_180007A57
0x180007a3f  mov     rcx, [rcx+10h]
0x180007a43  lea     r8, WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids
0x180007a4a  mov     edx, 0Eh
0x180007a4f  mov     r9d, eax
0x180007a52  call    WPP_SF_d
0x180007a57  xor     eax, eax
0x180007a59  mov     [rsp+68h+dwRegister], eax
0x180007a5d  jmp     short loc_180007A63
0x180007a5f  mov     eax, [rsp+68h+dwRegister]
0x180007a63  xchg    eax, [rbp+8]
0x180007a66  test    ebx, ebx
0x180007a68  jns     short loc_180007A86
0x180007a6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a71  cmp     rcx, r12
0x180007a74  jz      short loc_180007A95
0x180007a76  test    [rcx+1Ch], dil
0x180007a7a  jz      short loc_180007A95
0x180007a7c  mov     edx, 13h
0x180007a81  jmp     loc_1800077F8
0x180007a86  mov     edx, 4; unsigned int
0x180007a8b  mov     rcx, rsi; this
0x180007a8e  call    ?_SetServiceStatus@CWerCplSupportService@@AEAAXKK@Z; CWerCplSupportService::_SetServiceStatus(ulong,ulong)
0x180007a93  xor     ebx, ebx
0x180007a95  mov     rcx, rsi; lpCriticalSection
0x180007a98  call    cs:__imp_LeaveCriticalSection
0x180007a9e  mov     rcx, [rsp+68h+arg_8]
0x180007aa3  test    rcx, rcx
0x180007aa6  jz      short loc_180007AB4
0x180007aa8  mov     rax, [rcx]
0x180007aab  mov     rax, [rax+10h]
0x180007aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ab4  test    ebx, ebx
0x180007ab6  jns     short loc_180007ACF
0x180007ab8  cmp     qword ptr [rsi+30h], 0
0x180007abd  jz      short loc_180007ACF
0x180007abf  mov     rcx, rsi; this
0x180007ac2  call    ?Stop@CWerCplSupportService@@AEAAXXZ; CWerCplSupportService::Stop(void)
0x180007ac7  mov     rcx, rsi; this
0x180007aca  call    ?FinalStop@CWerCplSupportService@@QEAAXXZ; CWerCplSupportService::FinalStop(void)
0x180007acf  test    r14d, r14d
0x180007ad2  jz      short loc_180007ADA
0x180007ad4  call    cs:__imp_CoUninitialize
0x180007ada  lea     r11, [rsp+68h+var_28]
0x180007adf  mov     eax, ebx
0x180007ae1  mov     rbx, [r11+40h]
0x180007ae5  mov     rbp, [r11+48h]
0x180007ae9  mov     rsp, r11
0x180007aec  pop     r14
0x180007aee  pop     r13
0x180007af0  pop     r12
0x180007af2  pop     rdi
0x180007af3  pop     rsi
0x180007af4  retn
```

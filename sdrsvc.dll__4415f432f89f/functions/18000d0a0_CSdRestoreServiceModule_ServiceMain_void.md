# CSdRestoreServiceModule::ServiceMain(void)

- ea: `0x18000d0a0`
- end: `0x18000d2b4`
- name: `?ServiceMain@CSdRestoreServiceModule@@QEAAJXZ`
- size: `532`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ea00`

## callees

- `0x18000ac34`
- `0x18000cfb8`
- `0x18000d0a0`
- `0x18000d530`
- `0x18000e420`
- `0x18000ea7c`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000d0ea`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000d0ea`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18000d1c6`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18000d200`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18000d1c6`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18000d200`

## string_xrefs

- `0x18000d0b8`: `CSdRestoreServiceModule::ServiceMain`
- `0x18000d192`: `CSdRestoreServiceModule::Stop`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::ServiceMain(CSdRestoreServiceModule *this)
{
  CSdRestoreServiceModule *v1; // rcx
  CSdRestoreServiceModule *v2; // rcx
  __int16 v3; // ax
  CSdRestoreServiceModule *v4; // rcx
  __int64 v5; // rbx
  HRESULT v6; // eax
  __int64 *v7; // rbx
  __int64 v8; // rdx
  CSdRestoreServiceModule *v9; // rcx
  unsigned int v10; // ebx
  signed int LastFailureAsHRESULT; // [rsp+20h] [rbp-19h] BYREF
  __int16 v13; // [rsp+24h] [rbp-15h]
  __int16 v14; // [rsp+26h] [rbp-13h]
  int v15; // [rsp+58h] [rbp+1Fh] BYREF
  __int16 v16; // [rsp+5Ch] [rbp+23h]
  __int16 v17; // [rsp+5Eh] [rbp+25h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdRestoreServiceModule::ServiceMain",
    317,
    1);
  ServiceStatus.dwCurrentState = 2;
  g_Service = RegisterServiceCtrlHandlerExW(L"SDRSVC", HandlerEx, 0);
  if ( !g_Service )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v1);
    v3 = 324;
LABEL_8:
    v14 = v3;
    goto LABEL_9;
  }
  LastFailureAsHRESULT = 0;
  v13 = 324;
  LastFailureAsHRESULT = CSdRestoreServiceModule::_SetServiceStatus(v1, 2u);
  v3 = 327;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v13 = 327;
  LastFailureAsHRESULT = CSdRestoreServiceModule::Initialize(v2);
  v3 = 330;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v13 = 330;
  ServiceStatus.dwControlsAccepted = 69;
  LastFailureAsHRESULT = CSdRestoreServiceModule::_SetServiceStatus(v2, 4u);
  v3 = 339;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v13 = 339;
  LastFailureAsHRESULT = CSdRestoreServiceModule::Run(v2);
  v3 = 342;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v13 = 342;
LABEL_9:
  CSdRestoreServiceModule::_SetServiceStatus(v2, 3u);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "CSdRestoreServiceModule::Stop", 669, 1);
  v5 = qword_18002E1D8;
  if ( qword_18002E1D8 && (v6 = 0, *(_QWORD *)qword_18002E1D8) )
  {
    while ( !v6 )
    {
      v4 = (CSdRestoreServiceModule *)*(unsigned int *)(v5 + 40);
      if ( (_DWORD)v4 )
        v6 = CoRevokeClassObject((DWORD)v4);
      v5 += 72;
      if ( !*(_QWORD *)v5 )
      {
        if ( v6 )
          break;
        goto LABEL_16;
      }
    }
  }
  else
  {
LABEL_16:
    v7 = off_18002D3B0[0];
    v6 = 0;
    v4 = (CSdRestoreServiceModule *)off_18002D3B8;
    while ( v7 < (__int64 *)v4 && !v6 )
    {
      v8 = *v7;
      if ( *v7 && *(_DWORD *)(v8 + 40) )
      {
        v6 = CoRevokeClassObject(*(_DWORD *)(v8 + 40));
        v4 = (CSdRestoreServiceModule *)off_18002D3B8;
      }
      ++v7;
    }
  }
  v15 = v6;
  if ( v6 < 0 )
  {
    v4 = (CSdRestoreServiceModule *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_649b3fb5f13c32b4c81a27164fdda673_Traceguids,
        (unsigned int)v6);
  }
  CSdRestoreServiceModule::UninitializeCOM(v4);
  if ( v15 >= 0 )
    v16 = 681;
  else
    v17 = 681;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15);
  if ( LastFailureAsHRESULT < 0 )
  {
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = LastFailureAsHRESULT;
  }
  CSdRestoreServiceModule::_SetServiceStatus(v9, 1u);
  v10 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v10;
}

```

## disassembly

```asm
0x18000d0a0  mov     [rsp-8+arg_0], rbx
0x18000d0a5  push    rbp
0x18000d0a6  lea     rbp, [rsp-57h]
0x18000d0ab  sub     rsp, 90h
0x18000d0b2  mov     r9d, 1; unsigned __int16
0x18000d0b8  lea     rdx, aCsdrestoreserv_5; "CSdRestoreServiceModule::ServiceMain"
0x18000d0bf  mov     r8d, 13Dh; unsigned __int16
0x18000d0c5  lea     rcx, [rbp+57h+var_70]; this
0x18000d0c9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d0ce  mov     ebx, 2
0x18000d0d3  lea     rdx, HandlerEx; lpHandlerProc
0x18000d0da  xor     r8d, r8d; lpContext
0x18000d0dd  mov     cs:ServiceStatus.dwCurrentState, ebx
0x18000d0e3  lea     rcx, ?s_wszSvcName@CSdRestoreServiceModule@@0QBGB; "SDRSVC"
0x18000d0ea  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000d0f0  mov     cs:?g_Service@@3VCSdRestoreServiceModule@@A, rax; CSdRestoreServiceModule g_Service
0x18000d0f7  test    rax, rax
0x18000d0fa  jz      short loc_18000D171
0x18000d0fc  mov     eax, 144h
0x18000d101  mov     [rbp+57h+var_70], 0
0x18000d108  mov     edx, ebx; unsigned int
0x18000d10a  mov     [rbp+57h+var_6C], ax
0x18000d10e  call    ?_SetServiceStatus@CSdRestoreServiceModule@@AEAAJK@Z; CSdRestoreServiceModule::_SetServiceStatus(ulong)
0x18000d113  mov     [rbp+57h+var_70], eax
0x18000d116  test    eax, eax
0x18000d118  mov     eax, 147h
0x18000d11d  js      short loc_18000D17E
0x18000d11f  mov     [rbp+57h+var_6C], ax
0x18000d123  call    ?Initialize@CSdRestoreServiceModule@@AEAAJXZ; CSdRestoreServiceModule::Initialize(void)
0x18000d128  mov     [rbp+57h+var_70], eax
0x18000d12b  test    eax, eax
0x18000d12d  mov     eax, 14Ah
0x18000d132  js      short loc_18000D17E
0x18000d134  lea     edx, [rbx+2]; unsigned int
0x18000d137  mov     [rbp+57h+var_6C], ax
0x18000d13b  mov     cs:ServiceStatus.dwControlsAccepted, 45h ; 'E'
0x18000d145  call    ?_SetServiceStatus@CSdRestoreServiceModule@@AEAAJK@Z; CSdRestoreServiceModule::_SetServiceStatus(ulong)
0x18000d14a  mov     [rbp+57h+var_70], eax
0x18000d14d  test    eax, eax
0x18000d14f  mov     eax, 153h
0x18000d154  js      short loc_18000D17E
0x18000d156  mov     [rbp+57h+var_6C], ax
0x18000d15a  call    ?Run@CSdRestoreServiceModule@@AEAAJXZ; CSdRestoreServiceModule::Run(void)
0x18000d15f  mov     [rbp+57h+var_70], eax
0x18000d162  test    eax, eax
0x18000d164  mov     eax, 156h
0x18000d169  js      short loc_18000D17E
0x18000d16b  mov     [rbp+57h+var_6C], ax
0x18000d16f  jmp     short loc_18000D182
0x18000d171  call    GetLastFailureAsHRESULT
0x18000d176  mov     [rbp+57h+var_70], eax
0x18000d179  mov     eax, 144h
0x18000d17e  mov     [rbp+57h+var_6A], ax
0x18000d182  mov     edx, 3; unsigned int
0x18000d187  call    ?_SetServiceStatus@CSdRestoreServiceModule@@AEAAJK@Z; CSdRestoreServiceModule::_SetServiceStatus(ulong)
0x18000d18c  mov     r9d, 1; unsigned __int16
0x18000d192  lea     rdx, aCsdrestoreserv; "CSdRestoreServiceModule::Stop"
0x18000d199  mov     r8d, 29Dh; unsigned __int16
0x18000d19f  lea     rcx, [rbp+57h+var_38]; this
0x18000d1a3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d1a8  mov     rbx, cs:qword_18002E1D8
0x18000d1af  test    rbx, rbx
0x18000d1b2  jz      short loc_18000D1DA
0x18000d1b4  xor     eax, eax
0x18000d1b6  cmp     [rbx], rax
0x18000d1b9  jz      short loc_18000D1DA
0x18000d1bb  test    eax, eax
0x18000d1bd  jnz     short loc_18000D216
0x18000d1bf  mov     ecx, [rbx+28h]; dwRegister
0x18000d1c2  test    ecx, ecx
0x18000d1c4  jz      short loc_18000D1CC
0x18000d1c6  call    cs:__imp_CoRevokeClassObject
0x18000d1cc  add     rbx, 48h ; 'H'
0x18000d1d0  cmp     qword ptr [rbx], 0
0x18000d1d4  jnz     short loc_18000D1BB
0x18000d1d6  test    eax, eax
0x18000d1d8  jnz     short loc_18000D216
0x18000d1da  mov     rbx, cs:off_18002D3B0
0x18000d1e1  xor     eax, eax
0x18000d1e3  mov     rcx, cs:off_18002D3B8
0x18000d1ea  jmp     short loc_18000D211
0x18000d1ec  test    eax, eax
0x18000d1ee  jnz     short loc_18000D216
0x18000d1f0  mov     rdx, [rbx]
0x18000d1f3  test    rdx, rdx
0x18000d1f6  jz      short loc_18000D20D
0x18000d1f8  cmp     [rdx+28h], eax
0x18000d1fb  jz      short loc_18000D20D
0x18000d1fd  mov     ecx, [rdx+28h]; dwRegister
0x18000d200  call    cs:__imp_CoRevokeClassObject
0x18000d206  mov     rcx, cs:off_18002D3B8
0x18000d20d  add     rbx, 8
0x18000d211  cmp     rbx, rcx
0x18000d214  jb      short loc_18000D1EC
0x18000d216  mov     [rbp+57h+var_38], eax
0x18000d219  test    eax, eax
0x18000d21b  jns     short loc_18000D251
0x18000d21d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d224  lea     rdx, WPP_GLOBAL_Control
0x18000d22b  cmp     rcx, rdx
0x18000d22e  jz      short loc_18000D251
0x18000d230  test    dword ptr [rcx+1Ch], 2000000h
0x18000d237  jz      short loc_18000D251
0x18000d239  mov     rcx, [rcx+10h]
0x18000d23d  lea     r8, WPP_649b3fb5f13c32b4c81a27164fdda673_Traceguids
0x18000d244  mov     edx, 0Ch
0x18000d249  mov     r9d, eax
0x18000d24c  call    WPP_SF_d
0x18000d251  call    ?UninitializeCOM@CSdRestoreServiceModule@@QEAAJXZ; CSdRestoreServiceModule::UninitializeCOM(void)
0x18000d256  cmp     [rbp+57h+var_38], 0
0x18000d25a  mov     eax, 2A9h
0x18000d25f  jge     short loc_18000D267
0x18000d261  mov     [rbp+57h+var_32], ax
0x18000d265  jmp     short loc_18000D26B
0x18000d267  mov     [rbp+57h+var_34], ax
0x18000d26b  lea     rcx, [rbp+57h+var_38]; this
0x18000d26f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d274  mov     eax, [rbp+57h+var_70]
0x18000d277  test    eax, eax
0x18000d279  jns     short loc_18000D28B
0x18000d27b  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18000d285  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x18000d28b  mov     edx, 1; unsigned int
0x18000d290  call    ?_SetServiceStatus@CSdRestoreServiceModule@@AEAAJK@Z; CSdRestoreServiceModule::_SetServiceStatus(ulong)
0x18000d295  mov     ebx, [rbp+57h+var_70]
0x18000d298  lea     rcx, [rbp+57h+var_70]; this
0x18000d29c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d2a1  mov     eax, ebx
0x18000d2a3  mov     rbx, [rsp+90h+arg_0]
0x18000d2ab  add     rsp, 90h
0x18000d2b2  pop     rbp
0x18000d2b3  retn
```

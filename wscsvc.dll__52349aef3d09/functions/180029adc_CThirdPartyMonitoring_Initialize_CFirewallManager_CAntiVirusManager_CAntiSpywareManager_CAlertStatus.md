# CThirdPartyMonitoring::Initialize(CFirewallManager *,CAntiVirusManager *,CAntiSpywareManager *,CAlertStatus *)

- ea: `0x180029adc`
- end: `0x180029c96`
- name: `?Initialize@CThirdPartyMonitoring@@QEAAJPEAVCFirewallManager@@PEAVCAntiVirusManager@@PEAVCAntiSpywareManager@@PEAVCAlertStatus@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(CThirdPartyMonitoring *this, struct CFirewallManager *, struct CAntiVirusManager *, struct CAntiSpywareManager *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001d9e0`

## callees

- `0x18002331c`
- `0x1800292bc`
- `0x180029adc`
- `0x18002a6b4`
- `0x180038448`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029c0a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029c3c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029c0a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029c3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c4b`

## pseudocode

```c
__int64 __fastcall CThirdPartyMonitoring::Initialize(
        CThirdPartyMonitoring *this,
        struct CFirewallManager *a2,
        struct CAntiVirusManager *a3,
        struct CAntiSpywareManager *a4)
{
  CThirdPartyManager *v4; // r15
  CThirdPartyManager *v5; // rsi
  CThirdPartyManager *v6; // rbp
  LPCRITICAL_SECTION v7; // r14
  LPHANDLE v8; // rdi
  _DWORD *v9; // rax
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  int v13; // eax
  signed int v14; // ebx
  HANDLE v15; // rcx
  CRecheckQueue *v16; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v19; // rax
  signed int v20; // eax

  v4 = WscServiceUtils::g_pFirewallManager;
  if ( !WscServiceUtils::g_pFirewallManager )
    return 2147942487LL;
  v5 = WscServiceUtils::g_pAntiVirusManager;
  if ( !WscServiceUtils::g_pAntiVirusManager )
    return 2147942487LL;
  v6 = WscServiceUtils::g_pAntiSpywareManager;
  if ( !WscServiceUtils::g_pAntiSpywareManager )
    return 2147942487LL;
  v7 = g_pAlertStatus;
  if ( !g_pAlertStatus )
    return 2147942487LL;
  v8 = g_pThirdPartyMonitoring;
  v9 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( v9 )
  {
    *v9 = 0;
    v9[12] = 0;
    v11 = v9 + 14;
    v10[8] = v11;
    v10[9] = v11;
    *v11 = v11;
  }
  else
  {
    v10 = 0;
  }
  v8[135] = v10;
  if ( !v10 )
    return 2147942414LL;
  v13 = CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::Initialize(v10);
  v14 = v13;
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  if ( v14 < 0 )
  {
    v15 = v8[135];
    if ( v15 )
      CList<CDetectoid *,CDetectoid *>::`scalar deleting destructor'(v15);
    v8[135] = 0;
  }
  v16 = (CRecheckQueue *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v16 )
    *(_QWORD *)v16 = 0;
  v8[136] = v16;
  if ( v16 )
  {
    if ( v14 >= 0 )
    {
      v14 = CRecheckQueue::Initialize(v16);
      if ( v14 >= 0 )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        v8[1] = EventW;
        if ( EventW )
          goto LABEL_26;
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        if ( v14 >= 0 )
        {
LABEL_26:
          v19 = CreateEventW(0, 0, 0, 0);
          v8[4] = v19;
          if ( v19 )
            goto LABEL_30;
          v20 = GetLastError();
          v14 = v20;
          if ( v20 > 0 )
            v14 = (unsigned __int16)v20 | 0x80070000;
          if ( v14 >= 0 )
          {
LABEL_30:
            v8[137] = v4;
            v8[138] = v5;
            v8[139] = v6;
            v8[140] = v7;
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180029adc  push    rbx
0x180029ade  push    rbp
0x180029adf  push    rsi
0x180029ae0  push    rdi
0x180029ae1  push    r14
0x180029ae3  push    r15
0x180029ae5  sub     rsp, 28h
0x180029ae9  mov     r15, cs:?g_pFirewallManager@WscServiceUtils@@3PEAVCFirewallManager@@EA; CFirewallManager * WscServiceUtils::g_pFirewallManager
0x180029af0  test    r15, r15
0x180029af3  jz      loc_180029C84
0x180029af9  mov     rsi, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x180029b00  test    rsi, rsi
0x180029b03  jz      loc_180029C84
0x180029b09  mov     rbp, cs:?g_pAntiSpywareManager@WscServiceUtils@@3PEAVCAntiSpywareManager@@EA; CAntiSpywareManager * WscServiceUtils::g_pAntiSpywareManager
0x180029b10  test    rbp, rbp
0x180029b13  jz      loc_180029C84
0x180029b19  mov     r14, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; CAlertStatus * g_pAlertStatus
0x180029b20  test    r14, r14
0x180029b23  jz      loc_180029C84
0x180029b29  mov     rdi, cs:?g_pThirdPartyMonitoring@@3PEAVCThirdPartyMonitoring@@EA; CThirdPartyMonitoring * g_pThirdPartyMonitoring
0x180029b30  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029b37  mov     ecx, 50h ; 'P'; unsigned __int64
0x180029b3c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029b41  mov     rcx, rax
0x180029b44  test    rax, rax
0x180029b47  jz      short loc_180029B67
0x180029b49  mov     dword ptr [rax], 0
0x180029b4f  mov     dword ptr [rax+30h], 0
0x180029b56  add     rax, 38h ; '8'
0x180029b5a  mov     [rcx+40h], rax
0x180029b5e  mov     [rcx+48h], rax
0x180029b62  mov     [rax], rax
0x180029b65  jmp     short loc_180029B69
0x180029b67  xor     ecx, ecx
0x180029b69  mov     [rdi+438h], rcx
0x180029b70  test    rcx, rcx
0x180029b73  jnz     short loc_180029B7F
0x180029b75  mov     eax, 8007000Eh
0x180029b7a  jmp     loc_180029C89
0x180029b7f  call    ?Initialize@?$CList@PEAUSTATUSCHANGENOTIFICATION@@PEAU1@@@QEAAJXZ; CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::Initialize(void)
0x180029b84  mov     ebx, eax
0x180029b86  test    eax, eax
0x180029b88  jle     short loc_180029B93
0x180029b8a  movzx   ebx, ax
0x180029b8d  or      ebx, 80070000h
0x180029b93  test    ebx, ebx
0x180029b95  jns     short loc_180029BB3
0x180029b97  mov     rcx, [rdi+438h]; Block
0x180029b9e  test    rcx, rcx
0x180029ba1  jz      short loc_180029BA8
0x180029ba3  call    ??_G?$CList@PEAVCDetectoid@@PEAV1@@@QEAAPEAXI@Z; CList<CDetectoid *,CDetectoid *>::`scalar deleting destructor'(uint)
0x180029ba8  mov     qword ptr [rdi+438h], 0
0x180029bb3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029bba  mov     ecx, 8; unsigned __int64
0x180029bbf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029bc4  test    rax, rax
0x180029bc7  jz      short loc_180029BD0
0x180029bc9  mov     qword ptr [rax], 0
0x180029bd0  mov     [rdi+440h], rax
0x180029bd7  test    rax, rax
0x180029bda  jnz     short loc_180029BE6
0x180029bdc  mov     ebx, 8007000Eh
0x180029be1  jmp     loc_180029C80
0x180029be6  test    ebx, ebx
0x180029be8  js      loc_180029C80
0x180029bee  mov     rcx, rax; this
0x180029bf1  call    ?Initialize@CRecheckQueue@@QEAAJXZ; CRecheckQueue::Initialize(void)
0x180029bf6  mov     ebx, eax
0x180029bf8  test    eax, eax
0x180029bfa  js      loc_180029C80
0x180029c00  xor     r9d, r9d; lpName
0x180029c03  xor     r8d, r8d; bInitialState
0x180029c06  xor     edx, edx; bManualReset
0x180029c08  xor     ecx, ecx; lpEventAttributes
0x180029c0a  call    cs:__imp_CreateEventW
0x180029c10  mov     [rdi+8], rax
0x180029c14  test    rax, rax
0x180029c17  jnz     short loc_180029C32
0x180029c19  call    cs:__imp_GetLastError
0x180029c1f  mov     ebx, eax
0x180029c21  test    eax, eax
0x180029c23  jle     short loc_180029C2E
0x180029c25  movzx   ebx, ax
0x180029c28  or      ebx, 80070000h
0x180029c2e  test    ebx, ebx
0x180029c30  js      short loc_180029C80
0x180029c32  xor     r9d, r9d; lpName
0x180029c35  xor     r8d, r8d; bInitialState
0x180029c38  xor     edx, edx; bManualReset
0x180029c3a  xor     ecx, ecx; lpEventAttributes
0x180029c3c  call    cs:__imp_CreateEventW
0x180029c42  mov     [rdi+20h], rax
0x180029c46  test    rax, rax
0x180029c49  jnz     short loc_180029C64
0x180029c4b  call    cs:__imp_GetLastError
0x180029c51  mov     ebx, eax
0x180029c53  test    eax, eax
0x180029c55  jle     short loc_180029C60
0x180029c57  movzx   ebx, ax
0x180029c5a  or      ebx, 80070000h
0x180029c60  test    ebx, ebx
0x180029c62  js      short loc_180029C80
0x180029c64  mov     [rdi+448h], r15
0x180029c6b  mov     [rdi+450h], rsi
0x180029c72  mov     [rdi+458h], rbp
0x180029c79  mov     [rdi+460h], r14
0x180029c80  mov     eax, ebx
0x180029c82  jmp     short loc_180029C89
0x180029c84  mov     eax, 80070057h
0x180029c89  add     rsp, 28h
0x180029c8d  pop     r15
0x180029c8f  pop     r14
0x180029c91  pop     rdi
0x180029c92  pop     rsi
0x180029c93  pop     rbp
0x180029c94  pop     rbx
0x180029c95  retn
```

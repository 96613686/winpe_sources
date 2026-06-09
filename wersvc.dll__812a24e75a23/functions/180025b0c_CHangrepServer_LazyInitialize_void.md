# CHangrepServer::_LazyInitialize(void)

- ea: `0x180025b0c`
- end: `0x180025ce1`
- name: `?_LazyInitialize@CHangrepServer@@AEAAJXZ`
- size: `469`
- prototype: `__int64 __fastcall(CHangrepServer *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800248f4`

## callees

- `0x180001008`
- `0x180002a24`
- `0x180003cf8`
- `0x180003d6c`
- `0x180006900`
- `0x180006a80`
- `0x180011ef8`
- `0x180013df4`
- `0x180025a0c`
- `0x180025b0c`
- `0x180029330`
- `0x18002bf44`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180025c95`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180025c95`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180025ca8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180025ca8`

## pseudocode

```c
__int64 __fastcall CHangrepServer::_LazyInitialize(CHangrepServer *this)
{
  char **v2; // rdi
  unsigned __int64 v4; // r14
  __int64 v5; // rax
  bool v6; // cf
  unsigned __int64 v7; // rax
  unsigned __int64 *v8; // rax
  char *v9; // rbx
  char *v10; // rcx
  char *v11; // rbx
  int v12; // ebx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v14; // rcx

  v2 = (char **)((char *)this + 48);
  if ( *((_DWORD *)this + 10) )
  {
    if ( *v2 )
      return 0;
    goto LABEL_5;
  }
  if ( *v2 )
LABEL_5:
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *v2 )
    return 0;
  v4 = ReadDwordCheckBounds((HKEY)this, L"MaxHangrepInstances", 8u, 0, 0x64u);
  v5 = 2456 * v4;
  if ( !is_mul_ok(v4, 0x998u) )
    v5 = -1;
  v6 = __CFADD__(v5, 8);
  v7 = v5 + 8;
  if ( v6 )
    v7 = -1;
  v8 = (unsigned __int64 *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
  {
    *v8 = v4;
    v9 = (char *)(v8 + 1);
    `eh vector constructor iterator'(
      v8 + 1,
      0x998u,
      (unsigned int)v4,
      (void (*)(void *))CHungApp::CHungApp,
      (void (*)(void *))CHungApp::~CHungApp);
  }
  else
  {
    v9 = 0;
  }
  v10 = *v2;
  *v2 = v9;
  if ( v10 )
  {
    v11 = v10 - 8;
    `eh vector destructor iterator'(v10, 2456, *((_QWORD *)v10 - 1), (void (__fastcall *)(char *))CHungApp::~CHungApp);
    operator delete[](v11, (const struct std::nothrow_t *)(2456LL * *(_QWORD *)v11 + 8));
  }
  if ( *v2 )
  {
    *((_DWORD *)this + 10) = v4;
    v12 = CHungApp::StaticInitialize();
    if ( v12 >= 0 )
    {
      ThreadpoolWait = CreateThreadpoolWait(CHangrepServer::StaticActivationQuiesceReportCompletedCallback, this, 0);
      v14 = (struct _TP_WAIT *)*((_QWORD *)this + 7);
      *((_QWORD *)this + 7) = ThreadpoolWait;
      if ( v14 )
        CloseThreadpoolWait(v14);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800470C8);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180047100);
      return 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids,
        (unsigned int)v12);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids);
    v12 = -2147024882;
  }
  CHangrepServer::_Cleanup(this);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180025b0c  mov     [rsp+arg_8], rbx
0x180025b11  mov     [rsp+arg_10], rbp
0x180025b16  push    rsi
0x180025b17  push    rdi
0x180025b18  push    r12
0x180025b1a  push    r13
0x180025b1c  push    r14
0x180025b1e  sub     rsp, 30h
0x180025b22  mov     rsi, rcx
0x180025b25  mov     eax, [rcx+28h]
0x180025b28  lea     rdi, [rcx+30h]
0x180025b2c  test    eax, eax
0x180025b2e  jnz     short loc_180025B38
0x180025b30  cmp     qword ptr [rdi], 0
0x180025b34  jnz     short loc_180025B3E
0x180025b36  jmp     short loc_180025B43
0x180025b38  cmp     qword ptr [rdi], 0
0x180025b3c  jnz     short loc_180025B49
0x180025b3e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025b43  cmp     qword ptr [rdi], 0
0x180025b47  jz      short loc_180025B50
0x180025b49  xor     eax, eax
0x180025b4b  jmp     loc_180025CCA
0x180025b50  mov     dword ptr [rsp+58h+var_38], 64h ; 'd'; unsigned int
0x180025b58  xor     r9d, r9d; unsigned int
0x180025b5b  lea     r8d, [r9+8]; unsigned int
0x180025b5f  lea     rdx, aMaxhangrepinst; "MaxHangrepInstances"
0x180025b66  call    ?ReadDwordCheckBounds@@YAKPEAUHKEY__@@PEB_WKKK@Z; ReadDwordCheckBounds(HKEY__ *,wchar_t const *,ulong,ulong,ulong)
0x180025b6b  mov     r14d, eax
0x180025b6e  mov     r12d, 998h
0x180025b74  mov     eax, r12d
0x180025b77  mul     r14
0x180025b7a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025b81  cmovb   rax, rcx
0x180025b85  add     rax, 8
0x180025b89  cmovb   rax, rcx
0x180025b8d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025b94  mov     rcx, rax; unsigned __int64
0x180025b97  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180025b9c  mov     [rsp+58h+arg_0], rax
0x180025ba1  lea     r13, ??1CHungApp@@QEAA@XZ; CHungApp::~CHungApp(void)
0x180025ba8  test    rax, rax
0x180025bab  jz      short loc_180025BD0
0x180025bad  mov     [rax], r14
0x180025bb0  lea     rbx, [rax+8]
0x180025bb4  mov     [rsp+58h+var_38], r13; void (*)(void *)
0x180025bb9  lea     r9, ??0CHungApp@@QEAA@XZ; void (*)(void *)
0x180025bc0  mov     r8d, r14d; unsigned __int64
0x180025bc3  mov     edx, r12d; unsigned __int64
0x180025bc6  mov     rcx, rbx; void *
0x180025bc9  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180025bce  jmp     short loc_180025BD2
0x180025bd0  xor     ebx, ebx
0x180025bd2  mov     rcx, [rdi]; void *
0x180025bd5  mov     [rdi], rbx
0x180025bd8  test    rcx, rcx
0x180025bdb  jz      short loc_180025C03
0x180025bdd  lea     rbx, [rcx-8]
0x180025be1  mov     r9, r13; void (*)(void *)
0x180025be4  mov     r8, [rbx]; unsigned __int64
0x180025be7  mov     rdx, r12; unsigned __int64
0x180025bea  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180025bef  imul    rdx, [rbx], 998h
0x180025bf6  add     rdx, 8; struct std::nothrow_t *
0x180025bfa  mov     rcx, rbx; void *
0x180025bfd  call    ??_V@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete[](void *,std::nothrow_t const &)
0x180025c02  nop
0x180025c03  cmp     qword ptr [rdi], 0
0x180025c07  jnz     short loc_180025C3E
0x180025c09  lea     rax, WPP_GLOBAL_Control
0x180025c10  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c17  cmp     rcx, rax
0x180025c1a  jz      short loc_180025C37
0x180025c1c  test    byte ptr [rcx+1Ch], 1
0x180025c20  jz      short loc_180025C37
0x180025c22  mov     edx, 0Ah
0x180025c27  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x180025c2e  mov     rcx, [rcx+10h]
0x180025c32  call    WPP_SF_
0x180025c37  mov     ebx, 8007000Eh
0x180025c3c  jmp     short loc_180025C7E
0x180025c3e  mov     [rsi+28h], r14d
0x180025c42  call    ?StaticInitialize@CHungApp@@SAJXZ; CHungApp::StaticInitialize(void)
0x180025c47  mov     ebx, eax
0x180025c49  test    eax, eax
0x180025c4b  jns     short loc_180025C88
0x180025c4d  lea     rax, WPP_GLOBAL_Control
0x180025c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c5b  cmp     rcx, rax
0x180025c5e  jz      short loc_180025C7E
0x180025c60  test    byte ptr [rcx+1Ch], 1
0x180025c64  jz      short loc_180025C7E
0x180025c66  mov     edx, 0Bh
0x180025c6b  mov     r9d, ebx
0x180025c6e  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x180025c75  mov     rcx, [rcx+10h]
0x180025c79  call    WPP_SF_d
0x180025c7e  mov     rcx, rsi; this
0x180025c81  call    ?_Cleanup@CHangrepServer@@AEAAXXZ; CHangrepServer::_Cleanup(void)
0x180025c86  jmp     short loc_180025CC8
0x180025c88  xor     r8d, r8d; pcbe
0x180025c8b  mov     rdx, rsi; pv
0x180025c8e  lea     rcx, ?StaticActivationQuiesceReportCompletedCallback@CHangrepServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180025c95  call    cs:__imp_CreateThreadpoolWait
0x180025c9b  mov     rcx, [rsi+38h]; pwa
0x180025c9f  mov     [rsi+38h], rax
0x180025ca3  test    rcx, rcx
0x180025ca6  jz      short loc_180025CAE
0x180025ca8  call    cs:__imp_CloseThreadpoolWait
0x180025cae  lea     rcx, dword_1800470C8; CallbackContext
0x180025cb5  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180025cba  lea     rcx, dword_180047100; CallbackContext
0x180025cc1  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180025cc6  xor     ebx, ebx
0x180025cc8  mov     eax, ebx
0x180025cca  mov     rbx, [rsp+58h+arg_8]
0x180025ccf  mov     rbp, [rsp+58h+arg_10]
0x180025cd4  add     rsp, 30h
0x180025cd8  pop     r14
0x180025cda  pop     r13
0x180025cdc  pop     r12
0x180025cde  pop     rdi
0x180025cdf  pop     rsi
0x180025ce0  retn
```

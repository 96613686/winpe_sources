# WlanInternalRequestFTM

- ea: `0x180029e70`
- end: `0x18002a2ee`
- name: `WlanInternalRequestFTM`
- size: `1150`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x180007938`
- `0x180015bd0`
- `0x180023cf4`
- `0x180029e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029fb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029fb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a02a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a0a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a02a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a0a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002a181`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002a181`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002a0be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002a0be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180029fcb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180029fcb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002a222`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002a222`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18002a16d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18002a16d`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002a240`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002a240`

## pseudocode

```c
__int64 __fastcall WlanInternalRequestFTM(void *a1, __int64 a2, int a3, __int64 a4, __int64 a5, __int64 a6, _QWORD *a7)
{
  int v7; // eax
  struct _WLAN_FTM_REQUEST_ASYNC_CONTEXT *v9; // rdi
  union DOT11_OUI_HEADER *v10; // rcx
  __int64 v11; // r15
  _QWORD *v12; // r13
  DWORD v13; // esi
  __int64 v14; // rax
  DWORD LastError; // eax
  _QWORD *v16; // rcx
  struct _TP_WAIT *ThreadpoolWait; // r12
  int v18; // ecx
  int v19; // r8d
  __int64 v21; // [rsp+50h] [rbp-48h] BYREF
  __int64 v22; // [rsp+58h] [rbp-40h] BYREF
  struct _WLAN_FTM_REQUEST_ASYNC_CONTEXT *v23; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+10h]
  int v25; // [rsp+B0h] [rbp+18h]
  __int64 v26; // [rsp+B8h] [rbp+20h]

  v26 = a4;
  v25 = a3;
  v24 = a2;
  v7 = a3;
  v9 = 0;
  v23 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 159, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
    v10 = WPP_GLOBAL_Control;
    v7 = v25;
    a4 = v26;
    a2 = v24;
  }
  if ( a1 && a2 && a4 && (unsigned int)(v7 - 1) <= 0x1D && (v11 = a5) != 0 && (v12 = a7) != 0 )
  {
    v13 = LocalCreateFTMAsyncContext(a1, &v23);
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 161, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
      }
      v9 = v23;
      goto LABEL_36;
    }
    v9 = v23;
    *((_QWORD *)v23 + 18) = a6;
    *((_QWORD *)v9 + 17) = v11;
    EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)v9 + 1) + 168LL));
    if ( !*(_QWORD *)(*((_QWORD *)v9 + 1) + 296LL) )
    {
      *(_QWORD *)(*((_QWORD *)v9 + 1) + 296LL) = CreateThreadpoolCleanupGroup();
      v14 = *((_QWORD *)v9 + 1);
      if ( !*(_QWORD *)(v14 + 296) )
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            162,
            WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids,
            LastError);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)v9 + 1) + 168LL));
        goto LABEL_36;
      }
      *(_DWORD *)(v14 + 224) = 3;
      *(_QWORD *)(v14 + 232) = 0;
      *(_QWORD *)(v14 + 240) = 0;
      *(_QWORD *)(v14 + 248) = 0;
      *(_QWORD *)(v14 + 256) = 0;
      *(_QWORD *)(v14 + 264) = 0;
      *(_QWORD *)(v14 + 272) = 0;
      *(_DWORD *)(v14 + 280) = 0;
      *(_DWORD *)(v14 + 284) = 1;
      *(_DWORD *)(v14 + 288) = 72;
      v16 = (_QWORD *)*((_QWORD *)v9 + 1);
      v16[30] = v16[37];
      v16[31] = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)v9 + 1) + 168LL));
    ThreadpoolWait = CreateThreadpoolWait(
                       LocalFtmAsyncCompletionCallback,
                       *(PVOID *)v9,
                       (PTP_CALLBACK_ENVIRON)(*((_QWORD *)v9 + 1) + 224LL));
    v21 = (__int64)ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 163, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
      }
      Ndr64AsyncClientCall(
        (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo,
        0x3Cu,
        0,
        (char *)v9 + 16,
        **((_QWORD **)v9 + 1),
        v24,
        12 * v25,
        v26,
        (char *)v9 + 152,
        (char *)v9 + 160,
        v21);
      SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)v9 + 16), 0);
      *v12 = *(_QWORD *)v9;
      v9 = 0;
    }
    else
    {
      v13 = GetLastError();
    }
  }
  else
  {
    v13 = 87;
    if ( v10 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v10 + 105)
      && (*((_BYTE *)v10 + 108) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)v10 + 12), 160, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
    }
  }
LABEL_36:
  if ( v9 )
    HtDereferenceHandleWithTag(g_hHandleTable, *(_QWORD *)v9, 0, 1);
  if ( (unsigned int)dword_180084008 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180084008, 0x400000000000LL) )
  {
    v21 = 0x1000000;
    LODWORD(v23) = v13;
    v22 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v18,
      (unsigned int)byte_180076D8B,
      v19,
      (unsigned int)&v22,
      (__int64)&v23,
      (__int64)&v21);
  }
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 165, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x180029e70  mov     r11, rsp
0x180029e73  mov     [r11+20h], r9
0x180029e77  mov     [r11+18h], r8d
0x180029e7b  mov     [r11+10h], rdx
0x180029e7f  push    rbx
0x180029e80  push    rsi
0x180029e81  push    rdi
0x180029e82  push    r12
0x180029e84  push    r13
0x180029e86  push    r14
0x180029e88  push    r15
0x180029e8a  sub     rsp, 60h
0x180029e8e  mov     eax, r8d
0x180029e91  mov     rsi, rcx
0x180029e94  xor     ebx, ebx
0x180029e96  mov     edi, ebx
0x180029e98  mov     [r11+8], rbx
0x180029e9c  mov     r12d, ebx
0x180029e9f  lea     r14, WPP_GLOBAL_Control
0x180029ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ead  cmp     rcx, r14
0x180029eb0  jz      short loc_180029EF1
0x180029eb2  cmp     byte ptr [rcx+69h], 4
0x180029eb6  jb      short loc_180029EF1
0x180029eb8  test    byte ptr [rcx+6Ch], 2
0x180029ebc  jz      short loc_180029EF1
0x180029ebe  mov     edx, 9Fh
0x180029ec3  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180029eca  mov     rcx, [rcx+60h]
0x180029ece  call    WPP_SF_
0x180029ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180029eda  mov     eax, [rsp+98h+arg_10]
0x180029ee1  mov     r9, [rsp+98h+arg_18]
0x180029ee9  mov     rdx, [rsp+98h+arg_8]
0x180029ef1  test    rsi, rsi
0x180029ef4  jz      loc_18002A1F1
0x180029efa  test    rdx, rdx
0x180029efd  jz      loc_18002A1F1
0x180029f03  test    r9, r9
0x180029f06  jz      loc_18002A1F1
0x180029f0c  dec     eax
0x180029f0e  cmp     eax, 1Dh
0x180029f11  ja      loc_18002A1F1
0x180029f17  mov     r15, [rsp+98h+arg_20]
0x180029f1f  test    r15, r15
0x180029f22  jz      loc_18002A1F1
0x180029f28  mov     r13, [rsp+98h+arg_30]
0x180029f30  test    r13, r13
0x180029f33  jz      loc_18002A1F1
0x180029f39  lea     rdx, [rsp+98h+arg_0]; struct _WLAN_FTM_REQUEST_ASYNC_CONTEXT **
0x180029f41  mov     rcx, rsi; void *
0x180029f44  call    ?LocalCreateFTMAsyncContext@@YAKPEAXPEAPEAU_WLAN_FTM_REQUEST_ASYNC_CONTEXT@@@Z; LocalCreateFTMAsyncContext(void *,_WLAN_FTM_REQUEST_ASYNC_CONTEXT * *)
0x180029f49  mov     esi, eax
0x180029f4b  test    eax, eax
0x180029f4d  jz      short loc_180029F89
0x180029f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f56  cmp     rcx, r14
0x180029f59  jz      short loc_180029F7C
0x180029f5b  cmp     byte ptr [rcx+69h], 1
0x180029f5f  jb      short loc_180029F7C
0x180029f61  test    byte ptr [rcx+6Ch], 2
0x180029f65  jz      short loc_180029F7C
0x180029f67  mov     edx, 0A1h
0x180029f6c  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180029f73  mov     rcx, [rcx+60h]
0x180029f77  call    WPP_SF_
0x180029f7c  mov     rdi, [rsp+98h+arg_0]
0x180029f84  jmp     loc_18002A21A
0x180029f89  mov     rax, [rsp+98h+arg_28]
0x180029f91  mov     rdi, [rsp+98h+arg_0]
0x180029f99  mov     [rdi+90h], rax
0x180029fa0  mov     [rdi+88h], r15
0x180029fa7  mov     rcx, [rdi+8]
0x180029fab  mov     r15d, 0A8h
0x180029fb1  add     rcx, r15; lpCriticalSection
0x180029fb4  call    cs:__imp_EnterCriticalSection
0x180029fba  mov     rax, [rdi+8]
0x180029fbe  cmp     [rax+128h], rbx
0x180029fc5  jnz     loc_18002A09C
0x180029fcb  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180029fd1  mov     rcx, rax
0x180029fd4  mov     rax, [rdi+8]
0x180029fd8  mov     [rax+128h], rcx
0x180029fdf  mov     rax, [rdi+8]
0x180029fe3  cmp     [rax+128h], rbx
0x180029fea  jnz     short loc_18002A035
0x180029fec  call    cs:__imp_GetLastError
0x180029ff2  mov     esi, eax
0x180029ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ffb  cmp     rcx, r14
0x180029ffe  jz      short loc_18002A023
0x18002a000  cmp     byte ptr [rcx+69h], 1
0x18002a004  jb      short loc_18002A023
0x18002a006  test    byte ptr [rcx+6Ch], 2
0x18002a00a  jz      short loc_18002A023
0x18002a00c  lea     edx, [r15-6]
0x18002a010  mov     r9d, eax
0x18002a013  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x18002a01a  mov     rcx, [rcx+60h]
0x18002a01e  call    WPP_SF_d
0x18002a023  mov     rcx, [rdi+8]
0x18002a027  add     rcx, r15; lpCriticalSection
0x18002a02a  call    cs:__imp_LeaveCriticalSection
0x18002a030  jmp     loc_18002A21A
0x18002a035  mov     dword ptr [rax+0E0h], 3
0x18002a03f  mov     [rax+0E8h], rbx
0x18002a046  mov     [rax+0F0h], rbx
0x18002a04d  mov     [rax+0F8h], rbx
0x18002a054  mov     [rax+100h], rbx
0x18002a05b  mov     [rax+108h], rbx
0x18002a062  mov     [rax+110h], rbx
0x18002a069  mov     [rax+118h], ebx
0x18002a06f  mov     dword ptr [rax+11Ch], 1
0x18002a079  mov     dword ptr [rax+120h], 48h ; 'H'
0x18002a083  mov     rcx, [rdi+8]
0x18002a087  mov     rax, [rcx+128h]
0x18002a08e  mov     [rcx+0F0h], rax
0x18002a095  mov     [rcx+0F8h], rbx
0x18002a09c  mov     rcx, [rdi+8]
0x18002a0a0  add     rcx, r15; lpCriticalSection
0x18002a0a3  call    cs:__imp_LeaveCriticalSection
0x18002a0a9  mov     r8, [rdi+8]
0x18002a0ad  add     r8, 0E0h; pcbe
0x18002a0b4  mov     rdx, [rdi]; pv
0x18002a0b7  lea     rcx, ?LocalFtmAsyncCompletionCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18002a0be  call    cs:__imp_CreateThreadpoolWait
0x18002a0c4  mov     r12, rax
0x18002a0c7  mov     [rsp+98h+var_48], rax
0x18002a0cc  test    rax, rax
0x18002a0cf  jnz     short loc_18002A0DE
0x18002a0d1  call    cs:__imp_GetLastError
0x18002a0d7  mov     esi, eax
0x18002a0d9  jmp     loc_18002A21A
0x18002a0de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0e5  cmp     rcx, r14
0x18002a0e8  jz      short loc_18002A10C
0x18002a0ea  cmp     byte ptr [rcx+69h], 3
0x18002a0ee  jb      short loc_18002A10C
0x18002a0f0  test    byte ptr [rcx+6Ch], 2
0x18002a0f4  jz      short loc_18002A10C
0x18002a0f6  mov     edx, 0A3h
0x18002a0fb  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x18002a102  mov     rcx, [rcx+60h]
0x18002a106  call    WPP_SF_
0x18002a10b  nop
0x18002a10c  lea     rax, [rdi+0A0h]
0x18002a113  lea     rcx, [rdi+98h]
0x18002a11a  mov     edx, [rsp+98h+arg_10]
0x18002a121  lea     edx, [rdx+rdx*2]
0x18002a124  shl     edx, 2
0x18002a127  mov     r8, [rdi+8]
0x18002a12b  lea     r9, [rdi+10h]
0x18002a12f  mov     [rsp+98h+var_50], rax
0x18002a134  mov     [rsp+98h+var_58], rcx
0x18002a139  mov     rax, [rsp+98h+arg_18]
0x18002a141  mov     [rsp+98h+var_60], rax
0x18002a146  mov     [rsp+98h+var_68], edx
0x18002a14a  mov     rax, [rsp+98h+arg_8]
0x18002a152  mov     [rsp+98h+var_70], rax
0x18002a157  mov     rax, [r8]
0x18002a15a  mov     [rsp+98h+var_78], rax
0x18002a15f  xor     r8d, r8d; pReturnValue
0x18002a162  lea     edx, [r8+3Ch]; nProcNum
0x18002a166  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18002a16d  call    cs:__imp_Ndr64AsyncClientCall
0x18002a173  nop
0x18002a174  xor     r8d, r8d; pftTimeout
0x18002a177  mov     rdx, [rdi+80h]; h
0x18002a17e  mov     rcx, r12; pwa
0x18002a181  call    cs:__imp_SetThreadpoolWait
0x18002a187  mov     r12, rbx
0x18002a18a  mov     rax, [rdi]
0x18002a18d  mov     [r13+0], rax
0x18002a191  mov     rdi, rbx
0x18002a194  jmp     loc_18002A21A
0x18002a199  mov     ebx, eax
0x18002a19b  lea     rax, WPP_GLOBAL_Control
0x18002a1a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1a9  cmp     rcx, rax
0x18002a1ac  jz      short loc_18002A1D2
0x18002a1ae  cmp     byte ptr [rcx+69h], 1
0x18002a1b2  jb      short loc_18002A1D2
0x18002a1b4  test    byte ptr [rcx+6Ch], 2
0x18002a1b8  jz      short loc_18002A1D2
0x18002a1ba  mov     edx, 0A4h
0x18002a1bf  mov     r9d, ebx
0x18002a1c2  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x18002a1c9  mov     rcx, [rcx+60h]
0x18002a1cd  call    WPP_SF_d
0x18002a1d2  mov     ecx, ebx; unsigned int
0x18002a1d4  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x18002a1d9  mov     esi, eax
0x18002a1db  lea     r14, WPP_GLOBAL_Control
0x18002a1e2  mov     rdi, [rsp+98h+arg_0]
0x18002a1ea  mov     r12, [rsp+98h+var_48]
0x18002a1ef  jmp     short loc_18002A21A
0x18002a1f1  mov     esi, 57h ; 'W'
0x18002a1f6  cmp     rcx, r14
0x18002a1f9  jz      short loc_18002A21A
0x18002a1fb  cmp     byte ptr [rcx+69h], 1
0x18002a1ff  jb      short loc_18002A21A
0x18002a201  test    byte ptr [rcx+6Ch], 2
0x18002a205  jz      short loc_18002A21A
0x18002a207  lea     edx, [rsi+49h]
0x18002a20a  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x18002a211  mov     rcx, [rcx+60h]
0x18002a215  call    WPP_SF_
0x18002a21a  test    r12, r12
0x18002a21d  jz      short loc_18002A228
0x18002a21f  mov     rcx, r12; pwa
0x18002a222  call    cs:__imp_CloseThreadpoolWait
0x18002a228  test    rdi, rdi
0x18002a22b  jz      short loc_18002A246
0x18002a22d  mov     r9d, 1
0x18002a233  xor     r8d, r8d
0x18002a236  mov     rdx, [rdi]
0x18002a239  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18002a240  call    cs:__imp_HtDereferenceHandleWithTag
0x18002a246  mov     eax, cs:dword_180084008
0x18002a24c  cmp     eax, 5
0x18002a24f  jbe     short loc_18002A2AC
0x18002a251  mov     rdx, 400000000000h
0x18002a25b  lea     rcx, dword_180084008
0x18002a262  call    _tlgKeywordOn
0x18002a267  test    al, al
0x18002a269  jz      short loc_18002A2AC
0x18002a26b  mov     [rsp+98h+var_48], 1000000h
0x18002a274  mov     dword ptr [rsp+98h+arg_0], esi
0x18002a27b  mov     [rsp+98h+var_40], 1
0x18002a284  lea     rax, [rsp+98h+var_48]
0x18002a289  mov     [rsp+98h+var_70], rax
0x18002a28e  lea     rax, [rsp+98h+arg_0]
0x18002a296  mov     [rsp+98h+var_78], rax
0x18002a29b  lea     r9, [rsp+98h+var_40]
0x18002a2a0  lea     rdx, byte_180076D8B
0x18002a2a7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18002a2ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2b3  cmp     rcx, r14
0x18002a2b6  jz      short loc_18002A2DC
0x18002a2b8  cmp     byte ptr [rcx+69h], 4
0x18002a2bc  jb      short loc_18002A2DC
0x18002a2be  test    byte ptr [rcx+6Ch], 2
0x18002a2c2  jz      short loc_18002A2DC
0x18002a2c4  mov     edx, 0A5h
0x18002a2c9  mov     r9d, esi
0x18002a2cc  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x18002a2d3  mov     rcx, [rcx+60h]
0x18002a2d7  call    WPP_SF_d
0x18002a2dc  mov     eax, esi
0x18002a2de  add     rsp, 60h
0x18002a2e2  pop     r15
0x18002a2e4  pop     r14
0x18002a2e6  pop     r13
0x18002a2e8  pop     r12
0x18002a2ea  pop     rdi
0x18002a2eb  pop     rsi
0x18002a2ec  pop     rbx
0x18002a2ed  retn
0x180060ff4  push    rbp
0x180060ff6  sub     rsp, 50h
0x180060ffa  mov     rbp, rdx
0x180060ffd  mov     rcx, [rcx]
0x180061000  mov     ecx, [rcx]; ExceptionCode
0x180061002  call    cs:__imp_RpcExceptionFilter
0x180061008  nop
0x180061009  add     rsp, 50h
0x18006100d  pop     rbp
0x18006100e  retn
```

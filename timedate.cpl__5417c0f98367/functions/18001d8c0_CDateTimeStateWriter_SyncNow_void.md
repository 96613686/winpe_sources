# CDateTimeStateWriter::_SyncNow(void)

- ea: `0x18001d8c0`
- end: `0x18001dcae`
- name: `?_SyncNow@CDateTimeStateWriter@@AEAAJXZ`
- size: `1006`
- prototype: `__int64 __fastcall(CDateTimeStateWriter *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dcc0`

## callees

- `0x180004da4`
- `0x180006dd8`
- `0x1800085b8`
- `0x1800089c8`
- `0x180008a0c`
- `0x1800092c4`
- `0x180016818`
- `0x18001704c`
- `0x18001cedc`
- `0x18001d3f8`
- `0x18001d8c0`
- `0x180028f2e`
- `0x180028f60`
- `0x180028ff0`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x18001da00`
- `SHLWAPI!StrChrW` at `0x18001da00`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001db0b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001db0b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001dab7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001dab7`
- `USER32!PostMessageW` at `0x18001dc34`
- `USER32!PostMessageW` at `0x18001dc34`

## pseudocode

```c
__int64 __fastcall CDateTimeStateWriter::_SyncNow(CDateTimeStateWriter *this)
{
  unsigned int v2; // edi
  int v3; // eax
  char *v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // r14d
  const WCHAR *v7; // rsi
  int v8; // eax
  int i; // esi
  int v10; // eax
  unsigned int v11; // esi
  int v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  HWND v15; // rcx
  int v16; // ecx
  int *v18; // [rsp+20h] [rbp-E0h]
  _QWORD v19[42]; // [rsp+40h] [rbp-C0h] BYREF
  size_t psz2[66]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v21[264]; // [rsp+3A0h] [rbp+2A0h] BYREF
  int v22[1044]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 v23[2088]; // [rsp+1600h] [rbp+1500h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+26A8h] [rbp+25A8h]

  wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v19,
    "SynchronizeWithAnInternetTimeServer_SyncNow");
  v19[0] = &TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow::`vftable';
  TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow::StartActivity((TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow *)v19);
  v2 = 0;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 4, 3) == 3 )
  {
    memset_0(v21, 0, 0x208u);
    memset_0(psz2, 0, 0x208u);
    v3 = (*(__int64 (__fastcall **)(CDateTimeStateWriter *, __int64, int *, __int64))(*(_QWORD *)this + 120LL))(
           this,
           1,
           v22,
           2084);
    v2 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"shell\\cpls\\utc\\state.cpp",
        (const char *)(unsigned int)v3,
        (int)v18);
LABEL_33:
      _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 2, 4);
      goto LABEL_34;
    }
    StringCchCopyW(v21, 0x104u, (size_t *)this + 6);
    StringCchCopyW((unsigned __int16 *)psz2, 0x100u, (size_t *)this + 6);
    v4 = (char *)v22;
    v5 = 0;
    v6 = 18;
    while ( v4 )
    {
      v7 = (const WCHAR *)&v4[2 * v5];
      if ( (unsigned int)ComparePeers(v7, (PCWSTR)psz2) )
        goto LABEL_9;
      v4 = (char *)StrChrW(v7, 0x20u);
      v5 = 1;
    }
    StringCchCopyW(v23, 0x824u, psz2);
    v18 = v22;
    StringCchPrintfW((unsigned __int16 *)psz2, 0x104u, L"%s %s", v23);
    v6 = 26;
LABEL_9:
    if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 4, 4) != 4 )
      goto LABEL_33;
    if ( !(unsigned int)InternetTime_IsW32TimeServiceRunning() )
    {
      v8 = (*(__int64 (__fastcall **)(CDateTimeStateWriter *, _QWORD))(*(_QWORD *)this + 104LL))(this, 0);
      v2 = v8;
      if ( v8 >= 0 )
      {
        for ( i = 0; i < 1000; ++i )
        {
          if ( (unsigned int)InternetTime_IsW32TimeServiceRunning() )
            break;
          if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 4, 4) != 4 )
            break;
          Sleep(0xAu);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x175,
          (unsigned int)"shell\\cpls\\utc\\state.cpp",
          (const char *)(unsigned int)v8,
          (int)v18);
      }
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 4, 4) != 4 )
      goto LABEL_33;
    if ( (v2 & 0x80000000) == 0 )
    {
      v10 = (*(__int64 (__fastcall **)(CDateTimeStateWriter *, _QWORD))(*(_QWORD *)this + 112LL))(this, v6);
      v11 = v10;
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18E,
          (unsigned int)"shell\\cpls\\utc\\state.cpp",
          (const char *)(unsigned int)v10,
          (int)v18);
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 4, 4) == 4 )
      {
        v18 = (int *)psz2;
        v12 = (*(__int64 (__fastcall **)(CDateTimeStateWriter *, _QWORD, char *, __int64))(*(_QWORD *)this + 128LL))(
                this,
                v11,
                (char *)this + 560,
                4024);
        v2 = v12;
        if ( v12 >= 0 )
        {
          v14 = (*(__int64 (__fastcall **)(CDateTimeStateWriter *, int *))(*(_QWORD *)this + 72LL))(this, v22);
          if ( v14 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x199,
              (unsigned int)"shell\\cpls\\utc\\state.cpp",
              (const char *)(unsigned int)v14,
              (int)psz2);
          v12 = (*(__int64 (__fastcall **)(CDateTimeStateWriter *, __int64))(*(_QWORD *)this + 104LL))(this, 1);
          if ( v12 >= 0 )
            goto LABEL_31;
          v13 = 410;
        }
        else
        {
          v13 = 406;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"shell\\cpls\\utc\\state.cpp",
          (const char *)(unsigned int)v12,
          (int)v18);
      }
      else
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x19F,
          (unsigned int)"shell\\cpls\\utc\\state.cpp",
          (const char *)0x80004005LL,
          (int)v18);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"shell\\cpls\\utc\\state.cpp",
        (const char *)v2,
        (int)v18);
      LoadStringW(g_hInst, 0x1FEu, (LPWSTR)this + 280, 4024);
    }
LABEL_31:
    v15 = (HWND)*((_QWORD *)this + 1076);
    if ( v15 )
      PostMessageW(v15, *((_DWORD *)this + 2154), 1u, 0);
    goto LABEL_33;
  }
LABEL_34:
  v16 = *((_DWORD *)this + 11);
  if ( ((v16 - 2) & 0xFFFFFFFC) != 0 || v16 == 4 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"shell\\cpls\\utc\\state.cpp",
      (const char *)0x80004005LL,
      (int)v18);
  wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19, v2);
  TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow::~SynchronizeWithAnInternetTimeServer_SyncNow((TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow *)v19);
  return v2;
}

```

## disassembly

```asm
0x18001d8c0  push    rbp
0x18001d8c2  push    rbx
0x18001d8c3  push    rsi
0x18001d8c4  push    rdi
0x18001d8c5  push    r12
0x18001d8c7  push    r13
0x18001d8c9  push    r14
0x18001d8cb  push    r15
0x18001d8cd  lea     rbp, [rsp-2568h]
0x18001d8d5  mov     eax, 2668h
0x18001d8da  call    _alloca_probe
0x18001d8df  sub     rsp, rax
0x18001d8e2  mov     rax, cs:__security_cookie
0x18001d8e9  xor     rax, rsp
0x18001d8ec  mov     [rbp+25A0h+var_50], rax
0x18001d8f3  mov     rbx, rcx
0x18001d8f6  lea     rdx, aSynchronizewit; "SynchronizeWithAnInternetTimeServer_Syn"...
0x18001d8fd  lea     rcx, [rsp+26A0h+var_2660]
0x18001d902  call    ??0?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001d907  lea     rax, ??_7SynchronizeWithAnInternetTimeServer_SyncNow@TimeDateTraceLoggingTelemetry@@6B@; const TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow::`vftable'
0x18001d90e  lea     rcx, [rsp+26A0h+var_2660]; this
0x18001d913  mov     [rsp+26A0h+var_2660], rax
0x18001d918  call    ?StartActivity@SynchronizeWithAnInternetTimeServer_SyncNow@TimeDateTraceLoggingTelemetry@@QEAAXXZ; TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow::StartActivity(void)
0x18001d91d  xor     edi, edi
0x18001d91f  lea     r12, aShellCplsUtcSt; "shell\\cpls\\utc\\state.cpp"
0x18001d926  lea     eax, [rdi+3]
0x18001d929  lea     r15d, [rdi+4]
0x18001d92d  lock cmpxchg [rbx+2Ch], r15d
0x18001d933  jnz     loc_18001DC47
0x18001d939  mov     edi, 208h
0x18001d93e  lea     rcx, [rbp+25A0h+var_2300]; void *
0x18001d945  mov     r8d, edi; Size
0x18001d948  xor     edx, edx; Val
0x18001d94a  call    memset_0
0x18001d94f  mov     r8d, edi; Size
0x18001d952  lea     rcx, [rbp+25A0h+psz2]; void *
0x18001d959  xor     edx, edx; Val
0x18001d95b  call    memset_0
0x18001d960  mov     rax, [rbx]
0x18001d963  lea     r13d, [r15-3]
0x18001d967  mov     r9d, 824h
0x18001d96d  lea     r8, [rbp+25A0h+var_20F0]
0x18001d974  mov     edx, r13d
0x18001d977  mov     rcx, rbx
0x18001d97a  mov     rax, [rax+78h]
0x18001d97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d983  mov     edi, eax
0x18001d985  test    eax, eax
0x18001d987  jns     short loc_18001D9A5
0x18001d989  mov     rcx, [rbp+25A8h]; this
0x18001d990  mov     r9d, eax; char *
0x18001d993  mov     r8, r12; unsigned int
0x18001d996  mov     edx, 156h; void *
0x18001d99b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d9a0  jmp     loc_18001DC3A
0x18001d9a5  lea     r8, [rbx+30h]; unsigned __int16 *
0x18001d9a9  mov     edx, 104h; unsigned __int64
0x18001d9ae  lea     rcx, [rbp+25A0h+var_2300]; unsigned __int16 *
0x18001d9b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d9ba  lea     r8, [rbx+30h]; unsigned __int16 *
0x18001d9be  mov     edx, 100h; unsigned __int64
0x18001d9c3  lea     rcx, [rbp+25A0h+psz2]; unsigned __int16 *
0x18001d9ca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d9cf  lea     rax, [rbp+25A0h+var_20F0]
0x18001d9d6  xor     ecx, ecx
0x18001d9d8  mov     r14d, 12h
0x18001d9de  test    rax, rax
0x18001d9e1  jz      short loc_18001DA0B
0x18001d9e3  lea     rsi, [rax+rcx*2]
0x18001d9e7  mov     rcx, rsi; psz1
0x18001d9ea  lea     rdx, [rbp+25A0h+psz2]; psz2
0x18001d9f1  call    ?ComparePeers@@YAHPEAG0@Z; ComparePeers(ushort *,ushort *)
0x18001d9f6  test    eax, eax
0x18001d9f8  jnz     short loc_18001DA54
0x18001d9fa  lea     edx, [rax+20h]; wMatch
0x18001d9fd  mov     rcx, rsi; pszStart
0x18001da00  call    cs:__imp_StrChrW
0x18001da06  mov     rcx, r13
0x18001da09  jmp     short loc_18001D9DE
0x18001da0b  lea     r8, [rbp+25A0h+psz2]; unsigned __int16 *
0x18001da12  mov     edx, 824h; unsigned __int64
0x18001da17  lea     rcx, [rbp+25A0h+var_10A0]; unsigned __int16 *
0x18001da1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001da23  lea     r11, [rbp+25A0h+var_20F0]
0x18001da2a  mov     edx, 104h; unsigned __int64
0x18001da2f  lea     r9, [rbp+25A0h+var_10A0]
0x18001da36  mov     qword ptr [rsp+26A0h+var_2680], r11; int
0x18001da3b  lea     r8, aSS_0; "%s %s"
0x18001da42  lea     rcx, [rbp+25A0h+psz2]; unsigned __int16 *
0x18001da49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001da4e  mov     r14d, 1Ah
0x18001da54  mov     eax, r15d
0x18001da57  lock cmpxchg [rbx+2Ch], r15d
0x18001da5d  jnz     loc_18001DC3A
0x18001da63  call    InternetTime_IsW32TimeServiceRunning
0x18001da68  test    eax, eax
0x18001da6a  jnz     short loc_18001DAC8
0x18001da6c  mov     rax, [rbx]
0x18001da6f  xor     edx, edx
0x18001da71  mov     rcx, rbx
0x18001da74  mov     rax, [rax+68h]
0x18001da78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da7d  mov     edi, eax
0x18001da7f  test    eax, eax
0x18001da81  jns     short loc_18001DA9C
0x18001da83  mov     rcx, [rbp+25A8h]; this
0x18001da8a  mov     r9d, eax; char *
0x18001da8d  mov     r8, r12; unsigned int
0x18001da90  mov     edx, 175h; void *
0x18001da95  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001da9a  jmp     short loc_18001DAC8
0x18001da9c  xor     esi, esi
0x18001da9e  call    InternetTime_IsW32TimeServiceRunning
0x18001daa3  test    eax, eax
0x18001daa5  jnz     short loc_18001DAC8
0x18001daa7  mov     eax, r15d
0x18001daaa  lock cmpxchg [rbx+2Ch], r15d
0x18001dab0  jnz     short loc_18001DAC8
0x18001dab2  mov     ecx, 0Ah; dwMilliseconds
0x18001dab7  call    cs:__imp_Sleep
0x18001dabd  add     esi, r13d
0x18001dac0  cmp     esi, 3E8h
0x18001dac6  jl      short loc_18001DA9E
0x18001dac8  mov     eax, r15d
0x18001dacb  lock cmpxchg [rbx+2Ch], r15d
0x18001dad1  jnz     loc_18001DC3A
0x18001dad7  test    edi, edi
0x18001dad9  jns     short loc_18001DB16
0x18001dadb  mov     rcx, [rbp+25A8h]; this
0x18001dae2  mov     r9d, edi; char *
0x18001dae5  mov     r8, r12; unsigned int
0x18001dae8  mov     edx, 189h; void *
0x18001daed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001daf2  mov     rcx, cs:g_hInst; hInstance
0x18001daf9  lea     r8, [rbx+230h]; lpBuffer
0x18001db00  mov     edx, 1FEh; uID
0x18001db05  mov     r9d, 0FB8h; cchBufferMax
0x18001db0b  call    cs:__imp_LoadStringW
0x18001db11  jmp     loc_18001DC1C
0x18001db16  mov     rax, [rbx]
0x18001db19  mov     edx, r14d
0x18001db1c  mov     rcx, rbx
0x18001db1f  mov     rax, [rax+70h]
0x18001db23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db28  mov     esi, eax
0x18001db2a  test    eax, eax
0x18001db2c  jns     short loc_18001DB45
0x18001db2e  mov     rcx, [rbp+25A8h]; this
0x18001db35  mov     r9d, eax; char *
0x18001db38  mov     r8, r12; unsigned int
0x18001db3b  mov     edx, 18Eh; void *
0x18001db40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001db45  mov     eax, r15d
0x18001db48  lock cmpxchg [rbx+2Ch], r15d
0x18001db4e  jnz     loc_18001DC02
0x18001db54  mov     rax, [rbx]
0x18001db57  lea     rcx, [rbp+25A0h+var_2300]
0x18001db5e  mov     [rsp+26A0h+var_2670], rcx
0x18001db63  lea     r8, [rbx+230h]
0x18001db6a  lea     rcx, [rbp+25A0h+psz2]
0x18001db71  mov     [rsp+26A0h+var_2678], 104h
0x18001db79  mov     qword ptr [rsp+26A0h+var_2680], rcx; int
0x18001db7e  mov     r9d, 0FB8h
0x18001db84  mov     rax, [rax+80h]
0x18001db8b  mov     rcx, rbx
0x18001db8e  mov     edx, esi
0x18001db90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db95  mov     edi, eax
0x18001db97  test    eax, eax
0x18001db99  jns     short loc_18001DBB4
0x18001db9b  mov     edx, 196h; void *
0x18001dba0  mov     rcx, [rbp+25A8h]; this
0x18001dba7  mov     r8, r12; unsigned int
0x18001dbaa  mov     r9d, eax; char *
0x18001dbad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dbb2  jmp     short loc_18001DC1C
0x18001dbb4  mov     rax, [rbx]
0x18001dbb7  lea     rdx, [rbp+25A0h+var_20F0]
0x18001dbbe  mov     rcx, rbx
0x18001dbc1  mov     rax, [rax+48h]
0x18001dbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbca  test    eax, eax
0x18001dbcc  jns     short loc_18001DBE5
0x18001dbce  mov     rcx, [rbp+25A8h]; this
0x18001dbd5  mov     r9d, eax; char *
0x18001dbd8  mov     r8, r12; unsigned int
0x18001dbdb  mov     edx, 199h; void *
0x18001dbe0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dbe5  mov     rax, [rbx]
0x18001dbe8  mov     edx, r13d
0x18001dbeb  mov     rcx, rbx
0x18001dbee  mov     rax, [rax+68h]
0x18001dbf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbf7  test    eax, eax
0x18001dbf9  jns     short loc_18001DC1C
0x18001dbfb  mov     edx, 19Ah
0x18001dc00  jmp     short loc_18001DBA0
0x18001dc02  mov     rcx, [rbp+25A8h]; this
0x18001dc09  mov     r9d, 80004005h; char *
0x18001dc0f  mov     r8, r12; unsigned int
0x18001dc12  mov     edx, 19Fh; void *
0x18001dc17  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001dc1c  mov     rcx, [rbx+21A0h]; hWnd
0x18001dc23  test    rcx, rcx
0x18001dc26  jz      short loc_18001DC3A
0x18001dc28  mov     edx, [rbx+21A8h]; Msg
0x18001dc2e  xor     r9d, r9d; lParam
0x18001dc31  mov     r8, r13; wParam
0x18001dc34  call    cs:__imp_PostMessageW
0x18001dc3a  mov     ecx, 2
0x18001dc3f  mov     eax, r15d
0x18001dc42  lock cmpxchg [rbx+2Ch], ecx
0x18001dc47  mov     ecx, [rbx+2Ch]
0x18001dc4a  lea     eax, [rcx-2]
0x18001dc4d  test    eax, 0FFFFFFFCh
0x18001dc52  jnz     short loc_18001DC59
0x18001dc54  cmp     ecx, r15d
0x18001dc57  jnz     short loc_18001DC73
0x18001dc59  mov     rcx, [rbp+25A8h]; this
0x18001dc60  mov     r9d, 80004005h; char *
0x18001dc66  mov     r8, r12; unsigned int
0x18001dc69  mov     edx, 1B2h; void *
0x18001dc6e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dc73  mov     edx, edi
0x18001dc75  lea     rcx, [rsp+26A0h+var_2660]
0x18001dc7a  call    ?Stop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001dc7f  lea     rcx, [rsp+26A0h+var_2660]; this
0x18001dc84  call    ??1SynchronizeWithAnInternetTimeServer_SyncNow@TimeDateTraceLoggingTelemetry@@QEAA@XZ; TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow::~SynchronizeWithAnInternetTimeServer_SyncNow(void)
0x18001dc89  mov     eax, edi
0x18001dc8b  mov     rcx, [rbp+25A0h+var_50]
0x18001dc92  xor     rcx, rsp; StackCookie
0x18001dc95  call    __security_check_cookie
0x18001dc9a  add     rsp, 2668h
0x18001dca1  pop     r15
0x18001dca3  pop     r14
0x18001dca5  pop     r13
0x18001dca7  pop     r12
0x18001dca9  pop     rdi
0x18001dcaa  pop     rsi
0x18001dcab  pop     rbx
0x18001dcac  pop     rbp
0x18001dcad  retn
```

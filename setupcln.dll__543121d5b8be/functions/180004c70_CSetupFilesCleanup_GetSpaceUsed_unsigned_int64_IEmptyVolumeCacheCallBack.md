# CSetupFilesCleanup::GetSpaceUsed(unsigned __int64 *,IEmptyVolumeCacheCallBack *)

- ea: `0x180004c70`
- end: `0x18000506d`
- name: `?GetSpaceUsed@CSetupFilesCleanup@@UEAAJPEA_KPEAUIEmptyVolumeCacheCallBack@@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(CSetupFilesCleanup *__hidden this, unsigned __int64 *, struct IEmptyVolumeCacheCallBack *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001418`
- `0x180001524`
- `0x18000166c`
- `0x180003be8`
- `0x1800040c0`
- `0x1800047ac`
- `0x180004c30`
- `0x180004c70`
- `0x1800131a2`
- `0x1800131e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004dad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004dad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180004d8d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180004d8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004db6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004db6`
- `WDSCORE!CurrentIP` at `0x180004cc8`
- `WDSCORE!CurrentIP` at `0x180004dc4`
- `WDSCORE!CurrentIP` at `0x180004e35`
- `WDSCORE!CurrentIP` at `0x180004ea2`
- `WDSCORE!CurrentIP` at `0x180004cc8`
- `WDSCORE!CurrentIP` at `0x180004dc4`
- `WDSCORE!CurrentIP` at `0x180004e35`
- `WDSCORE!CurrentIP` at `0x180004ea2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004d28`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004e27`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004e94`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004f01`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004d28`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004e27`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004e94`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004f01`

## pseudocode

```c
__int64 __fastcall CSetupFilesCleanup::GetSpaceUsed(
        CSetupFilesCleanup *this,
        unsigned __int64 *a2,
        struct IEmptyVolumeCacheCallBack *a3)
{
  unsigned int v6; // r14d
  DWORD LastError; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  unsigned int v10; // r15d
  HANDLE MutexW; // rbx
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  unsigned int v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v29; // [rsp+64h] [rbp-9Ch] BYREF
  int v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h] BYREF
  _TlgCVGetter *v35; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v36[10]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v37[144]; // [rsp+F0h] [rbp-10h] BYREF

  memset_0(v36, 0, sizeof(v36));
  v6 = 0;
  v30 = 0;
  LastError = GetLastError();
  v8 = CurrentIP();
  v9 = ConstructPartialMsgW(
         0x4000000,
         "CSetupFilesCleanup::GetSpaceUsed - Calculating the space for session: %s",
         *((const char **)this + 9));
  WdsSetupLogMessageW(
    v9,
    0,
    L"D",
    0,
    530,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::GetSpaceUsed",
    v8,
    LastError,
    0,
    0);
  if ( a2 )
  {
    *a2 = 0;
    v10 = CSetupFilesCleanup::FullBlockChecks(this);
    if ( !v10 )
    {
      v36[3] = *((_QWORD *)this + 2);
      v36[8] = *((_QWORD *)this + 10);
      v36[0] = 0;
      v36[1] = 0;
      v36[2] = &v30;
      v36[4] = a3;
      v36[5] = a2;
      v36[9] = 0;
      MutexW = CreateMutexW(0, 1, L"Global\\Microsoft.Windows.Setup.SetupCln");
      v6 = CSetupFilesCleanup::CleanVolume(this, (struct _SETUPCLN_PARAMS *)v36);
      if ( MutexW )
      {
        ReleaseMutex(MutexW);
        CloseHandle(MutexW);
      }
    }
  }
  else
  {
    v10 = 0;
    v6 = -2147024809;
  }
  v12 = GetLastError();
  v13 = CurrentIP();
  v14 = ConstructPartialMsgW(0x4000000, "CSetupFilesCleanup::GetSpaceUsed - Space used : %llu", *a2);
  WdsSetupLogMessageW(
    v14,
    0,
    L"D",
    0,
    566,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::GetSpaceUsed",
    v13,
    v12,
    0,
    0);
  v15 = GetLastError();
  v16 = CurrentIP();
  v17 = ConstructPartialMsgW(0x4000000, "CSetupFilesCleanup::GetSpaceUsed - Block status: %d", v10);
  WdsSetupLogMessageW(
    v17,
    0,
    L"D",
    0,
    567,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::GetSpaceUsed",
    v16,
    v15,
    0,
    0);
  v18 = GetLastError();
  v19 = CurrentIP();
  v20 = ConstructPartialMsgW(0x4000000, "CSetupFilesCleanup::GetSpaceUsed - Return status: %x", v6);
  WdsSetupLogMessageW(
    v20,
    0,
    L"D",
    0,
    568,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::GetSpaceUsed",
    v19,
    v18,
    0,
    0);
  if ( *((_QWORD *)this + 10) )
  {
    if ( (unsigned int)dword_18001F018 > 5 && (unsigned __int8)tlgKeywordOn() )
    {
      v35 = _TlgCVGetter::_TlgCVGetter((_TlgCVGetter *)v37, *((struct TraceLoggingCorrelationVector **)this + 10));
      v31 = *a2;
      v32 = *((_QWORD *)this + 8);
      v33 = *((_QWORD *)this + 9);
      v34 = 0x80000000LL;
      v28 = v6;
      v29 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v21,
        (__int64)word_18001B86A,
        v22,
        v23,
        (__int64)&v34,
        &v33,
        &v32,
        (__int64)&v31,
        (__int64)&v29,
        (__int64)&v28,
        &v35);
    }
  }
  else if ( (unsigned int)dword_18001F018 > 5 && (unsigned __int8)tlgKeywordOn() )
  {
    v34 = *a2;
    v33 = *((_QWORD *)this + 8);
    v32 = *((_QWORD *)this + 9);
    v31 = 0x80000000LL;
    v29 = v6;
    v28 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v24,
      (__int64)&word_18001B7E6,
      v25,
      v26,
      (__int64)&v31,
      &v32,
      &v33);
  }
  return v6;
}

```

## disassembly

```asm
0x180004c70  mov     [rsp-8+arg_18], rbx
0x180004c75  push    rbp
0x180004c76  push    rsi
0x180004c77  push    rdi
0x180004c78  push    r12
0x180004c7a  push    r13
0x180004c7c  push    r14
0x180004c7e  push    r15
0x180004c80  lea     rbp, [rsp-90h]
0x180004c88  sub     rsp, 190h
0x180004c8f  mov     rax, cs:__security_cookie
0x180004c96  xor     rax, rsp
0x180004c99  mov     [rbp+0C0h+var_40], rax
0x180004ca0  mov     r12, rdx
0x180004ca3  mov     r13, r8
0x180004ca6  xor     edx, edx; Val
0x180004ca8  mov     rsi, rcx
0x180004cab  lea     rcx, [rbp+0C0h+var_120]; void *
0x180004caf  lea     r8d, [rdx+50h]; Size
0x180004cb3  call    memset_0
0x180004cb8  xor     r14d, r14d
0x180004cbb  mov     [rsp+1C0h+var_158], r14d
0x180004cc0  call    cs:__imp_GetLastError
0x180004cc6  mov     edi, eax
0x180004cc8  call    cs:__imp_CurrentIP
0x180004cce  mov     r8, [rsi+48h]
0x180004cd2  lea     rdx, aCsetupfilescle_17; "CSetupFilesCleanup::GetSpaceUsed - Calc"...
0x180004cd9  mov     ecx, 4000000h; unsigned int
0x180004cde  mov     rbx, rax
0x180004ce1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004ce6  mov     dword ptr [rsp+1C0h+var_170], r14d
0x180004ceb  lea     rcx, aCsetupfilescle_1; "CSetupFilesCleanup::GetSpaceUsed"
0x180004cf2  mov     [rsp+1C0h+var_178], r14
0x180004cf7  lea     r8, aD; "D"
0x180004cfe  mov     dword ptr [rsp+1C0h+var_180], edi
0x180004d02  xor     r9d, r9d
0x180004d05  mov     [rsp+1C0h+var_188], rbx
0x180004d0a  xor     edx, edx
0x180004d0c  mov     [rsp+1C0h+var_190], rcx
0x180004d11  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180004d18  mov     [rsp+1C0h+var_198], rcx
0x180004d1d  mov     rcx, rax
0x180004d20  mov     dword ptr [rsp+1C0h+var_1A0], 212h
0x180004d28  call    cs:__imp_WdsSetupLogMessageW
0x180004d2e  xor     edi, edi
0x180004d30  test    r12, r12
0x180004d33  jnz     short loc_180004D40
0x180004d35  mov     r15d, edi
0x180004d38  mov     r14d, 80070057h
0x180004d3e  jmp     short loc_180004DBC
0x180004d40  mov     rcx, rsi; this
0x180004d43  mov     [r12], rdi
0x180004d47  call    ?FullBlockChecks@CSetupFilesCleanup@@QEAAKXZ; CSetupFilesCleanup::FullBlockChecks(void)
0x180004d4c  mov     r15d, eax
0x180004d4f  test    eax, eax
0x180004d51  jnz     short loc_180004DBC
0x180004d53  mov     rcx, [rsi+10h]
0x180004d57  lea     rax, [rsp+1C0h+var_158]
0x180004d5c  mov     [rbp+0C0h+var_108], rcx
0x180004d60  lea     r8, Name; "Global\\Microsoft.Windows.Setup.SetupCl"...
0x180004d67  mov     rcx, [rsi+50h]
0x180004d6b  lea     edx, [r15+1]; bInitialOwner
0x180004d6f  mov     [rbp+0C0h+var_E0], rcx
0x180004d73  xor     ecx, ecx; lpMutexAttributes
0x180004d75  mov     [rbp+0C0h+var_120], rdi
0x180004d79  mov     [rbp+0C0h+var_118], rdi
0x180004d7d  mov     [rbp+0C0h+var_110], rax
0x180004d81  mov     [rbp+0C0h+var_100], r13
0x180004d85  mov     [rbp+0C0h+var_F8], r12
0x180004d89  mov     [rbp+0C0h+var_D8], rdi
0x180004d8d  call    cs:__imp_CreateMutexW
0x180004d93  lea     rdx, [rbp+0C0h+var_120]; struct _SETUPCLN_PARAMS *
0x180004d97  mov     rcx, rsi; this
0x180004d9a  mov     rbx, rax
0x180004d9d  call    ?CleanVolume@CSetupFilesCleanup@@QEAAJPEAU_SETUPCLN_PARAMS@@@Z; CSetupFilesCleanup::CleanVolume(_SETUPCLN_PARAMS *)
0x180004da2  mov     r14d, eax
0x180004da5  test    rbx, rbx
0x180004da8  jz      short loc_180004DBC
0x180004daa  mov     rcx, rbx; hMutex
0x180004dad  call    cs:__imp_ReleaseMutex
0x180004db3  mov     rcx, rbx; hObject
0x180004db6  call    cs:__imp_CloseHandle
0x180004dbc  call    cs:__imp_GetLastError
0x180004dc2  mov     edi, eax
0x180004dc4  call    cs:__imp_CurrentIP
0x180004dca  mov     r8, [r12]
0x180004dce  lea     rdx, aCsetupfilescle_12; "CSetupFilesCleanup::GetSpaceUsed - Spac"...
0x180004dd5  mov     ecx, 4000000h; unsigned int
0x180004dda  mov     rbx, rax
0x180004ddd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004de2  xor     r13d, r13d
0x180004de5  lea     rcx, aCsetupfilescle_1; "CSetupFilesCleanup::GetSpaceUsed"
0x180004dec  mov     dword ptr [rsp+1C0h+var_170], r13d
0x180004df1  lea     r8, aD; "D"
0x180004df8  mov     [rsp+1C0h+var_178], r13
0x180004dfd  xor     r9d, r9d
0x180004e00  mov     dword ptr [rsp+1C0h+var_180], edi
0x180004e04  xor     edx, edx
0x180004e06  mov     [rsp+1C0h+var_188], rbx
0x180004e0b  mov     [rsp+1C0h+var_190], rcx
0x180004e10  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180004e17  mov     [rsp+1C0h+var_198], rcx
0x180004e1c  mov     rcx, rax
0x180004e1f  mov     dword ptr [rsp+1C0h+var_1A0], 236h
0x180004e27  call    cs:__imp_WdsSetupLogMessageW
0x180004e2d  call    cs:__imp_GetLastError
0x180004e33  mov     edi, eax
0x180004e35  call    cs:__imp_CurrentIP
0x180004e3b  mov     r8d, r15d
0x180004e3e  lea     rdx, aCsetupfilescle_18; "CSetupFilesCleanup::GetSpaceUsed - Bloc"...
0x180004e45  mov     ecx, 4000000h; unsigned int
0x180004e4a  mov     rbx, rax
0x180004e4d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004e52  mov     dword ptr [rsp+1C0h+var_170], r13d
0x180004e57  lea     rcx, aCsetupfilescle_1; "CSetupFilesCleanup::GetSpaceUsed"
0x180004e5e  mov     [rsp+1C0h+var_178], r13
0x180004e63  lea     r8, aD; "D"
0x180004e6a  mov     dword ptr [rsp+1C0h+var_180], edi
0x180004e6e  xor     r9d, r9d
0x180004e71  mov     [rsp+1C0h+var_188], rbx
0x180004e76  xor     edx, edx
0x180004e78  mov     [rsp+1C0h+var_190], rcx
0x180004e7d  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180004e84  mov     [rsp+1C0h+var_198], rcx
0x180004e89  mov     rcx, rax
0x180004e8c  mov     dword ptr [rsp+1C0h+var_1A0], 237h
0x180004e94  call    cs:__imp_WdsSetupLogMessageW
0x180004e9a  call    cs:__imp_GetLastError
0x180004ea0  mov     edi, eax
0x180004ea2  call    cs:__imp_CurrentIP
0x180004ea8  mov     r8d, r14d
0x180004eab  lea     rdx, aCsetupfilescle_6; "CSetupFilesCleanup::GetSpaceUsed - Retu"...
0x180004eb2  mov     ecx, 4000000h; unsigned int
0x180004eb7  mov     rbx, rax
0x180004eba  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004ebf  mov     dword ptr [rsp+1C0h+var_170], r13d
0x180004ec4  lea     rcx, aCsetupfilescle_1; "CSetupFilesCleanup::GetSpaceUsed"
0x180004ecb  mov     [rsp+1C0h+var_178], r13
0x180004ed0  lea     r8, aD; "D"
0x180004ed7  mov     dword ptr [rsp+1C0h+var_180], edi
0x180004edb  xor     r9d, r9d
0x180004ede  mov     [rsp+1C0h+var_188], rbx
0x180004ee3  xor     edx, edx
0x180004ee5  mov     [rsp+1C0h+var_190], rcx
0x180004eea  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180004ef1  mov     [rsp+1C0h+var_198], rcx
0x180004ef6  mov     rcx, rax
0x180004ef9  mov     dword ptr [rsp+1C0h+var_1A0], 238h
0x180004f01  call    cs:__imp_WdsSetupLogMessageW
0x180004f07  mov     eax, cs:dword_18001F018
0x180004f0d  cmp     [rsi+50h], r13
0x180004f11  jz      loc_180004FBF
0x180004f17  cmp     eax, 5
0x180004f1a  jbe     loc_180005040
0x180004f20  call    _tlgKeywordOn
0x180004f25  test    al, al
0x180004f27  jz      loc_180005040
0x180004f2d  mov     rdx, [rsi+50h]; struct TraceLoggingCorrelationVector *
0x180004f31  lea     rcx, [rbp+0C0h+var_D0]; this
0x180004f35  call    ??0_TlgCVGetter@@QEAA@PEAVTraceLoggingCorrelationVector@@@Z; _TlgCVGetter::_TlgCVGetter(TraceLoggingCorrelationVector *)
0x180004f3a  mov     [rbp+0C0h+var_130], rax
0x180004f3e  lea     rdx, word_18001B86A
0x180004f45  mov     rax, [r12]
0x180004f49  mov     [rsp+1C0h+var_150], rax
0x180004f4e  mov     rax, [rsi+40h]
0x180004f52  mov     [rsp+1C0h+var_148], rax
0x180004f57  mov     rax, [rsi+48h]
0x180004f5b  mov     [rbp+0C0h+var_140], rax
0x180004f5f  mov     eax, 80000000h
0x180004f64  mov     [rbp+0C0h+var_138], rax
0x180004f68  lea     rax, [rbp+0C0h+var_130]
0x180004f6c  mov     [rsp+1C0h+var_170], rax
0x180004f71  lea     rax, [rsp+1C0h+var_160]
0x180004f76  mov     [rsp+1C0h+var_178], rax
0x180004f7b  lea     rax, [rsp+1C0h+var_15C]
0x180004f80  mov     [rsp+1C0h+var_180], rax
0x180004f85  lea     rax, [rsp+1C0h+var_150]
0x180004f8a  mov     [rsp+1C0h+var_188], rax
0x180004f8f  lea     rax, [rsp+1C0h+var_148]
0x180004f94  mov     [rsp+1C0h+var_190], rax
0x180004f99  lea     rax, [rbp+0C0h+var_140]
0x180004f9d  mov     [rsp+1C0h+var_198], rax
0x180004fa2  lea     rax, [rbp+0C0h+var_138]
0x180004fa6  mov     [rsp+1C0h+var_1A0], rax
0x180004fab  mov     [rsp+1C0h+var_160], r14d
0x180004fb0  mov     [rsp+1C0h+var_15C], r15d
0x180004fb5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U1@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@43AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180004fba  jmp     loc_180005040
0x180004fbf  cmp     eax, 5
0x180004fc2  jbe     short loc_180005040
0x180004fc4  call    _tlgKeywordOn
0x180004fc9  test    al, al
0x180004fcb  jz      short loc_180005040
0x180004fcd  mov     rax, [r12]
0x180004fd1  lea     rdx, word_18001B7E6
0x180004fd8  mov     [rbp+0C0h+var_138], rax
0x180004fdc  mov     rax, [rsi+40h]
0x180004fe0  mov     [rbp+0C0h+var_140], rax
0x180004fe4  mov     rax, [rsi+48h]
0x180004fe8  mov     [rsp+1C0h+var_148], rax
0x180004fed  mov     eax, 80000000h
0x180004ff2  mov     [rsp+1C0h+var_150], rax
0x180004ff7  lea     rax, [rsp+1C0h+var_15C]
0x180004ffc  mov     [rsp+1C0h+var_178], rax
0x180005001  lea     rax, [rsp+1C0h+var_160]
0x180005006  mov     [rsp+1C0h+var_180], rax
0x18000500b  lea     rax, [rbp+0C0h+var_138]
0x18000500f  mov     [rsp+1C0h+var_188], rax
0x180005014  lea     rax, [rbp+0C0h+var_140]
0x180005018  mov     [rsp+1C0h+var_190], rax
0x18000501d  lea     rax, [rsp+1C0h+var_148]
0x180005022  mov     [rsp+1C0h+var_198], rax
0x180005027  lea     rax, [rsp+1C0h+var_150]
0x18000502c  mov     [rsp+1C0h+var_1A0], rax
0x180005031  mov     [rsp+1C0h+var_15C], r14d
0x180005036  mov     [rsp+1C0h+var_160], r15d
0x18000503b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@43AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180005040  mov     eax, r14d
0x180005043  mov     rcx, [rbp+0C0h+var_40]
0x18000504a  xor     rcx, rsp; StackCookie
0x18000504d  call    __security_check_cookie
0x180005052  mov     rbx, [rsp+1C0h+arg_18]
0x18000505a  add     rsp, 190h
0x180005061  pop     r15
0x180005063  pop     r14
0x180005065  pop     r13
0x180005067  pop     r12
0x180005069  pop     rdi
0x18000506a  pop     rsi
0x18000506b  pop     rbp
0x18000506c  retn
```

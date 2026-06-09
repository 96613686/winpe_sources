# SkpMedicLaunch

- ea: `0x14003a708`
- end: `0x14003aaa8`
- name: `SkpMedicLaunch`
- size: `928`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x14003a6a0`
- `0x140042dd0`

## callees

- `0x140001008`
- `0x14000160c`
- `0x14002330c`
- `0x140026494`
- `0x140038698`
- `0x14003a708`
- `0x140040038`
- `0x14004049c`
- `0x140042bc0`
- `0x1400575b0`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a983`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14003a979`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14003a979`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14003a7bb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14003a7bb`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14003a781`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14003a781`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a9f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a9fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a9f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a9fc`
- `RPCRT4!UuidCreate` at `0x14003a7c5`
- `RPCRT4!UuidCreate` at `0x14003a7c5`

## pseudocode

```c
__int64 __fastcall SkpMedicLaunch(int a1)
{
  __int64 v2; // rdx
  const char *v3; // r9
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  DWORD LastError; // ebx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  int Value; // [rsp+50h] [rbp-B0h] BYREF
  char *v18; // [rsp+58h] [rbp-A8h] BYREF
  UUID v19; // [rsp+60h] [rbp-A0h] BYREF
  ULONG_PTR Size; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _STARTUPINFOEXW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  UUID Uuid; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v24[3]; // [rsp+110h] [rbp+10h] BYREF
  _WORD v25[68]; // [rsp+140h] [rbp+40h] BYREF
  signed __int64 v26[6]; // [rsp+1C8h] [rbp+C8h] BYREF
  int v27; // [rsp+1F8h] [rbp+F8h]
  int v28; // [rsp+1FCh] [rbp+FCh]
  char v29[144]; // [rsp+200h] [rbp+100h] BYREF

  memset(&StartupInfo, 0, sizeof(StartupInfo));
  Size = 48;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  Uuid = 0;
  memset(v24, 0, sizeof(v24));
  InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v24, 1u, 0, &Size);
  Value = 2;
  UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v24, 0, 0x2000Bu, &Value, 4u, 0, 0);
  UuidCreate(&Uuid);
  *(_WORD *)((char *)&v25[64] + 1) = -32489;
  v19 = Uuid;
  v26[0] = 0x1900000000LL;
  memset(v25, 0, 0x81u);
  TLV::Base64Encode<129>(&v19, v2, v25);
  v25[11] = 46;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v25,
    _InterlockedExchangeAdd64(v26, 0),
    v29);
  v3 = "boot";
  if ( !a1 )
    v3 = "periodic";
  swprintf_s(Buffer, BufferCount, L" /launchtype %hs /cv %hs", v3, v29);
  ScInitStartupInfo(&StartupInfo, 0);
  StartupInfo.lpAttributeList = (LPPROC_THREAD_ATTRIBUTE_LIST)v24;
  if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v4) )
  {
    v18 = v29;
    *(_QWORD *)&v19.Data1 = P;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v5,
      (__int64)byte_1400AEE1D,
      v4,
      v6,
      &v19,
      &v18);
  }
  if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x800000000000LL, v4) )
  {
    *(_QWORD *)&v19.Data1 = v29;
    v18 = (char *)P;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v7,
      (__int64)&byte_1400AEDD7,
      v8,
      v9,
      &v18,
      &v19);
  }
  if ( CreateProcessW(0, P, 0, 0, 0, 0xC0000u, 0, 0, &StartupInfo.StartupInfo, &ProcessInformation) )
  {
    CloseHandle(ProcessInformation.hThread);
    CloseHandle(ProcessInformation.hProcess);
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x800000000000LL, v11) )
      {
        LODWORD(v18) = LastError;
        *(_QWORD *)&v19.Data1 = v29;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v12,
          (__int64)byte_1400AEDA1,
          v13,
          v14,
          (__int64)&v18,
          &v19);
      }
      return LastError;
    }
  }
  if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x800000000000LL, v11) )
  {
    v15 = -1;
    do
      ++v15;
    while ( v29[v15] );
    v28 = 0;
    v27 = v15 + 1;
    v26[5] = (signed __int64)v29;
    tlgWriteTransfer_EventWriteTransfer(&dword_1400BA2A0);
  }
  return LastError;
}

```

## disassembly

```asm
0x14003a708  mov     [rsp-8+arg_0], rbx
0x14003a70d  mov     [rsp-8+arg_8], rsi
0x14003a712  push    rbp
0x14003a713  lea     rbp, [rsp-1A0h]
0x14003a71b  sub     rsp, 2A0h
0x14003a722  mov     rax, cs:__security_cookie
0x14003a729  xor     rax, rsp
0x14003a72c  mov     [rbp+1A0h+var_10], rax
0x14003a733  xor     edx, edx; Val
0x14003a735  mov     ebx, ecx
0x14003a737  lea     rcx, [rbp+1A0h+StartupInfo]; void *
0x14003a73b  lea     r8d, [rdx+70h]; Size
0x14003a73f  call    memset
0x14003a744  xor     eax, eax
0x14003a746  mov     [rsp+2A0h+Size], 30h ; '0'
0x14003a74f  xorps   xmm1, xmm1
0x14003a752  mov     qword ptr [rbp+1A0h+ProcessInformation.dwProcessId], rax
0x14003a756  xorps   xmm0, xmm0
0x14003a759  mov     [rsp+2A0h+Value], eax
0x14003a75d  lea     r9, [rsp+2A0h+Size]; lpSize
0x14003a762  xor     r8d, r8d; dwFlags
0x14003a765  lea     edx, [rax+1]; dwAttributeCount
0x14003a768  lea     rcx, [rbp+1A0h+var_190]; lpAttributeList
0x14003a76c  movups  xmmword ptr [rsp+2A0h+ProcessInformation.hProcess], xmm0
0x14003a771  movups  xmmword ptr [rbp+1A0h+Uuid.Data1], xmm0
0x14003a775  movups  [rbp+1A0h+var_190], xmm1
0x14003a779  movups  [rbp+1A0h+var_180], xmm1
0x14003a77d  movups  [rbp+1A0h+var_170], xmm1
0x14003a781  call    cs:__imp_InitializeProcThreadAttributeList
0x14003a787  mov     [rsp+2A0h+lpReturnSize], 0; lpReturnSize
0x14003a790  lea     r9, [rsp+2A0h+Value]; lpValue
0x14003a795  mov     [rsp+2A0h+lpPreviousValue], 0; lpPreviousValue
0x14003a79e  lea     rcx, [rbp+1A0h+var_190]; lpAttributeList
0x14003a7a2  xor     edx, edx; dwFlags
0x14003a7a4  mov     [rsp+2A0h+cbSize], 4; cbSize
0x14003a7ad  mov     r8d, 2000Bh; Attribute
0x14003a7b3  mov     [rsp+2A0h+Value], 2
0x14003a7bb  call    cs:__imp_UpdateProcThreadAttribute
0x14003a7c1  lea     rcx, [rbp+1A0h+Uuid]; Uuid
0x14003a7c5  call    cs:__imp_UuidCreate
0x14003a7cb  movaps  xmm0, xmmword ptr [rbp+1A0h+Uuid.Data1]
0x14003a7cf  lea     rcx, [rbp+1A0h+var_160]; void *
0x14003a7d3  mov     rax, 1900000000h
0x14003a7dd  mov     [rbp+1A0h+var_DF], 8117h
0x14003a7e6  xor     edx, edx; Val
0x14003a7e8  movdqa  [rsp+2A0h+var_240], xmm0
0x14003a7ee  mov     r8d, 81h; Size
0x14003a7f4  mov     [rbp+1A0h+var_D8], rax
0x14003a7fb  call    memset
0x14003a800  lea     r8, [rbp+1A0h+var_160]
0x14003a804  lea     rcx, [rsp+2A0h+var_240]
0x14003a809  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x14003a80e  xor     edx, edx
0x14003a810  mov     [rbp+1A0h+var_14A], 2Eh ; '.'
0x14003a816  lock xadd [rbp+1A0h+var_D8], rdx; unsigned __int64
0x14003a81f  lea     r8, [rbp+1A0h+var_A0]; char *
0x14003a826  lea     rcx, [rbp+1A0h+var_160]; this
0x14003a82a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x14003a82f  mov     rdx, cs:BufferCount; BufferCount
0x14003a836  lea     rax, aPeriodic; "periodic"
0x14003a83d  mov     rcx, cs:Buffer; Buffer
0x14003a844  lea     r9, aBoot; "boot"
0x14003a84b  test    ebx, ebx
0x14003a84d  lea     r8, aLaunchtypeHsCv; " /launchtype %hs /cv %hs"
0x14003a854  cmovz   r9, rax
0x14003a858  lea     rax, [rbp+1A0h+var_A0]
0x14003a85f  mov     [rsp+2A0h+cbSize], rax
0x14003a864  call    swprintf_s
0x14003a869  xor     edx, edx; int
0x14003a86b  lea     rcx, [rbp+1A0h+StartupInfo]; struct _STARTUPINFOEXW *
0x14003a86f  call    ?ScInitStartupInfo@@YAXPEAU_STARTUPINFOEXW@@H@Z; ScInitStartupInfo(_STARTUPINFOEXW *,int)
0x14003a874  mov     eax, cs:dword_1400BA2A0
0x14003a87a  lea     rcx, [rbp+1A0h+var_190]
0x14003a87e  mov     [rbp+1A0h+var_1A8], rcx
0x14003a882  lea     rsi, dword_1400BA2A0
0x14003a889  cmp     eax, 5
0x14003a88c  jbe     short loc_14003A8DC
0x14003a88e  mov     rdx, 400000000000h
0x14003a898  mov     rcx, rsi
0x14003a89b  call    _tlgKeywordOn
0x14003a8a0  test    al, al
0x14003a8a2  jz      short loc_14003A8DC
0x14003a8a4  lea     rax, [rbp+1A0h+var_A0]
0x14003a8ab  mov     [rsp+2A0h+var_248], rax
0x14003a8b0  lea     rdx, byte_1400AEE1D
0x14003a8b7  mov     rax, cs:P
0x14003a8be  mov     qword ptr [rsp+2A0h+var_240], rax
0x14003a8c3  lea     rax, [rsp+2A0h+var_248]
0x14003a8c8  mov     [rsp+2A0h+lpPreviousValue], rax
0x14003a8cd  lea     rax, [rsp+2A0h+var_240]
0x14003a8d2  mov     [rsp+2A0h+cbSize], rax
0x14003a8d7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x14003a8dc  mov     eax, cs:dword_1400BA2A0
0x14003a8e2  cmp     eax, 5
0x14003a8e5  jbe     short loc_14003A935
0x14003a8e7  mov     rdx, 800000000000h
0x14003a8f1  mov     rcx, rsi
0x14003a8f4  call    _tlgKeywordOn
0x14003a8f9  test    al, al
0x14003a8fb  jz      short loc_14003A935
0x14003a8fd  lea     rax, [rbp+1A0h+var_A0]
0x14003a904  mov     qword ptr [rsp+2A0h+var_240], rax
0x14003a909  lea     rdx, byte_1400AEDD7
0x14003a910  mov     rax, cs:P
0x14003a917  mov     [rsp+2A0h+var_248], rax
0x14003a91c  lea     rax, [rsp+2A0h+var_240]
0x14003a921  mov     [rsp+2A0h+lpPreviousValue], rax
0x14003a926  lea     rax, [rsp+2A0h+var_248]
0x14003a92b  mov     [rsp+2A0h+cbSize], rax
0x14003a930  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x14003a935  mov     rdx, cs:P; lpCommandLine
0x14003a93c  lea     rax, [rsp+2A0h+ProcessInformation]
0x14003a941  mov     [rsp+2A0h+lpProcessInformation], rax; lpProcessInformation
0x14003a946  xor     r9d, r9d; lpThreadAttributes
0x14003a949  lea     rax, [rbp+1A0h+StartupInfo]
0x14003a94d  xor     r8d, r8d; lpProcessAttributes
0x14003a950  mov     [rsp+2A0h+lpStartupInfo], rax; lpStartupInfo
0x14003a955  xor     ecx, ecx; lpApplicationName
0x14003a957  mov     [rsp+2A0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14003a960  mov     [rsp+2A0h+lpReturnSize], 0; lpEnvironment
0x14003a969  mov     dword ptr [rsp+2A0h+lpPreviousValue], 0C0000h; dwCreationFlags
0x14003a971  mov     dword ptr [rsp+2A0h+cbSize], 0; bInheritHandles
0x14003a979  call    cs:__imp_CreateProcessW
0x14003a97f  test    eax, eax
0x14003a981  jnz     short loc_14003A9ED
0x14003a983  call    cs:__imp_GetLastError
0x14003a989  mov     ebx, eax
0x14003a98b  test    eax, eax
0x14003a98d  jz      short loc_14003AA04
0x14003a98f  mov     eax, cs:dword_1400BA2A0
0x14003a995  cmp     eax, 5
0x14003a998  jbe     loc_14003AA82
0x14003a99e  mov     rdx, 800000000000h
0x14003a9a8  mov     rcx, rsi
0x14003a9ab  call    _tlgKeywordOn
0x14003a9b0  test    al, al
0x14003a9b2  jz      loc_14003AA82
0x14003a9b8  lea     rax, [rbp+1A0h+var_A0]
0x14003a9bf  mov     dword ptr [rsp+2A0h+var_248], ebx
0x14003a9c3  mov     qword ptr [rsp+2A0h+var_240], rax
0x14003a9c8  lea     rdx, byte_1400AEDA1
0x14003a9cf  lea     rax, [rsp+2A0h+var_240]
0x14003a9d4  mov     [rsp+2A0h+lpPreviousValue], rax
0x14003a9d9  lea     rax, [rsp+2A0h+var_248]
0x14003a9de  mov     [rsp+2A0h+cbSize], rax
0x14003a9e3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14003a9e8  jmp     loc_14003AA82
0x14003a9ed  mov     rcx, [rbp+1A0h+ProcessInformation.hThread]; hObject
0x14003a9f1  call    cs:__imp_CloseHandle
0x14003a9f7  mov     rcx, [rsp+2A0h+ProcessInformation.hProcess]; hObject
0x14003a9fc  call    cs:__imp_CloseHandle
0x14003aa02  xor     ebx, ebx
0x14003aa04  mov     eax, cs:dword_1400BA2A0
0x14003aa0a  cmp     eax, 5
0x14003aa0d  jbe     short loc_14003AA82
0x14003aa0f  mov     rdx, 800000000000h
0x14003aa19  mov     rcx, rsi
0x14003aa1c  call    _tlgKeywordOn
0x14003aa21  test    al, al
0x14003aa23  jz      short loc_14003AA82
0x14003aa25  lea     rax, [rbp+1A0h+var_A0]
0x14003aa2c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14003aa30  inc     rcx
0x14003aa33  cmp     byte ptr [rax+rcx], 0
0x14003aa37  jnz     short loc_14003AA30
0x14003aa39  inc     ecx
0x14003aa3b  mov     [rbp+1A0h+var_A4], 0
0x14003aa45  lea     rax, [rbp+1A0h+var_A0]
0x14003aa4c  mov     [rbp+1A0h+var_A8], ecx
0x14003aa52  mov     [rbp+1A0h+var_B0], rax
0x14003aa59  lea     rdx, unk_1400AED70
0x14003aa60  lea     rax, [rbp+1A0h+var_D0]
0x14003aa67  xor     r9d, r9d
0x14003aa6a  mov     [rsp+2A0h+lpPreviousValue], rax
0x14003aa6f  xor     r8d, r8d
0x14003aa72  mov     rcx, rsi
0x14003aa75  mov     dword ptr [rsp+2A0h+cbSize], 3
0x14003aa7d  call    _tlgWriteTransfer_EventWriteTransfer
0x14003aa82  mov     eax, ebx
0x14003aa84  mov     rcx, [rbp+1A0h+var_10]
0x14003aa8b  xor     rcx, rsp; StackCookie
0x14003aa8e  call    __security_check_cookie
0x14003aa93  lea     r11, [rsp+2A0h+var_s0]
0x14003aa9b  mov     rbx, [r11+10h]
0x14003aa9f  mov     rsi, [r11+18h]
0x14003aaa3  mov     rsp, r11
0x14003aaa6  pop     rbp
0x14003aaa7  retn
```

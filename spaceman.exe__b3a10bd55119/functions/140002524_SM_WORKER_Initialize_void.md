# SM_WORKER::Initialize(void)

- ea: `0x140002524`
- end: `0x140002625`
- name: `?Initialize@SM_WORKER@@QEAAHXZ`
- size: `257`
- prototype: `__int64 __fastcall(PVOID pv, __int64, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400037dc`

## callees

- `0x140001008`
- `0x1400010b0`
- `0x140002524`
- `0x140009328`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140002589`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140002589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000259a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000259a`

## pseudocode

```c
__int64 __fastcall SM_WORKER::Initialize(PVOID pv, __int64 a2, int a3, int a4)
{
  unsigned int v5; // ebx
  PTP_WORK ThreadpoolWork; // rax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  DWORD LastError; // eax
  int v11; // r8d
  int v12; // r9d
  int v14; // [rsp+68h] [rbp+28h] BYREF
  const char *v15; // [rsp+70h] [rbp+30h] BYREF
  const char *v16; // [rsp+78h] [rbp+38h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v14 = 162;
    v15 = "SM_WORKER::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)pv,
      (unsigned int)word_140010AD2,
      a3,
      a4,
      (__int64)&v15,
      (__int64)&v14);
  }
  v5 = SuInitialize();
  if ( !v5 )
    goto LABEL_6;
  ThreadpoolWork = CreateThreadpoolWork(SM_WORKER::Callback, pv, 0);
  *((_QWORD *)pv + 7) = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    v5 = 0;
LABEL_6:
    LastError = GetLastError();
    if ( (unsigned int)dword_140014048 > 2 )
    {
      v14 = LastError;
      LODWORD(v15) = 183;
      v16 = "SM_WORKER::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_140014048,
        (unsigned int)byte_140010869,
        v11,
        v12,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
    return v5;
  }
  if ( (unsigned int)dword_140014048 > 5 )
  {
    v14 = 183;
    v15 = "SM_WORKER::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)&word_140010A1E,
      v8,
      v9,
      (__int64)&v15,
      (__int64)&v14);
  }
  return v5;
}

```

## disassembly

```asm
0x140002524  mov     [rsp-18h+arg_0], rbx
0x140002529  push    rbp
0x14000252a  push    rsi
0x14000252b  push    rdi
0x14000252c  mov     rbp, rsp
0x14000252f  sub     rsp, 40h
0x140002533  mov     eax, cs:dword_140014048
0x140002539  lea     rsi, aSmWorkerInitia; "SM_WORKER::Initialize"
0x140002540  mov     rdi, rcx
0x140002543  cmp     eax, 5
0x140002546  jbe     short loc_140002571
0x140002548  lea     rax, [rbp+arg_8]
0x14000254c  mov     [rbp+arg_8], 0A2h
0x140002553  mov     [rsp+40h+var_18], rax
0x140002558  lea     rdx, word_140010AD2
0x14000255f  lea     rax, [rbp+arg_10]
0x140002563  mov     [rbp+arg_10], rsi
0x140002567  mov     [rsp+40h+var_20], rax
0x14000256c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140002571  call    ?SuInitialize@@YAHXZ; SuInitialize(void)
0x140002576  mov     ebx, eax
0x140002578  test    eax, eax
0x14000257a  jz      short loc_14000259A
0x14000257c  xor     r8d, r8d; pcbe
0x14000257f  lea     rcx, ?Callback@SM_WORKER@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x140002586  mov     rdx, rdi; pv
0x140002589  call    cs:__imp_CreateThreadpoolWork
0x14000258f  mov     [rdi+38h], rax
0x140002593  test    rax, rax
0x140002596  jnz     short loc_1400025EF
0x140002598  xor     ebx, ebx
0x14000259a  call    cs:__imp_GetLastError
0x1400025a0  mov     ecx, cs:dword_140014048
0x1400025a6  cmp     ecx, 2
0x1400025a9  jbe     short loc_1400025E0
0x1400025ab  mov     [rbp+arg_8], eax
0x1400025ae  lea     rdx, byte_140010869
0x1400025b5  lea     rax, [rbp+arg_8]
0x1400025b9  mov     dword ptr [rbp+arg_10], 0B7h
0x1400025c0  mov     [rsp+40h+var_10], rax
0x1400025c5  lea     rax, [rbp+arg_10]
0x1400025c9  mov     [rsp+40h+var_18], rax
0x1400025ce  lea     rax, [rbp+arg_18]
0x1400025d2  mov     [rsp+40h+var_20], rax
0x1400025d7  mov     [rbp+arg_18], rsi
0x1400025db  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400025e0  mov     eax, ebx
0x1400025e2  mov     rbx, [rsp+40h+arg_0]
0x1400025e7  add     rsp, 40h
0x1400025eb  pop     rdi
0x1400025ec  pop     rsi
0x1400025ed  pop     rbp
0x1400025ee  retn
0x1400025ef  mov     eax, cs:dword_140014048
0x1400025f5  cmp     eax, 5
0x1400025f8  jbe     short loc_1400025E0
0x1400025fa  lea     rax, [rbp+arg_8]
0x1400025fe  mov     [rbp+arg_8], 0B7h
0x140002605  mov     [rsp+40h+var_18], rax
0x14000260a  lea     rdx, word_140010A1E
0x140002611  lea     rax, [rbp+arg_10]
0x140002615  mov     [rbp+arg_10], rsi
0x140002619  mov     [rsp+40h+var_20], rax
0x14000261e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140002623  jmp     short loc_1400025E0
```

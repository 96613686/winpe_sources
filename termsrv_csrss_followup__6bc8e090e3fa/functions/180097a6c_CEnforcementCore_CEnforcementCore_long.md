# CEnforcementCore::CEnforcementCore(long *)

- ea: `0x180097a6c`
- end: `0x180097ccd`
- name: `??0CEnforcementCore@@QEAA@PEAJ@Z`
- size: `609`
- prototype: `CEnforcementCore *__fastcall(CEnforcementCore *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180097ec0`

## callees

- `0x180005314`
- `0x18000542c`
- `0x180012210`
- `0x180027434`
- `0x18003ed60`
- `0x1800979d4`
- `0x180097a6c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180097b25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180097b25`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180097c35`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180097c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097c4d`

## string_xrefs

- `0x180097c73`: `CEnforcementCore constructor - FAILED to created event`

## pseudocode

```c
CEnforcementCore *__fastcall CEnforcementCore::CEnforcementCore(CEnforcementCore *this, int *a2)
{
  signed int v4; // ebx
  __int16 *v5; // rdx
  const char *v6; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  const char *v10; // [rsp+90h] [rbp+48h] BYREF
  const char *v11; // [rsp+98h] [rbp+50h] BYREF
  const char *v12; // [rsp+A0h] [rbp+58h] BYREF
  const char *v13; // [rsp+A8h] [rbp+60h] BYREF

  CTSPrivateObject<IEnforcementCore>::CTSPrivateObject<IEnforcementCore>();
  *(_QWORD *)this = &CEnforcementCore::`vftable';
  *((_QWORD *)this + 199) = 0;
  *((_QWORD *)this + 200) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_QWORD *)this + 203) = 0;
  *((_QWORD *)this + 204) = 0;
  *((_QWORD *)this + 205) = 0;
  *((_DWORD *)this + 436) = 0;
  *((_DWORD *)this + 462) = 0;
  *((_QWORD *)this + 234) = 0;
  *((_QWORD *)this + 232) = 0;
  *((_DWORD *)this + 466) = 0;
  *((_DWORD *)this + 470) = 0;
  CDefTSNotifySink::CDefTSNotifySink((CEnforcementCore *)((char *)this + 1888));
  *((_QWORD *)this + 236) = &CEnforcementCore::CSessionMonitor::`vftable';
  if ( !GetModuleHandleExW(6u, (LPCWSTR)IEnforcementCore::GetInstanceOfEnforcementCore, (HMODULE *)this + 232)
    && (unsigned int)dword_18012E170 > 2 )
  {
    v10 = "CEnforcementCore Constructor FAILED - Error in GetModuleHandleEx";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_18012E170,
      (unsigned int)byte_180119349,
      0,
      0,
      (__int64)&v10);
  }
  v4 = CResource::Initialize((CEnforcementCore *)((char *)this + 1648));
  if ( v4 >= 0 )
  {
    v4 = CResource::Initialize((CEnforcementCore *)((char *)this + 1752));
    if ( v4 < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_17;
      v11 = "CEnforcementCore";
      v5 = (__int16 *)byte_1801192CB;
      v6 = "MembersLock.Initialize";
      goto LABEL_7;
    }
    EventW = CreateEventW(0, 0, 1, 0);
    *((_QWORD *)this + 234) = EventW;
    if ( EventW )
    {
      *((_QWORD *)this + 435) = this;
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_18012E170 > 2 )
      {
        LODWORD(v10) = v4;
        v11 = "CEnforcementCore constructor - FAILED to created event";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18012E170,
          (unsigned int)byte_1801192A1,
          0,
          0,
          (__int64)&v11,
          (__int64)&v10);
      }
    }
  }
  else if ( (unsigned int)dword_18012E170 > 3 )
  {
    v11 = "CEnforcementCore";
    v5 = word_18011930A;
    v6 = "StartStopLock.Initialize";
LABEL_7:
    v12 = v6;
    LODWORD(v10) = v4;
    v13 = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)&dword_18012E170,
      (_DWORD)v5,
      0,
      0,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v10,
      (__int64)&v11);
  }
LABEL_17:
  *a2 = v4;
  return this;
}

```

## disassembly

```asm
0x180097a6c  push    rbp
0x180097a6e  push    rbx
0x180097a6f  push    rsi
0x180097a70  push    rdi
0x180097a71  push    r12
0x180097a73  push    r13
0x180097a75  push    r14
0x180097a77  push    r15
0x180097a79  mov     rbp, rsp
0x180097a7c  sub     rsp, 48h
0x180097a80  mov     r12, rdx
0x180097a83  mov     rsi, rcx
0x180097a86  call    ??0?$CTSPrivateObject@VIEnforcementCore@@@@QEAA@PEBD@Z; CTSPrivateObject<IEnforcementCore>::CTSPrivateObject<IEnforcementCore>(char const *)
0x180097a8b  xor     r13d, r13d
0x180097a8e  lea     rax, ??_7CEnforcementCore@@6B@; const CEnforcementCore::`vftable'
0x180097a95  mov     [rsi], rax
0x180097a98  lea     r14, [rsi+670h]
0x180097a9f  mov     [rsi+638h], r13
0x180097aa6  lea     r15, [rsi+6D8h]
0x180097aad  mov     [rsi+640h], r13
0x180097ab4  lea     rbx, [rsi+760h]
0x180097abb  mov     [rsi+648h], r13
0x180097ac2  lea     rdi, [rsi+740h]
0x180097ac9  mov     [rsi+650h], r13
0x180097ad0  mov     rcx, rbx; this
0x180097ad3  mov     [rsi+658h], r13
0x180097ada  mov     [rsi+660h], r13
0x180097ae1  mov     [rsi+668h], r13
0x180097ae8  mov     [r14+60h], r13d
0x180097aec  mov     [r15+60h], r13d
0x180097af0  mov     [rsi+750h], r13
0x180097af7  mov     [rdi], r13
0x180097afa  mov     [rsi+748h], r13d
0x180097b01  mov     [rsi+758h], r13d
0x180097b08  call    ??0CDefTSNotifySink@@QEAA@XZ; CDefTSNotifySink::CDefTSNotifySink(void)
0x180097b0d  lea     rax, ??_7CSessionMonitor@CEnforcementCore@@6B@; const CEnforcementCore::CSessionMonitor::`vftable'
0x180097b14  mov     r8, rdi; phModule
0x180097b17  lea     rdx, ?GetInstanceOfEnforcementCore@IEnforcementCore@@SAJPEAPEAV1@@Z; lpModuleName
0x180097b1e  mov     [rbx], rax
0x180097b21  lea     ecx, [r13+6]; dwFlags
0x180097b25  call    cs:__imp_GetModuleHandleExW
0x180097b2c  nop     dword ptr [rax+rax+00h]
0x180097b31  lea     rdi, dword_18012E170
0x180097b38  test    eax, eax
0x180097b3a  jnz     short loc_180097B70
0x180097b3c  mov     eax, cs:dword_18012E170
0x180097b42  cmp     eax, 2
0x180097b45  jbe     short loc_180097B70
0x180097b47  lea     rax, aCenforcementco_21; "CEnforcementCore Constructor FAILED - E"...
0x180097b4e  xor     r9d, r9d
0x180097b51  mov     [rbp+arg_0], rax
0x180097b55  lea     rdx, byte_180119349
0x180097b5c  lea     rax, [rbp+arg_0]
0x180097b60  xor     r8d, r8d
0x180097b63  mov     rcx, rdi
0x180097b66  mov     [rsp+48h+var_28], rax
0x180097b6b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180097b70  mov     rcx, r14; this
0x180097b73  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180097b78  mov     ebx, eax
0x180097b7a  test    eax, eax
0x180097b7c  jns     short loc_180097BEF
0x180097b7e  mov     ecx, cs:dword_18012E170
0x180097b84  cmp     ecx, 3
0x180097b87  jbe     loc_180097CB4
0x180097b8d  lea     rax, aCenforcementco_20; "CEnforcementCore"
0x180097b94  mov     [rbp+arg_8], rax
0x180097b98  lea     rdx, word_18011930A
0x180097b9f  lea     rax, aStartstoplockI_0; "StartStopLock.Initialize"
0x180097ba6  mov     [rbp+arg_10], rax
0x180097baa  xor     r9d, r9d
0x180097bad  lea     rax, aWarningHresult; "Warning HResult failed"
0x180097bb4  mov     dword ptr [rbp+arg_0], ebx
0x180097bb7  mov     [rbp+arg_18], rax
0x180097bbb  xor     r8d, r8d
0x180097bbe  lea     rax, [rbp+arg_8]
0x180097bc2  mov     rcx, rdi
0x180097bc5  mov     [rsp+48h+var_10], rax
0x180097bca  lea     rax, [rbp+arg_0]
0x180097bce  mov     [rsp+48h+var_18], rax
0x180097bd3  lea     rax, [rbp+arg_10]
0x180097bd7  mov     [rsp+48h+var_20], rax
0x180097bdc  lea     rax, [rbp+arg_18]
0x180097be0  mov     [rsp+48h+var_28], rax
0x180097be5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180097bea  jmp     loc_180097CB4
0x180097bef  mov     rcx, r15; this
0x180097bf2  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180097bf7  mov     ebx, eax
0x180097bf9  test    eax, eax
0x180097bfb  jns     short loc_180097C2A
0x180097bfd  mov     eax, cs:dword_18012E170
0x180097c03  cmp     eax, 3
0x180097c06  jbe     loc_180097CB4
0x180097c0c  lea     rax, aCenforcementco_20; "CEnforcementCore"
0x180097c13  mov     [rbp+arg_8], rax
0x180097c17  lea     rdx, byte_1801192CB
0x180097c1e  lea     rax, aMemberslockIni; "MembersLock.Initialize"
0x180097c25  jmp     loc_180097BA6
0x180097c2a  xor     r9d, r9d; lpName
0x180097c2d  xor     edx, edx; bManualReset
0x180097c2f  xor     ecx, ecx; lpEventAttributes
0x180097c31  lea     r8d, [r9+1]; bInitialState
0x180097c35  call    cs:__imp_CreateEventW
0x180097c3c  nop     dword ptr [rax+rax+00h]
0x180097c41  mov     [rsi+750h], rax
0x180097c48  test    rax, rax
0x180097c4b  jnz     short loc_180097CAA
0x180097c4d  call    cs:__imp_GetLastError
0x180097c54  nop     dword ptr [rax+rax+00h]
0x180097c59  mov     ebx, eax
0x180097c5b  test    eax, eax
0x180097c5d  jle     short loc_180097C68
0x180097c5f  movzx   ebx, ax
0x180097c62  or      ebx, 80070000h
0x180097c68  mov     eax, cs:dword_18012E170
0x180097c6e  cmp     eax, 2
0x180097c71  jbe     short loc_180097CB4
0x180097c73  lea     rax, aCenforcementco_11; "CEnforcementCore constructor - FAILED t"...
0x180097c7a  mov     dword ptr [rbp+arg_0], ebx
0x180097c7d  mov     [rbp+arg_8], rax
0x180097c81  lea     rdx, byte_1801192A1
0x180097c88  lea     rax, [rbp+arg_0]
0x180097c8c  xor     r9d, r9d
0x180097c8f  mov     [rsp+48h+var_20], rax
0x180097c94  xor     r8d, r8d
0x180097c97  lea     rax, [rbp+arg_8]
0x180097c9b  mov     rcx, rdi
0x180097c9e  mov     [rsp+48h+var_28], rax
0x180097ca3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180097ca8  jmp     short loc_180097CB4
0x180097caa  mov     [rsi+0D98h], rsi
0x180097cb1  mov     ebx, r13d
0x180097cb4  mov     [r12], ebx
0x180097cb8  mov     rax, rsi
0x180097cbb  add     rsp, 48h
0x180097cbf  pop     r15
0x180097cc1  pop     r14
0x180097cc3  pop     r13
0x180097cc5  pop     r12
0x180097cc7  pop     rdi
0x180097cc8  pop     rsi
0x180097cc9  pop     rbx
0x180097cca  pop     rbp
0x180097ccb  retn
```

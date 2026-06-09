# CEnforcementCore::CEnforcementCore(long *)

- ea: `0x180093a5c`
- end: `0x180093caa`
- name: `??0CEnforcementCore@@QEAA@PEAJ@Z`
- size: `590`
- prototype: `CEnforcementCore *__fastcall(CEnforcementCore *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180093e90`

## callees

- `0x1800052d0`
- `0x1800053e4`
- `0x180011a80`
- `0x180025fc4`
- `0x18003cb10`
- `0x1800939c4`
- `0x180093a5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180093b15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180093b15`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180093c1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180093c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c31`

## string_xrefs

- `0x180093c51`: `CEnforcementCore constructor - FAILED to created event`

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
    && (unsigned int)dword_180128170 > 2 )
  {
    v10 = "CEnforcementCore Constructor FAILED - Error in GetModuleHandleEx";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_180128170,
      (unsigned int)byte_1801132C9,
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
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_17;
      v11 = "CEnforcementCore";
      v5 = (__int16 *)byte_18011324B;
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
      if ( (unsigned int)dword_180128170 > 2 )
      {
        LODWORD(v10) = v4;
        v11 = "CEnforcementCore constructor - FAILED to created event";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180128170,
          (unsigned int)byte_180113221,
          0,
          0,
          (__int64)&v11,
          (__int64)&v10);
      }
    }
  }
  else if ( (unsigned int)dword_180128170 > 3 )
  {
    v11 = "CEnforcementCore";
    v5 = word_18011328A;
    v6 = "StartStopLock.Initialize";
LABEL_7:
    v12 = v6;
    LODWORD(v10) = v4;
    v13 = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)&dword_180128170,
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
0x180093a5c  push    rbp
0x180093a5e  push    rbx
0x180093a5f  push    rsi
0x180093a60  push    rdi
0x180093a61  push    r12
0x180093a63  push    r13
0x180093a65  push    r14
0x180093a67  push    r15
0x180093a69  mov     rbp, rsp
0x180093a6c  sub     rsp, 48h
0x180093a70  mov     r12, rdx
0x180093a73  mov     rsi, rcx
0x180093a76  call    ??0?$CTSPrivateObject@VIEnforcementCore@@@@QEAA@PEBD@Z; CTSPrivateObject<IEnforcementCore>::CTSPrivateObject<IEnforcementCore>(char const *)
0x180093a7b  xor     r13d, r13d
0x180093a7e  lea     rax, ??_7CEnforcementCore@@6B@; const CEnforcementCore::`vftable'
0x180093a85  mov     [rsi], rax
0x180093a88  lea     r14, [rsi+670h]
0x180093a8f  mov     [rsi+638h], r13
0x180093a96  lea     r15, [rsi+6D8h]
0x180093a9d  mov     [rsi+640h], r13
0x180093aa4  lea     rbx, [rsi+760h]
0x180093aab  mov     [rsi+648h], r13
0x180093ab2  lea     rdi, [rsi+740h]
0x180093ab9  mov     [rsi+650h], r13
0x180093ac0  mov     rcx, rbx; this
0x180093ac3  mov     [rsi+658h], r13
0x180093aca  mov     [rsi+660h], r13
0x180093ad1  mov     [rsi+668h], r13
0x180093ad8  mov     [r14+60h], r13d
0x180093adc  mov     [r15+60h], r13d
0x180093ae0  mov     [rsi+750h], r13
0x180093ae7  mov     [rdi], r13
0x180093aea  mov     [rsi+748h], r13d
0x180093af1  mov     [rsi+758h], r13d
0x180093af8  call    ??0CDefTSNotifySink@@QEAA@XZ; CDefTSNotifySink::CDefTSNotifySink(void)
0x180093afd  lea     rax, ??_7CSessionMonitor@CEnforcementCore@@6B@; const CEnforcementCore::CSessionMonitor::`vftable'
0x180093b04  mov     r8, rdi; phModule
0x180093b07  lea     rdx, ?GetInstanceOfEnforcementCore@IEnforcementCore@@SAJPEAPEAV1@@Z; lpModuleName
0x180093b0e  mov     [rbx], rax
0x180093b11  lea     ecx, [r13+6]; dwFlags
0x180093b15  call    cs:__imp_GetModuleHandleExW
0x180093b1b  lea     rdi, dword_180128170
0x180093b22  test    eax, eax
0x180093b24  jnz     short loc_180093B5A
0x180093b26  mov     eax, cs:dword_180128170
0x180093b2c  cmp     eax, 2
0x180093b2f  jbe     short loc_180093B5A
0x180093b31  lea     rax, aCenforcementco_21; "CEnforcementCore Constructor FAILED - E"...
0x180093b38  xor     r9d, r9d
0x180093b3b  mov     [rbp+arg_0], rax
0x180093b3f  lea     rdx, byte_1801132C9
0x180093b46  lea     rax, [rbp+arg_0]
0x180093b4a  xor     r8d, r8d
0x180093b4d  mov     rcx, rdi
0x180093b50  mov     [rsp+48h+var_28], rax
0x180093b55  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180093b5a  mov     rcx, r14; this
0x180093b5d  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180093b62  mov     ebx, eax
0x180093b64  test    eax, eax
0x180093b66  jns     short loc_180093BD9
0x180093b68  mov     ecx, cs:dword_180128170
0x180093b6e  cmp     ecx, 3
0x180093b71  jbe     loc_180093C92
0x180093b77  lea     rax, aCenforcementco_20; "CEnforcementCore"
0x180093b7e  mov     [rbp+arg_8], rax
0x180093b82  lea     rdx, word_18011328A
0x180093b89  lea     rax, aStartstoplockI_0; "StartStopLock.Initialize"
0x180093b90  mov     [rbp+arg_10], rax
0x180093b94  xor     r9d, r9d
0x180093b97  lea     rax, aWarningHresult; "Warning HResult failed"
0x180093b9e  mov     dword ptr [rbp+arg_0], ebx
0x180093ba1  mov     [rbp+arg_18], rax
0x180093ba5  xor     r8d, r8d
0x180093ba8  lea     rax, [rbp+arg_8]
0x180093bac  mov     rcx, rdi
0x180093baf  mov     [rsp+48h+var_10], rax
0x180093bb4  lea     rax, [rbp+arg_0]
0x180093bb8  mov     [rsp+48h+var_18], rax
0x180093bbd  lea     rax, [rbp+arg_10]
0x180093bc1  mov     [rsp+48h+var_20], rax
0x180093bc6  lea     rax, [rbp+arg_18]
0x180093bca  mov     [rsp+48h+var_28], rax
0x180093bcf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180093bd4  jmp     loc_180093C92
0x180093bd9  mov     rcx, r15; this
0x180093bdc  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180093be1  mov     ebx, eax
0x180093be3  test    eax, eax
0x180093be5  jns     short loc_180093C14
0x180093be7  mov     eax, cs:dword_180128170
0x180093bed  cmp     eax, 3
0x180093bf0  jbe     loc_180093C92
0x180093bf6  lea     rax, aCenforcementco_20; "CEnforcementCore"
0x180093bfd  mov     [rbp+arg_8], rax
0x180093c01  lea     rdx, byte_18011324B
0x180093c08  lea     rax, aMemberslockIni; "MembersLock.Initialize"
0x180093c0f  jmp     loc_180093B90
0x180093c14  xor     r9d, r9d; lpName
0x180093c17  xor     edx, edx; bManualReset
0x180093c19  xor     ecx, ecx; lpEventAttributes
0x180093c1b  lea     r8d, [r9+1]; bInitialState
0x180093c1f  call    cs:__imp_CreateEventW
0x180093c25  mov     [rsi+750h], rax
0x180093c2c  test    rax, rax
0x180093c2f  jnz     short loc_180093C88
0x180093c31  call    cs:__imp_GetLastError
0x180093c37  mov     ebx, eax
0x180093c39  test    eax, eax
0x180093c3b  jle     short loc_180093C46
0x180093c3d  movzx   ebx, ax
0x180093c40  or      ebx, 80070000h
0x180093c46  mov     eax, cs:dword_180128170
0x180093c4c  cmp     eax, 2
0x180093c4f  jbe     short loc_180093C92
0x180093c51  lea     rax, aCenforcementco_11; "CEnforcementCore constructor - FAILED t"...
0x180093c58  mov     dword ptr [rbp+arg_0], ebx
0x180093c5b  mov     [rbp+arg_8], rax
0x180093c5f  lea     rdx, byte_180113221
0x180093c66  lea     rax, [rbp+arg_0]
0x180093c6a  xor     r9d, r9d
0x180093c6d  mov     [rsp+48h+var_20], rax
0x180093c72  xor     r8d, r8d
0x180093c75  lea     rax, [rbp+arg_8]
0x180093c79  mov     rcx, rdi
0x180093c7c  mov     [rsp+48h+var_28], rax
0x180093c81  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180093c86  jmp     short loc_180093C92
0x180093c88  mov     [rsi+0D98h], rsi
0x180093c8f  mov     ebx, r13d
0x180093c92  mov     [r12], ebx
0x180093c96  mov     rax, rsi
0x180093c99  add     rsp, 48h
0x180093c9d  pop     r15
0x180093c9f  pop     r14
0x180093ca1  pop     r13
0x180093ca3  pop     r12
0x180093ca5  pop     rdi
0x180093ca6  pop     rsi
0x180093ca7  pop     rbx
0x180093ca8  pop     rbp
0x180093ca9  retn
```

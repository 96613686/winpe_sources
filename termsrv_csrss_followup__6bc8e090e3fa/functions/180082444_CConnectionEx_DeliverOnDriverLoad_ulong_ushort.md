# CConnectionEx::DeliverOnDriverLoad(ulong,ushort *)

- ea: `0x180082444`
- end: `0x180082746`
- name: `?DeliverOnDriverLoad@CConnectionEx@@AEAAJKPEAG@Z`
- size: `770`
- prototype: `int(CConnectionEx *__hidden this, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800885f8`

## callees

- `0x180001294`
- `0x1800016a8`
- `0x180015310`
- `0x180082444`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082479`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008263b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082479`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008263b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800824bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800824d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008266e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800824bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800824d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008266e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800825e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800825e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800825d0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800825d0`

## string_xrefs

- `0x18008255b`: `Failed to notify protocol stack about driver load`
- `0x1800826ec`: `Failed to notify protocol stack about driver load`
- `0x180082625`: `Fail to open Indirect Display device`

## pseudocode

```c
__int64 __fastcall CConnectionEx::DeliverOnDriverLoad(CConnectionEx *this, unsigned int a2, unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  char *v10; // rdx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  signed int v15; // ebx
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  char *v19; // rdx
  const char **v20; // rax
  HANDLE FileW; // r14
  signed int LastError; // eax
  const char *v23; // rax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  const char **dwFlagsAndAttributes; // [rsp+28h] [rbp-28h]
  const char *v28; // [rsp+40h] [rbp-10h] BYREF
  const char *v29; // [rsp+48h] [rbp-8h] BYREF
  const char *v30; // [rsp+70h] [rbp+20h] BYREF
  const char *v31; // [rsp+88h] [rbp+38h] BYREF

  if ( !*((_QWORD *)this + 204) )
  {
    v15 = -2147467261;
    if ( !*((_QWORD *)this + 203) )
      return (unsigned int)v15;
    FileW = CreateFileW(a3, 0x10000000u, 3u, 0, 4u, 0x800080u, 0);
    if ( FileW != (HANDLE)-1LL )
      goto LABEL_19;
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        return (unsigned int)v15;
      v31 = "DeliverOnDriverLoad";
      v19 = byte_180113C03;
      v23 = "Fail to open Indirect Display device";
    }
    else
    {
LABEL_19:
      v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1648);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1648));
      if ( *((_DWORD *)this + 4467) == 1 )
      {
        if ( (unsigned int)dword_18012E170 <= 2 )
          goto LABEL_6;
        v10 = &byte_180113BD7;
        goto LABEL_5;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1648));
      if ( (unsigned int)dword_18012E170 > 5 )
      {
        LODWORD(v30) = a2;
        v31 = "Calling OnDriverLoad";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)byte_180113BAB,
          v25,
          v26,
          (__int64)&v31,
          (__int64)&v30);
      }
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HANDLE))(**((_QWORD **)this + 203) + 32LL))(
              *((_QWORD *)this + 203),
              a2,
              FileW);
      if ( v15 >= 0 || (unsigned int)dword_18012E170 <= 3 )
        return (unsigned int)v15;
      v31 = "DeliverOnDriverLoad";
      v19 = byte_180113B65;
      v23 = "Failed to notify protocol stack about driver load";
    }
    v29 = v23;
    v28 = "Warning HResult failed";
    dwFlagsAndAttributes = &v29;
    v20 = &v28;
    goto LABEL_28;
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1648);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1648));
  if ( *((_DWORD *)this + 4467) == 1 )
  {
    if ( (unsigned int)dword_18012E170 <= 2 )
    {
LABEL_6:
      LeaveCriticalSection(v6);
      return 2147944650LL;
    }
    v10 = byte_180113CBB;
LABEL_5:
    v30 = "CConnectionEx::DeliverOnDriverLoad called after BrokenConnection was signaled. Returning ERROR_NOT_CONNECTED";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v7,
      (_DWORD)v10,
      v8,
      v9,
      (__int64)&v30);
    goto LABEL_6;
  }
  LeaveCriticalSection(v6);
  if ( (unsigned int)dword_18012E170 > 5 )
  {
    LODWORD(v30) = a2;
    v31 = "Calling OnDriverLoad";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)&byte_180113C8F,
      v13,
      v14,
      (__int64)&v31,
      (__int64)&v30);
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 204) + 32LL))(
          *((_QWORD *)this + 204),
          a2,
          a3);
  if ( v15 < 0 )
  {
    v18 = dword_18012E170;
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v31 = "DeliverOnDriverLoad";
      v19 = byte_180113C49;
      v28 = "Failed to notify protocol stack about driver load";
      v29 = "Warning HResult failed";
      dwFlagsAndAttributes = &v28;
      v20 = &v29;
LABEL_28:
      LODWORD(v30) = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v18,
        (_DWORD)v19,
        v16,
        v17,
        (__int64)v20,
        (__int64)dwFlagsAndAttributes,
        (__int64)&v30,
        (__int64)&v31);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180082444  mov     [rsp-18h+arg_8], rbx
0x180082449  mov     [rsp-18h+arg_10], rsi
0x18008244e  push    rbp
0x18008244f  push    rdi
0x180082450  push    r14
0x180082452  mov     rbp, rsp
0x180082455  sub     rsp, 50h
0x180082459  cmp     qword ptr [rcx+660h], 0
0x180082461  mov     r14, r8
0x180082464  mov     esi, edx
0x180082466  mov     rdi, rcx
0x180082469  jz      loc_180082595
0x18008246f  lea     rbx, [rcx+670h]
0x180082476  mov     rcx, rbx; lpCriticalSection
0x180082479  call    cs:__imp_EnterCriticalSection
0x180082480  nop     dword ptr [rax+rax+00h]
0x180082485  cmp     dword ptr [rdi+45CCh], 1
0x18008248c  jnz     short loc_1800824D2
0x18008248e  mov     eax, cs:dword_18012E170
0x180082494  cmp     eax, 2
0x180082497  jbe     short loc_1800824B9
0x180082499  lea     rdx, byte_180113CBB
0x1800824a0  lea     rax, aCconnectionexD; "CConnectionEx::DeliverOnDriverLoad call"...
0x1800824a7  mov     [rbp+arg_0], rax
0x1800824ab  lea     rax, [rbp+arg_0]
0x1800824af  mov     qword ptr [rsp+50h+dwCreationDisposition], rax
0x1800824b4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800824b9  mov     rcx, rbx; lpCriticalSection
0x1800824bc  call    cs:__imp_LeaveCriticalSection
0x1800824c3  nop     dword ptr [rax+rax+00h]
0x1800824c8  mov     eax, 800708CAh
0x1800824cd  jmp     loc_180082730
0x1800824d2  mov     rcx, rbx; lpCriticalSection
0x1800824d5  call    cs:__imp_LeaveCriticalSection
0x1800824dc  nop     dword ptr [rax+rax+00h]
0x1800824e1  mov     eax, cs:dword_18012E170
0x1800824e7  cmp     eax, 5
0x1800824ea  jbe     short loc_180082518
0x1800824ec  lea     rax, aCallingOndrive; "Calling OnDriverLoad"
0x1800824f3  mov     dword ptr [rbp+arg_0], esi
0x1800824f6  mov     [rbp+arg_18], rax
0x1800824fa  lea     rdx, byte_180113C8F
0x180082501  lea     rax, [rbp+arg_0]
0x180082505  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rax
0x18008250a  lea     rax, [rbp+arg_18]
0x18008250e  mov     qword ptr [rsp+50h+dwCreationDisposition], rax
0x180082513  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180082518  mov     rcx, [rdi+660h]
0x18008251f  mov     r8, r14
0x180082522  mov     edx, esi
0x180082524  mov     rax, [rcx]
0x180082527  mov     rax, [rax+20h]
0x18008252b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082530  mov     ebx, eax
0x180082532  test    eax, eax
0x180082534  jns     loc_18008272E
0x18008253a  mov     ecx, cs:dword_18012E170
0x180082540  cmp     ecx, 3
0x180082543  jbe     loc_18008272E
0x180082549  lea     rax, aDeliverondrive; "DeliverOnDriverLoad"
0x180082550  mov     [rbp+arg_18], rax
0x180082554  lea     rdx, byte_180113C49
0x18008255b  lea     rax, aFailedToNotify; "Failed to notify protocol stack about d"...
0x180082562  mov     [rbp+var_10], rax
0x180082566  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008256d  mov     [rbp+var_8], rax
0x180082571  lea     rax, [rbp+arg_18]
0x180082575  mov     [rsp+50h+var_18], rax
0x18008257a  lea     rax, [rbp+arg_0]
0x18008257e  mov     [rsp+50h+hTemplateFile], rax
0x180082583  lea     rax, [rbp+var_10]
0x180082587  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rax
0x18008258c  lea     rax, [rbp+var_8]
0x180082590  jmp     loc_180082721
0x180082595  cmp     qword ptr [rcx+658h], 0
0x18008259d  mov     ebx, 80004003h
0x1800825a2  jz      loc_18008272E
0x1800825a8  xor     r9d, r9d; lpSecurityAttributes
0x1800825ab  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x1800825b4  mov     [rsp+50h+dwFlagsAndAttributes], 800080h; dwFlagsAndAttributes
0x1800825bc  mov     edx, 10000000h; dwDesiredAccess
0x1800825c1  mov     rcx, r14; lpFileName
0x1800825c4  mov     [rsp+50h+dwCreationDisposition], 4; dwCreationDisposition
0x1800825cc  lea     r8d, [r9+3]; dwShareMode
0x1800825d0  call    cs:__imp_CreateFileW
0x1800825d7  nop     dword ptr [rax+rax+00h]
0x1800825dc  mov     r14, rax
0x1800825df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800825e3  jnz     short loc_180082631
0x1800825e5  call    cs:__imp_GetLastError
0x1800825ec  nop     dword ptr [rax+rax+00h]
0x1800825f1  mov     ebx, eax
0x1800825f3  test    eax, eax
0x1800825f5  jle     short loc_180082600
0x1800825f7  movzx   ebx, ax
0x1800825fa  or      ebx, 80070000h
0x180082600  test    ebx, ebx
0x180082602  jns     short loc_180082631
0x180082604  mov     eax, cs:dword_18012E170
0x18008260a  cmp     eax, 3
0x18008260d  jbe     loc_18008272E
0x180082613  lea     rax, aDeliverondrive; "DeliverOnDriverLoad"
0x18008261a  mov     [rbp+arg_18], rax
0x18008261e  lea     rdx, byte_180113C03
0x180082625  lea     rax, aFailToOpenIndi; "Fail to open Indirect Display device"
0x18008262c  jmp     loc_1800826F3
0x180082631  lea     rbx, [rdi+670h]
0x180082638  mov     rcx, rbx; lpCriticalSection
0x18008263b  call    cs:__imp_EnterCriticalSection
0x180082642  nop     dword ptr [rax+rax+00h]
0x180082647  cmp     dword ptr [rdi+45CCh], 1
0x18008264e  jnz     short loc_18008266B
0x180082650  mov     eax, cs:dword_18012E170
0x180082656  cmp     eax, 2
0x180082659  jbe     loc_1800824B9
0x18008265f  lea     rdx, byte_180113BD7
0x180082666  jmp     loc_1800824A0
0x18008266b  mov     rcx, rbx; lpCriticalSection
0x18008266e  call    cs:__imp_LeaveCriticalSection
0x180082675  nop     dword ptr [rax+rax+00h]
0x18008267a  mov     eax, cs:dword_18012E170
0x180082680  cmp     eax, 5
0x180082683  jbe     short loc_1800826B1
0x180082685  lea     rax, aCallingOndrive; "Calling OnDriverLoad"
0x18008268c  mov     dword ptr [rbp+arg_0], esi
0x18008268f  mov     [rbp+arg_18], rax
0x180082693  lea     rdx, byte_180113BAB
0x18008269a  lea     rax, [rbp+arg_0]
0x18008269e  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rax
0x1800826a3  lea     rax, [rbp+arg_18]
0x1800826a7  mov     qword ptr [rsp+50h+dwCreationDisposition], rax
0x1800826ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800826b1  mov     rcx, [rdi+658h]
0x1800826b8  mov     r8, r14
0x1800826bb  mov     edx, esi
0x1800826bd  mov     rax, [rcx]
0x1800826c0  mov     rax, [rax+20h]
0x1800826c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800826c9  mov     ebx, eax
0x1800826cb  test    eax, eax
0x1800826cd  jns     short loc_18008272E
0x1800826cf  mov     eax, cs:dword_18012E170
0x1800826d5  cmp     eax, 3
0x1800826d8  jbe     short loc_18008272E
0x1800826da  lea     rax, aDeliverondrive; "DeliverOnDriverLoad"
0x1800826e1  mov     [rbp+arg_18], rax
0x1800826e5  lea     rdx, byte_180113B65
0x1800826ec  lea     rax, aFailedToNotify; "Failed to notify protocol stack about d"...
0x1800826f3  mov     [rbp+var_8], rax
0x1800826f7  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800826fe  mov     [rbp+var_10], rax
0x180082702  lea     rax, [rbp+arg_18]
0x180082706  mov     [rsp+50h+var_18], rax
0x18008270b  lea     rax, [rbp+arg_0]
0x18008270f  mov     [rsp+50h+hTemplateFile], rax
0x180082714  lea     rax, [rbp+var_8]
0x180082718  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rax
0x18008271d  lea     rax, [rbp+var_10]
0x180082721  mov     qword ptr [rsp+50h+dwCreationDisposition], rax
0x180082726  mov     dword ptr [rbp+arg_0], ebx
0x180082729  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008272e  mov     eax, ebx
0x180082730  lea     r11, [rsp+50h+var_s0]
0x180082735  mov     rbx, [r11+28h]
0x180082739  mov     rsi, [r11+30h]
0x18008273d  mov     rsp, r11
0x180082740  pop     r14
0x180082742  pop     rdi
0x180082743  pop     rbp
0x180082744  retn
```

# CConnectionEx::DeliverOnDriverLoad(ulong,ushort *)

- ea: `0x18007ed04`
- end: `0x18007efdb`
- name: `?DeliverOnDriverLoad@CConnectionEx@@AEAAJKPEAG@Z`
- size: `727`
- prototype: `__int64 __fastcall(CConnectionEx *this, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180084d34`

## callees

- `0x180001284`
- `0x180001688`
- `0x1800148f0`
- `0x18007ed04`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ed39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007eedd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ed39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007eedd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ed76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ed89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ef0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ed76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ed89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ef0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ee8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ee8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007ee7e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007ee7e`

## string_xrefs

- `0x18007ee09`: `Failed to notify protocol stack about driver load`
- `0x18007ef82`: `Failed to notify protocol stack about driver load`
- `0x18007eec7`: `Fail to open Indirect Display device`

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
      if ( (unsigned int)dword_180128170 <= 3 )
        return (unsigned int)v15;
      v31 = "DeliverOnDriverLoad";
      v19 = byte_18010DB83;
      v23 = "Fail to open Indirect Display device";
    }
    else
    {
LABEL_19:
      v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1648);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1648));
      if ( *((_DWORD *)this + 4467) == 1 )
      {
        if ( (unsigned int)dword_180128170 <= 2 )
          goto LABEL_6;
        v10 = &byte_18010DB57;
        goto LABEL_5;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1648));
      if ( (unsigned int)dword_180128170 > 5 )
      {
        LODWORD(v30) = a2;
        v31 = "Calling OnDriverLoad";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)byte_18010DB2B,
          v25,
          v26,
          (__int64)&v31,
          (__int64)&v30);
      }
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HANDLE))(**((_QWORD **)this + 203) + 32LL))(
              *((_QWORD *)this + 203),
              a2,
              FileW);
      if ( v15 >= 0 || (unsigned int)dword_180128170 <= 3 )
        return (unsigned int)v15;
      v31 = "DeliverOnDriverLoad";
      v19 = byte_18010DAE5;
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
    if ( (unsigned int)dword_180128170 <= 2 )
    {
LABEL_6:
      LeaveCriticalSection(v6);
      return 2147944650LL;
    }
    v10 = byte_18010DC3B;
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
  if ( (unsigned int)dword_180128170 > 5 )
  {
    LODWORD(v30) = a2;
    v31 = "Calling OnDriverLoad";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)&byte_18010DC0F,
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
    v18 = dword_180128170;
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v31 = "DeliverOnDriverLoad";
      v19 = byte_18010DBC9;
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
0x18007ed04  mov     [rsp-18h+arg_8], rbx
0x18007ed09  mov     [rsp-18h+arg_10], rsi
0x18007ed0e  push    rbp
0x18007ed0f  push    rdi
0x18007ed10  push    r14
0x18007ed12  mov     rbp, rsp
0x18007ed15  sub     rsp, 50h
0x18007ed19  cmp     qword ptr [rcx+660h], 0
0x18007ed21  mov     r14, r8
0x18007ed24  mov     esi, edx
0x18007ed26  mov     rdi, rcx
0x18007ed29  jz      loc_18007EE43
0x18007ed2f  lea     rbx, [rcx+670h]
0x18007ed36  mov     rcx, rbx; lpCriticalSection
0x18007ed39  call    cs:__imp_EnterCriticalSection
0x18007ed3f  cmp     dword ptr [rdi+45CCh], 1
0x18007ed46  jnz     short loc_18007ED86
0x18007ed48  mov     eax, cs:dword_180128170
0x18007ed4e  cmp     eax, 2
0x18007ed51  jbe     short loc_18007ED73
0x18007ed53  lea     rdx, byte_18010DC3B
0x18007ed5a  lea     rax, aCconnectionexD; "CConnectionEx::DeliverOnDriverLoad call"...
0x18007ed61  mov     [rbp+arg_0], rax
0x18007ed65  lea     rax, [rbp+arg_0]
0x18007ed69  mov     qword ptr [rsp+50h+dwCreationDisposition], rax
0x18007ed6e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007ed73  mov     rcx, rbx; lpCriticalSection
0x18007ed76  call    cs:__imp_LeaveCriticalSection
0x18007ed7c  mov     eax, 800708CAh
0x18007ed81  jmp     loc_18007EFC6
0x18007ed86  mov     rcx, rbx; lpCriticalSection
0x18007ed89  call    cs:__imp_LeaveCriticalSection
0x18007ed8f  mov     eax, cs:dword_180128170
0x18007ed95  cmp     eax, 5
0x18007ed98  jbe     short loc_18007EDC6
0x18007ed9a  lea     rax, aCallingOndrive; "Calling OnDriverLoad"
0x18007eda1  mov     dword ptr [rbp+arg_0], esi
0x18007eda4  mov     [rbp+arg_18], rax
0x18007eda8  lea     rdx, byte_18010DC0F
0x18007edaf  lea     rax, [rbp+arg_0]
0x18007edb3  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rax
0x18007edb8  lea     rax, [rbp+arg_18]
0x18007edbc  mov     qword ptr [rsp+50h+dwCreationDisposition], rax
0x18007edc1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007edc6  mov     rcx, [rdi+660h]
0x18007edcd  mov     r8, r14
0x18007edd0  mov     edx, esi
0x18007edd2  mov     rax, [rcx]
0x18007edd5  mov     rax, [rax+20h]
0x18007edd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007edde  mov     ebx, eax
0x18007ede0  test    eax, eax
0x18007ede2  jns     loc_18007EFC4
0x18007ede8  mov     ecx, cs:dword_180128170
0x18007edee  cmp     ecx, 3
0x18007edf1  jbe     loc_18007EFC4
0x18007edf7  lea     rax, aDeliverondrive; "DeliverOnDriverLoad"
0x18007edfe  mov     [rbp+arg_18], rax
0x18007ee02  lea     rdx, byte_18010DBC9
0x18007ee09  lea     rax, aFailedToNotify; "Failed to notify protocol stack about d"...
0x18007ee10  mov     [rbp+var_10], rax
0x18007ee14  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007ee1b  mov     [rbp+var_8], rax
0x18007ee1f  lea     rax, [rbp+arg_18]
0x18007ee23  mov     [rsp+50h+var_18], rax
0x18007ee28  lea     rax, [rbp+arg_0]
0x18007ee2c  mov     [rsp+50h+hTemplateFile], rax
0x18007ee31  lea     rax, [rbp+var_10]
0x18007ee35  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rax
0x18007ee3a  lea     rax, [rbp+var_8]
0x18007ee3e  jmp     loc_18007EFB7
0x18007ee43  cmp     qword ptr [rcx+658h], 0
0x18007ee4b  mov     ebx, 80004003h
0x18007ee50  jz      loc_18007EFC4
0x18007ee56  xor     r9d, r9d; lpSecurityAttributes
0x18007ee59  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x18007ee62  mov     [rsp+50h+dwFlagsAndAttributes], 800080h; dwFlagsAndAttributes
0x18007ee6a  mov     edx, 10000000h; dwDesiredAccess
0x18007ee6f  mov     rcx, r14; lpFileName
0x18007ee72  mov     [rsp+50h+dwCreationDisposition], 4; dwCreationDisposition
0x18007ee7a  lea     r8d, [r9+3]; dwShareMode
0x18007ee7e  call    cs:__imp_CreateFileW
0x18007ee84  mov     r14, rax
0x18007ee87  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007ee8b  jnz     short loc_18007EED3
0x18007ee8d  call    cs:__imp_GetLastError
0x18007ee93  mov     ebx, eax
0x18007ee95  test    eax, eax
0x18007ee97  jle     short loc_18007EEA2
0x18007ee99  movzx   ebx, ax
0x18007ee9c  or      ebx, 80070000h
0x18007eea2  test    ebx, ebx
0x18007eea4  jns     short loc_18007EED3
0x18007eea6  mov     eax, cs:dword_180128170
0x18007eeac  cmp     eax, 3
0x18007eeaf  jbe     loc_18007EFC4
0x18007eeb5  lea     rax, aDeliverondrive; "DeliverOnDriverLoad"
0x18007eebc  mov     [rbp+arg_18], rax
0x18007eec0  lea     rdx, byte_18010DB83
0x18007eec7  lea     rax, aFailToOpenIndi; "Fail to open Indirect Display device"
0x18007eece  jmp     loc_18007EF89
0x18007eed3  lea     rbx, [rdi+670h]
0x18007eeda  mov     rcx, rbx; lpCriticalSection
0x18007eedd  call    cs:__imp_EnterCriticalSection
0x18007eee3  cmp     dword ptr [rdi+45CCh], 1
0x18007eeea  jnz     short loc_18007EF07
0x18007eeec  mov     eax, cs:dword_180128170
0x18007eef2  cmp     eax, 2
0x18007eef5  jbe     loc_18007ED73
0x18007eefb  lea     rdx, byte_18010DB57
0x18007ef02  jmp     loc_18007ED5A
0x18007ef07  mov     rcx, rbx; lpCriticalSection
0x18007ef0a  call    cs:__imp_LeaveCriticalSection
0x18007ef10  mov     eax, cs:dword_180128170
0x18007ef16  cmp     eax, 5
0x18007ef19  jbe     short loc_18007EF47
0x18007ef1b  lea     rax, aCallingOndrive; "Calling OnDriverLoad"
0x18007ef22  mov     dword ptr [rbp+arg_0], esi
0x18007ef25  mov     [rbp+arg_18], rax
0x18007ef29  lea     rdx, byte_18010DB2B
0x18007ef30  lea     rax, [rbp+arg_0]
0x18007ef34  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rax
0x18007ef39  lea     rax, [rbp+arg_18]
0x18007ef3d  mov     qword ptr [rsp+50h+dwCreationDisposition], rax
0x18007ef42  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007ef47  mov     rcx, [rdi+658h]
0x18007ef4e  mov     r8, r14
0x18007ef51  mov     edx, esi
0x18007ef53  mov     rax, [rcx]
0x18007ef56  mov     rax, [rax+20h]
0x18007ef5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ef5f  mov     ebx, eax
0x18007ef61  test    eax, eax
0x18007ef63  jns     short loc_18007EFC4
0x18007ef65  mov     eax, cs:dword_180128170
0x18007ef6b  cmp     eax, 3
0x18007ef6e  jbe     short loc_18007EFC4
0x18007ef70  lea     rax, aDeliverondrive; "DeliverOnDriverLoad"
0x18007ef77  mov     [rbp+arg_18], rax
0x18007ef7b  lea     rdx, byte_18010DAE5
0x18007ef82  lea     rax, aFailedToNotify; "Failed to notify protocol stack about d"...
0x18007ef89  mov     [rbp+var_8], rax
0x18007ef8d  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007ef94  mov     [rbp+var_10], rax
0x18007ef98  lea     rax, [rbp+arg_18]
0x18007ef9c  mov     [rsp+50h+var_18], rax
0x18007efa1  lea     rax, [rbp+arg_0]
0x18007efa5  mov     [rsp+50h+hTemplateFile], rax
0x18007efaa  lea     rax, [rbp+var_8]
0x18007efae  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rax
0x18007efb3  lea     rax, [rbp+var_10]
0x18007efb7  mov     qword ptr [rsp+50h+dwCreationDisposition], rax
0x18007efbc  mov     dword ptr [rbp+arg_0], ebx
0x18007efbf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007efc4  mov     eax, ebx
0x18007efc6  lea     r11, [rsp+50h+var_s0]
0x18007efcb  mov     rbx, [r11+28h]
0x18007efcf  mov     rsi, [r11+30h]
0x18007efd3  mov     rsp, r11
0x18007efd6  pop     r14
0x18007efd8  pop     rdi
0x18007efd9  pop     rbp
0x18007efda  retn
```

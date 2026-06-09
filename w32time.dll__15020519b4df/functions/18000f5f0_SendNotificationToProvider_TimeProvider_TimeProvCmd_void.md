# SendNotificationToProvider(TimeProvider *,TimeProvCmd,void *)

- ea: `0x18000f5f0`
- end: `0x18000fad7`
- name: `?SendNotificationToProvider@@YAJPEAUTimeProvider@@W4TimeProvCmd@@PEAX@Z`
- size: `1255`
- prototype: `__int64 __fastcall(struct TimeProvider *, enum TimeProvCmd, void *)`
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180006930`
- `0x18000ec50`
- `0x18000ee90`
- `0x18000fae0`
- `0x1800103a0`
- `0x180032ff0`
- `0x1800376c0`
- `0x18004c890`

## callees

- `0x18000a7e0`
- `0x18000f5f0`
- `0x180018138`
- `0x18001d9a0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f63e`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f695`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f6a8`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f6c8`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f63e`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f695`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f6a8`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f6c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f8d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f947`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fac6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f8d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f947`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fac6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f664`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f664`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f70c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f70c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8ea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f75a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f7c9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f75a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f7c9`
- `ntdll!RtlInitUnicodeString` at `0x18000f843`
- `ntdll!RtlInitUnicodeString` at `0x18000f857`
- `ntdll!RtlInitUnicodeString` at `0x18000f843`
- `ntdll!RtlInitUnicodeString` at `0x18000f857`

## string_xrefs

- `0x18000f882`: `Logging warning: The time provider '%s' returned an error while updating its configuration. The error will be ignored. The error was: %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall SendNotificationToProvider(struct TimeProvider *a1, enum TimeProvCmd a2, void *a3)
{
  enum TimeProvCmd v4; // r12d
  struct TimeProvider *v5; // rdi
  WCHAR *v6; // r15
  _DWORD *v7; // rbx
  __int64 result; // rax
  __int64 v9; // rax
  signed int LastError; // eax
  signed int v11; // r14d
  unsigned int v12; // eax
  char v13; // [rsp+40h] [rbp-D8h]
  signed int v14; // [rsp+44h] [rbp-D4h]
  WCHAR *v15; // [rsp+48h] [rbp-D0h]
  WCHAR Buffer[8]; // [rsp+58h] [rbp-C0h] BYREF
  va_list Arguments[2]; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+78h] [rbp-A0h]
  _BYTE v19[24]; // [rsp+80h] [rbp-98h] BYREF
  int v20; // [rsp+98h] [rbp-80h]
  _BYTE v21[24]; // [rsp+A0h] [rbp-78h] BYREF
  _BYTE v22[24]; // [rsp+C0h] [rbp-58h] BYREF
  _BYTE v23[64]; // [rsp+D8h] [rbp-40h] BYREF
  struct TimeProvider *lpBuffer; // [rsp+120h] [rbp+8h] BYREF
  enum TimeProvCmd v25; // [rsp+128h] [rbp+10h]
  char *v26; // [rsp+138h] [rbp+20h]

  v25 = a2;
  lpBuffer = a1;
  v4 = a2;
  v5 = a1;
  v13 = 0;
  v6 = 0;
  v15 = 0;
  v7 = (_DWORD *)((char *)a1 + 72);
  v26 = (char *)a1 + 72;
  ++*((_DWORD *)a1 + 18);
  *(_QWORD *)Buffer = _set_se_translator(SeTransFunc);
  try
  {
    if ( *((_BYTE *)v5 + 18) )
    {
      LeaveCriticalSection(&CriticalSection);
      v13 = 1;
      v14 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, void *))v5 + 6))(*((_QWORD *)v5 + 5), (unsigned int)v4, a3);
    }
    else
    {
      v14 = -2147023834;
    }
  }
  catch ( SeException v19 )
  {
    v12 = v20;
    if ( v20 > 0 )
      v12 = (unsigned __int16)v20 | 0x80070000;
    v14 = v12;
    SeException::~SeException((SeException *)v19);
    v4 = v25;
    v5 = lpBuffer;
    v6 = 0;
    v7 = v26;
  }
  catch ( std::bad_alloc v22 )
  {
    v14 = -2147024882;
    SeException::~SeException((SeException *)v22);
    v4 = v25;
    v5 = lpBuffer;
    v6 = 0;
    v7 = v26;
  }
  catch ( ... )
  {
    v14 = -2147418113;
    v4 = v25;
    v5 = lpBuffer;
    v6 = 0;
    v7 = v26;
  }
  _set_se_translator(*(_QWORD *)Buffer);
  v18 = _set_se_translator(SeTransFunc);
  try
  {
    if ( v14 >= 0 )
      goto LABEL_65;
    Arguments[0] = 0;
    Arguments[1] = (va_list)v14;
    *(_QWORD *)Buffer = 0;
    lpBuffer = 0;
    v6 = 0;
    v15 = 0;
    if ( FormatMessageW(0x1100u, 0, v14, 0, Buffer, 0, 0) )
    {
      Arguments[0] = *(va_list *)Buffer;
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v9) );
      if ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v9 - 4) == 13 )
        *(_WORD *)(*(_QWORD *)Buffer + 2 * v9 - 4) = 0;
    }
    else
    {
      if ( GetLastError() != 317 )
        goto LABEL_18;
      Arguments[0] = (va_list)&qword_180071478;
    }
    if ( FormatMessageW(0x2500u, L"%1 (0x%2!08X!)", 0, 0, (LPWSTR)&lpBuffer, 0, Arguments) )
    {
      v6 = (WCHAR *)lpBuffer;
      v15 = (WCHAR *)lpBuffer;
      lpBuffer = 0;
      v11 = 0;
LABEL_20:
      if ( *(_QWORD *)Buffer )
        LocalFree(*(HLOCAL *)Buffer);
      if ( lpBuffer )
        LocalFree(lpBuffer);
      if ( v11 >= 0 )
      {
        *(_OWORD *)Arguments = 0;
        *(_OWORD *)Buffer = 0;
        RtlInitUnicodeString((PUNICODE_STRING)Arguments, *((PCWSTR *)v5 + 1));
        RtlInitUnicodeString((PUNICODE_STRING)Buffer, v6);
        if ( v4 == TPC_UpdateConfig )
        {
          if ( (unsigned __int8)FileLogAllowEntry(9) )
            FileLogAdd(
              L"Logging warning: The time provider '%s' returned an error while updating its configuration. The error will"
               " be ignored. The error was: %s\n",
              *((_QWORD *)v5 + 1),
              v6);
          LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIMEPROV_FAILED_UPDATE, L"uu", Arguments);
        }
        else if ( v4 == TPC_PollIntervalChanged )
        {
          if ( (unsigned __int8)FileLogAllowEntry(9) )
            FileLogAdd(
              L"Logging warning: The time provider '%s' returned an error when notified of a polling interval change. The "
               "error will be ignored. The error was: %s\n",
              *((_QWORD *)v5 + 1),
              v6);
          LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIMEPROV_FAILED_POLLUPDATE, L"uu", Arguments);
        }
        else if ( v4 )
        {
          if ( v4 == TPC_NetTopoChange )
          {
            if ( (unsigned __int8)FileLogAllowEntry(9) )
              FileLogAdd(
                L"Logging warning: The time provider '%s' returned an error when notified of a net topography change. The "
                 "error will be ignored. The error was: %s\n",
                *((_QWORD *)v5 + 1),
                v6);
            LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIMEPROV_FAILED_NETTOPOCHANGE, L"uu", Arguments);
          }
          else if ( v4 == TPC_GetSamples )
          {
            if ( (unsigned __int8)FileLogAllowEntry(9) )
              FileLogAdd(
                L"Logging warning: The time provider '%s' returned an error when notified of a get sample. The error will "
                 "be ignored. The error was: %s\n",
                *((_QWORD *)v5 + 1),
                v6);
          }
          else if ( v4 == TPC_Query && (unsigned __int8)FileLogAllowEntry(9) )
          {
            FileLogAdd(
              L"Logging warning: The time provider '%s' returned an error when querying information. The error will be ign"
               "ored. The error was: %s\n",
              *((_QWORD *)v5 + 1),
              v6);
          }
        }
        else
        {
          if ( (unsigned __int8)FileLogAllowEntry(9) )
            FileLogAdd(
              L"Logging warning: The time provider '%s' returned an error when notified of a time jump. The error will be "
               "ignored. The error was: %s\n",
              *((_QWORD *)v5 + 1),
              v6);
          LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIMEPROV_FAILED_TIMEJUMP, L"uu", Arguments);
        }
      }
      goto LABEL_65;
    }
LABEL_18:
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_20;
  }
  catch ( SeException v21 )
  {
    SeException::~SeException((SeException *)v21);
    v6 = v15;
    v7 = v26;
  }
  catch ( std::bad_alloc v23 )
  {
    SeException::~SeException((SeException *)v23);
    v6 = v15;
    v7 = v26;
  }
  catch ( ... )
  {
    v6 = v15;
    v7 = v26;
  }
LABEL_65:
  _set_se_translator(v18);
  if ( v6 )
    LocalFree(v6);
  if ( v13 )
    EnterCriticalSection(&CriticalSection);
  result = (unsigned int)v14;
  --*v7;
  return result;
}

```

## disassembly

```asm
0x18000f5f0  mov     [rsp+arg_10], rbx
0x18000f5f5  mov     [rsp+arg_8], edx
0x18000f5f9  mov     [rsp+arg_0], rcx
0x18000f5fe  push    rsi
0x18000f5ff  push    rdi
0x18000f600  push    r12
0x18000f602  push    r14
0x18000f604  push    r15
0x18000f606  sub     rsp, 0F0h
0x18000f60d  mov     r14, r8
0x18000f610  mov     r12d, edx
0x18000f613  mov     rdi, rcx
0x18000f616  mov     [rsp+118h+var_D8], 0
0x18000f61b  xor     esi, esi
0x18000f61d  mov     [rsp+118h+var_D4], esi
0x18000f621  mov     r15d, esi
0x18000f624  mov     [rsp+118h+var_D0], rsi
0x18000f629  lea     rbx, [rcx+48h]
0x18000f62d  mov     [rsp+118h+arg_18], rbx
0x18000f635  inc     dword ptr [rbx]
0x18000f637  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18000f63e  call    cs:__imp__set_se_translator
0x18000f645  nop     dword ptr [rax+rax+00h]
0x18000f64a  mov     qword ptr [rsp+118h+Buffer], rax
0x18000f64f  mov     [rsp+118h+var_D4], esi
0x18000f653  cmp     [rdi+12h], sil
0x18000f657  jz      loc_18000F912
0x18000f65d  lea     rcx, CriticalSection; lpCriticalSection
0x18000f664  call    cs:__imp_LeaveCriticalSection
0x18000f66b  nop     dword ptr [rax+rax+00h]
0x18000f670  mov     [rsp+118h+var_D4], esi
0x18000f674  mov     [rsp+118h+var_D8], 1
0x18000f679  mov     r8, r14
0x18000f67c  mov     edx, r12d
0x18000f67f  mov     rcx, [rdi+28h]
0x18000f683  mov     rax, [rdi+30h]
0x18000f687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f68c  mov     [rsp+118h+var_D4], eax
0x18000f690  mov     rcx, qword ptr [rsp+118h+Buffer]
0x18000f695  call    cs:__imp__set_se_translator
0x18000f69c  nop     dword ptr [rax+rax+00h]
0x18000f6a1  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18000f6a8  call    cs:__imp__set_se_translator
0x18000f6af  nop     dword ptr [rax+rax+00h]
0x18000f6b4  mov     [rsp+118h+var_A0], rax
0x18000f6b9  movsxd  r8, [rsp+118h+var_D4]; dwMessageId
0x18000f6be  test    r8d, r8d
0x18000f6c1  js      short loc_18000F71E
0x18000f6c3  mov     rcx, [rsp+118h+var_A0]
0x18000f6c8  call    cs:__imp__set_se_translator
0x18000f6cf  nop     dword ptr [rax+rax+00h]
0x18000f6d4  mov     edi, [rsp+118h+var_D4]
0x18000f6d8  test    r15, r15
0x18000f6db  jnz     loc_18000FAC3
0x18000f6e1  cmp     [rsp+118h+var_D8], 0
0x18000f6e6  jnz     short loc_18000F705
0x18000f6e8  mov     eax, edi
0x18000f6ea  dec     dword ptr [rbx]
0x18000f6ec  mov     rbx, [rsp+118h+arg_10]
0x18000f6f4  add     rsp, 0F0h
0x18000f6fb  pop     r15
0x18000f6fd  pop     r14
0x18000f6ff  pop     r12
0x18000f701  pop     rdi
0x18000f702  pop     rsi
0x18000f703  retn
0x18000f705  lea     rcx, CriticalSection; lpCriticalSection
0x18000f70c  call    cs:__imp_EnterCriticalSection
0x18000f713  nop     dword ptr [rax+rax+00h]
0x18000f718  mov     [rsp+118h+var_D4], esi
0x18000f71c  jmp     short loc_18000F6E8
0x18000f71e  mov     [rsp+118h+var_B0], rsi
0x18000f723  mov     [rsp+118h+var_B0+8], r8
0x18000f728  mov     qword ptr [rsp+118h+Buffer], rsi
0x18000f72d  mov     [rsp+118h+arg_0], rsi
0x18000f735  mov     r15, rsi
0x18000f738  mov     [rsp+118h+var_D0], rsi
0x18000f73d  mov     [rsp+118h+Arguments], rsi; Arguments
0x18000f742  mov     [rsp+118h+nSize], esi; nSize
0x18000f746  lea     rax, [rsp+118h+Buffer]
0x18000f74b  mov     [rsp+118h+lpBuffer], rax; lpBuffer
0x18000f750  xor     r9d, r9d; dwLanguageId
0x18000f753  xor     edx, edx; lpSource
0x18000f755  mov     ecx, 1100h; dwFlags
0x18000f75a  call    cs:__imp_FormatMessageW
0x18000f761  nop     dword ptr [rax+rax+00h]
0x18000f766  test    eax, eax
0x18000f768  jz      loc_18000F8EA
0x18000f76e  mov     rcx, qword ptr [rsp+118h+Buffer]
0x18000f773  mov     [rsp+118h+var_B0], rcx
0x18000f778  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f77f  nop
0x18000f780  lea     rax, [rax+1]
0x18000f784  cmp     word ptr [rcx+rax*2], 0
0x18000f789  jnz     short loc_18000F780
0x18000f78b  mov     edx, 0Dh
0x18000f790  cmp     dx, [rcx+rax*2-4]
0x18000f795  jnz     short loc_18000F79C
0x18000f797  mov     [rcx+rax*2-4], si
0x18000f79c  lea     rax, [rsp+118h+var_B0]
0x18000f7a1  mov     [rsp+118h+Arguments], rax; Arguments
0x18000f7a6  mov     [rsp+118h+nSize], esi; nSize
0x18000f7aa  lea     rax, [rsp+118h+arg_0]
0x18000f7b2  mov     [rsp+118h+lpBuffer], rax; lpBuffer
0x18000f7b7  xor     r9d, r9d; dwLanguageId
0x18000f7ba  xor     r8d, r8d; dwMessageId
0x18000f7bd  lea     rdx, a10x208x; "%1 (0x%2!08X!)"
0x18000f7c4  mov     ecx, 2500h; dwFlags
0x18000f7c9  call    cs:__imp_FormatMessageW
0x18000f7d0  nop     dword ptr [rax+rax+00h]
0x18000f7d5  test    eax, eax
0x18000f7d7  jnz     loc_18000F8BC
0x18000f7dd  call    cs:__imp_GetLastError
0x18000f7e4  nop     dword ptr [rax+rax+00h]
0x18000f7e9  mov     r14d, eax
0x18000f7ec  test    eax, eax
0x18000f7ee  jg      short loc_18000F7F2
0x18000f7f0  jmp     short loc_18000F7FD
0x18000f7f2  movzx   r14d, ax
0x18000f7f6  or      r14d, 80070000h
0x18000f7fd  mov     rcx, qword ptr [rsp+118h+Buffer]; hMem
0x18000f802  test    rcx, rcx
0x18000f805  jnz     loc_18000F8D9
0x18000f80b  mov     rcx, [rsp+118h+arg_0]; hMem
0x18000f813  test    rcx, rcx
0x18000f816  jnz     loc_18000F947
0x18000f81c  mov     [rsp+118h+var_C8], r14d
0x18000f821  test    r14d, r14d
0x18000f824  js      loc_18000F6C3
0x18000f82a  xorps   xmm0, xmm0
0x18000f82d  movups  xmmword ptr [rsp+118h+var_B0], xmm0
0x18000f832  xorps   xmm1, xmm1
0x18000f835  movups  xmmword ptr [rsp+118h+Buffer], xmm1
0x18000f83a  mov     rdx, [rdi+8]; SourceString
0x18000f83e  lea     rcx, [rsp+118h+var_B0]; DestinationString
0x18000f843  call    cs:__imp_RtlInitUnicodeString
0x18000f84a  nop     dword ptr [rax+rax+00h]
0x18000f84f  mov     rdx, r15; SourceString
0x18000f852  lea     rcx, [rsp+118h+Buffer]; DestinationString
0x18000f857  call    cs:__imp_RtlInitUnicodeString
0x18000f85e  nop     dword ptr [rax+rax+00h]
0x18000f863  cmp     r12d, 1
0x18000f867  jnz     loc_18000F958
0x18000f86d  mov     ecx, 9
0x18000f872  call    FileLogAllowEntry
0x18000f877  test    al, al
0x18000f879  jz      short loc_18000F88E
0x18000f87b  mov     r8, r15
0x18000f87e  mov     rdx, [rdi+8]
0x18000f882  lea     rcx, aLoggingWarning_11; "Logging warning: The time provider '%s'"...
0x18000f889  call    FileLogAdd
0x18000f88e  lea     rax, [rsp+118h+Buffer]
0x18000f893  mov     [rsp+118h+lpBuffer], rax
0x18000f898  lea     r9, [rsp+118h+var_B0]
0x18000f89d  lea     r8, aUu; "uu"
0x18000f8a4  lea     rdx, W32TIME_EVENT_TIMEPROV_FAILED_UPDATE
0x18000f8ab  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18000f8b2  call    LogEvent
0x18000f8b7  jmp     loc_18000F6C3
0x18000f8bc  mov     r15, [rsp+118h+arg_0]
0x18000f8c4  mov     [rsp+118h+var_D0], r15
0x18000f8c9  mov     [rsp+118h+arg_0], rsi
0x18000f8d1  mov     r14d, esi
0x18000f8d4  jmp     loc_18000F7FD
0x18000f8d9  call    cs:__imp_LocalFree
0x18000f8e0  nop     dword ptr [rax+rax+00h]
0x18000f8e5  jmp     loc_18000F80B
0x18000f8ea  call    cs:__imp_GetLastError
0x18000f8f1  nop     dword ptr [rax+rax+00h]
0x18000f8f6  cmp     eax, 13Dh
0x18000f8fb  jnz     loc_18000F7DD
0x18000f901  lea     rax, qword_180071478
0x18000f908  mov     [rsp+118h+var_B0], rax
0x18000f90d  jmp     loc_18000F79C
0x18000f912  mov     [rsp+118h+var_D4], 80070426h
0x18000f91a  jmp     loc_18000F690
0x18000f91f  jmp     short loc_18000F923
0x18000f921  jmp     short $+2
0x18000f923  xor     esi, esi
0x18000f925  mov     r12d, [rsp+118h+arg_8]
0x18000f92d  mov     rdi, [rsp+118h+arg_0]
0x18000f935  mov     r15, [rsp+118h+var_D0]
0x18000f93a  mov     rbx, [rsp+118h+arg_18]
0x18000f942  jmp     loc_18000F690
0x18000f947  call    cs:__imp_LocalFree
0x18000f94e  nop     dword ptr [rax+rax+00h]
0x18000f953  jmp     loc_18000F81C
0x18000f958  cmp     r12d, 2
0x18000f95c  jnz     short loc_18000F9AD
0x18000f95e  mov     ecx, 9
0x18000f963  call    FileLogAllowEntry
0x18000f968  test    al, al
0x18000f96a  jz      short loc_18000F97F
0x18000f96c  mov     r8, r15
0x18000f96f  mov     rdx, [rdi+8]
0x18000f973  lea     rcx, aLoggingWarning_35; "Logging warning: The time provider '%s'"...
0x18000f97a  call    FileLogAdd
0x18000f97f  lea     rax, [rsp+118h+Buffer]
0x18000f984  mov     [rsp+118h+lpBuffer], rax
0x18000f989  lea     r9, [rsp+118h+var_B0]
0x18000f98e  lea     r8, aUu; "uu"
0x18000f995  lea     rdx, W32TIME_EVENT_TIMEPROV_FAILED_POLLUPDATE
0x18000f99c  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18000f9a3  call    LogEvent
0x18000f9a8  jmp     loc_18000F6C3
0x18000f9ad  test    r12d, r12d
0x18000f9b0  jnz     short loc_18000FA01
0x18000f9b2  mov     ecx, 9
0x18000f9b7  call    FileLogAllowEntry
0x18000f9bc  test    al, al
0x18000f9be  jz      short loc_18000F9D3
0x18000f9c0  mov     r8, r15
0x18000f9c3  mov     rdx, [rdi+8]
0x18000f9c7  lea     rcx, aLoggingWarning_7; "Logging warning: The time provider '%s'"...
0x18000f9ce  call    FileLogAdd
0x18000f9d3  lea     rax, [rsp+118h+Buffer]
0x18000f9d8  mov     [rsp+118h+lpBuffer], rax
0x18000f9dd  lea     r9, [rsp+118h+var_B0]
0x18000f9e2  lea     r8, aUu; "uu"
0x18000f9e9  lea     rdx, W32TIME_EVENT_TIMEPROV_FAILED_TIMEJUMP
0x18000f9f0  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18000f9f7  call    LogEvent
0x18000f9fc  jmp     loc_18000F6C3
0x18000fa01  cmp     r12d, 4
0x18000fa05  jnz     short loc_18000FA56
0x18000fa07  mov     ecx, 9
0x18000fa0c  call    FileLogAllowEntry
0x18000fa11  test    al, al
0x18000fa13  jz      short loc_18000FA28
0x18000fa15  mov     r8, r15
0x18000fa18  mov     rdx, [rdi+8]
0x18000fa1c  lea     rcx, aLoggingWarning_4; "Logging warning: The time provider '%s'"...
0x18000fa23  call    FileLogAdd
0x18000fa28  lea     rax, [rsp+118h+Buffer]
0x18000fa2d  mov     [rsp+118h+lpBuffer], rax
0x18000fa32  lea     r9, [rsp+118h+var_B0]
0x18000fa37  lea     r8, aUu; "uu"
0x18000fa3e  lea     rdx, W32TIME_EVENT_TIMEPROV_FAILED_NETTOPOCHANGE
0x18000fa45  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18000fa4c  call    LogEvent
0x18000fa51  jmp     loc_18000F6C3
0x18000fa56  cmp     r12d, 3
0x18000fa5a  jnz     short loc_18000FA77
0x18000fa5c  mov     ecx, 9
0x18000fa61  call    FileLogAllowEntry
0x18000fa66  test    al, al
0x18000fa68  jz      loc_18000F6C3
0x18000fa6e  lea     rcx, aLoggingWarning_25; "Logging warning: The time provider '%s'"...
0x18000fa75  jmp     short loc_18000FA9A
0x18000fa77  cmp     r12d, 5
0x18000fa7b  jnz     loc_18000F6C3
0x18000fa81  mov     ecx, 9
0x18000fa86  call    FileLogAllowEntry
0x18000fa8b  test    al, al
0x18000fa8d  jz      loc_18000F6C3
0x18000fa93  lea     rcx, aLoggingWarning_21; "Logging warning: The time provider '%s'"...
0x18000fa9a  mov     r8, r15
0x18000fa9d  mov     rdx, [rdi+8]
0x18000faa1  call    FileLogAdd
0x18000faa6  jmp     loc_18000F6C3
0x18000faab  jmp     short loc_18000FAAF
0x18000faad  jmp     short $+2
0x18000faaf  xor     esi, esi
0x18000fab1  mov     r15, [rsp+118h+var_D0]
0x18000fab6  mov     rbx, [rsp+118h+arg_18]
0x18000fabe  jmp     loc_18000F6C3
0x18000fac3  mov     rcx, r15; hMem
0x18000fac6  call    cs:__imp_LocalFree
0x18000facd  nop     dword ptr [rax+rax+00h]
0x18000fad2  jmp     loc_18000F6E1
```

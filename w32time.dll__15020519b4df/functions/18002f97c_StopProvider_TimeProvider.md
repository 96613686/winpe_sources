# StopProvider(TimeProvider *)

- ea: `0x18002f97c`
- end: `0x18002fbd5`
- name: `?StopProvider@@YAJPEAUTimeProvider@@@Z`
- size: `601`
- prototype: `__int64 __fastcall(struct TimeProvider *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010b74`

## callees

- `0x18000a7e0`
- `0x180018138`
- `0x18001a780`
- `0x18001d9a0`
- `0x18002f97c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002f9bc`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002fa28`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002fa3e`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002fb82`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002f9bc`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002fa28`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002fa3e`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002fb82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fb9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fb9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f9a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fb21`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fb21`
- `ntdll!RtlInitUnicodeString` at `0x18002fac6`
- `ntdll!RtlInitUnicodeString` at `0x18002fadf`
- `ntdll!RtlInitUnicodeString` at `0x18002fac6`
- `ntdll!RtlInitUnicodeString` at `0x18002fadf`

## string_xrefs

- `0x18002f9ed`: `Stopping '%s', dll:'%s'\n`
- `0x18002fa94`: `Logging error: The time provider '%s' returned the following error during shutdown: %s\n`
- `0x18002fb65`: `FreeLibrary dll:%s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall StopProvider(struct TimeProvider *a1)
{
  struct TimeProvider *v1; // rdi
  PCWSTR *v2; // rsi
  HMODULE v3; // rcx
  signed int LastError; // eax
  unsigned int v5; // edi
  unsigned int v7; // eax
  signed int dwMessageId; // [rsp+30h] [rbp-B8h]
  struct _UNICODE_STRING v9; // [rsp+38h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v11[24]; // [rsp+58h] [rbp-90h] BYREF
  int v12; // [rsp+70h] [rbp-78h]
  _BYTE v13[80]; // [rsp+98h] [rbp-50h] BYREF
  PCWSTR SourceString; // [rsp+F8h] [rbp+10h] BYREF
  __int64 v17; // [rsp+100h] [rbp+18h]
  struct TimeProvider *v18; // [rsp+108h] [rbp+20h]

  v1 = a1;
  v18 = a1;
  SourceString = 0;
  EnterCriticalSection(&CriticalSection);
  v17 = _set_se_translator(SeTransFunc);
  try
  {
    if ( *((_QWORD *)v1 + 7) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(61) )
        FileLogAdd(L"Stopping '%s', dll:'%s'\n", *((_QWORD *)v1 + 1), *(_QWORD *)v1);
      dwMessageId = (*((__int64 (__fastcall **)(_QWORD))v1 + 7))(*((_QWORD *)v1 + 5));
    }
    else
    {
      dwMessageId = 0;
    }
  }
  catch ( SeException v11 )
  {
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    dwMessageId = v7;
    SeException::~SeException((SeException *)v11);
    v1 = a1;
  }
  catch ( std::bad_alloc v13 )
  {
    dwMessageId = -2147024882;
    SeException::~SeException((SeException *)v13);
    v1 = a1;
  }
  catch ( ... )
  {
    dwMessageId = -2147418113;
    v1 = a1;
  }
  _set_se_translator(v17);
  *((_BYTE *)v1 + 18) = 0;
  v17 = _set_se_translator(SeTransFunc);
  if ( dwMessageId < 0 && (int)GetSystemErrorString(dwMessageId, (unsigned __int16 **)&SourceString) >= 0 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(9) )
    {
      v2 = (PCWSTR *)((char *)v1 + 8);
      FileLogAdd(
        L"Logging error: The time provider '%s' returned the following error during shutdown: %s\n",
        *((_QWORD *)v1 + 1),
        SourceString);
    }
    else
    {
      v2 = (PCWSTR *)((char *)v18 + 8);
    }
    DestinationString = 0;
    v9 = 0;
    RtlInitUnicodeString(&DestinationString, *v2);
    RtlInitUnicodeString(&v9, SourceString);
    LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIMEPROV_FAILED_STOP, L"uu", &DestinationString);
  }
  v3 = (HMODULE)*((_QWORD *)v1 + 4);
  if ( !v3 )
    goto LABEL_21;
  if ( FreeLibrary(v3) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(9) )
      FileLogAdd(L"FreeLibrary dll:%s\n", *(_QWORD *)v1);
LABEL_21:
    _set_se_translator(v17);
    v5 = 0;
    goto LABEL_22;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_22:
  LeaveCriticalSection(&CriticalSection);
  if ( SourceString )
    LocalFree((HLOCAL)SourceString);
  return v5;
}

```

## disassembly

```asm
0x18002f97c  mov     rax, rsp
0x18002f97f  mov     [rax+8], rcx
0x18002f983  push    rbx
0x18002f984  push    rsi
0x18002f985  push    rdi
0x18002f986  sub     rsp, 0D0h
0x18002f98d  mov     rdi, rcx
0x18002f990  mov     [rsp+0E8h+arg_18], rcx
0x18002f998  xor     ebx, ebx
0x18002f99a  mov     [rsp+0E8h+dwMessageId], ebx
0x18002f99e  mov     [rax+10h], rbx
0x18002f9a2  lea     rcx, CriticalSection; lpCriticalSection
0x18002f9a9  call    cs:__imp_EnterCriticalSection
0x18002f9b0  nop     dword ptr [rax+rax+00h]
0x18002f9b5  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18002f9bc  call    cs:__imp__set_se_translator
0x18002f9c3  nop     dword ptr [rax+rax+00h]
0x18002f9c8  mov     [rsp+0E8h+arg_10], rax
0x18002f9d0  mov     [rsp+0E8h+dwMessageId], ebx
0x18002f9d4  cmp     [rdi+38h], rbx
0x18002f9d8  jz      short loc_18002FA0C
0x18002f9da  lea     ecx, [rbx+3Dh]
0x18002f9dd  call    FileLogAllowEntry
0x18002f9e2  test    al, al
0x18002f9e4  jz      short loc_18002F9F9
0x18002f9e6  mov     r8, [rdi]
0x18002f9e9  mov     rdx, [rdi+8]
0x18002f9ed  lea     rcx, aStoppingSDllS; "Stopping '%s', dll:'%s'\n"
0x18002f9f4  call    FileLogAdd
0x18002f9f9  mov     rcx, [rdi+28h]
0x18002f9fd  mov     rax, [rdi+38h]
0x18002fa01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa06  mov     [rsp+0E8h+dwMessageId], eax
0x18002fa0a  jmp     short loc_18002FA10
0x18002fa0c  mov     [rsp+0E8h+dwMessageId], ebx
0x18002fa10  jmp     short loc_18002FA20
0x18002fa12  jmp     short loc_18002FA16
0x18002fa14  jmp     short $+2
0x18002fa16  xor     ebx, ebx
0x18002fa18  mov     rdi, [rsp+0E8h+arg_0]
0x18002fa20  mov     rcx, [rsp+0E8h+arg_10]
0x18002fa28  call    cs:__imp__set_se_translator
0x18002fa2f  nop     dword ptr [rax+rax+00h]
0x18002fa34  mov     [rdi+12h], bl
0x18002fa37  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18002fa3e  call    cs:__imp__set_se_translator
0x18002fa45  nop     dword ptr [rax+rax+00h]
0x18002fa4a  mov     [rsp+0E8h+arg_10], rax
0x18002fa52  mov     ecx, [rsp+0E8h+dwMessageId]; dwMessageId
0x18002fa56  test    ecx, ecx
0x18002fa58  jns     loc_18002FB14
0x18002fa5e  lea     rdx, [rsp+0E8h+SourceString]; unsigned __int16 **
0x18002fa66  call    ?GetSystemErrorString@@YAJJPEAPEAG@Z; GetSystemErrorString(long,ushort * *)
0x18002fa6b  mov     [rsp+0E8h+var_B4], eax
0x18002fa6f  test    eax, eax
0x18002fa71  js      loc_18002FB14
0x18002fa77  mov     ecx, 9
0x18002fa7c  call    FileLogAllowEntry
0x18002fa81  test    al, al
0x18002fa83  jz      short loc_18002FAA2
0x18002fa85  lea     rsi, [rdi+8]
0x18002fa89  mov     r8, [rsp+0E8h+SourceString]
0x18002fa91  mov     rdx, [rsi]
0x18002fa94  lea     rcx, aLoggingErrorTh_0; "Logging error: The time provider '%s' r"...
0x18002fa9b  call    FileLogAdd
0x18002faa0  jmp     short loc_18002FAAE
0x18002faa2  mov     rsi, [rsp+0E8h+arg_18]
0x18002faaa  add     rsi, 8
0x18002faae  xorps   xmm0, xmm0
0x18002fab1  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x18002fab6  xorps   xmm1, xmm1
0x18002fab9  movups  xmmword ptr [rsp+0E8h+var_B0.Length], xmm1
0x18002fabe  mov     rdx, [rsi]; SourceString
0x18002fac1  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x18002fac6  call    cs:__imp_RtlInitUnicodeString
0x18002facd  nop     dword ptr [rax+rax+00h]
0x18002fad2  mov     rdx, [rsp+0E8h+SourceString]; SourceString
0x18002fada  lea     rcx, [rsp+0E8h+var_B0]; DestinationString
0x18002fadf  call    cs:__imp_RtlInitUnicodeString
0x18002fae6  nop     dword ptr [rax+rax+00h]
0x18002faeb  lea     rax, [rsp+0E8h+var_B0]
0x18002faf0  mov     [rsp+0E8h+var_C8], rax
0x18002faf5  lea     r9, [rsp+0E8h+DestinationString]
0x18002fafa  lea     r8, aUu; "uu"
0x18002fb01  lea     rdx, W32TIME_EVENT_TIMEPROV_FAILED_STOP
0x18002fb08  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18002fb0f  call    LogEvent
0x18002fb14  mov     [rsp+0E8h+var_B4], ebx
0x18002fb18  mov     rcx, [rdi+20h]; hLibModule
0x18002fb1c  test    rcx, rcx
0x18002fb1f  jz      short loc_18002FB72
0x18002fb21  call    cs:__imp_FreeLibrary
0x18002fb28  nop     dword ptr [rax+rax+00h]
0x18002fb2d  test    eax, eax
0x18002fb2f  jnz     short loc_18002FB54
0x18002fb31  call    cs:__imp_GetLastError
0x18002fb38  nop     dword ptr [rax+rax+00h]
0x18002fb3d  mov     edi, eax
0x18002fb3f  test    eax, eax
0x18002fb41  jg      short loc_18002FB45
0x18002fb43  jmp     short loc_18002FB4E
0x18002fb45  movzx   edi, ax
0x18002fb48  or      edi, 80070000h
0x18002fb4e  mov     [rsp+0E8h+var_B4], edi
0x18002fb52  jmp     short loc_18002FB97
0x18002fb54  mov     ecx, 9
0x18002fb59  call    FileLogAllowEntry
0x18002fb5e  test    al, al
0x18002fb60  jz      short loc_18002FB72
0x18002fb62  mov     rdx, [rdi]
0x18002fb65  lea     rcx, aFreelibraryDll; "FreeLibrary dll:%s\n"
0x18002fb6c  call    FileLogAdd
0x18002fb71  nop
0x18002fb72  jmp     short loc_18002FB7A
0x18002fb74  jmp     short loc_18002FB78
0x18002fb76  jmp     short $+2
0x18002fb78  xor     ebx, ebx
0x18002fb7a  mov     rcx, [rsp+0E8h+arg_10]
0x18002fb82  call    cs:__imp__set_se_translator
0x18002fb89  nop     dword ptr [rax+rax+00h]
0x18002fb8e  mov     edi, [rsp+0E8h+var_B4]
0x18002fb92  test    edi, edi
0x18002fb94  cmovns  edi, ebx
0x18002fb97  lea     rcx, CriticalSection; lpCriticalSection
0x18002fb9e  call    cs:__imp_LeaveCriticalSection
0x18002fba5  nop     dword ptr [rax+rax+00h]
0x18002fbaa  mov     [rsp+0E8h+dwMessageId], ebx
0x18002fbae  mov     rcx, [rsp+0E8h+SourceString]; hMem
0x18002fbb6  test    rcx, rcx
0x18002fbb9  jz      short loc_18002FBC7
0x18002fbbb  call    cs:__imp_LocalFree
0x18002fbc2  nop     dword ptr [rax+rax+00h]
0x18002fbc7  mov     eax, edi
0x18002fbc9  add     rsp, 0D0h
0x18002fbd0  pop     rdi
0x18002fbd1  pop     rsi
0x18002fbd2  pop     rbx
0x18002fbd3  retn
```

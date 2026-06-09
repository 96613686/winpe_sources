# Microsoft::Diagnostics::Utils::Os::GetCommandLineForPids(std::vector<ulong,std::allocator<ulong>> const &,std::vector<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong>>> &)

- ea: `0x1800fbba4`
- end: `0x1800fbe3c`
- name: `?GetCommandLineForPids@Os@Utils@Diagnostics@Microsoft@@SAJAEBV?$vector@KV?$allocator@K@std@@@std@@AEAV?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@6@@Z`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e7680`
- `0x1800fb8a0`

## callees

- `0x1800035ec`
- `0x18001d160`
- `0x180027be0`
- `0x1800495cc`
- `0x18005d050`
- `0x1800fbba4`
- `0x18012de40`
- `0x180173794`
- `0x180186cb8`
- `0x1801d15b0`
- `0x180204670`
- `0x180204c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbc98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbcf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbd57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbc98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbcf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbd57`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800fbbea`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800fbbea`
- `ntdll!NtQueryInformationProcess` at `0x1800fbc2d`
- `ntdll!NtQueryInformationProcess` at `0x1800fbc2d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800fbc88`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800fbce6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800fbd47`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800fbc88`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800fbce6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800fbd47`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::GetCommandLineForPids(DWORD **a1, __int64 a2)
{
  DWORD *v3; // rdi
  DWORD *v4; // r15
  DWORD v5; // r14d
  HANDLE v6; // rax
  void *v7; // rbx
  NTSTATUS InformationProcess; // eax
  DWORD LastError; // eax
  __int64 v10; // rdx
  LPVOID *v11; // r8
  DWORD v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // r8d
  int v16; // r9d
  int ReturnLength; // [rsp+20h] [rbp-69h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-69h]
  unsigned int ReturnLengthb; // [rsp+20h] [rbp-69h]
  DWORD v21; // [rsp+30h] [rbp-59h] BYREF
  HANDLE v22; // [rsp+38h] [rbp-51h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+40h] [rbp-49h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-41h] BYREF
  LPCVOID lpBaseAddress[2]; // [rsp+50h] [rbp-39h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+60h] [rbp-29h] BYREF
  LPVOID lpBuffer[4]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v3 = *a1;
  v4 = a1[1];
  while ( v3 != v4 )
  {
    v5 = *v3;
    v21 = v5;
    v6 = OpenProcess(0x410u, 0, v5);
    v7 = v6;
    v22 = v6;
    if ( v6 )
    {
      memset(ProcessInformation, 0, sizeof(ProcessInformation));
      InformationProcess = NtQueryInformationProcess(v6, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
      if ( InformationProcess < 0 )
      {
        wil::details::in1diag3::_Log_NtStatus(
          retaddr,
          (void *)0xCC1,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
          (const char *)(unsigned int)InformationProcess,
          ReturnLength);
        goto LABEL_21;
      }
      Buffer = 0;
      NumberOfBytesRead = 0;
      if ( !ReadProcessMemory(
              v7,
              (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 32LL),
              &Buffer,
              8u,
              &NumberOfBytesRead) )
      {
        LastError = GetLastError();
        v10 = 3281;
LABEL_7:
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
          (const char *)LastError,
          ReturnLengtha);
        goto LABEL_21;
      }
      *(_OWORD *)lpBaseAddress = 0;
      if ( !ReadProcessMemory(v7, (LPCVOID)(Buffer + 112), lpBaseAddress, 0x10u, &NumberOfBytesRead) )
      {
        LastError = GetLastError();
        v10 = 3292;
        goto LABEL_7;
      }
      std::wstring::wstring(lpBuffer);
      std::wstring::resize(lpBuffer, LOWORD(lpBaseAddress[0]) + 2LL);
      v11 = lpBuffer;
      if ( lpBuffer[3] > (LPVOID)7 )
        v11 = (LPVOID *)lpBuffer[0];
      if ( ReadProcessMemory(v7, lpBaseAddress[1], v11, LOWORD(lpBaseAddress[0]), &NumberOfBytesRead) )
      {
        std::wstring::resize(lpBuffer, NumberOfBytesRead >> 1);
        v14 = *(_QWORD *)(a2 + 8);
        if ( v14 == *(_QWORD *)(a2 + 16) )
        {
          std::vector<std::pair<std::wstring,unsigned long>>::_Emplace_reallocate<std::wstring &,unsigned long const &>(
            a2,
            v14,
            lpBuffer,
            &v21);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<std::pair<std::wstring,unsigned long>>>::construct<std::pair<std::wstring,unsigned long>,std::wstring &,unsigned long const &>(
            v13,
            v14,
            lpBuffer,
            &v21);
          *(_QWORD *)(a2 + 8) += 40LL;
        }
      }
      else
      {
        v12 = GetLastError();
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0xCE9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
          (const char *)v12,
          ReturnLengthb);
      }
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
    }
    else if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x20000) )
    {
      v21 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803CC57C,
        v15,
        v16,
        (__int64)&v21);
    }
LABEL_21:
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
    ++v3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800fbba4  mov     [rsp-8+arg_10], rbx
0x1800fbba9  push    rbp
0x1800fbbaa  push    rsi
0x1800fbbab  push    rdi
0x1800fbbac  push    r14
0x1800fbbae  push    r15
0x1800fbbb0  lea     rbp, [rsp-37h]
0x1800fbbb5  sub     rsp, 0C0h
0x1800fbbbc  mov     rax, cs:__security_cookie
0x1800fbbc3  xor     rax, rsp
0x1800fbbc6  mov     [rbp+57h+var_30], rax
0x1800fbbca  mov     rsi, rdx
0x1800fbbcd  mov     rdi, [rcx]
0x1800fbbd0  mov     r15, [rcx+8]
0x1800fbbd4  jmp     loc_1800FBE0D
0x1800fbbd9  mov     r14d, [rdi]
0x1800fbbdc  mov     [rbp+57h+var_B0], r14d
0x1800fbbe0  mov     r8d, r14d; dwProcessId
0x1800fbbe3  xor     edx, edx; bInheritHandle
0x1800fbbe5  mov     ecx, 410h; dwDesiredAccess
0x1800fbbea  call    cs:__imp_OpenProcess
0x1800fbbf1  nop     dword ptr [rax+rax+00h]
0x1800fbbf6  mov     rbx, rax
0x1800fbbf9  mov     [rbp+57h+var_A8], rax
0x1800fbbfd  test    rax, rax
0x1800fbc00  jz      loc_1800FBDBF
0x1800fbc06  xorps   xmm0, xmm0
0x1800fbc09  movups  [rbp+57h+ProcessInformation], xmm0
0x1800fbc0d  movups  [rbp+57h+var_70], xmm0
0x1800fbc11  movups  [rbp+57h+var_60], xmm0
0x1800fbc15  mov     qword ptr [rsp+0E0h+ReturnLength], 0; int
0x1800fbc1e  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1800fbc24  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x1800fbc28  xor     edx, edx; ProcessInformationClass
0x1800fbc2a  mov     rcx, rax; ProcessHandle
0x1800fbc2d  call    cs:__imp_NtQueryInformationProcess
0x1800fbc34  nop     dword ptr [rax+rax+00h]
0x1800fbc39  test    eax, eax
0x1800fbc3b  jns     short loc_1800FBC5A
0x1800fbc3d  mov     rcx, [rbp+5Fh]; this
0x1800fbc41  mov     r9d, eax; char *
0x1800fbc44  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x1800fbc4b  mov     edx, 0CC1h; void *
0x1800fbc50  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800fbc55  jmp     loc_1800FBE00
0x1800fbc5a  mov     [rbp+57h+Buffer], 0
0x1800fbc62  mov     [rbp+57h+NumberOfBytesRead], 0
0x1800fbc6a  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x1800fbc6e  add     rdx, 20h ; ' '; lpBaseAddress
0x1800fbc72  lea     rax, [rbp+57h+NumberOfBytesRead]
0x1800fbc76  mov     qword ptr [rsp+0E0h+ReturnLength], rax; unsigned int
0x1800fbc7b  mov     r9d, 8; nSize
0x1800fbc81  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800fbc85  mov     rcx, rbx; hProcess
0x1800fbc88  call    cs:__imp_ReadProcessMemory
0x1800fbc8f  nop     dword ptr [rax+rax+00h]
0x1800fbc94  test    eax, eax
0x1800fbc96  jnz     short loc_1800FBCC1
0x1800fbc98  call    cs:__imp_GetLastError
0x1800fbc9f  nop     dword ptr [rax+rax+00h]
0x1800fbca4  mov     edx, 0CD1h; void *
0x1800fbca9  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x1800fbcb0  mov     rcx, [rbp+5Fh]; this
0x1800fbcb4  mov     r9d, eax; char *
0x1800fbcb7  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800fbcbc  jmp     loc_1800FBE00
0x1800fbcc1  xorps   xmm0, xmm0
0x1800fbcc4  movups  xmmword ptr [rbp+57h+lpBaseAddress], xmm0
0x1800fbcc8  mov     rdx, [rbp+57h+Buffer]
0x1800fbccc  add     rdx, 70h ; 'p'; lpBaseAddress
0x1800fbcd0  lea     rax, [rbp+57h+NumberOfBytesRead]
0x1800fbcd4  mov     qword ptr [rsp+0E0h+ReturnLength], rax; lpNumberOfBytesRead
0x1800fbcd9  mov     r9d, 10h; nSize
0x1800fbcdf  lea     r8, [rbp+57h+lpBaseAddress]; lpBuffer
0x1800fbce3  mov     rcx, rbx; hProcess
0x1800fbce6  call    cs:__imp_ReadProcessMemory
0x1800fbced  nop     dword ptr [rax+rax+00h]
0x1800fbcf2  test    eax, eax
0x1800fbcf4  jnz     short loc_1800FBD09
0x1800fbcf6  call    cs:__imp_GetLastError
0x1800fbcfd  nop     dword ptr [rax+rax+00h]
0x1800fbd02  mov     edx, 0CDCh
0x1800fbd07  jmp     short loc_1800FBCA9
0x1800fbd09  lea     rcx, [rbp+57h+lpBuffer]; void *
0x1800fbd0d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800fbd12  nop
0x1800fbd13  movzx   edx, word ptr [rbp+57h+lpBaseAddress]
0x1800fbd17  add     rdx, 2
0x1800fbd1b  lea     rcx, [rbp+57h+lpBuffer]
0x1800fbd1f  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800fbd24  lea     r8, [rbp+57h+lpBuffer]
0x1800fbd28  cmp     [rbp+57h+var_38], 7
0x1800fbd2d  cmova   r8, [rbp+57h+lpBuffer]; lpBuffer
0x1800fbd32  movzx   r9d, word ptr [rbp+57h+lpBaseAddress]; nSize
0x1800fbd37  lea     rax, [rbp+57h+NumberOfBytesRead]
0x1800fbd3b  mov     qword ptr [rsp+0E0h+ReturnLength], rax; unsigned int
0x1800fbd40  mov     rdx, [rbp+57h+lpBaseAddress+8]; lpBaseAddress
0x1800fbd44  mov     rcx, rbx; hProcess
0x1800fbd47  call    cs:__imp_ReadProcessMemory
0x1800fbd4e  nop     dword ptr [rax+rax+00h]
0x1800fbd53  test    eax, eax
0x1800fbd55  jnz     short loc_1800FBD7D
0x1800fbd57  call    cs:__imp_GetLastError
0x1800fbd5e  nop     dword ptr [rax+rax+00h]
0x1800fbd63  mov     r9d, eax; char *
0x1800fbd66  mov     rcx, [rbp+5Fh]; this
0x1800fbd6a  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x1800fbd71  mov     edx, 0CE9h; void *
0x1800fbd76  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800fbd7b  jmp     short loc_1800FBDB4
0x1800fbd7d  mov     rdx, [rbp+57h+NumberOfBytesRead]
0x1800fbd81  shr     rdx, 1
0x1800fbd84  lea     rcx, [rbp+57h+lpBuffer]
0x1800fbd88  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800fbd8d  mov     rdx, [rsi+8]
0x1800fbd91  lea     r9, [rbp+57h+var_B0]
0x1800fbd95  lea     r8, [rbp+57h+lpBuffer]
0x1800fbd99  cmp     rdx, [rsi+10h]
0x1800fbd9d  jz      short loc_1800FBDAB
0x1800fbd9f  call    ??$construct@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEBK@?$_Default_allocator_traits@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@std@@@std@@SAXAEAV?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@1@QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@1@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBK@Z; std::_Default_allocator_traits<std::allocator<std::pair<std::wstring,ulong>>>::construct<std::pair<std::wstring,ulong>,std::wstring &,ulong const &>(std::allocator<std::pair<std::wstring,ulong>> &,std::pair<std::wstring,ulong> * const,std::wstring &,ulong const &)
0x1800fbda4  add     qword ptr [rsi+8], 28h ; '('
0x1800fbda9  jmp     short loc_1800FBDB4
0x1800fbdab  mov     rcx, rsi
0x1800fbdae  call    ??$_Emplace_reallocate@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@1@QEAU21@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBK@Z; std::vector<std::pair<std::wstring,ulong>>::_Emplace_reallocate<std::wstring &,ulong const &>(std::pair<std::wstring,ulong> * const,std::wstring &,ulong const &)
0x1800fbdb3  nop
0x1800fbdb4  lea     rcx, [rbp+57h+lpBuffer]; this
0x1800fbdb8  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800fbdbd  jmp     short loc_1800FBE00
0x1800fbdbf  mov     eax, cs:dword_18042D328
0x1800fbdc5  cmp     eax, 4
0x1800fbdc8  jbe     short loc_1800FBE00
0x1800fbdca  mov     edx, 20000h
0x1800fbdcf  lea     rcx, dword_18042D328
0x1800fbdd6  call    _tlgKeywordOn
0x1800fbddb  test    al, al
0x1800fbddd  jz      short loc_1800FBE00
0x1800fbddf  mov     [rbp+57h+var_B0], r14d
0x1800fbde3  lea     rax, [rbp+57h+var_B0]
0x1800fbde7  mov     qword ptr [rsp+0E0h+ReturnLength], rax
0x1800fbdec  lea     rdx, unk_1803CC57C
0x1800fbdf3  lea     rcx, dword_18042D328
0x1800fbdfa  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800fbdff  nop
0x1800fbe00  lea     rcx, [rbp+57h+var_A8]
0x1800fbe04  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fbe09  add     rdi, 4
0x1800fbe0d  cmp     rdi, r15
0x1800fbe10  jnz     loc_1800FBBD9
0x1800fbe16  xor     eax, eax
0x1800fbe18  mov     rcx, [rbp+57h+var_30]
0x1800fbe1c  xor     rcx, rsp; StackCookie
0x1800fbe1f  call    __security_check_cookie
0x1800fbe24  mov     rbx, [rsp+0E0h+arg_10]
0x1800fbe2c  add     rsp, 0C0h
0x1800fbe33  pop     r15
0x1800fbe35  pop     r14
0x1800fbe37  pop     rdi
0x1800fbe38  pop     rsi
0x1800fbe39  pop     rbp
0x1800fbe3a  retn
```

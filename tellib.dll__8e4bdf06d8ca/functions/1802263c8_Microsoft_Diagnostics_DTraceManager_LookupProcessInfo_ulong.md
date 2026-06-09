# Microsoft::Diagnostics::DTraceManager::LookupProcessInfo(ulong)

- ea: `0x1802263c8`
- end: `0x180226691`
- name: `?LookupProcessInfo@DTraceManager@Diagnostics@Microsoft@@CA?AV?$optional@UProcessInfo@DTraceManager@Diagnostics@Microsoft@@@std@@K@Z`
- size: `713`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802261d4`
- `0x180226930`

## callees

- `0x18000364c`
- `0x180008bc0`
- `0x18001d160`
- `0x180027be0`
- `0x180034d94`
- `0x18005d050`
- `0x180080054`
- `0x18012de40`
- `0x180161298`
- `0x1802263c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022644a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180226504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022644a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180226504`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18022640e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18022640e`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x1802264b7`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x1802264b7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180226577`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180226577`

## string_xrefs

- `0x1802264d3`: `onecore\base\telemetry\utc\service\scenarios\base\dtracemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::DTraceManager::LookupProcessInfo(__int64 a1, DWORD a2)
{
  HANDLE v4; // rax
  signed int LastError; // eax
  int v6; // r8d
  int v7; // r9d
  const char *v9; // r9
  signed int v10; // eax
  int v11; // r8d
  int v12; // r9d
  LPWSTR FileNameW; // rax
  __int64 v14; // r8
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  char **v18; // rax
  DWORD v19; // [rsp+30h] [rbp-478h] BYREF
  char **v20; // [rsp+38h] [rbp-470h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-468h] BYREF
  char *v22[2]; // [rsp+58h] [rbp-450h] BYREF
  __m128i si128; // [rsp+68h] [rbp-440h]
  DWORD v24; // [rsp+78h] [rbp-430h]
  WCHAR ImageFileName[520]; // [rsp+80h] [rbp-428h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+0h]

  v21[2] = a1;
  if ( (a2 & 0xFFFFFFFB) != 0 )
  {
    v4 = OpenProcess(0x1000u, 0, a2);
    v21[0] = v4;
    if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 8) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        LODWORD(v20) = LastError;
        v19 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18042D328,
          (unsigned int)&unk_1803CF818,
          v6,
          v7,
          (__int64)&v19,
          (__int64)&v20);
      }
LABEL_8:
      *(_BYTE *)(a1 + 40) = 0;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v21);
      return a1;
    }
    if ( !K32GetProcessImageFileNameW(v4, ImageFileName, 0x208u) )
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\dtracemanager.cpp",
        v9);
      if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 8) )
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        v19 = v10;
        LODWORD(v20) = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18042D328,
          (unsigned int)&unk_1803CF86E,
          v11,
          v12,
          (__int64)&v20,
          (__int64)&v19);
      }
      goto LABEL_8;
    }
    std::wstring::wstring(v22);
    v24 = a2;
    FileNameW = PathFindFileNameW(ImageFileName);
    v14 = -1;
    do
      ++v14;
    while ( FileNameW[v14] );
    std::wstring::_Assign<wchar_t>(v22, FileNameW, (char *)v14);
    if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 8) )
    {
      v18 = v22;
      if ( si128.m128i_i64[1] > 7uLL )
        v18 = (char **)v22[0];
      v20 = v18;
      v19 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v15,
        (unsigned int)&unk_1803CF785,
        v16,
        v17,
        (__int64)&v19,
        (__int64)&v20);
    }
    *(_OWORD *)a1 = 0;
    *(char **)a1 = v22[0];
    *(char **)(a1 + 8) = v22[1];
    *(__m128i *)(a1 + 16) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v22[0]) = 0;
    *(_DWORD *)(a1 + 32) = v24;
    *(_BYTE *)(a1 + 40) = 1;
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v22);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v21);
    return a1;
  }
  else
  {
    *(_BYTE *)(a1 + 40) = 0;
    return a1;
  }
}

```

## disassembly

```asm
0x1802263c8  mov     [rsp+arg_10], rbx
0x1802263cd  mov     [rsp+arg_18], rsi
0x1802263d2  push    rdi
0x1802263d3  sub     rsp, 4A0h
0x1802263da  mov     rax, cs:__security_cookie
0x1802263e1  xor     rax, rsp
0x1802263e4  mov     [rsp+4A8h+var_18], rax
0x1802263ec  mov     esi, edx
0x1802263ee  mov     rdi, rcx
0x1802263f1  mov     [rsp+4A8h+var_458], rcx
0x1802263f6  xor     ebx, ebx
0x1802263f8  test    edx, 0FFFFFFFBh
0x1802263fe  jz      loc_180226659
0x180226404  mov     r8d, edx; dwProcessId
0x180226407  xor     edx, edx; bInheritHandle
0x180226409  mov     ecx, 1000h; dwDesiredAccess
0x18022640e  call    cs:__imp_OpenProcess
0x180226415  nop     dword ptr [rax+rax+00h]
0x18022641a  mov     [rsp+4A8h+var_468], rax
0x18022641f  lea     rcx, [rax+1]
0x180226423  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18022642a  jnz     short loc_1802264A6
0x18022642c  mov     eax, cs:dword_18042D328
0x180226432  cmp     eax, 5
0x180226435  jbe     short loc_180226491
0x180226437  lea     edx, [rbx+8]
0x18022643a  lea     rcx, dword_18042D328
0x180226441  call    _tlgKeywordOn
0x180226446  test    al, al
0x180226448  jz      short loc_180226491
0x18022644a  call    cs:__imp_GetLastError
0x180226451  nop     dword ptr [rax+rax+00h]
0x180226456  test    eax, eax
0x180226458  jle     short loc_180226462
0x18022645a  movzx   eax, ax
0x18022645d  or      eax, 80070000h
0x180226462  mov     dword ptr [rsp+4A8h+var_470], eax
0x180226466  mov     [rsp+4A8h+var_478], esi
0x18022646a  lea     rax, [rsp+4A8h+var_470]
0x18022646f  mov     [rsp+4A8h+var_480], rax
0x180226474  lea     rax, [rsp+4A8h+var_478]
0x180226479  mov     [rsp+4A8h+var_488], rax
0x18022647e  lea     rdx, unk_1803CF818
0x180226485  lea     rcx, dword_18042D328
0x18022648c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180226491  mov     [rdi+28h], bl
0x180226494  lea     rcx, [rsp+4A8h+var_468]
0x180226499  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18022649e  mov     rax, rdi
0x1802264a1  jmp     loc_18022666B
0x1802264a6  mov     r8d, 208h; nSize
0x1802264ac  lea     rdx, [rsp+4A8h+ImageFileName]; lpImageFileName
0x1802264b4  mov     rcx, rax; hProcess
0x1802264b7  call    cs:__imp_K32GetProcessImageFileNameW
0x1802264be  nop     dword ptr [rax+rax+00h]
0x1802264c3  test    eax, eax
0x1802264c5  jnz     loc_180226560
0x1802264cb  mov     rcx, [rsp+4A8h]; this
0x1802264d3  lea     r8, aOnecoreBaseTel_96; "onecore\\base\\telemetry\\utc\\service"...
0x1802264da  mov     edx, 1AFh; void *
0x1802264df  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1802264e4  mov     eax, cs:dword_18042D328
0x1802264ea  cmp     eax, 5
0x1802264ed  jbe     short loc_18022654B
0x1802264ef  mov     edx, 8
0x1802264f4  lea     rcx, dword_18042D328
0x1802264fb  call    _tlgKeywordOn
0x180226500  test    al, al
0x180226502  jz      short loc_18022654B
0x180226504  call    cs:__imp_GetLastError
0x18022650b  nop     dword ptr [rax+rax+00h]
0x180226510  test    eax, eax
0x180226512  jle     short loc_18022651C
0x180226514  movzx   eax, ax
0x180226517  or      eax, 80070000h
0x18022651c  mov     [rsp+4A8h+var_478], eax
0x180226520  mov     dword ptr [rsp+4A8h+var_470], esi
0x180226524  lea     rax, [rsp+4A8h+var_478]
0x180226529  mov     [rsp+4A8h+var_480], rax
0x18022652e  lea     rax, [rsp+4A8h+var_470]
0x180226533  mov     [rsp+4A8h+var_488], rax
0x180226538  lea     rdx, unk_1803CF86E
0x18022653f  lea     rcx, dword_18042D328
0x180226546  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18022654b  mov     [rdi+28h], bl
0x18022654e  lea     rcx, [rsp+4A8h+var_468]
0x180226553  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180226558  mov     rax, rdi
0x18022655b  jmp     loc_18022666B
0x180226560  lea     rcx, [rsp+4A8h+var_450]; void *
0x180226565  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18022656a  nop
0x18022656b  mov     [rsp+4A8h+var_430], esi
0x18022656f  lea     rcx, [rsp+4A8h+ImageFileName]; pszPath
0x180226577  call    cs:__imp_PathFindFileNameW
0x18022657e  nop     dword ptr [rax+rax+00h]
0x180226583  or      r8, 0FFFFFFFFFFFFFFFFh
0x180226587  inc     r8
0x18022658a  cmp     [rax+r8*2], bx
0x18022658f  jnz     short loc_180226587
0x180226591  mov     rdx, rax
0x180226594  lea     rcx, [rsp+4A8h+var_450]
0x180226599  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18022659e  mov     eax, cs:dword_18042D328
0x1802265a4  cmp     eax, 5
0x1802265a7  jbe     short loc_1802265F8
0x1802265a9  mov     edx, 8
0x1802265ae  lea     rcx, dword_18042D328
0x1802265b5  call    _tlgKeywordOn
0x1802265ba  test    al, al
0x1802265bc  jz      short loc_1802265F8
0x1802265be  lea     rax, [rsp+4A8h+var_450]
0x1802265c3  cmp     qword ptr [rsp+4A8h+var_440+8], 7
0x1802265c9  cmova   rax, [rsp+4A8h+var_450]
0x1802265cf  mov     [rsp+4A8h+var_470], rax
0x1802265d4  mov     [rsp+4A8h+var_478], esi
0x1802265d8  lea     rax, [rsp+4A8h+var_470]
0x1802265dd  mov     [rsp+4A8h+var_480], rax
0x1802265e2  lea     rax, [rsp+4A8h+var_478]
0x1802265e7  mov     [rsp+4A8h+var_488], rax
0x1802265ec  lea     rdx, unk_1803CF785
0x1802265f3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1802265f8  xorps   xmm0, xmm0
0x1802265fb  movups  xmmword ptr [rdi], xmm0
0x1802265fe  mov     rax, [rsp+4A8h+var_450]
0x180226603  mov     [rdi], rax
0x180226606  mov     rax, [rsp+4A8h+var_448]
0x18022660b  mov     [rdi+8], rax
0x18022660f  mov     rax, qword ptr [rsp+4A8h+var_440]
0x180226614  mov     [rdi+10h], rax
0x180226618  mov     rax, qword ptr [rsp+4A8h+var_440+8]
0x18022661d  mov     [rdi+18h], rax
0x180226621  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180226629  movdqu  [rsp+4A8h+var_440], xmm0
0x18022662f  mov     word ptr [rsp+4A8h+var_450], bx
0x180226634  mov     eax, [rsp+4A8h+var_430]
0x180226638  mov     [rdi+20h], eax
0x18022663b  mov     byte ptr [rdi+28h], 1
0x18022663f  lea     rcx, [rsp+4A8h+var_450]; this
0x180226644  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180226649  nop
0x18022664a  lea     rcx, [rsp+4A8h+var_468]
0x18022664f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180226654  mov     rax, rdi
0x180226657  jmp     short loc_18022666B
0x180226659  mov     [rcx+28h], bl
0x18022665c  mov     rax, rdi
0x18022665f  jmp     short loc_18022666B
0x180226661  xor     ebx, ebx
0x180226663  mov     rax, [rsp+4A8h+var_458]
0x180226668  mov     [rax+28h], bl
0x18022666b  mov     rcx, [rsp+4A8h+var_18]
0x180226673  xor     rcx, rsp; StackCookie
0x180226676  call    __security_check_cookie
0x18022667b  lea     r11, [rsp+4A8h+var_8]
0x180226683  mov     rbx, [r11+20h]
0x180226687  mov     rsi, [r11+28h]
0x18022668b  mov     rsp, r11
0x18022668e  pop     rdi
0x18022668f  retn
```

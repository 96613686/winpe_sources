# CNtService::Run(ushort *,ulong,ushort * *,void *)

- ea: `0x180005a60`
- end: `0x180005f0e`
- name: `?Run@CNtService@@UEAAKPEAGKPEAPEAGPEAX@Z`
- size: `1198`
- prototype: `__int64 __fastcall(CNtService *this, unsigned __int16 *, unsigned int, unsigned __int16 **, void *lpContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800062c8`

## callees

- `0x180004120`
- `0x180005a60`
- `0x18000ae04`
- `0x180010740`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ed3`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x180005ddd`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x180005ddd`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x180005e7b`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x180005e7b`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x180005e5b`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x180005e5b`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x180005c70`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x180005c70`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x180005c4c`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x180005c4c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005ab0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005c27`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005ab0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005c27`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005b4f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005bd2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005ec9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005b4f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005bd2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005ec9`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005aea`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005aea`

## string_xrefs

- `0x180005b11`: `Initial call to RegisterServiceCtrlHandler failed`
- `0x180005b65`: `Could not SetServiceStatus`
- `0x180005be8`: `Could not SetServiceStatus`
- `0x180005edc`: `Could not SetServiceStatus`

## pseudocode

```c
__int64 __fastcall CNtService::Run(
        CNtService *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4,
        void *lpContext)
{
  CNtService *v8; // rbx
  __int64 v9; // rax
  unsigned __int64 v10; // r14
  unsigned __int16 *v11; // rax
  SERVICE_STATUS_HANDLE v13; // rax
  SERVICE_STATUS_HANDLE *v14; // r15
  DWORD LastError; // r14d
  CEventLog *v16; // rax
  CEventLog *v17; // rsi
  CInsertionString *v18; // r12
  CInsertionString *v19; // r13
  __int64 v20; // rax
  unsigned int v21; // edx
  CEventLog *v22; // [rsp+70h] [rbp-168h]
  SERVICE_STATUS_HANDLE *v23; // [rsp+78h] [rbp-160h]
  CInsertionString *v24; // [rsp+80h] [rbp-158h]
  CInsertionString *v25; // [rsp+90h] [rbp-148h]
  CInsertionString *v26; // [rsp+98h] [rbp-140h]
  CInsertionString *v27; // [rsp+A0h] [rbp-138h]
  CInsertionString *v28; // [rsp+A8h] [rbp-130h]
  CInsertionString *v29; // [rsp+B0h] [rbp-128h]
  CInsertionString *v30; // [rsp+B8h] [rbp-120h]
  _BYTE v31[16]; // [rsp+110h] [rbp-C8h] BYREF
  _BYTE v32[16]; // [rsp+120h] [rbp-B8h] BYREF
  _BYTE v33[16]; // [rsp+130h] [rbp-A8h] BYREF
  _BYTE v34[16]; // [rsp+140h] [rbp-98h] BYREF
  _BYTE v35[16]; // [rsp+150h] [rbp-88h] BYREF
  _BYTE v36[16]; // [rsp+160h] [rbp-78h] BYREF
  _BYTE v37[16]; // [rsp+170h] [rbp-68h] BYREF
  _BYTE v38[16]; // [rsp+180h] [rbp-58h] BYREF
  _BYTE v39[16]; // [rsp+190h] [rbp-48h] BYREF
  _BYTE v40[16]; // [rsp+1A0h] [rbp-38h] BYREF

  v8 = this;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = v9 + 1;
  v11 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v9 + 1, 2u));
  *((_QWORD *)v8 + 2) = v11;
  if ( !v11 )
    return 8;
  StringCchCopyW(v11, v10, a2);
  v13 = RegisterServiceCtrlHandlerExW(*((LPCWSTR *)v8 + 2), (LPHANDLER_FUNCTION_EX)CNtService::_HandlerEx, lpContext);
  v14 = (SERVICE_STATUS_HANDLE *)((char *)v8 + 56);
  v23 = (SERVICE_STATUS_HANDLE *)((char *)v8 + 56);
  *((_QWORD *)v8 + 7) = v13;
  if ( v13 )
  {
    *((_DWORD *)v8 + 7) = 32;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 4) = 2;
    *((_DWORD *)v8 + 12) = 1;
    *((_DWORD *)v8 + 13) = 120000;
    if ( !SetServiceStatus(v13, (LPSERVICE_STATUS)v8 + 1) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(CNtService *, const wchar_t *))(*(_QWORD *)v8 + 56LL))(v8, L"Could not SetServiceStatus");
      if ( LastError )
        goto LABEL_25;
    }
    LastError = (*(__int64 (__fastcall **)(CNtService *, _QWORD, unsigned __int16 **))(*(_QWORD *)v8 + 24LL))(
                  v8,
                  a3,
                  a4);
    if ( LastError )
    {
      (*(void (__fastcall **)(CNtService *, const wchar_t *))(*(_QWORD *)v8 + 56LL))(
        v8,
        L"Initialize call failed, bailing out");
LABEL_25:
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v16 = (CEventLog *)CWin32DefaultArena::WbemMemAlloc(0x58u);
        if ( v16 )
        {
          v17 = CEventLog::CEventLog(v16, 0, (const struct _GUID *)S_WinMgmtR, 0xAu);
          v22 = v17;
        }
        else
        {
          v17 = 0;
          v22 = 0;
        }
        if ( v17 )
        {
          CEventLog::Open(v17);
          if ( __eh34_try(0, 1) )
          {
            __eh34_scope_strut(1);
            v18 = CInsertionString::CInsertionString((CInsertionString *)v31);
            v19 = CInsertionString::CInsertionString((CInsertionString *)v32);
            v25 = CInsertionString::CInsertionString((CInsertionString *)v33);
            v26 = CInsertionString::CInsertionString((CInsertionString *)v34);
            v27 = CInsertionString::CInsertionString((CInsertionString *)v35);
            v28 = CInsertionString::CInsertionString((CInsertionString *)v36);
            v29 = CInsertionString::CInsertionString((CInsertionString *)v37);
            v30 = CInsertionString::CInsertionString((CInsertionString *)v38);
            v24 = CInsertionString::CInsertionString((CInsertionString *)v39);
            v20 = CInsertionString::CInsertionString(v40, LastError);
            CEventLog::Report(
              v17,
              1,
              WBEM_MC_WBEM_SERVICE_INIT_FAILURE,
              v20,
              v24,
              v30,
              v29,
              v28,
              v27,
              v26,
              v25,
              v19,
              v18);
          }
          if ( __eh34_catch(1) )
          {
            if ( __eh34_catch_type(1, &CX_MemoryException `RTTI Type Descriptor', 0) )
            {
              v8 = this;
              v17 = v22;
              v14 = v23;
              __eh34_try_continuation(1, &CX_MemoryException `RTTI Type Descriptor', &loc_180005E64);
            }
          }
          CEventLog::Close(v17);
          CEventLog::`scalar deleting destructor'(v17, v21);
        }
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
        {
          v8 = this;
          v14 = v23;
          __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_180005E8C);
        }
      }
      goto LABEL_22;
    }
    *((_DWORD *)v8 + 9) = *((_DWORD *)v8 + 6) | 5;
    *((_DWORD *)v8 + 8) = 4;
    *((_DWORD *)v8 + 10) = 0;
    *((_QWORD *)v8 + 6) = 0;
    if ( !SetServiceStatus(*v14, (LPSERVICE_STATUS)v8 + 1) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(CNtService *, const wchar_t *))(*(_QWORD *)v8 + 56LL))(v8, L"Could not SetServiceStatus");
      if ( LastError )
        goto LABEL_25;
    }
    *((_DWORD *)v8 + 2) = 1;
    LastError = (*(__int64 (__fastcall **)(CNtService *))(*(_QWORD *)v8 + 8LL))(v8);
  }
  else
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(CNtService *, const wchar_t *))(*(_QWORD *)v8 + 56LL))(
      v8,
      L"Initial call to RegisterServiceCtrlHandler failed");
  }
  if ( LastError )
    goto LABEL_25;
LABEL_22:
  *((_DWORD *)v8 + 2) = 0;
  (*(void (__fastcall **)(CNtService *))(*(_QWORD *)v8 + 32LL))(v8);
  *((_DWORD *)v8 + 9) = 0;
  *((_DWORD *)v8 + 8) = 1;
  *((_DWORD *)v8 + 10) = 0;
  *((_QWORD *)v8 + 6) = 0;
  if ( !SetServiceStatus(*v14, (LPSERVICE_STATUS)v8 + 1) )
  {
    GetLastError();
    (*(void (__fastcall **)(CNtService *, const wchar_t *))(*(_QWORD *)v8 + 56LL))(v8, L"Could not SetServiceStatus");
  }
  return 0;
}

```

## disassembly

```asm
0x180005a60  mov     [rsp+arg_8], rbx
0x180005a65  mov     [rsp+arg_10], rsi
0x180005a6a  mov     [rsp+arg_0], rcx
0x180005a6f  push    rdi
0x180005a70  push    r12
0x180005a72  push    r13
0x180005a74  push    r14
0x180005a76  push    r15
0x180005a78  sub     rsp, 1B0h
0x180005a7f  mov     r12, r9
0x180005a82  mov     r13d, r8d
0x180005a85  mov     rsi, rdx
0x180005a88  mov     rbx, rcx
0x180005a8b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180005a8f  mov     rax, rcx
0x180005a92  xor     edi, edi
0x180005a94  inc     rax
0x180005a97  cmp     [rdx+rax*2], di
0x180005a9b  jnz     short loc_180005A94
0x180005a9d  lea     r14, [rax+1]
0x180005aa1  mov     eax, 2
0x180005aa6  mul     r14
0x180005aa9  cmovb   rax, rcx
0x180005aad  mov     rcx, rax
0x180005ab0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180005ab6  mov     [rbx+10h], rax
0x180005aba  test    rax, rax
0x180005abd  jnz     short loc_180005AC9
0x180005abf  mov     eax, 8
0x180005ac4  jmp     loc_180005EF1
0x180005ac9  mov     r8, rsi; unsigned __int16 *
0x180005acc  mov     rdx, r14; unsigned __int64
0x180005acf  mov     rcx, rax; unsigned __int16 *
0x180005ad2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005ad7  mov     r8, [rsp+1D8h+lpContext]; lpContext
0x180005adf  lea     rdx, ?_HandlerEx@CNtService@@CAKKKPEAX0@Z; lpHandlerProc
0x180005ae6  mov     rcx, [rbx+10h]; lpServiceName
0x180005aea  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180005af0  lea     r15, [rbx+38h]
0x180005af4  mov     [rsp+1D8h+var_160], r15
0x180005af9  mov     [r15], rax
0x180005afc  test    rax, rax
0x180005aff  jnz     short loc_180005B25
0x180005b01  call    cs:__imp_GetLastError
0x180005b07  mov     r14d, eax
0x180005b0a  mov     rcx, [rbx]
0x180005b0d  mov     rax, [rcx+38h]
0x180005b11  lea     rdx, aInitialCallToR; "Initial call to RegisterServiceCtrlHand"...
0x180005b18  mov     rcx, rbx
0x180005b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b20  jmp     loc_180005C19
0x180005b25  lea     rsi, [rbx+1Ch]
0x180005b29  mov     dword ptr [rsi], 20h ; ' '
0x180005b2f  mov     [rbx+28h], rdi
0x180005b33  mov     qword ptr [rbx+20h], 2
0x180005b3b  mov     dword ptr [rbx+30h], 1
0x180005b42  mov     dword ptr [rbx+34h], 1D4C0h
0x180005b49  mov     rdx, rsi; lpServiceStatus
0x180005b4c  mov     rcx, rax; hServiceStatus
0x180005b4f  call    cs:__imp_SetServiceStatus
0x180005b55  test    eax, eax
0x180005b57  jnz     short loc_180005B81
0x180005b59  call    cs:__imp_GetLastError
0x180005b5f  mov     r14d, eax
0x180005b62  mov     rax, [rbx]
0x180005b65  lea     rdx, aCouldNotSetser; "Could not SetServiceStatus"
0x180005b6c  mov     rcx, rbx
0x180005b6f  mov     rax, [rax+38h]
0x180005b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b78  test    r14d, r14d
0x180005b7b  jnz     loc_180005C22
0x180005b81  mov     rax, [rbx]
0x180005b84  mov     r8, r12
0x180005b87  mov     edx, r13d
0x180005b8a  mov     rcx, rbx
0x180005b8d  mov     rax, [rax+18h]
0x180005b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b96  mov     r14d, eax
0x180005b99  test    eax, eax
0x180005b9b  jz      short loc_180005BB5
0x180005b9d  mov     rax, [rbx]
0x180005ba0  lea     rdx, aInitializeCall; "Initialize call failed, bailing out"
0x180005ba7  mov     rcx, rbx
0x180005baa  mov     rax, [rax+38h]
0x180005bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb3  jmp     short loc_180005C22
0x180005bb5  mov     eax, [rbx+18h]
0x180005bb8  or      eax, 5
0x180005bbb  mov     [rbx+24h], eax
0x180005bbe  mov     dword ptr [rbx+20h], 4
0x180005bc5  mov     [rbx+28h], edi
0x180005bc8  mov     [rbx+30h], rdi
0x180005bcc  mov     rdx, rsi; lpServiceStatus
0x180005bcf  mov     rcx, [r15]; hServiceStatus
0x180005bd2  call    cs:__imp_SetServiceStatus
0x180005bd8  test    eax, eax
0x180005bda  jnz     short loc_180005C00
0x180005bdc  call    cs:__imp_GetLastError
0x180005be2  mov     r14d, eax
0x180005be5  mov     rax, [rbx]
0x180005be8  lea     rdx, aCouldNotSetser; "Could not SetServiceStatus"
0x180005bef  mov     rcx, rbx
0x180005bf2  mov     rax, [rax+38h]
0x180005bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bfb  test    r14d, r14d
0x180005bfe  jnz     short loc_180005C22
0x180005c00  mov     dword ptr [rbx+8], 1
0x180005c07  mov     rax, [rbx]
0x180005c0a  mov     rcx, rbx
0x180005c0d  mov     rax, [rax+8]
0x180005c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c16  mov     r14d, eax
0x180005c19  test    r14d, r14d
0x180005c1c  jz      loc_180005E9B
0x180005c22  mov     ecx, 58h ; 'X'
0x180005c27  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180005c2d  mov     [rsp+1D8h+var_158], rax
0x180005c35  test    rax, rax
0x180005c38  jz      short loc_180005C5C
0x180005c3a  mov     r9d, 0Ah
0x180005c40  lea     r8, S_WinMgmtR
0x180005c47  xor     edx, edx
0x180005c49  mov     rcx, rax
0x180005c4c  call    cs:__imp_??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z; CEventLog::CEventLog(ushort const *,_GUID const &,ulong)
0x180005c52  mov     rsi, rax
0x180005c55  mov     [rsp+1D8h+var_168], rax
0x180005c5a  jmp     short loc_180005C64
0x180005c5c  mov     rsi, rdi
0x180005c5f  mov     [rsp+1D8h+var_168], rdi
0x180005c64  test    rsi, rsi
0x180005c67  jz      loc_180005E8A
0x180005c6d  mov     rcx, rsi
0x180005c70  call    cs:__imp_?Open@CEventLog@@QEAAHXZ; CEventLog::Open(void)
0x180005c76  nop
0x180005c77  lea     rax, [rsp+1D8h+var_C8]
0x180005c7f  mov     [rsp+1D8h+var_118], rax
0x180005c87  lea     rcx, [rsp+1D8h+var_C8]; this
0x180005c8f  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180005c94  mov     r12, rax
0x180005c97  lea     rax, [rsp+1D8h+var_B8]
0x180005c9f  mov     [rsp+1D8h+var_110], rax
0x180005ca7  lea     rcx, [rsp+1D8h+var_B8]; this
0x180005caf  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180005cb4  mov     r13, rax
0x180005cb7  lea     rax, [rsp+1D8h+var_A8]
0x180005cbf  mov     [rsp+1D8h+var_108], rax
0x180005cc7  lea     rcx, [rsp+1D8h+var_A8]; this
0x180005ccf  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180005cd4  mov     [rsp+1D8h+var_148], rax
0x180005cdc  lea     rax, [rsp+1D8h+var_98]
0x180005ce4  mov     [rsp+1D8h+var_100], rax
0x180005cec  lea     rcx, [rsp+1D8h+var_98]; this
0x180005cf4  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180005cf9  mov     [rsp+1D8h+var_140], rax
0x180005d01  lea     rax, [rsp+1D8h+var_88]
0x180005d09  mov     [rsp+1D8h+var_F8], rax
0x180005d11  lea     rcx, [rsp+1D8h+var_88]; this
0x180005d19  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180005d1e  mov     [rsp+1D8h+var_138], rax
0x180005d26  lea     rax, [rsp+1D8h+var_78]
0x180005d2e  mov     [rsp+1D8h+var_F0], rax
0x180005d36  lea     rcx, [rsp+1D8h+var_78]; this
0x180005d3e  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180005d43  mov     [rsp+1D8h+var_130], rax
0x180005d4b  lea     rax, [rsp+1D8h+var_68]
0x180005d53  mov     [rsp+1D8h+var_E8], rax
0x180005d5b  lea     rcx, [rsp+1D8h+var_68]; this
0x180005d63  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180005d68  mov     [rsp+1D8h+var_128], rax
0x180005d70  lea     rax, [rsp+1D8h+var_58]
0x180005d78  mov     [rsp+1D8h+var_E0], rax
0x180005d80  lea     rcx, [rsp+1D8h+var_58]; this
0x180005d88  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180005d8d  mov     [rsp+1D8h+var_120], rax
0x180005d95  lea     rax, [rsp+1D8h+var_48]
0x180005d9d  mov     [rsp+1D8h+var_D8], rax
0x180005da5  lea     rcx, [rsp+1D8h+var_48]; this
0x180005dad  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180005db2  mov     [rsp+1D8h+var_158], rax
0x180005dba  lea     rax, [rsp+1D8h+var_38]
0x180005dc2  mov     [rsp+1D8h+var_D0], rax
0x180005dca  mov     [rsp+1D8h+var_150], r14d
0x180005dd2  mov     edx, r14d
0x180005dd5  lea     rcx, [rsp+1D8h+var_38]
0x180005ddd  call    cs:__imp_??0CInsertionString@@QEAA@VCHex@@@Z; CInsertionString::CInsertionString(CHex)
0x180005de3  nop
0x180005de4  mov     edx, 1
0x180005de9  mov     [rsp+1D8h+var_178], r12
0x180005dee  mov     [rsp+1D8h+var_180], r13
0x180005df3  mov     rcx, [rsp+1D8h+var_148]
0x180005dfb  mov     [rsp+1D8h+var_188], rcx
0x180005e00  mov     rcx, [rsp+1D8h+var_140]
0x180005e08  mov     [rsp+1D8h+var_190], rcx
0x180005e0d  mov     rcx, [rsp+1D8h+var_138]
0x180005e15  mov     [rsp+1D8h+var_198], rcx
0x180005e1a  mov     rcx, [rsp+1D8h+var_130]
0x180005e22  mov     [rsp+1D8h+var_1A0], rcx
0x180005e27  mov     rcx, [rsp+1D8h+var_128]
0x180005e2f  mov     [rsp+1D8h+var_1A8], rcx
0x180005e34  mov     rcx, [rsp+1D8h+var_120]
0x180005e3c  mov     [rsp+1D8h+var_1B0], rcx
0x180005e41  mov     rcx, [rsp+1D8h+var_158]
0x180005e49  mov     [rsp+1D8h+var_1B8], rcx
0x180005e4e  mov     r9, rax
0x180005e51  lea     r8, WBEM_MC_WBEM_SERVICE_INIT_FAILURE
0x180005e58  mov     rcx, rsi
0x180005e5b  call    cs:__imp_?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CEventLog::Report(ushort,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x180005e61  nop
0x180005e62  jmp     short loc_180005E78
0x180005e64  xor     edi, edi
0x180005e66  mov     rbx, [rsp+1D8h+arg_0]
0x180005e6e  mov     rsi, [rsp+1D8h+var_168]
0x180005e73  mov     r15, [rsp+1D8h+var_160]
0x180005e78  mov     rcx, rsi
0x180005e7b  call    cs:__imp_?Close@CEventLog@@QEAAHXZ; CEventLog::Close(void)
0x180005e81  mov     rcx, rsi; this
0x180005e84  call    ??_GCEventLog@@QEAAPEAXI@Z; CEventLog::`scalar deleting destructor'(uint)
0x180005e89  nop
0x180005e8a  jmp     short loc_180005E9B
0x180005e8c  xor     edi, edi
0x180005e8e  mov     rbx, [rsp+1D8h+arg_0]
0x180005e96  mov     r15, [rsp+1D8h+var_160]
0x180005e9b  mov     [rbx+8], edi
0x180005e9e  mov     rax, [rbx]
0x180005ea1  mov     rcx, rbx
0x180005ea4  mov     rax, [rax+20h]
0x180005ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ead  lea     rdx, [rbx+1Ch]; lpServiceStatus
0x180005eb1  mov     [rdx+8], edi
0x180005eb4  mov     dword ptr [rbx+20h], 1
0x180005ebb  mov     [rbx+28h], edi
0x180005ebe  mov     qword ptr [rbx+30h], 0
0x180005ec6  mov     rcx, [r15]; hServiceStatus
0x180005ec9  call    cs:__imp_SetServiceStatus
0x180005ecf  test    eax, eax
0x180005ed1  jnz     short loc_180005EEF
0x180005ed3  call    cs:__imp_GetLastError
0x180005ed9  mov     rax, [rbx]
0x180005edc  lea     rdx, aCouldNotSetser; "Could not SetServiceStatus"
0x180005ee3  mov     rcx, rbx
0x180005ee6  mov     rax, [rax+38h]
0x180005eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eef  xor     eax, eax
0x180005ef1  lea     r11, [rsp+1D8h+var_28]
0x180005ef9  mov     rbx, [r11+38h]
0x180005efd  mov     rsi, [r11+40h]
0x180005f01  mov     rsp, r11
0x180005f04  pop     r15
0x180005f06  pop     r14
0x180005f08  pop     r13
0x180005f0a  pop     r12
0x180005f0c  pop     rdi
0x180005f0d  retn
```

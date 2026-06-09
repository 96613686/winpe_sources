# SupplementalCredentialsManager::StartWorkerThread(void)

- ea: `0x18003d634`
- end: `0x18003d71c`
- name: `?StartWorkerThread@SupplementalCredentialsManager@@AEAAXXZ`
- size: `232`
- prototype: `void __fastcall(SupplementalCredentialsManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18003bef4`

## callees

- `0x180001008`
- `0x18001a280`
- `0x18003a8d4`
- `0x18003c134`
- `0x18003c664`
- `0x18003d634`
- `0x18003e238`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d6b5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003d6a8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003d6a8`

## string_xrefs

- `0x18003d65a`: `Starting working thread`
- `0x18003d6cb`: `CreateThread failed. Error = `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SupplementalCredentialsManager::StartWorkerThread(SupplementalCredentialsManager *this)
{
  DWORD LastError; // eax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rcx
  const char *v6; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v8[32]; // [rsp+58h] [rbp-30h] BYREF

  if ( (unsigned int)dword_180084170 > 4 )
  {
    v6 = "Starting working thread";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_180084170,
      (unsigned int)byte_18007A951,
      0,
      0,
      (__int64)&v6);
  }
  *((_QWORD *)this + 199) = CreateThread(0, 0, SupplementalCredentialsManager::UpdateSupplementalCredentials, 0, 0, 0);
  LastError = GetLastError();
  v3 = std::to_string(v8, LastError);
  v4 = std::operator+<char>(v7, "CreateThread failed. Error = ", v3);
  LOBYTE(v5) = *((_QWORD *)this + 199) != 0;
  CHECK_BOOL_THROW_SUPCREDEXCEPTION(v5, v4);
  std::string::~string(v7);
  std::string::~string(v8);
}

```

## disassembly

```asm
0x18003d634  push    rbx
0x18003d636  sub     rsp, 80h
0x18003d63d  mov     rax, cs:__security_cookie
0x18003d644  xor     rax, rsp
0x18003d647  mov     [rsp+88h+var_10], rax
0x18003d64c  mov     rbx, rcx
0x18003d64f  mov     eax, cs:dword_180084170
0x18003d655  cmp     eax, 4
0x18003d658  jbe     short loc_18003D689
0x18003d65a  lea     rax, aStartingWorkin; "Starting working thread"
0x18003d661  mov     [rsp+88h+var_58], rax
0x18003d666  lea     rax, [rsp+88h+var_58]
0x18003d66b  mov     qword ptr [rsp+88h+dwCreationFlags], rax
0x18003d670  xor     r9d, r9d
0x18003d673  xor     r8d, r8d
0x18003d676  lea     rdx, byte_18007A951
0x18003d67d  lea     rcx, dword_180084170
0x18003d684  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d689  mov     [rsp+88h+lpThreadId], 0; lpThreadId
0x18003d692  mov     [rsp+88h+dwCreationFlags], 0; dwCreationFlags
0x18003d69a  xor     r9d, r9d; lpParameter
0x18003d69d  lea     r8, ?UpdateSupplementalCredentials@SupplementalCredentialsManager@@SAKPEAX@Z; lpStartAddress
0x18003d6a4  xor     edx, edx; dwStackSize
0x18003d6a6  xor     ecx, ecx; lpThreadAttributes
0x18003d6a8  call    cs:__imp_CreateThread
0x18003d6ae  mov     [rbx+638h], rax
0x18003d6b5  call    cs:__imp_GetLastError
0x18003d6bb  mov     edx, eax
0x18003d6bd  lea     rcx, [rsp+88h+var_30]
0x18003d6c2  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@K@Z; std::to_string(ulong)
0x18003d6c7  nop
0x18003d6c8  mov     r8, rax
0x18003d6cb  lea     rdx, aCreatethreadFa; "CreateThread failed. Error = "
0x18003d6d2  lea     rcx, [rsp+88h+var_50]
0x18003d6d7  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18003d6dc  nop
0x18003d6dd  cmp     qword ptr [rbx+638h], 0
0x18003d6e5  setnz   cl
0x18003d6e8  mov     rdx, rax
0x18003d6eb  call    ?CHECK_BOOL_THROW_SUPCREDEXCEPTION@@YAX_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CHECK_BOOL_THROW_SUPCREDEXCEPTION(bool,std::string const &)
0x18003d6f0  nop
0x18003d6f1  lea     rcx, [rsp+88h+var_50]
0x18003d6f6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003d6fb  nop
0x18003d6fc  lea     rcx, [rsp+88h+var_30]
0x18003d701  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003d706  mov     rcx, [rsp+88h+var_10]
0x18003d70b  xor     rcx, rsp; StackCookie
0x18003d70e  call    __security_check_cookie
0x18003d713  add     rsp, 80h
0x18003d71a  pop     rbx
0x18003d71b  retn
```

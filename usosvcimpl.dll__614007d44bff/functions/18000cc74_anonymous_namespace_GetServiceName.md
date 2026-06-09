# _anonymous_namespace_::GetServiceName

- ea: `0x18000cc74`
- end: `0x18000ce91`
- name: `_anonymous_namespace_::GetServiceName`
- size: `541`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18000ceb8`

## callees

- `0x18000cc74`
- `0x18000f03c`
- `0x18000f0b8`
- `0x1800108b4`
- `0x180010f24`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd1f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000ccb6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000ccb6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000ce01`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000ce01`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18000cd15`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18000cd9e`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18000cd15`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18000cd9e`

## string_xrefs

- `0x18000cde4`: `Unknown service`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall anonymous_namespace_::GetServiceName(_QWORD *a1, int a2)
{
  SC_HANDLE v4; // rbx
  const char *v5; // r9
  const char *v6; // r9
  bool v7; // zf
  char v8; // al
  DWORD cbBufSize; // edi
  const char *v10; // r9
  unsigned __int64 v11; // rax
  LPBYTE v12; // rcx
  unsigned __int64 v13; // r8
  const wchar_t *v14; // rdx
  DWORD ResumeHandle; // [rsp+60h] [rbp+7h] BYREF
  DWORD pcbBytesNeeded; // [rsp+64h] [rbp+Bh] BYREF
  DWORD ServicesReturned[2]; // [rsp+68h] [rbp+Fh] BYREF
  LPBYTE lpServices[2]; // [rsp+70h] [rbp+17h] BYREF
  __int64 v20; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *(_QWORD *)ServicesReturned = a1;
  v4 = OpenSCManagerW(0, 0, 4u);
  if ( !v4 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xF7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Orchestrator.cpp",
      v5);
  pcbBytesNeeded = 0;
  ServicesReturned[0] = 0;
  ResumeHandle = 0;
  if ( EnumServicesStatusExW(
         v4,
         SC_ENUM_PROCESS_INFO,
         0x30u,
         3u,
         0,
         0,
         &pcbBytesNeeded,
         ServicesReturned,
         &ResumeHandle,
         0)
    || (v7 = GetLastError() == 234, v8 = 1, v7) )
  {
    v8 = 0;
  }
  if ( v8 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xFE,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Orchestrator.cpp",
      v6);
  cbBufSize = 2 * pcbBytesNeeded;
  *(_OWORD *)lpServices = 0;
  v20 = 0;
  std::vector<unsigned char>::vector<unsigned char>(lpServices, 2 * pcbBytesNeeded);
  ResumeHandle = 0;
  if ( !EnumServicesStatusExW(
          v4,
          SC_ENUM_PROCESS_INFO,
          0x30u,
          3u,
          lpServices[0],
          cbBufSize,
          &pcbBytesNeeded,
          ServicesReturned,
          &ResumeHandle,
          0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x107,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Orchestrator.cpp",
      v10);
  v11 = 0;
  if ( ServicesReturned[0] )
  {
    v12 = lpServices[0] + 44;
    while ( a2 != *(_DWORD *)v12 )
    {
      ++v11;
      v12 += 56;
      if ( v11 >= ServicesReturned[0] )
        goto LABEL_11;
    }
    v14 = *(const wchar_t **)&lpServices[0][56 * v11];
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 0;
    v13 = -1;
    do
      ++v13;
    while ( v14[v13] );
  }
  else
  {
LABEL_11:
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 0;
    v13 = 15;
    v14 = L"Unknown service";
  }
  std::wstring::_Construct<1,wchar_t const *>(a1, v14, v13);
  std::vector<enum std::byte>::~vector<enum std::byte>(lpServices);
  CloseServiceHandle(v4);
  return a1;
}

```

## disassembly

```asm
0x18000cc74  mov     [rsp-8+arg_8], rbx
0x18000cc79  mov     [rsp-8+arg_10], rsi
0x18000cc7e  push    rbp
0x18000cc7f  push    rdi
0x18000cc80  push    r12
0x18000cc82  push    r14
0x18000cc84  push    r15
0x18000cc86  lea     rbp, [rsp-37h]
0x18000cc8b  sub     rsp, 90h
0x18000cc92  mov     rax, cs:__security_cookie
0x18000cc99  xor     rax, rsp
0x18000cc9c  mov     [rbp+57h+var_28], rax
0x18000cca0  mov     r15d, edx
0x18000cca3  mov     rsi, rcx
0x18000cca6  mov     qword ptr [rbp+57h+ServicesReturned], rcx
0x18000ccaa  xor     r12d, r12d
0x18000ccad  xor     edx, edx; lpDatabaseName
0x18000ccaf  xor     ecx, ecx; lpMachineName
0x18000ccb1  lea     r8d, [r12+4]; dwDesiredAccess
0x18000ccb6  call    cs:__imp_OpenSCManagerW
0x18000ccbc  mov     rbx, rax
0x18000ccbf  mov     [rbp+57h+var_58], rax
0x18000ccc3  mov     rcx, [rbp+5Fh]; this
0x18000ccc7  test    rax, rax
0x18000ccca  jz      loc_18000CE6D
0x18000ccd0  mov     [rbp+57h+var_4C], r12d
0x18000ccd4  mov     [rbp+57h+ServicesReturned], r12d
0x18000ccd8  mov     [rbp+57h+ResumeHandle], r12d
0x18000ccdc  mov     [rsp+0B0h+pszGroupName], r12; pszGroupName
0x18000cce1  lea     rax, [rbp+57h+ResumeHandle]
0x18000cce5  mov     [rsp+0B0h+lpResumeHandle], rax; lpResumeHandle
0x18000ccea  lea     rax, [rbp+57h+ServicesReturned]
0x18000ccee  mov     [rsp+0B0h+lpServicesReturned], rax; lpServicesReturned
0x18000ccf3  lea     rax, [rbp+57h+var_4C]
0x18000ccf7  mov     [rsp+0B0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000ccfc  mov     [rsp+0B0h+cbBufSize], r12d; cbBufSize
0x18000cd01  mov     [rsp+0B0h+lpServices], r12; lpServices
0x18000cd06  xor     edx, edx; InfoLevel
0x18000cd08  lea     r9d, [r12+3]; dwServiceState
0x18000cd0d  lea     r8d, [r12+30h]; dwServiceType
0x18000cd12  mov     rcx, rbx; hSCManager
0x18000cd15  call    cs:__imp_EnumServicesStatusExW
0x18000cd1b  test    eax, eax
0x18000cd1d  jnz     short loc_18000CD2E
0x18000cd1f  call    cs:__imp_GetLastError
0x18000cd25  cmp     eax, 0EAh
0x18000cd2a  mov     al, 1
0x18000cd2c  jnz     short loc_18000CD31
0x18000cd2e  mov     al, r12b
0x18000cd31  mov     rcx, [rbp+5Fh]; this
0x18000cd35  test    al, al
0x18000cd37  jnz     loc_18000CE7F
0x18000cd3d  mov     eax, [rbp+57h+var_4C]
0x18000cd40  lea     edi, [rax+rax]
0x18000cd43  xorps   xmm0, xmm0
0x18000cd46  xor     eax, eax
0x18000cd48  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18000cd4c  mov     [rbp+57h+var_30], rax
0x18000cd50  mov     edx, edi
0x18000cd52  lea     rcx, [rbp+57h+var_40]
0x18000cd56  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18000cd5b  nop
0x18000cd5c  mov     [rbp+57h+ResumeHandle], r12d
0x18000cd60  mov     rax, [rbp+57h+var_40]
0x18000cd64  mov     r14, [rbp+5Fh]
0x18000cd68  mov     [rsp+0B0h+pszGroupName], r12; pszGroupName
0x18000cd6d  lea     rcx, [rbp+57h+ResumeHandle]
0x18000cd71  mov     [rsp+0B0h+lpResumeHandle], rcx; lpResumeHandle
0x18000cd76  lea     rcx, [rbp+57h+ServicesReturned]
0x18000cd7a  mov     [rsp+0B0h+lpServicesReturned], rcx; lpServicesReturned
0x18000cd7f  lea     rcx, [rbp+57h+var_4C]
0x18000cd83  mov     [rsp+0B0h+pcbBytesNeeded], rcx; pcbBytesNeeded
0x18000cd88  mov     [rsp+0B0h+cbBufSize], edi; cbBufSize
0x18000cd8c  mov     [rsp+0B0h+lpServices], rax; lpServices
0x18000cd91  xor     edx, edx; InfoLevel
0x18000cd93  lea     r9d, [rdx+3]; dwServiceState
0x18000cd97  lea     r8d, [rdx+30h]; dwServiceType
0x18000cd9b  mov     rcx, rbx; hSCManager
0x18000cd9e  call    cs:__imp_EnumServicesStatusExW
0x18000cda4  test    eax, eax
0x18000cda6  jz      loc_18000CE58
0x18000cdac  mov     rax, r12
0x18000cdaf  mov     edx, [rbp+57h+ServicesReturned]
0x18000cdb2  test    rdx, rdx
0x18000cdb5  jz      short loc_18000CDD0
0x18000cdb7  mov     r8, [rbp+57h+var_40]
0x18000cdbb  lea     rcx, [r8+2Ch]
0x18000cdbf  cmp     r15d, [rcx]
0x18000cdc2  jz      short loc_18000CE32
0x18000cdc4  inc     rax
0x18000cdc7  add     rcx, 38h ; '8'
0x18000cdcb  cmp     rax, rdx
0x18000cdce  jb      short loc_18000CDBF
0x18000cdd0  xorps   xmm0, xmm0
0x18000cdd3  movups  xmmword ptr [rsi], xmm0
0x18000cdd6  mov     [rsi+10h], r12
0x18000cdda  mov     [rsi+18h], r12
0x18000cdde  mov     r8d, 0Fh
0x18000cde4  lea     rdx, aUnknownService; "Unknown service"
0x18000cdeb  mov     rcx, rsi
0x18000cdee  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000cdf3  nop
0x18000cdf4  lea     rcx, [rbp+57h+var_40]
0x18000cdf8  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x18000cdfd  nop
0x18000cdfe  mov     rcx, rbx; hSCObject
0x18000ce01  call    cs:__imp_CloseServiceHandle
0x18000ce07  mov     rax, rsi
0x18000ce0a  mov     rcx, [rbp+57h+var_28]
0x18000ce0e  xor     rcx, rsp; StackCookie
0x18000ce11  call    __security_check_cookie
0x18000ce16  lea     r11, [rsp+0B0h+var_20]
0x18000ce1e  mov     rbx, [r11+38h]
0x18000ce22  mov     rsi, [r11+40h]
0x18000ce26  mov     rsp, r11
0x18000ce29  pop     r15
0x18000ce2b  pop     r14
0x18000ce2d  pop     r12
0x18000ce2f  pop     rdi
0x18000ce30  pop     rbp
0x18000ce31  retn
0x18000ce32  imul    rax, 38h ; '8'
0x18000ce36  mov     rdx, [rax+r8]
0x18000ce3a  xorps   xmm0, xmm0
0x18000ce3d  movups  xmmword ptr [rsi], xmm0
0x18000ce40  mov     [rsi+10h], r12
0x18000ce44  mov     [rsi+18h], r12
0x18000ce48  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ce4c  inc     r8
0x18000ce4f  cmp     [rdx+r8*2], r12w
0x18000ce54  jnz     short loc_18000CE4C
0x18000ce56  jmp     short loc_18000CDEB
0x18000ce58  lea     r8, aCW1SSrcOrchest_14; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18000ce5f  mov     edx, 107h; void *
0x18000ce64  mov     rcx, r14; this
0x18000ce67  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18000ce6d  lea     r8, aCW1SSrcOrchest_14; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18000ce74  mov     edx, 0F7h; void *
0x18000ce79  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18000ce7f  lea     r8, aCW1SSrcOrchest_14; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18000ce86  mov     edx, 0FEh; void *
0x18000ce8b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

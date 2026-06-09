# _anonymous_namespace_::_dynamic_initializer_for__windiag_running_in_whesvc_context__

- ea: `0x1800024b0`
- end: `0x1800025aa`
- name: `_anonymous_namespace_::_dynamic_initializer_for__windiag_running_in_whesvc_context__`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800024b0`
- `0x180004510`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800024d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002564`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800024d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002564`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800024e1`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800024e1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180002501`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180002501`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000251d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000251d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002575`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000257e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002575`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000257e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000255a`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000255a`

## pseudocode

```c
int anonymous_namespace_::_dynamic_initializer_for__windiag_running_in_whesvc_context__()
{
  bool v0; // si
  DWORD CurrentProcessId; // eax
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  SC_HANDLE v4; // rdi
  DWORD pSessionId; // [rsp+30h] [rbp-48h] BYREF
  DWORD pcbBytesNeeded; // [rsp+34h] [rbp-44h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+58h] [rbp-20h]

  v0 = 0;
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  LODWORD(v2) = ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  if ( (_DWORD)v2 )
  {
    if ( !pSessionId )
    {
      v2 = OpenSCManagerW(0, 0, 1u);
      v3 = v2;
      if ( v2 )
      {
        v4 = OpenServiceW(v2, L"whesvc", 4u);
        if ( v4 )
        {
          pcbBytesNeeded = 0;
          v10 = 0;
          *(_OWORD *)Buffer = 0;
          v9 = 0;
          if ( QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
            v0 = HIDWORD(v9) == GetCurrentProcessId();
          CloseServiceHandle(v4);
        }
        LODWORD(v2) = CloseServiceHandle(v3);
      }
    }
  }
  byte_1800BEDF8 = v0;
  return (int)v2;
}

```

## disassembly

```asm
0x1800024b0  mov     [rsp+arg_0], rbx
0x1800024b5  mov     [rsp+arg_8], rsi
0x1800024ba  push    rdi
0x1800024bb  sub     rsp, 70h
0x1800024bf  mov     rax, cs:__security_cookie
0x1800024c6  xor     rax, rsp
0x1800024c9  mov     [rsp+78h+var_18], rax
0x1800024ce  xor     esi, esi
0x1800024d0  mov     [rsp+78h+pSessionId], esi
0x1800024d4  call    cs:__imp_GetCurrentProcessId
0x1800024da  mov     ecx, eax; dwProcessId
0x1800024dc  lea     rdx, [rsp+78h+pSessionId]; pSessionId
0x1800024e1  call    cs:__imp_ProcessIdToSessionId
0x1800024e7  test    eax, eax
0x1800024e9  jz      loc_180002584
0x1800024ef  cmp     [rsp+78h+pSessionId], esi
0x1800024f3  jnz     loc_180002584
0x1800024f9  xor     edx, edx; lpDatabaseName
0x1800024fb  lea     r8d, [rsi+1]; dwDesiredAccess
0x1800024ff  xor     ecx, ecx; lpMachineName
0x180002501  call    cs:__imp_OpenSCManagerW
0x180002507  mov     rbx, rax
0x18000250a  test    rax, rax
0x18000250d  jz      short loc_180002584
0x18000250f  lea     r8d, [rsi+4]; dwDesiredAccess
0x180002513  mov     rcx, rax; hSCManager
0x180002516  lea     rdx, ServiceName; "whesvc"
0x18000251d  call    cs:__imp_OpenServiceW
0x180002523  mov     rdi, rax
0x180002526  test    rax, rax
0x180002529  jz      short loc_18000257B
0x18000252b  xor     eax, eax
0x18000252d  mov     [rsp+78h+var_44], esi
0x180002531  xorps   xmm0, xmm0
0x180002534  mov     [rsp+78h+var_20], eax
0x180002538  lea     rax, [rsp+78h+var_44]
0x18000253d  xor     edx, edx; InfoLevel
0x18000253f  lea     r9d, [rsi+24h]; cbBufSize
0x180002543  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180002548  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x18000254d  mov     rcx, rdi; hService
0x180002550  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x180002555  movups  [rsp+78h+var_30], xmm0
0x18000255a  call    cs:__imp_QueryServiceStatusEx
0x180002560  test    eax, eax
0x180002562  jz      short loc_180002572
0x180002564  call    cs:__imp_GetCurrentProcessId
0x18000256a  cmp     dword ptr [rsp+78h+var_30+0Ch], eax
0x18000256e  setz    sil
0x180002572  mov     rcx, rdi; hSCObject
0x180002575  call    cs:__imp_CloseServiceHandle
0x18000257b  mov     rcx, rbx; hSCObject
0x18000257e  call    cs:__imp_CloseServiceHandle
0x180002584  mov     cs:byte_1800BEDF8, sil
0x18000258b  mov     rcx, [rsp+78h+var_18]
0x180002590  xor     rcx, rsp; StackCookie
0x180002593  call    __security_check_cookie
0x180002598  lea     r11, [rsp+78h+var_8]
0x18000259d  mov     rbx, [r11+10h]
0x1800025a1  mov     rsi, [r11+18h]
0x1800025a5  mov     rsp, r11
0x1800025a8  pop     rdi
0x1800025a9  retn
```

# StartServiceW(ushort const *,ulong,ushort const * *)

- ea: `0x1800c24e0`
- end: `0x1800c25ba`
- name: `?StartServiceW@@YAKPEBGKPEAPEBG@Z`
- size: `218`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800c26a0`
- `0x1800c27a8`

## callees

- `0x1800c24e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2583`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x1800c2570`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x1800c2570`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800c2549`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800c2549`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c2599`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c25a2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c2599`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c25a2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800c24f7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800c24f7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800c2522`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800c2522`

## pseudocode

```c
__int64 __fastcall StartServiceW(const unsigned __int16 *a1, __int64 a2, const unsigned __int16 **a3)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v6; // rdi
  unsigned __int8 i; // bl
  int v8; // eax

  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( v3 )
  {
    v6 = OpenServiceW(v3, L"IPxlatCfgSvc", 0x14u);
    if ( v6 )
    {
      for ( i = 0; i < 2u; ++i )
      {
        if ( !StartServiceW(v6, 0, 0) && GetLastError() != 1056 || (v8 = WaitServiceState(v6, 9, 30000)) == 0 )
        {
          LastError = GetLastError();
          goto LABEL_15;
        }
        if ( v8 == 4 )
        {
          LastError = 0;
          goto LABEL_15;
        }
      }
      LastError = 1077;
LABEL_15:
      CloseServiceHandle(v6);
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v4);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x1800c24e0  mov     [rsp+arg_0], rbx
0x1800c24e5  mov     [rsp+arg_8], rsi
0x1800c24ea  push    rdi
0x1800c24eb  sub     rsp, 20h
0x1800c24ef  xor     edx, edx; lpDatabaseName
0x1800c24f1  xor     ecx, ecx; lpMachineName
0x1800c24f3  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800c24f7  call    cs:__imp_OpenSCManagerW
0x1800c24fd  mov     rsi, rax
0x1800c2500  test    rax, rax
0x1800c2503  jnz     short loc_1800C2512
0x1800c2505  call    cs:__imp_GetLastError
0x1800c250b  mov     ebx, eax
0x1800c250d  jmp     loc_1800C25A8
0x1800c2512  mov     r8d, 14h; dwDesiredAccess
0x1800c2518  lea     rdx, ServiceName; "IPxlatCfgSvc"
0x1800c251f  mov     rcx, rsi; hSCManager
0x1800c2522  call    cs:__imp_OpenServiceW
0x1800c2528  mov     rdi, rax
0x1800c252b  test    rax, rax
0x1800c252e  jnz     short loc_1800C253A
0x1800c2530  call    cs:__imp_GetLastError
0x1800c2536  mov     ebx, eax
0x1800c2538  jmp     short loc_1800C259F
0x1800c253a  xor     bl, bl
0x1800c253c  cmp     bl, 2
0x1800c253f  jnb     short loc_1800C2591
0x1800c2541  xor     r8d, r8d; lpServiceArgVectors
0x1800c2544  xor     edx, edx; dwNumServiceArgs
0x1800c2546  mov     rcx, rdi; hService
0x1800c2549  call    cs:__imp_StartServiceW
0x1800c254f  test    eax, eax
0x1800c2551  jnz     short loc_1800C2560
0x1800c2553  call    cs:__imp_GetLastError
0x1800c2559  cmp     eax, 420h
0x1800c255e  jnz     short loc_1800C2583
0x1800c2560  xor     r9d, r9d
0x1800c2563  mov     r8d, 7530h
0x1800c2569  mov     rcx, rdi
0x1800c256c  lea     edx, [r9+9]
0x1800c2570  call    cs:__imp_WaitServiceState
0x1800c2576  test    eax, eax
0x1800c2578  jz      short loc_1800C2583
0x1800c257a  cmp     eax, 4
0x1800c257d  jz      short loc_1800C258D
0x1800c257f  inc     bl
0x1800c2581  jmp     short loc_1800C253C
0x1800c2583  call    cs:__imp_GetLastError
0x1800c2589  mov     ebx, eax
0x1800c258b  jmp     short loc_1800C2596
0x1800c258d  xor     ebx, ebx
0x1800c258f  jmp     short loc_1800C2596
0x1800c2591  mov     ebx, 435h
0x1800c2596  mov     rcx, rdi; hSCObject
0x1800c2599  call    cs:__imp_CloseServiceHandle
0x1800c259f  mov     rcx, rsi; hSCObject
0x1800c25a2  call    cs:__imp_CloseServiceHandle
0x1800c25a8  mov     rsi, [rsp+28h+arg_8]
0x1800c25ad  mov     eax, ebx
0x1800c25af  mov     rbx, [rsp+28h+arg_0]
0x1800c25b4  add     rsp, 20h
0x1800c25b8  pop     rdi
0x1800c25b9  retn
```

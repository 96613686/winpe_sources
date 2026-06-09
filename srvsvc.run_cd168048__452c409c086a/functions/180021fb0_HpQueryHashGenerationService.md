# HpQueryHashGenerationService

- ea: `0x180021fb0`
- end: `0x1800220b6`
- name: `HpQueryHashGenerationService`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180005820`
- `0x180006040`

## callees

- `0x18001deb0`
- `0x180021fb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002200d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002200d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022063`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180022059`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180022059`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180022027`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180022027`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180021fff`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180021fff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180022086`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002208f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180022086`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002208f`

## pseudocode

```c
__int64 HpQueryHashGenerationService()
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  DWORD LastError; // ebx
  SC_HANDLE v4; // rsi
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v7; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+58h] [rbp-20h]

  *(_OWORD *)Buffer = 0;
  v8 = 0;
  v7 = 0;
  pcbBytesNeeded = 0;
  if ( !dword_18005E4B0 )
    return 50;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v4 = OpenServiceW(v1, L"SmbHash", 0x14u);
    if ( v4 )
    {
      if ( QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
        LastError = (unsigned int)(*(_DWORD *)&Buffer[4] - 4) > 3 ? 0x426 : 0;
      else
        LastError = GetLastError();
      CloseServiceHandle(v4);
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v2);
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
0x180021fb0  mov     [rsp+arg_0], rbx
0x180021fb5  mov     [rsp+arg_8], rsi
0x180021fba  push    rdi
0x180021fbb  sub     rsp, 70h
0x180021fbf  mov     rax, cs:__security_cookie
0x180021fc6  xor     rax, rsp
0x180021fc9  mov     [rsp+78h+var_18], rax
0x180021fce  xor     eax, eax
0x180021fd0  xorps   xmm0, xmm0
0x180021fd3  cmp     cs:dword_18005E4B0, eax
0x180021fd9  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x180021fde  mov     [rsp+78h+var_20], eax
0x180021fe2  movups  [rsp+78h+var_30], xmm0
0x180021fe7  mov     [rsp+78h+var_48], eax
0x180021feb  jnz     short loc_180021FF7
0x180021fed  mov     eax, 32h ; '2'
0x180021ff2  jmp     loc_180022097
0x180021ff7  xor     edx, edx; lpDatabaseName
0x180021ff9  xor     ecx, ecx; lpMachineName
0x180021ffb  lea     r8d, [rdx+1]; dwDesiredAccess
0x180021fff  call    cs:__imp_OpenSCManagerW
0x180022005  mov     rdi, rax
0x180022008  test    rax, rax
0x18002200b  jnz     short loc_180022017
0x18002200d  call    cs:__imp_GetLastError
0x180022013  mov     ebx, eax
0x180022015  jmp     short loc_180022095
0x180022017  mov     r8d, 14h; dwDesiredAccess
0x18002201d  lea     rdx, aSmbhash; "SmbHash"
0x180022024  mov     rcx, rdi; hSCManager
0x180022027  call    cs:__imp_OpenServiceW
0x18002202d  mov     rsi, rax
0x180022030  test    rax, rax
0x180022033  jnz     short loc_18002203F
0x180022035  call    cs:__imp_GetLastError
0x18002203b  mov     ebx, eax
0x18002203d  jmp     short loc_18002208C
0x18002203f  lea     rax, [rsp+78h+var_48]
0x180022044  mov     r9d, 24h ; '$'; cbBufSize
0x18002204a  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x18002204f  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180022054  xor     edx, edx; InfoLevel
0x180022056  mov     rcx, rsi; hService
0x180022059  call    cs:__imp_QueryServiceStatusEx
0x18002205f  test    eax, eax
0x180022061  jnz     short loc_18002206D
0x180022063  call    cs:__imp_GetLastError
0x180022069  mov     ebx, eax
0x18002206b  jmp     short loc_180022083
0x18002206d  mov     eax, dword ptr [rsp+78h+Buffer+4]
0x180022071  mov     ecx, 3
0x180022076  add     eax, 0FFFFFFFCh
0x180022079  cmp     ecx, eax
0x18002207b  sbb     ebx, ebx
0x18002207d  and     ebx, 426h
0x180022083  mov     rcx, rsi; hSCObject
0x180022086  call    cs:__imp_CloseServiceHandle
0x18002208c  mov     rcx, rdi; hSCObject
0x18002208f  call    cs:__imp_CloseServiceHandle
0x180022095  mov     eax, ebx
0x180022097  mov     rcx, [rsp+78h+var_18]
0x18002209c  xor     rcx, rsp; StackCookie
0x18002209f  call    __security_check_cookie
0x1800220a4  lea     r11, [rsp+78h+var_8]
0x1800220a9  mov     rbx, [r11+10h]
0x1800220ad  mov     rsi, [r11+18h]
0x1800220b1  mov     rsp, r11
0x1800220b4  pop     rdi
0x1800220b5  retn
```

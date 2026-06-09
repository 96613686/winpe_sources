# IsMachineInShutdown

- ea: `0x180026190`
- end: `0x18002627c`
- name: `IsMachineInShutdown`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002631c`

## callees

- `0x180026190`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800261e2`
- `KERNEL32!GetLastError` at `0x18002620a`
- `KERNEL32!GetLastError` at `0x180026238`
- `KERNEL32!GetLastError` at `0x1800261e2`
- `KERNEL32!GetLastError` at `0x18002620a`
- `KERNEL32!GetLastError` at `0x180026238`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800261fc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800261fc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180026243`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002624c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180026243`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002624c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800261d4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800261d4`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002622e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002622e`

## string_xrefs

- `0x1800261b1`: `ServicesActive`

## pseudocode

```c
_BOOL8 IsMachineInShutdown()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  DWORD LastError; // ebx
  SC_HANDLE v3; // rsi
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v7; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+58h] [rbp-20h]

  v8 = 0;
  *(_OWORD *)Buffer = 0;
  pcbBytesNeeded = 0;
  v7 = 0;
  v0 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"rpcss", 4u);
    if ( v3 )
    {
      LastError = 0;
      if ( !QueryServiceStatusEx(v3, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
        LastError = GetLastError();
      CloseServiceHandle(v3);
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v1);
  }
  else
  {
    LastError = GetLastError();
  }
  return LastError == 1115;
}

```

## disassembly

```asm
0x180026190  mov     [rsp+arg_0], rbx
0x180026195  mov     [rsp+arg_8], rsi
0x18002619a  push    rdi
0x18002619b  sub     rsp, 70h
0x18002619f  mov     rax, cs:__security_cookie
0x1800261a6  xor     rax, rsp
0x1800261a9  mov     [rsp+78h+var_18], rax
0x1800261ae  xorps   xmm0, xmm0
0x1800261b1  lea     rdx, DatabaseName; "ServicesActive"
0x1800261b8  xor     eax, eax
0x1800261ba  mov     r8d, 80000000h; dwDesiredAccess
0x1800261c0  xor     ecx, ecx; lpMachineName
0x1800261c2  mov     [rsp+78h+var_20], eax
0x1800261c6  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x1800261cb  mov     [rsp+78h+var_48], eax
0x1800261cf  movups  [rsp+78h+var_30], xmm0
0x1800261d4  call    cs:__imp_OpenSCManagerW
0x1800261da  mov     rdi, rax
0x1800261dd  test    rax, rax
0x1800261e0  jnz     short loc_1800261EC
0x1800261e2  call    cs:__imp_GetLastError
0x1800261e8  mov     ebx, eax
0x1800261ea  jmp     short loc_180026252
0x1800261ec  mov     r8d, 4; dwDesiredAccess
0x1800261f2  lea     rdx, ServiceName; "rpcss"
0x1800261f9  mov     rcx, rdi; hSCManager
0x1800261fc  call    cs:__imp_OpenServiceW
0x180026202  mov     rsi, rax
0x180026205  test    rax, rax
0x180026208  jnz     short loc_180026214
0x18002620a  call    cs:__imp_GetLastError
0x180026210  mov     ebx, eax
0x180026212  jmp     short loc_180026249
0x180026214  lea     rax, [rsp+78h+var_48]
0x180026219  xor     ebx, ebx
0x18002621b  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x180026220  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180026225  xor     edx, edx; InfoLevel
0x180026227  mov     rcx, rsi; hService
0x18002622a  lea     r9d, [rbx+24h]; cbBufSize
0x18002622e  call    cs:__imp_QueryServiceStatusEx
0x180026234  test    eax, eax
0x180026236  jnz     short loc_180026240
0x180026238  call    cs:__imp_GetLastError
0x18002623e  mov     ebx, eax
0x180026240  mov     rcx, rsi; hSCObject
0x180026243  call    cs:__imp_CloseServiceHandle
0x180026249  mov     rcx, rdi; hSCObject
0x18002624c  call    cs:__imp_CloseServiceHandle
0x180026252  xor     eax, eax
0x180026254  cmp     ebx, 45Bh
0x18002625a  setz    al
0x18002625d  mov     rcx, [rsp+78h+var_18]
0x180026262  xor     rcx, rsp; StackCookie
0x180026265  call    __security_check_cookie
0x18002626a  lea     r11, [rsp+78h+var_8]
0x18002626f  mov     rbx, [r11+10h]
0x180026273  mov     rsi, [r11+18h]
0x180026277  mov     rsp, r11
0x18002627a  pop     rdi
0x18002627b  retn
```

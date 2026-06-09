# IsRunningInIASService

- ea: `0x18004150c`
- end: `0x1800415ea`
- name: `IsRunningInIASService`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180041310`

## callees

- `0x18004150c`
- `0x180055030`

## import_xrefs

- `ADVAPI32!OpenServiceA` at `0x180041567`
- `ADVAPI32!OpenServiceA` at `0x180041567`
- `ADVAPI32!QueryServiceStatusEx` at `0x1800415b9`
- `ADVAPI32!QueryServiceStatusEx` at `0x1800415b9`
- `ADVAPI32!OpenSCManagerA` at `0x180041549`
- `ADVAPI32!OpenSCManagerA` at `0x180041549`
- `ADVAPI32!CloseServiceHandle` at `0x180041578`
- `ADVAPI32!CloseServiceHandle` at `0x1800415c4`
- `ADVAPI32!CloseServiceHandle` at `0x1800415cd`
- `ADVAPI32!CloseServiceHandle` at `0x180041578`
- `ADVAPI32!CloseServiceHandle` at `0x1800415c4`
- `ADVAPI32!CloseServiceHandle` at `0x1800415cd`
- `KERNEL32!GetCurrentProcessId` at `0x1800415d7`
- `KERNEL32!GetCurrentProcessId` at `0x1800415d7`

## pseudocode

```c
_BOOL8 IsRunningInIASService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  SC_HANDLE v2; // rsi
  BOOL v4; // ebx
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v7; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+58h] [rbp-20h]

  v8 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v7 = 0;
  v0 = OpenSCManagerA(0, 0, 0x1Du);
  v1 = v0;
  if ( !v0 )
    return 0;
  v2 = OpenServiceA(v0, "IAS", 4u);
  if ( !v2 )
  {
    CloseServiceHandle(v1);
    return 0;
  }
  v4 = QueryServiceStatusEx(v2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded);
  CloseServiceHandle(v2);
  CloseServiceHandle(v1);
  if ( !v4 )
    return 0;
  return HIDWORD(v7) == GetCurrentProcessId();
}

```

## disassembly

```asm
0x18004150c  mov     [rsp+arg_0], rbx
0x180041511  mov     [rsp+arg_8], rsi
0x180041516  push    rdi
0x180041517  sub     rsp, 70h
0x18004151b  mov     rax, cs:__security_cookie
0x180041522  xor     rax, rsp
0x180041525  mov     [rsp+78h+var_18], rax
0x18004152a  xor     eax, eax
0x18004152c  xorps   xmm0, xmm0
0x18004152f  xor     edx, edx; lpDatabaseName
0x180041531  mov     [rsp+78h+var_20], eax
0x180041535  xor     ecx, ecx; lpMachineName
0x180041537  mov     [rsp+78h+var_48], eax
0x18004153b  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x180041540  lea     r8d, [rax+1Dh]; dwDesiredAccess
0x180041544  movups  [rsp+78h+var_30], xmm0
0x180041549  call    cs:__imp_OpenSCManagerA
0x18004154f  mov     rdi, rax
0x180041552  test    rax, rax
0x180041555  jz      short loc_18004157E
0x180041557  mov     r8d, 4; dwDesiredAccess
0x18004155d  lea     rdx, ServiceName; "IAS"
0x180041564  mov     rcx, rax; hSCManager
0x180041567  call    cs:__imp_OpenServiceA
0x18004156d  mov     rsi, rax
0x180041570  test    rax, rax
0x180041573  jnz     short loc_18004159F
0x180041575  mov     rcx, rdi; hSCObject
0x180041578  call    cs:__imp_CloseServiceHandle
0x18004157e  xor     eax, eax
0x180041580  mov     rcx, [rsp+78h+var_18]
0x180041585  xor     rcx, rsp; StackCookie
0x180041588  call    __security_check_cookie
0x18004158d  lea     r11, [rsp+78h+var_8]
0x180041592  mov     rbx, [r11+10h]
0x180041596  mov     rsi, [r11+18h]
0x18004159a  mov     rsp, r11
0x18004159d  pop     rdi
0x18004159e  retn
0x18004159f  lea     rax, [rsp+78h+var_48]
0x1800415a4  mov     r9d, 24h ; '$'; cbBufSize
0x1800415aa  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x1800415af  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800415b4  xor     edx, edx; InfoLevel
0x1800415b6  mov     rcx, rsi; hService
0x1800415b9  call    cs:__imp_QueryServiceStatusEx
0x1800415bf  mov     rcx, rsi; hSCObject
0x1800415c2  mov     ebx, eax
0x1800415c4  call    cs:__imp_CloseServiceHandle
0x1800415ca  mov     rcx, rdi; hSCObject
0x1800415cd  call    cs:__imp_CloseServiceHandle
0x1800415d3  test    ebx, ebx
0x1800415d5  jz      short loc_18004157E
0x1800415d7  call    cs:__imp_GetCurrentProcessId
0x1800415dd  xor     ecx, ecx
0x1800415df  cmp     dword ptr [rsp+78h+var_30+0Ch], eax
0x1800415e3  setz    cl
0x1800415e6  mov     eax, ecx
0x1800415e8  jmp     short loc_180041580
```

# UnregisterService(void)

- ea: `0x18004ab90`
- end: `0x18004ac92`
- name: `?UnregisterService@@YAJXZ`
- size: `258`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18004afb0`

## callees

- `0x18004ab90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac6a`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x18004ac5a`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x18004ac5a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004aba7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004aba7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004ac29`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004ac38`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004ac29`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004ac38`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004abe8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004abe8`

## pseudocode

```c
__int64 UnregisterService(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  signed int v2; // eax
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  signed int v6; // eax
  signed int LastError; // eax

  v0 = OpenSCManagerW(0, 0, 2u);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"w32time", 0x10000u);
    v5 = v4;
    if ( v4 )
    {
      if ( !DeleteService(v4) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 == -2147023824 )
          v3 = 0;
        goto LABEL_9;
      }
    }
    else
    {
      v6 = GetLastError();
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      if ( v3 != -2147023836 )
        goto LABEL_10;
    }
    v3 = 0;
    if ( !v5 )
    {
LABEL_10:
      CloseServiceHandle(v1);
      return v3;
    }
LABEL_9:
    CloseServiceHandle(v5);
    goto LABEL_10;
  }
  v2 = GetLastError();
  v3 = v2;
  if ( v2 > 0 )
    return (unsigned __int16)v2 | 0x80070000;
  return v3;
}

```

## disassembly

```asm
0x18004ab90  mov     [rsp+arg_0], rbx
0x18004ab95  mov     [rsp+arg_8], rsi
0x18004ab9a  push    rdi
0x18004ab9b  sub     rsp, 20h
0x18004ab9f  xor     edx, edx; lpDatabaseName
0x18004aba1  xor     ecx, ecx; lpMachineName
0x18004aba3  lea     r8d, [rdx+2]; dwDesiredAccess
0x18004aba7  call    cs:__imp_OpenSCManagerW
0x18004abae  nop     dword ptr [rax+rax+00h]
0x18004abb3  mov     rsi, rax
0x18004abb6  test    rax, rax
0x18004abb9  jnz     short loc_18004ABD8
0x18004abbb  call    cs:__imp_GetLastError
0x18004abc2  nop     dword ptr [rax+rax+00h]
0x18004abc7  mov     ebx, eax
0x18004abc9  test    eax, eax
0x18004abcb  jle     short loc_18004AC44
0x18004abcd  movzx   ebx, ax
0x18004abd0  or      ebx, 80070000h
0x18004abd6  jmp     short loc_18004AC44
0x18004abd8  mov     r8d, 10000h; dwDesiredAccess
0x18004abde  lea     rdx, ModuleName; "w32time"
0x18004abe5  mov     rcx, rsi; hSCManager
0x18004abe8  call    cs:__imp_OpenServiceW
0x18004abef  nop     dword ptr [rax+rax+00h]
0x18004abf4  mov     rdi, rax
0x18004abf7  test    rax, rax
0x18004abfa  jnz     short loc_18004AC57
0x18004abfc  call    cs:__imp_GetLastError
0x18004ac03  nop     dword ptr [rax+rax+00h]
0x18004ac08  mov     ebx, eax
0x18004ac0a  test    eax, eax
0x18004ac0c  jle     short loc_18004AC17
0x18004ac0e  movzx   ebx, ax
0x18004ac11  or      ebx, 80070000h
0x18004ac17  cmp     ebx, 80070424h
0x18004ac1d  jnz     short loc_18004AC35
0x18004ac1f  xor     ebx, ebx
0x18004ac21  test    rdi, rdi
0x18004ac24  jz      short loc_18004AC35
0x18004ac26  mov     rcx, rdi; hSCObject
0x18004ac29  call    cs:__imp_CloseServiceHandle
0x18004ac30  nop     dword ptr [rax+rax+00h]
0x18004ac35  mov     rcx, rsi; hSCObject
0x18004ac38  call    cs:__imp_CloseServiceHandle
0x18004ac3f  nop     dword ptr [rax+rax+00h]
0x18004ac44  mov     rsi, [rsp+28h+arg_8]
0x18004ac49  mov     eax, ebx
0x18004ac4b  mov     rbx, [rsp+28h+arg_0]
0x18004ac50  add     rsp, 20h
0x18004ac54  pop     rdi
0x18004ac55  retn
0x18004ac57  mov     rcx, rdi; hService
0x18004ac5a  call    cs:__imp_DeleteService
0x18004ac61  nop     dword ptr [rax+rax+00h]
0x18004ac66  test    eax, eax
0x18004ac68  jnz     short loc_18004AC1F
0x18004ac6a  call    cs:__imp_GetLastError
0x18004ac71  nop     dword ptr [rax+rax+00h]
0x18004ac76  mov     ebx, eax
0x18004ac78  test    eax, eax
0x18004ac7a  jle     short loc_18004AC85
0x18004ac7c  movzx   ebx, ax
0x18004ac7f  or      ebx, 80070000h
0x18004ac85  xor     eax, eax
0x18004ac87  cmp     ebx, 80070430h
0x18004ac8d  cmovz   ebx, eax
0x18004ac90  jmp     short loc_18004AC26
```

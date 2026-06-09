# UbpmUtilsWaitForAutoStartComplete(void)

- ea: `0x18002aaa0`
- end: `0x18002ab02`
- name: `?UbpmUtilsWaitForAutoStartComplete@@YAKXZ`
- size: `98`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180036a90`

## callees

- `0x18002aaa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aae0`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002aab8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002aab8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002aad6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002aad6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aaef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aaef`

## string_xrefs

- `0x18002aaaa`: `Global\SC_AutoStartComplete`

## pseudocode

```c
__int64 UbpmUtilsWaitForAutoStartComplete(void)
{
  HANDLE v0; // rax
  void *v1; // rdi
  DWORD LastError; // ebx

  v0 = OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
  v1 = v0;
  if ( v0 )
  {
    if ( WaitForSingleObject(v0, 0xFFFFFFFF) )
      LastError = GetLastError();
    else
      LastError = 0;
    CloseHandle(v1);
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
0x18002aaa0  mov     [rsp+arg_0], rbx
0x18002aaa5  push    rdi
0x18002aaa6  sub     rsp, 20h
0x18002aaaa  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x18002aab1  xor     edx, edx; bInheritHandle
0x18002aab3  mov     ecx, 100000h; dwDesiredAccess
0x18002aab8  call    cs:__imp_OpenEventW
0x18002aabe  mov     rdi, rax
0x18002aac1  test    rax, rax
0x18002aac4  jnz     short loc_18002AAD0
0x18002aac6  call    cs:__imp_GetLastError
0x18002aacc  mov     ebx, eax
0x18002aace  jmp     short loc_18002AAF5
0x18002aad0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002aad3  mov     rcx, rdi; hHandle
0x18002aad6  call    cs:__imp_WaitForSingleObject
0x18002aadc  test    eax, eax
0x18002aade  jz      short loc_18002AAEA
0x18002aae0  call    cs:__imp_GetLastError
0x18002aae6  mov     ebx, eax
0x18002aae8  jmp     short loc_18002AAEC
0x18002aaea  xor     ebx, ebx
0x18002aaec  mov     rcx, rdi; hObject
0x18002aaef  call    cs:__imp_CloseHandle
0x18002aaf5  mov     eax, ebx
0x18002aaf7  mov     rbx, [rsp+28h+arg_0]
0x18002aafc  add     rsp, 20h
0x18002ab00  pop     rdi
0x18002ab01  retn
```

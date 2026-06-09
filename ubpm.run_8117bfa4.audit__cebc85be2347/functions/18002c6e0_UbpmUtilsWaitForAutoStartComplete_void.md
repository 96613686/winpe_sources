# UbpmUtilsWaitForAutoStartComplete(void)

- ea: `0x18002c6e0`
- end: `0x18002c761`
- name: `?UbpmUtilsWaitForAutoStartComplete@@YAKXZ`
- size: `129`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800390b0`

## callees

- `0x18002c6e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c70c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c70c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c732`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002c6f8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002c6f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c722`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c722`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c747`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c747`

## string_xrefs

- `0x18002c6ea`: `Global\SC_AutoStartComplete`

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
0x18002c6e0  mov     [rsp+arg_0], rbx
0x18002c6e5  push    rdi
0x18002c6e6  sub     rsp, 20h
0x18002c6ea  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x18002c6f1  xor     edx, edx; bInheritHandle
0x18002c6f3  mov     ecx, 100000h; dwDesiredAccess
0x18002c6f8  call    cs:__imp_OpenEventW
0x18002c6ff  nop     dword ptr [rax+rax+00h]
0x18002c704  mov     rdi, rax
0x18002c707  test    rax, rax
0x18002c70a  jnz     short loc_18002C71C
0x18002c70c  call    cs:__imp_GetLastError
0x18002c713  nop     dword ptr [rax+rax+00h]
0x18002c718  mov     ebx, eax
0x18002c71a  jmp     short loc_18002C753
0x18002c71c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002c71f  mov     rcx, rdi; hHandle
0x18002c722  call    cs:__imp_WaitForSingleObject
0x18002c729  nop     dword ptr [rax+rax+00h]
0x18002c72e  test    eax, eax
0x18002c730  jz      short loc_18002C742
0x18002c732  call    cs:__imp_GetLastError
0x18002c739  nop     dword ptr [rax+rax+00h]
0x18002c73e  mov     ebx, eax
0x18002c740  jmp     short loc_18002C744
0x18002c742  xor     ebx, ebx
0x18002c744  mov     rcx, rdi; hObject
0x18002c747  call    cs:__imp_CloseHandle
0x18002c74e  nop     dword ptr [rax+rax+00h]
0x18002c753  mov     eax, ebx
0x18002c755  mov     rbx, [rsp+28h+arg_0]
0x18002c75a  add     rsp, 20h
0x18002c75e  pop     rdi
0x18002c75f  retn
```

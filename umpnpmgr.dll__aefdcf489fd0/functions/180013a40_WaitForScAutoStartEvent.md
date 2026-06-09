# WaitForScAutoStartEvent

- ea: `0x180013a40`
- end: `0x180013ac8`
- name: `WaitForScAutoStartEvent`
- size: `136`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a6b0`

## callees

- `0x1800135f0`
- `0x180013a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180013a58`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180013a58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180013aac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180013aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ab5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ab5`

## string_xrefs

- `0x180013a4a`: `Global\SC_AutoStartComplete`
- `0x180013a8e`: `Global\SC_AutoStartComplete`

## pseudocode

```c
__int64 WaitForScAutoStartEvent()
{
  HANDLE v0; // rax
  void *v1; // rdi
  DWORD LastError; // ebx
  int v3; // r8d

  v0 = OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
  v1 = v0;
  if ( v0 )
  {
    LastError = 0;
    WaitForSingleObjectEx(v0, 0xFFFFFFFF, 1);
    CloseHandle(v1);
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v3, (unsigned int)L"Global\\SC_AutoStartComplete", LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180013a40  mov     [rsp+arg_0], rbx
0x180013a45  push    rdi
0x180013a46  sub     rsp, 30h
0x180013a4a  lea     r8, aGlobalScAutost; "Global\\SC_AutoStartComplete"
0x180013a51  xor     edx, edx; bInheritHandle
0x180013a53  mov     ecx, 100000h; dwDesiredAccess
0x180013a58  call    cs:__imp_OpenEventW
0x180013a5e  mov     rdi, rax
0x180013a61  test    rax, rax
0x180013a64  jnz     short loc_180013AA0
0x180013a66  call    cs:__imp_GetLastError
0x180013a6c  mov     ebx, eax
0x180013a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a75  lea     rax, WPP_GLOBAL_Control
0x180013a7c  cmp     rcx, rax
0x180013a7f  jz      short loc_180013ABB
0x180013a81  test    byte ptr [rcx+1Ch], 1
0x180013a85  jz      short loc_180013ABB
0x180013a87  mov     rcx, [rcx+10h]
0x180013a8b  lea     edx, [rdi+36h]
0x180013a8e  lea     r9, aGlobalScAutost; "Global\\SC_AutoStartComplete"
0x180013a95  mov     [rsp+38h+var_18], ebx
0x180013a99  call    WPP_SF_Sd
0x180013a9e  jmp     short loc_180013ABB
0x180013aa0  xor     ebx, ebx
0x180013aa2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013aa5  mov     rcx, rdi; hHandle
0x180013aa8  lea     r8d, [rbx+1]; bAlertable
0x180013aac  call    cs:__imp_WaitForSingleObjectEx
0x180013ab2  mov     rcx, rdi; hObject
0x180013ab5  call    cs:__imp_CloseHandle
0x180013abb  mov     eax, ebx
0x180013abd  mov     rbx, [rsp+38h+arg_0]
0x180013ac2  add     rsp, 30h
0x180013ac6  pop     rdi
0x180013ac7  retn
```

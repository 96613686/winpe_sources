# GetShellProcessHandle(ulong,void * *)

- ea: `0x1400153e4`
- end: `0x140015460`
- name: `?GetShellProcessHandle@@YAJKPEAPEAX@Z`
- size: `124`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140014844`

## callees

- `0x1400153e4`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x140015434`
- `KERNEL32!OpenProcess` at `0x140015434`
- `USER32!GetWindowThreadProcessId` at `0x140015418`
- `USER32!GetWindowThreadProcessId` at `0x140015418`
- `USER32!GetShellWindow` at `0x1400153f7`
- `USER32!GetShellWindow` at `0x1400153f7`

## pseudocode

```c
__int64 __fastcall GetShellProcessHandle(DWORD a1, void **a2)
{
  HWND ShellWindow; // rax
  HANDLE v4; // rax
  unsigned int v5; // ecx
  DWORD dwProcessId; // [rsp+30h] [rbp+8h] BYREF

  dwProcessId = a1;
  *a2 = 0;
  ShellWindow = GetShellWindow();
  if ( !ShellWindow )
    return 2147500037LL;
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(ShellWindow, &dwProcessId) )
    return 2147500037LL;
  v4 = OpenProcess(0x80u, 0, dwProcessId);
  v5 = 0;
  *a2 = v4;
  if ( !v4 )
    return (unsigned int)-2147467259;
  return v5;
}

```

## disassembly

```asm
0x1400153e4  mov     [rsp+dwProcessId], ecx
0x1400153e8  push    rbx
0x1400153e9  sub     rsp, 20h
0x1400153ed  mov     rbx, rdx
0x1400153f0  mov     qword ptr [rdx], 0
0x1400153f7  call    cs:__imp_GetShellWindow
0x1400153fe  nop     dword ptr [rax+rax+00h]
0x140015403  test    rax, rax
0x140015406  jz      short loc_140015454
0x140015408  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x14001540d  mov     [rsp+28h+dwProcessId], 0
0x140015415  mov     rcx, rax; hWnd
0x140015418  call    cs:__imp_GetWindowThreadProcessId
0x14001541f  nop     dword ptr [rax+rax+00h]
0x140015424  test    eax, eax
0x140015426  jz      short loc_140015454
0x140015428  mov     r8d, [rsp+28h+dwProcessId]; dwProcessId
0x14001542d  xor     edx, edx; bInheritHandle
0x14001542f  mov     ecx, 80h; dwDesiredAccess
0x140015434  call    cs:__imp_OpenProcess
0x14001543b  nop     dword ptr [rax+rax+00h]
0x140015440  xor     ecx, ecx
0x140015442  mov     edx, 80004005h
0x140015447  test    rax, rax
0x14001544a  mov     [rbx], rax
0x14001544d  cmovz   ecx, edx
0x140015450  mov     eax, ecx
0x140015452  jmp     short loc_140015459
0x140015454  mov     eax, 80004005h
0x140015459  add     rsp, 20h
0x14001545d  pop     rbx
0x14001545e  retn
```

# IsMainShellProcess

- ea: `0x180062a48`
- end: `0x180062ad9`
- name: `IsMainShellProcess`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180060140`

## callees

- `0x180062a48`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180062a7f`
- `KERNEL32!GetCurrentProcessId` at `0x180062a7f`
- `KERNEL32!GetModuleHandleW` at `0x180062aa3`
- `KERNEL32!GetModuleHandleW` at `0x180062aa3`
- `USER32!GetWindowThreadProcessId` at `0x180062a79`
- `USER32!GetWindowThreadProcessId` at `0x180062a79`
- `USER32!GetShellWindow` at `0x180062a5e`
- `USER32!GetShellWindow` at `0x180062a5e`

## pseudocode

```c
HWND IsMainShellProcess()
{
  int v0; // eax
  unsigned int v1; // ebx
  HWND result; // rax
  bool v3; // cf
  DWORD dwProcessId; // [rsp+30h] [rbp+8h] BYREF

  v0 = dword_18009560C;
  v1 = 1;
  if ( dword_18009560C == -1 )
  {
    result = GetShellWindow();
    if ( !result )
      return result;
    dwProcessId = 0;
    GetWindowThreadProcessId(result, &dwProcessId);
    if ( dwProcessId != GetCurrentProcessId() )
    {
      dword_18009560C = 0;
      return 0;
    }
    v0 = 1;
    dword_18009560C = 1;
    if ( !dword_180095A34 )
    {
      v3 = GetModuleHandleW(L"EXPLORER.EXE") != 0;
      v0 = dword_18009560C;
      dword_180095A34 = 2 - v3;
    }
  }
  if ( !v0 )
    return 0;
  return (HWND)v1;
}

```

## disassembly

```asm
0x180062a48  push    rbx
0x180062a4a  sub     rsp, 20h
0x180062a4e  mov     eax, cs:dword_18009560C
0x180062a54  mov     ebx, 1
0x180062a59  cmp     eax, 0FFFFFFFFh
0x180062a5c  jnz     short loc_180062ABD
0x180062a5e  call    cs:__imp_GetShellWindow
0x180062a64  test    rax, rax
0x180062a67  jz      short loc_180062AD7
0x180062a69  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180062a6e  mov     [rsp+28h+dwProcessId], 0
0x180062a76  mov     rcx, rax; hWnd
0x180062a79  call    cs:__imp_GetWindowThreadProcessId
0x180062a7f  call    cs:__imp_GetCurrentProcessId
0x180062a85  cmp     [rsp+28h+dwProcessId], eax
0x180062a89  jnz     short loc_180062ACB
0x180062a8b  cmp     cs:dword_180095A34, 0
0x180062a92  mov     eax, ebx
0x180062a94  mov     cs:dword_18009560C, ebx
0x180062a9a  jnz     short loc_180062ABD
0x180062a9c  lea     rcx, aExplorerExe; "EXPLORER.EXE"
0x180062aa3  call    cs:__imp_GetModuleHandleW
0x180062aa9  neg     rax
0x180062aac  mov     eax, cs:dword_18009560C
0x180062ab2  sbb     ecx, ecx
0x180062ab4  add     ecx, 2
0x180062ab7  mov     cs:dword_180095A34, ecx
0x180062abd  test    eax, eax
0x180062abf  jnz     short loc_180062AC3
0x180062ac1  xor     ebx, ebx
0x180062ac3  mov     eax, ebx
0x180062ac5  add     rsp, 20h
0x180062ac9  pop     rbx
0x180062aca  retn
0x180062acb  mov     cs:dword_18009560C, 0
0x180062ad5  jmp     short loc_180062AC1
0x180062ad7  jmp     short loc_180062AC5
```

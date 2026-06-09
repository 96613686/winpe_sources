# ImmersiveOwnedWindowHelper::EnumImmersiveComponentOwnedWindows(HWND__ *,__int64)

- ea: `0x180019c00`
- end: `0x180019cc7`
- name: `?EnumImmersiveComponentOwnedWindows@ImmersiveOwnedWindowHelper@@YAHPEAUHWND__@@_J@Z`
- size: `199`
- prototype: `__int64 __fastcall(HWND, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019c00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019c1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019c1c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetAncestor` at `0x180019c55`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetAncestor` at `0x180019c55`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x180019c30`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x180019c72`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x180019c30`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x180019c72`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindow` at `0x180019c47`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindow` at `0x180019c47`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetWindowPos` at `0x180019cac`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetWindowPos` at `0x180019cac`

## string_xrefs

- `0x180019c29`: `ImmersiveComponentOwnedWindow`
- `0x180019c68`: `ImmersiveComponentOwnedWindow`

## pseudocode

```c
__int64 __fastcall ImmersiveOwnedWindowHelper::EnumImmersiveComponentOwnedWindows(HWND a1, __int64 a2)
{
  HWND v5; // rdi
  HWND Window; // rax
  HWND Ancestor; // rax

  if ( a1 == *(HWND *)a2 )
  {
    SetLastError(0);
    return 0;
  }
  else
  {
    if ( GetPropW(a1, L"ImmersiveComponentOwnedWindow") == HANDLE_FLAG_INHERIT )
    {
      v5 = a1;
      do
      {
        Window = GetWindow(v5, 4u);
        Ancestor = GetAncestor(Window, 2u);
        v5 = Ancestor;
        if ( !Ancestor )
          break;
        if ( Ancestor == *(HWND *)a2 )
          goto LABEL_9;
      }
      while ( GetPropW(Ancestor, L"ImmersiveComponentOwnedWindow") != HANDLE_FLAG_INHERIT );
      if ( v5 != *(HWND *)a2 )
        return 1;
LABEL_9:
      SetWindowPos(
        a1,
        0,
        *(_DWORD *)(a2 + 8),
        *(_DWORD *)(a2 + 12),
        *(_DWORD *)(a2 + 16) - *(_DWORD *)(a2 + 8),
        *(_DWORD *)(a2 + 20) - *(_DWORD *)(a2 + 12),
        0x4014u);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x180019c00  mov     [rsp+arg_0], rbx
0x180019c05  mov     [rsp+arg_8], rsi
0x180019c0a  push    rdi
0x180019c0b  sub     rsp, 40h
0x180019c0f  mov     rbx, rdx
0x180019c12  mov     rsi, rcx
0x180019c15  cmp     rcx, [rdx]
0x180019c18  jnz     short loc_180019C29
0x180019c1a  xor     ecx, ecx; dwErrCode
0x180019c1c  call    cs:__imp_SetLastError
0x180019c22  xor     eax, eax
0x180019c24  jmp     loc_180019CB7
0x180019c29  lea     rdx, String; "ImmersiveComponentOwnedWindow"
0x180019c30  call    cs:__imp_GetPropW
0x180019c36  cmp     rax, 1
0x180019c3a  jnz     short loc_180019CB2
0x180019c3c  mov     rdi, rsi
0x180019c3f  mov     edx, 4; uCmd
0x180019c44  mov     rcx, rdi; hWnd
0x180019c47  call    cs:__imp_GetWindow
0x180019c4d  mov     rcx, rax; hwnd
0x180019c50  mov     edx, 2; gaFlags
0x180019c55  call    cs:__imp_GetAncestor
0x180019c5b  mov     rdi, rax
0x180019c5e  test    rax, rax
0x180019c61  jz      short loc_180019C7E
0x180019c63  cmp     rax, [rbx]
0x180019c66  jz      short loc_180019C83
0x180019c68  lea     rdx, String; "ImmersiveComponentOwnedWindow"
0x180019c6f  mov     rcx, rax; hWnd
0x180019c72  call    cs:__imp_GetPropW
0x180019c78  cmp     rax, 1
0x180019c7c  jnz     short loc_180019C3F
0x180019c7e  cmp     rdi, [rbx]
0x180019c81  jnz     short loc_180019CB2
0x180019c83  mov     edx, [rbx+14h]
0x180019c86  mov     ecx, [rbx+10h]
0x180019c89  mov     r9d, [rbx+0Ch]; Y
0x180019c8d  sub     edx, r9d
0x180019c90  mov     r8d, [rbx+8]; X
0x180019c94  sub     ecx, r8d
0x180019c97  mov     [rsp+48h+uFlags], 4014h; uFlags
0x180019c9f  mov     [rsp+48h+cy], edx; cy
0x180019ca3  xor     edx, edx; hWndInsertAfter
0x180019ca5  mov     [rsp+48h+var_28], ecx; cx
0x180019ca9  mov     rcx, rsi; hWnd
0x180019cac  call    cs:__imp_SetWindowPos
0x180019cb2  mov     eax, 1
0x180019cb7  mov     rbx, [rsp+48h+arg_0]
0x180019cbc  mov     rsi, [rsp+48h+arg_8]
0x180019cc1  add     rsp, 40h
0x180019cc5  pop     rdi
0x180019cc6  retn
```

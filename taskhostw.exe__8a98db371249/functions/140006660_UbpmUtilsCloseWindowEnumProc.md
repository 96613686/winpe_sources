# UbpmUtilsCloseWindowEnumProc

- ea: `0x140006660`
- end: `0x140006764`
- name: `UbpmUtilsCloseWindowEnumProc`
- size: `260`
- prototype: `__int64 __fastcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140006660`
- `0x140009330`
- `0x140009370`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400066c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400066c5`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x14000670b`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x14000670b`
- `ext-ms-win-ntuser-window-l1-1-0!EnumThreadWindows` at `0x1400066a2`
- `ext-ms-win-ntuser-window-l1-1-0!EnumThreadWindows` at `0x1400066a2`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1400066f3`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1400066f3`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14000667d`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14000667d`

## pseudocode

```c
__int64 __fastcall UbpmUtilsCloseWindowEnumProc(HWND a1, LPARAM a2)
{
  DWORD WindowThreadProcessId; // eax
  DWORD LastError; // eax
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  dwProcessId = 0;
  WindowThreadProcessId = GetWindowThreadProcessId(a1, &dwProcessId);
  if ( dwProcessId != *(_DWORD *)a2 )
    return 1;
  if ( !EnumThreadWindows(WindowThreadProcessId, UbpmUtilsThreadWindowEnumProc, a2)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e1cbaf32598e3fc3fa4e29b4f005223e_Traceguids, LastError);
  }
  if ( !*(_BYTE *)(a2 + 4) )
  {
    if ( IsWindow(a1) )
    {
      PostMessageW(a1, 0x10u, 0, 0);
      *(_BYTE *)(a2 + 4) = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e1cbaf32598e3fc3fa4e29b4f005223e_Traceguids, a1);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140006660  mov     [rsp+arg_10], rbx
0x140006665  push    rdi
0x140006666  sub     rsp, 20h
0x14000666a  mov     rbx, rdx
0x14000666d  mov     [rsp+28h+dwProcessId], 0
0x140006675  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x14000667a  mov     rdi, rcx
0x14000667d  call    cs:__imp_GetWindowThreadProcessId
0x140006683  mov     r8d, [rbx]
0x140006686  cmp     [rsp+28h+dwProcessId], r8d
0x14000668b  jnz     loc_140006754
0x140006691  mov     r8, rbx; lParam
0x140006694  mov     [rsp+28h+arg_0], rsi
0x140006699  lea     rdx, UbpmUtilsThreadWindowEnumProc; lpfn
0x1400066a0  mov     ecx, eax; dwThreadId
0x1400066a2  call    cs:__imp_EnumThreadWindows
0x1400066a8  lea     rsi, WPP_GLOBAL_Control
0x1400066af  test    eax, eax
0x1400066b1  jnz     short loc_1400066EA
0x1400066b3  mov     rax, cs:WPP_GLOBAL_Control
0x1400066ba  cmp     rax, rsi
0x1400066bd  jz      short loc_1400066EA
0x1400066bf  test    byte ptr [rax+1Ch], 4
0x1400066c3  jz      short loc_1400066EA
0x1400066c5  call    cs:__imp_GetLastError
0x1400066cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066d2  lea     r8, WPP_e1cbaf32598e3fc3fa4e29b4f005223e_Traceguids
0x1400066d9  mov     edx, 0Bh
0x1400066de  mov     r9d, eax
0x1400066e1  mov     rcx, [rcx+10h]
0x1400066e5  call    WPP_SF_d
0x1400066ea  cmp     byte ptr [rbx+4], 0
0x1400066ee  jnz     short loc_14000673F
0x1400066f0  mov     rcx, rdi; hWnd
0x1400066f3  call    cs:__imp_IsWindow
0x1400066f9  test    eax, eax
0x1400066fb  jz      short loc_14000673F
0x1400066fd  xor     r9d, r9d; lParam
0x140006700  xor     r8d, r8d; wParam
0x140006703  mov     edx, 10h; Msg
0x140006708  mov     rcx, rdi; hWnd
0x14000670b  call    cs:__imp_PostMessageW
0x140006711  mov     byte ptr [rbx+4], 1
0x140006715  mov     rcx, cs:WPP_GLOBAL_Control
0x14000671c  cmp     rcx, rsi
0x14000671f  jz      short loc_14000673F
0x140006721  test    byte ptr [rcx+1Ch], 4
0x140006725  jz      short loc_14000673F
0x140006727  mov     rcx, [rcx+10h]
0x14000672b  lea     r8, WPP_e1cbaf32598e3fc3fa4e29b4f005223e_Traceguids
0x140006732  mov     edx, 0Ch
0x140006737  mov     r9, rdi
0x14000673a  call    WPP_SF_q
0x14000673f  mov     rsi, [rsp+28h+arg_0]
0x140006744  mov     eax, 1
0x140006749  mov     rbx, [rsp+28h+arg_10]
0x14000674e  add     rsp, 20h
0x140006752  pop     rdi
0x140006753  retn
0x140006754  mov     rbx, [rsp+28h+arg_10]
0x140006759  mov     eax, 1
0x14000675e  add     rsp, 20h
0x140006762  pop     rdi
0x140006763  retn
```

# UbpmUtilsThreadWindowEnumProc

- ea: `0x140009260`
- end: `0x140009315`
- name: `UbpmUtilsThreadWindowEnumProc`
- size: `181`
- prototype: `__int64 __fastcall(HWND, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140009260`
- `0x1400093b0`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x1400092d1`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x1400092e8`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x1400092fb`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x1400092d1`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x1400092e8`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x1400092fb`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14000927d`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14000927d`

## pseudocode

```c
__int64 __fastcall UbpmUtilsThreadWindowEnumProc(HWND a1, __int64 a2)
{
  DWORD dwProcessId; // [rsp+48h] [rbp+10h] BYREF

  dwProcessId = 0;
  GetWindowThreadProcessId(a1, &dwProcessId);
  if ( dwProcessId == *(_DWORD *)a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_e1cbaf32598e3fc3fa4e29b4f005223e_Traceguids,
        a1,
        dwProcessId);
    PostMessageW(a1, 0x111u, 0, 7);
    PostMessageW(a1, 0x111u, 0, 2);
    PostMessageW(a1, 0x10u, 0, 0);
    *(_BYTE *)(a2 + 4) = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x140009260  mov     [rsp+arg_0], rbx
0x140009265  push    rdi
0x140009266  sub     rsp, 30h
0x14000926a  mov     rdi, rdx
0x14000926d  mov     [rsp+38h+dwProcessId], 0
0x140009275  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x14000927a  mov     rbx, rcx
0x14000927d  call    cs:__imp_GetWindowThreadProcessId
0x140009283  mov     eax, [rsp+38h+dwProcessId]
0x140009287  cmp     eax, [rdi]
0x140009289  jnz     short loc_140009305
0x14000928b  mov     rcx, cs:WPP_GLOBAL_Control
0x140009292  lea     rdx, WPP_GLOBAL_Control
0x140009299  cmp     rcx, rdx
0x14000929c  jz      short loc_1400092C0
0x14000929e  test    byte ptr [rcx+1Ch], 4
0x1400092a2  jz      short loc_1400092C0
0x1400092a4  mov     rcx, [rcx+10h]
0x1400092a8  lea     r8, WPP_e1cbaf32598e3fc3fa4e29b4f005223e_Traceguids
0x1400092af  mov     edx, 0Ah
0x1400092b4  mov     [rsp+38h+var_18], eax
0x1400092b8  mov     r9, rbx
0x1400092bb  call    WPP_SF_qd
0x1400092c0  mov     r9d, 7; lParam
0x1400092c6  xor     r8d, r8d; wParam
0x1400092c9  mov     edx, 111h; Msg
0x1400092ce  mov     rcx, rbx; hWnd
0x1400092d1  call    cs:__imp_PostMessageW
0x1400092d7  mov     r9d, 2; lParam
0x1400092dd  xor     r8d, r8d; wParam
0x1400092e0  mov     edx, 111h; Msg
0x1400092e5  mov     rcx, rbx; hWnd
0x1400092e8  call    cs:__imp_PostMessageW
0x1400092ee  xor     r9d, r9d; lParam
0x1400092f1  xor     r8d, r8d; wParam
0x1400092f4  mov     rcx, rbx; hWnd
0x1400092f7  lea     edx, [r9+10h]; Msg
0x1400092fb  call    cs:__imp_PostMessageW
0x140009301  mov     byte ptr [rdi+4], 1
0x140009305  mov     rbx, [rsp+38h+arg_0]
0x14000930a  mov     eax, 1
0x14000930f  add     rsp, 30h
0x140009313  pop     rdi
0x140009314  retn
```

# FindReasonOrVisibleWindowFromThread

- ea: `0x180010db0`
- end: `0x180010e6a`
- name: `FindReasonOrVisibleWindowFromThread`
- size: `186`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a69c`
- `0x180010db0`

## import_xrefs

- `USER32!IsInDesktopWindowBand` at `0x180010dc5`
- `USER32!IsInDesktopWindowBand` at `0x180010dc5`
- `USER32!IsWindowVisible` at `0x180010e44`
- `USER32!IsWindowVisible` at `0x180010e44`
- `USER32!ShutdownBlockReasonQuery` at `0x180010e22`
- `USER32!ShutdownBlockReasonQuery` at `0x180010e22`

## pseudocode

```c
__int64 __fastcall FindReasonOrVisibleWindowFromThread(HWND a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  DWORD pcchBuff; // [rsp+40h] [rbp+18h] BYREF

  if ( (unsigned int)IsInDesktopWindowBand(a1) )
  {
    pcchBuff = 0;
    if ( ShutdownBlockReasonQuery(a1, 0, &pcchBuff) )
    {
      v4 = 0;
    }
    else
    {
      v4 = 1;
      if ( *a2 || !IsWindowVisible(a1) )
        return v4;
    }
    *a2 = a1;
    return v4;
  }
  v4 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_505945c03e493a216d84854f631c34ea_Traceguids, a1);
  }
  return v4;
}

```

## disassembly

```asm
0x180010db0  mov     [rsp+arg_0], rbx
0x180010db5  mov     [rsp+arg_8], rsi
0x180010dba  push    rdi
0x180010dbb  sub     rsp, 20h
0x180010dbf  mov     rsi, rdx
0x180010dc2  mov     rdi, rcx
0x180010dc5  call    cs:__imp_IsInDesktopWindowBand
0x180010dcc  nop     dword ptr [rax+rax+00h]
0x180010dd1  test    eax, eax
0x180010dd3  jnz     short loc_180010E10
0x180010dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ddc  lea     rax, WPP_GLOBAL_Control
0x180010de3  mov     ebx, 1
0x180010de8  cmp     rcx, rax
0x180010deb  jz      short loc_180010E57
0x180010ded  test    [rcx+1Ch], bl
0x180010df0  jz      short loc_180010E57
0x180010df2  cmp     byte ptr [rcx+19h], 4
0x180010df6  jb      short loc_180010E57
0x180010df8  mov     rcx, [rcx+10h]
0x180010dfc  lea     edx, [rbx+9]
0x180010dff  mov     r9, rdi
0x180010e02  lea     r8, WPP_505945c03e493a216d84854f631c34ea_Traceguids
0x180010e09  call    WPP_SF_q
0x180010e0e  jmp     short loc_180010E57
0x180010e10  lea     r8, [rsp+28h+pcchBuff]; pcchBuff
0x180010e15  mov     [rsp+28h+pcchBuff], 0
0x180010e1d  xor     edx, edx; pwszBuff
0x180010e1f  mov     rcx, rdi; hWnd
0x180010e22  call    cs:__imp_ShutdownBlockReasonQuery
0x180010e29  nop     dword ptr [rax+rax+00h]
0x180010e2e  test    eax, eax
0x180010e30  jz      short loc_180010E36
0x180010e32  xor     ebx, ebx
0x180010e34  jmp     short loc_180010E54
0x180010e36  cmp     qword ptr [rsi], 0
0x180010e3a  mov     ebx, 1
0x180010e3f  jnz     short loc_180010E57
0x180010e41  mov     rcx, rdi; hWnd
0x180010e44  call    cs:__imp_IsWindowVisible
0x180010e4b  nop     dword ptr [rax+rax+00h]
0x180010e50  test    eax, eax
0x180010e52  jz      short loc_180010E57
0x180010e54  mov     [rsi], rdi
0x180010e57  mov     rsi, [rsp+28h+arg_8]
0x180010e5c  mov     eax, ebx
0x180010e5e  mov     rbx, [rsp+28h+arg_0]
0x180010e63  add     rsp, 20h
0x180010e67  pop     rdi
0x180010e68  retn
```

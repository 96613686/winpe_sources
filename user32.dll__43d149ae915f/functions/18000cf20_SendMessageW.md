# SendMessageW

- ea: `0x18000cf20`
- end: `0x18000d098`
- name: `SendMessageW`
- size: `376`
- prototype: `LRESULT __stdcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `95`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000772c`
- `0x180007a50`
- `0x180008ab0`
- `0x180009710`
- `0x18000a6a0`
- `0x18000c490`
- `0x18000f140`
- `0x180011c6c`
- `0x180011f38`
- `0x180012580`
- `0x180015ac8`
- `0x180016488`
- `0x180020990`
- `0x180021270`
- `0x1800216b0`
- `0x180026988`
- `0x180026c20`
- `0x180027c00`
- `0x180028740`
- `0x180029cf4`
- `0x18002a2e8`
- `0x18002a858`
- `0x18002b854`
- `0x18002f878`
- `0x1800333a0`
- `0x180033af0`
- `0x180034508`
- `0x180034604`
- `0x180036bc4`
- `0x180036cd0`
- `0x180037968`
- `0x180037ae4`
- `0x1800389bc`
- `0x180039fc0`
- `0x18003ae48`
- `0x18003b604`
- `0x18003bfac`
- `0x180042450`
- `0x180042b10`
- `0x180042e90`
- `0x1800435a0`
- `0x180045fc0`
- `0x18004b930`
- `0x18004b9a0`
- `0x18004baa0`
- `0x18004d4d0`
- `0x1800559c4`
- `0x180055da4`
- `0x180056148`
- `0x1800579a0`

## callees

- `0x18000cf20`
- `0x18000d0a0`
- `0x18000d210`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserGetThreadState` at `0x18000d081`
- `win32u!NtUserGetThreadState` at `0x18000d081`
- `win32u!NtUserMessageCall` at `0x18000d02c`
- `win32u!NtUserMessageCall` at `0x18000d02c`
- `ntdll!RtlSetLastWin32Error` at `0x18000d064`
- `ntdll!RtlSetLastWin32Error` at `0x18000d064`

## pseudocode

```c
LRESULT __stdcall SendMessageW(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  __int64 v4; // rbx
  struct _TEB *v7; // rcx
  HWND *v8; // rdi
  SIZE_T *Win32ClientInfo; // rax
  HWND v10; // r10
  HWND v12; // rcx

  v4 = Msg;
  if ( (Msg & 0xFFFE0000) != 0 )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  else if ( (((unsigned __int64)hWnd + 1) & 0xFFFFFFFFFFFEFFFFuLL) != 0 )
  {
    return SendMessageInternal(hWnd, Msg, wParam, lParam, 0);
  }
  else
  {
    if ( NtCurrentTeb()->Win32ThreadInfo || NtUserGetThreadState(14) )
    {
      v7 = NtCurrentTeb();
      v8 = (HWND *)(v7->Win32ClientInfo[5] + *(_QWORD *)(v7->Win32ClientInfo[4] + 8));
    }
    else
    {
      v8 = 0;
    }
    Win32ClientInfo = NtCurrentTeb()->Win32ClientInfo;
    if ( !Win32ClientInfo || (*((_DWORD *)Win32ClientInfo + 7) & 0x20000000) == 0 )
      goto LABEL_7;
    v12 = 0;
    if ( v8 )
      v12 = *v8;
    if ( !ValidateHwnd(v12) )
    {
      v10 = 0;
    }
    else
    {
LABEL_7:
      if ( v8 )
        v10 = *v8;
      else
        v10 = 0;
    }
    if ( (unsigned int)v4 >= 0x400 )
    {
      return NtUserMessageCall(v10, (unsigned int)v4, wParam, lParam, 0, 690, 0);
    }
    else
    {
      _mm_lfence();
      return ((__int64 (__fastcall **)(HWND, _QWORD, WPARAM, LPARAM, _QWORD, int, _DWORD))gapfnScSendMessage)[(unsigned __int8)MessageTable[v4]](
               v10,
               (unsigned int)v4,
               wParam,
               lParam,
               0,
               690,
               0);
    }
  }
}

```

## disassembly

```asm
0x18000cf20  mov     [rsp+arg_10], rbx
0x18000cf25  mov     [rsp+arg_18], rbp
0x18000cf2a  push    rsi
0x18000cf2b  sub     rsp, 40h
0x18000cf2f  mov     ebx, edx
0x18000cf31  mov     rsi, r9
0x18000cf34  mov     rbp, r8
0x18000cf37  test    edx, 0FFFE0000h
0x18000cf3d  jnz     loc_18000D05F
0x18000cf43  mov     [rsp+48h+arg_8], r14
0x18000cf48  lea     rax, [rcx+1]
0x18000cf4c  xor     r14d, r14d
0x18000cf4f  test    rax, 0FFFFFFFFFFFEFFFFh
0x18000cf55  jnz     loc_18000D006
0x18000cf5b  mov     rax, gs:30h
0x18000cf64  mov     [rsp+48h+arg_0], rdi
0x18000cf69  cmp     [rax+78h], r14
0x18000cf6d  jz      loc_18000D07C
0x18000cf73  mov     rcx, gs:30h
0x18000cf7c  mov     rax, [rcx+820h]
0x18000cf83  mov     rdi, [rax+8]
0x18000cf87  add     rdi, [rcx+828h]
0x18000cf8e  mov     rax, gs:30h
0x18000cf97  add     rax, 800h
0x18000cf9d  jz      short loc_18000CFAC
0x18000cf9f  test    dword ptr [rax+1Ch], 20000000h
0x18000cfa6  jnz     loc_18000D034
0x18000cfac  test    rdi, rdi
0x18000cfaf  jz      loc_18000D057
0x18000cfb5  mov     r10, [rdi]
0x18000cfb8  mov     rdi, [rsp+48h+arg_0]
0x18000cfbd  mov     r9, rsi
0x18000cfc0  mov     [rsp+48h+var_18], r14d
0x18000cfc5  mov     r8, rbp
0x18000cfc8  mov     [rsp+48h+var_20], 2B2h
0x18000cfd0  mov     qword ptr [rsp+48h+var_28], r14
0x18000cfd5  cmp     ebx, 400h
0x18000cfdb  jnb     short loc_18000D027
0x18000cfdd  lfence
0x18000cfe0  lea     rdx, __ImageBase
0x18000cfe7  movzx   eax, ds:(MessageTable - 180000000h)[rdx+rbx*2]
0x18000cfef  movzx   ecx, al
0x18000cff2  mov     rax, ds:(gapfnScSendMessage - 180000000h)[rdx+rcx*8]
0x18000cffa  mov     edx, ebx
0x18000cffc  mov     rcx, r10
0x18000cfff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d004  jmp     short loc_18000D012
0x18000d006  mov     edx, ebx; unsigned int
0x18000d008  mov     [rsp+48h+var_28], r14d; int
0x18000d00d  call    ?SendMessageInternal@@YA_JPEAUHWND__@@I_K_JH@Z; SendMessageInternal(HWND__ *,uint,unsigned __int64,__int64,int)
0x18000d012  mov     r14, [rsp+48h+arg_8]
0x18000d017  mov     rbx, [rsp+48h+arg_10]
0x18000d01c  mov     rbp, [rsp+48h+arg_18]
0x18000d021  add     rsp, 40h
0x18000d025  pop     rsi
0x18000d026  retn
0x18000d027  mov     edx, ebx
0x18000d029  mov     rcx, r10
0x18000d02c  call    cs:__imp_NtUserMessageCall
0x18000d032  jmp     short loc_18000D012
0x18000d034  mov     rcx, r14; HWND
0x18000d037  test    rdi, rdi
0x18000d03a  jnz     short loc_18000D052
0x18000d03c  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x18000d041  test    rax, rax
0x18000d044  jnz     loc_18000CFAC
0x18000d04a  mov     r10, r14
0x18000d04d  jmp     loc_18000CFB8
0x18000d052  mov     rcx, [rdi]
0x18000d055  jmp     short loc_18000D03C
0x18000d057  mov     r10, r14
0x18000d05a  jmp     loc_18000CFB8
0x18000d05f  mov     ecx, 57h ; 'W'; LastError
0x18000d064  call    cs:__imp_RtlSetLastWin32Error
0x18000d06a  mov     rbx, [rsp+48h+arg_10]
0x18000d06f  xor     eax, eax
0x18000d071  mov     rbp, [rsp+48h+arg_18]
0x18000d076  add     rsp, 40h
0x18000d07a  pop     rsi
0x18000d07b  retn
0x18000d07c  mov     ecx, 0Eh
0x18000d081  call    cs:__imp_NtUserGetThreadState
0x18000d087  test    rax, rax
0x18000d08a  jnz     loc_18000CF73
0x18000d090  mov     rdi, r14
0x18000d093  jmp     loc_18000CF8E
```

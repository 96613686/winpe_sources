# GetWindowThreadProcessId

- ea: `0x180040c50`
- end: `0x180040e32`
- name: `GetWindowThreadProcessId`
- size: `482`
- prototype: `DWORD __stdcall(HWND hWnd, LPDWORD lpdwProcessId)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002a230`
- `0x180030130`
- `0x180040ae0`
- `0x180040b90`
- `0x180069bf0`
- `0x18006e4b4`
- `0x18007f97c`

## callees

- `0x18000d9b0`
- `0x180040c50`

## import_xrefs

- `win32u!NtUserMapDesktopObject` at `0x180040e1c`
- `win32u!NtUserMapDesktopObject` at `0x180040e1c`
- `win32u!NtUserValidateHandleSecure` at `0x180040df9`
- `win32u!NtUserValidateHandleSecure` at `0x180040df9`
- `ntdll!RtlSetLastWin32Error` at `0x180040d48`
- `ntdll!RtlSetLastWin32Error` at `0x180040e0c`
- `ntdll!RtlSetLastWin32Error` at `0x180040d48`
- `ntdll!RtlSetLastWin32Error` at `0x180040e0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040ce2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040ce2`

## pseudocode

```c
DWORD __stdcall GetWindowThreadProcessId(HWND hWnd, LPDWORD lpdwProcessId)
{
  unsigned __int64 v3; // rbx
  __int64 v5; // rax
  char v6; // cl
  __int16 v7; // di
  __int64 v8; // rsi
  __int64 v9; // rdx
  struct _TEB *v11; // rax
  __int64 v12; // rbx
  struct _TEB *v13; // r8
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rsi
  __int64 v17; // rdi
  _QWORD *v18; // rax

  v3 = (unsigned __int16)hWnd;
  if ( (unsigned __int64)(unsigned __int16)hWnd >= *(_QWORD *)(gpsi + 8) )
    goto LABEL_17;
  if ( (unsigned __int64)(unsigned __int16)hWnd >= *(_QWORD *)(gSharedInfo + 8) )
    goto LABEL_17;
  v5 = dword_1800C9380 * (unsigned int)(unsigned __int16)hWnd + qword_1800C9378;
  v6 = *(_BYTE *)(v5 + 24);
  if ( !v6 )
    goto LABEL_17;
  if ( !v5 )
    goto LABEL_17;
  if ( v6 != 1 )
    goto LABEL_17;
  if ( (*(_BYTE *)(v5 + 25) & 1) != 0 )
    goto LABEL_17;
  v7 = WORD1(hWnd) & 0x7FFF;
  if ( (WORD1(hWnd) & 0x7FFF) != *(_WORD *)(v5 + 26) )
    goto LABEL_17;
  v8 = *(_QWORD *)(v5 + 8);
  if ( !v8 )
    return 0;
  if ( v8 == GetCurrentThreadId() )
  {
    if ( lpdwProcessId )
      *lpdwProcessId = (DWORD)NtCurrentTeb()->ClientId.UniqueProcess;
    return (DWORD)NtCurrentTeb()->ClientId.UniqueThread;
  }
  v11 = NtCurrentTeb();
  if ( hWnd && hWnd == (HWND)v11->Win32ClientInfo[8] )
  {
    v12 = v11->Win32ClientInfo[9];
    goto LABEL_16;
  }
  v13 = NtCurrentTeb();
  if ( v3 >= *(_QWORD *)(gpsi + 8) )
    goto LABEL_36;
  v14 = HANDLEENTRY_FROM_INDEX((unsigned int)v3, v9, v13);
  v16 = v14;
  if ( !v14 || v7 != *(_WORD *)(v14 + 26) && v7 != 0x7FFF )
    goto LABEL_36;
  v12 = 0;
  v17 = v15 + 2048;
  if ( (*(_BYTE *)(v14 + 25) & 1) == 0 && *(_BYTE *)(v14 + 24) == 1 )
  {
    v18 = *(_QWORD **)(v15 + 2080);
    if ( v18 && *(_QWORD *)(v16 + 16) == *v18 )
      v12 = *(_QWORD *)v16 + *(_QWORD *)(v15 + 2088);
    else
      v12 = NtUserMapDesktopObject(hWnd);
  }
  if ( (*(_BYTE *)(v16 + 25) & 4) != 0 || !v17 || (*(_DWORD *)(v17 + 28) & 0x20000000) == 0 )
  {
    if ( v12 )
      goto LABEL_30;
    goto LABEL_36;
  }
  if ( !v12 || !(unsigned int)NtUserValidateHandleSecure(hWnd) )
  {
LABEL_36:
    RtlSetLastWin32Error(0x578u);
    v12 = 0;
  }
LABEL_16:
  if ( !v12 )
  {
LABEL_17:
    RtlSetLastWin32Error(0x578u);
    return 0;
  }
LABEL_30:
  if ( lpdwProcessId )
    *lpdwProcessId = *(_DWORD *)(v12 + 332);
  return *(_DWORD *)(v12 + 328);
}

```

## disassembly

```asm
0x180040c50  push    rbx
0x180040c52  push    rbp
0x180040c53  push    rsi
0x180040c54  push    rdi
0x180040c55  push    r14
0x180040c57  push    r15
0x180040c59  sub     rsp, 28h
0x180040c5d  mov     rax, cs:gpsi
0x180040c64  mov     r14, rdx
0x180040c67  movzx   ebx, cx
0x180040c6a  mov     rbp, rcx
0x180040c6d  cmp     rbx, [rax+8]
0x180040c71  jnb     loc_180040D43
0x180040c77  mov     rax, cs:gSharedInfo
0x180040c7e  cmp     rbx, [rax+8]
0x180040c82  jnb     loc_180040D43
0x180040c88  mov     rax, cs:qword_1800C9378
0x180040c8f  mov     ecx, ebx
0x180040c91  imul    ecx, cs:dword_1800C9380
0x180040c98  add     rax, rcx
0x180040c9b  movzx   ecx, byte ptr [rax+18h]
0x180040c9f  test    cl, cl
0x180040ca1  jz      loc_180040D43
0x180040ca7  test    rax, rax
0x180040caa  jz      loc_180040D43
0x180040cb0  cmp     cl, 1
0x180040cb3  jnz     loc_180040D43
0x180040cb9  test    [rax+19h], cl
0x180040cbc  jnz     loc_180040D43
0x180040cc2  mov     rdi, rbp
0x180040cc5  mov     r15d, 7FFFh
0x180040ccb  shr     rdi, 10h
0x180040ccf  and     di, r15w
0x180040cd3  cmp     di, [rax+1Ah]
0x180040cd7  jnz     short loc_180040D43
0x180040cd9  mov     rsi, [rax+8]
0x180040cdd  test    rsi, rsi
0x180040ce0  jz      short loc_180040D4E
0x180040ce2  call    cs:__imp_GetCurrentThreadId
0x180040ce8  mov     eax, eax
0x180040cea  cmp     rsi, rax
0x180040ced  jnz     short loc_180040D1C
0x180040cef  test    r14, r14
0x180040cf2  jz      short loc_180040D03
0x180040cf4  mov     rax, gs:30h
0x180040cfd  mov     ecx, [rax+40h]
0x180040d00  mov     [r14], ecx
0x180040d03  mov     rax, gs:30h
0x180040d0c  mov     eax, [rax+48h]
0x180040d0f  add     rsp, 28h
0x180040d13  pop     r15
0x180040d15  pop     r14
0x180040d17  pop     rdi
0x180040d18  pop     rsi
0x180040d19  pop     rbp
0x180040d1a  pop     rbx
0x180040d1b  retn
0x180040d1c  mov     rax, gs:30h
0x180040d25  test    rbp, rbp
0x180040d28  jz      short loc_180040D52
0x180040d2a  cmp     rbp, [rax+840h]
0x180040d31  jnz     short loc_180040D52
0x180040d33  mov     rbx, [rax+848h]
0x180040d3a  test    rbx, rbx
0x180040d3d  jnz     loc_180040DC7
0x180040d43  mov     ecx, 578h; LastError
0x180040d48  call    cs:__imp_RtlSetLastWin32Error
0x180040d4e  xor     eax, eax
0x180040d50  jmp     short loc_180040D0F
0x180040d52  mov     r8, gs:30h
0x180040d5b  mov     rax, cs:gpsi
0x180040d62  cmp     rbx, [rax+8]
0x180040d66  jnb     loc_180040E07
0x180040d6c  mov     ecx, ebx
0x180040d6e  call    _HANDLEENTRY_FROM_INDEX
0x180040d73  mov     rsi, rax
0x180040d76  test    rax, rax
0x180040d79  jz      loc_180040E07
0x180040d7f  cmp     di, [rax+1Ah]
0x180040d83  jnz     loc_180040E27
0x180040d89  xor     ebx, ebx
0x180040d8b  lea     rdi, [r8+800h]
0x180040d92  test    byte ptr [rax+19h], 1
0x180040d96  jnz     short loc_180040DB7
0x180040d98  cmp     byte ptr [rax+18h], 1
0x180040d9c  jnz     short loc_180040DB7
0x180040d9e  mov     rax, [rdi+20h]
0x180040da2  test    rax, rax
0x180040da5  jz      short loc_180040E19
0x180040da7  mov     rax, [rax]
0x180040daa  cmp     [rsi+10h], rax
0x180040dae  jnz     short loc_180040E19
0x180040db0  mov     rbx, [rdi+28h]
0x180040db4  add     rbx, [rsi]
0x180040db7  test    byte ptr [rsi+19h], 4
0x180040dbb  jnz     short loc_180040DC2
0x180040dbd  test    rdi, rdi
0x180040dc0  jnz     short loc_180040DE8
0x180040dc2  test    rbx, rbx
0x180040dc5  jz      short loc_180040E07
0x180040dc7  test    r14, r14
0x180040dca  jz      short loc_180040DD5
0x180040dcc  mov     ecx, [rbx+14Ch]
0x180040dd2  mov     [r14], ecx
0x180040dd5  mov     eax, [rbx+148h]
0x180040ddb  add     rsp, 28h
0x180040ddf  pop     r15
0x180040de1  pop     r14
0x180040de3  pop     rdi
0x180040de4  pop     rsi
0x180040de5  pop     rbp
0x180040de6  pop     rbx
0x180040de7  retn
0x180040de8  test    dword ptr [rdi+1Ch], 20000000h
0x180040def  jz      short loc_180040DC2
0x180040df1  test    rbx, rbx
0x180040df4  jz      short loc_180040E07
0x180040df6  mov     rcx, rbp
0x180040df9  call    cs:__imp_NtUserValidateHandleSecure
0x180040dff  test    eax, eax
0x180040e01  jnz     loc_180040D3A
0x180040e07  mov     ecx, 578h; LastError
0x180040e0c  call    cs:__imp_RtlSetLastWin32Error
0x180040e12  xor     ebx, ebx
0x180040e14  jmp     loc_180040D3A
0x180040e19  mov     rcx, rbp
0x180040e1c  call    cs:__imp_NtUserMapDesktopObject
0x180040e22  mov     rbx, rax
0x180040e25  jmp     short loc_180040DB7
0x180040e27  cmp     di, r15w
0x180040e2b  jnz     short loc_180040E07
0x180040e2d  jmp     loc_180040D89
```

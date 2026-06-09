# ExitWindowsWorker(uint,int)

- ea: `0x18005db8c`
- end: `0x18005dbf7`
- name: `?ExitWindowsWorker@@YAHIH@Z`
- size: `107`
- prototype: `int(unsigned int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x1800778e0`
- `0x180077970`

## callees

- `0x180009e20`
- `0x18000ac60`
- `0x18000ae90`
- `0x180020e80`
- `0x180041250`
- `0x18005db8c`
- `0x18005dc00`

## import_xrefs

- `win32u!NtUserPrepareForLogoff` at `0x18005dbc1`
- `win32u!NtUserPrepareForLogoff` at `0x18005dbc1`
- `ntdll!RtlSetLastWin32Error` at `0x1800a00c9`
- `ntdll!RtlSetLastWin32Error` at `0x1800a00c9`
- `ntdll!NtClose` at `0x1800a00b5`
- `ntdll!NtClose` at `0x1800a00b5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800a0037`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800a0037`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800a00a0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800a00a0`

## pseudocode

```c
__int64 __fastcall ExitWindowsWorker(unsigned int a1, int a2)
{
  int v5; // eax
  DWORD ThreadId; // [rsp+30h] [rbp-40h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-38h] BYREF
  struct tagMSG Msg; // [rsp+40h] [rbp-30h] BYREF
  DWORD ExitCode; // [rsp+90h] [rbp+20h] BYREF
  unsigned int Parameter; // [rsp+98h] [rbp+28h] BYREF

  ThreadId = 0;
  ExitCode = 0;
  Parameter = 0;
  if ( !PtiCurrent() || !(unsigned int)NtUserPrepareForLogoff() )
    return 0;
  v5 = CallUserpExitWindowsEx(a1, &Parameter);
  if ( v5 >= 0 )
    return Parameter;
  if ( v5 != -1073741608 || a2 )
  {
    SetLastNtError((unsigned int)v5);
    return 0;
  }
  pHandles = 0;
  Parameter = a1;
  memset(&Msg, 0, sizeof(Msg));
  pHandles = CreateThread(0, 0, ExitWindowsThread, &Parameter, 0, &ThreadId);
  if ( !pHandles )
    return 0;
  while ( MsgWaitForMultipleObjectsEx(1u, &pHandles, 0xFFFFFFFF, 0x1CFFu, 0) )
  {
    while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      DispatchMessageWorker(&Msg, 0);
  }
  if ( !GetExitCodeThread(pHandles, &ExitCode) )
    ExitCode = 14;
  NtClose(pHandles);
  if ( ExitCode )
  {
    RtlSetLastWin32Error(ExitCode);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18005db8c  mov     [rsp-8+arg_0], rbx
0x18005db91  mov     [rsp-8+arg_8], rdi
0x18005db96  push    rbp
0x18005db97  mov     rbp, rsp
0x18005db9a  sub     rsp, 70h
0x18005db9e  mov     edi, edx
0x18005dba0  mov     [rbp+ThreadId], 0
0x18005dba7  mov     ebx, ecx
0x18005dba9  mov     [rbp+ExitCode], 0
0x18005dbb0  mov     [rbp+Parameter], 0
0x18005dbb7  call    PtiCurrent
0x18005dbbc  test    rax, rax
0x18005dbbf  jz      short loc_18005DBCB
0x18005dbc1  call    cs:__imp_NtUserPrepareForLogoff
0x18005dbc7  test    eax, eax
0x18005dbc9  jnz     short loc_18005DBDF
0x18005dbcb  xor     eax, eax
0x18005dbcd  lea     r11, [rsp+70h+var_s0]
0x18005dbd2  mov     rbx, [r11+10h]
0x18005dbd6  mov     rdi, [r11+18h]
0x18005dbda  mov     rsp, r11
0x18005dbdd  pop     rbp
0x18005dbde  retn
0x18005dbdf  lea     rdx, [rbp+Parameter]
0x18005dbe3  mov     ecx, ebx
0x18005dbe5  call    CallUserpExitWindowsEx
0x18005dbea  test    eax, eax
0x18005dbec  js      loc_18009FFEE
0x18005dbf2  mov     eax, [rbp+Parameter]
0x18005dbf5  jmp     short loc_18005DBCD
0x18009ffee  cmp     eax, 0C00000D8h
0x18009fff3  jnz     loc_1800A00D5
0x18009fff9  test    edi, edi
0x18009fffb  jnz     loc_1800A00D5
0x1800a0001  xorps   xmm0, xmm0
0x1800a0004  mov     [rbp+pHandles], 0
0x1800a000c  lea     rax, [rbp+ThreadId]
0x1800a0010  mov     [rbp+Parameter], ebx
0x1800a0013  mov     [rsp+70h+lpThreadId], rax; lpThreadId
0x1800a0018  lea     r9, [rbp+Parameter]; lpParameter
0x1800a001c  lea     r8, ?ExitWindowsThread@@YAKPEAX@Z; lpStartAddress
0x1800a0023  mov     [rsp+70h+dwCreationFlags], edi; dwCreationFlags
0x1800a0027  xor     edx, edx; dwStackSize
0x1800a0029  xor     ecx, ecx; lpThreadAttributes
0x1800a002b  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x1800a002f  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x1800a0033  movups  xmmword ptr [rbp+Msg.time], xmm0
0x1800a0037  call    cs:__imp_CreateThread
0x1800a003d  mov     [rbp+pHandles], rax
0x1800a0041  test    rax, rax
0x1800a0044  jz      loc_18005DBCB
0x1800a004a  mov     edi, 1CFFh
0x1800a004f  mov     ebx, 1
0x1800a0054  jmp     short loc_1800A007A
0x1800a0056  xor     edx, edx
0x1800a0058  lea     rcx, [rbp+Msg]
0x1800a005c  call    DispatchMessageWorker
0x1800a0061  xor     r9d, r9d; wMsgFilterMax
0x1800a0064  mov     [rsp+70h+dwCreationFlags], ebx; wRemoveMsg
0x1800a0068  xor     r8d, r8d; wMsgFilterMin
0x1800a006b  lea     rcx, [rbp+Msg]; lpMsg
0x1800a006f  xor     edx, edx; hWnd
0x1800a0071  call    PeekMessageW
0x1800a0076  test    eax, eax
0x1800a0078  jnz     short loc_1800A0056
0x1800a007a  mov     r9d, edi; dwWakeMask
0x1800a007d  mov     [rsp+70h+dwCreationFlags], 0; dwFlags
0x1800a0085  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800a0089  lea     rdx, [rbp+pHandles]; pHandles
0x1800a008d  mov     ecx, ebx; nCount
0x1800a008f  call    MsgWaitForMultipleObjectsEx
0x1800a0094  test    eax, eax
0x1800a0096  jnz     short loc_1800A0061
0x1800a0098  mov     rcx, [rbp+pHandles]; hThread
0x1800a009c  lea     rdx, [rbp+ExitCode]; lpExitCode
0x1800a00a0  call    cs:__imp_GetExitCodeThread
0x1800a00a6  test    eax, eax
0x1800a00a8  jnz     short loc_1800A00B1
0x1800a00aa  mov     [rbp+ExitCode], 0Eh
0x1800a00b1  mov     rcx, [rbp+pHandles]; Handle
0x1800a00b5  call    cs:__imp_NtClose
0x1800a00bb  mov     ecx, [rbp+ExitCode]; LastError
0x1800a00be  test    ecx, ecx
0x1800a00c0  jnz     short loc_1800A00C9
0x1800a00c2  mov     eax, ebx
0x1800a00c4  jmp     loc_18005DBCD
0x1800a00c9  call    cs:__imp_RtlSetLastWin32Error
0x1800a00cf  nop
0x1800a00d0  jmp     loc_18005DBCB
0x1800a00d5  mov     ecx, eax
0x1800a00d7  call    SetLastNtError
0x1800a00dc  nop
0x1800a00dd  jmp     loc_18005DBCB
```

# WinSATWaitngThread

- ea: `0x18001ccd0`
- end: `0x18001ce2a`
- name: `WinSATWaitngThread`
- size: `346`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180013128`
- `0x180013fb6`
- `0x18001ccd0`
- `0x18002dec0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001cd81`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001cd81`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001cd3d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001cd3d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001cd53`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001cdb6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001cd53`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001cdb6`
- `USER32!PostMessageW` at `0x18001ce00`
- `USER32!PostMessageW` at `0x18001ce00`
- `USER32!IsWindow` at `0x18001cddb`
- `USER32!IsWindow` at `0x18001cddb`

## pseudocode

```c
__int64 __fastcall WinSATWaitngThread(PVOID Parameter)
{
  DWORD v1; // esi
  void (__fastcall *v2)(__int64, void *); // rdi
  void (__fastcall *v3)(__int64, _QWORD); // rax
  HANDLE Handles[2]; // [rsp+30h] [rbp-28h] BYREF
  HANDLE v6; // [rsp+40h] [rbp-18h]

  Handles[0] = qword_18004DEE0;
  v1 = 2;
  Handles[1] = g_WinSATProcessInfo;
  v6 = 0;
  if ( qword_18004DE90 )
  {
    v6 = qword_18004DE90;
    v1 = 3;
  }
  while ( !WaitForMultipleObjectsEx(v1, Handles, 0, 0xFFFFFFFF, 0) )
  {
    if ( Ptr )
    {
      v2 = (void (__fastcall *)(__int64, void *))DecodePointer(Ptr);
      if ( Src )
        memcpy_0(&s_LocalStatus, Src, 0x80Cu);
      SetEvent(hEvent);
      if ( v2 )
        v2(qword_18004DE68, &s_LocalStatus);
    }
  }
  _InterlockedExchange(&g_RunState, 2);
  if ( Ptr )
  {
    v3 = (void (__fastcall *)(__int64, _QWORD))DecodePointer(Ptr);
    if ( v3 )
      v3(qword_18004DE68, 0);
  }
  if ( hWnd && IsWindow(hWnd) )
    PostMessageW(hWnd, *((UINT *)&hWnd + 2), wParam, *(&wParam + 1));
  ResetGlobalState();
  return 0;
}

```

## disassembly

```asm
0x18001ccd0  mov     r11, rsp
0x18001ccd3  mov     [r11+8], rbx
0x18001ccd7  mov     [r11+10h], rsi
0x18001ccdb  push    rdi
0x18001ccdc  sub     rsp, 50h
0x18001cce0  mov     rax, cs:__security_cookie
0x18001cce7  xor     rax, rsp
0x18001ccea  mov     [rsp+58h+var_10], rax
0x18001ccef  mov     rax, cs:qword_18004DEE0
0x18001ccf6  mov     ebx, 2
0x18001ccfb  mov     [r11-28h], rax
0x18001ccff  mov     esi, ebx
0x18001cd01  mov     rax, qword ptr cs:?g_WinSATProcessInfo@@3U_PROCESS_INFORMATION@@A; _PROCESS_INFORMATION g_WinSATProcessInfo
0x18001cd08  mov     [r11-20h], rax
0x18001cd0c  mov     rax, cs:qword_18004DE90
0x18001cd13  mov     qword ptr [r11-18h], 0
0x18001cd1b  test    rax, rax
0x18001cd1e  jz      short loc_18001CD27
0x18001cd20  mov     [r11-18h], rax
0x18001cd24  lea     esi, [rbx+1]
0x18001cd27  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001cd2b  mov     [rsp+58h+bAlertable], 0; bAlertable
0x18001cd33  xor     r8d, r8d; bWaitAll
0x18001cd36  lea     rdx, [rsp+58h+Handles]; lpHandles
0x18001cd3b  mov     ecx, esi; nCount
0x18001cd3d  call    cs:__imp_WaitForMultipleObjectsEx
0x18001cd43  test    eax, eax
0x18001cd45  jnz     short loc_18001CDA4
0x18001cd47  mov     rcx, cs:Ptr; Ptr
0x18001cd4e  test    rcx, rcx
0x18001cd51  jz      short loc_18001CD27
0x18001cd53  call    cs:__imp_DecodePointer
0x18001cd59  mov     rdx, cs:Src; Src
0x18001cd60  mov     rdi, rax
0x18001cd63  test    rdx, rdx
0x18001cd66  jz      short loc_18001CD7A
0x18001cd68  lea     rcx, ?s_LocalStatus@@3U_WinSATStatus@@A; void *
0x18001cd6f  mov     r8d, 80Ch; Size
0x18001cd75  call    memcpy_0
0x18001cd7a  mov     rcx, cs:hEvent; hEvent
0x18001cd81  call    cs:__imp_SetEvent
0x18001cd87  test    rdi, rdi
0x18001cd8a  jz      short loc_18001CD27
0x18001cd8c  mov     rcx, cs:qword_18004DE68
0x18001cd93  lea     rdx, ?s_LocalStatus@@3U_WinSATStatus@@A; _WinSATStatus s_LocalStatus
0x18001cd9a  mov     rax, rdi
0x18001cd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cda2  jmp     short loc_18001CD27
0x18001cda4  xchg    ebx, cs:?g_RunState@@3JA; long g_RunState
0x18001cdaa  mov     rcx, cs:Ptr; Ptr
0x18001cdb1  test    rcx, rcx
0x18001cdb4  jz      short loc_18001CDCF
0x18001cdb6  call    cs:__imp_DecodePointer
0x18001cdbc  test    rax, rax
0x18001cdbf  jz      short loc_18001CDCF
0x18001cdc1  mov     rcx, cs:qword_18004DE68
0x18001cdc8  xor     edx, edx
0x18001cdca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdcf  mov     rcx, qword ptr cs:hWnd; hWnd
0x18001cdd6  test    rcx, rcx
0x18001cdd9  jz      short loc_18001CE06
0x18001cddb  call    cs:__imp_IsWindow
0x18001cde1  test    eax, eax
0x18001cde3  jz      short loc_18001CE06
0x18001cde5  mov     r9, qword ptr cs:wParam+8; lParam
0x18001cdec  mov     r8, qword ptr cs:wParam; wParam
0x18001cdf3  mov     edx, dword ptr cs:hWnd+8; Msg
0x18001cdf9  mov     rcx, qword ptr cs:hWnd; hWnd
0x18001ce00  call    cs:__imp_PostMessageW
0x18001ce06  call    ResetGlobalState
0x18001ce0b  xor     eax, eax
0x18001ce0d  mov     rcx, [rsp+58h+var_10]
0x18001ce12  xor     rcx, rsp; StackCookie
0x18001ce15  call    __security_check_cookie
0x18001ce1a  mov     rbx, [rsp+58h+arg_0]
0x18001ce1f  mov     rsi, [rsp+58h+arg_8]
0x18001ce24  add     rsp, 50h
0x18001ce28  pop     rdi
0x18001ce29  retn
```

# CFciPropertiesShellExt::TaskDialogCallbackApply(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000f6dc`
- end: `0x18000f794`
- name: `?TaskDialogCallbackApply@CFciPropertiesShellExt@@QEAAJPEAUHWND__@@I_K_J@Z`
- size: `184`
- prototype: `__int64 __fastcall(HANDLE *this, HWND, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800065f0`

## callees

- `0x18000f294`
- `0x18000f6dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f70b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f70b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f721`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f721`
- `USER32!SendMessageW` at `0x18000f765`
- `USER32!SendMessageW` at `0x18000f77c`
- `USER32!SendMessageW` at `0x18000f765`
- `USER32!SendMessageW` at `0x18000f77c`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::TaskDialogCallbackApply(HANDLE *this, HWND a2, int a3)
{
  unsigned int v5; // ebx
  HANDLE v6; // rcx
  UINT v7; // edx
  WPARAM v8; // r8
  signed int started; // eax

  if ( !a3 )
  {
    started = CFciPropertiesShellExt::StartBackgroundThread(
                (CFciPropertiesShellExt *)this,
                (LPTHREAD_START_ROUTINE)CFciPropertiesShellExt::ThreadProcStatic<{private: void CFciPropertiesShellExt::ApplyThreadProc(void),0},0>,
                0);
    v5 = started;
    if ( started < 0 )
    {
      *((_DWORD *)this + 42) = started;
      SendMessageW(a2, 0x466u, 2u, 0);
    }
    v7 = 1131;
    v8 = 1;
    goto LABEL_10;
  }
  v5 = 0;
  if ( a3 == 4 && !WaitForSingleObject(this[17], 0) )
  {
    v6 = this[17];
    if ( v6 )
      CloseHandle(v6);
    this[17] = 0;
    v7 = 1126;
    v8 = 2;
LABEL_10:
    SendMessageW(a2, v7, v8, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x18000f6dc  mov     [rsp+arg_0], rbx
0x18000f6e1  mov     [rsp+arg_8], rsi
0x18000f6e6  push    rdi
0x18000f6e7  sub     rsp, 20h
0x18000f6eb  mov     rsi, rdx
0x18000f6ee  mov     rdi, rcx
0x18000f6f1  test    r8d, r8d
0x18000f6f4  jz      short loc_18000F73B
0x18000f6f6  xor     ebx, ebx
0x18000f6f8  cmp     r8d, 4
0x18000f6fc  jnz     loc_18000F782
0x18000f702  xor     edx, edx; dwMilliseconds
0x18000f704  mov     rcx, [rcx+88h]; hHandle
0x18000f70b  call    cs:__imp_WaitForSingleObject
0x18000f711  test    eax, eax
0x18000f713  jnz     short loc_18000F782
0x18000f715  mov     rcx, [rdi+88h]; hObject
0x18000f71c  test    rcx, rcx
0x18000f71f  jz      short loc_18000F727
0x18000f721  call    cs:__imp_CloseHandle
0x18000f727  mov     [rdi+88h], rbx
0x18000f72e  mov     edx, 466h
0x18000f733  mov     r8d, 2
0x18000f739  jmp     short loc_18000F776
0x18000f73b  xor     r8d, r8d; HWND
0x18000f73e  lea     rdx, ??$ThreadProcStatic@$H?ApplyThreadProc@CFciPropertiesShellExt@@AEAAXXZA@$0A@@CFciPropertiesShellExt@@CAKPEAX@Z; lpStartAddress
0x18000f745  call    ?StartBackgroundThread@CFciPropertiesShellExt@@AEAAJP6AKPEAX@ZPEAUHWND__@@@Z; CFciPropertiesShellExt::StartBackgroundThread(ulong (*)(void *),HWND__ *)
0x18000f74a  mov     ebx, eax
0x18000f74c  test    eax, eax
0x18000f74e  jns     short loc_18000F76B
0x18000f750  mov     [rdi+0A8h], eax
0x18000f756  xor     r9d, r9d; lParam
0x18000f759  mov     edx, 466h; Msg
0x18000f75e  lea     r8d, [r9+2]; wParam
0x18000f762  mov     rcx, rsi; hWnd
0x18000f765  call    cs:__imp_SendMessageW
0x18000f76b  mov     edx, 46Bh; Msg
0x18000f770  mov     r8d, 1; wParam
0x18000f776  xor     r9d, r9d; lParam
0x18000f779  mov     rcx, rsi; hWnd
0x18000f77c  call    cs:__imp_SendMessageW
0x18000f782  mov     eax, ebx
0x18000f784  mov     rbx, [rsp+28h+arg_0]
0x18000f789  mov     rsi, [rsp+28h+arg_8]
0x18000f78e  add     rsp, 20h
0x18000f792  pop     rdi
0x18000f793  retn
```

# CBridgeWindow::_AttachOrDetachInputQueues(bool,HWND__ *,bool)

- ea: `0x18005ecdc`
- end: `0x18005edab`
- name: `?_AttachOrDetachInputQueues@CBridgeWindow@@AEAAJ_NPEAUHWND__@@0@Z`
- size: `207`
- prototype: `int(CBridgeWindow *__hidden this, bool, HWND, bool)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800414e0`
- `0x18005dc10`
- `0x18005f828`
- `0x18005fa00`

## callees

- `0x18005ecdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ed3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ed6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ed3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ed6e`
- `USER32!AttachThreadInput` at `0x18005ed51`
- `USER32!AttachThreadInput` at `0x18005ed81`
- `USER32!AttachThreadInput` at `0x18005ed51`
- `USER32!AttachThreadInput` at `0x18005ed81`
- `USER32!SetActiveWindow` at `0x18005ed60`
- `USER32!SetActiveWindow` at `0x18005ed60`
- `USER32!GetActiveWindow` at `0x18005ed20`
- `USER32!GetActiveWindow` at `0x18005ed20`
- `USER32!GetWindowThreadProcessId` at `0x18005ed09`
- `USER32!GetWindowThreadProcessId` at `0x18005ed09`

## pseudocode

```c
__int64 __fastcall CBridgeWindow::_AttachOrDetachInputQueues(CBridgeWindow *this, char a2, HWND a3, char a4)
{
  DWORD WindowThreadProcessId; // ebp
  HWND ActiveWindow; // rsi
  DWORD CurrentThreadId; // eax
  DWORD v10; // eax

  if ( *((_BYTE *)this + 248) )
  {
    *((_BYTE *)this + 249) = a2;
  }
  else
  {
    WindowThreadProcessId = GetWindowThreadProcessId(a3, 0);
    if ( WindowThreadProcessId )
    {
      if ( a2 )
      {
        ActiveWindow = GetActiveWindow();
        if ( !ActiveWindow )
          ActiveWindow = (HWND)*((_QWORD *)this + 21);
        CurrentThreadId = GetCurrentThreadId();
        AttachThreadInput(WindowThreadProcessId, CurrentThreadId, 1);
        SetActiveWindow(ActiveWindow);
      }
      else
      {
        do
          v10 = GetCurrentThreadId();
        while ( AttachThreadInput(WindowThreadProcessId, v10, 0) );
      }
    }
  }
  if ( !a4 )
    *((_BYTE *)this + 249) = a2;
  return 0;
}

```

## disassembly

```asm
0x18005ecdc  push    rbx
0x18005ecde  push    rbp
0x18005ecdf  push    rsi
0x18005ece0  push    rdi
0x18005ece1  push    r14
0x18005ece3  sub     rsp, 20h
0x18005ece7  cmp     byte ptr [rcx+0F8h], 0
0x18005ecee  mov     r14b, r9b
0x18005ecf1  mov     dil, dl
0x18005ecf4  mov     rbx, rcx
0x18005ecf7  jz      short loc_18005ED04
0x18005ecf9  mov     [rcx+0F9h], dl
0x18005ecff  jmp     loc_18005ED91
0x18005ed04  xor     edx, edx; lpdwProcessId
0x18005ed06  mov     rcx, r8; hWnd
0x18005ed09  call    cs:__imp_GetWindowThreadProcessId
0x18005ed10  nop     dword ptr [rax+rax+00h]
0x18005ed15  mov     ebp, eax
0x18005ed17  test    eax, eax
0x18005ed19  jz      short loc_18005ED91
0x18005ed1b  test    dil, dil
0x18005ed1e  jz      short loc_18005ED6E
0x18005ed20  call    cs:__imp_GetActiveWindow
0x18005ed27  nop     dword ptr [rax+rax+00h]
0x18005ed2c  mov     rsi, rax
0x18005ed2f  test    rax, rax
0x18005ed32  jnz     short loc_18005ED3B
0x18005ed34  mov     rsi, [rbx+0A8h]
0x18005ed3b  call    cs:__imp_GetCurrentThreadId
0x18005ed42  nop     dword ptr [rax+rax+00h]
0x18005ed47  mov     r8d, 1; fAttach
0x18005ed4d  mov     ecx, ebp; idAttach
0x18005ed4f  mov     edx, eax; idAttachTo
0x18005ed51  call    cs:__imp_AttachThreadInput
0x18005ed58  nop     dword ptr [rax+rax+00h]
0x18005ed5d  mov     rcx, rsi; hWnd
0x18005ed60  call    cs:__imp_SetActiveWindow
0x18005ed67  nop     dword ptr [rax+rax+00h]
0x18005ed6c  jmp     short loc_18005ED91
0x18005ed6e  call    cs:__imp_GetCurrentThreadId
0x18005ed75  nop     dword ptr [rax+rax+00h]
0x18005ed7a  xor     r8d, r8d; fAttach
0x18005ed7d  mov     ecx, ebp; idAttach
0x18005ed7f  mov     edx, eax; idAttachTo
0x18005ed81  call    cs:__imp_AttachThreadInput
0x18005ed88  nop     dword ptr [rax+rax+00h]
0x18005ed8d  test    eax, eax
0x18005ed8f  jnz     short loc_18005ED6E
0x18005ed91  test    r14b, r14b
0x18005ed94  jnz     short loc_18005ED9D
0x18005ed96  mov     [rbx+0F9h], dil
0x18005ed9d  xor     eax, eax
0x18005ed9f  add     rsp, 20h
0x18005eda3  pop     r14
0x18005eda5  pop     rdi
0x18005eda6  pop     rsi
0x18005eda7  pop     rbp
0x18005eda8  pop     rbx
0x18005eda9  retn
```

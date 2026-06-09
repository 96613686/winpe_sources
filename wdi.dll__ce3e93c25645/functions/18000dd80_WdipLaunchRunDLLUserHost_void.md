# WdipLaunchRunDLLUserHost(void)

- ea: `0x18000dd80`
- end: `0x18000dfbe`
- name: `?WdipLaunchRunDLLUserHost@@YAJXZ`
- size: `574`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x180002ba0`
- `0x18000dd80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000deaa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000deaa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000df81`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000dfb6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000df81`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000dfb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df1c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000df03`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000df03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de81`
- `USER32!DestroyWindow` at `0x18000de56`
- `USER32!DestroyWindow` at `0x18000de56`
- `USER32!CreateWindowExW` at `0x18000ddf2`
- `USER32!CreateWindowExW` at `0x18000ddf2`
- `USER32!PeekMessageW` at `0x18000dfa7`
- `USER32!PeekMessageW` at `0x18000dfa7`
- `USER32!DispatchMessageW` at `0x18000df8c`
- `USER32!DispatchMessageW` at `0x18000df8c`
- `USER32!MsgWaitForMultipleObjects` at `0x18000df5b`
- `USER32!MsgWaitForMultipleObjects` at `0x18000df5b`

## string_xrefs

- `0x18000de37`: `WdipLaunchRunDLLUserHost`

## pseudocode

```c
__int64 WdipLaunchRunDLLUserHost(void)
{
  HWND Window; // rsi
  signed int LastError; // eax
  signed int v2; // ebx
  char *EventW; // rdi
  int v4; // r8d
  signed int v6; // eax
  signed int v7; // eax
  DWORD v8; // eax
  MSG Msg; // [rsp+60h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp+8h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  hObject = 0;
  Window = CreateWindowExW(0, L"MESSAGE", L"WDIWnd", 0, 0x80000000, 0x80000000, 0x80000000, 0x80000000, 0, 0, 0, 0);
  if ( (((unsigned __int64)Window + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
      EventW = 0;
      v4 = 203;
LABEL_6:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
        (int)L"WdipLaunchRunDLLUserHost",
        v4,
        (int)L"Error = %d",
        v2);
      goto LABEL_7;
    }
  }
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  if ( ((unsigned __int64)(EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = GetLastError();
    v2 = v6;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    if ( v2 < 0 )
    {
      v4 = 209;
      goto LABEL_6;
    }
  }
  hObject = CreateThread(0, 0, WdipTriggerHost, EventW, 0, 0);
  if ( (((unsigned __int64)hObject + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v7 = GetLastError();
    v2 = v7;
    if ( v7 > 0 )
      v2 = (unsigned __int16)v7 | 0x80070000;
    if ( v2 < 0 )
    {
      v4 = 221;
      goto LABEL_6;
    }
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v8 = MsgWaitForMultipleObjects(1u, &hObject, 0, 0xFFFFFFFF, 0x1CFFu);
      v2 = v8;
      if ( v8 != -1 )
        break;
      SetEvent(EventW);
    }
    if ( !v8 )
      break;
    if ( v8 == 1 )
    {
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        if ( Msg.message == 22 )
          SetEvent(EventW);
        DispatchMessageW(&Msg);
      }
    }
  }
LABEL_7:
  if ( Window )
    DestroyWindow(Window);
  if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(EventW);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000dd80  mov     rax, rsp
0x18000dd83  mov     [rax+10h], rbx
0x18000dd87  mov     [rax+18h], rsi
0x18000dd8b  push    rdi
0x18000dd8c  sub     rsp, 90h
0x18000dd93  mov     qword ptr [rax-40h], 0
0x18000dd9b  lea     r8, WindowName; "WDIWnd"
0x18000dda2  mov     qword ptr [rax-48h], 0
0x18000ddaa  lea     rdx, ClassName; "MESSAGE"
0x18000ddb1  mov     qword ptr [rax-50h], 0
0x18000ddb9  xorps   xmm0, xmm0
0x18000ddbc  mov     qword ptr [rax-58h], 0
0x18000ddc4  xor     r9d, r9d; dwStyle
0x18000ddc7  movups  xmmword ptr [rax-38h], xmm0
0x18000ddcb  mov     qword ptr [rax+8], 0
0x18000ddd3  xor     ecx, ecx; dwExStyle
0x18000ddd5  movups  xmmword ptr [rax-28h], xmm0
0x18000ddd9  movups  xmmword ptr [rax-18h], xmm0
0x18000dddd  mov     eax, 80000000h
0x18000dde2  mov     [rsp+98h+nHeight], eax; nHeight
0x18000dde6  mov     [rsp+98h+nWidth], eax; nWidth
0x18000ddea  mov     [rsp+98h+Y], eax; Y
0x18000ddee  mov     [rsp+98h+X], eax; X
0x18000ddf2  call    cs:__imp_CreateWindowExW
0x18000ddf8  mov     rsi, rax
0x18000ddfb  lea     rcx, [rax+1]
0x18000ddff  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18000de06  jnz     loc_18000DE9E
0x18000de0c  call    cs:__imp_GetLastError
0x18000de12  mov     ebx, eax
0x18000de14  test    eax, eax
0x18000de16  jle     short loc_18000DE21
0x18000de18  movzx   ebx, ax
0x18000de1b  or      ebx, 80070000h
0x18000de21  test    ebx, ebx
0x18000de23  jns     short loc_18000DE9E
0x18000de25  xor     edi, edi
0x18000de27  mov     r8d, 0CBh; int
0x18000de2d  movzx   eax, bx
0x18000de30  lea     r9, aErrorD_0; "Error = %d"
0x18000de37  lea     rdx, aWdiplaunchrund_0; "WdipLaunchRunDLLUserHost"
0x18000de3e  mov     [rsp+98h+X], eax; Args
0x18000de42  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000de49  call    WdipTraceError
0x18000de4e  test    rsi, rsi
0x18000de51  jz      short loc_18000DE5C
0x18000de53  mov     rcx, rsi; hWnd
0x18000de56  call    cs:__imp_DestroyWindow
0x18000de5c  lea     rax, [rdi-1]
0x18000de60  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000de64  ja      short loc_18000DE6F
0x18000de66  mov     rcx, rdi; hObject
0x18000de69  call    cs:__imp_CloseHandle
0x18000de6f  mov     rcx, [rsp+98h+hObject]; hObject
0x18000de77  lea     rax, [rcx-1]
0x18000de7b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000de7f  ja      short loc_18000DE87
0x18000de81  call    cs:__imp_CloseHandle
0x18000de87  lea     r11, [rsp+98h+var_8]
0x18000de8f  mov     eax, ebx
0x18000de91  mov     rbx, [r11+18h]
0x18000de95  mov     rsi, [r11+20h]
0x18000de99  mov     rsp, r11
0x18000de9c  pop     rdi
0x18000de9d  retn
0x18000de9e  xor     r9d, r9d; lpName
0x18000dea1  xor     r8d, r8d; bInitialState
0x18000dea4  xor     ecx, ecx; lpEventAttributes
0x18000dea6  lea     edx, [r9+1]; bManualReset
0x18000deaa  call    cs:__imp_CreateEventW
0x18000deb0  mov     rdi, rax
0x18000deb3  lea     rcx, [rax+1]
0x18000deb7  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18000debe  jnz     short loc_18000DEE4
0x18000dec0  call    cs:__imp_GetLastError
0x18000dec6  mov     ebx, eax
0x18000dec8  test    eax, eax
0x18000deca  jle     short loc_18000DED5
0x18000decc  movzx   ebx, ax
0x18000decf  or      ebx, 80070000h
0x18000ded5  test    ebx, ebx
0x18000ded7  jns     short loc_18000DEE4
0x18000ded9  mov     r8d, 0D1h
0x18000dedf  jmp     loc_18000DE2D
0x18000dee4  mov     qword ptr [rsp+98h+Y], 0; lpThreadId
0x18000deed  lea     r8, WdipTriggerHost; lpStartAddress
0x18000def4  mov     r9, rdi; lpParameter
0x18000def7  mov     [rsp+98h+X], 0; dwCreationFlags
0x18000deff  xor     edx, edx; dwStackSize
0x18000df01  xor     ecx, ecx; lpThreadAttributes
0x18000df03  call    cs:__imp_CreateThread
0x18000df09  mov     [rsp+98h+hObject], rax
0x18000df11  inc     rax
0x18000df14  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000df1a  jnz     short loc_18000DF40
0x18000df1c  call    cs:__imp_GetLastError
0x18000df22  mov     ebx, eax
0x18000df24  test    eax, eax
0x18000df26  jle     short loc_18000DF31
0x18000df28  movzx   ebx, ax
0x18000df2b  or      ebx, 80070000h
0x18000df31  test    ebx, ebx
0x18000df33  jns     short loc_18000DF40
0x18000df35  mov     r8d, 0DDh
0x18000df3b  jmp     loc_18000DE2D
0x18000df40  xor     r8d, r8d; fWaitAll
0x18000df43  mov     [rsp+98h+X], 1CFFh; dwWakeMask
0x18000df4b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000df4f  lea     rdx, [rsp+98h+hObject]; pHandles
0x18000df57  lea     ecx, [r8+1]; nCount
0x18000df5b  call    cs:__imp_MsgWaitForMultipleObjects
0x18000df61  mov     ebx, eax
0x18000df63  cmp     eax, 0FFFFFFFFh
0x18000df66  jz      short loc_18000DFB3
0x18000df68  test    eax, eax
0x18000df6a  jz      loc_18000DE4E
0x18000df70  cmp     eax, 1
0x18000df73  jnz     short loc_18000DF40
0x18000df75  jmp     short loc_18000DF92
0x18000df77  cmp     [rsp+98h+Msg.message], 16h
0x18000df7c  jnz     short loc_18000DF87
0x18000df7e  mov     rcx, rdi; hEvent
0x18000df81  call    cs:__imp_SetEvent
0x18000df87  lea     rcx, [rsp+98h+Msg]; lpMsg
0x18000df8c  call    cs:__imp_DispatchMessageW
0x18000df92  xor     r9d, r9d; wMsgFilterMax
0x18000df95  mov     [rsp+98h+X], 1; wRemoveMsg
0x18000df9d  xor     r8d, r8d; wMsgFilterMin
0x18000dfa0  lea     rcx, [rsp+98h+Msg]; lpMsg
0x18000dfa5  xor     edx, edx; hWnd
0x18000dfa7  call    cs:__imp_PeekMessageW
0x18000dfad  test    eax, eax
0x18000dfaf  jnz     short loc_18000DF77
0x18000dfb1  jmp     short loc_18000DF40
0x18000dfb3  mov     rcx, rdi; hEvent
0x18000dfb6  call    cs:__imp_SetEvent
0x18000dfbc  jmp     short loc_18000DF40
```

# ComTaskMgrWnd::CreateMsgPumpThread(void)

- ea: `0x140005b50`
- end: `0x140005c61`
- name: `?CreateMsgPumpThread@ComTaskMgrWnd@@AEAAJXZ`
- size: `273`
- prototype: `__int64 __fastcall(ComTaskMgrWnd *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140005b20`

## callees

- `0x140005b50`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140005bb5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140005bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005c13`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005b69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005b8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005b69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005b8b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005bcc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005bcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005bf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005bf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c55`

## pseudocode

```c
__int64 __fastcall ComTaskMgrWnd::CreateMsgPumpThread(ComTaskMgrWnd *this)
{
  HANDLE EventW; // rax
  HANDLE v3; // rax
  HANDLE *v4; // rbx
  HANDLE Thread; // rax
  signed int v6; // edi
  signed int LastError; // eax
  signed int v9; // eax
  char *v10; // rcx

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 7) = EventW;
  if ( EventW )
  {
    v3 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 5) = v3;
    v4 = (HANDLE *)((char *)this + 40);
    if ( v3
      && (Thread = CreateThread(0, 0, ComTaskMgrWnd::MsgPumpThreadProc, 0, 0, 0), (*((_QWORD *)this + 6) = Thread) != 0) )
    {
      WaitForSingleObject(*v4, 0xFFFFFFFF);
      v6 = *((_DWORD *)this + 8);
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v9 = GetLastError();
    v6 = v9;
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
    v4 = (HANDLE *)((char *)this + 40);
  }
  if ( (char *)*v4 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*v4);
    *v4 = 0;
  }
  if ( v6 < 0 )
  {
    if ( *((_QWORD *)this + 6) )
    {
      (*(void (__fastcall **)(ComTaskMgrWnd *))(*(_QWORD *)this + 48LL))(this);
    }
    else
    {
      v10 = (char *)*((_QWORD *)this + 7);
      if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(v10);
        *((_QWORD *)this + 7) = 0;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140005b50  push    rbx
0x140005b52  push    rbp
0x140005b53  push    rsi
0x140005b54  push    rdi
0x140005b55  sub     rsp, 38h
0x140005b59  mov     rsi, rcx
0x140005b5c  xor     r9d, r9d; lpName
0x140005b5f  xor     ecx, ecx; lpEventAttributes
0x140005b61  xor     r8d, r8d; bInitialState
0x140005b64  mov     edx, 1; bManualReset
0x140005b69  call    cs:__imp_CreateEventW
0x140005b6f  xor     ebp, ebp
0x140005b71  mov     [rsi+38h], rax
0x140005b75  test    rax, rax
0x140005b78  jz      loc_140005C13
0x140005b7e  xor     r9d, r9d; lpName
0x140005b81  xor     r8d, r8d; bInitialState
0x140005b84  mov     edx, 1; bManualReset
0x140005b89  xor     ecx, ecx; lpEventAttributes
0x140005b8b  call    cs:__imp_CreateEventW
0x140005b91  mov     [rsi+28h], rax
0x140005b95  lea     rbx, [rsi+28h]
0x140005b99  test    rax, rax
0x140005b9c  jz      short loc_140005BFC
0x140005b9e  mov     [rsp+58h+lpThreadId], rbp; lpThreadId
0x140005ba3  lea     r8, ?MsgPumpThreadProc@ComTaskMgrWnd@@CAKPEAX@Z; lpStartAddress
0x140005baa  xor     r9d, r9d; lpParameter
0x140005bad  mov     [rsp+58h+dwCreationFlags], ebp; dwCreationFlags
0x140005bb1  xor     edx, edx; dwStackSize
0x140005bb3  xor     ecx, ecx; lpThreadAttributes
0x140005bb5  call    cs:__imp_CreateThread
0x140005bbb  mov     [rsi+30h], rax
0x140005bbf  test    rax, rax
0x140005bc2  jz      short loc_140005BFC
0x140005bc4  mov     rcx, [rbx]; hHandle
0x140005bc7  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140005bcc  call    cs:__imp_WaitForSingleObject
0x140005bd2  mov     edi, [rsi+20h]
0x140005bd5  mov     rcx, [rbx]; hObject
0x140005bd8  lea     rax, [rcx-1]
0x140005bdc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140005be0  jbe     short loc_140005BF1
0x140005be2  test    edi, edi
0x140005be4  js      short loc_140005C30
0x140005be6  mov     eax, edi
0x140005be8  add     rsp, 38h
0x140005bec  pop     rdi
0x140005bed  pop     rsi
0x140005bee  pop     rbp
0x140005bef  pop     rbx
0x140005bf0  retn
0x140005bf1  call    cs:__imp_CloseHandle
0x140005bf7  mov     [rbx], rbp
0x140005bfa  jmp     short loc_140005BE2
0x140005bfc  call    cs:__imp_GetLastError
0x140005c02  mov     edi, eax
0x140005c04  test    eax, eax
0x140005c06  jle     short loc_140005BD5
0x140005c08  movzx   edi, ax
0x140005c0b  or      edi, 80070000h
0x140005c11  jmp     short loc_140005BD5
0x140005c13  call    cs:__imp_GetLastError
0x140005c19  mov     edi, eax
0x140005c1b  test    eax, eax
0x140005c1d  jg      short loc_140005C25
0x140005c1f  lea     rbx, [rsi+28h]
0x140005c23  jmp     short loc_140005BD5
0x140005c25  movzx   edi, ax
0x140005c28  or      edi, 80070000h
0x140005c2e  jmp     short loc_140005C1F
0x140005c30  cmp     [rsi+30h], rbp
0x140005c34  jz      short loc_140005C47
0x140005c36  mov     rcx, [rsi]
0x140005c39  mov     rax, [rcx+30h]
0x140005c3d  mov     rcx, rsi
0x140005c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c45  jmp     short loc_140005BE6
0x140005c47  mov     rcx, [rsi+38h]; hObject
0x140005c4b  lea     rax, [rcx-1]
0x140005c4f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140005c53  ja      short loc_140005BE6
0x140005c55  call    cs:__imp_CloseHandle
0x140005c5b  mov     [rsi+38h], rbp
0x140005c5f  jmp     short loc_140005BE6
```

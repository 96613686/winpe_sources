# ComTaskHost::Stop(void)

- ea: `0x140004cf0`
- end: `0x140004eb9`
- name: `?Stop@ComTaskHost@@QEAAJXZ`
- size: `457`
- prototype: `__int64 __fastcall(ComTaskHost *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009a40`

## callees

- `0x140004cf0`
- `0x1400050c0`
- `0x140005150`
- `0x140009be0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x140004e34`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x140004e34`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004d76`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004d76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004d90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004d90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004dfe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004dfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004ea3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004ea3`

## pseudocode

```c
__int64 __fastcall ComTaskHost::Stop(ComTaskHost *this)
{
  char *v2; // rbx
  signed int v3; // edi
  signed __int32 v4; // eax
  signed __int32 v5; // eax
  char *Thread; // rax
  signed int LastError; // eax
  signed int v8; // eax
  signed int v9; // eax
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF
  char *v12; // [rsp+60h] [rbp+18h]

  ExitCode = 0;
  v2 = 0;
  v12 = 0;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 8, 1) != 1 )
  {
    v3 = 0;
    v4 = _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 8, 5);
    if ( v4 == 4
      || v4 == 7
      || (v5 = _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 8, 2), v5 == 4)
      || v5 == 7 )
    {
      ComTaskHost::ReleaseLifetimeRef(this, L"Stop");
    }
    goto LABEL_32;
  }
  Thread = (char *)CreateThread(0, 0, ComTaskHost::StopTaskThread, this, 0, 0);
  v2 = Thread;
  v12 = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids, this, v3);
    ComTaskHost::WaitForTaskStartCompletion(this);
    ComTaskHost::ReleaseLifetimeRef(this, L"Stop");
LABEL_28:
    if ( v3 >= 0 )
      goto LABEL_32;
    goto LABEL_29;
  }
  ExitCode = WaitForSingleObject(Thread, 0xFFFFFFFF);
  if ( ExitCode )
  {
    v8 = GetLastError();
    v3 = v8;
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
  }
  else
  {
    if ( GetExitCodeThread(v2, &ExitCode) )
    {
      v3 = ExitCode;
      goto LABEL_28;
    }
    v9 = GetLastError();
    v3 = v9;
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
  }
LABEL_29:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids, this, v3);
LABEL_32:
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140004cf0  mov     [rsp+arg_18], rbx
0x140004cf5  push    rbp
0x140004cf6  push    rsi
0x140004cf7  push    rdi
0x140004cf8  sub     rsp, 30h
0x140004cfc  mov     rsi, rcx
0x140004cff  xor     ecx, ecx
0x140004d01  mov     [rsp+48h+ExitCode], ecx
0x140004d05  mov     ebx, ecx
0x140004d07  mov     [rsp+48h+arg_10], rcx
0x140004d0c  mov     edx, 8
0x140004d11  mov     eax, 1
0x140004d16  lock cmpxchg [rsi+10h], edx
0x140004d1b  jz      short loc_140004D5F
0x140004d1d  mov     edi, ecx
0x140004d1f  mov     eax, 5
0x140004d24  lock cmpxchg [rsi+10h], edx
0x140004d29  cmp     eax, 4
0x140004d2c  jz      short loc_140004D4B
0x140004d2e  cmp     eax, 7
0x140004d31  jz      short loc_140004D4B
0x140004d33  mov     eax, 2
0x140004d38  lock cmpxchg [rsi+10h], edx
0x140004d3d  cmp     eax, 4
0x140004d40  jz      short loc_140004D4B
0x140004d42  cmp     eax, 7
0x140004d45  jnz     loc_140004E96
0x140004d4b  lea     rdx, aStop; "Stop"
0x140004d52  mov     rcx, rsi; this
0x140004d55  call    ?ReleaseLifetimeRef@ComTaskHost@@QEAAKPEBG@Z; ComTaskHost::ReleaseLifetimeRef(ushort const *)
0x140004d5a  jmp     loc_140004E96
0x140004d5f  mov     [rsp+48h+lpThreadId], rcx; lpThreadId
0x140004d64  mov     [rsp+48h+dwCreationFlags], ecx; dwCreationFlags
0x140004d68  mov     r9, rsi; lpParameter
0x140004d6b  lea     r8, ?StopTaskThread@ComTaskHost@@CAKPEAX@Z; lpStartAddress
0x140004d72  xor     edx, edx; dwStackSize
0x140004d74  xor     ecx, ecx; lpThreadAttributes
0x140004d76  call    cs:__imp_CreateThread
0x140004d7c  mov     rbx, rax
0x140004d7f  mov     [rsp+48h+arg_10], rax
0x140004d84  lea     rbp, WPP_GLOBAL_Control
0x140004d8b  test    rax, rax
0x140004d8e  jnz     short loc_140004DF6
0x140004d90  call    cs:__imp_GetLastError
0x140004d96  mov     edi, eax
0x140004d98  test    eax, eax
0x140004d9a  jle     short loc_140004DA5
0x140004d9c  movzx   edi, ax
0x140004d9f  or      edi, 80070000h
0x140004da5  mov     eax, 80004005h
0x140004daa  test    edi, edi
0x140004dac  cmovns  edi, eax
0x140004daf  mov     rcx, cs:WPP_GLOBAL_Control
0x140004db6  cmp     rcx, rbp
0x140004db9  jz      short loc_140004DDD
0x140004dbb  test    byte ptr [rcx+1Ch], 1
0x140004dbf  jz      short loc_140004DDD
0x140004dc1  mov     edx, 11h
0x140004dc6  mov     [rsp+48h+dwCreationFlags], edi
0x140004dca  mov     r9, rsi
0x140004dcd  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x140004dd4  mov     rcx, [rcx+10h]
0x140004dd8  call    WPP_SF_qD
0x140004ddd  mov     rcx, rsi; this
0x140004de0  call    ?WaitForTaskStartCompletion@ComTaskHost@@AEAAJXZ; ComTaskHost::WaitForTaskStartCompletion(void)
0x140004de5  lea     rdx, aStop; "Stop"
0x140004dec  mov     rcx, rsi; this
0x140004def  call    ?ReleaseLifetimeRef@ComTaskHost@@QEAAKPEBG@Z; ComTaskHost::ReleaseLifetimeRef(ushort const *)
0x140004df4  jmp     short loc_140004E63
0x140004df6  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140004dfb  mov     rcx, rbx; hHandle
0x140004dfe  call    cs:__imp_WaitForSingleObject
0x140004e04  mov     [rsp+48h+ExitCode], eax
0x140004e08  test    eax, eax
0x140004e0a  jz      short loc_140004E2C
0x140004e0c  call    cs:__imp_GetLastError
0x140004e12  mov     edi, eax
0x140004e14  test    eax, eax
0x140004e16  jle     short loc_140004E21
0x140004e18  movzx   edi, ax
0x140004e1b  or      edi, 80070000h
0x140004e21  test    edi, edi
0x140004e23  js      short loc_140004E67
0x140004e25  mov     edi, 80004005h
0x140004e2a  jmp     short loc_140004E67
0x140004e2c  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x140004e31  mov     rcx, rbx; hThread
0x140004e34  call    cs:__imp_GetExitCodeThread
0x140004e3a  test    eax, eax
0x140004e3c  jnz     short loc_140004E5F
0x140004e3e  call    cs:__imp_GetLastError
0x140004e44  mov     edi, eax
0x140004e46  test    eax, eax
0x140004e48  jle     short loc_140004E53
0x140004e4a  movzx   edi, ax
0x140004e4d  or      edi, 80070000h
0x140004e53  mov     eax, 80004005h
0x140004e58  test    edi, edi
0x140004e5a  cmovns  edi, eax
0x140004e5d  jmp     short loc_140004E67
0x140004e5f  mov     edi, [rsp+48h+ExitCode]
0x140004e63  test    edi, edi
0x140004e65  jns     short loc_140004E96
0x140004e67  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e6e  cmp     rcx, rbp
0x140004e71  jz      short loc_140004E96
0x140004e73  test    byte ptr [rcx+1Ch], 1
0x140004e77  jz      short loc_140004E96
0x140004e79  mov     edx, 12h
0x140004e7e  mov     [rsp+48h+dwCreationFlags], edi
0x140004e82  mov     r9, rsi
0x140004e85  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x140004e8c  mov     rcx, [rcx+10h]
0x140004e90  call    WPP_SF_qD
0x140004e95  nop
0x140004e96  lea     rcx, [rbx-1]
0x140004e9a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140004e9e  ja      short loc_140004EAA
0x140004ea0  mov     rcx, rbx; hObject
0x140004ea3  call    cs:__imp_CloseHandle
0x140004ea9  nop
0x140004eaa  mov     eax, edi
0x140004eac  mov     rbx, [rsp+48h+arg_18]
0x140004eb1  add     rsp, 30h
0x140004eb5  pop     rdi
0x140004eb6  pop     rsi
0x140004eb7  pop     rbp
0x140004eb8  retn
```

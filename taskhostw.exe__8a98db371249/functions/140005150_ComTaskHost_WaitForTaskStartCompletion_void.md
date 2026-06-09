# ComTaskHost::WaitForTaskStartCompletion(void)

- ea: `0x140005150`
- end: `0x140005264`
- name: `?WaitForTaskStartCompletion@ComTaskHost@@AEAAJXZ`
- size: `276`
- prototype: `__int64 __fastcall(ComTaskHost *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004cf0`
- `0x140004ec0`

## callees

- `0x140005150`
- `0x140009370`
- `0x140009be0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400051f2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400051f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400051b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400051b3`

## pseudocode

```c
__int64 __fastcall ComTaskHost::WaitForTaskStartCompletion(ComTaskHost *this)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  signed int v4; // eax
  DWORD ExitCode; // [rsp+40h] [rbp+8h] BYREF

  ExitCode = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids, this);
  ExitCode = WaitForSingleObject(
               (HANDLE)_InterlockedCompareExchange64((volatile signed __int64 *)this + 10, -1, -1),
               0xFFFFFFFF);
  if ( ExitCode )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( (v3 & 0x80000000) == 0 )
      v3 = -2147467259;
  }
  else if ( GetExitCodeThread(
              (HANDLE)_InterlockedCompareExchange64((volatile signed __int64 *)this + 10, -1, -1),
              &ExitCode) )
  {
    v3 = ExitCode;
    if ( (ExitCode & 0x80000000) == 0 )
      return v3;
  }
  else
  {
    v4 = GetLastError();
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
    v3 = v4;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids, this, v3);
  return v3;
}

```

## disassembly

```asm
0x140005150  mov     [rsp+arg_8], rbx
0x140005155  mov     [rsp+arg_10], rsi
0x14000515a  push    rdi
0x14000515b  sub     rsp, 30h
0x14000515f  mov     rdi, rcx
0x140005162  mov     [rsp+38h+ExitCode], 0
0x14000516a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005171  lea     rsi, WPP_GLOBAL_Control
0x140005178  cmp     rcx, rsi
0x14000517b  jz      short loc_14000519B
0x14000517d  test    byte ptr [rcx+1Ch], 4
0x140005181  jz      short loc_14000519B
0x140005183  mov     rcx, [rcx+10h]
0x140005187  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x14000518e  mov     edx, 15h
0x140005193  mov     r9, rdi
0x140005196  call    WPP_SF_q
0x14000519b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400051a2  mov     rax, rbx
0x1400051a5  lock cmpxchg [rdi+50h], rbx
0x1400051ab  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1400051b0  mov     rcx, rax; hHandle
0x1400051b3  call    cs:__imp_WaitForSingleObject
0x1400051b9  mov     [rsp+38h+ExitCode], eax
0x1400051bd  test    eax, eax
0x1400051bf  jz      short loc_1400051E1
0x1400051c1  call    cs:__imp_GetLastError
0x1400051c7  mov     ebx, eax
0x1400051c9  test    eax, eax
0x1400051cb  jle     short loc_1400051D6
0x1400051cd  movzx   ebx, ax
0x1400051d0  or      ebx, 80070000h
0x1400051d6  test    ebx, ebx
0x1400051d8  js      short loc_140005224
0x1400051da  mov     ebx, 80004005h
0x1400051df  jmp     short loc_140005224
0x1400051e1  mov     rax, rbx
0x1400051e4  lock cmpxchg [rdi+50h], rbx
0x1400051ea  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x1400051ef  mov     rcx, rax; hThread
0x1400051f2  call    cs:__imp_GetExitCodeThread
0x1400051f8  test    eax, eax
0x1400051fa  jnz     short loc_14000521C
0x1400051fc  call    cs:__imp_GetLastError
0x140005202  test    eax, eax
0x140005204  jle     short loc_14000520E
0x140005206  movzx   eax, ax
0x140005209  or      eax, 80070000h
0x14000520e  mov     ebx, 80004005h
0x140005213  test    eax, eax
0x140005215  cmovns  eax, ebx
0x140005218  mov     ebx, eax
0x14000521a  jmp     short loc_140005224
0x14000521c  mov     ebx, [rsp+38h+ExitCode]
0x140005220  test    ebx, ebx
0x140005222  jns     short loc_140005252
0x140005224  mov     rcx, cs:WPP_GLOBAL_Control
0x14000522b  cmp     rcx, rsi
0x14000522e  jz      short loc_140005252
0x140005230  test    byte ptr [rcx+1Ch], 1
0x140005234  jz      short loc_140005252
0x140005236  mov     rcx, [rcx+10h]
0x14000523a  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x140005241  mov     edx, 16h
0x140005246  mov     [rsp+38h+var_18], ebx
0x14000524a  mov     r9, rdi
0x14000524d  call    WPP_SF_qD
0x140005252  mov     rsi, [rsp+38h+arg_10]
0x140005257  mov     eax, ebx
0x140005259  mov     rbx, [rsp+38h+arg_8]
0x14000525e  add     rsp, 30h
0x140005262  pop     rdi
0x140005263  retn
```

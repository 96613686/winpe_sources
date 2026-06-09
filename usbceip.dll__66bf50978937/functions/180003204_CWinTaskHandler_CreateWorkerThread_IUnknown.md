# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180003204`
- end: `0x180003358`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003990`

## callees

- `0x180003204`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003255`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003255`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000330c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000330c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032bf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800032aa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800032aa`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003340`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003340`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::CreateWorkerThread(CWinTaskHandler *this, struct IUnknown *a2)
{
  _QWORD *v2; // rsi
  signed int v4; // ebx
  signed int LastError; // eax
  HANDLE Thread; // rax
  signed int v7; // eax
  char *v8; // rcx
  HMODULE v9; // rcx
  signed __int32 v11[8]; // [rsp+0h] [rbp-38h] BYREF

  v2 = (_QWORD *)((char *)this + 48);
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         (char *)this + 48);
  if ( v4 >= 0 )
  {
    if ( *((_DWORD *)this + 4) )
    {
      if ( GetModuleHandleExW(4u, &_ImageBase, (HMODULE *)this + 3) )
      {
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_13;
      }
    }
    (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 8LL))(this);
    Thread = CreateThread(0, 0, CWinTaskHandler::WorkerThreadProc, this, 4u, 0);
    *((_QWORD *)this + 5) = Thread;
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 16LL))(this);
    }
  }
  if ( v4 >= 0 )
  {
    _InterlockedOr(v11, 0);
    ResumeThread(*((HANDLE *)this + 5));
    return (unsigned int)v4;
  }
LABEL_13:
  v8 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 5) = -1;
  }
  v9 = (HMODULE)*((_QWORD *)this + 3);
  if ( v9 )
  {
    FreeLibrary(v9);
    *((_QWORD *)this + 3) = 0;
  }
  if ( *v2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003204  mov     [rsp+arg_0], rbx
0x180003209  mov     [rsp+arg_8], rsi
0x18000320e  push    rdi
0x18000320f  sub     rsp, 30h
0x180003213  mov     rax, [rdx]
0x180003216  lea     rsi, [rcx+30h]
0x18000321a  mov     r9, rdx
0x18000321d  mov     rdi, rcx
0x180003220  mov     r8, rsi
0x180003223  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000322a  mov     rcx, r9
0x18000322d  mov     rax, [rax]
0x180003230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003235  mov     ebx, eax
0x180003237  test    eax, eax
0x180003239  js      loc_1800032E3
0x18000323f  cmp     dword ptr [rdi+10h], 0
0x180003243  jz      short loc_18000327C
0x180003245  lea     r8, [rdi+18h]; phModule
0x180003249  mov     ecx, 4; dwFlags
0x18000324e  lea     rdx, __ImageBase; lpModuleName
0x180003255  call    cs:__imp_GetModuleHandleExW
0x18000325b  test    eax, eax
0x18000325d  jz      short loc_180003263
0x18000325f  xor     ebx, ebx
0x180003261  jmp     short loc_18000327C
0x180003263  call    cs:__imp_GetLastError
0x180003269  mov     ebx, eax
0x18000326b  test    eax, eax
0x18000326d  jle     short loc_180003278
0x18000326f  movzx   ebx, ax
0x180003272  or      ebx, 80070000h
0x180003278  test    ebx, ebx
0x18000327a  js      short loc_1800032E7
0x18000327c  mov     rax, [rdi]
0x18000327f  mov     rcx, rdi
0x180003282  mov     rax, [rax+8]
0x180003286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328b  mov     r9, rdi; lpParameter
0x18000328e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180003297  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000329e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1800032a6  xor     edx, edx; dwStackSize
0x1800032a8  xor     ecx, ecx; lpThreadAttributes
0x1800032aa  call    cs:__imp_CreateThread
0x1800032b0  mov     [rdi+28h], rax
0x1800032b4  inc     rax
0x1800032b7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800032bd  jnz     short loc_1800032E3
0x1800032bf  call    cs:__imp_GetLastError
0x1800032c5  mov     ebx, eax
0x1800032c7  test    eax, eax
0x1800032c9  jle     short loc_1800032D4
0x1800032cb  movzx   ebx, ax
0x1800032ce  or      ebx, 80070000h
0x1800032d4  mov     rax, [rdi]
0x1800032d7  mov     rcx, rdi
0x1800032da  mov     rax, [rax+10h]
0x1800032de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e3  test    ebx, ebx
0x1800032e5  jns     short loc_180003337
0x1800032e7  mov     rcx, [rdi+28h]; hObject
0x1800032eb  lea     rax, [rcx-1]
0x1800032ef  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800032f3  ja      short loc_180003303
0x1800032f5  call    cs:__imp_CloseHandle
0x1800032fb  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180003303  mov     rcx, [rdi+18h]; hLibModule
0x180003307  test    rcx, rcx
0x18000330a  jz      short loc_18000331A
0x18000330c  call    cs:__imp_FreeLibrary
0x180003312  mov     qword ptr [rdi+18h], 0
0x18000331a  mov     rcx, [rsi]
0x18000331d  test    rcx, rcx
0x180003320  jz      short loc_180003346
0x180003322  mov     rax, [rcx]
0x180003325  mov     rax, [rax+10h]
0x180003329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000332e  mov     qword ptr [rsi], 0
0x180003335  jmp     short loc_180003346
0x180003337  lock or [rsp+38h+var_38], 0
0x18000333c  mov     rcx, [rdi+28h]; hThread
0x180003340  call    cs:__imp_ResumeThread
0x180003346  mov     rsi, [rsp+38h+arg_8]
0x18000334b  mov     eax, ebx
0x18000334d  mov     rbx, [rsp+38h+arg_0]
0x180003352  add     rsp, 30h
0x180003356  pop     rdi
0x180003357  retn
```

# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180042db4`
- end: `0x180042f08`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180046c50`

## callees

- `0x180042db4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180042ef0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180042ef0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180042e5a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180042e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e6f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042ebc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042ebc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180042e05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180042e05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042ea5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042ea5`

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
0x180042db4  mov     [rsp+arg_0], rbx
0x180042db9  mov     [rsp+arg_8], rsi
0x180042dbe  push    rdi
0x180042dbf  sub     rsp, 30h
0x180042dc3  mov     rax, [rdx]
0x180042dc6  lea     rsi, [rcx+30h]
0x180042dca  mov     r9, rdx
0x180042dcd  mov     rdi, rcx
0x180042dd0  mov     r8, rsi
0x180042dd3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180042dda  mov     rcx, r9
0x180042ddd  mov     rax, [rax]
0x180042de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042de5  mov     ebx, eax
0x180042de7  test    eax, eax
0x180042de9  js      loc_180042E93
0x180042def  cmp     dword ptr [rdi+10h], 0
0x180042df3  jz      short loc_180042E2C
0x180042df5  lea     r8, [rdi+18h]; phModule
0x180042df9  mov     ecx, 4; dwFlags
0x180042dfe  lea     rdx, __ImageBase; lpModuleName
0x180042e05  call    cs:__imp_GetModuleHandleExW
0x180042e0b  test    eax, eax
0x180042e0d  jz      short loc_180042E13
0x180042e0f  xor     ebx, ebx
0x180042e11  jmp     short loc_180042E2C
0x180042e13  call    cs:__imp_GetLastError
0x180042e19  mov     ebx, eax
0x180042e1b  test    eax, eax
0x180042e1d  jle     short loc_180042E28
0x180042e1f  movzx   ebx, ax
0x180042e22  or      ebx, 80070000h
0x180042e28  test    ebx, ebx
0x180042e2a  js      short loc_180042E97
0x180042e2c  mov     rax, [rdi]
0x180042e2f  mov     rcx, rdi
0x180042e32  mov     rax, [rax+8]
0x180042e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e3b  mov     r9, rdi; lpParameter
0x180042e3e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180042e47  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180042e4e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180042e56  xor     edx, edx; dwStackSize
0x180042e58  xor     ecx, ecx; lpThreadAttributes
0x180042e5a  call    cs:__imp_CreateThread
0x180042e60  mov     [rdi+28h], rax
0x180042e64  inc     rax
0x180042e67  test    rax, 0FFFFFFFFFFFFFFFEh
0x180042e6d  jnz     short loc_180042E93
0x180042e6f  call    cs:__imp_GetLastError
0x180042e75  mov     ebx, eax
0x180042e77  test    eax, eax
0x180042e79  jle     short loc_180042E84
0x180042e7b  movzx   ebx, ax
0x180042e7e  or      ebx, 80070000h
0x180042e84  mov     rax, [rdi]
0x180042e87  mov     rcx, rdi
0x180042e8a  mov     rax, [rax+10h]
0x180042e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e93  test    ebx, ebx
0x180042e95  jns     short loc_180042EE7
0x180042e97  mov     rcx, [rdi+28h]; hObject
0x180042e9b  lea     rax, [rcx-1]
0x180042e9f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180042ea3  ja      short loc_180042EB3
0x180042ea5  call    cs:__imp_CloseHandle
0x180042eab  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180042eb3  mov     rcx, [rdi+18h]; hLibModule
0x180042eb7  test    rcx, rcx
0x180042eba  jz      short loc_180042ECA
0x180042ebc  call    cs:__imp_FreeLibrary
0x180042ec2  mov     qword ptr [rdi+18h], 0
0x180042eca  mov     rcx, [rsi]
0x180042ecd  test    rcx, rcx
0x180042ed0  jz      short loc_180042EF6
0x180042ed2  mov     rax, [rcx]
0x180042ed5  mov     rax, [rax+10h]
0x180042ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ede  mov     qword ptr [rsi], 0
0x180042ee5  jmp     short loc_180042EF6
0x180042ee7  lock or [rsp+38h+var_38], 0
0x180042eec  mov     rcx, [rdi+28h]; hThread
0x180042ef0  call    cs:__imp_ResumeThread
0x180042ef6  mov     rsi, [rsp+38h+arg_8]
0x180042efb  mov     eax, ebx
0x180042efd  mov     rbx, [rsp+38h+arg_0]
0x180042f02  add     rsp, 30h
0x180042f06  pop     rdi
0x180042f07  retn
```

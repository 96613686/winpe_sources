# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180006cc4`
- end: `0x180006e18`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000d200`

## callees

- `0x180006cc4`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006dcc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006dcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180006d15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180006d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d7f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180006e00`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180006e00`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006d6a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006d6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006db5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006db5`

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
      if ( GetModuleHandleExW(4u, (LPCWSTR)0x180000000LL, (HMODULE *)this + 3) )
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
0x180006cc4  mov     [rsp+arg_0], rbx
0x180006cc9  mov     [rsp+arg_8], rsi
0x180006cce  push    rdi
0x180006ccf  sub     rsp, 30h
0x180006cd3  mov     rax, [rdx]
0x180006cd6  lea     rsi, [rcx+30h]
0x180006cda  mov     r9, rdx
0x180006cdd  mov     rdi, rcx
0x180006ce0  mov     r8, rsi
0x180006ce3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180006cea  mov     rcx, r9
0x180006ced  mov     rax, [rax]
0x180006cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cf5  mov     ebx, eax
0x180006cf7  test    eax, eax
0x180006cf9  js      loc_180006DA3
0x180006cff  cmp     dword ptr [rdi+10h], 0
0x180006d03  jz      short loc_180006D3C
0x180006d05  lea     r8, [rdi+18h]; phModule
0x180006d09  mov     ecx, 4; dwFlags
0x180006d0e  lea     rdx, cs:180000000h; lpModuleName
0x180006d15  call    cs:__imp_GetModuleHandleExW
0x180006d1b  test    eax, eax
0x180006d1d  jz      short loc_180006D23
0x180006d1f  xor     ebx, ebx
0x180006d21  jmp     short loc_180006D3C
0x180006d23  call    cs:__imp_GetLastError
0x180006d29  mov     ebx, eax
0x180006d2b  test    eax, eax
0x180006d2d  jle     short loc_180006D38
0x180006d2f  movzx   ebx, ax
0x180006d32  or      ebx, 80070000h
0x180006d38  test    ebx, ebx
0x180006d3a  js      short loc_180006DA7
0x180006d3c  mov     rax, [rdi]
0x180006d3f  mov     rcx, rdi
0x180006d42  mov     rax, [rax+8]
0x180006d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d4b  mov     r9, rdi; lpParameter
0x180006d4e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180006d57  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180006d5e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180006d66  xor     edx, edx; dwStackSize
0x180006d68  xor     ecx, ecx; lpThreadAttributes
0x180006d6a  call    cs:__imp_CreateThread
0x180006d70  mov     [rdi+28h], rax
0x180006d74  inc     rax
0x180006d77  test    rax, 0FFFFFFFFFFFFFFFEh
0x180006d7d  jnz     short loc_180006DA3
0x180006d7f  call    cs:__imp_GetLastError
0x180006d85  mov     ebx, eax
0x180006d87  test    eax, eax
0x180006d89  jle     short loc_180006D94
0x180006d8b  movzx   ebx, ax
0x180006d8e  or      ebx, 80070000h
0x180006d94  mov     rax, [rdi]
0x180006d97  mov     rcx, rdi
0x180006d9a  mov     rax, [rax+10h]
0x180006d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da3  test    ebx, ebx
0x180006da5  jns     short loc_180006DF7
0x180006da7  mov     rcx, [rdi+28h]; hObject
0x180006dab  lea     rax, [rcx-1]
0x180006daf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006db3  ja      short loc_180006DC3
0x180006db5  call    cs:__imp_CloseHandle
0x180006dbb  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180006dc3  mov     rcx, [rdi+18h]; hLibModule
0x180006dc7  test    rcx, rcx
0x180006dca  jz      short loc_180006DDA
0x180006dcc  call    cs:__imp_FreeLibrary
0x180006dd2  mov     qword ptr [rdi+18h], 0
0x180006dda  mov     rcx, [rsi]
0x180006ddd  test    rcx, rcx
0x180006de0  jz      short loc_180006E06
0x180006de2  mov     rax, [rcx]
0x180006de5  mov     rax, [rax+10h]
0x180006de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dee  mov     qword ptr [rsi], 0
0x180006df5  jmp     short loc_180006E06
0x180006df7  lock or [rsp+38h+var_38], 0
0x180006dfc  mov     rcx, [rdi+28h]; hThread
0x180006e00  call    cs:__imp_ResumeThread
0x180006e06  mov     rsi, [rsp+38h+arg_8]
0x180006e0b  mov     eax, ebx
0x180006e0d  mov     rbx, [rsp+38h+arg_0]
0x180006e12  add     rsp, 30h
0x180006e16  pop     rdi
0x180006e17  retn
```

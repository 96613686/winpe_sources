# CWdiHandler::Start(IUnknown *,ushort *)

- ea: `0x180003cc0`
- end: `0x180003ec5`
- name: `?Start@CWdiHandler@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `517`
- prototype: `__int64 __fastcall(CWdiHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002ba0`
- `0x180003cc0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003d78`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e20`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003e05`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003e05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003e97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003e97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003dbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003dbf`

## string_xrefs

- `0x180003d22`: `clientcore\base\diagnosis\pdi\wdi\framework\library\taskhandler.cpp`
- `0x180003e42`: `clientcore\base\diagnosis\pdi\wdi\framework\library\taskhandler.cpp`

## pseudocode

```c
__int64 __fastcall CWdiHandler::Start(CWdiHandler *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  signed int v4; // edi
  HANDLE *v5; // r14
  _QWORD *v6; // rsi
  int v7; // r8d
  int v8; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  signed int v12; // eax
  char *Thread; // rax
  signed int v14; // eax
  char *v15; // rcx
  HMODULE v16; // rcx

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = (HANDLE *)((char *)this + 24);
    v6 = (_QWORD *)((char *)this + 40);
    v7 = 91;
    LOBYTE(v8) = 87;
LABEL_24:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\taskhandler.cpp",
      (int)L"CWdiHandler::Start",
      v7,
      (int)L"Error = %d",
      v8);
    v15 = (char *)*((_QWORD *)this + 2);
    if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v15);
      *((_QWORD *)this + 2) = 0;
    }
    if ( (char *)*v5 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(*v5);
      *v5 = 0;
    }
    v16 = (HMODULE)*((_QWORD *)this + 4);
    if ( v16 )
    {
      FreeLibrary(v16);
      *((_QWORD *)this + 4) = 0;
    }
    if ( *v6 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 16LL))(*v6);
      *v6 = 0;
    }
    return (unsigned int)v4;
  }
  if ( _InterlockedCompareExchange(&g_HostState, 1, 0) )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\taskhandler.cpp",
      (int)L"CWdiHandler::Start",
      104,
      (int)L"Error = %d",
      5);
    return 2147500037LL;
  }
  v6 = (_QWORD *)((char *)this + 40);
  v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         (char *)this + 40);
  v5 = (HANDLE *)((char *)this + 24);
  v4 = v8;
  if ( v8 < 0 )
  {
    v7 = 108;
    goto LABEL_24;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *v5 = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v7 = 114;
LABEL_23:
      LOBYTE(v8) = v4;
      goto LABEL_24;
    }
  }
  if ( !GetModuleHandleExW(0, L"wdi", (HMODULE *)this + 4) )
  {
    v12 = GetLastError();
    v4 = v12;
    if ( v12 > 0 )
      v4 = (unsigned __int16)v12 | 0x80070000;
    if ( v4 < 0 )
    {
      v7 = 117;
      goto LABEL_23;
    }
  }
  Thread = (char *)CreateThread(0, 0, CWdiHandler::WdipLaunchUserHost, this, 0, 0);
  *((_QWORD *)this + 2) = Thread;
  if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  v14 = GetLastError();
  v4 = v14;
  if ( v14 > 0 )
    v4 = (unsigned __int16)v14 | 0x80070000;
  if ( v4 < 0 )
  {
    v7 = 129;
    goto LABEL_23;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003cc0  push    rbx
0x180003cc2  push    rbp
0x180003cc3  push    rsi
0x180003cc4  push    rdi
0x180003cc5  push    r14
0x180003cc7  sub     rsp, 30h
0x180003ccb  mov     r9, rdx
0x180003cce  mov     rbx, rcx
0x180003cd1  test    rdx, rdx
0x180003cd4  jnz     short loc_180003CF5
0x180003cd6  mov     edi, 80070057h
0x180003cdb  lea     r14, [rcx+18h]
0x180003cdf  lea     rsi, [rcx+28h]
0x180003ce3  mov     r8d, 5Bh ; '['
0x180003ce9  mov     eax, 57h ; 'W'
0x180003cee  xor     ebp, ebp
0x180003cf0  jmp     loc_180003E42
0x180003cf5  mov     ebp, 1
0x180003cfa  xor     eax, eax
0x180003cfc  lock cmpxchg cs:g_HostState, ebp
0x180003d04  jz      short loc_180003D38
0x180003d06  lea     r9, aErrorD_0; "Error = %d"
0x180003d0d  mov     [rsp+58h+dwCreationFlags], 4005h; Args
0x180003d15  mov     r8d, 68h ; 'h'; int
0x180003d1b  lea     rdx, aCwdihandlerSta; "CWdiHandler::Start"
0x180003d22  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180003d29  call    WdipTraceError
0x180003d2e  mov     eax, 80004005h
0x180003d33  jmp     loc_180003EBA
0x180003d38  mov     rax, [rdx]
0x180003d3b  lea     rsi, [rcx+28h]
0x180003d3f  mov     r8, rsi
0x180003d42  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180003d49  mov     rcx, r9
0x180003d4c  mov     rax, [rax]
0x180003d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d54  lea     r14, [rbx+18h]
0x180003d58  mov     edi, eax
0x180003d5a  test    eax, eax
0x180003d5c  jns     short loc_180003D6E
0x180003d5e  mov     r8d, 6Ch ; 'l'
0x180003d64  movzx   eax, ax
0x180003d67  xor     ebp, ebp
0x180003d69  jmp     loc_180003E42
0x180003d6e  xor     r9d, r9d; lpName
0x180003d71  xor     r8d, r8d; bInitialState
0x180003d74  mov     edx, ebp; bManualReset
0x180003d76  xor     ecx, ecx; lpEventAttributes
0x180003d78  call    cs:__imp_CreateEventW
0x180003d7e  mov     [r14], rax
0x180003d81  inc     rax
0x180003d84  test    rax, 0FFFFFFFFFFFFFFFEh
0x180003d8a  jnz     short loc_180003DB2
0x180003d8c  call    cs:__imp_GetLastError
0x180003d92  mov     edi, eax
0x180003d94  test    eax, eax
0x180003d96  jle     short loc_180003DA1
0x180003d98  movzx   edi, ax
0x180003d9b  or      edi, 80070000h
0x180003da1  test    edi, edi
0x180003da3  jns     short loc_180003DB2
0x180003da5  mov     r8d, 72h ; 'r'
0x180003dab  xor     ebp, ebp
0x180003dad  jmp     loc_180003E3F
0x180003db2  lea     r8, [rbx+20h]; phModule
0x180003db6  xor     ecx, ecx; dwFlags
0x180003db8  lea     rdx, ModuleName; "wdi"
0x180003dbf  call    cs:__imp_GetModuleHandleExW
0x180003dc5  test    eax, eax
0x180003dc7  jnz     short loc_180003DEC
0x180003dc9  call    cs:__imp_GetLastError
0x180003dcf  mov     edi, eax
0x180003dd1  test    eax, eax
0x180003dd3  jle     short loc_180003DDE
0x180003dd5  movzx   edi, ax
0x180003dd8  or      edi, 80070000h
0x180003dde  test    edi, edi
0x180003de0  jns     short loc_180003DEC
0x180003de2  mov     r8d, 75h ; 'u'
0x180003de8  xor     ebp, ebp
0x180003dea  jmp     short loc_180003E3F
0x180003dec  xor     ebp, ebp
0x180003dee  lea     r8, ?WdipLaunchUserHost@CWdiHandler@@CAKPEAX@Z; lpStartAddress
0x180003df5  mov     [rsp+58h+lpThreadId], rbp; lpThreadId
0x180003dfa  mov     r9, rbx; lpParameter
0x180003dfd  xor     edx, edx; dwStackSize
0x180003dff  mov     [rsp+58h+dwCreationFlags], ebp; dwCreationFlags
0x180003e03  xor     ecx, ecx; lpThreadAttributes
0x180003e05  call    cs:__imp_CreateThread
0x180003e0b  mov     [rbx+10h], rax
0x180003e0f  lea     rcx, [rax-1]
0x180003e13  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180003e17  ja      short loc_180003E20
0x180003e19  mov     eax, ebp
0x180003e1b  jmp     loc_180003EBA
0x180003e20  call    cs:__imp_GetLastError
0x180003e26  mov     edi, eax
0x180003e28  test    eax, eax
0x180003e2a  jle     short loc_180003E35
0x180003e2c  movzx   edi, ax
0x180003e2f  or      edi, 80070000h
0x180003e35  test    edi, edi
0x180003e37  jns     short loc_180003EB8
0x180003e39  mov     r8d, 81h; int
0x180003e3f  movzx   eax, di
0x180003e42  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180003e49  mov     [rsp+58h+dwCreationFlags], eax; Args
0x180003e4d  lea     rdx, aCwdihandlerSta; "CWdiHandler::Start"
0x180003e54  lea     r9, aErrorD_0; "Error = %d"
0x180003e5b  call    WdipTraceError
0x180003e60  mov     rcx, [rbx+10h]; hObject
0x180003e64  lea     rax, [rcx-1]
0x180003e68  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003e6c  ja      short loc_180003E78
0x180003e6e  call    cs:__imp_CloseHandle
0x180003e74  mov     [rbx+10h], rbp
0x180003e78  mov     rcx, [r14]; hObject
0x180003e7b  lea     rax, [rcx-1]
0x180003e7f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003e83  ja      short loc_180003E8E
0x180003e85  call    cs:__imp_CloseHandle
0x180003e8b  mov     [r14], rbp
0x180003e8e  mov     rcx, [rbx+20h]; hLibModule
0x180003e92  test    rcx, rcx
0x180003e95  jz      short loc_180003EA1
0x180003e97  call    cs:__imp_FreeLibrary
0x180003e9d  mov     [rbx+20h], rbp
0x180003ea1  mov     rcx, [rsi]
0x180003ea4  test    rcx, rcx
0x180003ea7  jz      short loc_180003EB8
0x180003ea9  mov     rax, [rcx]
0x180003eac  mov     rax, [rax+10h]
0x180003eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb5  mov     [rsi], rbp
0x180003eb8  mov     eax, edi
0x180003eba  add     rsp, 30h
0x180003ebe  pop     r14
0x180003ec0  pop     rdi
0x180003ec1  pop     rsi
0x180003ec2  pop     rbp
0x180003ec3  pop     rbx
0x180003ec4  retn
```

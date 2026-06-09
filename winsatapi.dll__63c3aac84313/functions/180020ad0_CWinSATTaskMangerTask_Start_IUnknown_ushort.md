# CWinSATTaskMangerTask::Start(IUnknown *,ushort *)

- ea: `0x180020ad0`
- end: `0x180020d57`
- name: `?Start@CWinSATTaskMangerTask@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `647`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x18000e6ac`
- `0x18001ca88`
- `0x180020ad0`
- `0x180024d48`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180020cbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180020cbe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020bcd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020cc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020cc8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180020d20`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180020d20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ba3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ba3`

## string_xrefs

- `0x180020ae1`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020b1e`: `Cannot get the TaskHandlerStatus interface`
- `0x180020b58`: `Cannot get the ITaskVariables interface`
- `0x180020b87`: `Cannot create cancel event`
- `0x180020c3c`: `Starting  thread is running as ADMIN`
- `0x180020c61`: `Starting thread is *NOT* running as ADMIN`
- `0x180020d2f`: `Cannot create task thread`

## pseudocode

```c
__int64 __fastcall CWinSATTaskMangerTask::Start(CWinSATTaskMangerTask *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  int v5; // esi
  int TheCancelEvent; // ebx
  HANDLE *v8; // r14
  char v9; // si
  void *v10; // rdx
  HMODULE v11; // rcx
  void (__fastcall *v12)(__int64 *, __int64, __int64); // rax
  __int64 v13; // r8
  signed int LastError; // eax
  HANDLE Thread; // rax
  bool v16; // [rsp+70h] [rbp+8h] BYREF

  Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 539, "Received START signal !++!");
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_ITaskHandlerStatus,
         (char *)this + 72);
  if ( v5 < 0 )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 544, "Cannot get the TaskHandlerStatus interface");
    return (unsigned int)v5;
  }
  TheCancelEvent = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
                     a2,
                     &IID_ITaskVariables,
                     (char *)this + 80);
  if ( TheCancelEvent >= 0 )
  {
    v8 = (HANDLE *)((char *)this + 112);
    v9 = 0;
    TheCancelEvent = CreateTheCancelEvent((_QWORD *)this + 14, (__int64)this + 120);
    if ( TheCancelEvent < 0 )
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 557, "Cannot create cancel event");
      goto LABEL_7;
    }
    v16 = 0;
    if ( (unsigned int)IsUserAdmin(&v16, v10) )
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 563, "Cannot determine if running as admin...");
      v12 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 17);
      if ( !v12 )
        goto LABEL_24;
      v13 = 0;
    }
    else if ( v16 )
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 567, "Starting  thread is running as ADMIN");
      v12 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 17);
      if ( !v12 )
        goto LABEL_24;
      v13 = 1;
    }
    else
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 570, "Starting thread is *NOT* running as ADMIN");
      v12 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 17);
      if ( !v12 )
        goto LABEL_24;
      v13 = 2;
    }
    v12(qword_1800487B0, 10268, v13);
LABEL_24:
    TheCancelEvent = (*(__int64 (__fastcall **)(CWinSATTaskMangerTask *))(*(_QWORD *)this + 8LL))(this);
    if ( TheCancelEvent >= 0 )
    {
      if ( GetModuleHandleExW(4u, (LPCWSTR)CWinSATTaskMangerTask::TNThreadProcS, (HMODULE *)this + 12) )
      {
        Thread = CreateThread(0, 0, CWinSATTaskMangerTask::TNThreadProcS, this, 0, (LPDWORD)this + 26);
        *((_QWORD *)this + 11) = Thread;
        if ( Thread )
          return 0;
        v9 = 1;
        Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 605, "Cannot create task thread");
        TheCancelEvent = -2147467259;
      }
      else
      {
        LastError = GetLastError();
        TheCancelEvent = LastError;
        if ( LastError > 0 )
          TheCancelEvent = (unsigned __int16)LastError | 0x80070000;
        Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 593, "Cannot get module handle");
        v9 = 1;
        if ( TheCancelEvent >= 0 )
          return (unsigned int)TheCancelEvent;
      }
    }
LABEL_7:
    if ( *v8 )
    {
      CloseHandle(*v8);
      *v8 = 0;
    }
    if ( v9 )
      (*(void (__fastcall **)(CWinSATTaskMangerTask *))(*(_QWORD *)this + 16LL))(this);
    v11 = (HMODULE)*((_QWORD *)this + 12);
    if ( v11 )
    {
      FreeLibrary(v11);
      *((_QWORD *)this + 12) = 0;
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 9) + 32LL))(
      *((_QWORD *)this + 9),
      (unsigned int)TheCancelEvent);
    return (unsigned int)TheCancelEvent;
  }
  Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 550, "Cannot get the ITaskVariables interface");
  return (unsigned int)TheCancelEvent;
}

```

## disassembly

```asm
0x180020ad0  push    rbx
0x180020ad2  push    rsi
0x180020ad3  push    rdi
0x180020ad4  push    r12
0x180020ad6  push    r14
0x180020ad8  push    r15
0x180020ada  sub     rsp, 38h
0x180020ade  mov     rbx, rdx
0x180020ae1  lea     r12, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020ae8  mov     rdi, rcx
0x180020aeb  lea     r8, aReceivedStartS; "Received START signal !++!"
0x180020af2  mov     rcx, r12
0x180020af5  mov     edx, 21Bh
0x180020afa  call    Log_Text_F
0x180020aff  mov     rax, [rbx]
0x180020b02  lea     r8, [rdi+48h]
0x180020b06  lea     rdx, IID_ITaskHandlerStatus
0x180020b0d  mov     rcx, rbx
0x180020b10  mov     rax, [rax]
0x180020b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b18  mov     esi, eax
0x180020b1a  test    eax, eax
0x180020b1c  jns     short loc_180020B39
0x180020b1e  lea     r8, aCannotGetTheTa; "Cannot get the TaskHandlerStatus interf"...
0x180020b25  mov     edx, 220h
0x180020b2a  mov     rcx, r12
0x180020b2d  call    Log_Text_F
0x180020b32  mov     eax, esi
0x180020b34  jmp     loc_180020BEF
0x180020b39  mov     rax, [rbx]
0x180020b3c  lea     r8, [rdi+50h]
0x180020b40  lea     rdx, IID_ITaskVariables
0x180020b47  mov     rcx, rbx
0x180020b4a  mov     rax, [rax]
0x180020b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b52  mov     ebx, eax
0x180020b54  test    eax, eax
0x180020b56  jns     short loc_180020B6E
0x180020b58  lea     r8, aCannotGetTheIt; "Cannot get the ITaskVariables interface"
0x180020b5f  mov     edx, 226h
0x180020b64  mov     rcx, r12
0x180020b67  call    Log_Text_F
0x180020b6c  jmp     short loc_180020BED
0x180020b6e  lea     r14, [rdi+70h]
0x180020b72  xor     sil, sil
0x180020b75  mov     rcx, r14
0x180020b78  lea     rdx, [rdi+78h]
0x180020b7c  call    ?CreateTheCancelEvent@@YAJAEAPEAXAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; CreateTheCancelEvent(void * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180020b81  mov     ebx, eax
0x180020b83  test    eax, eax
0x180020b85  jns     short loc_180020BFD
0x180020b87  lea     r8, aCannotCreateCa; "Cannot create cancel event"
0x180020b8e  mov     edx, 22Dh
0x180020b93  mov     rcx, r12
0x180020b96  call    Log_Text_F
0x180020b9b  mov     rcx, [r14]; hObject
0x180020b9e  test    rcx, rcx
0x180020ba1  jz      short loc_180020BB0
0x180020ba3  call    cs:__imp_CloseHandle
0x180020ba9  mov     qword ptr [r14], 0
0x180020bb0  test    sil, sil
0x180020bb3  jz      short loc_180020BC4
0x180020bb5  mov     rax, [rdi]
0x180020bb8  mov     rcx, rdi
0x180020bbb  mov     rax, [rax+10h]
0x180020bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bc4  mov     rcx, [rdi+60h]; hLibModule
0x180020bc8  test    rcx, rcx
0x180020bcb  jz      short loc_180020BDB
0x180020bcd  call    cs:__imp_FreeLibrary
0x180020bd3  mov     qword ptr [rdi+60h], 0
0x180020bdb  mov     rcx, [rdi+48h]
0x180020bdf  mov     edx, ebx
0x180020be1  mov     rax, [rcx]
0x180020be4  mov     rax, [rax+20h]
0x180020be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bed  mov     eax, ebx
0x180020bef  add     rsp, 38h
0x180020bf3  pop     r15
0x180020bf5  pop     r14
0x180020bf7  pop     r12
0x180020bf9  pop     rdi
0x180020bfa  pop     rsi
0x180020bfb  pop     rbx
0x180020bfc  retn
0x180020bfd  lea     rcx, [rsp+68h+arg_0]; bool *
0x180020c02  mov     [rsp+68h+arg_0], sil
0x180020c07  call    ?IsUserAdmin@@YAKAEA_NPEAX@Z; IsUserAdmin(bool &,void *)
0x180020c0c  mov     rcx, r12
0x180020c0f  test    eax, eax
0x180020c11  jz      short loc_180020C35
0x180020c13  lea     r8, aCannotDetermin_1; "Cannot determine if running as admin..."
0x180020c1a  mov     edx, 233h
0x180020c1f  call    Log_Text_F
0x180020c24  mov     rax, [rdi+88h]
0x180020c2b  test    rax, rax
0x180020c2e  jz      short loc_180020C95
0x180020c30  xor     r8d, r8d
0x180020c33  jmp     short loc_180020C84
0x180020c35  cmp     [rsp+68h+arg_0], sil
0x180020c3a  jz      short loc_180020C61
0x180020c3c  lea     r8, aStartingThread_0; "Starting  thread is running as ADMIN"
0x180020c43  mov     edx, 237h
0x180020c48  call    Log_Text_F
0x180020c4d  mov     rax, [rdi+88h]
0x180020c54  test    rax, rax
0x180020c57  jz      short loc_180020C95
0x180020c59  mov     r8d, 1
0x180020c5f  jmp     short loc_180020C84
0x180020c61  lea     r8, aStartingThread; "Starting thread is *NOT* running as ADM"...
0x180020c68  mov     edx, 23Ah
0x180020c6d  call    Log_Text_F
0x180020c72  mov     rax, [rdi+88h]
0x180020c79  test    rax, rax
0x180020c7c  jz      short loc_180020C95
0x180020c7e  mov     r8d, 2
0x180020c84  mov     edx, 281Ch
0x180020c89  lea     rcx, qword_1800487B0
0x180020c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c95  mov     rax, [rdi]
0x180020c98  mov     rcx, rdi
0x180020c9b  mov     rax, [rax+8]
0x180020c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ca4  mov     ebx, eax
0x180020ca6  test    eax, eax
0x180020ca8  js      loc_180020B9B
0x180020cae  lea     r8, [rdi+60h]; phModule
0x180020cb2  mov     ecx, 4; dwFlags
0x180020cb7  lea     rdx, ?TNThreadProcS@CWinSATTaskMangerTask@@CAKPEAX@Z; lpModuleName
0x180020cbe  call    cs:__imp_GetModuleHandleExW
0x180020cc4  test    eax, eax
0x180020cc6  jnz     short loc_180020D01
0x180020cc8  call    cs:__imp_GetLastError
0x180020cce  mov     ebx, eax
0x180020cd0  test    eax, eax
0x180020cd2  jle     short loc_180020CDD
0x180020cd4  movzx   ebx, ax
0x180020cd7  or      ebx, 80070000h
0x180020cdd  lea     r8, aCannotGetModul; "Cannot get module handle"
0x180020ce4  mov     edx, 251h
0x180020ce9  mov     rcx, r12
0x180020cec  call    Log_Text_F
0x180020cf1  mov     sil, 1
0x180020cf4  test    ebx, ebx
0x180020cf6  jns     loc_180020BED
0x180020cfc  jmp     loc_180020B9B
0x180020d01  lea     rax, [rdi+68h]
0x180020d05  mov     r9, rdi; lpParameter
0x180020d08  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180020d0d  lea     r8, ?TNThreadProcS@CWinSATTaskMangerTask@@CAKPEAX@Z; lpStartAddress
0x180020d14  xor     edx, edx; dwStackSize
0x180020d16  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x180020d1e  xor     ecx, ecx; lpThreadAttributes
0x180020d20  call    cs:__imp_CreateThread
0x180020d26  mov     [rdi+58h], rax
0x180020d2a  test    rax, rax
0x180020d2d  jnz     short loc_180020D50
0x180020d2f  lea     r8, aCannotCreateTa; "Cannot create task thread"
0x180020d36  mov     edx, 25Dh
0x180020d3b  mov     rcx, r12
0x180020d3e  mov     sil, 1
0x180020d41  call    Log_Text_F
0x180020d46  mov     ebx, 80004005h
0x180020d4b  jmp     loc_180020B9B
0x180020d50  xor     ebx, ebx
0x180020d52  jmp     loc_180020BED
```

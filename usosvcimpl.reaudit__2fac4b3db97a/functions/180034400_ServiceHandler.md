# ServiceHandler

- ea: `0x180034400`
- end: `0x180034581`
- name: `ServiceHandler`
- size: `385`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18001b064`
- `0x18002dedc`
- `0x18003436c`
- `0x180034400`
- `0x180035258`
- `0x1800353e0`
- `0x18006ea28`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180034502`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180034502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003453a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003453a`

## string_xrefs

- `0x18003451c`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x1800344b7`: `UsoSvc setting service state to: SERVICE_STOP_PENDING`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD v4; // ecx
  DWORD v5; // ecx
  __int64 **System; // rax
  __int64 *v8; // rcx
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  char *Thread; // rbx
  const char *v12; // r9
  const wchar_t *v13; // rax
  const wchar_t *v14; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  int v17; // [rsp+50h] [rbp+10h] BYREF

  v4 = dwControl - 1;
  if ( !v4 )
  {
    v13 = L"SCM Stop";
    v15 = 8;
    goto LABEL_14;
  }
  v5 = v4 - 4;
  if ( !v5 )
  {
    v13 = L"SCM Shutdown";
    v15 = 12;
LABEL_14:
    v14 = v13;
    SystemInterface::Log<>(&v14);
    InitiateStop();
    return 0;
  }
  if ( v5 != 10 )
    return 120;
  System = (__int64 **)SystemInterface::Service::GetSystem(&v14);
  v8 = *System;
  v9 = **System;
  v17 = 0;
  (*(void (__fastcall **)(__int64 *, int *))(v9 + 152))(v8, &v17);
  v10 = (volatile signed __int32 *)v15;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  SvcAddRef();
  v14 = L"SCM Preshutdown";
  v15 = 15;
  SystemInterface::Log<>(&v14);
  v14 = L"UsoSvc setting service state to: SERVICE_STOP_PENDING";
  v15 = 53;
  SystemInterface::Log<>(&v14);
  ServiceHelpers::UpdateServiceStatus(3u, 0, 0x1D4C0u);
  Thread = (char *)CreateThread(0, 0, HandlePreShutdown, 0, 0, 0);
  if ( ((unsigned __int64)(Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
    || (wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x348,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
          v12),
        (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL) )
  {
    CloseHandle(Thread);
  }
  return 0;
}

```

## disassembly

```asm
0x180034400  mov     [rsp-8+arg_8], rbx
0x180034405  push    rbp
0x180034406  mov     rbp, rsp
0x180034409  sub     rsp, 40h
0x18003440d  sub     ecx, 1
0x180034410  jz      loc_180034553
0x180034416  sub     ecx, 4
0x180034419  jz      loc_180034542
0x18003441f  cmp     ecx, 0Ah
0x180034422  jz      short loc_18003442E
0x180034424  mov     eax, 78h ; 'x'
0x180034429  jmp     loc_180034576
0x18003442e  lea     rcx, [rbp+var_10]
0x180034432  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180034437  nop
0x180034438  mov     rcx, [rax]
0x18003443b  mov     rax, [rcx]
0x18003443e  mov     [rbp+arg_0], 0
0x180034445  lea     rdx, [rbp+arg_0]
0x180034449  mov     rax, [rax+98h]
0x180034450  call    _guard_dispatch_icall
0x180034455  nop
0x180034456  mov     rbx, [rbp+var_8]
0x18003445a  test    rbx, rbx
0x18003445d  jz      short loc_180034496
0x18003445f  or      eax, 0FFFFFFFFh
0x180034462  lock xadd [rbx+8], eax
0x180034467  cmp     eax, 1
0x18003446a  jnz     short loc_180034496
0x18003446c  mov     rax, [rbx]
0x18003446f  mov     rcx, rbx
0x180034472  mov     rax, [rax]
0x180034475  call    _guard_dispatch_icall
0x18003447a  or      eax, 0FFFFFFFFh
0x18003447d  lock xadd [rbx+0Ch], eax
0x180034482  cmp     eax, 1
0x180034485  jnz     short loc_180034496
0x180034487  mov     rax, [rbx]
0x18003448a  mov     rcx, rbx
0x18003448d  mov     rax, [rax+8]
0x180034491  call    _guard_dispatch_icall
0x180034496  call    ?SvcAddRef@@YAXXZ; SvcAddRef(void)
0x18003449b  lea     rax, aScmPreshutdown; "SCM Preshutdown"
0x1800344a2  mov     [rbp+var_10], rax
0x1800344a6  mov     [rbp+var_8], 0Fh
0x1800344ae  lea     rcx, [rbp+var_10]
0x1800344b2  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800344b7  lea     rax, aUsosvcSettingS_1; "UsoSvc setting service state to: SERVIC"...
0x1800344be  mov     [rbp+var_10], rax
0x1800344c2  mov     [rbp+var_8], 35h ; '5'
0x1800344ca  lea     rcx, [rbp+var_10]
0x1800344ce  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800344d3  xor     edx, edx; unsigned int
0x1800344d5  lea     ecx, [rdx+3]; unsigned int
0x1800344d8  mov     r8d, 1D4C0h; unsigned int
0x1800344de  call    ?UpdateServiceStatus@ServiceHelpers@@SAJKKK@Z; ServiceHelpers::UpdateServiceStatus(ulong,ulong,ulong)
0x1800344e3  mov     [rsp+40h+lpThreadId], 0; lpThreadId
0x1800344ec  mov     [rsp+40h+dwCreationFlags], 0; dwCreationFlags
0x1800344f4  xor     r9d, r9d; lpParameter
0x1800344f7  lea     r8, ?HandlePreShutdown@@YAKPEAX@Z; lpStartAddress
0x1800344fe  xor     edx, edx; dwStackSize
0x180034500  xor     ecx, ecx; lpThreadAttributes
0x180034502  call    cs:__imp_CreateThread
0x180034508  mov     rbx, rax
0x18003450b  mov     rcx, [rbp+8]; this
0x18003450f  lea     rdx, [rax+1]
0x180034513  test    rdx, 0FFFFFFFFFFFFFFFEh
0x18003451a  jnz     short loc_180034537
0x18003451c  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180034523  mov     edx, 348h; void *
0x180034528  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003452d  lea     rcx, [rbx-1]
0x180034531  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180034535  ja      short loc_180034574
0x180034537  mov     rcx, rbx; hObject
0x18003453a  call    cs:__imp_CloseHandle
0x180034540  jmp     short loc_180034574
0x180034542  lea     rax, aScmShutdown; "SCM Shutdown"
0x180034549  mov     [rbp+var_8], 0Ch
0x180034551  jmp     short loc_180034562
0x180034553  lea     rax, aScmStop; "SCM Stop"
0x18003455a  mov     [rbp+var_8], 8
0x180034562  mov     [rbp+var_10], rax
0x180034566  lea     rcx, [rbp+var_10]
0x18003456a  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x18003456f  call    ?InitiateStop@@YAXXZ; InitiateStop(void)
0x180034574  xor     eax, eax
0x180034576  mov     rbx, [rsp+40h+arg_8]
0x18003457b  add     rsp, 40h
0x18003457f  pop     rbp
0x180034580  retn
```

# WUServiceWatcher::StartWatcher(WUServiceAPIMethod)

- ea: `0x1800854a8`
- end: `0x18008563b`
- name: `?StartWatcher@WUServiceWatcher@@QEAAJW4WUServiceAPIMethod@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180042740`
- `0x180042c7c`
- `0x18004452c`
- `0x180048dd0`
- `0x180049860`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x1800854a8`
- `0x18008662c`
- `0x180090bc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180085618`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180085618`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800855d7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800855d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085580`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800855e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085580`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800855e9`

## string_xrefs

- `0x1800854cd`: `C:\__w\1\s\src\Client\lib\util\WUServiceWatcher.cpp`
- `0x180085559`: `C:\__w\1\s\src\Client\lib\util\WUServiceWatcher.cpp`
- `0x1800855a0`: `C:\__w\1\s\src\Client\lib\util\WUServiceWatcher.cpp`
- `0x180085602`: `C:\__w\1\s\src\Client\lib\util\WUServiceWatcher.cpp`
- `0x180085506`: `WUServiceWatcher::StartWatcher`

## pseudocode

```c
__int64 __fastcall WUServiceWatcher::StartWatcher(__int64 a1, int a2)
{
  __int64 v4; // rdx
  void *v6; // rcx
  int SingleTriggerEvent; // eax
  unsigned int v8; // edi
  HANDLE *v9; // rdi
  void *v10; // rcx
  int v11; // eax
  unsigned int v12; // esi
  HANDLE Thread; // rax
  const char *v14; // r9
  void *v15; // rcx
  HANDLE v16; // rsi
  __int64 v17; // rdx
  int dwCreationFlags; // [rsp+20h] [rbp-18h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !*(_QWORD *)(a1 + 8) )
  {
    v4 = 111;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUServiceWatcher.cpp",
      (const char *)0x80240004LL,
      dwCreationFlags);
    return 2149842948LL;
  }
  if ( !*(_QWORD *)(a1 + 48) )
  {
    v4 = 112;
    goto LABEL_3;
  }
  if ( !*(_QWORD *)(a1 + 40) )
  {
    v4 = 113;
    goto LABEL_3;
  }
  WUTrace(0, 0, 32, 5, 0, L"WUServiceWatcher::StartWatcher");
  *(_DWORD *)(a1 + 56) = a2;
  v6 = *(void **)(a1 + 24);
  if ( v6 )
  {
    CloseHandle(v6);
    *(_QWORD *)(a1 + 24) = 0;
  }
  SingleTriggerEvent = CreateSingleTriggerEvent((void **)(a1 + 24));
  v8 = SingleTriggerEvent;
  if ( SingleTriggerEvent < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUServiceWatcher.cpp",
      (const char *)(unsigned int)SingleTriggerEvent,
      dwCreationFlagsa);
    return v8;
  }
  v9 = (HANDLE *)(a1 + 32);
  v10 = *(void **)(a1 + 32);
  if ( v10 )
  {
    CloseHandle(v10);
    *v9 = 0;
  }
  v11 = CreateSingleTriggerEvent((void **)(a1 + 32));
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUServiceWatcher.cpp",
      (const char *)(unsigned int)v11,
      dwCreationFlagsa);
    return v12;
  }
  Thread = CreateThread(0, 0, WUServiceWatcher::StaticThreadStart, (LPVOID)a1, 0, 0);
  v15 = *(void **)(a1 + 16);
  v16 = Thread;
  if ( v15 )
    CloseHandle(v15);
  *(_QWORD *)(a1 + 16) = v16;
  if ( !v16 )
  {
    v17 = 130;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v17,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUServiceWatcher.cpp",
             v14);
  }
  if ( WaitForSingleObject(*v9, 0xEA60u) )
  {
    v17 = 134;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v17,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUServiceWatcher.cpp",
             v14);
  }
  return 0;
}

```

## disassembly

```asm
0x1800854a8  mov     [rsp+arg_0], rbx
0x1800854ad  mov     [rsp+arg_8], rsi
0x1800854b2  push    rdi
0x1800854b3  sub     rsp, 30h
0x1800854b7  cmp     qword ptr [rcx+8], 0
0x1800854bc  mov     edi, edx
0x1800854be  mov     rbx, rcx
0x1800854c1  jnz     short loc_1800854E8
0x1800854c3  mov     edx, 6Fh ; 'o'; void *
0x1800854c8  mov     rcx, [rsp+38h]; this
0x1800854cd  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800854d4  mov     ebx, 80240004h
0x1800854d9  mov     r9d, ebx; char *
0x1800854dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800854e1  mov     eax, ebx
0x1800854e3  jmp     loc_18008562B
0x1800854e8  cmp     qword ptr [rcx+30h], 0
0x1800854ed  jnz     short loc_1800854F6
0x1800854ef  mov     edx, 70h ; 'p'
0x1800854f4  jmp     short loc_1800854C8
0x1800854f6  cmp     qword ptr [rcx+28h], 0
0x1800854fb  jnz     short loc_180085504
0x1800854fd  mov     edx, 71h ; 'q'
0x180085502  jmp     short loc_1800854C8
0x180085504  xor     edx, edx
0x180085506  lea     rax, aWuservicewatch_2; "WUServiceWatcher::StartWatcher"
0x18008550d  mov     [rsp+38h+lpThreadId], rax
0x180085512  xor     ecx, ecx
0x180085514  mov     qword ptr [rsp+38h+dwCreationFlags], 0; int
0x18008551d  lea     r9d, [rdx+5]
0x180085521  lea     r8d, [rdx+20h]
0x180085525  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18008552a  mov     [rbx+38h], edi
0x18008552d  lea     rdi, [rbx+18h]
0x180085531  mov     rcx, [rdi]; hObject
0x180085534  test    rcx, rcx
0x180085537  jz      short loc_180085546
0x180085539  call    cs:__imp_CloseHandle
0x18008553f  mov     qword ptr [rdi], 0
0x180085546  mov     rcx, rdi; void **
0x180085549  call    ?CreateSingleTriggerEvent@@YAJPEAPEAX@Z; CreateSingleTriggerEvent(void * *)
0x18008554e  mov     edi, eax
0x180085550  test    eax, eax
0x180085552  jns     short loc_180085574
0x180085554  mov     rcx, [rsp+38h]; this
0x180085559  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180085560  mov     r9d, eax; char *
0x180085563  mov     edx, 77h ; 'w'; void *
0x180085568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008556d  mov     eax, edi
0x18008556f  jmp     loc_18008562B
0x180085574  lea     rdi, [rbx+20h]
0x180085578  mov     rcx, [rdi]; hObject
0x18008557b  test    rcx, rcx
0x18008557e  jz      short loc_18008558D
0x180085580  call    cs:__imp_CloseHandle
0x180085586  mov     qword ptr [rdi], 0
0x18008558d  mov     rcx, rdi; void **
0x180085590  call    ?CreateSingleTriggerEvent@@YAJPEAPEAX@Z; CreateSingleTriggerEvent(void * *)
0x180085595  mov     esi, eax
0x180085597  test    eax, eax
0x180085599  jns     short loc_1800855B8
0x18008559b  mov     rcx, [rsp+38h]; this
0x1800855a0  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800855a7  mov     r9d, eax; char *
0x1800855aa  mov     edx, 78h ; 'x'; void *
0x1800855af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800855b4  mov     eax, esi
0x1800855b6  jmp     short loc_18008562B
0x1800855b8  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800855c1  lea     r8, ?StaticThreadStart@WUServiceWatcher@@CAKPEAX@Z; lpStartAddress
0x1800855c8  mov     r9, rbx; lpParameter
0x1800855cb  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800855d3  xor     edx, edx; dwStackSize
0x1800855d5  xor     ecx, ecx; lpThreadAttributes
0x1800855d7  call    cs:__imp_CreateThread
0x1800855dd  mov     rcx, [rbx+10h]; hObject
0x1800855e1  mov     rsi, rax
0x1800855e4  test    rcx, rcx
0x1800855e7  jz      short loc_1800855EF
0x1800855e9  call    cs:__imp_CloseHandle
0x1800855ef  mov     [rbx+10h], rsi
0x1800855f3  test    rsi, rsi
0x1800855f6  jnz     short loc_180085610
0x1800855f8  mov     edx, 82h; void *
0x1800855fd  mov     rcx, [rsp+38h]; this
0x180085602  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180085609  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008560e  jmp     short loc_18008562B
0x180085610  mov     rcx, [rdi]; hHandle
0x180085613  mov     edx, 0EA60h; dwMilliseconds
0x180085618  call    cs:__imp_WaitForSingleObject
0x18008561e  test    eax, eax
0x180085620  jz      short loc_180085629
0x180085622  mov     edx, 86h
0x180085627  jmp     short loc_1800855FD
0x180085629  xor     eax, eax
0x18008562b  mov     rbx, [rsp+38h+arg_0]
0x180085630  mov     rsi, [rsp+38h+arg_8]
0x180085635  add     rsp, 30h
0x180085639  pop     rdi
0x18008563a  retn
```

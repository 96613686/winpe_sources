# FederatedDownloadJob::StartFederationWorker(void)

- ea: `0x180013794`
- end: `0x180013907`
- name: `?StartFederationWorker@FederatedDownloadJob@@AEAAJXZ`
- size: `371`
- prototype: `__int64 __fastcall(FederatedDownloadJob *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012e54`

## callees

- `0x180006ac4`
- `0x180013794`
- `0x18008662c`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180013884`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180013884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800138ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800138ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800137b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800137ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013830`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013899`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800137b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800137ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013830`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013899`

## string_xrefs

- `0x1800137da`: `C:\__w\1\s\src\Client\comapi\FederatedDownloadJob.cpp`
- `0x1800138dd`: `C:\__w\1\s\src\Client\comapi\FederatedDownloadJob.cpp`

## pseudocode

```c
__int64 __fastcall FederatedDownloadJob::StartFederationWorker(FederatedDownloadJob *this)
{
  void **v1; // rdi
  void *v3; // rcx
  int SingleTriggerEvent; // edi
  __int64 v5; // rdx
  void *v7; // rcx
  void *v8; // rcx
  char *v9; // rsi
  HANDLE Thread; // rax
  void *v11; // rcx
  HANDLE v12; // rdi
  signed int LastError; // eax
  char *v14; // rcx
  unsigned int v15; // ebx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = (void **)((char *)this + 808);
  v3 = (void *)*((_QWORD *)this + 101);
  if ( v3 )
  {
    CloseHandle(v3);
    *v1 = 0;
  }
  SingleTriggerEvent = CreateSingleTriggerEvent(v1);
  if ( SingleTriggerEvent < 0 )
  {
    v5 = 251;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedDownloadJob.cpp",
      (const char *)(unsigned int)SingleTriggerEvent,
      dwCreationFlags);
    return (unsigned int)SingleTriggerEvent;
  }
  v7 = (void *)*((_QWORD *)this + 100);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 100) = 0;
  }
  SingleTriggerEvent = CreateSingleTriggerEvent((void **)this + 100);
  if ( SingleTriggerEvent < 0 )
  {
    v5 = 252;
    goto LABEL_5;
  }
  v8 = (void *)*((_QWORD *)this + 103);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 103) = 0;
  }
  SingleTriggerEvent = CreateSingleTriggerEvent((void **)this + 103);
  if ( SingleTriggerEvent < 0 )
  {
    v5 = 253;
    goto LABEL_5;
  }
  v9 = (char *)this + 8;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
  Thread = CreateThread(0, 0, FederatedDownloadJob::StaticFederationWorker, this, 0, 0);
  v11 = (void *)*((_QWORD *)this + 102);
  v12 = Thread;
  if ( v11 )
    CloseHandle(v11);
  *((_QWORD *)this + 102) = v12;
  if ( v12 )
    return 0;
  LastError = GetLastError();
  v14 = (char *)this + 8;
  v15 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v15 = LastError;
  if ( (v15 & 0x80000000) == 0 )
    v15 = -2147418113;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v14);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x111,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedDownloadJob.cpp",
    (const char *)v15,
    dwCreationFlagsa);
  return v15;
}

```

## disassembly

```asm
0x180013794  mov     [rsp+arg_0], rbx
0x180013799  mov     [rsp+arg_8], rsi
0x18001379e  push    rdi
0x18001379f  sub     rsp, 30h
0x1800137a3  lea     rdi, [rcx+328h]
0x1800137aa  mov     rbx, rcx
0x1800137ad  mov     rcx, [rdi]; hObject
0x1800137b0  test    rcx, rcx
0x1800137b3  jz      short loc_1800137C2
0x1800137b5  call    cs:__imp_CloseHandle
0x1800137bb  mov     qword ptr [rdi], 0
0x1800137c2  mov     rcx, rdi; void **
0x1800137c5  call    ?CreateSingleTriggerEvent@@YAJPEAPEAX@Z; CreateSingleTriggerEvent(void * *)
0x1800137ca  mov     edi, eax
0x1800137cc  test    eax, eax
0x1800137ce  jns     short loc_1800137F0
0x1800137d0  mov     edx, 0FBh; void *
0x1800137d5  mov     rcx, [rsp+38h]; this
0x1800137da  lea     r8, aCW1SSrcClientC_38; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x1800137e1  mov     r9d, edi; char *
0x1800137e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800137e9  mov     eax, edi
0x1800137eb  jmp     loc_1800138F7
0x1800137f0  lea     rdi, [rbx+320h]
0x1800137f7  mov     rcx, [rdi]; hObject
0x1800137fa  test    rcx, rcx
0x1800137fd  jz      short loc_18001380C
0x1800137ff  call    cs:__imp_CloseHandle
0x180013805  mov     qword ptr [rdi], 0
0x18001380c  mov     rcx, rdi; void **
0x18001380f  call    ?CreateSingleTriggerEvent@@YAJPEAPEAX@Z; CreateSingleTriggerEvent(void * *)
0x180013814  mov     edi, eax
0x180013816  test    eax, eax
0x180013818  jns     short loc_180013821
0x18001381a  mov     edx, 0FCh
0x18001381f  jmp     short loc_1800137D5
0x180013821  lea     rdi, [rbx+338h]
0x180013828  mov     rcx, [rdi]; hObject
0x18001382b  test    rcx, rcx
0x18001382e  jz      short loc_18001383D
0x180013830  call    cs:__imp_CloseHandle
0x180013836  mov     qword ptr [rdi], 0
0x18001383d  mov     rcx, rdi; void **
0x180013840  call    ?CreateSingleTriggerEvent@@YAJPEAPEAX@Z; CreateSingleTriggerEvent(void * *)
0x180013845  mov     edi, eax
0x180013847  test    eax, eax
0x180013849  jns     short loc_180013852
0x18001384b  mov     edx, 0FDh
0x180013850  jmp     short loc_1800137D5
0x180013852  lea     rsi, [rbx+8]
0x180013856  mov     rax, [rsi]
0x180013859  mov     rcx, rsi
0x18001385c  mov     rax, [rax+8]
0x180013860  call    _guard_dispatch_icall
0x180013865  mov     r9, rbx; lpParameter
0x180013868  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180013871  lea     r8, ?StaticFederationWorker@FederatedDownloadJob@@CAKPEAX@Z; lpStartAddress
0x180013878  mov     [rsp+38h+dwCreationFlags], 0; int
0x180013880  xor     edx, edx; dwStackSize
0x180013882  xor     ecx, ecx; lpThreadAttributes
0x180013884  call    cs:__imp_CreateThread
0x18001388a  mov     rcx, [rbx+330h]; hObject
0x180013891  mov     rdi, rax
0x180013894  test    rcx, rcx
0x180013897  jz      short loc_18001389F
0x180013899  call    cs:__imp_CloseHandle
0x18001389f  mov     [rbx+330h], rdi
0x1800138a6  test    rdi, rdi
0x1800138a9  jnz     short loc_1800138F5
0x1800138ab  call    cs:__imp_GetLastError
0x1800138b1  mov     rdx, [rsi]
0x1800138b4  mov     rcx, rsi
0x1800138b7  movzx   ebx, ax
0x1800138ba  or      ebx, 80070000h
0x1800138c0  test    eax, eax
0x1800138c2  cmovle  ebx, eax
0x1800138c5  mov     eax, 8000FFFFh
0x1800138ca  test    ebx, ebx
0x1800138cc  cmovns  ebx, eax
0x1800138cf  mov     rax, [rdx+10h]
0x1800138d3  call    _guard_dispatch_icall
0x1800138d8  mov     rcx, [rsp+38h]; this
0x1800138dd  lea     r8, aCW1SSrcClientC_38; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x1800138e4  mov     r9d, ebx; char *
0x1800138e7  mov     edx, 111h; void *
0x1800138ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800138f1  mov     eax, ebx
0x1800138f3  jmp     short loc_1800138F7
0x1800138f5  xor     eax, eax
0x1800138f7  mov     rbx, [rsp+38h+arg_0]
0x1800138fc  mov     rsi, [rsp+38h+arg_8]
0x180013901  add     rsp, 30h
0x180013905  pop     rdi
0x180013906  retn
```

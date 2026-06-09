# FederatedInstallJob::StartFederationWorker(void)

- ea: `0x180017b60`
- end: `0x180017c85`
- name: `?StartFederationWorker@FederatedInstallJob@@AEAAJXZ`
- size: `293`
- prototype: `__int64 __fastcall(FederatedInstallJob *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017208`

## callees

- `0x180006ac4`
- `0x180017b60`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017b7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017b7e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180017c15`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180017c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017c2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017c2a`

## string_xrefs

- `0x180017bcd`: `C:\__w\1\s\src\Client\comapi\FederatedInstallJob.cpp`

## pseudocode

```c
__int64 __fastcall FederatedInstallJob::StartFederationWorker(FederatedInstallJob *this)
{
  HANDLE EventW; // rax
  void *v3; // rcx
  HANDLE v4; // rdi
  signed int LastError; // eax
  __int64 v6; // rdx
  signed int v7; // ebx
  char *v9; // rsi
  HANDLE Thread; // rax
  void *v11; // rcx
  HANDLE v12; // rdi
  signed int v13; // eax
  char *v14; // rcx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  EventW = CreateEventW(0, 1, 0, 0);
  v3 = (void *)*((_QWORD *)this + 100);
  v4 = EventW;
  if ( v3 )
    CloseHandle(v3);
  *((_QWORD *)this + 100) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v6 = 243;
    v7 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v7 = LastError;
    if ( v7 >= 0 )
      v7 = -2147418113;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedInstallJob.cpp",
      (const char *)(unsigned int)v7,
      dwCreationFlags);
    return (unsigned int)v7;
  }
  v9 = (char *)this + 8;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
  Thread = CreateThread(0, 0, FederatedInstallJob::StaticFederationWorker, this, 0, 0);
  v11 = (void *)*((_QWORD *)this + 101);
  v12 = Thread;
  if ( v11 )
    CloseHandle(v11);
  *((_QWORD *)this + 101) = v12;
  if ( !v12 )
  {
    v13 = GetLastError();
    v14 = (char *)this + 8;
    v7 = (unsigned __int16)v13 | 0x80070000;
    if ( v13 <= 0 )
      v7 = v13;
    if ( v7 >= 0 )
      v7 = -2147418113;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v14);
    v6 = 262;
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x180017b60  mov     [rsp+arg_0], rbx
0x180017b65  mov     [rsp+arg_8], rsi
0x180017b6a  push    rdi
0x180017b6b  sub     rsp, 30h
0x180017b6f  xor     r9d, r9d; lpName
0x180017b72  mov     rbx, rcx
0x180017b75  xor     r8d, r8d; bInitialState
0x180017b78  xor     ecx, ecx; lpEventAttributes
0x180017b7a  lea     edx, [r9+1]; bManualReset
0x180017b7e  call    cs:__imp_CreateEventW
0x180017b84  mov     rcx, [rbx+320h]; hObject
0x180017b8b  mov     rdi, rax
0x180017b8e  test    rcx, rcx
0x180017b91  jz      short loc_180017B99
0x180017b93  call    cs:__imp_CloseHandle
0x180017b99  mov     [rbx+320h], rdi
0x180017ba0  test    rdi, rdi
0x180017ba3  jnz     short loc_180017BE3
0x180017ba5  call    cs:__imp_GetLastError
0x180017bab  movzx   ebx, ax
0x180017bae  mov     edx, 0F3h; void *
0x180017bb3  or      ebx, 80070000h
0x180017bb9  test    eax, eax
0x180017bbb  cmovle  ebx, eax
0x180017bbe  mov     eax, 8000FFFFh
0x180017bc3  test    ebx, ebx
0x180017bc5  cmovns  ebx, eax
0x180017bc8  mov     rcx, [rsp+38h]; this
0x180017bcd  lea     r8, aCW1SSrcClientC_37; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x180017bd4  mov     r9d, ebx; char *
0x180017bd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017bdc  mov     eax, ebx
0x180017bde  jmp     loc_180017C75
0x180017be3  lea     rsi, [rbx+8]
0x180017be7  mov     rax, [rsi]
0x180017bea  mov     rcx, rsi
0x180017bed  mov     rax, [rax+8]
0x180017bf1  call    _guard_dispatch_icall
0x180017bf6  mov     r9, rbx; lpParameter
0x180017bf9  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180017c02  lea     r8, ?StaticFederationWorker@FederatedInstallJob@@CAKPEAX@Z; lpStartAddress
0x180017c09  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180017c11  xor     edx, edx; dwStackSize
0x180017c13  xor     ecx, ecx; lpThreadAttributes
0x180017c15  call    cs:__imp_CreateThread
0x180017c1b  mov     rcx, [rbx+328h]; hObject
0x180017c22  mov     rdi, rax
0x180017c25  test    rcx, rcx
0x180017c28  jz      short loc_180017C30
0x180017c2a  call    cs:__imp_CloseHandle
0x180017c30  mov     [rbx+328h], rdi
0x180017c37  test    rdi, rdi
0x180017c3a  jnz     short loc_180017C73
0x180017c3c  call    cs:__imp_GetLastError
0x180017c42  mov     rdx, [rsi]
0x180017c45  mov     rcx, rsi
0x180017c48  movzx   ebx, ax
0x180017c4b  or      ebx, 80070000h
0x180017c51  test    eax, eax
0x180017c53  cmovle  ebx, eax
0x180017c56  mov     eax, 8000FFFFh
0x180017c5b  test    ebx, ebx
0x180017c5d  cmovns  ebx, eax
0x180017c60  mov     rax, [rdx+10h]
0x180017c64  call    _guard_dispatch_icall
0x180017c69  mov     edx, 106h
0x180017c6e  jmp     loc_180017BC8
0x180017c73  xor     eax, eax
0x180017c75  mov     rbx, [rsp+38h+arg_0]
0x180017c7a  mov     rsi, [rsp+38h+arg_8]
0x180017c7f  add     rsp, 30h
0x180017c83  pop     rdi
0x180017c84  retn
```

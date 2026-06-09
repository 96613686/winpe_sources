# GetGlobalLockForUploadingReports

- ea: `0x140007554`
- end: `0x14000761b`
- name: `GetGlobalLockForUploadingReports`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005f98`

## callees

- `0x140007554`
- `0x140008c40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400075a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400075a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007585`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007585`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007608`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000756f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000756f`

## pseudocode

```c
__int64 __fastcall GetGlobalLockForUploadingReports(void **a1)
{
  HANDLE MutexW; // rax
  void *v3; // rcx
  signed int LastError; // eax
  signed int v6; // ebx
  void *v7; // rcx
  wil::details *v8; // [rsp+20h] [rbp-18h]
  const char *v9; // [rsp+30h] [rbp-8h]
  wil::details::in1diag4 *retaddr; // [rsp+38h] [rbp+0h]

  MutexW = CreateMutexW(0, 1, L"Global\\WerMgrUploadingLock");
  v3 = *a1;
  *a1 = MutexW;
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  if ( *a1 != (void *)-1LL && (char *)*a1 + 1 != (void *)1 && GetLastError() != 183 )
    return 0;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
    v6 = -2147467259;
  LODWORD(v8) = v6;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x3AE,
    (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
    "GetGlobalLockForUploadingReports",
    v8,
    (int)"Could not get lock",
    v9);
  v7 = *a1;
  *a1 = 0;
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140007554  mov     [rsp+arg_0], rbx
0x140007559  push    rdi; char *
0x14000755a  sub     rsp, 30h
0x14000755e  mov     rdi, rcx
0x140007561  lea     r8, Name; "Global\\WerMgrUploadingLock"
0x140007568  xor     ecx, ecx; lpMutexAttributes
0x14000756a  mov     edx, 1; bInitialOwner
0x14000756f  call    cs:__imp_CreateMutexW
0x140007575  mov     rcx, [rdi]; hObject
0x140007578  mov     [rdi], rax
0x14000757b  lea     rax, [rcx+1]
0x14000757f  cmp     rax, 1
0x140007583  jbe     short loc_14000758B
0x140007585  call    cs:__imp_CloseHandle
0x14000758b  mov     rax, [rdi]
0x14000758e  inc     rax
0x140007591  cmp     rax, 1
0x140007595  jbe     short loc_1400075A8
0x140007597  call    cs:__imp_GetLastError
0x14000759d  cmp     eax, 0B7h
0x1400075a2  jz      short loc_1400075A8
0x1400075a4  xor     eax, eax
0x1400075a6  jmp     short loc_140007610
0x1400075a8  call    cs:__imp_GetLastError
0x1400075ae  mov     ebx, eax
0x1400075b0  test    eax, eax
0x1400075b2  jle     short loc_1400075BD
0x1400075b4  movzx   ebx, ax
0x1400075b7  or      ebx, 80070000h
0x1400075bd  mov     rcx, [rsp+38h]; this
0x1400075c2  lea     r9, aGetgloballockf; "GetGlobalLockForUploadingReports"
0x1400075c9  mov     eax, 80004005h
0x1400075ce  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x1400075d5  test    ebx, ebx
0x1400075d7  mov     edx, 3AEh; void *
0x1400075dc  cmovns  ebx, eax
0x1400075df  lea     rax, aCouldNotGetLoc; "Could not get lock"
0x1400075e6  mov     qword ptr [rsp+38h+var_10], rax; int
0x1400075eb  mov     dword ptr [rsp+38h+var_18], ebx; wil::details *
0x1400075ef  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400075f4  mov     rcx, [rdi]; hObject
0x1400075f7  mov     qword ptr [rdi], 0
0x1400075fe  lea     rdx, [rcx+1]
0x140007602  cmp     rdx, 1
0x140007606  jbe     short loc_14000760E
0x140007608  call    cs:__imp_CloseHandle
0x14000760e  mov     eax, ebx
0x140007610  mov     rbx, [rsp+38h+arg_0]
0x140007615  add     rsp, 30h
0x140007619  pop     rdi
0x14000761a  retn
```

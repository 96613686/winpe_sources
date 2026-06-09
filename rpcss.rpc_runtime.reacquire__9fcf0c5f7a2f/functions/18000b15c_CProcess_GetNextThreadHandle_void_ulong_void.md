# CProcess::GetNextThreadHandle(void *,ulong,void * *)

- ea: `0x18000b15c`
- end: `0x18000b38f`
- name: `?GetNextThreadHandle@CProcess@@QEBAJPEAXKPEAPEAX@Z`
- size: `563`
- prototype: `__int64 __fastcall(CProcess *__hidden this, void *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000afb8`
- `0x18000b618`

## callees

- `0x18000b15c`
- `0x18000b398`
- `0x1800210f8`
- `0x180024590`
- `0x18002f5a0`
- `0x18002f670`
- `0x18006016c`
- `0x180093f20`

## import_xrefs

- `ntdll!NtGetNextThread` at `0x18000b1cb`
- `ntdll!NtGetNextThread` at `0x18000b23c`
- `ntdll!NtGetNextThread` at `0x18000b1cb`
- `ntdll!NtGetNextThread` at `0x18000b23c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b32f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b341`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b37e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b32f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b341`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b37e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b1e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b1e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b260`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b302`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b260`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b302`

## string_xrefs

- `0x18000b29c`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18000b2d9`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18000b314`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18000b353`: `onecore\com\combase\rpcss\objex\process.cxx`

## pseudocode

```c
__int64 __fastcall CProcess::GetNextThreadHandle(CProcess *this, void *a2, unsigned int a3, void **a4)
{
  int ProcessHandle; // eax
  unsigned int v8; // ebx
  CToken *v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  int NextThread; // eax
  int v14; // [rsp+20h] [rbp-20h]
  HANDLE hObject; // [rsp+30h] [rbp-10h] BYREF
  char *v16; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v18; // [rsp+88h] [rbp+48h] BYREF

  *a4 = 0;
  hObject = 0;
  ProcessHandle = CProcess::GetProcessHandle(this, 0x400u, &hObject);
  v8 = ProcessHandle;
  if ( ProcessHandle >= 0 )
  {
    if ( a3 == 0x2000000 || (v14 = 0, (int)NtGetNextThread(hObject, a2, a3, 0) < 0) )
    {
      AcquireSRWLockShared((PSRWLOCK)this + 68);
      v9 = (CToken *)*((_QWORD *)this + 3);
      v16 = (char *)this + 544;
      if ( !v9 )
      {
        v11 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A9,
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
          (const char *)0x8000FFFFLL,
          v14);
LABEL_13:
        if ( this != (CProcess *)-544LL )
          ReleaseSRWLockShared((PSRWLOCK)this + 68);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        return v11;
      }
      v18 = 0;
      v10 = CToken::Impersonate(v9, 0, &v18);
      v11 = v10;
      if ( v10 >= 0 )
      {
        NextThread = NtGetNextThread(hObject, a2, a3, 0);
        if ( NextThread >= 0 )
        {
          CToken::Revert(*((CToken **)this + 3), v18);
          if ( this != (CProcess *)-544LL )
            ReleaseSRWLockShared((PSRWLOCK)this + 68);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          return 0;
        }
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x3B0,
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
                (const char *)(unsigned int)NextThread,
                0);
        CToken::Revert(*((CToken **)this + 3), v18);
        goto LABEL_13;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3AC,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
        (const char *)(unsigned int)v10,
        v14);
      Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v16);
    }
    else
    {
      v11 = 0;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    return v11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x39B,
    (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
    (const char *)(unsigned int)ProcessHandle,
    v14);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v8;
}

```

## disassembly

```asm
0x18000b15c  mov     [rsp-28h+arg_0], rbx
0x18000b161  mov     [rsp-28h+arg_8], rsi
0x18000b166  push    rbp
0x18000b167  push    rdi
0x18000b168  push    r12
0x18000b16a  push    r14
0x18000b16c  push    r15
0x18000b16e  mov     rbp, rsp
0x18000b171  sub     rsp, 40h
0x18000b175  mov     r14d, r8d
0x18000b178  mov     qword ptr [r9], 0
0x18000b17f  mov     r12, rdx
0x18000b182  mov     [rbp+hObject], 0
0x18000b18a  lea     r8, [rbp+hObject]; void **
0x18000b18e  mov     edx, 400h; unsigned int
0x18000b193  mov     r15, r9
0x18000b196  mov     rsi, rcx
0x18000b199  call    ?GetProcessHandle@CProcess@@QEBAJKPEAPEAX@Z; CProcess::GetProcessHandle(ulong,void * *)
0x18000b19e  mov     ebx, eax
0x18000b1a0  test    eax, eax
0x18000b1a2  js      loc_18000B2D5
0x18000b1a8  cmp     r14d, 2000000h
0x18000b1af  jz      short loc_18000B1DF
0x18000b1b1  mov     rcx, [rbp+hObject]
0x18000b1b5  xor     r9d, r9d
0x18000b1b8  mov     [rsp+40h+var_18], r15
0x18000b1bd  mov     r8d, r14d
0x18000b1c0  mov     rdx, r12
0x18000b1c3  mov     [rsp+40h+var_20], 0; int
0x18000b1cb  call    cs:__imp_NtGetNextThread
0x18000b1d2  nop     dword ptr [rax+rax+00h]
0x18000b1d7  test    eax, eax
0x18000b1d9  jns     loc_18000B33D
0x18000b1df  lea     rbx, [rsi+220h]
0x18000b1e6  mov     rcx, rbx; SRWLock
0x18000b1e9  call    cs:__imp_AcquireSRWLockShared
0x18000b1f0  nop     dword ptr [rax+rax+00h]
0x18000b1f5  mov     rcx, [rsi+18h]; this
0x18000b1f9  mov     [rbp+var_8], rbx
0x18000b1fd  test    rcx, rcx
0x18000b200  jz      loc_18000B310
0x18000b206  lea     r8, [rbp+arg_18]; int *
0x18000b20a  mov     [rbp+arg_18], 0
0x18000b211  xor     edx, edx; int
0x18000b213  call    ?Impersonate@CToken@@UEAAJHPEAH@Z; CToken::Impersonate(int,int *)
0x18000b218  mov     edi, eax
0x18000b21a  test    eax, eax
0x18000b21c  js      loc_18000B34F
0x18000b222  mov     rcx, [rbp+hObject]
0x18000b226  xor     r9d, r9d
0x18000b229  mov     [rsp+40h+var_18], r15
0x18000b22e  mov     r8d, r14d
0x18000b231  mov     rdx, r12
0x18000b234  mov     [rsp+40h+var_20], 0; int
0x18000b23c  call    cs:__imp_NtGetNextThread
0x18000b243  nop     dword ptr [rax+rax+00h]
0x18000b248  test    eax, eax
0x18000b24a  js      short loc_18000B298
0x18000b24c  mov     edx, [rbp+arg_18]; int
0x18000b24f  mov     rcx, [rsi+18h]; this
0x18000b253  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18000b258  test    rbx, rbx
0x18000b25b  jz      short loc_18000B26C
0x18000b25d  mov     rcx, rbx; SRWLock
0x18000b260  call    cs:__imp_ReleaseSRWLockShared
0x18000b267  nop     dword ptr [rax+rax+00h]
0x18000b26c  mov     rcx, [rbp+hObject]; hObject
0x18000b270  lea     rax, [rcx-1]
0x18000b274  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b278  jbe     loc_18000B37E
0x18000b27e  xor     eax, eax
0x18000b280  mov     rbx, [rsp+40h+arg_0]
0x18000b285  mov     rsi, [rsp+40h+arg_8]
0x18000b28a  add     rsp, 40h
0x18000b28e  pop     r15
0x18000b290  pop     r14
0x18000b292  pop     r12
0x18000b294  pop     rdi
0x18000b295  pop     rbp
0x18000b296  retn
0x18000b298  mov     rcx, [rbp+28h]; this
0x18000b29c  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x18000b2a3  mov     r9d, eax; char *
0x18000b2a6  mov     edx, 3B0h; void *
0x18000b2ab  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000b2b0  mov     edx, [rbp+arg_18]; int
0x18000b2b3  mov     edi, eax
0x18000b2b5  mov     rcx, [rsi+18h]; this
0x18000b2b9  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18000b2be  test    rbx, rbx
0x18000b2c1  jnz     short loc_18000B2FF
0x18000b2c3  mov     rcx, [rbp+hObject]; hObject
0x18000b2c7  lea     rdx, [rcx-1]
0x18000b2cb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000b2cf  jbe     short loc_18000B341
0x18000b2d1  mov     eax, edi
0x18000b2d3  jmp     short loc_18000B280
0x18000b2d5  mov     rcx, [rbp+28h]; this
0x18000b2d9  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x18000b2e0  mov     r9d, ebx; char *
0x18000b2e3  mov     edx, 39Bh; void *
0x18000b2e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2ed  mov     rcx, [rbp+hObject]; hObject
0x18000b2f1  lea     rdx, [rcx-1]
0x18000b2f5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000b2f9  jbe     short loc_18000B32F
0x18000b2fb  mov     eax, ebx
0x18000b2fd  jmp     short loc_18000B280
0x18000b2ff  mov     rcx, rbx; SRWLock
0x18000b302  call    cs:__imp_ReleaseSRWLockShared
0x18000b309  nop     dword ptr [rax+rax+00h]
0x18000b30e  jmp     short loc_18000B2C3
0x18000b310  mov     rcx, [rbp+28h]; this
0x18000b314  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x18000b31b  mov     edi, 8000FFFFh
0x18000b320  mov     edx, 3A9h; void *
0x18000b325  mov     r9d, edi; char *
0x18000b328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b32d  jmp     short loc_18000B2BE
0x18000b32f  call    cs:__imp_CloseHandle
0x18000b336  nop     dword ptr [rax+rax+00h]
0x18000b33b  jmp     short loc_18000B2FB
0x18000b33d  xor     edi, edi
0x18000b33f  jmp     short loc_18000B370
0x18000b341  call    cs:__imp_CloseHandle
0x18000b348  nop     dword ptr [rax+rax+00h]
0x18000b34d  jmp     short loc_18000B2D1
0x18000b34f  mov     rcx, [rbp+28h]; this
0x18000b353  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x18000b35a  mov     r9d, eax; char *
0x18000b35d  mov     edx, 3ACh; void *
0x18000b362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b367  lea     rcx, [rbp+var_8]; this
0x18000b36b  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x18000b370  lea     rcx, [rbp+hObject]
0x18000b374  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000b379  jmp     loc_18000B2D1
0x18000b37e  call    cs:__imp_CloseHandle
0x18000b385  nop     dword ptr [rax+rax+00h]
0x18000b38a  jmp     loc_18000B27E
```

# ATL::CAccessToken::GetThreadToken(ulong,void *,bool)

- ea: `0x180053cf8`
- end: `0x180053d4f`
- name: `?GetThreadToken@CAccessToken@ATL@@QEAA_NKPEAX_N@Z`
- size: `87`
- prototype: `bool __fastcall(ATL::CAccessToken *__hidden this, unsigned int, void *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180053d58`

## callees

- `0x180053cf8`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053d25`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053d25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180053d05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180053d05`

## pseudocode

```c
bool __fastcall ATL::CAccessToken::GetThreadToken(ATL::CAccessToken *this, __int64 a2, void *a3)
{
  HANDLE CurrentThread; // rax
  BOOL v5; // eax
  HANDLE TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = a3;
  CurrentThread = GetCurrentThread();
  TokenHandle = 0;
  v5 = OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle);
  if ( v5 )
  {
    (*(void (__fastcall **)(ATL::CAccessToken *))(*(_QWORD *)this + 8LL))(this);
    LOBYTE(v5) = 1;
    *((_QWORD *)this + 1) = TokenHandle;
  }
  return v5;
}

```

## disassembly

```asm
0x180053cf8  mov     [rsp+TokenHandle], r8
0x180053cfd  push    rbx
0x180053cfe  sub     rsp, 20h
0x180053d02  mov     rbx, rcx
0x180053d05  call    cs:__imp_GetCurrentThread
0x180053d0b  mov     edx, 0Eh; DesiredAccess
0x180053d10  mov     [rsp+28h+TokenHandle], 0
0x180053d19  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180053d1e  mov     rcx, rax; ThreadHandle
0x180053d21  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180053d25  call    cs:__imp_OpenThreadToken
0x180053d2b  test    eax, eax
0x180053d2d  jz      short loc_180053D49
0x180053d2f  mov     rcx, [rbx]
0x180053d32  mov     rax, [rcx+8]
0x180053d36  mov     rcx, rbx
0x180053d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d3e  mov     rcx, [rsp+28h+TokenHandle]
0x180053d43  mov     al, 1
0x180053d45  mov     [rbx+8], rcx
0x180053d49  add     rsp, 20h
0x180053d4d  pop     rbx
0x180053d4e  retn
```

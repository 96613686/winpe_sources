# ATL::CAccessToken::GetThreadToken(ulong,void *,bool)

- ea: `0x180016170`
- end: `0x1800161c7`
- name: `?GetThreadToken@CAccessToken@ATL@@QEAA_NKPEAX_N@Z`
- size: `87`
- prototype: `bool __fastcall(ATL::CAccessToken *__hidden this, unsigned int, void *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18004db08`

## callees

- `0x180016170`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001617d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001617d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001619d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001619d`

## pseudocode

```c
bool __fastcall ATL::CAccessToken::GetThreadToken(ATL::CAccessToken *this, __int64 a2, void *a3)
{
  HANDLE CurrentThread; // rax
  BOOL v5; // eax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

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
0x180016170  mov     [rsp+TokenHandle], r8
0x180016175  push    rbx
0x180016176  sub     rsp, 20h
0x18001617a  mov     rbx, rcx
0x18001617d  call    cs:__imp_GetCurrentThread
0x180016183  mov     edx, 0Eh; DesiredAccess
0x180016188  mov     [rsp+28h+TokenHandle], 0
0x180016191  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180016196  mov     rcx, rax; ThreadHandle
0x180016199  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x18001619d  call    cs:__imp_OpenThreadToken
0x1800161a3  test    eax, eax
0x1800161a5  jz      short loc_1800161C1
0x1800161a7  mov     rcx, [rbx]
0x1800161aa  mov     rax, [rcx+8]
0x1800161ae  mov     rcx, rbx
0x1800161b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161b6  mov     rcx, [rsp+28h+TokenHandle]
0x1800161bb  mov     al, 1
0x1800161bd  mov     [rbx+8], rcx
0x1800161c1  add     rsp, 20h
0x1800161c5  pop     rbx
0x1800161c6  retn
```

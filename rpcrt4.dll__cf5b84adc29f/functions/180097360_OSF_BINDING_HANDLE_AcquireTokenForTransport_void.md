# OSF_BINDING_HANDLE::AcquireTokenForTransport(void * *)

- ea: `0x180097360`
- end: `0x180097401`
- name: `?AcquireTokenForTransport@OSF_BINDING_HANDLE@@QEAAJPEAPEAX@Z`
- size: `161`
- prototype: `int(OSF_BINDING_HANDLE *__hidden this, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800af198`

## callees

- `0x1800295d8`
- `0x180097360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800973bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800973bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009738d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009738d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180097370`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180097370`

## pseudocode

```c
__int64 __fastcall OSF_BINDING_HANDLE::AcquireTokenForTransport(OSF_BINDING_HANDLE *this, void **a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  _DWORD v7[10]; // [rsp+30h] [rbp-28h] BYREF

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, a2) )
    return 0;
  *((_DWORD *)this + 43) = 1;
  *((_QWORD *)this + 54) = 0;
  LastError = GetLastError();
  if ( LastError == 1008 )
    return 0;
  v7[2] = LastError;
  v7[0] = 3;
  RpcpErrorAddRecord(2u, 5, 0x334u, 1, (struct tagParam *)v7);
  return 5;
}

```

## disassembly

```asm
0x180097360  mov     [rsp+arg_0], rbx
0x180097365  push    rdi
0x180097366  sub     rsp, 50h
0x18009736a  mov     rbx, rdx
0x18009736d  mov     rdi, rcx
0x180097370  call    cs:__imp_GetCurrentThread
0x180097377  nop     dword ptr [rax+rax+00h]
0x18009737c  mov     r9, rbx; TokenHandle
0x18009737f  mov     ebx, 1
0x180097384  mov     rcx, rax; ThreadHandle
0x180097387  mov     r8d, ebx; OpenAsSelf
0x18009738a  lea     edx, [rbx+0Bh]; DesiredAccess
0x18009738d  call    cs:__imp_OpenThreadToken
0x180097394  nop     dword ptr [rax+rax+00h]
0x180097399  test    eax, eax
0x18009739b  jz      short loc_1800973AB
0x18009739d  xor     eax, eax
0x18009739f  mov     rbx, [rsp+58h+arg_0]
0x1800973a4  add     rsp, 50h
0x1800973a8  pop     rdi
0x1800973a9  retn
0x1800973ab  mov     [rdi+0ACh], ebx
0x1800973b1  mov     qword ptr [rdi+1B0h], 0
0x1800973bc  call    cs:__imp_GetLastError
0x1800973c3  nop     dword ptr [rax+rax+00h]
0x1800973c8  cmp     eax, 3F0h
0x1800973cd  jz      short loc_18009739D
0x1800973cf  mov     r9d, ebx; int
0x1800973d2  mov     [rsp+58h+var_20], eax
0x1800973d6  mov     ebx, 5
0x1800973db  mov     [rsp+58h+var_28], 3
0x1800973e3  lea     rax, [rsp+58h+var_28]
0x1800973e8  mov     r8d, 334h; unsigned __int16
0x1800973ee  mov     edx, ebx; int
0x1800973f0  mov     [rsp+58h+var_38], rax; struct tagParam *
0x1800973f5  lea     ecx, [rbx-3]; unsigned int
0x1800973f8  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800973fd  mov     eax, ebx
0x1800973ff  jmp     short loc_18009739F
```

# OSF_BINDING_HANDLE::AcquireTokenForTransport(void * *)

- ea: `0x18009486c`
- end: `0x1800948fa`
- name: `?AcquireTokenForTransport@OSF_BINDING_HANDLE@@QEAAJPEAPEAX@Z`
- size: `142`
- prototype: `int(OSF_BINDING_HANDLE *__hidden this, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800ab758`

## callees

- `0x1800283bc`
- `0x18009486c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800948bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800948bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180094893`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180094893`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009487c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009487c`

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
0x18009486c  mov     [rsp+arg_0], rbx
0x180094871  push    rdi
0x180094872  sub     rsp, 50h
0x180094876  mov     rbx, rdx
0x180094879  mov     rdi, rcx
0x18009487c  call    cs:__imp_GetCurrentThread
0x180094882  mov     r9, rbx; TokenHandle
0x180094885  mov     ebx, 1
0x18009488a  mov     rcx, rax; ThreadHandle
0x18009488d  mov     r8d, ebx; OpenAsSelf
0x180094890  lea     edx, [rbx+0Bh]; DesiredAccess
0x180094893  call    cs:__imp_OpenThreadToken
0x180094899  test    eax, eax
0x18009489b  jz      short loc_1800948AA
0x18009489d  xor     eax, eax
0x18009489f  mov     rbx, [rsp+58h+arg_0]
0x1800948a4  add     rsp, 50h
0x1800948a8  pop     rdi
0x1800948a9  retn
0x1800948aa  mov     [rdi+0ACh], ebx
0x1800948b0  mov     qword ptr [rdi+1B0h], 0
0x1800948bb  call    cs:__imp_GetLastError
0x1800948c1  cmp     eax, 3F0h
0x1800948c6  jz      short loc_18009489D
0x1800948c8  mov     r9d, ebx; int
0x1800948cb  mov     [rsp+58h+var_20], eax
0x1800948cf  mov     ebx, 5
0x1800948d4  mov     [rsp+58h+var_28], 3
0x1800948dc  lea     rax, [rsp+58h+var_28]
0x1800948e1  mov     r8d, 334h; unsigned __int16
0x1800948e7  mov     edx, ebx; int
0x1800948e9  mov     [rsp+58h+var_38], rax; struct tagParam *
0x1800948ee  lea     ecx, [rbx-3]; unsigned int
0x1800948f1  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800948f6  mov     eax, ebx
0x1800948f8  jmp     short loc_18009489F
```

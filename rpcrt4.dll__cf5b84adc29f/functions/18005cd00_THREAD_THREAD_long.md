# THREAD::THREAD(long *)

- ea: `0x18005cd00`
- end: `0x18005ce21`
- name: `??0THREAD@@QEAA@PEAJ@Z`
- size: `289`
- prototype: `THREAD *__fastcall(THREAD *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ccb4`

## callees

- `0x18005cd00`
- `0x18005ce28`
- `0x18005ce84`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005cd88`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005cd88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cde4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cde4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cd49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cd49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005cd58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005cd58`

## pseudocode

```c
THREAD *__fastcall THREAD::THREAD(THREAD *this, int *a2)
{
  bool v4; // zf
  HANDLE *v5; // r14
  HANDLE CurrentProcess; // rbx
  HANDLE CurrentThread; // rax

  EVENT::EVENT((THREAD *)((char *)this + 24), a2, 1);
  *((_DWORD *)this + 24) = 0;
  *((_DWORD *)this + 30) = 0;
  THREAD::CommonConstructor(this);
  v4 = *a2 == 0;
  v5 = (HANDLE *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  if ( v4 )
  {
    CurrentProcess = GetCurrentProcess();
    CurrentThread = GetCurrentThread();
    if ( !DuplicateHandle(CurrentProcess, CurrentThread, CurrentProcess, (LPHANDLE)this + 1, 0, 0, 2u) )
    {
LABEL_6:
      *a2 = 14;
      return this;
    }
    if ( gfRPCVerifierEnabled
      && *((_DWORD *)pRpcVerifierSettings + 24)
      && !(*((unsigned int (__fastcall **)(HANDLE))pRpcVerifierSettings + 25))(*v5) )
    {
      CloseHandle(*v5);
      *v5 = 0;
      goto LABEL_6;
    }
    *a2 = 0;
    NtCurrentTeb()->ReservedForNtRpc = (PVOID)(((unsigned __int64)this ^ 0xABABABABDEDEDEDEuLL) & -(__int64)(this != 0));
  }
  return this;
}

```

## disassembly

```asm
0x18005cd00  push    rbx
0x18005cd02  push    rsi
0x18005cd03  push    rdi
0x18005cd04  push    r14
0x18005cd06  sub     rsp, 48h
0x18005cd0a  mov     rdi, rcx
0x18005cd0d  mov     r8d, 1; int
0x18005cd13  add     rcx, 18h; this
0x18005cd17  mov     rsi, rdx
0x18005cd1a  call    ??0EVENT@@QEAA@PEAJH@Z; EVENT::EVENT(long *,int)
0x18005cd1f  mov     dword ptr [rdi+60h], 0
0x18005cd26  mov     rcx, rdi; this
0x18005cd29  mov     dword ptr [rdi+78h], 0
0x18005cd30  call    ?CommonConstructor@THREAD@@QEAAXXZ; THREAD::CommonConstructor(void)
0x18005cd35  cmp     dword ptr [rsi], 0
0x18005cd38  lea     r14, [rdi+8]
0x18005cd3c  mov     qword ptr [r14], 0
0x18005cd43  jnz     loc_18005CDD3
0x18005cd49  call    cs:__imp_GetCurrentProcess
0x18005cd50  nop     dword ptr [rax+rax+00h]
0x18005cd55  mov     rbx, rax
0x18005cd58  call    cs:__imp_GetCurrentThread
0x18005cd5f  nop     dword ptr [rax+rax+00h]
0x18005cd64  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18005cd6c  mov     r9, r14; lpTargetHandle
0x18005cd6f  mov     rdx, rax; hSourceHandle
0x18005cd72  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18005cd7a  mov     r8, rbx; hTargetProcessHandle
0x18005cd7d  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18005cd85  mov     rcx, rbx; hSourceProcessHandle
0x18005cd88  call    cs:__imp_DuplicateHandle
0x18005cd8f  nop     dword ptr [rax+rax+00h]
0x18005cd94  test    eax, eax
0x18005cd96  jz      short loc_18005CDF7
0x18005cd98  cmp     cs:?gfRPCVerifierEnabled@@3HA, 0; int gfRPCVerifierEnabled
0x18005cd9f  jnz     short loc_18005CDFF
0x18005cda1  mov     rcx, 0ABABABABDEDEDEDEh
0x18005cdab  mov     dword ptr [rsi], 0
0x18005cdb1  mov     rdx, rdi
0x18005cdb4  mov     rax, rdi
0x18005cdb7  xor     rdx, rcx
0x18005cdba  neg     rax
0x18005cdbd  mov     rax, gs:30h
0x18005cdc6  sbb     rcx, rcx
0x18005cdc9  and     rcx, rdx
0x18005cdcc  mov     [rax+1698h], rcx
0x18005cdd3  mov     rax, rdi
0x18005cdd6  add     rsp, 48h
0x18005cdda  pop     r14
0x18005cddc  pop     rdi
0x18005cddd  pop     rsi
0x18005cdde  pop     rbx
0x18005cddf  retn
0x18005cde1  mov     rcx, [r14]; hObject
0x18005cde4  call    cs:__imp_CloseHandle
0x18005cdeb  nop     dword ptr [rax+rax+00h]
0x18005cdf0  mov     qword ptr [r14], 0
0x18005cdf7  mov     dword ptr [rsi], 0Eh
0x18005cdfd  jmp     short loc_18005CDD3
0x18005cdff  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x18005ce06  cmp     dword ptr [rax+60h], 0
0x18005ce0a  jz      short loc_18005CDA1
0x18005ce0c  mov     rcx, [r14]
0x18005ce0f  mov     rax, [rax+0C8h]
0x18005ce16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce1b  test    eax, eax
0x18005ce1d  jnz     short loc_18005CDA1
0x18005ce1f  jmp     short loc_18005CDE1
```

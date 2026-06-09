# THREAD::THREAD(long *)

- ea: `0x18004a934`
- end: `0x18004aa38`
- name: `??0THREAD@@QEAA@PEAJ@Z`
- size: `260`
- prototype: `THREAD *__fastcall(THREAD *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a8e8`

## callees

- `0x18004a934`
- `0x18004aa40`
- `0x18004aa94`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004a9ac`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004a9ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aa01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aa01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004a979`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004a979`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004a982`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004a982`

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
0x18004a934  push    rbx
0x18004a936  push    rsi
0x18004a937  push    rdi
0x18004a938  push    r14
0x18004a93a  sub     rsp, 48h
0x18004a93e  mov     rdi, rcx
0x18004a941  mov     r8d, 1; int
0x18004a947  add     rcx, 18h; this
0x18004a94b  mov     rsi, rdx
0x18004a94e  call    ??0EVENT@@QEAA@PEAJH@Z; EVENT::EVENT(long *,int)
0x18004a953  mov     dword ptr [rdi+60h], 0
0x18004a95a  mov     rcx, rdi; this
0x18004a95d  mov     dword ptr [rdi+78h], 0
0x18004a964  call    ?CommonConstructor@THREAD@@QEAAXXZ; THREAD::CommonConstructor(void)
0x18004a969  cmp     dword ptr [rsi], 0
0x18004a96c  lea     r14, [rdi+8]
0x18004a970  mov     qword ptr [r14], 0
0x18004a977  jnz     short loc_18004A9F1
0x18004a979  call    cs:__imp_GetCurrentProcess
0x18004a97f  mov     rbx, rax
0x18004a982  call    cs:__imp_GetCurrentThread
0x18004a988  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18004a990  mov     r9, r14; lpTargetHandle
0x18004a993  mov     rdx, rax; hSourceHandle
0x18004a996  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18004a99e  mov     r8, rbx; hTargetProcessHandle
0x18004a9a1  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18004a9a9  mov     rcx, rbx; hSourceProcessHandle
0x18004a9ac  call    cs:__imp_DuplicateHandle
0x18004a9b2  test    eax, eax
0x18004a9b4  jz      short loc_18004AA0E
0x18004a9b6  cmp     cs:?gfRPCVerifierEnabled@@3HA, 0; int gfRPCVerifierEnabled
0x18004a9bd  jnz     short loc_18004AA16
0x18004a9bf  mov     rcx, 0ABABABABDEDEDEDEh
0x18004a9c9  mov     dword ptr [rsi], 0
0x18004a9cf  mov     rdx, rdi
0x18004a9d2  mov     rax, rdi
0x18004a9d5  xor     rdx, rcx
0x18004a9d8  neg     rax
0x18004a9db  mov     rax, gs:30h
0x18004a9e4  sbb     rcx, rcx
0x18004a9e7  and     rcx, rdx
0x18004a9ea  mov     [rax+1698h], rcx
0x18004a9f1  mov     rax, rdi
0x18004a9f4  add     rsp, 48h
0x18004a9f8  pop     r14
0x18004a9fa  pop     rdi
0x18004a9fb  pop     rsi
0x18004a9fc  pop     rbx
0x18004a9fd  retn
0x18004a9fe  mov     rcx, [r14]; hObject
0x18004aa01  call    cs:__imp_CloseHandle
0x18004aa07  mov     qword ptr [r14], 0
0x18004aa0e  mov     dword ptr [rsi], 0Eh
0x18004aa14  jmp     short loc_18004A9F1
0x18004aa16  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x18004aa1d  cmp     dword ptr [rax+60h], 0
0x18004aa21  jz      short loc_18004A9BF
0x18004aa23  mov     rcx, [r14]
0x18004aa26  mov     rax, [rax+0C8h]
0x18004aa2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa32  test    eax, eax
0x18004aa34  jnz     short loc_18004A9BF
0x18004aa36  jmp     short loc_18004A9FE
```

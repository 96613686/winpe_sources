# FiberScheduler::PreemptiveSwitchHelper(void *)

- ea: `0x100484290`
- end: `0x1004843f2`
- name: `?PreemptiveSwitchHelper@FiberScheduler@@CAXPEAX@Z`
- size: `354`
- prototype: `void __stdcall(LPVOID lpFiberParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x100426a00`
- `0x10042bf30`
- `0x100434d70`
- `0x1004360f0`
- `0x100484290`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!SwitchToFiber` at `0x1004843e6`
- `KERNEL32!SwitchToFiber` at `0x1004843e6`
- `KERNEL32!GetLastError` at `0x100484383`
- `KERNEL32!GetLastError` at `0x100484383`
- `ADVAPI32!SetThreadToken` at `0x100484379`
- `ADVAPI32!SetThreadToken` at `0x100484379`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x1004843be`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x1004843be`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x1004843d9`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x1004843d9`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x1004843c8`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x1004843c8`

## string_xrefs

- `0x100484393`: `Sql\DkTemp\sos\include\worker_ext.inl`
- `0x1004842a6`: `SetThreadToken failed: %d`

## pseudocode

```c
void __fastcall __noreturn FiberScheduler::PreemptiveSwitchHelper(LPVOID lpFiberParameter)
{
  __int64 v1; // rbx
  __int64 v2; // rdx
  _QWORD *v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rdi
  struct SystemThread *v6; // rbx
  __int64 v7; // rbx
  void *v8; // rdx
  DWORD LastError; // eax

  while ( 1 )
  {
    v1 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
       + (unsigned int)SystemThread_TlsOffset;
    v2 = *(_QWORD *)(v1 + 256);
    if ( !v2 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v2 = *(_QWORD *)(v1 + 256);
    }
    v3 = *(_QWORD **)(v2 + 608);
    *(_QWORD *)(v2 + 624) = 0;
    SystemThreadDispatcher::EnqueueWorker(v3[650] + 192LL, v2, 2);
    v4 = v3[641];
    v3[640] = v4;
    _InterlockedExchange((volatile __int32 *)(v4 + 728), 2);
    v5 = v3[641];
    v6 = (struct SystemThread *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                               + (unsigned int)SystemThread_TlsOffset);
    BindSystemThreadAndWorker(v6, (struct Worker *const)v5);
    *((_DWORD *)v6 + 66) &= 0xFFFFFFFC;
    SystemThread::ChangeCPUId(v6, *(_DWORD *)(v5 + 76));
    v7 = *(_QWORD *)(v5 + 624);
    v8 = *(void **)(v5 + 504);
    if ( *(void **)(v7 + 304) != v8 )
    {
      if ( !SetThreadToken(0, v8) )
      {
        LastError = GetLastError();
        utassert_fail(
          1u,
          "result",
          "Sql\\DkTemp\\sos\\include\\worker_ext.inl",
          559,
          "SetThreadToken failed: %d",
          LastError);
      }
      *(_QWORD *)(v7 + 304) = *(_QWORD *)(v5 + 504);
    }
    if ( (_clearfp() & 0x10) != 0 )
      _fpreset();
    _controlfp(*(_DWORD *)(v5 + 808), 0x8001Fu);
    SwitchToFiber(*(LPVOID *)(v5 + 640));
  }
}

```

## disassembly

```asm
0x100484290  mov     [rsp+arg_0], rbx
0x100484295  mov     [rsp+arg_8], rbp
0x10048429a  mov     [rsp+arg_10], rsi
0x10048429f  push    rdi
0x1004842a0  sub     rsp, 30h
0x1004842a4  xor     ebp, ebp
0x1004842a6  lea     rsi, ?szText@?9??TokenFiberSuspending@Worker@@KAXPEAV2@0@Z@4QBDB; "SetThreadToken failed: %d"
0x1004842ad  nop     dword ptr [rax]
0x1004842b0  mov     rcx, gs:58h
0x1004842b9  mov     eax, cs:_tls_index
0x1004842bf  mov     ebx, cs:SystemThread_TlsOffset
0x1004842c5  add     rbx, [rcx+rax*8]
0x1004842c9  mov     rdx, [rbx+100h]
0x1004842d0  test    rdx, rdx
0x1004842d3  jnz     short loc_1004842E3
0x1004842d5  xor     ecx, ecx; void *
0x1004842d7  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004842dc  mov     rdx, [rbx+100h]
0x1004842e3  mov     rbx, [rdx+260h]
0x1004842ea  mov     r8d, 2
0x1004842f0  mov     [rdx+270h], rbp
0x1004842f7  mov     rcx, [rbx+1450h]
0x1004842fe  add     rcx, 0C0h
0x100484305  call    ?EnqueueWorker@SystemThreadDispatcher@@QEAA?AW4SOS_RESULT@@PEAVWorker@@W4SYSTHREAD_DISPATCH_TYPE@@@Z; SystemThreadDispatcher::EnqueueWorker(Worker *,SYSTHREAD_DISPATCH_TYPE)
0x10048430a  mov     rcx, [rbx+1408h]
0x100484311  mov     eax, 2
0x100484316  mov     [rbx+1400h], rcx
0x10048431d  xchg    eax, [rcx+2D8h]
0x100484323  mov     rdx, gs:58h
0x10048432c  mov     rdi, [rbx+1408h]
0x100484333  mov     eax, cs:_tls_index
0x100484339  mov     ebx, cs:SystemThread_TlsOffset
0x10048433f  add     rbx, [rdx+rax*8]
0x100484343  mov     rdx, rdi; struct Worker *
0x100484346  mov     rcx, rbx; struct SystemThread *
0x100484349  call    ?BindSystemThreadAndWorker@@YAXQEAVSystemThread@@QEAVWorker@@@Z; BindSystemThreadAndWorker(SystemThread * const,Worker * const)
0x10048434e  and     dword ptr [rbx+108h], 0FFFFFFFCh
0x100484355  mov     rcx, rbx; this
0x100484358  mov     edx, [rdi+4Ch]; unsigned int
0x10048435b  call    ?ChangeCPUId@SystemThread@@QEAAKK@Z; SystemThread::ChangeCPUId(ulong)
0x100484360  mov     rbx, [rdi+270h]
0x100484367  mov     rdx, [rdi+1F8h]; Token
0x10048436e  cmp     [rbx+130h], rdx
0x100484375  jz      short loc_1004843BE
0x100484377  xor     ecx, ecx; Thread
0x100484379  call    cs:__imp_SetThreadToken
0x10048437f  test    eax, eax
0x100484381  jnz     short loc_1004843B0
0x100484383  call    cs:__imp_GetLastError
0x100484389  mov     [rsp+38h+var_10], eax
0x10048438d  mov     r9d, 22Fh; int
0x100484393  lea     r8, ?szFileName@?9??TokenTaskDetach@Worker@@IEAAXXZ@4QBDB; "Sql\\DkTemp\\sos\\include\\worker_ext.i"...
0x10048439a  mov     [rsp+38h+Format], rsi; Format
0x10048439f  lea     rdx, ?szExpression@?9??TokenFiberSuspending@Worker@@KAXPEAV2@0@Z@4QBDB; "result"
0x1004843a6  mov     ecx, 1; unsigned int
0x1004843ab  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004843b0  mov     rax, [rdi+1F8h]
0x1004843b7  mov     [rbx+130h], rax
0x1004843be  call    cs:__imp__clearfp
0x1004843c4  test    al, 10h
0x1004843c6  jz      short loc_1004843CE
0x1004843c8  call    cs:__imp__fpreset
0x1004843ce  mov     ecx, [rdi+328h]; NewValue
0x1004843d4  mov     edx, 8001Fh; Mask
0x1004843d9  call    cs:__imp__controlfp
0x1004843df  mov     rcx, [rdi+280h]; lpFiber
0x1004843e6  call    cs:__imp_SwitchToFiber
0x1004843ec  jmp     loc_1004842B0
```

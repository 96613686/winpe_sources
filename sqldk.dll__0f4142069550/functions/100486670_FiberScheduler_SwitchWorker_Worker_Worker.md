# FiberScheduler::SwitchWorker(Worker *,Worker *)

- ea: `0x100486670`
- end: `0x100486786`
- name: `?SwitchWorker@FiberScheduler@@UEAAXPEAVWorker@@0@Z`
- size: `278`
- prototype: `void(FiberScheduler *__hidden this, struct Worker *, struct Worker *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100426a00`
- `0x100434d70`
- `0x100486670`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!SwitchToFiber` at `0x10048677f`
- `KERNEL32!GetLastError` at `0x1004866ee`
- `KERNEL32!GetLastError` at `0x1004866ee`
- `ADVAPI32!SetThreadToken` at `0x1004866e4`
- `ADVAPI32!SetThreadToken` at `0x1004866e4`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x100486748`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x100486748`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x100486763`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x100486763`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x100486752`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x100486752`

## string_xrefs

- `0x1004866fe`: `Sql\DkTemp\sos\include\worker_ext.inl`
- `0x10048670a`: `SetThreadToken failed: %d`

## pseudocode

```c
void __fastcall FiberScheduler::SwitchWorker(FiberScheduler *this, struct Worker *a2, struct Worker *a3)
{
  struct SystemThread *v5; // rsi
  __int64 v6; // rsi
  void *v7; // rdx
  DWORD LastError; // eax

  v5 = (struct SystemThread *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                             + (unsigned int)SystemThread_TlsOffset);
  if ( a2 )
    *((_QWORD *)a2 + 78) = 0;
  BindSystemThreadAndWorker(v5, a3);
  *((_DWORD *)v5 + 66) &= 0xFFFFFFFC;
  SystemThread::ChangeCPUId(v5, *((_DWORD *)a3 + 19));
  v6 = *((_QWORD *)a3 + 78);
  v7 = (void *)*((_QWORD *)a3 + 63);
  if ( *(void **)(v6 + 304) != v7 )
  {
    if ( !SetThreadToken(0, v7) )
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
    *(_QWORD *)(v6 + 304) = *((_QWORD *)a3 + 63);
  }
  if ( !a2 || ((*((_DWORD *)a3 + 202) ^ *((_DWORD *)a2 + 202)) & 0x8001F) != 0 )
  {
    if ( (_clearfp() & 0x10) != 0 )
      _fpreset();
    _controlfp(*((_DWORD *)a3 + 202), 0x8001Fu);
  }
  SwitchToFiber(*((LPVOID *)a3 + 80));
}

```

## disassembly

```asm
0x100486670  mov     [rsp+arg_0], rbx
0x100486675  mov     [rsp+arg_8], rsi
0x10048667a  push    rdi
0x10048667b  sub     rsp, 30h
0x10048667f  mov     r9, gs:58h
0x100486688  mov     rbx, r8
0x10048668b  mov     eax, cs:_tls_index
0x100486691  mov     rdi, rdx
0x100486694  mov     esi, cs:SystemThread_TlsOffset
0x10048669a  add     rsi, [r9+rax*8]
0x10048669e  test    rdx, rdx
0x1004866a1  jz      short loc_1004866AE
0x1004866a3  mov     qword ptr [rdx+270h], 0
0x1004866ae  mov     rdx, rbx; struct Worker *
0x1004866b1  mov     rcx, rsi; struct SystemThread *
0x1004866b4  call    ?BindSystemThreadAndWorker@@YAXQEAVSystemThread@@QEAVWorker@@@Z; BindSystemThreadAndWorker(SystemThread * const,Worker * const)
0x1004866b9  and     dword ptr [rsi+108h], 0FFFFFFFCh
0x1004866c0  mov     rcx, rsi; this
0x1004866c3  mov     edx, [rbx+4Ch]; unsigned int
0x1004866c6  call    ?ChangeCPUId@SystemThread@@QEAAKK@Z; SystemThread::ChangeCPUId(ulong)
0x1004866cb  mov     rsi, [rbx+270h]
0x1004866d2  mov     rdx, [rbx+1F8h]; Token
0x1004866d9  cmp     [rsi+130h], rdx
0x1004866e0  jz      short loc_100486730
0x1004866e2  xor     ecx, ecx; Thread
0x1004866e4  call    cs:__imp_SetThreadToken
0x1004866ea  test    eax, eax
0x1004866ec  jnz     short loc_100486722
0x1004866ee  call    cs:__imp_GetLastError
0x1004866f4  mov     [rsp+38h+var_10], eax
0x1004866f8  mov     r9d, 22Fh; int
0x1004866fe  lea     r8, ?szFileName@?9??TokenTaskDetach@Worker@@IEAAXXZ@4QBDB; "Sql\\DkTemp\\sos\\include\\worker_ext.i"...
0x100486705  mov     ecx, 1; unsigned int
0x10048670a  lea     rax, ?szText@?9??TokenFiberSuspending@Worker@@KAXPEAV2@0@Z@4QBDB; "SetThreadToken failed: %d"
0x100486711  lea     rdx, ?szExpression@?9??TokenFiberSuspending@Worker@@KAXPEAV2@0@Z@4QBDB; "result"
0x100486718  mov     [rsp+38h+Format], rax; Format
0x10048671d  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100486722  mov     rax, [rbx+1F8h]
0x100486729  mov     [rsi+130h], rax
0x100486730  test    rdi, rdi
0x100486733  jz      short loc_100486748
0x100486735  mov     eax, [rdi+328h]
0x10048673b  xor     eax, [rbx+328h]
0x100486741  test    eax, 8001Fh
0x100486746  jz      short loc_100486769
0x100486748  call    cs:__imp__clearfp
0x10048674e  test    al, 10h
0x100486750  jz      short loc_100486758
0x100486752  call    cs:__imp__fpreset
0x100486758  mov     ecx, [rbx+328h]; NewValue
0x10048675e  mov     edx, 8001Fh; Mask
0x100486763  call    cs:__imp__controlfp
0x100486769  mov     rcx, [rbx+280h]
0x100486770  mov     rbx, [rsp+38h+arg_0]
0x100486775  mov     rsi, [rsp+38h+arg_8]
0x10048677a  add     rsp, 30h
0x10048677e  pop     rdi
0x10048677f  jmp     cs:__imp_SwitchToFiber
```

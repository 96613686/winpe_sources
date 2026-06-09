# FiberScheduler::RunWorker(SystemThread *,Worker *)

- ea: `0x1004867a0`
- end: `0x1004868b4`
- name: `?RunWorker@FiberScheduler@@UEAA?AW4SOS_RESULT@@PEAVSystemThread@@PEAVWorker@@@Z`
- size: `276`
- prototype: `enum SOS_RESULT __high(struct SystemThread *, struct Worker *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100426a00`
- `0x100434d70`
- `0x1004867a0`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!SwitchToFiber` at `0x1004868a1`
- `KERNEL32!SwitchToFiber` at `0x1004868a1`
- `KERNEL32!ConvertThreadToFiber` at `0x1004867bc`
- `KERNEL32!ConvertThreadToFiber` at `0x1004867bc`
- `KERNEL32!GetLastError` at `0x100486837`
- `KERNEL32!GetLastError` at `0x100486837`
- `ADVAPI32!SetThreadToken` at `0x10048682d`
- `ADVAPI32!SetThreadToken` at `0x10048682d`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x100486879`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x100486879`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x100486894`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x100486894`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x100486883`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x100486883`

## string_xrefs

- `0x100486847`: `Sql\DkTemp\sos\include\worker_ext.inl`
- `0x100486853`: `SetThreadToken failed: %d`

## pseudocode

```c
__int64 __fastcall FiberScheduler::RunWorker(__int64 a1, __int64 a2, __int64 a3)
{
  LPVOID v5; // rax
  struct SystemThread *v7; // rbx
  __int64 v8; // rbx
  void *v9; // rdx
  DWORD LastError; // eax

  if ( !*(_QWORD *)(a2 + 288) )
  {
    v5 = ConvertThreadToFiber(0);
    *(_QWORD *)(a2 + 288) = v5;
    if ( !v5 )
      return 0x80000000LL;
  }
  v7 = (struct SystemThread *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                             + (unsigned int)SystemThread_TlsOffset);
  BindSystemThreadAndWorker(v7, (struct Worker *const)a3);
  *((_DWORD *)v7 + 66) &= 0xFFFFFFFC;
  SystemThread::ChangeCPUId(v7, *(_DWORD *)(a3 + 76));
  v8 = *(_QWORD *)(a3 + 624);
  v9 = *(void **)(a3 + 504);
  if ( *(void **)(v8 + 304) != v9 )
  {
    if ( !SetThreadToken(0, v9) )
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
    *(_QWORD *)(v8 + 304) = *(_QWORD *)(a3 + 504);
  }
  if ( (_clearfp() & 0x10) != 0 )
    _fpreset();
  _controlfp(*(_DWORD *)(a3 + 808), 0x8001Fu);
  SwitchToFiber(*(LPVOID *)(a3 + 640));
  return 0;
}

```

## disassembly

```asm
0x1004867a0  mov     [rsp+arg_0], rbx
0x1004867a5  push    rdi
0x1004867a6  sub     rsp, 30h
0x1004867aa  cmp     qword ptr [rdx+120h], 0
0x1004867b2  mov     rdi, r8
0x1004867b5  mov     rbx, rdx
0x1004867b8  jnz     short loc_1004867DE
0x1004867ba  xor     ecx, ecx; lpParameter
0x1004867bc  call    cs:__imp_ConvertThreadToFiber
0x1004867c2  mov     [rbx+120h], rax
0x1004867c9  test    rax, rax
0x1004867cc  jnz     short loc_1004867DE
0x1004867ce  mov     eax, 80000000h
0x1004867d3  mov     rbx, [rsp+38h+arg_0]
0x1004867d8  add     rsp, 30h
0x1004867dc  pop     rdi
0x1004867dd  retn
0x1004867de  mov     rdx, gs:58h
0x1004867e7  mov     eax, cs:_tls_index
0x1004867ed  mov     ebx, cs:SystemThread_TlsOffset
0x1004867f3  add     rbx, [rdx+rax*8]
0x1004867f7  mov     rdx, rdi; struct Worker *
0x1004867fa  mov     rcx, rbx; struct SystemThread *
0x1004867fd  call    ?BindSystemThreadAndWorker@@YAXQEAVSystemThread@@QEAVWorker@@@Z; BindSystemThreadAndWorker(SystemThread * const,Worker * const)
0x100486802  and     dword ptr [rbx+108h], 0FFFFFFFCh
0x100486809  mov     rcx, rbx; this
0x10048680c  mov     edx, [rdi+4Ch]; unsigned int
0x10048680f  call    ?ChangeCPUId@SystemThread@@QEAAKK@Z; SystemThread::ChangeCPUId(ulong)
0x100486814  mov     rbx, [rdi+270h]
0x10048681b  mov     rdx, [rdi+1F8h]; Token
0x100486822  cmp     [rbx+130h], rdx
0x100486829  jz      short loc_100486879
0x10048682b  xor     ecx, ecx; Thread
0x10048682d  call    cs:__imp_SetThreadToken
0x100486833  test    eax, eax
0x100486835  jnz     short loc_10048686B
0x100486837  call    cs:__imp_GetLastError
0x10048683d  mov     [rsp+38h+var_10], eax
0x100486841  mov     r9d, 22Fh; int
0x100486847  lea     r8, ?szFileName@?9??TokenTaskDetach@Worker@@IEAAXXZ@4QBDB; "Sql\\DkTemp\\sos\\include\\worker_ext.i"...
0x10048684e  mov     ecx, 1; unsigned int
0x100486853  lea     rax, ?szText@?9??TokenFiberSuspending@Worker@@KAXPEAV2@0@Z@4QBDB; "SetThreadToken failed: %d"
0x10048685a  lea     rdx, ?szExpression@?9??TokenFiberSuspending@Worker@@KAXPEAV2@0@Z@4QBDB; "result"
0x100486861  mov     [rsp+38h+Format], rax; Format
0x100486866  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10048686b  mov     rax, [rdi+1F8h]
0x100486872  mov     [rbx+130h], rax
0x100486879  call    cs:__imp__clearfp
0x10048687f  test    al, 10h
0x100486881  jz      short loc_100486889
0x100486883  call    cs:__imp__fpreset
0x100486889  mov     ecx, [rdi+328h]; NewValue
0x10048688f  mov     edx, 8001Fh; Mask
0x100486894  call    cs:__imp__controlfp
0x10048689a  mov     rcx, [rdi+280h]; lpFiber
0x1004868a1  call    cs:__imp_SwitchToFiber
0x1004868a7  mov     rbx, [rsp+38h+arg_0]
0x1004868ac  xor     eax, eax
0x1004868ae  add     rsp, 30h
0x1004868b2  pop     rdi
0x1004868b3  retn
```

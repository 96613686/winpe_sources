# p9fs::WorkItem::`vector deleting destructor'(uint)

- ea: `0x18002b100`
- end: `0x18002b17e`
- name: `??_EWorkItem@p9fs@@UEAAPEAXI@Z`
- size: `126`
- prototype: `void *__fastcall(p9fs::WorkItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180004534`
- `0x18002b100`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002b152`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002b152`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002b149`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002b149`

## pseudocode

```c
p9fs::WorkItem *__fastcall p9fs::WorkItem::`vector deleting destructor'(p9fs::WorkItem *this, __int64 a2)
{
  char *v2; // rdi
  char *v4; // rcx
  char v5; // si
  struct _TP_WORK *v6; // rdi

  v2 = (char *)this + 16;
  v4 = (char *)*((_QWORD *)this + 9);
  v5 = a2;
  if ( v4 )
  {
    LOBYTE(a2) = v4 != v2;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
    *((_QWORD *)v2 + 7) = 0;
  }
  v6 = (struct _TP_WORK *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 1), 0);
    CloseThreadpoolWork(v6);
  }
  if ( (v5 & 1) != 0 )
    operator delete(this, 0x50u);
  return this;
}

```

## disassembly

```asm
0x18002b100  mov     [rsp+arg_0], rbx
0x18002b105  mov     [rsp+arg_8], rsi
0x18002b10a  push    rdi
0x18002b10b  sub     rsp, 20h
0x18002b10f  lea     rdi, [rcx+10h]
0x18002b113  mov     rbx, rcx
0x18002b116  mov     rcx, [rdi+38h]
0x18002b11a  mov     esi, edx
0x18002b11c  test    rcx, rcx
0x18002b11f  jz      short loc_18002B13B
0x18002b121  mov     rax, [rcx]
0x18002b124  cmp     rcx, rdi
0x18002b127  setnz   dl
0x18002b12a  mov     rax, [rax+20h]
0x18002b12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b133  mov     qword ptr [rdi+38h], 0
0x18002b13b  mov     rdi, [rbx+8]
0x18002b13f  test    rdi, rdi
0x18002b142  jz      short loc_18002B158
0x18002b144  xor     edx, edx; fCancelPendingCallbacks
0x18002b146  mov     rcx, rdi; pwk
0x18002b149  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002b14f  mov     rcx, rdi; pwk
0x18002b152  call    cs:__imp_CloseThreadpoolWork
0x18002b158  test    sil, 1
0x18002b15c  jz      short loc_18002B16B
0x18002b15e  mov     edx, 50h ; 'P'; unsigned __int64
0x18002b163  mov     rcx, rbx; void *
0x18002b166  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b16b  mov     rsi, [rsp+28h+arg_8]
0x18002b170  mov     rax, rbx
0x18002b173  mov     rbx, [rsp+28h+arg_0]
0x18002b178  add     rsp, 20h
0x18002b17c  pop     rdi
0x18002b17d  retn
```

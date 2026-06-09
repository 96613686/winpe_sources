# _Cnd_register_at_thread_exit

- ea: `0x14004e520`
- end: `0x14004e5d5`
- name: `_Cnd_register_at_thread_exit`
- size: `181`
- prototype: `void __cdecl(_Cnd_t, _Mtx_t, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140036e80`

## callees

- `0x1400072e4`
- `0x14001a5d8`
- `0x14004e520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004e59a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004e59a`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x14004e567`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x14004e567`

## pseudocode

```c
void __cdecl Cnd_register_at_thread_exit(_Cnd_t a1, _Mtx_t a2, int *a3)
{
  __int64 *v6; // rbx
  __int64 **v7; // rdi
  int i; // ecx
  __int64 v9; // rdi

  v6 = qword_1400881E0;
  std::_Mutex_base::lock((std::_Mutex_base *)qword_140087A40);
  while ( *((_DWORD *)v6 + 200) == 20 )
  {
    v7 = (__int64 **)(v6 + 101);
    v6 = (__int64 *)v6[101];
    if ( !v6 )
    {
      v6 = (__int64 *)calloc(1u, 0x330u);
      *v7 = v6;
      if ( !v6 )
        goto LABEL_11;
    }
  }
  for ( i = 0; i < 20; ++i )
  {
    v9 = 5LL * i;
    if ( !v6[5 * i + 2] )
    {
      LODWORD(v6[5 * i + 1]) = GetCurrentThreadId();
      v6[v9 + 2] = (__int64)a2;
      v6[v9 + 3] = (__int64)a1;
      v6[v9 + 4] = (__int64)a3;
      ++*((_DWORD *)v6 + 200);
      break;
    }
  }
LABEL_11:
  std::_Mutex_base::unlock((std::_Mutex_base *)qword_140087A40);
}

```

## disassembly

```asm
0x14004e520  push    rbx
0x14004e522  push    rbp
0x14004e523  push    rsi
0x14004e524  push    rdi
0x14004e525  push    r14
0x14004e527  sub     rsp, 20h
0x14004e52b  mov     rsi, r8
0x14004e52e  mov     rbp, rdx
0x14004e531  mov     r14, rcx
0x14004e534  lea     rbx, qword_1400881E0
0x14004e53b  lea     rcx, qword_140087A40; this
0x14004e542  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14004e547  cmp     dword ptr [rbx+320h], 14h
0x14004e54e  jnz     short loc_14004E580
0x14004e550  lea     rdi, [rbx+328h]
0x14004e557  mov     rbx, [rdi]
0x14004e55a  test    rbx, rbx
0x14004e55d  jnz     short loc_14004E547
0x14004e55f  mov     edx, 330h; Size
0x14004e564  lea     ecx, [rbx+1]; Count
0x14004e567  call    cs:__imp_calloc
0x14004e56e  nop     dword ptr [rax+rax+00h]
0x14004e573  mov     rbx, rax
0x14004e576  mov     [rdi], rax
0x14004e579  test    rax, rax
0x14004e57c  jnz     short loc_14004E547
0x14004e57e  jmp     short loc_14004E5BF
0x14004e580  xor     ecx, ecx
0x14004e582  cmp     ecx, 14h
0x14004e585  jge     short loc_14004E5BF
0x14004e587  movsxd  rax, ecx
0x14004e58a  lea     rdi, [rax+rax*4]
0x14004e58e  cmp     qword ptr [rbx+rdi*8+10h], 0
0x14004e594  jz      short loc_14004E59A
0x14004e596  inc     ecx
0x14004e598  jmp     short loc_14004E582
0x14004e59a  call    cs:__imp_GetCurrentThreadId
0x14004e5a1  nop     dword ptr [rax+rax+00h]
0x14004e5a6  mov     [rbx+rdi*8+8], eax
0x14004e5aa  mov     [rbx+rdi*8+10h], rbp
0x14004e5af  mov     [rbx+rdi*8+18h], r14
0x14004e5b4  mov     [rbx+rdi*8+20h], rsi
0x14004e5b9  inc     dword ptr [rbx+320h]
0x14004e5bf  lea     rcx, qword_140087A40; this
0x14004e5c6  add     rsp, 20h
0x14004e5ca  pop     r14
0x14004e5cc  pop     rdi
0x14004e5cd  pop     rsi
0x14004e5ce  pop     rbp
0x14004e5cf  pop     rbx
0x14004e5d0  jmp     ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
```

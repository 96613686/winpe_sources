# _Cnd_register_at_thread_exit

- ea: `0x14004cb94`
- end: `0x14004cc3d`
- name: `_Cnd_register_at_thread_exit`
- size: `169`
- prototype: `void __cdecl(_Cnd_t, _Mtx_t, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140035930`

## callees

- `0x140006e8c`
- `0x1400198d0`
- `0x14004cb94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004cc08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004cc08`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x14004cbdb`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x14004cbdb`

## pseudocode

```c
void __cdecl Cnd_register_at_thread_exit(_Cnd_t a1, _Mtx_t a2, int *a3)
{
  __int64 *v6; // rbx
  __int64 **v7; // rdi
  int i; // ecx
  __int64 v9; // rdi

  v6 = qword_1400861F0;
  std::_Mutex_base::lock((std::_Mutex_base *)qword_140085A40);
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
  std::_Mutex_base::unlock((std::_Mutex_base *)qword_140085A40);
}

```

## disassembly

```asm
0x14004cb94  push    rbx
0x14004cb96  push    rbp
0x14004cb97  push    rsi
0x14004cb98  push    rdi
0x14004cb99  push    r14
0x14004cb9b  sub     rsp, 20h
0x14004cb9f  mov     rsi, r8
0x14004cba2  mov     rbp, rdx
0x14004cba5  mov     r14, rcx
0x14004cba8  lea     rbx, qword_1400861F0
0x14004cbaf  lea     rcx, qword_140085A40; this
0x14004cbb6  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14004cbbb  cmp     dword ptr [rbx+320h], 14h
0x14004cbc2  jnz     short loc_14004CBEE
0x14004cbc4  lea     rdi, [rbx+328h]
0x14004cbcb  mov     rbx, [rdi]
0x14004cbce  test    rbx, rbx
0x14004cbd1  jnz     short loc_14004CBBB
0x14004cbd3  mov     edx, 330h; Size
0x14004cbd8  lea     ecx, [rbx+1]; Count
0x14004cbdb  call    cs:__imp_calloc
0x14004cbe1  mov     rbx, rax
0x14004cbe4  mov     [rdi], rax
0x14004cbe7  test    rax, rax
0x14004cbea  jnz     short loc_14004CBBB
0x14004cbec  jmp     short loc_14004CC27
0x14004cbee  xor     ecx, ecx
0x14004cbf0  cmp     ecx, 14h
0x14004cbf3  jge     short loc_14004CC27
0x14004cbf5  movsxd  rax, ecx
0x14004cbf8  lea     rdi, [rax+rax*4]
0x14004cbfc  cmp     qword ptr [rbx+rdi*8+10h], 0
0x14004cc02  jz      short loc_14004CC08
0x14004cc04  inc     ecx
0x14004cc06  jmp     short loc_14004CBF0
0x14004cc08  call    cs:__imp_GetCurrentThreadId
0x14004cc0e  mov     [rbx+rdi*8+8], eax
0x14004cc12  mov     [rbx+rdi*8+10h], rbp
0x14004cc17  mov     [rbx+rdi*8+18h], r14
0x14004cc1c  mov     [rbx+rdi*8+20h], rsi
0x14004cc21  inc     dword ptr [rbx+320h]
0x14004cc27  lea     rcx, qword_140085A40; this
0x14004cc2e  add     rsp, 20h
0x14004cc32  pop     r14
0x14004cc34  pop     rdi
0x14004cc35  pop     rsi
0x14004cc36  pop     rbp
0x14004cc37  pop     rbx
0x14004cc38  jmp     ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
```

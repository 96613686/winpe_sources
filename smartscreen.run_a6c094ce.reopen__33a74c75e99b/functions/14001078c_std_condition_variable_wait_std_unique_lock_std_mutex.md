# std::condition_variable::wait(std::unique_lock<std::mutex> &)

- ea: `0x14001078c`
- end: `0x1400107d1`
- name: `?wait@condition_variable@std@@QEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z`
- size: `69`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140006ec8`
- `0x140010730`
- `0x14001a310`
- `0x140036cb4`
- `0x140037620`

## callees

- `0x14001078c`
- `0x14001c148`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1400107ab`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1400107ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400107b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400107b8`

## pseudocode

```c
DWORD __fastcall std::condition_variable::wait(struct _Cnd_internal_imp_t *a1, __int64 *a2, unsigned int a3)
{
  __int64 v3; // rbx
  DWORD result; // eax

  v3 = *a2;
  --*(_DWORD *)(v3 + 76);
  *(_DWORD *)(v3 + 72) = -1;
  if ( !_Primitive_wait_for(a1, (struct _Mtx_internal_imp_t *const)v3, a3) )
    abort();
  result = GetCurrentThreadId();
  ++*(_DWORD *)(v3 + 76);
  *(_DWORD *)(v3 + 72) = result;
  return result;
}

```

## disassembly

```asm
0x14001078c  push    rbx
0x14001078e  sub     rsp, 20h
0x140010792  mov     rbx, [rdx]
0x140010795  mov     rdx, rbx; struct _Mtx_internal_imp_t *
0x140010798  dec     dword ptr [rbx+4Ch]
0x14001079b  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x1400107a2  call    ?_Primitive_wait_for@@YA_NQEAU_Cnd_internal_imp_t@@QEAU_Mtx_internal_imp_t@@I@Z; _Primitive_wait_for(_Cnd_internal_imp_t * const,_Mtx_internal_imp_t * const,uint)
0x1400107a7  test    al, al
0x1400107a9  jnz     short loc_1400107B8
0x1400107ab  call    cs:__imp_abort
0x1400107b8  call    cs:__imp_GetCurrentThreadId
0x1400107bf  nop     dword ptr [rax+rax+00h]
0x1400107c4  inc     dword ptr [rbx+4Ch]
0x1400107c7  mov     [rbx+48h], eax
0x1400107ca  add     rsp, 20h
0x1400107ce  pop     rbx
0x1400107cf  retn
```

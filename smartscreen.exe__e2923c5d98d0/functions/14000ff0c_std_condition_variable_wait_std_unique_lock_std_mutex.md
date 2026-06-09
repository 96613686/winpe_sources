# std::condition_variable::wait(std::unique_lock<std::mutex> &)

- ea: `0x14000ff0c`
- end: `0x14000ff44`
- name: `?wait@condition_variable@std@@QEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z`
- size: `56`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140006b30`
- `0x14000feb0`
- `0x140019610`
- `0x140035764`
- `0x140036110`

## callees

- `0x14000ff0c`
- `0x14001b294`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x14000ff2b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x14000ff2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ff32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ff32`

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
0x14000ff0c  push    rbx
0x14000ff0e  sub     rsp, 20h
0x14000ff12  mov     rbx, [rdx]
0x14000ff15  mov     rdx, rbx; struct _Mtx_internal_imp_t *
0x14000ff18  dec     dword ptr [rbx+4Ch]
0x14000ff1b  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x14000ff22  call    ?_Primitive_wait_for@@YA_NQEAU_Cnd_internal_imp_t@@QEAU_Mtx_internal_imp_t@@I@Z; _Primitive_wait_for(_Cnd_internal_imp_t * const,_Mtx_internal_imp_t * const,uint)
0x14000ff27  test    al, al
0x14000ff29  jnz     short loc_14000FF32
0x14000ff2b  call    cs:__imp_abort
0x14000ff32  call    cs:__imp_GetCurrentThreadId
0x14000ff38  inc     dword ptr [rbx+4Ch]
0x14000ff3b  mov     [rbx+48h], eax
0x14000ff3e  add     rsp, 20h
0x14000ff42  pop     rbx
0x14000ff43  retn
```

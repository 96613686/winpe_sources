# UdfSeqCacheUpdateFileRefCount

- ea: `0x140009980`
- end: `0x140009a4f`
- name: `UdfSeqCacheUpdateFileRefCount`
- size: `207`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000cce0`
- `0x140019980`
- `0x14001a478`
- `0x14001aba0`

## callees

- `0x140009980`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400099c7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400099c7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140009a2d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140009a2d`

## pseudocode

```c
void __fastcall UdfSeqCacheUpdateFileRefCount(__int64 a1, char a2, _DWORD *a3)
{
  unsigned int v5; // ebx
  signed __int32 v6; // edi

  v5 = a2 != 0 ? 1 : -1;
  v6 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 376), v5);
  if ( a2 && !v6 )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL) + 1584LL));
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL) + 1640LL) = KeGetCurrentThread();
    ++*(_DWORD *)(a1 + 204);
    ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL) + 256LL);
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL) + 1640LL) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL) + 1584LL));
  }
  if ( a3 )
    *a3 = v5 + v6;
}

```

## disassembly

```asm
0x140009980  push    rbx
0x140009982  push    rsi
0x140009983  push    rdi
0x140009984  push    r14
0x140009986  sub     rsp, 28h
0x14000998a  mov     al, dl
0x14000998c  mov     r14, r8
0x14000998f  neg     al
0x140009991  mov     rsi, rcx
0x140009994  sbb     ebx, ebx
0x140009996  and     ebx, 2
0x140009999  dec     ebx
0x14000999b  mov     edi, ebx
0x14000999d  lock xadd [rcx+178h], edi
0x1400099a5  test    dl, dl
0x1400099a7  jz      loc_140009A39
0x1400099ad  test    edi, edi
0x1400099af  jnz     loc_140009A39
0x1400099b5  mov     rax, [rcx+88h]
0x1400099bc  mov     rcx, [rax+8]
0x1400099c0  add     rcx, 630h; FastMutex
0x1400099c7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400099ce  nop     dword ptr [rax+rax+00h]
0x1400099d3  mov     rdx, gs:188h
0x1400099dc  mov     rax, [rsi+88h]
0x1400099e3  mov     rcx, [rax+8]
0x1400099e7  mov     [rcx+668h], rdx
0x1400099ee  inc     dword ptr [rsi+0CCh]
0x1400099f4  mov     rax, [rsi+88h]
0x1400099fb  mov     rcx, [rax+8]
0x1400099ff  inc     dword ptr [rcx+100h]
0x140009a05  mov     rax, [rsi+88h]
0x140009a0c  mov     rcx, [rax+8]
0x140009a10  mov     qword ptr [rcx+668h], 0
0x140009a1b  mov     rax, [rsi+88h]
0x140009a22  mov     rcx, [rax+8]
0x140009a26  add     rcx, 630h; FastMutex
0x140009a2d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140009a34  nop     dword ptr [rax+rax+00h]
0x140009a39  test    r14, r14
0x140009a3c  jz      short loc_140009A44
0x140009a3e  lea     eax, [rbx+rdi]
0x140009a41  mov     [r14], eax
0x140009a44  add     rsp, 28h
0x140009a48  pop     r14
0x140009a4a  pop     rdi
0x140009a4b  pop     rsi
0x140009a4c  pop     rbx
0x140009a4d  retn
```

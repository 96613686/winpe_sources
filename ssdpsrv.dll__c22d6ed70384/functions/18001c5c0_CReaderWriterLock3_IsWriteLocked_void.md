# CReaderWriterLock3::IsWriteLocked(void)

- ea: `0x18001c5c0`
- end: `0x18001c5df`
- name: `?IsWriteLocked@CReaderWriterLock3@@QEBA_NXZ`
- size: `31`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001c440`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c5c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c5c9`

## pseudocode

```c
bool __fastcall CReaderWriterLock3::IsWriteLocked(CReaderWriterLock3 *this)
{
  int v1; // ebx

  v1 = *((_DWORD *)this + 1);
  return ((v1 ^ GetCurrentThreadId()) & 0xFFFFFFF) == 0;
}

```

## disassembly

```asm
0x18001c5c0  push    rbx
0x18001c5c2  sub     rsp, 20h
0x18001c5c6  mov     ebx, [rcx+4]
0x18001c5c9  call    cs:__imp_GetCurrentThreadId
0x18001c5cf  xor     eax, ebx
0x18001c5d1  test    eax, 0FFFFFFFh
0x18001c5d6  setz    al
0x18001c5d9  add     rsp, 20h
0x18001c5dd  pop     rbx
0x18001c5de  retn
```

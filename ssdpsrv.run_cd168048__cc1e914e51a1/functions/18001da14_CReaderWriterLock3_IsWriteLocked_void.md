# CReaderWriterLock3::IsWriteLocked(void)

- ea: `0x18001da14`
- end: `0x18001da3a`
- name: `?IsWriteLocked@CReaderWriterLock3@@QEBA_NXZ`
- size: `38`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001d89c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001da1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001da1d`

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
0x18001da14  push    rbx
0x18001da16  sub     rsp, 20h
0x18001da1a  mov     ebx, [rcx+4]
0x18001da1d  call    cs:__imp_GetCurrentThreadId
0x18001da24  nop     dword ptr [rax+rax+00h]
0x18001da29  xor     eax, ebx
0x18001da2b  test    eax, 0FFFFFFFh
0x18001da30  setz    al
0x18001da33  add     rsp, 20h
0x18001da37  pop     rbx
0x18001da38  retn
```

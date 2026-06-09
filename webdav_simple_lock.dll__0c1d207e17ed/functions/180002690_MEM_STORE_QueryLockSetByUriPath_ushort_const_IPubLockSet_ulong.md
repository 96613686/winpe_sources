# MEM_STORE::QueryLockSetByUriPath(ushort const *,IPubLockSet *,ulong)

- ea: `0x180002690`
- end: `0x1800026db`
- name: `?QueryLockSetByUriPath@MEM_STORE@@UEAAJPEBGPEAVIPubLockSet@@K@Z`
- size: `75`
- prototype: `__int64 __fastcall(MEM_STORE *__hidden this, wchar_t *String1, struct IPubLockSet *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002094`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800026c8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800026c8`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800026ab`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800026ab`

## pseudocode

```c
__int64 __fastcall MEM_STORE::QueryLockSetByUriPath(
        MEM_STORE *this,
        wchar_t *String1,
        struct IPubLockSet *a3,
        unsigned int a4)
{
  unsigned int v8; // ebx

  CReaderWriterLock3::WriteLock((MEM_STORE *)((char *)this + 88));
  v8 = MEM_STORE::BuildLockSetForUri(this, String1, a3, a4);
  CReaderWriterLock3::WriteUnlock((MEM_STORE *)((char *)this + 88));
  return v8;
}

```

## disassembly

```asm
0x180002690  push    rbx
0x180002692  push    rbp
0x180002693  push    rsi
0x180002694  push    rdi
0x180002695  push    r14
0x180002697  sub     rsp, 20h
0x18000269b  mov     rbp, rcx
0x18000269e  mov     ebx, r9d
0x1800026a1  add     rcx, 58h ; 'X'
0x1800026a5  mov     rdi, r8
0x1800026a8  mov     rsi, rdx
0x1800026ab  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800026b1  mov     r9d, ebx; unsigned int
0x1800026b4  mov     r8, rdi; struct IPubLockSet *
0x1800026b7  mov     rdx, rsi; String1
0x1800026ba  mov     rcx, rbp; this
0x1800026bd  call    ?BuildLockSetForUri@MEM_STORE@@AEAAJPEBGPEAVIPubLockSet@@K@Z; MEM_STORE::BuildLockSetForUri(ushort const *,IPubLockSet *,ulong)
0x1800026c2  lea     rcx, [rbp+58h]
0x1800026c6  mov     ebx, eax
0x1800026c8  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800026ce  mov     eax, ebx
0x1800026d0  add     rsp, 20h
0x1800026d4  pop     r14
0x1800026d6  pop     rdi
0x1800026d7  pop     rsi
0x1800026d8  pop     rbp
0x1800026d9  pop     rbx
0x1800026da  retn
```

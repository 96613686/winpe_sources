# CAutoWriterLock::Unlock(void)

- ea: `0x180006e20`
- end: `0x180006e48`
- name: `?Unlock@CAutoWriterLock@@QEAAXXZ`
- size: `40`
- prototype: `void __fastcall(CAutoWriterLock *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007700`
- `0x180008f9c`
- `0x180009490`
- `0x18000c69c`

## callees

- `0x180006e20`

## import_xrefs

- `WdsCommonLib!?WriterRelease@CMRSWLock@@QEAAXXZ` at `0x180006e36`
- `WdsCommonLib!?WriterRelease@CMRSWLock@@QEAAXXZ` at `0x180006e36`

## pseudocode

```c
void __fastcall CAutoWriterLock::Unlock(CAutoWriterLock *this)
{
  int v1; // eax
  int v2; // eax

  v1 = *((_DWORD *)this + 2);
  if ( v1 )
  {
    v2 = v1 - 1;
    *((_DWORD *)this + 2) = v2;
    if ( !v2 )
      CMRSWLock::WriterRelease(*(CMRSWLock **)this);
  }
}

```

## disassembly

```asm
0x180006e20  sub     rsp, 28h
0x180006e24  mov     eax, [rcx+8]
0x180006e27  test    eax, eax
0x180006e29  jz      short loc_180006E42
0x180006e2b  sub     eax, 1
0x180006e2e  mov     [rcx+8], eax
0x180006e31  jnz     short loc_180006E42
0x180006e33  mov     rcx, [rcx]
0x180006e36  call    cs:__imp_?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180006e3d  nop     dword ptr [rax+rax+00h]
0x180006e42  add     rsp, 28h
0x180006e46  retn
```

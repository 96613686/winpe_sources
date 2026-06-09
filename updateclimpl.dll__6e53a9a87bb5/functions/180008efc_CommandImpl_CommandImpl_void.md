# CommandImpl::~CommandImpl(void)

- ea: `0x180008efc`
- end: `0x180008f1f`
- name: `??1CommandImpl@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(CommandImpl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015a66`

## callees

- `0x180008efc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008f14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008f14`

## pseudocode

```c
void __fastcall CommandImpl::~CommandImpl(CommandImpl *this)
{
  void *v1; // rax

  v1 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v1 )
    LocalFree(v1);
}

```

## disassembly

```asm
0x180008efc  sub     rsp, 28h
0x180008f00  mov     rax, [rcx+8]
0x180008f04  mov     qword ptr [rcx+8], 0
0x180008f0c  test    rax, rax
0x180008f0f  jz      short loc_180008F1A
0x180008f11  mov     rcx, rax; hMem
0x180008f14  call    cs:__imp_LocalFree
0x180008f1a  add     rsp, 28h
0x180008f1e  retn
```

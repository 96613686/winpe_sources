# std::unique_ptr<TzautoupdateWorker,std::default_delete<TzautoupdateWorker>>::_Delete(void)

- ea: `0x18000acdc`
- end: `0x18000ad01`
- name: `?_Delete@?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@AEAAXXZ`
- size: `37`
- prototype: `void __fastcall(TzautoupdateWorker **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x1800094c0`
- `0x1800140a0`
- `0x1800144ac`
- `0x18001c7a0`

## callees

- `0x1800049c8`
- `0x18000acdc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000acf5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000acf5`

## pseudocode

```c
void __fastcall std::unique_ptr<TzautoupdateWorker>::_Delete(TzautoupdateWorker **a1)
{
  TzautoupdateWorker *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    TzautoupdateWorker::~TzautoupdateWorker(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000acdc  push    rbx
0x18000acde  sub     rsp, 20h
0x18000ace2  mov     rbx, [rcx]
0x18000ace5  test    rbx, rbx
0x18000ace8  jz      short loc_18000ACFB
0x18000acea  mov     rcx, rbx; this
0x18000aced  call    ??1TzautoupdateWorker@@QEAA@XZ; TzautoupdateWorker::~TzautoupdateWorker(void)
0x18000acf2  mov     rcx, rbx
0x18000acf5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000acfb  add     rsp, 20h
0x18000acff  pop     rbx
0x18000ad00  retn
```

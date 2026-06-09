# std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>::~unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>(void)

- ea: `0x180004990`
- end: `0x1800049b5`
- name: `??1?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@QEAA@XZ`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f95e`

## callees

- `0x180004990`
- `0x180004f20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800049a9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800049a9`

## pseudocode

```c
void __fastcall std::unique_ptr<ProcessWatcherDesc>::~unique_ptr<ProcessWatcherDesc>(
        ProcessWatcherDesc **a1,
        __int64 a2)
{
  ProcessWatcherDesc *v2; // rbx

  v2 = *a1;
  if ( *a1 )
  {
    ProcessWatcherDesc::~ProcessWatcherDesc(*a1, a2);
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x180004990  push    rbx
0x180004992  sub     rsp, 20h
0x180004996  mov     rbx, [rcx]
0x180004999  test    rbx, rbx
0x18000499c  jz      short loc_1800049AF
0x18000499e  mov     rcx, rbx; this
0x1800049a1  call    ??1ProcessWatcherDesc@@QEAA@XZ; ProcessWatcherDesc::~ProcessWatcherDesc(void)
0x1800049a6  mov     rcx, rbx
0x1800049a9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800049af  add     rsp, 20h
0x1800049b3  pop     rbx
0x1800049b4  retn
```

# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x18000570c`
- end: `0x18000572c`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800077d0`

## callees

- `0x18000570c`
- `0x1800065bc`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rax

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    wil::details::FreeProcessHeap(v2, a2);
}

```

## disassembly

```asm
0x18000570c  sub     rsp, 28h
0x180005710  mov     rax, [rcx]
0x180005713  mov     qword ptr [rcx], 0
0x18000571a  test    rax, rax
0x18000571d  jz      short loc_180005727
0x18000571f  mov     rcx, rax; this
0x180005722  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180005727  add     rsp, 28h
0x18000572b  retn
```

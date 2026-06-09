# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x1800153e8`
- end: `0x180015408`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015fd8`

## callees

- `0x1800153e8`
- `0x18001578c`

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
0x1800153e8  sub     rsp, 28h
0x1800153ec  mov     rax, [rcx]
0x1800153ef  mov     qword ptr [rcx], 0
0x1800153f6  test    rax, rax
0x1800153f9  jz      short loc_180015403
0x1800153fb  mov     rcx, rax; this
0x1800153fe  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180015403  add     rsp, 28h
0x180015407  retn
```

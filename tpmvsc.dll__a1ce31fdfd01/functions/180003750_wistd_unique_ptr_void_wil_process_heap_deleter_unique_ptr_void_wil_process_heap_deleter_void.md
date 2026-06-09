# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180003750`
- end: `0x180003770`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b24`

## callees

- `0x180003750`
- `0x180003c50`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    I_InternalFree(v1);
}

```

## disassembly

```asm
0x180003750  sub     rsp, 28h
0x180003754  mov     rax, [rcx]
0x180003757  mov     qword ptr [rcx], 0
0x18000375e  test    rax, rax
0x180003761  jz      short loc_18000376B
0x180003763  mov     rcx, rax; void *
0x180003766  call    ?I_InternalFree@@YAXPEAX@Z; I_InternalFree(void *)
0x18000376b  add     rsp, 28h
0x18000376f  retn
```

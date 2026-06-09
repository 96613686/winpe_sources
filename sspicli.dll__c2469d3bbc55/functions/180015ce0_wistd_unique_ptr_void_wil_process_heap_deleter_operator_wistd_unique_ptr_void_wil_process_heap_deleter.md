# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180015ce0`
- end: `0x180015d0c`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180015c60`
- `0x18001600c`

## callees

- `0x180015ce0`
- `0x180015fe0`

## pseudocode

```c
void **__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(void **a1, void **a2)
{
  void *v2; // rax
  void *v4; // rcx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    operator delete(v4);
  return a1;
}

```

## disassembly

```asm
0x180015ce0  push    rbx
0x180015ce2  sub     rsp, 20h
0x180015ce6  mov     rax, [rdx]
0x180015ce9  mov     rbx, rcx
0x180015cec  mov     qword ptr [rdx], 0
0x180015cf3  mov     rcx, [rcx]; void *
0x180015cf6  mov     [rbx], rax
0x180015cf9  test    rcx, rcx
0x180015cfc  jz      short loc_180015D03
0x180015cfe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015d03  mov     rax, rbx
0x180015d06  add     rsp, 20h
0x180015d0a  pop     rbx
0x180015d0b  retn
```

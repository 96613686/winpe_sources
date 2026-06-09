# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180007e50`
- end: `0x180007e7c`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a6c0`
- `0x18000b46c`

## callees

- `0x180007e50`
- `0x18000882c`

## pseudocode

```c
wil::details **__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(
        wil::details **a1,
        wil::details **a2)
{
  wil::details *v2; // rax
  wil::details *v4; // rcx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    wil::details::FreeProcessHeap(v4, a2);
  return a1;
}

```

## disassembly

```asm
0x180007e50  push    rbx
0x180007e52  sub     rsp, 20h
0x180007e56  mov     rax, [rdx]
0x180007e59  mov     rbx, rcx
0x180007e5c  mov     qword ptr [rdx], 0
0x180007e63  mov     rcx, [rcx]; this
0x180007e66  mov     [rbx], rax
0x180007e69  test    rcx, rcx
0x180007e6c  jz      short loc_180007E73
0x180007e6e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007e73  mov     rax, rbx
0x180007e76  add     rsp, 20h
0x180007e7a  pop     rbx
0x180007e7b  retn
```

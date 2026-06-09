# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180003e70`
- end: `0x180003e9c`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039fc`
- `0x180003dcc`

## callees

- `0x180003e70`
- `0x1800043e4`

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
0x180003e70  push    rbx
0x180003e72  sub     rsp, 20h
0x180003e76  mov     rax, [rdx]
0x180003e79  mov     rbx, rcx
0x180003e7c  mov     qword ptr [rdx], 0
0x180003e83  mov     rcx, [rcx]; this
0x180003e86  mov     [rbx], rax
0x180003e89  test    rcx, rcx
0x180003e8c  jz      short loc_180003E93
0x180003e8e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180003e93  mov     rax, rbx
0x180003e96  add     rsp, 20h
0x180003e9a  pop     rbx
0x180003e9b  retn
```

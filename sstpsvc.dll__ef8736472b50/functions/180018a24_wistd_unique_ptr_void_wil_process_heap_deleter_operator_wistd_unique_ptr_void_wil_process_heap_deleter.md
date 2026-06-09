# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180018a24`
- end: `0x180018a51`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001832c`
- `0x18001b168`

## callees

- `0x180018a24`
- `0x180019424`

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
0x180018a24  push    rbx
0x180018a26  sub     rsp, 20h
0x180018a2a  mov     rax, [rdx]
0x180018a2d  mov     rbx, rcx
0x180018a30  mov     qword ptr [rdx], 0
0x180018a37  mov     rcx, [rcx]; this
0x180018a3a  mov     [rbx], rax
0x180018a3d  test    rcx, rcx
0x180018a40  jz      short loc_180018A47
0x180018a42  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180018a47  mov     rax, rbx
0x180018a4a  add     rsp, 20h
0x180018a4e  pop     rbx
0x180018a4f  retn
```

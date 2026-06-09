# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180004a98`
- end: `0x180004ac4`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d44`
- `0x180009398`

## callees

- `0x180004a98`
- `0x18000576c`

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
0x180004a98  push    rbx
0x180004a9a  sub     rsp, 20h
0x180004a9e  mov     rax, [rdx]
0x180004aa1  mov     rbx, rcx
0x180004aa4  mov     qword ptr [rdx], 0
0x180004aab  mov     rcx, [rcx]; this
0x180004aae  mov     [rbx], rax
0x180004ab1  test    rcx, rcx
0x180004ab4  jz      short loc_180004ABB
0x180004ab6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004abb  mov     rax, rbx
0x180004abe  add     rsp, 20h
0x180004ac2  pop     rbx
0x180004ac3  retn
```

# WString::BindPtr(ushort *)

- ea: `0x180011af0`
- end: `0x180011b17`
- name: `?BindPtr@WString@@QEAAXPEAG@Z`
- size: `39`
- prototype: `void __fastcall(WString *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x180011b03`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x180011b03`

## pseudocode

```c
void __fastcall WString::BindPtr(WString *this, unsigned __int16 *a2)
{
  WString::DeleteString(this, *(unsigned __int16 **)this);
  *(_QWORD *)this = a2;
}

```

## disassembly

```asm
0x180011af0  mov     [rsp+arg_0], rbx
0x180011af5  push    rdi
0x180011af6  sub     rsp, 20h
0x180011afa  mov     rdi, rdx
0x180011afd  mov     rbx, rcx
0x180011b00  mov     rdx, [rcx]
0x180011b03  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x180011b09  mov     [rbx], rdi
0x180011b0c  mov     rbx, [rsp+28h+arg_0]
0x180011b11  add     rsp, 20h
0x180011b15  pop     rdi
0x180011b16  retn
```

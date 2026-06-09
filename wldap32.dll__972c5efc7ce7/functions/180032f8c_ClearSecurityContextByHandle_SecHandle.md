# ClearSecurityContextByHandle(_SecHandle *)

- ea: `0x180032f8c`
- end: `0x180032fd1`
- name: `?ClearSecurityContextByHandle@@YAXPEAU_SecHandle@@@Z`
- size: `69`
- prototype: `void __fastcall(struct _SecHandle *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017854`

## callees

- `0x180032f8c`
- `0x18004d010`

## pseudocode

```c
void __fastcall ClearSecurityContextByHandle(struct _SecHandle *a1)
{
  if ( a1->dwLower != -1 || a1->dwUpper != -1 )
  {
    ((void (*)(void))SspiFunctionTableW->DeleteSecurityContext)();
    a1->dwLower = -1;
    a1->dwUpper = -1;
  }
}

```

## disassembly

```asm
0x180032f8c  mov     [rsp+arg_0], rbx
0x180032f91  push    rdi
0x180032f92  sub     rsp, 20h
0x180032f96  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180032f9a  mov     rdi, rcx
0x180032f9d  jnz     short loc_180032FA6
0x180032f9f  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180032fa4  jz      short loc_180032FC5
0x180032fa6  mov     rax, cs:SspiFunctionTableW
0x180032fad  mov     rax, [rax+48h]
0x180032fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fb6  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180032fbd  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x180032fc5  mov     rbx, [rsp+28h+arg_0]
0x180032fca  add     rsp, 20h
0x180032fce  pop     rdi
0x180032fcf  retn
```

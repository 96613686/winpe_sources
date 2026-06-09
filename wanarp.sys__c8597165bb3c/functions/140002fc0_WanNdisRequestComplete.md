# WanNdisRequestComplete

- ea: `0x140002fc0`
- end: `0x14000300d`
- name: `WanNdisRequestComplete`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002fc0`
- `0x1400050f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002fdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002fdb`

## pseudocode

```c
void __fastcall WanNdisRequestComplete(__int64 a1, void (__fastcall **a2)(_QWORD))
{
  if ( a2[31] )
    a2[31](a1);
  else
    ExFreePoolWithTag(a2, 0);
}

```

## disassembly

```asm
0x140002fc0  sub     rsp, 28h
0x140002fc4  mov     r9, [rdx+0F8h]
0x140002fcb  mov     rax, rdx
0x140002fce  mov     r10, rcx
0x140002fd1  test    r9, r9
0x140002fd4  jnz     short loc_140002FE9
0x140002fd6  xor     edx, edx; Tag
0x140002fd8  mov     rcx, rax; P
0x140002fdb  call    cs:__imp_ExFreePoolWithTag
0x140002fe2  nop     dword ptr [rax+rax+00h]
0x140002fe7  jmp     short loc_140003007
0x140002fe9  cmp     dword ptr [rdx+4], 1
0x140002fed  jnz     short loc_140002FFC
0x140002fef  xor     ecx, ecx
0x140002ff1  cmp     dword ptr [rdx+20h], 10119h
0x140002ff8  cmovz   r8d, ecx
0x140002ffc  mov     rcx, r10
0x140002fff  mov     rax, r9
0x140003002  call    _guard_dispatch_icall
0x140003007  add     rsp, 28h
0x14000300b  retn
```

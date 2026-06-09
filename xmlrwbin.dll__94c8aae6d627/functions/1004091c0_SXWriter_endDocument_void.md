# SXWriter::endDocument(void)

- ea: `0x1004091c0`
- end: `0x1004091df`
- name: `?endDocument@SXWriter@@UEAAJXZ`
- size: `31`
- prototype: `__int64 __fastcall(SXWriter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1004087e0`
- `0x1004091c0`
- `0x100414090`

## pseudocode

```c
__int64 __fastcall SXWriter::endDocument(SXWriter *this)
{
  SXWriter::commitStream((SXWriter *)((char *)this - 64));
  return 0;
}

```

## disassembly

```asm
0x1004091c0  push    rbx
0x1004091c2  sub     rsp, 40h
0x1004091c6  xor     ebx, ebx
0x1004091c8  add     rcx, 0FFFFFFFFFFFFFFC0h; this
0x1004091cc  call    ?commitStream@SXWriter@@IEAAXXZ; SXWriter::commitStream(void)
0x1004091d1  jmp     short loc_1004091D7
0x1004091d3  mov     ebx, [rsp+48h+var_28]
0x1004091d7  mov     eax, ebx
0x1004091d9  add     rsp, 40h
0x1004091dd  pop     rbx
0x1004091de  retn
0x100424620  push    rbp
0x100424622  sub     rsp, 20h
0x100424626  mov     rbp, rdx
0x100424629  mov     [rbp+38h], rcx
0x10042462d  mov     [rbp+30h], rcx
0x100424631  mov     rax, [rbp+30h]
0x100424635  mov     rcx, [rax]
0x100424638  mov     [rbp+28h], rcx
0x10042463c  mov     rax, [rbp+28h]
0x100424640  mov     eax, [rax]
0x100424642  cmp     eax, 0C0000005h
0x100424647  jz      short loc_100424679
0x100424649  add     eax, 1FFFFFFFh
0x10042464e  cmp     eax, 1
0x100424651  ja      short loc_100424669
0x100424653  mov     rax, [rbp+28h]
0x100424657  cmp     dword ptr [rax+18h], 1
0x10042465b  jnz     short loc_100424669
0x10042465d  mov     rax, [rbp+28h]
0x100424661  mov     ecx, [rax+20h]
0x100424664  mov     [rbp+20h], ecx
0x100424667  jmp     short loc_100424670
0x100424669  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424670  mov     dword ptr [rbp+24h], 1
0x100424677  jmp     short loc_100424680
0x100424679  mov     dword ptr [rbp+24h], 0
0x100424680  mov     eax, [rbp+24h]
0x100424683  add     rsp, 20h
0x100424687  pop     rbp
0x100424688  retn
```

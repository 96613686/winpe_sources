# SXWriter::endCurrentElement(void)

- ea: `0x10040a9e0`
- end: `0x10040aa15`
- name: `?endCurrentElement@SXWriter@@UEAAJXZ`
- size: `53`
- prototype: `__int64 __fastcall(SXWriter *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100409740`
- `0x10040a9e0`
- `0x10040adb0`
- `0x100414090`

## pseudocode

```c
__int64 __fastcall SXWriter::endCurrentElement(SXWriter *this)
{
  SXWriter *v1; // rbx

  v1 = (SXWriter *)((char *)this - 64);
  SXWriter::endAttributesCheck((SXWriter *)((char *)this - 64));
  SXWriter::WriteByte(v1, 247);
  return 0;
}

```

## disassembly

```asm
0x10040a9e0  mov     [rsp+arg_0], rbx
0x10040a9e5  push    rdi
0x10040a9e6  sub     rsp, 40h
0x10040a9ea  xor     edi, edi
0x10040a9ec  lea     rbx, [rcx-40h]
0x10040a9f0  mov     rcx, rbx; this
0x10040a9f3  call    ?endAttributesCheck@SXWriter@@AEAAXXZ; SXWriter::endAttributesCheck(void)
0x10040a9f8  mov     dl, 0F7h; unsigned __int8
0x10040a9fa  mov     rcx, rbx; this
0x10040a9fd  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x10040aa02  jmp     short loc_10040AA08
0x10040aa04  mov     edi, [rsp+48h+var_28]
0x10040aa08  mov     eax, edi
0x10040aa0a  mov     rbx, [rsp+48h+arg_0]
0x10040aa0f  add     rsp, 40h
0x10040aa13  pop     rdi
0x10040aa14  retn
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

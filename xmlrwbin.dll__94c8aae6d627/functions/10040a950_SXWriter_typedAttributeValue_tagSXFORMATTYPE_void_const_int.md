# SXWriter::typedAttributeValue(tagSXFORMATTYPE,void const *,int)

- ea: `0x10040a950`
- end: `0x10040a96f`
- name: `?typedAttributeValue@SXWriter@@UEAAJW4tagSXFORMATTYPE@@PEBXH@Z`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1004093d0`
- `0x10040a950`
- `0x100414090`

## pseudocode

```c
__int64 __fastcall SXWriter::typedAttributeValue(__int64 a1, int a2, unsigned __int64 *a3, int a4)
{
  SXWriter::WriteTypedData(a1 - 64, a2, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x10040a950  push    rbx
0x10040a952  sub     rsp, 40h
0x10040a956  xor     ebx, ebx
0x10040a958  add     rcx, 0FFFFFFFFFFFFFFC0h
0x10040a95c  call    ?WriteTypedData@SXWriter@@AEAAXW4tagSXFORMATTYPE@@PEBXH@Z; SXWriter::WriteTypedData(tagSXFORMATTYPE,void const *,int)
0x10040a961  jmp     short loc_10040A967
0x10040a963  mov     ebx, [rsp+48h+var_28]
0x10040a967  mov     eax, ebx
0x10040a969  add     rsp, 40h
0x10040a96d  pop     rbx
0x10040a96e  retn
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

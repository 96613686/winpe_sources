# UdfFullCompareNames

- ea: `0x140054780`
- end: `0x140054823`
- name: `UdfFullCompareNames`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140040820`

## callees

- `0x140054780`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400547c5`
- `ntoskrnl!RtlCompareMemory` at `0x1400547c5`

## pseudocode

```c
__int64 __fastcall UdfFullCompareNames(__int64 a1, const void **a2, const void **a3)
{
  unsigned int v5; // esi
  unsigned int v6; // ebp
  unsigned int v7; // r14d
  unsigned int v8; // eax

  v5 = -1;
  if ( *(_WORD *)a2 <= *(_WORD *)a3 )
  {
    v7 = -1;
    v6 = *(unsigned __int16 *)a2;
    if ( *(_WORD *)a2 == *(_WORD *)a3 )
      v7 = 0;
  }
  else
  {
    v6 = *(unsigned __int16 *)a3;
    v7 = 1;
  }
  v8 = RtlCompareMemory(a2[1], a3[1], v6);
  if ( v8 >= v6 )
    return v7;
  if ( *((_WORD *)a2[1] + ((unsigned __int64)v8 >> 1)) >= *((_WORD *)a3[1] + ((unsigned __int64)v8 >> 1)) )
    return 1;
  return v5;
}

```

## disassembly

```asm
0x140054780  mov     [rsp+arg_8], rbx
0x140054785  mov     [rsp+arg_10], rsi
0x14005478a  push    rdi
0x14005478b  push    r14
0x14005478d  push    r15
0x14005478f  sub     rsp, 20h
0x140054793  movzx   ecx, word ptr [rdx]
0x140054796  mov     rdi, r8
0x140054799  movzx   eax, word ptr [r8]
0x14005479d  mov     rbx, rdx
0x1400547a0  mov     [rsp+38h+arg_0], rbp
0x1400547a5  mov     esi, 0FFFFFFFFh
0x1400547aa  mov     r15d, 1
0x1400547b0  cmp     cx, ax
0x1400547b3  jbe     short loc_14005480E
0x1400547b5  mov     ebp, eax
0x1400547b7  mov     r14d, r15d
0x1400547ba  mov     rdx, [rdi+8]; Source2
0x1400547be  mov     rcx, [rbx+8]; Source1
0x1400547c2  mov     r8d, ebp; Length
0x1400547c5  call    cs:__imp_RtlCompareMemory
0x1400547cc  nop     dword ptr [rax+rax+00h]
0x1400547d1  cmp     eax, ebp
0x1400547d3  mov     rbp, [rsp+38h+arg_0]
0x1400547d8  jnb     short loc_14005481E
0x1400547da  mov     rcx, [rbx+8]
0x1400547de  mov     eax, eax
0x1400547e0  shr     rax, 1
0x1400547e3  lea     rdx, [rax+rax]
0x1400547e7  mov     rax, [rdi+8]
0x1400547eb  movzx   eax, word ptr [rdx+rax]
0x1400547ef  cmp     [rdx+rcx], ax
0x1400547f3  cmovnb  esi, r15d
0x1400547f7  mov     eax, esi
0x1400547f9  mov     rbx, [rsp+38h+arg_8]
0x1400547fe  mov     rsi, [rsp+38h+arg_10]
0x140054803  add     rsp, 20h
0x140054807  pop     r15
0x140054809  pop     r14
0x14005480b  pop     rdi
0x14005480c  retn
0x14005480e  xor     edx, edx
0x140054810  mov     r14d, esi
0x140054813  cmp     cx, ax
0x140054816  mov     ebp, ecx
0x140054818  cmovz   r14d, edx
0x14005481c  jmp     short loc_1400547BA
0x14005481e  mov     eax, r14d
0x140054821  jmp     short loc_1400547F9
```

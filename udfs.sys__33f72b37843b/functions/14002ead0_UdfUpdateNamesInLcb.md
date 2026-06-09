# UdfUpdateNamesInLcb

- ea: `0x14002ead0`
- end: `0x14002eb94`
- name: `UdfUpdateNamesInLcb`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140038194`
- `0x140050a8c`

## callees

- `0x14001bd80`
- `0x14002ead0`

## pseudocode

```c
void *__fastcall UdfUpdateNamesInLcb(__int64 a1, __int64 a2, const void **a3, const void **a4, const void **a5)
{
  __int16 v5; // ax
  void *v6; // rcx
  __int16 v9; // ax
  void *v10; // rcx
  void *v11; // rcx
  void *result; // rax

  v5 = *(_WORD *)a3;
  v6 = *(void **)(a2 + 224);
  *(_WORD *)(a2 + 130) = *(_WORD *)a3;
  *(_WORD *)(a2 + 128) = v5;
  *(_QWORD *)(a2 + 136) = v6;
  memmove(v6, a3[1], *(unsigned __int16 *)a3);
  v9 = *(_WORD *)a4;
  v10 = (void *)(*(_QWORD *)(a2 + 224) + *(unsigned __int16 *)(a2 + 128));
  *(_QWORD *)(a2 + 176) = v10;
  *(_WORD *)(a2 + 170) = v9;
  *(_WORD *)(a2 + 168) = v9;
  memmove(v10, a4[1], *(unsigned __int16 *)a4);
  v11 = (void *)(*(_QWORD *)(a2 + 176) + *(unsigned __int16 *)(a2 + 168));
  *(_WORD *)(a2 + 208) = *(_WORD *)a5;
  *(_WORD *)(a2 + 210) = 24;
  *(_QWORD *)(a2 + 216) = v11;
  result = (void *)*(unsigned __int16 *)a5;
  if ( (_WORD)result )
    return memmove(v11, a5[1], *(unsigned __int16 *)a5);
  return result;
}

```

## disassembly

```asm
0x14002ead0  mov     [rsp+arg_0], rbx
0x14002ead5  push    rdi
0x14002ead6  sub     rsp, 20h
0x14002eada  movzx   eax, word ptr [r8]
0x14002eade  mov     r10, r8
0x14002eae1  mov     rcx, [rdx+0E0h]; void *
0x14002eae8  mov     rdi, rdx
0x14002eaeb  mov     [rdx+82h], ax
0x14002eaf2  mov     rbx, r9
0x14002eaf5  mov     [rdx+80h], ax
0x14002eafc  mov     [rdx+88h], rcx
0x14002eb03  mov     rdx, [r10+8]; Src
0x14002eb07  movzx   r8d, word ptr [r8]; Size
0x14002eb0b  call    memmove
0x14002eb10  movzx   eax, word ptr [rbx]
0x14002eb13  movzx   ecx, word ptr [rdi+80h]
0x14002eb1a  add     rcx, [rdi+0E0h]; void *
0x14002eb21  mov     [rdi+0B0h], rcx
0x14002eb28  mov     [rdi+0AAh], ax
0x14002eb2f  mov     [rdi+0A8h], ax
0x14002eb36  movzx   r8d, word ptr [rbx]; Size
0x14002eb3a  mov     rdx, [rbx+8]; Src
0x14002eb3e  call    memmove
0x14002eb43  mov     rdx, [rsp+28h+arg_20]
0x14002eb48  xor     r8d, r8d
0x14002eb4b  movzx   ecx, word ptr [rdi+0A8h]
0x14002eb52  add     rcx, [rdi+0B0h]; void *
0x14002eb59  movzx   eax, word ptr [rdx]
0x14002eb5c  mov     [rdi+0D0h], ax
0x14002eb63  mov     word ptr [rdi+0D2h], 18h
0x14002eb6c  mov     [rdi+0D8h], rcx
0x14002eb73  movzx   eax, word ptr [rdx]
0x14002eb76  cmp     r8w, ax
0x14002eb7a  jz      short loc_14002EB88
0x14002eb7c  mov     rdx, [rdx+8]; Src
0x14002eb80  mov     r8d, eax; Size
0x14002eb83  call    memmove
0x14002eb88  mov     rbx, [rsp+28h+arg_0]
0x14002eb8d  add     rsp, 20h
0x14002eb91  pop     rdi
0x14002eb92  retn
```

# DeleteOutInterfaceRefs

- ea: `0x18001ba30`
- end: `0x18001bb22`
- name: `DeleteOutInterfaceRefs`
- size: `242`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180014580`
- `0x18001bce0`
- `0x18001be6c`

## callees

- `0x18001ba30`
- `0x18001d378`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001bae4`
- `KERNEL32!HeapFree` at `0x18001bae4`

## pseudocode

```c
void __fastcall DeleteOutInterfaceRefs(__int64 a1, __int64 a2, int a3)
{
  _WORD *v3; // rsi
  _WORD *v5; // rbx
  __int64 v8; // rdi
  _QWORD *v9; // rax

  v3 = (_WORD *)(a2 + 40);
  v5 = *(_WORD **)(a2 + 40);
  if ( v5 != (_WORD *)(a2 + 40) )
  {
    do
    {
      if ( a3 )
      {
        if ( (__int16)v5[16] < 0 )
          goto LABEL_4;
      }
      else if ( (v5[16] & 0x4000) != 0 )
      {
LABEL_4:
        DeleteInterfaceFromSourceEntry(
          a1,
          *((_DWORD *)v5 + 4),
          *((_DWORD *)v5 + 5),
          *((_DWORD *)v5 + 6),
          *((_DWORD *)v5 + 7),
          *(_DWORD *)(a2 + 16),
          *(_DWORD *)(a2 + 20),
          a3);
        v5[16] &= a3 != 0 ? 0x7FFF : -16385;
        v8 = *(_QWORD *)v5;
        if ( (v5[16] & 0xC000) == 0 )
        {
          if ( *(_WORD **)(v8 + 8) != v5 || (v9 = (_QWORD *)*((_QWORD *)v5 + 1), (_WORD *)*v9 != v5) )
            __fastfail(3u);
          *v9 = v8;
          *(_QWORD *)(v8 + 8) = v9;
          HeapFree(hHeap, 0, v5);
        }
        v5 = (_WORD *)v8;
        continue;
      }
      v5 = *(_WORD **)v5;
    }
    while ( v5 != v3 );
  }
}

```

## disassembly

```asm
0x18001ba30  push    rbx
0x18001ba32  push    rbp
0x18001ba33  push    rsi
0x18001ba34  push    rdi
0x18001ba35  push    r12
0x18001ba37  push    r13
0x18001ba39  push    r14
0x18001ba3b  push    r15
0x18001ba3d  sub     rsp, 48h
0x18001ba41  lea     rsi, [rdx+28h]
0x18001ba45  mov     ebp, r8d
0x18001ba48  mov     rbx, [rsi]
0x18001ba4b  mov     r14, rdx
0x18001ba4e  mov     r15, rcx
0x18001ba51  cmp     rbx, rsi
0x18001ba54  jz      loc_18001BAF6
0x18001ba5a  xor     r12d, r12d
0x18001ba5d  mov     r13d, 0C000h
0x18001ba63  test    ebp, ebp
0x18001ba65  jz      loc_18001BB07
0x18001ba6b  cmp     [rbx+20h], r12w
0x18001ba70  jge     loc_18001BB16
0x18001ba76  mov     eax, [r14+14h]
0x18001ba7a  mov     rcx, r15
0x18001ba7d  mov     r9d, [rbx+18h]
0x18001ba81  mov     r8d, [rbx+14h]
0x18001ba85  mov     edx, [rbx+10h]
0x18001ba88  mov     [rsp+88h+var_50], ebp
0x18001ba8c  mov     [rsp+88h+var_58], eax
0x18001ba90  mov     eax, [r14+10h]
0x18001ba94  mov     [rsp+88h+var_60], eax
0x18001ba98  mov     eax, [rbx+1Ch]
0x18001ba9b  mov     [rsp+88h+var_68], eax
0x18001ba9f  call    DeleteInterfaceFromSourceEntry
0x18001baa4  mov     eax, ebp
0x18001baa6  neg     eax
0x18001baa8  sbb     cx, cx
0x18001baab  and     cx, r13w
0x18001baaf  add     cx, 0BFFFh
0x18001bab4  and     [rbx+20h], cx
0x18001bab8  mov     rdi, [rbx]
0x18001babb  test    [rbx+20h], r13w
0x18001bac0  jnz     short loc_18001BAEA
0x18001bac2  cmp     [rdi+8], rbx
0x18001bac6  jnz     short loc_18001BB1B
0x18001bac8  mov     rax, [rbx+8]
0x18001bacc  cmp     [rax], rbx
0x18001bacf  jnz     short loc_18001BB1B
0x18001bad1  mov     [rax], rdi
0x18001bad4  mov     r8, rbx; lpMem
0x18001bad7  mov     [rdi+8], rax
0x18001badb  xor     edx, edx; dwFlags
0x18001badd  mov     rcx, cs:hHeap; hHeap
0x18001bae4  call    cs:__imp_HeapFree
0x18001baea  mov     rbx, rdi
0x18001baed  cmp     rbx, rsi
0x18001baf0  jnz     loc_18001BA63
0x18001baf6  add     rsp, 48h
0x18001bafa  pop     r15
0x18001bafc  pop     r14
0x18001bafe  pop     r13
0x18001bb00  pop     r12
0x18001bb02  pop     rdi
0x18001bb03  pop     rsi
0x18001bb04  pop     rbp
0x18001bb05  pop     rbx
0x18001bb06  retn
0x18001bb07  mov     eax, 4000h
0x18001bb0c  test    [rbx+20h], ax
0x18001bb10  jnz     loc_18001BA76
0x18001bb16  mov     rbx, [rbx]
0x18001bb19  jmp     short loc_18001BAED
0x18001bb1b  mov     ecx, 3
0x18001bb20  int     29h; Win8: RtlFailFast(ecx)
```

# SdbpMergeCompareEntriesSort

- ea: `0x14001c530`
- end: `0x14001c631`
- name: `SdbpMergeCompareEntriesSort`
- size: `257`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001f94`
- `0x14001c530`
- `0x14002e3d6`

## pseudocode

```c
unsigned int __fastcall SdbpMergeCompareEntriesSort(_WORD *a1, _QWORD *a2)
{
  int v2; // eax
  int v4; // edx
  int v6; // ecx
  unsigned int result; // eax
  unsigned __int64 v8; // rcx
  const void *v9; // rdx
  const void *v10; // rcx
  unsigned int v11; // esi
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned __int16 *v15; // rax
  __int64 v16; // rdx
  unsigned __int16 v17; // cx

  LOWORD(v2) = a1[6];
  v4 = *((unsigned __int16 *)a2 + 6);
  if ( (_WORD)v2 != (_WORD)v4 )
  {
    v6 = -1000;
    v2 = (unsigned __int16)v2;
    if ( (_WORD)v2 == 28683 )
      v2 = -1000;
    if ( (_WORD)v4 != 28683 )
      v6 = v4;
    return v2 - v6;
  }
  LOWORD(v2) = a1[7];
  v6 = *((unsigned __int16 *)a2 + 7);
  if ( (_WORD)v6 != (_WORD)v2 )
  {
    v2 = (unsigned __int16)v2;
    return v2 - v6;
  }
  v8 = *((_QWORD *)a1 + 4);
  if ( a2[4] != v8 )
    return a2[4] < v8 ? 1 : -1;
  v9 = (const void *)a2[5];
  v10 = (const void *)*((_QWORD *)a1 + 5);
  if ( !v9 )
    return -(v10 != 0);
  if ( !v10 )
    return 1;
  if ( (((v2 & 0xF000) - 24576) & 0xFFFFDFFF) != 0 )
  {
    v11 = *((_DWORD *)a2 + 12);
    v12 = v11;
    v13 = *((_DWORD *)a1 + 12);
    if ( v13 <= v11 )
      v12 = *((_DWORD *)a1 + 12);
    if ( v12 )
    {
      result = memcmp_0(v10, v9, v12);
      v14 = v13 - v11;
      if ( !result )
        return v14;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    result = wcsicmp_0((const wchar_t *)v10, (const wchar_t *)v9);
    if ( !result )
    {
      v15 = (unsigned __int16 *)*((_QWORD *)a1 + 5);
      v16 = a2[5] - (_QWORD)v15;
      while ( 1 )
      {
        v17 = *v15;
        if ( *v15 != *(unsigned __int16 *)((char *)v15 + v16) )
          break;
        ++v15;
        if ( !v17 )
          return 0;
      }
      return v17 < *(unsigned __int16 *)((char *)v15 + v16) ? -1 : 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001c530  mov     [rsp+arg_0], rbx
0x14001c535  mov     [rsp+arg_8], rsi
0x14001c53a  push    rdi
0x14001c53b  sub     rsp, 20h
0x14001c53f  movzx   eax, word ptr [rcx+0Ch]
0x14001c543  mov     rbx, rdx
0x14001c546  movzx   edx, word ptr [rdx+0Ch]
0x14001c54a  mov     rdi, rcx
0x14001c54d  cmp     ax, dx
0x14001c550  jz      short loc_14001C577
0x14001c552  mov     r8d, 700Bh
0x14001c558  mov     ecx, 0FFFFFC18h
0x14001c55d  cmp     ax, r8w
0x14001c561  movzx   eax, ax
0x14001c564  jnz     short loc_14001C568
0x14001c566  mov     eax, ecx
0x14001c568  cmp     dx, r8w
0x14001c56c  jz      short loc_14001C570
0x14001c56e  mov     ecx, edx
0x14001c570  sub     eax, ecx
0x14001c572  jmp     loc_14001C621
0x14001c577  movzx   eax, word ptr [rcx+0Eh]
0x14001c57b  movzx   ecx, word ptr [rbx+0Eh]
0x14001c57f  cmp     cx, ax
0x14001c582  jz      short loc_14001C589
0x14001c584  movzx   eax, ax
0x14001c587  jmp     short loc_14001C570
0x14001c589  mov     rcx, [rdi+20h]
0x14001c58d  cmp     [rbx+20h], rcx
0x14001c591  jz      short loc_14001C59F
0x14001c593  sbb     eax, eax
0x14001c595  and     eax, 2
0x14001c598  dec     eax
0x14001c59a  jmp     loc_14001C621
0x14001c59f  mov     rdx, [rbx+28h]; Buf2
0x14001c5a3  mov     rcx, [rdi+28h]; Buf1
0x14001c5a7  test    rdx, rdx
0x14001c5aa  jnz     short loc_14001C5B3
0x14001c5ac  neg     rcx
0x14001c5af  sbb     eax, eax
0x14001c5b1  jmp     short loc_14001C621
0x14001c5b3  test    rcx, rcx
0x14001c5b6  jnz     short loc_14001C5BD
0x14001c5b8  lea     eax, [rcx+1]
0x14001c5bb  jmp     short loc_14001C621
0x14001c5bd  and     eax, 0F000h
0x14001c5c2  sub     eax, 6000h
0x14001c5c7  test    eax, 0FFFFDFFFh
0x14001c5cc  jz      short loc_14001C5F4
0x14001c5ce  mov     esi, [rbx+30h]
0x14001c5d1  mov     eax, esi
0x14001c5d3  mov     ebx, [rdi+30h]
0x14001c5d6  cmp     ebx, esi
0x14001c5d8  cmovbe  eax, ebx
0x14001c5db  test    eax, eax
0x14001c5dd  jnz     short loc_14001C5E3
0x14001c5df  xor     eax, eax
0x14001c5e1  jmp     short loc_14001C621
0x14001c5e3  mov     r8d, eax; Size
0x14001c5e6  call    memcmp_0
0x14001c5eb  sub     ebx, esi
0x14001c5ed  test    eax, eax
0x14001c5ef  cmovz   eax, ebx
0x14001c5f2  jmp     short loc_14001C621
0x14001c5f4  call    _wcsicmp_0
0x14001c5f9  test    eax, eax
0x14001c5fb  jnz     short loc_14001C621
0x14001c5fd  mov     rax, [rdi+28h]
0x14001c601  mov     rdx, [rbx+28h]
0x14001c605  sub     rdx, rax
0x14001c608  movzx   ecx, word ptr [rax]
0x14001c60b  cmp     cx, [rax+rdx]
0x14001c60f  jnz     short loc_14001C61C
0x14001c611  add     rax, 2
0x14001c615  test    cx, cx
0x14001c618  jnz     short loc_14001C608
0x14001c61a  jmp     short loc_14001C5DF
0x14001c61c  sbb     eax, eax
0x14001c61e  or      eax, 1
0x14001c621  mov     rbx, [rsp+28h+arg_0]
0x14001c626  mov     rsi, [rsp+28h+arg_8]
0x14001c62b  add     rsp, 20h
0x14001c62f  pop     rdi
0x14001c630  retn
```

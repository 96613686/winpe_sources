# read_buffer_aligned::read<ulong>(ulong &)

- ea: `0x140008c08`
- end: `0x140008c8a`
- name: `??$read@K@read_buffer_aligned@@QEAAJAEAK@Z`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c590`
- `0x14000c6f0`
- `0x14000cad0`

## callees

- `0x140008c08`
- `0x14000fa40`

## pseudocode

```c
__int64 __fastcall read_buffer_aligned::read<unsigned long>(__int64 a1, void *a2)
{
  unsigned int v2; // r8d
  unsigned int v4; // eax
  unsigned int v5; // r9d
  int v7; // edi
  unsigned int v8; // edi

  v2 = *(_DWORD *)(a1 + 12);
  if ( (v2 & 3) != 0 )
  {
    v4 = v2 + (*(_DWORD *)(a1 + 12) & 3);
    if ( v4 < v2 )
      return v4 < v2 ? 0xC0000095 : 0;
    v5 = v2 + (*(_DWORD *)(a1 + 12) & 3);
    *(_DWORD *)(a1 + 12) = v5;
  }
  else
  {
    v5 = *(_DWORD *)(a1 + 12);
  }
  v7 = *(_DWORD *)(a1 + 8);
  if ( v5 == v7 )
    return 2147483682LL;
  v8 = v7 - v5;
  if ( v8 >= 4 )
    v8 = 4;
  memmove(a2, (const void *)(*(_QWORD *)a1 + v5), v8);
  *(_DWORD *)(a1 + 12) += v8;
  return 0;
}

```

## disassembly

```asm
0x140008c08  mov     [rsp+arg_0], rbx
0x140008c0d  push    rdi
0x140008c0e  sub     rsp, 20h
0x140008c12  mov     r8d, [rcx+0Ch]
0x140008c16  mov     r10, rdx
0x140008c19  mov     eax, r8d
0x140008c1c  mov     rbx, rcx
0x140008c1f  and     eax, 3
0x140008c22  jz      short loc_140008C49
0x140008c24  add     eax, r8d
0x140008c27  or      r9d, 0FFFFFFFFh
0x140008c2b  cmp     eax, r8d
0x140008c2e  cmovnb  r9d, eax
0x140008c32  sbb     ecx, ecx
0x140008c34  and     ecx, 0C0000095h
0x140008c3a  cmp     eax, r8d
0x140008c3d  jb      short loc_140008C45
0x140008c3f  mov     [rbx+0Ch], r9d
0x140008c43  jmp     short loc_140008C4C
0x140008c45  mov     eax, ecx
0x140008c47  jmp     short loc_140008C7E
0x140008c49  mov     r9d, r8d
0x140008c4c  mov     edi, [rbx+8]
0x140008c4f  cmp     r9d, edi
0x140008c52  jz      short loc_140008C79
0x140008c54  sub     edi, r9d
0x140008c57  mov     edx, r9d
0x140008c5a  mov     eax, 4
0x140008c5f  mov     rcx, r10; void *
0x140008c62  cmp     edi, eax
0x140008c64  cmovnb  edi, eax
0x140008c67  add     rdx, [rbx]; Src
0x140008c6a  mov     r8d, edi; Size
0x140008c6d  call    memmove
0x140008c72  add     [rbx+0Ch], edi
0x140008c75  xor     eax, eax
0x140008c77  jmp     short loc_140008C7E
0x140008c79  mov     eax, 80000022h
0x140008c7e  mov     rbx, [rsp+28h+arg_0]
0x140008c83  add     rsp, 20h
0x140008c87  pop     rdi
0x140008c88  retn
```

# CompareSort

- ea: `0x18000b670`
- end: `0x18000b6f0`
- name: `CompareSort`
- size: `128`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b670`
- `0x18000d1cc`

## pseudocode

```c
__int64 __fastcall CompareSort(int *a1, int *a2)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  unsigned int v4; // ecx
  __int64 v5; // rsi
  int *v6; // rbx
  unsigned int v7; // eax
  bool v8; // zf

  v2 = *(_QWORD *)a1;
  v3 = a1[2];
  v4 = 0;
  v5 = a2[2];
  v6 = *(int **)(v2 + 56);
  while ( v6 && !v4 )
  {
    LOBYTE(v7) = CTDCArr::VariantComp(
                   *(CTDCArr **)(*(_QWORD *)(v2 + 152) + 8 * v3),
                   (struct tagVARIANT *)(**(_QWORD **)(*(_QWORD *)(v2 + 152) + 8 * v3) + 24 * (*v6 - 1LL)),
                   (struct tagVARIANT *)(**(_QWORD **)(*(_QWORD *)(v2 + 152) + 8 * v5) + 24 * (*v6 - 1LL)),
                   *(_WORD *)(*(_QWORD *)(v2 + 176) + 8LL * *v6 - 8),
                   *(_BYTE *)(v2 + 116));
    v4 = -v7;
    v8 = *((_BYTE *)v6 + 4) == 0;
    v6 = (int *)*((_QWORD *)v6 + 1);
    if ( !v8 )
      v4 = v7;
  }
  return v4;
}

```

## disassembly

```asm
0x18000b670  push    rbx
0x18000b672  push    rbp
0x18000b673  push    rsi
0x18000b674  push    rdi
0x18000b675  sub     rsp, 38h
0x18000b679  mov     rdi, [rcx]
0x18000b67c  movsxd  rbp, dword ptr [rcx+8]
0x18000b680  xor     ecx, ecx
0x18000b682  movsxd  rsi, dword ptr [rdx+8]
0x18000b686  mov     rbx, [rdi+38h]
0x18000b68a  jmp     short loc_18000B6E0
0x18000b68c  test    ecx, ecx
0x18000b68e  jnz     short loc_18000B6E5
0x18000b690  mov     rdx, [rdi+98h]
0x18000b697  movsxd  r11, dword ptr [rbx]
0x18000b69a  mov     r9, [rdi+0B0h]
0x18000b6a1  mov     rcx, [rdx+rsi*8]
0x18000b6a5  lea     r10, [r11-1]
0x18000b6a9  movzx   r9d, word ptr [r9+r11*8-8]; unsigned __int16
0x18000b6af  lea     r10, [r10+r10*2]
0x18000b6b3  mov     rax, [rcx]
0x18000b6b6  mov     rcx, [rdx+rbp*8]; this
0x18000b6ba  lea     r8, [rax+r10*8]; struct tagVARIANT *
0x18000b6be  mov     rax, [rcx]
0x18000b6c1  lea     rdx, [rax+r10*8]; struct tagVARIANT *
0x18000b6c5  mov     al, [rdi+74h]
0x18000b6c8  mov     [rsp+58h+var_38], al; char
0x18000b6cc  call    ?VariantComp@CTDCArr@@AEAAHPEAUtagVARIANT@@0GE@Z; CTDCArr::VariantComp(tagVARIANT *,tagVARIANT *,ushort,uchar)
0x18000b6d1  mov     ecx, eax
0x18000b6d3  neg     ecx
0x18000b6d5  cmp     byte ptr [rbx+4], 0
0x18000b6d9  mov     rbx, [rbx+8]
0x18000b6dd  cmovnz  ecx, eax
0x18000b6e0  test    rbx, rbx
0x18000b6e3  jnz     short loc_18000B68C
0x18000b6e5  mov     eax, ecx
0x18000b6e7  add     rsp, 38h
0x18000b6eb  pop     rdi
0x18000b6ec  pop     rsi
0x18000b6ed  pop     rbp
0x18000b6ee  pop     rbx
0x18000b6ef  retn
```

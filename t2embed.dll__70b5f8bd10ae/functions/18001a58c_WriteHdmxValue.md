# WriteHdmxValue

- ea: `0x18001a58c`
- end: `0x18001a639`
- name: `WriteHdmxValue`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002bd0`

## callees

- `0x18001a58c`

## pseudocode

```c
int __fastcall WriteHdmxValue(__int16 a1, __int64 a2, int *a3)
{
  int v6; // eax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // eax
  int result; // eax
  __int16 v11; // di
  __int16 v12; // r8
  int v13; // eax
  int v14; // esi
  int v15; // r8d

  if ( a1 )
  {
    v11 = 0;
    v12 = -a1;
    if ( a1 > 0 )
      v12 = a1;
    if ( v12 > 0 )
    {
      v13 = *a3;
      do
      {
        v14 = v13 + 1;
        ++v11;
        *(_BYTE *)(v13 / 8 + a2) |= 1 << (v13 % 8);
        ++v13;
      }
      while ( v11 < v12 );
      *a3 = v14;
    }
    v15 = *a3;
    *(_BYTE *)(*a3 / 8 + a2) &= ~(1 << (*a3 % 8));
    *a3 = v15 + 2;
    v7 = (v15 + 1) % 8;
    v8 = (v15 + 1) / 8;
    v9 = *(unsigned __int8 *)(v8 + a2);
    if ( a1 <= 0 )
    {
      result = v9 | (1 << v7);
      goto LABEL_4;
    }
  }
  else
  {
    v6 = *a3 / 8;
    v7 = *a3 % 8;
    ++*a3;
    v8 = v6;
    v9 = *(unsigned __int8 *)(v6 + a2);
  }
  result = v9 & ~(1 << v7);
LABEL_4:
  *(_BYTE *)(v8 + a2) = result;
  return result;
}

```

## disassembly

```asm
0x18001a58c  push    rbx
0x18001a58e  push    rbp
0x18001a58f  push    rsi
0x18001a590  push    rdi
0x18001a591  xor     ebp, ebp
0x18001a593  mov     r10, r8
0x18001a596  mov     r9, rdx
0x18001a599  movzx   r11d, cx
0x18001a59d  lea     ebx, [rbp+8]
0x18001a5a0  test    cx, cx
0x18001a5a3  jnz     short loc_18001A5C5
0x18001a5a5  mov     eax, [r8]
0x18001a5a8  lea     ecx, [rax+1]
0x18001a5ab  cdq
0x18001a5ac  idiv    ebx
0x18001a5ae  mov     [r8], ecx
0x18001a5b1  movsxd  rcx, eax
0x18001a5b4  movzx   eax, byte ptr [rcx+r9]
0x18001a5b9  btr     eax, edx
0x18001a5bc  mov     [rcx+r9], al
0x18001a5c0  pop     rdi
0x18001a5c1  pop     rsi
0x18001a5c2  pop     rbp
0x18001a5c3  pop     rbx
0x18001a5c4  retn
0x18001a5c5  movzx   r8d, r11w
0x18001a5c9  mov     edi, ebp
0x18001a5cb  neg     r8w
0x18001a5cf  cmovs   r8w, r11w
0x18001a5d4  cmp     bp, r8w
0x18001a5d8  jge     short loc_18001A600
0x18001a5da  mov     eax, [r10]
0x18001a5dd  lea     esi, [rax+1]
0x18001a5e0  inc     di
0x18001a5e3  cdq
0x18001a5e4  idiv    ebx
0x18001a5e6  movsxd  rcx, eax
0x18001a5e9  movzx   eax, byte ptr [rcx+r9]
0x18001a5ee  bts     eax, edx
0x18001a5f1  mov     [rcx+r9], al
0x18001a5f5  mov     eax, esi
0x18001a5f7  cmp     di, r8w
0x18001a5fb  jl      short loc_18001A5DD
0x18001a5fd  mov     [r10], esi
0x18001a600  mov     r8d, [r10]
0x18001a603  mov     eax, r8d
0x18001a606  cdq
0x18001a607  idiv    ebx
0x18001a609  movsxd  rcx, eax
0x18001a60c  movzx   eax, byte ptr [rcx+r9]
0x18001a611  btr     eax, edx
0x18001a614  mov     [rcx+r9], al
0x18001a618  lea     eax, [r8+2]
0x18001a61c  mov     [r10], eax
0x18001a61f  lea     eax, [r8+1]
0x18001a623  cdq
0x18001a624  idiv    ebx
0x18001a626  movsxd  rcx, eax
0x18001a629  movzx   eax, byte ptr [rcx+r9]
0x18001a62e  test    r11w, r11w
0x18001a632  jg      short loc_18001A5B9
0x18001a634  bts     eax, edx
0x18001a637  jmp     short loc_18001A5BC
```

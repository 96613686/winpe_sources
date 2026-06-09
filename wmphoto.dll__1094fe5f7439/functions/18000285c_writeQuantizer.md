# writeQuantizer

- ea: `0x18000285c`
- end: `0x180002905`
- name: `writeQuantizer`
- size: `169`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021c0`
- `0x180032738`
- `0x180042088`
- `0x180042294`

## callees

- `0x18000285c`
- `0x180003760`

## pseudocode

```c
__int64 __fastcall writeQuantizer(_QWORD *a1, __int64 a2, char a3, unsigned __int64 a4, __int64 a5)
{
  char v7; // r11
  __int64 result; // rax
  __int64 v10; // r8
  char v11; // r11
  unsigned __int64 i; // r11
  __int64 v13; // r11

  v7 = 2;
  if ( (unsigned __int8)a3 <= 2u )
    v7 = a3;
  if ( a4 > 1 )
    putBit16z(a2, v7 & 3, 2);
  result = putBit16z(a2, *(unsigned __int8 *)(*a1 + 20 * a5), 8);
  if ( v11 == 1 )
    return putBit16z(a2, *(unsigned __int8 *)(a1[1] + 20 * a5), v10);
  if ( v11 )
  {
    for ( i = 1; i < a4; i = v13 + 1 )
      result = putBit16z(a2, *(unsigned __int8 *)(a1[i] + 20 * a5), v10);
  }
  return result;
}

```

## disassembly

```asm
0x18000285c  push    rbx
0x18000285e  push    rbp
0x18000285f  push    rsi
0x180002860  push    rdi
0x180002861  sub     rsp, 28h
0x180002865  mov     rsi, rcx
0x180002868  movzx   eax, r8b
0x18000286c  mov     ecx, 2
0x180002871  mov     rbp, r9
0x180002874  cmp     r8b, cl
0x180002877  mov     r11d, ecx
0x18000287a  mov     rbx, rdx
0x18000287d  cmovbe  r11d, eax
0x180002881  cmp     r9, 1
0x180002885  jbe     short loc_18000289B
0x180002887  movzx   edx, r11b
0x18000288b  mov     r8d, ecx
0x18000288e  and     edx, 3
0x180002891  mov     rcx, rbx
0x180002894  call    putBit16z
0x180002899  jmp     short loc_18000289E
0x18000289b  xor     r11b, r11b
0x18000289e  mov     rax, [rsp+48h+arg_20]
0x1800028a3  mov     r8d, 8
0x1800028a9  mov     rcx, rbx
0x1800028ac  lea     rdi, [rax+rax*4]
0x1800028b0  mov     rax, [rsi]
0x1800028b3  movzx   edx, byte ptr [rax+rdi*4]
0x1800028b7  call    putBit16z
0x1800028bc  cmp     r11b, 1
0x1800028c0  jnz     short loc_1800028D4
0x1800028c2  mov     rax, [rsi+8]
0x1800028c6  mov     rcx, rbx
0x1800028c9  movzx   edx, byte ptr [rax+rdi*4]
0x1800028cd  call    putBit16z
0x1800028d2  jmp     short loc_1800028FC
0x1800028d4  test    r11b, r11b
0x1800028d7  jz      short loc_1800028FC
0x1800028d9  mov     r11d, 1
0x1800028df  cmp     rbp, r11
0x1800028e2  jbe     short loc_1800028FC
0x1800028e4  mov     rax, [rsi+r11*8]
0x1800028e8  mov     rcx, rbx
0x1800028eb  movzx   edx, byte ptr [rax+rdi*4]
0x1800028ef  call    putBit16z
0x1800028f4  inc     r11
0x1800028f7  cmp     r11, rbp
0x1800028fa  jb      short loc_1800028E4
0x1800028fc  add     rsp, 28h
0x180002900  pop     rdi
0x180002901  pop     rsi
0x180002902  pop     rbp
0x180002903  pop     rbx
0x180002904  retn
```

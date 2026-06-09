# GetNextMsOs20Descriptor

- ea: `0x14000ed84`
- end: `0x14000edee`
- name: `GetNextMsOs20Descriptor`
- size: `106`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ecc8`
- `0x140022240`
- `0x14002d698`
- `0x14002d748`

## callees

- `0x14000ed84`

## pseudocode

```c
char __fastcall GetNextMsOs20Descriptor(unsigned __int64 a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // r9
  unsigned __int16 v4; // ax
  unsigned __int16 v5; // dx
  char v6; // r8
  unsigned __int16 *v7; // rdx

  v2 = *a2;
  v4 = **a2;
  if ( !v4 )
    goto LABEL_10;
  v5 = v2[1];
  v6 = 1;
  if ( v5 == 1 || v5 == 2 )
  {
    if ( v4 != 8 )
      goto LABEL_10;
    v4 = v2[3];
    if ( !v4 )
      goto LABEL_10;
  }
  v7 = (unsigned __int16 *)((char *)v2 + v4);
  if ( v7 == (unsigned __int16 *)a1 )
  {
LABEL_11:
    *a2 = 0;
    return v6;
  }
  if ( (unsigned __int64)v7 > a1 || (unsigned __int64)(v7 + 2) > a1 )
  {
LABEL_10:
    v6 = 0;
    goto LABEL_11;
  }
  *a2 = v7;
  return v6;
}

```

## disassembly

```asm
0x14000ed84  mov     [rsp+arg_0], rbx
0x14000ed89  mov     r9, [rdx]
0x14000ed8c  xor     ebx, ebx
0x14000ed8e  mov     r10, rdx
0x14000ed91  mov     r11, rcx
0x14000ed94  movzx   eax, word ptr [r9]
0x14000ed98  test    ax, ax
0x14000ed9b  jz      short loc_14000EDDE
0x14000ed9d  movzx   edx, word ptr [r9+2]
0x14000eda2  mov     r8w, 1
0x14000eda7  cmp     dx, r8w
0x14000edab  jz      short loc_14000EDB3
0x14000edad  cmp     dx, 2
0x14000edb1  jnz     short loc_14000EDC3
0x14000edb3  cmp     ax, 8
0x14000edb7  jnz     short loc_14000EDDE
0x14000edb9  movzx   eax, word ptr [r9+6]
0x14000edbe  test    ax, ax
0x14000edc1  jz      short loc_14000EDDE
0x14000edc3  movzx   edx, ax
0x14000edc6  add     rdx, r9
0x14000edc9  cmp     rdx, r11
0x14000edcc  jz      short loc_14000EDE1
0x14000edce  ja      short loc_14000EDDE
0x14000edd0  lea     rcx, [rdx+4]
0x14000edd4  cmp     rcx, r11
0x14000edd7  ja      short loc_14000EDDE
0x14000edd9  mov     [r10], rdx
0x14000eddc  jmp     short loc_14000EDE4
0x14000edde  mov     r8b, bl
0x14000ede1  mov     [r10], rbx
0x14000ede4  mov     rbx, [rsp+arg_0]
0x14000ede9  mov     al, r8b
0x14000edec  retn
```

# GetGenericSize

- ea: `0x180013230`
- end: `0x1800132a4`
- name: `GetGenericSize`
- size: `116`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ee80`
- `0x18000faf0`
- `0x18001009c`
- `0x180010448`
- `0x1800106c8`
- `0x180010b90`
- `0x1800110d0`
- `0x180012a18`
- `0x18001357c`
- `0x180013b44`
- `0x18001a874`
- `0x18001d5f8`
- `0x18001dc84`
- `0x180027480`
- `0x18002773c`
- `0x1800277fc`
- `0x1800278d8`
- `0x180028c2c`
- `0x180029228`
- `0x180029d3c`

## callees

- `0x180013230`

## pseudocode

```c
__int64 __fastcall GetGenericSize(unsigned __int8 *a1)
{
  unsigned __int16 v1; // dx
  unsigned __int16 i; // r9
  unsigned __int8 v3; // r8
  unsigned __int16 v4; // ax

  v1 = 0;
  for ( i = 1; ; ++i )
  {
    if ( i > *a1 )
      return v1;
    v3 = a1[i];
    if ( (v3 & 7) != 1 )
      break;
    if ( (v3 & 0x10) == 0 )
      ++v1;
LABEL_9:
    ;
  }
  if ( (a1[i] & 7) == 2 )
  {
    v4 = v1 + 2;
LABEL_6:
    if ( (v3 & 0x10) != 0 )
      v4 = v1;
    v1 = v4;
    goto LABEL_9;
  }
  if ( (a1[i] & 7) == 4 )
  {
    v4 = v1 + 4;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x180013230  mov     [rsp+arg_0], rbx
0x180013235  mov     [rsp+arg_8], rsi
0x18001323a  movzx   r11d, byte ptr [rcx]
0x18001323e  xor     edx, edx
0x180013240  mov     r10, rcx
0x180013243  lea     ebx, [rdx+1]
0x180013246  movzx   r9d, bx
0x18001324a  lea     esi, [rdx+2]
0x18001324d  cmp     r9w, r11w
0x180013251  ja      short loc_18001327E
0x180013253  movzx   eax, r9w
0x180013257  movzx   r8d, byte ptr [rax+r10]
0x18001325c  mov     ecx, r8d
0x18001325f  and     ecx, 7
0x180013262  sub     ecx, ebx
0x180013264  jz      short loc_180013295
0x180013266  sub     ecx, ebx
0x180013268  jnz     short loc_18001328C
0x18001326a  lea     eax, [rsi+rdx]
0x18001326d  test    r8b, 10h
0x180013271  cmovnz  ax, dx
0x180013275  movzx   edx, ax
0x180013278  add     r9w, bx
0x18001327c  jmp     short loc_18001324D
0x18001327e  movzx   eax, dx
0x180013281  mov     rbx, [rsp+arg_0]
0x180013286  mov     rsi, [rsp+arg_8]
0x18001328b  retn
0x18001328c  cmp     ecx, esi
0x18001328e  jnz     short loc_1800132A0
0x180013290  lea     eax, [rdx+4]
0x180013293  jmp     short loc_18001326D
0x180013295  test    r8b, 10h
0x180013299  jnz     short loc_180013278
0x18001329b  add     dx, bx
0x18001329e  jmp     short loc_180013278
0x1800132a0  xor     eax, eax
0x1800132a2  jmp     short loc_180013281
```

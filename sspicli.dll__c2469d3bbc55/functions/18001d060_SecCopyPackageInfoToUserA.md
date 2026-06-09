# SecCopyPackageInfoToUserA

- ea: `0x18001d060`
- end: `0x18001d11d`
- name: `SecCopyPackageInfoToUserA`
- size: `189`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004290`
- `0x1800197b0`
- `0x180019d70`
- `0x18001adc0`

## callees

- `0x18001d060`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0a7`

## pseudocode

```c
__int64 __fastcall SecCopyPackageInfoToUserA(__int64 a1, _QWORD *a2)
{
  _WORD *v2; // rsi
  __int64 result; // rax
  unsigned int v6; // ecx
  SIZE_T v7; // rdx
  _WORD *v8; // rax
  char *v9; // rbx
  char *v10; // rcx

  v2 = 0;
  if ( a1 )
  {
    v6 = *(_DWORD *)(a1 + 136) + 32;
    if ( v6 >= 0x20
      && (v7 = v6 + *(_DWORD *)(a1 + 152), (unsigned int)v7 >= v6)
      && (v8 = LocalAlloc(0x40u, v7), (v2 = v8) != 0) )
    {
      v9 = (char *)(v8 + 16);
      *(_DWORD *)v8 = *(_DWORD *)(a1 + 80);
      v8[2] = *(_WORD *)(a1 + 84);
      v8[3] = *(_WORD *)(a1 + 86);
      *((_DWORD *)v8 + 2) = *(_DWORD *)(a1 + 92);
      *((_QWORD *)v8 + 2) = v8 + 16;
      memcpy_0(v8 + 16, *(const void **)(a1 + 128), *(unsigned int *)(a1 + 136));
      v10 = &v9[*(unsigned int *)(a1 + 136)];
      *((_QWORD *)v2 + 3) = v10;
      memcpy_0(v10, *(const void **)(a1 + 144), *(unsigned int *)(a1 + 152));
      result = 0;
    }
    else
    {
      result = 2148074240LL;
    }
  }
  else
  {
    result = 2148074245LL;
  }
  *a2 = v2;
  return result;
}

```

## disassembly

```asm
0x18001d060  push    rbx
0x18001d062  push    rsi
0x18001d063  push    rdi
0x18001d064  push    r14
0x18001d066  sub     rsp, 28h
0x18001d06a  xor     esi, esi
0x18001d06c  mov     r14, rdx
0x18001d06f  mov     rdi, rcx
0x18001d072  test    rcx, rcx
0x18001d075  jnz     short loc_18001D081
0x18001d077  mov     eax, 80090305h
0x18001d07c  jmp     loc_18001D110
0x18001d081  mov     ecx, [rcx+88h]
0x18001d087  add     ecx, 20h ; ' '
0x18001d08a  cmp     ecx, 20h ; ' '
0x18001d08d  jnb     short loc_18001D096
0x18001d08f  mov     eax, 80090300h
0x18001d094  jmp     short loc_18001D110
0x18001d096  mov     edx, [rdi+98h]
0x18001d09c  add     edx, ecx; uBytes
0x18001d09e  cmp     edx, ecx
0x18001d0a0  jb      short loc_18001D08F
0x18001d0a2  mov     ecx, 40h ; '@'; uFlags
0x18001d0a7  call    cs:__imp_LocalAlloc
0x18001d0ad  mov     rsi, rax
0x18001d0b0  test    rax, rax
0x18001d0b3  jz      short loc_18001D08F
0x18001d0b5  lea     rbx, [rax+20h]
0x18001d0b9  mov     eax, [rdi+50h]
0x18001d0bc  mov     [rsi], eax
0x18001d0be  mov     rcx, rbx; void *
0x18001d0c1  movzx   eax, word ptr [rdi+54h]
0x18001d0c5  mov     [rsi+4], ax
0x18001d0c9  movzx   eax, word ptr [rdi+56h]
0x18001d0cd  mov     [rsi+6], ax
0x18001d0d1  mov     eax, [rdi+5Ch]
0x18001d0d4  mov     [rsi+8], eax
0x18001d0d7  mov     [rsi+10h], rbx
0x18001d0db  mov     r8d, [rdi+88h]; Size
0x18001d0e2  mov     rdx, [rdi+80h]; Src
0x18001d0e9  call    memcpy_0
0x18001d0ee  mov     ecx, [rdi+88h]
0x18001d0f4  add     rcx, rbx; void *
0x18001d0f7  mov     [rsi+18h], rcx
0x18001d0fb  mov     r8d, [rdi+98h]; Size
0x18001d102  mov     rdx, [rdi+90h]; Src
0x18001d109  call    memcpy_0
0x18001d10e  xor     eax, eax
0x18001d110  mov     [r14], rsi
0x18001d113  add     rsp, 28h
0x18001d117  pop     r14
0x18001d119  pop     rdi
0x18001d11a  pop     rsi
0x18001d11b  pop     rbx
0x18001d11c  retn
```

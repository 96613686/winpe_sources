# RtlStringCchCopyExW

- ea: `0x180015498`
- end: `0x18001553e`
- name: `RtlStringCchCopyExW`
- size: `166`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, _WORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001190`

## callees

- `0x180015498`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyExW(_WORD *a1, unsigned __int64 a2, _WORD *a3)
{
  unsigned int v6; // edx
  __int64 v7; // rax
  unsigned __int64 v8; // r8
  _WORD *v9; // r11
  _WORD *v10; // rcx

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v7 = 2147483646;
      v8 = a2;
      v9 = a1;
      do
      {
        if ( !v7 )
          break;
        if ( !*a3 )
          break;
        *v9++ = *a3++;
        --v7;
        --v8;
      }
      while ( v8 );
      v10 = v9 - 1;
      v6 = v8 == 0 ? 0x80000005 : 0;
      if ( v8 )
        v10 = v9;
      *v10 = 0;
      if ( !v8 && (a2 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
        *a1 = 0;
    }
    else
    {
      v6 = -1073741811;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v6;
}

```

## disassembly

```asm
0x180015498  mov     [rsp+arg_0], rbx
0x18001549d  mov     [rsp+arg_8], rdi
0x1800154a2  xor     edi, edi
0x1800154a4  mov     rbx, r8
0x1800154a7  mov     r9, rdx
0x1800154aa  mov     r10, rcx
0x1800154ad  test    rdx, rdx
0x1800154b0  jz      short loc_180015524
0x1800154b2  cmp     rdx, 7FFFFFFFh
0x1800154b9  jbe     short loc_1800154C2
0x1800154bb  mov     edx, 0C000000Dh
0x1800154c0  jmp     short loc_18001552E
0x1800154c2  mov     eax, 7FFFFFFEh
0x1800154c7  mov     r8, r9
0x1800154ca  mov     r11, r10
0x1800154cd  test    rax, rax
0x1800154d0  jz      short loc_1800154EF
0x1800154d2  movzx   ecx, word ptr [rbx]
0x1800154d5  test    cx, cx
0x1800154d8  jz      short loc_1800154EF
0x1800154da  mov     [r11], cx
0x1800154de  add     rbx, 2
0x1800154e2  add     r11, 2
0x1800154e6  dec     rax
0x1800154e9  sub     r8, 1
0x1800154ed  jnz     short loc_1800154CD
0x1800154ef  mov     rax, r8
0x1800154f2  lea     rcx, [r11-2]
0x1800154f6  neg     rax
0x1800154f9  sbb     edx, edx
0x1800154fb  not     edx
0x1800154fd  and     edx, 80000005h
0x180015503  test    r8, r8
0x180015506  cmovnz  rcx, r11
0x18001550a  mov     [rcx], di
0x18001550d  jnz     short loc_180015531
0x18001550f  mov     rax, 7FFFFFFFFFFFFFFFh
0x180015519  test    rax, r9
0x18001551c  jbe     short loc_180015531
0x18001551e  mov     [r10], di
0x180015522  jmp     short loc_180015531
0x180015524  mov     edx, 0C000000Dh
0x180015529  test    r9, r9
0x18001552c  jz      short loc_180015531
0x18001552e  mov     [rcx], di
0x180015531  mov     rbx, [rsp+arg_0]
0x180015536  mov     eax, edx
0x180015538  mov     rdi, [rsp+arg_8]
0x18001553d  retn
```

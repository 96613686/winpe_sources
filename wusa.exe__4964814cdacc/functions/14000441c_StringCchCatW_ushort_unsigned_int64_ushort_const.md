# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x14000441c`
- end: `0x1400044d7`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a8c`
- `0x14000456c`
- `0x14000fdf8`
- `0x1400135a4`

## callees

- `0x14000441c`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000441c  mov     [rsp+arg_0], rbx
0x140004421  mov     [rsp+arg_8], rdi
0x140004426  lea     rax, [rdx-1]
0x14000442a  mov     r10d, 7FFFFFFEh
0x140004430  mov     r9, rdx
0x140004433  mov     rbx, rcx
0x140004436  cmp     rax, r10
0x140004439  ja      loc_1400044C5
0x14000443f  mov     r11, rdx
0x140004442  mov     rax, rcx
0x140004445  xor     edi, edi
0x140004447  cmp     [rax], di
0x14000444a  jz      short loc_140004456
0x14000444c  add     rax, 2
0x140004450  sub     r11, 1
0x140004454  jnz     short loc_140004447
0x140004456  mov     rax, r11
0x140004459  mov     rcx, r9
0x14000445c  neg     rax
0x14000445f  mov     rax, r11
0x140004462  sbb     edx, edx
0x140004464  sub     rcx, r11
0x140004467  not     edx
0x140004469  and     edx, 80070057h
0x14000446f  neg     rax
0x140004472  sbb     rax, rax
0x140004475  and     rax, rcx
0x140004478  test    r11, r11
0x14000447b  jz      short loc_1400044CA
0x14000447d  sub     r9, rax
0x140004480  lea     rax, [rbx+rax*2]
0x140004484  jz      short loc_1400044A8
0x140004486  test    r10, r10
0x140004489  jz      short loc_1400044A8
0x14000448b  movzx   ecx, word ptr [r8]
0x14000448f  test    cx, cx
0x140004492  jz      short loc_1400044A8
0x140004494  mov     [rax], cx
0x140004497  add     r8, 2
0x14000449b  add     rax, 2
0x14000449f  dec     r10
0x1400044a2  sub     r9, 1
0x1400044a6  jnz     short loc_140004486
0x1400044a8  test    r9, r9
0x1400044ab  lea     rcx, [rax-2]
0x1400044af  cmovnz  rcx, rax
0x1400044b3  neg     r9
0x1400044b6  sbb     edx, edx
0x1400044b8  not     edx
0x1400044ba  and     edx, 8007007Ah
0x1400044c0  mov     [rcx], di
0x1400044c3  jmp     short loc_1400044CA
0x1400044c5  mov     edx, 80070057h
0x1400044ca  mov     rbx, [rsp+arg_0]
0x1400044cf  mov     eax, edx
0x1400044d1  mov     rdi, [rsp+arg_8]
0x1400044d6  retn
```

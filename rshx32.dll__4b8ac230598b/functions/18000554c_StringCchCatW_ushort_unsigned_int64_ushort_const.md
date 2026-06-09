# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000554c`
- end: `0x180005607`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003be0`
- `0x180005710`
- `0x180007390`
- `0x18000ca38`

## callees

- `0x18000554c`

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
0x18000554c  mov     [rsp+arg_0], rbx
0x180005551  mov     [rsp+arg_8], rdi
0x180005556  lea     rax, [rdx-1]
0x18000555a  mov     r10d, 7FFFFFFEh
0x180005560  mov     r9, rdx
0x180005563  mov     rbx, rcx
0x180005566  cmp     rax, r10
0x180005569  ja      loc_1800055F5
0x18000556f  mov     r11, rdx
0x180005572  mov     rax, rcx
0x180005575  xor     edi, edi
0x180005577  cmp     [rax], di
0x18000557a  jz      short loc_180005586
0x18000557c  add     rax, 2
0x180005580  sub     r11, 1
0x180005584  jnz     short loc_180005577
0x180005586  mov     rax, r11
0x180005589  mov     rcx, r9
0x18000558c  neg     rax
0x18000558f  mov     rax, r11
0x180005592  sbb     edx, edx
0x180005594  sub     rcx, r11
0x180005597  not     edx
0x180005599  and     edx, 80070057h
0x18000559f  neg     rax
0x1800055a2  sbb     rax, rax
0x1800055a5  and     rax, rcx
0x1800055a8  test    r11, r11
0x1800055ab  jz      short loc_1800055FA
0x1800055ad  sub     r9, rax
0x1800055b0  lea     rax, [rbx+rax*2]
0x1800055b4  jz      short loc_1800055D8
0x1800055b6  test    r10, r10
0x1800055b9  jz      short loc_1800055D8
0x1800055bb  movzx   ecx, word ptr [r8]
0x1800055bf  test    cx, cx
0x1800055c2  jz      short loc_1800055D8
0x1800055c4  mov     [rax], cx
0x1800055c7  add     r8, 2
0x1800055cb  add     rax, 2
0x1800055cf  dec     r10
0x1800055d2  sub     r9, 1
0x1800055d6  jnz     short loc_1800055B6
0x1800055d8  test    r9, r9
0x1800055db  lea     rcx, [rax-2]
0x1800055df  cmovnz  rcx, rax
0x1800055e3  neg     r9
0x1800055e6  sbb     edx, edx
0x1800055e8  not     edx
0x1800055ea  and     edx, 8007007Ah
0x1800055f0  mov     [rcx], di
0x1800055f3  jmp     short loc_1800055FA
0x1800055f5  mov     edx, 80070057h
0x1800055fa  mov     rbx, [rsp+arg_0]
0x1800055ff  mov     eax, edx
0x180005601  mov     rdi, [rsp+arg_8]
0x180005606  retn
```

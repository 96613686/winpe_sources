# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005830`
- end: `0x1800058eb`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f74`
- `0x1800059f4`
- `0x180006f54`
- `0x18000834c`
- `0x18000855c`

## callees

- `0x180005830`

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
0x180005830  mov     [rsp+arg_0], rbx
0x180005835  mov     [rsp+arg_8], rdi
0x18000583a  lea     rax, [rdx-1]
0x18000583e  mov     r10d, 7FFFFFFEh
0x180005844  mov     r9, rdx
0x180005847  mov     rbx, rcx
0x18000584a  cmp     rax, r10
0x18000584d  ja      loc_1800058D9
0x180005853  mov     r11, rdx
0x180005856  mov     rax, rcx
0x180005859  xor     edi, edi
0x18000585b  cmp     [rax], di
0x18000585e  jz      short loc_18000586A
0x180005860  add     rax, 2
0x180005864  sub     r11, 1
0x180005868  jnz     short loc_18000585B
0x18000586a  mov     rax, r11
0x18000586d  mov     rcx, r9
0x180005870  neg     rax
0x180005873  mov     rax, r11
0x180005876  sbb     edx, edx
0x180005878  sub     rcx, r11
0x18000587b  not     edx
0x18000587d  and     edx, 80070057h
0x180005883  neg     rax
0x180005886  sbb     rax, rax
0x180005889  and     rax, rcx
0x18000588c  test    r11, r11
0x18000588f  jz      short loc_1800058DE
0x180005891  sub     r9, rax
0x180005894  lea     rax, [rbx+rax*2]
0x180005898  jz      short loc_1800058BC
0x18000589a  test    r10, r10
0x18000589d  jz      short loc_1800058BC
0x18000589f  movzx   ecx, word ptr [r8]
0x1800058a3  test    cx, cx
0x1800058a6  jz      short loc_1800058BC
0x1800058a8  mov     [rax], cx
0x1800058ab  add     r8, 2
0x1800058af  add     rax, 2
0x1800058b3  dec     r10
0x1800058b6  sub     r9, 1
0x1800058ba  jnz     short loc_18000589A
0x1800058bc  test    r9, r9
0x1800058bf  lea     rcx, [rax-2]
0x1800058c3  cmovnz  rcx, rax
0x1800058c7  neg     r9
0x1800058ca  sbb     edx, edx
0x1800058cc  not     edx
0x1800058ce  and     edx, 8007007Ah
0x1800058d4  mov     [rcx], di
0x1800058d7  jmp     short loc_1800058DE
0x1800058d9  mov     edx, 80070057h
0x1800058de  mov     rbx, [rsp+arg_0]
0x1800058e3  mov     eax, edx
0x1800058e5  mov     rdi, [rsp+arg_8]
0x1800058ea  retn
```

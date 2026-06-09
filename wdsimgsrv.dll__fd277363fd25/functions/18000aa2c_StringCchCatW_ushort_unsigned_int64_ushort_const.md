# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000aa2c`
- end: `0x18000aafa`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `206`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800096e8`
- `0x18000bdc4`
- `0x18000d39c`
- `0x18000d980`

## callees

- `0x18000aa2c`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, char *a3)
{
  __int64 v5; // r10
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // r8
  unsigned __int16 *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  char *v12; // r11
  unsigned __int16 v13; // r8
  unsigned __int16 *v14; // rax

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
      v9 = &a1[v8];
      v10 = a2 - v8;
      if ( a2 != v8 )
      {
        v11 = 2147483646;
        v12 = (char *)(a3 - (char *)v9);
        do
        {
          if ( !v11 )
            break;
          v13 = *(unsigned __int16 *)((char *)v9 + (_QWORD)v12);
          if ( !v13 )
            break;
          *v9 = v13;
          --v11;
          ++v9;
          --v10;
        }
        while ( v10 );
      }
      v14 = v9 - 1;
      if ( v10 )
        v14 = v9;
      v7 = v10 == 0 ? 0x8007007A : 0;
      *v14 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000aa2c  mov     [rsp+arg_0], rbx
0x18000aa31  mov     [rsp+arg_8], rdi
0x18000aa36  lea     rax, [rdx-1]
0x18000aa3a  mov     r11, r8
0x18000aa3d  mov     r9, rdx
0x18000aa40  mov     rbx, rcx
0x18000aa43  cmp     rax, 7FFFFFFEh
0x18000aa49  ja      loc_18000AAE7
0x18000aa4f  mov     r10, rdx
0x18000aa52  mov     rax, rcx
0x18000aa55  xor     edi, edi
0x18000aa57  cmp     [rax], di
0x18000aa5a  jz      short loc_18000AA66
0x18000aa5c  add     rax, 2
0x18000aa60  sub     r10, 1
0x18000aa64  jnz     short loc_18000AA57
0x18000aa66  mov     rax, r10
0x18000aa69  mov     rcx, r9
0x18000aa6c  neg     rax
0x18000aa6f  mov     rax, r10
0x18000aa72  sbb     edx, edx
0x18000aa74  sub     rcx, r10
0x18000aa77  not     edx
0x18000aa79  and     edx, 80070057h
0x18000aa7f  neg     rax
0x18000aa82  sbb     r8, r8
0x18000aa85  and     r8, rcx
0x18000aa88  test    r10, r10
0x18000aa8b  jz      short loc_18000AAEC
0x18000aa8d  mov     rcx, r9
0x18000aa90  lea     rdx, [rbx+r8*2]
0x18000aa94  sub     rcx, r8
0x18000aa97  jz      short loc_18000AACA
0x18000aa99  sub     r8, r9
0x18000aa9c  lea     rax, [r8+7FFFFFFEh]
0x18000aaa3  add     rax, rcx
0x18000aaa6  sub     r11, rdx
0x18000aaa9  test    rax, rax
0x18000aaac  jz      short loc_18000AACA
0x18000aaae  movzx   r8d, word ptr [r11+rdx]
0x18000aab3  test    r8w, r8w
0x18000aab7  jz      short loc_18000AACA
0x18000aab9  mov     [rdx], r8w
0x18000aabd  dec     rax
0x18000aac0  add     rdx, 2
0x18000aac4  sub     rcx, 1
0x18000aac8  jnz     short loc_18000AAA9
0x18000aaca  lea     rax, [rdx-2]
0x18000aace  test    rcx, rcx
0x18000aad1  cmovnz  rax, rdx
0x18000aad5  neg     rcx
0x18000aad8  sbb     edx, edx
0x18000aada  not     edx
0x18000aadc  and     edx, 8007007Ah
0x18000aae2  mov     [rax], di
0x18000aae5  jmp     short loc_18000AAEC
0x18000aae7  mov     edx, 80070057h
0x18000aaec  mov     rbx, [rsp+arg_0]
0x18000aaf1  mov     eax, edx
0x18000aaf3  mov     rdi, [rsp+arg_8]
0x18000aaf8  retn
```

# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000bf5c`
- end: `0x18000bffc`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `160`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a904`
- `0x18000c03c`

## callees

- `0x18000bf5c`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, char *a3)
{
  __int64 v4; // r9
  unsigned __int16 *v5; // rax
  __int64 v6; // r8
  __int64 result; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  char *v11; // r10
  unsigned __int16 v12; // r8
  unsigned __int16 *v13; // rax

  v4 = 260;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = (260 - v4) & -(__int64)(v4 != 0);
  result = v4 == 0 ? 0x80070057 : 0;
  if ( v4 )
  {
    v8 = &a1[v6];
    v9 = 260 - v6;
    if ( 260 != v6 )
    {
      v10 = 2147483646;
      v11 = (char *)(a3 - (char *)v8);
      do
      {
        if ( !v10 )
          break;
        v12 = *(unsigned __int16 *)((char *)v8 + (_QWORD)v11);
        if ( !v12 )
          break;
        *v8 = v12;
        --v10;
        ++v8;
        --v9;
      }
      while ( v9 );
    }
    v13 = v8 - 1;
    if ( v9 )
      v13 = v8;
    *v13 = 0;
    return v9 == 0 ? 0x8007007A : 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000bf5c  mov     [rsp+arg_0], rbx
0x18000bf61  mov     edx, 104h
0x18000bf66  mov     r10, r8
0x18000bf69  mov     r9d, edx
0x18000bf6c  mov     r11, rcx
0x18000bf6f  mov     rax, rcx
0x18000bf72  xor     ebx, ebx
0x18000bf74  cmp     [rax], bx
0x18000bf77  jz      short loc_18000BF83
0x18000bf79  add     rax, 2
0x18000bf7d  sub     r9, 1
0x18000bf81  jnz     short loc_18000BF74
0x18000bf83  mov     rcx, rdx
0x18000bf86  mov     rax, r9
0x18000bf89  sub     rcx, r9
0x18000bf8c  neg     rax
0x18000bf8f  mov     rax, r9
0x18000bf92  sbb     r8, r8
0x18000bf95  and     r8, rcx
0x18000bf98  neg     rax
0x18000bf9b  sbb     eax, eax
0x18000bf9d  not     eax
0x18000bf9f  and     eax, 80070057h
0x18000bfa4  test    r9, r9
0x18000bfa7  jz      short loc_18000BFF5
0x18000bfa9  lea     rcx, [r11+r8*2]
0x18000bfad  sub     rdx, r8
0x18000bfb0  jz      short loc_18000BFDB
0x18000bfb2  mov     eax, 7FFFFFFEh
0x18000bfb7  sub     r10, rcx
0x18000bfba  test    rax, rax
0x18000bfbd  jz      short loc_18000BFDB
0x18000bfbf  movzx   r8d, word ptr [r10+rcx]
0x18000bfc4  test    r8w, r8w
0x18000bfc8  jz      short loc_18000BFDB
0x18000bfca  mov     [rcx], r8w
0x18000bfce  dec     rax
0x18000bfd1  add     rcx, 2
0x18000bfd5  sub     rdx, 1
0x18000bfd9  jnz     short loc_18000BFBA
0x18000bfdb  test    rdx, rdx
0x18000bfde  lea     rax, [rcx-2]
0x18000bfe2  cmovnz  rax, rcx
0x18000bfe6  neg     rdx
0x18000bfe9  mov     [rax], bx
0x18000bfec  sbb     eax, eax
0x18000bfee  not     eax
0x18000bff0  and     eax, 8007007Ah
0x18000bff5  mov     rbx, [rsp+arg_0]
0x18000bffa  retn
```

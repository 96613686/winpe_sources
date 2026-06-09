# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x180011454`
- end: `0x1800114b6`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eca4`

## callees

- `0x180011454`

## pseudocode

```c
__int64 __fastcall StringCchCopyA(char *a1, unsigned __int64 a2, char *a3)
{
  __int64 result; // rax
  __int64 v4; // rax
  char *v5; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = a1 - 1;
    if ( a2 )
      v5 = a1;
    *v5 = 0;
    return a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180011454  test    rdx, rdx
0x180011457  jz      short loc_1800114A8
0x180011459  cmp     rdx, 7FFFFFFFh
0x180011460  jbe     short loc_180011469
0x180011462  mov     eax, 80070057h
0x180011467  jmp     short loc_1800114B2
0x180011469  mov     eax, 7FFFFFFEh
0x18001146e  test    rax, rax
0x180011471  jz      short loc_18001148D
0x180011473  mov     r9b, [r8]
0x180011476  test    r9b, r9b
0x180011479  jz      short loc_18001148D
0x18001147b  mov     [rcx], r9b
0x18001147e  inc     r8
0x180011481  inc     rcx
0x180011484  dec     rax
0x180011487  sub     rdx, 1
0x18001148b  jnz     short loc_18001146E
0x18001148d  test    rdx, rdx
0x180011490  lea     rax, [rcx-1]
0x180011494  cmovnz  rax, rcx
0x180011498  neg     rdx
0x18001149b  mov     byte ptr [rax], 0
0x18001149e  sbb     eax, eax
0x1800114a0  not     eax
0x1800114a2  and     eax, 8007007Ah
0x1800114a7  retn
0x1800114a8  mov     eax, 80070057h
0x1800114ad  test    rdx, rdx
0x1800114b0  jz      short locret_1800114B5
0x1800114b2  mov     byte ptr [rcx], 0
0x1800114b5  retn
```

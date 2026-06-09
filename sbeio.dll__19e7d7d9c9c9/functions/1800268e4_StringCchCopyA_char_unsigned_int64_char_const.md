# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x1800268e4`
- end: `0x180026946`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c74c`
- `0x1800246a8`
- `0x1800248f8`
- `0x180024c20`
- `0x180024da0`
- `0x180025278`

## callees

- `0x1800268e4`

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
0x1800268e4  test    rdx, rdx
0x1800268e7  jz      short loc_180026938
0x1800268e9  cmp     rdx, 7FFFFFFFh
0x1800268f0  jbe     short loc_1800268F9
0x1800268f2  mov     eax, 80070057h
0x1800268f7  jmp     short loc_180026942
0x1800268f9  mov     eax, 7FFFFFFEh
0x1800268fe  test    rax, rax
0x180026901  jz      short loc_18002691D
0x180026903  mov     r9b, [r8]
0x180026906  test    r9b, r9b
0x180026909  jz      short loc_18002691D
0x18002690b  mov     [rcx], r9b
0x18002690e  inc     r8
0x180026911  inc     rcx
0x180026914  dec     rax
0x180026917  sub     rdx, 1
0x18002691b  jnz     short loc_1800268FE
0x18002691d  test    rdx, rdx
0x180026920  lea     rax, [rcx-1]
0x180026924  cmovnz  rax, rcx
0x180026928  neg     rdx
0x18002692b  mov     byte ptr [rax], 0
0x18002692e  sbb     eax, eax
0x180026930  not     eax
0x180026932  and     eax, 8007007Ah
0x180026937  retn
0x180026938  mov     eax, 80070057h
0x18002693d  test    rdx, rdx
0x180026940  jz      short locret_180026945
0x180026942  mov     byte ptr [rcx], 0
0x180026945  retn
```

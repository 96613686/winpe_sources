# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x18001ac00`
- end: `0x18001ac63`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180019c80`
- `0x18001cb20`
- `0x1800202e0`
- `0x18002309c`
- `0x180023204`
- `0x180024220`
- `0x180024900`

## callees

- `0x18001ac00`

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
0x18001ac00  test    rdx, rdx
0x18001ac03  jz      short loc_18001AC55
0x18001ac05  cmp     rdx, 7FFFFFFFh
0x18001ac0c  jbe     short loc_18001AC15
0x18001ac0e  mov     eax, 80070057h
0x18001ac13  jmp     short loc_18001AC5F
0x18001ac15  mov     eax, 7FFFFFFEh
0x18001ac1a  test    rax, rax
0x18001ac1d  jz      short loc_18001AC39
0x18001ac1f  mov     r9b, [r8]
0x18001ac22  test    r9b, r9b
0x18001ac25  jz      short loc_18001AC39
0x18001ac27  mov     [rcx], r9b
0x18001ac2a  inc     r8
0x18001ac2d  inc     rcx
0x18001ac30  dec     rax
0x18001ac33  sub     rdx, 1
0x18001ac37  jnz     short loc_18001AC1A
0x18001ac39  test    rdx, rdx
0x18001ac3c  lea     rax, [rcx-1]
0x18001ac40  cmovnz  rax, rcx
0x18001ac44  neg     rdx
0x18001ac47  mov     byte ptr [rax], 0
0x18001ac4a  sbb     eax, eax
0x18001ac4c  not     eax
0x18001ac4e  and     eax, 8007007Ah
0x18001ac53  retn
0x18001ac55  mov     eax, 80070057h
0x18001ac5a  test    rdx, rdx
0x18001ac5d  jz      short locret_18001AC62
0x18001ac5f  mov     byte ptr [rcx], 0
0x18001ac62  retn
```

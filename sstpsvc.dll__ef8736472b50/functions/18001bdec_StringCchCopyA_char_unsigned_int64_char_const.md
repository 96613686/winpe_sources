# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x18001bdec`
- end: `0x18001be4f`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019a4c`

## callees

- `0x18001bdec`

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
0x18001bdec  test    rdx, rdx
0x18001bdef  jz      short loc_18001BE41
0x18001bdf1  cmp     rdx, 7FFFFFFFh
0x18001bdf8  jbe     short loc_18001BE01
0x18001bdfa  mov     eax, 80070057h
0x18001bdff  jmp     short loc_18001BE4B
0x18001be01  mov     eax, 7FFFFFFEh
0x18001be06  test    rax, rax
0x18001be09  jz      short loc_18001BE25
0x18001be0b  mov     r9b, [r8]
0x18001be0e  test    r9b, r9b
0x18001be11  jz      short loc_18001BE25
0x18001be13  mov     [rcx], r9b
0x18001be16  inc     r8
0x18001be19  inc     rcx
0x18001be1c  dec     rax
0x18001be1f  sub     rdx, 1
0x18001be23  jnz     short loc_18001BE06
0x18001be25  test    rdx, rdx
0x18001be28  lea     rax, [rcx-1]
0x18001be2c  cmovnz  rax, rcx
0x18001be30  neg     rdx
0x18001be33  mov     byte ptr [rax], 0
0x18001be36  sbb     eax, eax
0x18001be38  not     eax
0x18001be3a  and     eax, 8007007Ah
0x18001be3f  retn
0x18001be41  mov     eax, 80070057h
0x18001be46  test    rdx, rdx
0x18001be49  jz      short locret_18001BE4E
0x18001be4b  mov     byte ptr [rcx], 0
0x18001be4e  retn
```

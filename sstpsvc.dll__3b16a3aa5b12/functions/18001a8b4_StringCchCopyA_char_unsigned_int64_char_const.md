# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x18001a8b4`
- end: `0x18001a916`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018634`

## callees

- `0x18001a8b4`

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
0x18001a8b4  test    rdx, rdx
0x18001a8b7  jz      short loc_18001A908
0x18001a8b9  cmp     rdx, 7FFFFFFFh
0x18001a8c0  jbe     short loc_18001A8C9
0x18001a8c2  mov     eax, 80070057h
0x18001a8c7  jmp     short loc_18001A912
0x18001a8c9  mov     eax, 7FFFFFFEh
0x18001a8ce  test    rax, rax
0x18001a8d1  jz      short loc_18001A8ED
0x18001a8d3  mov     r9b, [r8]
0x18001a8d6  test    r9b, r9b
0x18001a8d9  jz      short loc_18001A8ED
0x18001a8db  mov     [rcx], r9b
0x18001a8de  inc     r8
0x18001a8e1  inc     rcx
0x18001a8e4  dec     rax
0x18001a8e7  sub     rdx, 1
0x18001a8eb  jnz     short loc_18001A8CE
0x18001a8ed  test    rdx, rdx
0x18001a8f0  lea     rax, [rcx-1]
0x18001a8f4  cmovnz  rax, rcx
0x18001a8f8  neg     rdx
0x18001a8fb  mov     byte ptr [rax], 0
0x18001a8fe  sbb     eax, eax
0x18001a900  not     eax
0x18001a902  and     eax, 8007007Ah
0x18001a907  retn
0x18001a908  mov     eax, 80070057h
0x18001a90d  test    rdx, rdx
0x18001a910  jz      short locret_18001A915
0x18001a912  mov     byte ptr [rcx], 0
0x18001a915  retn
```

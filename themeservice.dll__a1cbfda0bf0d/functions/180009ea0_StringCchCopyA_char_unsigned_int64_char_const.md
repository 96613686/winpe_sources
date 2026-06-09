# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x180009ea0`
- end: `0x180009f02`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008fbc`
- `0x18000d524`
- `0x18000f390`

## callees

- `0x180009ea0`

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
0x180009ea0  test    rdx, rdx
0x180009ea3  jz      short loc_180009EF4
0x180009ea5  cmp     rdx, 7FFFFFFFh
0x180009eac  jbe     short loc_180009EB5
0x180009eae  mov     eax, 80070057h
0x180009eb3  jmp     short loc_180009EFE
0x180009eb5  mov     eax, 7FFFFFFEh
0x180009eba  test    rax, rax
0x180009ebd  jz      short loc_180009ED9
0x180009ebf  mov     r9b, [r8]
0x180009ec2  test    r9b, r9b
0x180009ec5  jz      short loc_180009ED9
0x180009ec7  mov     [rcx], r9b
0x180009eca  inc     r8
0x180009ecd  inc     rcx
0x180009ed0  dec     rax
0x180009ed3  sub     rdx, 1
0x180009ed7  jnz     short loc_180009EBA
0x180009ed9  test    rdx, rdx
0x180009edc  lea     rax, [rcx-1]
0x180009ee0  cmovnz  rax, rcx
0x180009ee4  neg     rdx
0x180009ee7  mov     byte ptr [rax], 0
0x180009eea  sbb     eax, eax
0x180009eec  not     eax
0x180009eee  and     eax, 8007007Ah
0x180009ef3  retn
0x180009ef4  mov     eax, 80070057h
0x180009ef9  test    rdx, rdx
0x180009efc  jz      short locret_180009F01
0x180009efe  mov     byte ptr [rcx], 0
0x180009f01  retn
```

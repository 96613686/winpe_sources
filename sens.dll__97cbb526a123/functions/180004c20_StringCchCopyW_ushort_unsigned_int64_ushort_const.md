# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180004c20`
- end: `0x180004c8d`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001850`
- `0x180003190`
- `0x1800049e0`
- `0x1800098f4`

## callees

- `0x180004c20`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  unsigned __int16 *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = v3 - 1;
    if ( a2 )
      v5 = v3;
    *v5 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004c20  mov     r9, rcx
0x180004c23  test    rdx, rdx
0x180004c26  jz      short loc_180004C7C
0x180004c28  cmp     rdx, 7FFFFFFFh
0x180004c2f  ja      short loc_180004C75
0x180004c31  mov     eax, 7FFFFFFEh
0x180004c36  test    rax, rax
0x180004c39  jz      short loc_180004C59
0x180004c3b  movzx   ecx, word ptr [r8]
0x180004c3f  test    cx, cx
0x180004c42  jz      short loc_180004C59
0x180004c44  mov     [r9], cx
0x180004c48  add     r8, 2
0x180004c4c  add     r9, 2
0x180004c50  dec     rax
0x180004c53  sub     rdx, 1
0x180004c57  jnz     short loc_180004C36
0x180004c59  test    rdx, rdx
0x180004c5c  lea     rax, [r9-2]
0x180004c60  cmovnz  rax, r9
0x180004c64  xor     ecx, ecx
0x180004c66  test    rdx, rdx
0x180004c69  mov     [rax], cx
0x180004c6c  mov     eax, 8007007Ah
0x180004c71  cmovnz  eax, ecx
0x180004c74  retn
0x180004c75  mov     eax, 80070057h
0x180004c7a  jmp     short loc_180004C86
0x180004c7c  mov     eax, 80070057h
0x180004c81  test    rdx, rdx
0x180004c84  jz      short locret_180004C74
0x180004c86  xor     ecx, ecx
0x180004c88  mov     [r9], cx
0x180004c8c  retn
```

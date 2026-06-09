# SortCompareMemory(char *,ushort,char *,ushort,uchar)

- ea: `0x14002dc68`
- end: `0x14002dce3`
- name: `?SortCompareMemory@@YAJPEADG0GE@Z`
- size: `123`
- prototype: `__int64 __fastcall(char *, unsigned __int16, char *, unsigned __int16, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002da1c`

## callees

- `0x14002dc68`

## pseudocode

```c
__int64 __fastcall SortCompareMemory(char *a1, unsigned __int16 a2, char *a3, unsigned __int16 a4, char a5)
{
  __int64 v5; // r10
  int v6; // eax
  int v7; // edx
  __int64 v8; // rdi
  int v9; // r9d
  int v10; // r11d
  int v11; // ebx

  v5 = a2;
  v6 = a2;
  v7 = a4;
  if ( a5 )
  {
    a1 = &a1[v5 - 1];
    a3 = &a3[a4 - 1];
    if ( (unsigned int)v5 > a4 )
      v6 = a4;
    v8 = -1;
  }
  else
  {
    v8 = 1;
    if ( (unsigned int)v5 > a4 )
      v6 = a4;
  }
  v9 = 0;
  if ( !v6 )
    return (unsigned int)(v5 - v7);
  while ( 1 )
  {
    v10 = (unsigned __int8)*a1;
    v11 = (unsigned __int8)*a3;
    if ( (_BYTE)v10 != (_BYTE)v11 )
      break;
    if ( ++v9 >= v6 )
      return (unsigned int)(v5 - v7);
    a1 += v8;
    a3 += v8;
  }
  return (unsigned int)(v10 - v11);
}

```

## disassembly

```asm
0x14002dc68  mov     [rsp+arg_0], rbx
0x14002dc6d  mov     [rsp+arg_8], rdi
0x14002dc72  cmp     [rsp+arg_20], 0
0x14002dc77  movzx   r10d, dx
0x14002dc7b  mov     eax, r10d
0x14002dc7e  movzx   edx, r9w
0x14002dc82  jz      short loc_14002DC9C
0x14002dc84  dec     rcx
0x14002dc87  dec     r8
0x14002dc8a  add     rcx, r10
0x14002dc8d  add     r8, rdx
0x14002dc90  cmp     r10d, edx
0x14002dc93  cmova   eax, edx
0x14002dc96  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14002dc9a  jmp     short loc_14002DCA7
0x14002dc9c  cmp     r10d, edx
0x14002dc9f  mov     edi, 1
0x14002dca4  cmova   eax, edx
0x14002dca7  xor     r9d, r9d
0x14002dcaa  test    eax, eax
0x14002dcac  jz      short loc_14002DCD2
0x14002dcae  movzx   r11d, byte ptr [rcx]
0x14002dcb2  movzx   ebx, byte ptr [r8]
0x14002dcb6  cmp     r11b, bl
0x14002dcb9  jnz     short loc_14002DCCB
0x14002dcbb  inc     r9d
0x14002dcbe  cmp     r9d, eax
0x14002dcc1  jge     short loc_14002DCD2
0x14002dcc3  add     rcx, rdi
0x14002dcc6  add     r8, rdi
0x14002dcc9  jmp     short loc_14002DCAE
0x14002dccb  mov     eax, r11d
0x14002dcce  sub     eax, ebx
0x14002dcd0  jmp     short loc_14002DCD8
0x14002dcd2  sub     r10d, edx
0x14002dcd5  mov     eax, r10d
0x14002dcd8  mov     rbx, [rsp+arg_0]
0x14002dcdd  mov     rdi, [rsp+arg_8]
0x14002dce2  retn
```

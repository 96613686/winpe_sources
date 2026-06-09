# AddToUnicodeString

- ea: `0x1400012f0`
- end: `0x140001331`
- name: `AddToUnicodeString`
- size: `65`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int16)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001338`
- `0x140001390`
- `0x140001dd0`
- `0x140001fa4`
- `0x1400028a4`

## callees

- `0x1400012f0`
- `0x1400023a0`

## pseudocode

```c
__int64 __fastcall AddToUnicodeString(unsigned __int16 *a1, __int16 a2)
{
  __int64 result; // rax

  if ( *a1 < a1[1] || (result = Realloc(a1), (int)result >= 0) )
  {
    *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * ((unsigned __int64)*a1 >> 1)) = a2;
    *a1 += 2;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400012f0  mov     [rsp+arg_0], rbx
0x1400012f5  push    rdi
0x1400012f6  sub     rsp, 20h
0x1400012fa  movzx   eax, word ptr [rcx+2]
0x1400012fe  movzx   edi, dx
0x140001301  mov     rbx, rcx
0x140001304  cmp     [rcx], ax
0x140001307  jb      short loc_140001312
0x140001309  call    Realloc
0x14000130e  test    eax, eax
0x140001310  js      short loc_140001326
0x140001312  movzx   ecx, word ptr [rbx]
0x140001315  mov     rax, [rbx+8]
0x140001319  shr     rcx, 1
0x14000131c  mov     [rax+rcx*2], di
0x140001320  add     word ptr [rbx], 2
0x140001324  xor     eax, eax
0x140001326  mov     rbx, [rsp+28h+arg_0]
0x14000132b  add     rsp, 20h
0x14000132f  pop     rdi
0x140001330  retn
```

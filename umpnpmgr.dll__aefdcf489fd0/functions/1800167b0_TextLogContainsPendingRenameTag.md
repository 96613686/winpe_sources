# TextLogContainsPendingRenameTag

- ea: `0x1800167b0`
- end: `0x18001680f`
- name: `TextLogContainsPendingRenameTag`
- size: `95`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`

## callees

- `0x18000b890`
- `0x1800167b0`

## pseudocode

```c
__int64 __fastcall TextLogContainsPendingRenameTag(__int64 a1)
{
  unsigned int v1; // ebx
  unsigned int v2; // edi
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  v1 = 0;
  v2 = 0;
  v6 = 0;
  v5 = 0;
  while ( (unsigned int)TextLogEnumerateOpenSections(a1, v2, &v5) )
  {
    if ( !DWORD1(v5) && (v6 & 0x10000) != 0 )
      return 1;
    ++v2;
  }
  return v1;
}

```

## disassembly

```asm
0x1800167b0  mov     [rsp+arg_0], rbx
0x1800167b5  mov     [rsp+arg_8], rsi
0x1800167ba  push    rdi
0x1800167bb  sub     rsp, 40h
0x1800167bf  xor     ebx, ebx
0x1800167c1  xor     edi, edi
0x1800167c3  xor     eax, eax
0x1800167c5  xorps   xmm0, xmm0
0x1800167c8  mov     [rsp+48h+var_18], eax
0x1800167cc  mov     rsi, rcx
0x1800167cf  movups  [rsp+48h+var_28], xmm0
0x1800167d4  lea     r8, [rsp+48h+var_28]
0x1800167d9  mov     edx, edi
0x1800167db  mov     rcx, rsi
0x1800167de  call    TextLogEnumerateOpenSections
0x1800167e3  test    eax, eax
0x1800167e5  jz      short loc_1800167FD
0x1800167e7  cmp     dword ptr [rsp+48h+var_28+4], ebx
0x1800167eb  jnz     short loc_1800167F4
0x1800167ed  test    byte ptr [rsp+48h+var_18+2], 1
0x1800167f2  jnz     short loc_1800167F8
0x1800167f4  inc     edi
0x1800167f6  jmp     short loc_1800167D4
0x1800167f8  mov     ebx, 1
0x1800167fd  mov     rsi, [rsp+48h+arg_8]
0x180016802  mov     eax, ebx
0x180016804  mov     rbx, [rsp+48h+arg_0]
0x180016809  add     rsp, 40h
0x18001680d  pop     rdi
0x18001680e  retn
```

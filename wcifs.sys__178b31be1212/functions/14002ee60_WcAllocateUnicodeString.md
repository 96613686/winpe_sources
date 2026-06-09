# WcAllocateUnicodeString

- ea: `0x14002ee60`
- end: `0x14002ee9d`
- name: `WcAllocateUnicodeString`
- size: `61`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140002520`
- `0x140014ad4`
- `0x140018e28`
- `0x14001e94c`
- `0x140020434`
- `0x140020e60`
- `0x140032550`
- `0x140032928`

## callees

- `0x14002ee60`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002ee75`
- `ntoskrnl!ExAllocatePool2` at `0x14002ee75`

## pseudocode

```c
__int64 __fastcall WcAllocateUnicodeString(unsigned int a1, __int64 a2)
{
  __int64 Pool2; // rax
  __int64 result; // rax

  Pool2 = ExAllocatePool2(256, *(unsigned __int16 *)(a2 + 2), a1);
  *(_QWORD *)(a2 + 8) = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  result = 0;
  *(_WORD *)a2 = 0;
  return result;
}

```

## disassembly

```asm
0x14002ee60  push    rbx
0x14002ee62  sub     rsp, 20h
0x14002ee66  mov     rbx, rdx
0x14002ee69  mov     r8d, ecx
0x14002ee6c  movzx   edx, word ptr [rdx+2]
0x14002ee70  mov     ecx, 100h
0x14002ee75  call    cs:__imp_ExAllocatePool2
0x14002ee7c  nop     dword ptr [rax+rax+00h]
0x14002ee81  mov     [rbx+8], rax
0x14002ee85  test    rax, rax
0x14002ee88  jz      short loc_14002EE96
0x14002ee8a  xor     eax, eax
0x14002ee8c  mov     [rbx], ax
0x14002ee8f  add     rsp, 20h
0x14002ee93  pop     rbx
0x14002ee94  retn
0x14002ee96  mov     eax, 0C000009Ah
0x14002ee9b  jmp     short loc_14002EE8F
```

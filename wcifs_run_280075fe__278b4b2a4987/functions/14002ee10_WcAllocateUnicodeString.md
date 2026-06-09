# WcAllocateUnicodeString

- ea: `0x14002ee10`
- end: `0x14002ee4d`
- name: `WcAllocateUnicodeString`
- size: `61`
- prototype: ``
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
- `0x140032500`
- `0x1400328d8`

## callees

- `0x14002ee10`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002ee25`
- `ntoskrnl!ExAllocatePool2` at `0x14002ee25`

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
0x14002ee10  push    rbx
0x14002ee12  sub     rsp, 20h
0x14002ee16  mov     rbx, rdx
0x14002ee19  mov     r8d, ecx
0x14002ee1c  movzx   edx, word ptr [rdx+2]
0x14002ee20  mov     ecx, 100h
0x14002ee25  call    cs:__imp_ExAllocatePool2
0x14002ee2c  nop     dword ptr [rax+rax+00h]
0x14002ee31  mov     [rbx+8], rax
0x14002ee35  test    rax, rax
0x14002ee38  jz      short loc_14002EE46
0x14002ee3a  xor     eax, eax
0x14002ee3c  mov     [rbx], ax
0x14002ee3f  add     rsp, 20h
0x14002ee43  pop     rbx
0x14002ee44  retn
0x14002ee46  mov     eax, 0C000009Ah
0x14002ee4b  jmp     short loc_14002EE3F
```

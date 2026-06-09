# PrintTaskOpcodeVersionSummary

- ea: `0x14002130c`
- end: `0x1400213a0`
- name: `PrintTaskOpcodeVersionSummary`
- size: `148`
- prototype: `__int64(FILE *Stream, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400277c8`

## callees

- `0x14002130c`

## import_xrefs

- `msvcrt!fwprintf` at `0x14002133b`
- `msvcrt!fwprintf` at `0x14002135b`
- `msvcrt!fwprintf` at `0x140021372`
- `msvcrt!fwprintf` at `0x14002133b`
- `msvcrt!fwprintf` at `0x14002135b`
- `msvcrt!fwprintf` at `0x140021372`
- `msvcrt!fwprintf` at `0x140021399`

## pseudocode

```c
int __fastcall PrintTaskOpcodeVersionSummary(FILE *Stream, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  fwprintf(Stream, L"| %10d   %-20s %-15d ", (unsigned int)a5, a3, *(unsigned __int16 *)(a2 + 30));
  if ( !*(_QWORD *)(a2 + 40) || (_DWORD)a6 )
    fwprintf(Stream, L"%-15d ", *(unsigned __int8 *)(a2 + 29));
  else
    fwprintf(Stream, L"%-15s ");
  return fwprintf(Stream, L"%-15d %38s|\n", *(unsigned __int8 *)(a2 + 26), a4, a5, a6);
}

```

## disassembly

```asm
0x14002130c  mov     [rsp+arg_0], rbx
0x140021311  mov     [rsp+arg_8], rsi
0x140021316  push    rdi
0x140021317  sub     rsp, 30h
0x14002131b  movzx   eax, word ptr [rdx+1Eh]
0x14002131f  mov     rsi, r9
0x140021322  mov     r9, r8
0x140021325  mov     [rsp+38h+var_18], eax
0x140021329  mov     r8d, dword ptr [rsp+38h+arg_20]
0x14002132e  mov     rdi, rdx
0x140021331  lea     rdx, a10d20s15d; "| %10d   %-20s %-15d "
0x140021338  mov     rbx, rcx
0x14002133b  call    cs:__imp_fwprintf
0x140021341  mov     r8, [rdi+28h]
0x140021345  test    r8, r8
0x140021348  jz      short loc_140021363
0x14002134a  cmp     [rsp+38h+arg_28], 0
0x14002134f  jnz     short loc_140021363
0x140021351  lea     rdx, a15s; "%-15s "
0x140021358  mov     rcx, rbx; Stream
0x14002135b  call    cs:__imp_fwprintf
0x140021361  jmp     short loc_140021378
0x140021363  movzx   r8d, byte ptr [rdi+1Dh]
0x140021368  lea     rdx, a15d; "%-15d "
0x14002136f  mov     rcx, rbx; Stream
0x140021372  call    cs:__imp_fwprintf
0x140021378  movzx   r8d, byte ptr [rdi+1Ah]
0x14002137d  lea     rdx, a15d38s; "%-15d %38s|\n"
0x140021384  mov     r9, rsi
0x140021387  mov     rcx, rbx
0x14002138a  mov     rbx, [rsp+38h+arg_0]
0x14002138f  mov     rsi, [rsp+38h+arg_8]
0x140021394  add     rsp, 30h
0x140021398  pop     rdi
0x140021399  jmp     cs:__imp_fwprintf
```

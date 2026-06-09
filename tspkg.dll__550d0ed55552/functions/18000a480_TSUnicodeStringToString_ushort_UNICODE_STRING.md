# TSUnicodeStringToString(ushort * *,_UNICODE_STRING *)

- ea: `0x18000a480`
- end: `0x18000a4ed`
- name: `?TSUnicodeStringToString@@YAJPEAPEAGPEAU_UNICODE_STRING@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 **, struct _UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180006650`
- `0x180012af0`
- `0x180016ac8`
- `0x180016eec`

## callees

- `0x1800032c0`
- `0x18000a480`
- `0x18001c63c`

## pseudocode

```c
__int64 __fastcall TSUnicodeStringToString(unsigned __int16 **a1, struct _UNICODE_STRING *a2)
{
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rdi

  if ( !a1 || !a2 )
    return 3221225485LL;
  if ( a2->Length )
  {
    v4 = (unsigned __int16 *)TSAllocate(a2->Length + 2LL);
    v5 = v4;
    if ( !v4 )
      return 3221225626LL;
    memcpy_0(v4, a2->Buffer, a2->Length);
    *a1 = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a480  mov     [rsp+arg_0], rbx
0x18000a485  mov     [rsp+arg_8], rsi
0x18000a48a  push    rdi
0x18000a48b  sub     rsp, 20h
0x18000a48f  mov     rbx, rdx
0x18000a492  mov     rsi, rcx
0x18000a495  test    rcx, rcx
0x18000a498  jz      short loc_18000A4D8
0x18000a49a  test    rdx, rdx
0x18000a49d  jz      short loc_18000A4D8
0x18000a49f  xor     eax, eax
0x18000a4a1  cmp     ax, [rdx]
0x18000a4a4  jz      short loc_18000A4D4
0x18000a4a6  movzx   ecx, word ptr [rdx]
0x18000a4a9  add     rcx, 2; Size
0x18000a4ad  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x18000a4b2  mov     rdi, rax
0x18000a4b5  test    rax, rax
0x18000a4b8  jnz     short loc_18000A4C1
0x18000a4ba  mov     eax, 0C000009Ah
0x18000a4bf  jmp     short loc_18000A4DD
0x18000a4c1  movzx   r8d, word ptr [rbx]; Size
0x18000a4c5  mov     rcx, rdi; void *
0x18000a4c8  mov     rdx, [rbx+8]; Src
0x18000a4cc  call    memcpy_0
0x18000a4d1  mov     [rsi], rdi
0x18000a4d4  xor     eax, eax
0x18000a4d6  jmp     short loc_18000A4DD
0x18000a4d8  mov     eax, 0C000000Dh
0x18000a4dd  mov     rbx, [rsp+28h+arg_0]
0x18000a4e2  mov     rsi, [rsp+28h+arg_8]
0x18000a4e7  add     rsp, 20h
0x18000a4eb  pop     rdi
0x18000a4ec  retn
```

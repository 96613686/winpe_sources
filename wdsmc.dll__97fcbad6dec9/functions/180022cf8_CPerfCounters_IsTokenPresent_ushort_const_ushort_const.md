# CPerfCounters::IsTokenPresent(ushort const *,ushort const *)

- ea: `0x180022cf8`
- end: `0x180022d4c`
- name: `?IsTokenPresent@CPerfCounters@@IEAAHPEBG0@Z`
- size: `84`
- prototype: `__int64 __fastcall(CPerfCounters *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800094c0`

## callees

- `0x180022cf8`

## import_xrefs

- `msvcrt!iswspace` at `0x180022d16`
- `msvcrt!iswspace` at `0x180022d29`
- `msvcrt!iswspace` at `0x180022d16`
- `msvcrt!iswspace` at `0x180022d29`

## pseudocode

```c
_BOOL8 __fastcall CPerfCounters::IsTokenPresent(CPerfCounters *this, CPerfCounters *a2, const unsigned __int16 *a3)
{
  wint_t v5; // cx
  _BOOL8 result; // rax

  result = 0;
  if ( a2 == this || iswspace(*((_WORD *)a2 - 1)) )
  {
    v5 = *((_WORD *)a2 + (_QWORD)a3);
    if ( !v5 || iswspace(v5) )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180022cf8  mov     [rsp+arg_0], rbx
0x180022cfd  mov     [rsp+arg_8], rsi
0x180022d02  push    rdi
0x180022d03  sub     rsp, 20h
0x180022d07  mov     rdi, r8
0x180022d0a  mov     rbx, rdx
0x180022d0d  cmp     rdx, rcx
0x180022d10  jz      short loc_180022D20
0x180022d12  movzx   ecx, word ptr [rdx-2]; C
0x180022d16  call    cs:__imp_iswspace
0x180022d1c  test    eax, eax
0x180022d1e  jz      short loc_180022D33
0x180022d20  movzx   ecx, word ptr [rbx+rdi*2]; C
0x180022d24  test    cx, cx
0x180022d27  jz      short loc_180022D37
0x180022d29  call    cs:__imp_iswspace
0x180022d2f  test    eax, eax
0x180022d31  jnz     short loc_180022D37
0x180022d33  xor     eax, eax
0x180022d35  jmp     short loc_180022D3C
0x180022d37  mov     eax, 1
0x180022d3c  mov     rbx, [rsp+28h+arg_0]
0x180022d41  mov     rsi, [rsp+28h+arg_8]
0x180022d46  add     rsp, 20h
0x180022d4a  pop     rdi
0x180022d4b  retn
```

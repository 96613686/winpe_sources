# SXWriter::WriteMb32(ulong)

- ea: `0x100409840`
- end: `0x1004098c8`
- name: `?WriteMb32@SXWriter@@IEAAXK@Z`
- size: `136`
- prototype: `void __fastcall(SXWriter *__hidden this, unsigned int)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x1004089c0`
- `0x1004091f0`
- `0x1004092b0`
- `0x100409320`
- `0x1004093d0`
- `0x1004095b0`
- `0x1004098d0`
- `0x100409da0`
- `0x10040a470`
- `0x10040a700`
- `0x10040a980`
- `0x10040aa20`
- `0x10040ace0`

## callees

- `0x1004086f0`
- `0x100409840`

## pseudocode

```c
void __fastcall SXWriter::WriteMb32(SXWriter *this, unsigned int a2)
{
  int i; // edi
  char v5; // al
  char v6; // cl
  char v7; // bp
  _BYTE *v8; // rax

  for ( i = 0; i <= 4 && a2 || !i; ++i )
  {
    v5 = a2;
    a2 >>= 7;
    v6 = v5 & 0x7F;
    v7 = v5 & 0x7F | 0x80;
    v8 = (_BYTE *)*((_QWORD *)this + 38);
    if ( !a2 )
      v7 = v6;
    if ( v8 == *((_BYTE **)this + 39) )
    {
      SXWriter::writeBuffer(this);
      v8 = (_BYTE *)*((_QWORD *)this + 38);
    }
    *v8 = v7;
    ++*((_QWORD *)this + 38);
  }
}

```

## disassembly

```asm
0x100409840  mov     [rsp+arg_8], rbx
0x100409845  mov     [rsp+arg_10], rsi
0x10040984a  push    rdi
0x10040984b  sub     rsp, 20h
0x10040984f  mov     esi, edx
0x100409851  mov     [rsp+28h+arg_0], rbp
0x100409856  mov     rbx, rcx
0x100409859  xor     edi, edi
0x10040985b  nop     dword ptr [rax+rax+00h]
0x100409860  cmp     edi, 4
0x100409863  jg      short loc_100409869
0x100409865  test    esi, esi
0x100409867  jnz     short loc_10040986D
0x100409869  test    edi, edi
0x10040986b  jnz     short loc_1004098B3
0x10040986d  movzx   eax, sil
0x100409871  shr     esi, 7
0x100409874  and     al, 7Fh
0x100409876  movzx   ecx, al
0x100409879  movzx   eax, cl
0x10040987c  or      al, 80h
0x10040987e  test    esi, esi
0x100409880  movzx   ebp, al
0x100409883  mov     rax, [rbx+130h]
0x10040988a  cmovz   ebp, ecx
0x10040988d  cmp     rax, [rbx+138h]
0x100409894  jnz     short loc_1004098A5
0x100409896  mov     rcx, rbx; this
0x100409899  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040989e  mov     rax, [rbx+130h]
0x1004098a5  mov     [rax], bpl
0x1004098a8  inc     qword ptr [rbx+130h]
0x1004098af  inc     edi
0x1004098b1  jmp     short loc_100409860
0x1004098b3  mov     rbp, [rsp+28h+arg_0]
0x1004098b8  mov     rbx, [rsp+28h+arg_8]
0x1004098bd  mov     rsi, [rsp+28h+arg_10]
0x1004098c2  add     rsp, 20h
0x1004098c6  pop     rdi
0x1004098c7  retn
```

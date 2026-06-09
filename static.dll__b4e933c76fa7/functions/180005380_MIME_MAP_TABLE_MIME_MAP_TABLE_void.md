# MIME_MAP_TABLE::~MIME_MAP_TABLE(void)

- ea: `0x180005380`
- end: `0x1800053db`
- name: `??1MIME_MAP_TABLE@@EEAA@XZ`
- size: `91`
- prototype: `void __fastcall(MIME_MAP_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005410`

## callees

- `0x180005380`
- `0x1800053e4`

## pseudocode

```c
void __fastcall MIME_MAP_TABLE::~MIME_MAP_TABLE(MIME_MAP_TABLE *this, unsigned int a2)
{
  __int64 i; // rbx
  MIME_MAP_ENTRY *v4; // rdi
  MIME_MAP_ENTRY *v5; // rcx

  *(_QWORD *)this = &MIME_MAP_TABLE::`vftable';
  for ( i = 0; i != 131; ++i )
  {
    v4 = (MIME_MAP_ENTRY *)*((_QWORD *)this + i + 1);
    *((_QWORD *)this + i + 1) = 0;
    while ( v4 )
    {
      v5 = v4;
      v4 = (MIME_MAP_ENTRY *)*((_QWORD *)v4 + 1);
      MIME_MAP_ENTRY::`scalar deleting destructor'(v5, a2);
    }
  }
}

```

## disassembly

```asm
0x180005380  mov     [rsp+arg_0], rbx
0x180005385  mov     [rsp+arg_8], rsi
0x18000538a  push    rdi
0x18000538b  sub     rsp, 20h
0x18000538f  lea     rax, ??_7MIME_MAP_TABLE@@6B@; const MIME_MAP_TABLE::`vftable'
0x180005396  mov     rsi, rcx
0x180005399  mov     [rcx], rax
0x18000539c  xor     ebx, ebx
0x18000539e  mov     rdi, [rsi+rbx*8+8]
0x1800053a3  mov     qword ptr [rsi+rbx*8+8], 0
0x1800053ac  jmp     short loc_1800053BA
0x1800053ae  mov     rcx, rdi; this
0x1800053b1  mov     rdi, [rdi+8]
0x1800053b5  call    ??_GMIME_MAP_ENTRY@@QEAAPEAXI@Z; MIME_MAP_ENTRY::`scalar deleting destructor'(uint)
0x1800053ba  test    rdi, rdi
0x1800053bd  jnz     short loc_1800053AE
0x1800053bf  inc     rbx
0x1800053c2  cmp     rbx, 83h
0x1800053c9  jnz     short loc_18000539E
0x1800053cb  mov     rbx, [rsp+28h+arg_0]
0x1800053d0  mov     rsi, [rsp+28h+arg_8]
0x1800053d5  add     rsp, 20h
0x1800053d9  pop     rdi
0x1800053da  retn
```

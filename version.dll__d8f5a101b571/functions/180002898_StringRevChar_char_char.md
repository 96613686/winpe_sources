# StringRevChar(char *,char)

- ea: `0x180002898`
- end: `0x1800028fb`
- name: `?StringRevChar@@YAPEADPEADD@Z`
- size: `99`
- prototype: `char *__fastcall(char *Buf1, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001f80`

## callees

- `0x180001d60`
- `0x180002898`
- `0x180003176`

## pseudocode

```c
char *__fastcall StringRevChar(char *Buf1)
{
  char *v1; // rbx
  char *v2; // rdi
  char *v3; // rax
  bool i; // zf
  const char *v5; // rsi
  char Buf2[24]; // [rsp+20h] [rbp-18h] BYREF

  v1 = Buf1;
  Buf2[0] = 92;
  v2 = 0;
  v3 = VerCharNextA(Buf1);
  for ( i = *v1 == 0; ; i = *v5 == 0 )
  {
    v5 = v3;
    if ( i )
      break;
    if ( !memcmp_0(v1, Buf2, (int)v3 - (int)v1) )
      v2 = v1;
    v1 = (char *)v5;
    v3 = VerCharNextA(v5);
  }
  return v2;
}

```

## disassembly

```asm
0x180002898  mov     [rsp+arg_0], rbx
0x18000289d  mov     [rsp+arg_8], rsi
0x1800028a2  push    rdi
0x1800028a3  sub     rsp, 30h
0x1800028a7  mov     rbx, rcx
0x1800028aa  mov     [rsp+38h+Buf2], 5Ch ; '\'
0x1800028af  xor     edi, edi
0x1800028b1  call    ?VerCharNextA@@YAPEADPEBD@Z; VerCharNextA(char const *)
0x1800028b6  cmp     [rbx], dil
0x1800028b9  jmp     short loc_1800028E3
0x1800028bb  mov     eax, esi
0x1800028bd  lea     rdx, [rsp+38h+Buf2]; Buf2
0x1800028c2  sub     eax, ebx
0x1800028c4  mov     rcx, rbx; Buf1
0x1800028c7  movsxd  r8, eax; Size
0x1800028ca  call    memcmp_0
0x1800028cf  test    eax, eax
0x1800028d1  mov     rcx, rsi; char *
0x1800028d4  cmovz   rdi, rbx
0x1800028d8  mov     rbx, rsi
0x1800028db  call    ?VerCharNextA@@YAPEADPEBD@Z; VerCharNextA(char const *)
0x1800028e0  cmp     byte ptr [rbx], 0
0x1800028e3  mov     rsi, rax
0x1800028e6  jnz     short loc_1800028BB
0x1800028e8  mov     rbx, [rsp+38h+arg_0]
0x1800028ed  mov     rax, rdi
0x1800028f0  mov     rsi, [rsp+38h+arg_8]
0x1800028f5  add     rsp, 30h
0x1800028f9  pop     rdi
0x1800028fa  retn
```

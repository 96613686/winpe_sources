# SymCryptEcpointCreateEx

- ea: `0x180029364`
- end: `0x180029419`
- name: `SymCryptEcpointCreateEx`
- size: `181`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180023e94`
- `0x1800249c0`
- `0x180024ac0`
- `0x180024be8`
- `0x180025888`
- `0x180026108`
- `0x180029420`
- `0x180029548`
- `0x180029fa0`
- `0x18002a4b0`
- `0x18002ab10`
- `0x18002efe8`
- `0x18002f1c0`

## callees

- `0x180029364`

## pseudocode

```c
_BYTE *__fastcall SymCryptEcpointCreateEx(_BYTE *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  _BYTE *v4; // r11
  __int64 v5; // rdi
  _BYTE *v6; // r10
  unsigned int v7; // edx
  __int64 v9; // rcx

  v4 = 0;
  if ( a2 && a4 )
  {
    v5 = *(unsigned int *)(a3 + 36);
    v6 = a1 + 32;
    v7 = 0;
    v4 = a1;
    while ( v7 < a4 )
    {
      v9 = (unsigned int)((*(_DWORD *)(*(_QWORD *)(a3 + 616) + 4LL) << 6) - 64);
      *(_QWORD *)&v6[v9] = 0;
      *(_QWORD *)&v6[v9 + 8] = 0;
      *(_QWORD *)&v6[v9 + 16] = 0;
      *(_QWORD *)&v6[v9 + 24] = 0;
      *(_QWORD *)&v6[v9 + 32] = 0;
      *(_QWORD *)&v6[v9 + 40] = 0;
      *(_QWORD *)&v6[v9 + 48] = 0;
      *(_QWORD *)&v6[v9 + 56] = 0;
      if ( !v6 )
        return 0;
      v6 += v5;
      ++v7;
    }
    *a1 = 0;
    *((_QWORD *)v4 + 1) = a3;
  }
  return v4;
}

```

## disassembly

```asm
0x180029364  mov     [rsp+arg_0], rbx
0x180029369  mov     [rsp+arg_8], rdi
0x18002936e  xor     r11d, r11d
0x180029371  mov     r10, rcx
0x180029374  test    rdx, rdx
0x180029377  jz      loc_18002940A
0x18002937d  test    r9d, r9d
0x180029380  jz      loc_18002940A
0x180029386  mov     edi, [r8+24h]
0x18002938a  add     r10, 20h ; ' '
0x18002938e  xor     edx, edx
0x180029390  mov     rbx, rcx
0x180029393  mov     r11, rcx
0x180029396  cmp     edx, r9d
0x180029399  jnb     short loc_180029403
0x18002939b  mov     rax, [r8+268h]
0x1800293a2  mov     ecx, [rax+4]
0x1800293a5  shl     ecx, 6
0x1800293a8  sub     ecx, 40h ; '@'
0x1800293ab  mov     qword ptr [rcx+r10], 0
0x1800293b3  mov     qword ptr [rcx+r10+8], 0
0x1800293bc  mov     qword ptr [rcx+r10+10h], 0
0x1800293c5  mov     qword ptr [rcx+r10+18h], 0
0x1800293ce  mov     qword ptr [rcx+r10+20h], 0
0x1800293d7  mov     qword ptr [rcx+r10+28h], 0
0x1800293e0  mov     qword ptr [rcx+r10+30h], 0
0x1800293e9  mov     qword ptr [rcx+r10+38h], 0
0x1800293f2  test    r10, r10
0x1800293f5  jz      short loc_1800293FE
0x1800293f7  add     r10, rdi
0x1800293fa  inc     edx
0x1800293fc  jmp     short loc_180029396
0x1800293fe  xor     r11d, r11d
0x180029401  jmp     short loc_18002940A
0x180029403  mov     byte ptr [rbx], 0
0x180029406  mov     [r11+8], r8
0x18002940a  mov     rbx, [rsp+arg_0]
0x18002940f  mov     rax, r11
0x180029412  mov     rdi, [rsp+arg_8]
0x180029417  retn
```

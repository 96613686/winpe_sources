# WcParseNextPathComponentName

- ea: `0x14002f3d8`
- end: `0x14002f46b`
- name: `WcParseNextPathComponentName`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140026210`

## callees

- `0x14002f3d8`

## pseudocode

```c
__int64 __fastcall WcParseNextPathComponentName(unsigned __int16 *a1, __int64 a2, bool *a3)
{
  _WORD *v3; // r10
  int v5; // r9d
  bool v6; // cl
  unsigned __int16 i; // dx
  __int16 v8; // dx
  __int16 v9; // dx
  __int64 result; // rax

  v3 = (_WORD *)*((_QWORD *)a1 + 1);
  if ( *v3 != 92 )
    return 3221225485LL;
  v5 = *a1;
  if ( v3[((unsigned __int64)*a1 >> 1) - 1] == 92 && v5 == 2 )
    return 3221225485LL;
  v6 = 0;
  for ( i = 4; i <= (unsigned __int16)v5; i += 2 )
  {
    if ( v3[((unsigned __int64)i >> 1) - 1] == 92 )
    {
      v6 = i == (unsigned __int16)v5;
      break;
    }
  }
  v8 = i - 2;
  *(_QWORD *)(a2 + 8) = v3 + 1;
  if ( v8 == (_WORD)v5 )
    v6 = 1;
  v9 = v8 - 2;
  *(_WORD *)a2 = v9;
  result = 0;
  *(_WORD *)(a2 + 2) = v9;
  *a3 = v6;
  return result;
}

```

## disassembly

```asm
0x14002f3d8  mov     [rsp+arg_0], rdi
0x14002f3dd  mov     r10, [rcx+8]
0x14002f3e1  mov     r11, rdx
0x14002f3e4  cmp     word ptr [r10], 5Ch ; '\'
0x14002f3e9  jnz     short loc_14002F45F
0x14002f3eb  movzx   r9d, word ptr [rcx]
0x14002f3ef  mov     eax, r9d
0x14002f3f2  shr     rax, 1
0x14002f3f5  cmp     word ptr [r10+rax*2-2], 5Ch ; '\'
0x14002f3fc  jnz     short loc_14002F404
0x14002f3fe  cmp     r9d, 2
0x14002f402  jz      short loc_14002F45F
0x14002f404  xor     cl, cl
0x14002f406  mov     edx, 4
0x14002f40b  mov     edi, 1
0x14002f410  cmp     dx, r9w
0x14002f414  ja      short loc_14002F435
0x14002f416  movzx   eax, dx
0x14002f419  shr     rax, 1
0x14002f41c  cmp     word ptr [r10+rax*2-2], 5Ch ; '\'
0x14002f423  jz      short loc_14002F42B
0x14002f425  add     dx, 2
0x14002f429  jmp     short loc_14002F40B
0x14002f42b  cmp     dx, r9w
0x14002f42f  movzx   ecx, cl
0x14002f432  cmovz   ecx, edi
0x14002f435  sub     dx, 2
0x14002f439  movzx   ecx, cl
0x14002f43c  cmp     dx, r9w
0x14002f440  lea     rax, [r10+2]
0x14002f444  mov     [r11+8], rax
0x14002f448  cmovz   ecx, edi
0x14002f44b  sub     dx, 2
0x14002f44f  mov     [r11], dx
0x14002f453  xor     eax, eax
0x14002f455  mov     [r11+2], dx
0x14002f45a  mov     [r8], cl
0x14002f45d  jmp     short loc_14002F464
0x14002f45f  mov     eax, 0C000000Dh
0x14002f464  mov     rdi, [rsp+arg_0]
0x14002f469  retn
```

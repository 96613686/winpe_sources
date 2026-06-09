# WcParseNextPathComponentName

- ea: `0x14002f428`
- end: `0x14002f4bb`
- name: `WcParseNextPathComponentName`
- size: `147`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140026260`

## callees

- `0x14002f428`

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
0x14002f428  mov     [rsp+arg_0], rdi
0x14002f42d  mov     r10, [rcx+8]
0x14002f431  mov     r11, rdx
0x14002f434  cmp     word ptr [r10], 5Ch ; '\'
0x14002f439  jnz     short loc_14002F4AF
0x14002f43b  movzx   r9d, word ptr [rcx]
0x14002f43f  mov     eax, r9d
0x14002f442  shr     rax, 1
0x14002f445  cmp     word ptr [r10+rax*2-2], 5Ch ; '\'
0x14002f44c  jnz     short loc_14002F454
0x14002f44e  cmp     r9d, 2
0x14002f452  jz      short loc_14002F4AF
0x14002f454  xor     cl, cl
0x14002f456  mov     edx, 4
0x14002f45b  mov     edi, 1
0x14002f460  cmp     dx, r9w
0x14002f464  ja      short loc_14002F485
0x14002f466  movzx   eax, dx
0x14002f469  shr     rax, 1
0x14002f46c  cmp     word ptr [r10+rax*2-2], 5Ch ; '\'
0x14002f473  jz      short loc_14002F47B
0x14002f475  add     dx, 2
0x14002f479  jmp     short loc_14002F45B
0x14002f47b  cmp     dx, r9w
0x14002f47f  movzx   ecx, cl
0x14002f482  cmovz   ecx, edi
0x14002f485  sub     dx, 2
0x14002f489  movzx   ecx, cl
0x14002f48c  cmp     dx, r9w
0x14002f490  lea     rax, [r10+2]
0x14002f494  mov     [r11+8], rax
0x14002f498  cmovz   ecx, edi
0x14002f49b  sub     dx, 2
0x14002f49f  mov     [r11], dx
0x14002f4a3  xor     eax, eax
0x14002f4a5  mov     [r11+2], dx
0x14002f4aa  mov     [r8], cl
0x14002f4ad  jmp     short loc_14002F4B4
0x14002f4af  mov     eax, 0C000000Dh
0x14002f4b4  mov     rdi, [rsp+arg_0]
0x14002f4b9  retn
```

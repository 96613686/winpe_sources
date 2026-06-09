# WsUseCheckLocal

- ea: `0x18000c24c`
- end: `0x18000c2e7`
- name: `WsUseCheckLocal`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180001750`
- `0x18002be90`

## callees

- `0x18000c24c`

## import_xrefs

- `netutils!NetpwPathCanonicalize` at `0x18000c2b5`
- `netutils!NetpwPathCanonicalize` at `0x18000c2b5`
- `netutils!NetpwPathType` at `0x18000c26c`
- `netutils!NetpwPathType` at `0x18000c26c`

## pseudocode

```c
__int64 __fastcall WsUseCheckLocal(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  int v8; // [rsp+78h] [rbp+20h] BYREF

  v8 = 0;
  result = NetpwPathType(a1, &v8, 0);
  if ( !(_DWORD)result )
  {
    if ( ((v8 - 0x4000) & 0xFFFFFFCF) != 0 || v8 == 16432 )
    {
      return 87;
    }
    else
    {
      result = NetpwPathCanonicalize(a1, a2, 162, 0, &v8, 0);
      if ( !(_DWORD)result )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)(a2 + 2 * v7) );
        *a3 = v7;
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c24c  push    rbx
0x18000c24e  push    rbp
0x18000c24f  push    rsi
0x18000c250  push    rdi
0x18000c251  sub     rsp, 38h
0x18000c255  mov     rsi, r8
0x18000c258  mov     rbx, rdx
0x18000c25b  xor     ebp, ebp
0x18000c25d  lea     rdx, [rsp+58h+arg_18]
0x18000c262  xor     r8d, r8d
0x18000c265  mov     [rsp+58h+arg_18], ebp
0x18000c269  mov     rdi, rcx
0x18000c26c  call    cs:__imp_NetpwPathType
0x18000c273  nop     dword ptr [rax+rax+00h]
0x18000c278  test    eax, eax
0x18000c27a  jnz     short loc_18000C2D6
0x18000c27c  mov     r9d, [rsp+58h+arg_18]
0x18000c281  lea     eax, [r9-4000h]
0x18000c288  test    eax, 0FFFFFFCFh
0x18000c28d  jnz     short loc_18000C2E0
0x18000c28f  cmp     r9d, 4030h
0x18000c296  jz      short loc_18000C2E0
0x18000c298  lea     rax, [rsp+58h+arg_18]
0x18000c29d  mov     [rsp+58h+var_30], ebp
0x18000c2a1  xor     r9d, r9d
0x18000c2a4  mov     [rsp+58h+var_38], rax
0x18000c2a9  mov     r8d, 0A2h
0x18000c2af  mov     rdx, rbx
0x18000c2b2  mov     rcx, rdi
0x18000c2b5  call    cs:__imp_NetpwPathCanonicalize
0x18000c2bc  nop     dword ptr [rax+rax+00h]
0x18000c2c1  test    eax, eax
0x18000c2c3  jnz     short loc_18000C2D6
0x18000c2c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c2c9  inc     rax
0x18000c2cc  cmp     [rbx+rax*2], bp
0x18000c2d0  jnz     short loc_18000C2C9
0x18000c2d2  mov     [rsi], eax
0x18000c2d4  xor     eax, eax
0x18000c2d6  add     rsp, 38h
0x18000c2da  pop     rdi
0x18000c2db  pop     rsi
0x18000c2dc  pop     rbp
0x18000c2dd  pop     rbx
0x18000c2de  retn
0x18000c2e0  mov     eax, 57h ; 'W'
0x18000c2e5  jmp     short loc_18000C2D6
```

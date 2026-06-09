# CSPList<IParseTreeNode *,IParseTreeNode *>::AddTail(IParseTreeNode *)

- ea: `0x180009c50`
- end: `0x180009d03`
- name: `?AddTail@?$CSPList@PEAUIParseTreeNode@@PEAU1@@@QEAAPEAXPEAUIParseTreeNode@@@Z`
- size: `179`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009e70`
- `0x18000bf40`
- `0x18000c2b8`
- `0x18000c514`

## callees

- `0x180009c50`
- `0x18000ac44`

## pseudocode

```c
_QWORD *__fastcall CSPList<IParseTreeNode *,IParseTreeNode *>::AddTail(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  struct CSPPlex *v5; // rax
  int v6; // r8d
  _QWORD *i; // rcx
  _QWORD *v8; // rdx
  _QWORD *v9; // rax

  v3 = *(_QWORD *)(a1 + 8);
  if ( !*(_QWORD *)(a1 + 24) )
  {
    v5 = CSPPlex::Create((struct CSPPlex **)(a1 + 32), *(_DWORD *)(a1 + 40));
    if ( v5 )
    {
      v6 = *(_DWORD *)(a1 + 40) - 1;
      for ( i = (_QWORD *)((char *)v5 + 24 * v6 + 16); v6 >= 0; --v6 )
      {
        *i = *(_QWORD *)(a1 + 24);
        *(_QWORD *)(a1 + 24) = i;
        i -= 3;
      }
    }
  }
  v8 = *(_QWORD **)(a1 + 24);
  if ( v8 )
  {
    v8[2] = 0;
    *(_QWORD *)(a1 + 24) = **(_QWORD **)(a1 + 24);
    v8[1] = v3;
    *v8 = 0;
    ++*(_DWORD *)(a1 + 16);
    v8[2] = a2;
    v9 = *(_QWORD **)(a1 + 8);
    if ( v9 )
      *v9 = v8;
    else
      *(_QWORD *)a1 = v8;
    *(_QWORD *)(a1 + 8) = v8;
  }
  return v8;
}

```

## disassembly

```asm
0x180009c50  mov     [rsp+arg_0], rbx
0x180009c55  mov     [rsp+arg_8], rsi
0x180009c5a  push    rdi
0x180009c5b  sub     rsp, 20h
0x180009c5f  cmp     qword ptr [rcx+18h], 0
0x180009c64  mov     rdi, rdx
0x180009c67  mov     rsi, [rcx+8]
0x180009c6b  mov     rbx, rcx
0x180009c6e  jnz     short loc_180009CAF
0x180009c70  mov     edx, [rbx+28h]; unsigned int
0x180009c73  add     rcx, 20h ; ' '; struct CSPPlex **
0x180009c77  call    ?Create@CSPPlex@@SAPEAU1@AEAPEAU1@II@Z; CSPPlex::Create(CSPPlex * &,uint,uint)
0x180009c7c  test    rax, rax
0x180009c7f  jz      short loc_180009CAF
0x180009c81  mov     r8d, [rbx+28h]
0x180009c85  sub     r8d, 1
0x180009c89  movsxd  rcx, r8d
0x180009c8c  lea     rcx, [rcx+rcx*2]
0x180009c90  lea     rcx, [rcx+2]
0x180009c94  lea     rcx, [rax+rcx*8]
0x180009c98  js      short loc_180009CAF
0x180009c9a  mov     rax, [rbx+18h]
0x180009c9e  mov     [rcx], rax
0x180009ca1  mov     [rbx+18h], rcx
0x180009ca5  sub     rcx, 18h
0x180009ca9  sub     r8d, 1
0x180009cad  jns     short loc_180009C9A
0x180009caf  mov     rdx, [rbx+18h]
0x180009cb3  test    rdx, rdx
0x180009cb6  jz      short loc_180009CF0
0x180009cb8  xor     eax, eax
0x180009cba  mov     [rdx+10h], rax
0x180009cbe  mov     rax, [rbx+18h]
0x180009cc2  mov     rcx, [rax]
0x180009cc5  mov     [rbx+18h], rcx
0x180009cc9  mov     [rdx+8], rsi
0x180009ccd  mov     qword ptr [rdx], 0
0x180009cd4  inc     dword ptr [rbx+10h]
0x180009cd7  mov     [rdx+10h], rdi
0x180009cdb  mov     rax, [rbx+8]
0x180009cdf  test    rax, rax
0x180009ce2  jz      short loc_180009CE9
0x180009ce4  mov     [rax], rdx
0x180009ce7  jmp     short loc_180009CEC
0x180009ce9  mov     [rbx], rdx
0x180009cec  mov     [rbx+8], rdx
0x180009cf0  mov     rbx, [rsp+28h+arg_0]
0x180009cf5  mov     rax, rdx
0x180009cf8  mov     rsi, [rsp+28h+arg_8]
0x180009cfd  add     rsp, 20h
0x180009d01  pop     rdi
0x180009d02  retn
```

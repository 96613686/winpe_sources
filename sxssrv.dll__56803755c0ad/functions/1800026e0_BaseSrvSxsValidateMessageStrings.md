# BaseSrvSxsValidateMessageStrings

- ea: `0x1800026e0`
- end: `0x1800027f7`
- name: `BaseSrvSxsValidateMessageStrings`
- size: `279`
- prototype: `__int64 __fastcall(const void *, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001d80`

## callees

- `0x1800026e0`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x1800027e9`
- `ntdll!DbgPrintEx` at `0x1800027e9`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000276a`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000276a`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsValidateMessageStrings(const void *a1, int a2, __int64 a3)
{
  __int64 i; // rbx
  unsigned __int16 *v8; // rax
  int v9; // ecx
  _QWORD *v10; // rdx
  char v11; // al
  unsigned __int16 *v12; // r8
  unsigned __int64 v13; // rax
  _WORD *v14; // rcx
  unsigned __int64 v15; // rax

  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (_DWORD)i == a2 )
      return 0;
    v8 = *(unsigned __int16 **)(8 * i + a3);
    if ( v8 )
    {
      v9 = *v8;
      v10 = v8 + 4;
      if ( (_WORD)v9 && !*v10 || (unsigned __int16)v9 > v8[1] || (v9 & 1) != 0 )
        return 3221225485LL;
      if ( *v10 )
        break;
    }
LABEL_13:
    ;
  }
  v11 = CsrValidateMessageBuffer(a1, v10, (unsigned int)(v9 + 2), 1);
  v12 = *(unsigned __int16 **)(8 * i + a3);
  if ( v11 )
  {
    v13 = *v12;
    v14 = (_WORD *)*((_QWORD *)v12 + 1);
    if ( (_WORD)v13 )
    {
      v15 = v13 >> 1;
      if ( v14[v15] && v14[v15 - 1] )
        return 3221225485LL;
    }
    else if ( *v14 )
    {
      return 3221225485LL;
    }
    goto LABEL_13;
  }
  DbgPrintEx(
    0x33u,
    0,
    "SXS: Validation of message buffer 0x%lx failed.\n"
    " Message:%p\n"
    " String %p{Length:0x%x, MaximumLength:0x%x, Buffer:%p}\n",
    i,
    a1,
    v12,
    *v12,
    v12[1],
    *((const void **)v12 + 1));
  return 3221225485LL;
}

```

## disassembly

```asm
0x1800026e0  mov     [rsp+arg_8], rbx
0x1800026e5  mov     [rsp+arg_10], rbp
0x1800026ea  mov     [rsp+arg_18], rdi
0x1800026ef  push    r14
0x1800026f1  sub     rsp, 50h
0x1800026f5  mov     rbp, r8
0x1800026f8  mov     [rsp+58h+arg_0], rsi
0x1800026fd  mov     edi, edx
0x1800026ff  mov     r14, rcx
0x180002702  xor     ebx, ebx
0x180002704  cmp     ebx, edi
0x180002706  jnz     short loc_180002726
0x180002708  xor     eax, eax
0x18000270a  mov     rsi, [rsp+58h+arg_0]
0x18000270f  mov     rbx, [rsp+58h+arg_8]
0x180002714  mov     rbp, [rsp+58h+arg_10]
0x180002719  mov     rdi, [rsp+58h+arg_18]
0x18000271e  add     rsp, 50h
0x180002722  pop     r14
0x180002724  retn
0x180002726  lea     rsi, ds:0[rbx*8]
0x18000272e  mov     rax, [rsi+rbp]
0x180002732  test    rax, rax
0x180002735  jz      short loc_180002795
0x180002737  movzx   ecx, word ptr [rax]
0x18000273a  lea     rdx, [rax+8]
0x18000273e  test    cx, cx
0x180002741  jz      short loc_180002749
0x180002743  cmp     qword ptr [rdx], 0
0x180002747  jz      short loc_1800027A4
0x180002749  cmp     cx, [rax+2]
0x18000274d  ja      short loc_1800027A4
0x18000274f  mov     r8d, ecx
0x180002752  test    cl, 1
0x180002755  jnz     short loc_1800027A4
0x180002757  cmp     qword ptr [rdx], 0
0x18000275b  jz      short loc_180002795
0x18000275d  add     r8d, 2
0x180002761  mov     r9d, 1
0x180002767  mov     rcx, r14
0x18000276a  call    cs:__imp_CsrValidateMessageBuffer
0x180002771  nop     dword ptr [rax+rax+00h]
0x180002776  mov     r8, [rsi+rbp]
0x18000277a  test    al, al
0x18000277c  jz      short loc_1800027B6
0x18000277e  movzx   eax, word ptr [r8]
0x180002782  mov     rcx, [r8+8]
0x180002786  test    ax, ax
0x180002789  jz      short loc_1800027AE
0x18000278b  shr     rax, 1
0x18000278e  cmp     word ptr [rcx+rax*2], 0
0x180002793  jnz     short loc_18000279C
0x180002795  inc     ebx
0x180002797  jmp     loc_180002704
0x18000279c  cmp     word ptr [rcx+rax*2-2], 0
0x1800027a2  jz      short loc_180002795
0x1800027a4  mov     eax, 0C000000Dh
0x1800027a9  jmp     loc_18000270A
0x1800027ae  cmp     word ptr [rcx], 0
0x1800027b2  jnz     short loc_1800027A4
0x1800027b4  jmp     short loc_180002795
0x1800027b6  movzx   ecx, word ptr [r8+2]
0x1800027bb  mov     r9d, ebx
0x1800027be  movzx   edx, word ptr [r8]
0x1800027c2  mov     rax, [r8+8]
0x1800027c6  mov     [rsp+58h+var_18], rax
0x1800027cb  mov     [rsp+58h+var_20], ecx
0x1800027cf  mov     [rsp+58h+var_28], edx
0x1800027d3  xor     edx, edx; Level
0x1800027d5  mov     [rsp+58h+var_30], r8
0x1800027da  lea     r8, Format; "SXS: Validation of message buffer 0x%lx"...
0x1800027e1  mov     [rsp+58h+var_38], r14
0x1800027e6  lea     ecx, [rdx+33h]; ComponentId
0x1800027e9  call    cs:__imp_DbgPrintEx
0x1800027f0  nop     dword ptr [rax+rax+00h]
0x1800027f5  jmp     short loc_1800027A4
```

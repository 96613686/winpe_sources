# BaseSrvSxsValidateMessageStrings

- ea: `0x1800027c0`
- end: `0x1800028c3`
- name: `BaseSrvSxsValidateMessageStrings`
- size: `259`
- prototype: `__int64 __fastcall(const void *, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001e00`

## callees

- `0x1800027c0`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x1800028b5`
- `ntdll!DbgPrintEx` at `0x1800028b5`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180002835`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180002835`

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
    v8 = *(unsigned __int16 **)(a3 + 8 * i);
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
  v12 = *(unsigned __int16 **)(a3 + 8 * i);
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
0x1800027c0  push    rbx
0x1800027c2  push    rbp
0x1800027c3  push    rdi
0x1800027c4  push    r14
0x1800027c6  sub     rsp, 58h
0x1800027ca  mov     r14, r8
0x1800027cd  mov     [rsp+78h+arg_0], rsi
0x1800027d5  mov     edi, edx
0x1800027d7  mov     rbp, rcx
0x1800027da  xor     ebx, ebx
0x1800027dc  cmp     ebx, edi
0x1800027de  jnz     short loc_1800027F5
0x1800027e0  xor     eax, eax
0x1800027e2  mov     rsi, [rsp+78h+arg_0]
0x1800027ea  add     rsp, 58h
0x1800027ee  pop     r14
0x1800027f0  pop     rdi
0x1800027f1  pop     rbp
0x1800027f2  pop     rbx
0x1800027f3  retn
0x1800027f5  mov     rax, [r14+rbx*8]
0x1800027f9  lea     rsi, [r14+rbx*8]
0x1800027fd  test    rax, rax
0x180002800  jz      short loc_18000285F
0x180002802  movzx   ecx, word ptr [rax]
0x180002805  lea     rdx, [rax+8]
0x180002809  test    cx, cx
0x18000280c  jz      short loc_180002814
0x18000280e  cmp     qword ptr [rdx], 0
0x180002812  jz      short loc_18000286E
0x180002814  cmp     cx, [rax+2]
0x180002818  ja      short loc_18000286E
0x18000281a  mov     r8d, ecx
0x18000281d  test    cl, 1
0x180002820  jnz     short loc_18000286E
0x180002822  cmp     qword ptr [rdx], 0
0x180002826  jz      short loc_18000285F
0x180002828  add     r8d, 2
0x18000282c  mov     r9d, 1
0x180002832  mov     rcx, rbp
0x180002835  call    cs:__imp_CsrValidateMessageBuffer
0x18000283c  nop     dword ptr [rax+rax+00h]
0x180002841  mov     r8, [rsi]
0x180002844  test    al, al
0x180002846  jz      short loc_180002880
0x180002848  movzx   eax, word ptr [r8]
0x18000284c  mov     rcx, [r8+8]
0x180002850  test    ax, ax
0x180002853  jz      short loc_180002878
0x180002855  shr     rax, 1
0x180002858  cmp     word ptr [rcx+rax*2], 0
0x18000285d  jnz     short loc_180002866
0x18000285f  inc     ebx
0x180002861  jmp     loc_1800027DC
0x180002866  cmp     word ptr [rcx+rax*2-2], 0
0x18000286c  jz      short loc_18000285F
0x18000286e  mov     eax, 0C000000Dh
0x180002873  jmp     loc_1800027E2
0x180002878  cmp     word ptr [rcx], 0
0x18000287c  jnz     short loc_18000286E
0x18000287e  jmp     short loc_18000285F
0x180002880  movzx   ecx, word ptr [r8+2]
0x180002885  mov     r9d, ebx
0x180002888  movzx   edx, word ptr [r8]
0x18000288c  mov     rax, [r8+8]
0x180002890  mov     [rsp+78h+var_38], rax
0x180002895  mov     [rsp+78h+var_40], ecx
0x180002899  mov     ecx, 33h ; '3'; ComponentId
0x18000289e  mov     [rsp+78h+var_48], edx
0x1800028a2  xor     edx, edx; Level
0x1800028a4  mov     [rsp+78h+var_50], r8
0x1800028a9  lea     r8, Format; "SXS: Validation of message buffer 0x%lx"...
0x1800028b0  mov     [rsp+78h+var_58], rbp
0x1800028b5  call    cs:__imp_DbgPrintEx
0x1800028bc  nop     dword ptr [rax+rax+00h]
0x1800028c1  jmp     short loc_18000286E
```

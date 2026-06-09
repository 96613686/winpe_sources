# CounterTableAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)

- ea: `0x140031fb8`
- end: `0x140032227`
- name: `?CounterTableAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z`
- size: `623`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COUNTER_TABLE *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140032230`

## callees

- `0x140016808`
- `0x140030910`
- `0x140031c54`
- `0x140031d28`
- `0x140031dfc`
- `0x140031ec8`
- `0x140031fb8`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
unsigned int __fastcall CounterTableAttributesCheck(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_COUNTER_TABLE *a3)
{
  __int64 v4; // rcx
  struct _UNICODE_STRING v7; // xmm0
  char v9; // al
  char v10; // al
  char *v11; // rcx
  char v12; // al
  char v13; // al
  struct _UNICODE_STRING v14; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v15; // [rsp+30h] [rbp-10h] BYREF
  int v16; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v17; // [rsp+68h] [rbp+28h] BYREF
  WCHAR *v18; // [rsp+78h] [rbp+38h] BYREF

  v18 = 0;
  v4 = *((_QWORD *)a1 + 3);
  v16 = 0;
  v14 = 0;
  (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 128LL))(v4, &v18, &v16);
  v7 = *a2;
  v14.Buffer = v18;
  v14.MaximumLength = 2 * v16;
  v14.Length = 2 * v16;
  v15 = v7;
  if ( EqualString(&v15, L"name", 0) )
    return CounterTableAttributeTitle(a1, &v14, a3);
  v15 = *a2;
  if ( EqualString(&v15, L"topic", 0) )
  {
    v9 = *((_BYTE *)a3 + 220);
    v17 = 0;
    if ( (v9 & 2) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v17);
      PrintMessage(0x422u, v17);
      return -1073222143;
    }
    v10 = v9 | 2;
    v11 = (char *)a3 + 88;
    goto LABEL_8;
  }
  v15 = *a2;
  if ( EqualString(&v15, L"object", 0) )
  {
    v12 = *((_BYTE *)a3 + 220);
    v17 = 0;
    if ( (v12 & 4) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v17);
      PrintMessage(0x423u, v17);
      return -1073222143;
    }
    v11 = (char *)a3 + 128;
    v10 = v12 | 4;
    *((_BYTE *)a3 + 160) = 0;
    goto LABEL_9;
  }
  v15 = *a2;
  if ( EqualString(&v15, L"level", 0) )
    return CounterTableAttributeLevel(a1, &v14, a3);
  v15 = *a2;
  if ( EqualString(&v15, L"key", 0) )
    return CounterTableAttributeKey(a1, &v14, a3);
  v15 = *a2;
  if ( EqualString(&v15, L"note", 0) )
  {
    v13 = *((_BYTE *)a3 + 220);
    v17 = 0;
    if ( (v13 & 8) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v17);
      PrintMessage(0x428u, v17);
      return -1073222143;
    }
    v10 = v13 | 8;
    v11 = (char *)a3 + 168;
LABEL_8:
    v11[32] = 1;
LABEL_9:
    *((_BYTE *)a3 + 220) = v10;
    RPT_STRING::operator=((__int64)v11, (const void **)&v14);
    return 0;
  }
  v15 = *a2;
  if ( !EqualString(&v15, L"threshold", 0) )
    return 0;
  return CounterTableAttributeThreshold(a1, &v14, a3);
}

```

## disassembly

```asm
0x140031fb8  mov     [rsp-18h+arg_10], rbx
0x140031fbd  push    rbp
0x140031fbe  push    rsi
0x140031fbf  push    rdi
0x140031fc0  mov     rbp, rsp
0x140031fc3  sub     rsp, 40h
0x140031fc7  mov     rdi, rcx
0x140031fca  mov     [rbp+arg_18], 0
0x140031fd2  mov     rcx, [rcx+18h]
0x140031fd6  xorps   xmm0, xmm0
0x140031fd9  mov     [rbp+arg_0], 0
0x140031fe0  mov     rbx, r8
0x140031fe3  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140031fe7  mov     rsi, rdx
0x140031fea  lea     r8, [rbp+arg_0]
0x140031fee  mov     rax, [rcx]
0x140031ff1  lea     rdx, [rbp+arg_18]
0x140031ff5  mov     rax, [rax+80h]
0x140031ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032001  mov     rax, [rbp+arg_18]
0x140032005  lea     rdx, aName_0; "name"
0x14003200c  movups  xmm0, xmmword ptr [rsi]
0x14003200f  mov     [rbp+var_20.Buffer], rax
0x140032013  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032017  movzx   eax, word ptr [rbp+arg_0]
0x14003201b  xor     r8d, r8d; unsigned __int8
0x14003201e  add     ax, ax
0x140032021  mov     [rbp+var_20.MaximumLength], ax
0x140032025  mov     [rbp+var_20.Length], ax
0x140032029  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003202e  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032033  test    al, al
0x140032035  jz      short loc_140032048
0x140032037  mov     r8, rbx; struct _TRACERPT_COUNTER_TABLE *
0x14003203a  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x14003203e  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140032041  call    ?CounterTableAttributeTitle@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z; CounterTableAttributeTitle(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)
0x140032046  jmp     short loc_1400320BE
0x140032048  movups  xmm0, xmmword ptr [rsi]
0x14003204b  xor     r8d, r8d; unsigned __int8
0x14003204e  lea     rdx, aTopic; "topic"
0x140032055  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032059  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003205e  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032063  test    al, al
0x140032065  jz      short loc_1400320CB
0x140032067  mov     al, [rbx+0DCh]
0x14003206d  mov     [rbp+arg_8], 0
0x140032074  test    al, 2
0x140032076  jz      short loc_1400320A3
0x140032078  mov     rcx, [rdi+18h]
0x14003207c  lea     rdx, [rbp+arg_8]
0x140032080  mov     rax, [rcx]
0x140032083  mov     rax, [rax+0A8h]
0x14003208a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003208f  mov     ecx, 422h; unsigned int
0x140032094  mov     edx, [rbp+arg_8]
0x140032097  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003209c  mov     eax, 0C007EE01h
0x1400320a1  jmp     short loc_1400320BE
0x1400320a3  or      al, 2
0x1400320a5  lea     rcx, [rbx+58h]
0x1400320a9  mov     byte ptr [rcx+20h], 1
0x1400320ad  lea     rdx, [rbp+var_20]
0x1400320b1  mov     [rbx+0DCh], al
0x1400320b7  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x1400320bc  xor     eax, eax
0x1400320be  mov     rbx, [rsp+40h+arg_10]
0x1400320c3  add     rsp, 40h
0x1400320c7  pop     rdi
0x1400320c8  pop     rsi
0x1400320c9  pop     rbp
0x1400320ca  retn
0x1400320cb  movups  xmm0, xmmword ptr [rsi]
0x1400320ce  xor     r8d, r8d; unsigned __int8
0x1400320d1  lea     rdx, aObject; "object"
0x1400320d8  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400320dc  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400320e1  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400320e6  test    al, al
0x1400320e8  jz      short loc_14003212B
0x1400320ea  mov     al, [rbx+0DCh]
0x1400320f0  mov     [rbp+arg_8], 0
0x1400320f7  test    al, 4
0x1400320f9  jz      short loc_14003211C
0x1400320fb  mov     rcx, [rdi+18h]
0x1400320ff  lea     rdx, [rbp+arg_8]
0x140032103  mov     rax, [rcx]
0x140032106  mov     rax, [rax+0A8h]
0x14003210d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032112  mov     ecx, 423h
0x140032117  jmp     loc_140032094
0x14003211c  lea     rcx, [rbx+80h]
0x140032123  or      al, 4
0x140032125  mov     byte ptr [rcx+20h], 0
0x140032129  jmp     short loc_1400320AD
0x14003212b  movups  xmm0, xmmword ptr [rsi]
0x14003212e  xor     r8d, r8d; unsigned __int8
0x140032131  lea     rdx, aLevel; "level"
0x140032138  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003213c  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140032141  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032146  test    al, al
0x140032148  jz      short loc_14003215E
0x14003214a  mov     r8, rbx; struct _TRACERPT_COUNTER_TABLE *
0x14003214d  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140032151  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140032154  call    ?CounterTableAttributeLevel@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z; CounterTableAttributeLevel(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)
0x140032159  jmp     loc_1400320BE
0x14003215e  movups  xmm0, xmmword ptr [rsi]
0x140032161  xor     r8d, r8d; unsigned __int8
0x140032164  lea     rdx, aKey; "key"
0x14003216b  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003216f  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140032174  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032179  test    al, al
0x14003217b  jz      short loc_140032191
0x14003217d  mov     r8, rbx; struct _TRACERPT_COUNTER_TABLE *
0x140032180  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140032184  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140032187  call    ?CounterTableAttributeKey@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z; CounterTableAttributeKey(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)
0x14003218c  jmp     loc_1400320BE
0x140032191  movups  xmm0, xmmword ptr [rsi]
0x140032194  xor     r8d, r8d; unsigned __int8
0x140032197  lea     rdx, aNote; "note"
0x14003219e  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400321a2  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400321a7  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400321ac  test    al, al
0x1400321ae  jz      short loc_1400321F0
0x1400321b0  mov     al, [rbx+0DCh]
0x1400321b6  mov     [rbp+arg_8], 0
0x1400321bd  test    al, 8
0x1400321bf  jz      short loc_1400321E2
0x1400321c1  mov     rcx, [rdi+18h]
0x1400321c5  lea     rdx, [rbp+arg_8]
0x1400321c9  mov     rax, [rcx]
0x1400321cc  mov     rax, [rax+0A8h]
0x1400321d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400321d8  mov     ecx, 428h
0x1400321dd  jmp     loc_140032094
0x1400321e2  or      al, 8
0x1400321e4  lea     rcx, [rbx+0A8h]
0x1400321eb  jmp     loc_1400320A9
0x1400321f0  movups  xmm0, xmmword ptr [rsi]
0x1400321f3  xor     r8d, r8d; unsigned __int8
0x1400321f6  lea     rdx, aThreshold; "threshold"
0x1400321fd  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032201  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140032206  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003220b  test    al, al
0x14003220d  jz      loc_1400320BC
0x140032213  mov     r8, rbx; struct _TRACERPT_COUNTER_TABLE *
0x140032216  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x14003221a  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x14003221d  call    ?CounterTableAttributeThreshold@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z; CounterTableAttributeThreshold(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)
0x140032222  jmp     loc_1400320BE
```

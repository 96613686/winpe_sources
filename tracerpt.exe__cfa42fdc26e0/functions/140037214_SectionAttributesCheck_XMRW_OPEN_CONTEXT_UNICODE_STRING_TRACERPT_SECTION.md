# SectionAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_SECTION *)

- ea: `0x140037214`
- end: `0x14003735d`
- name: `?SectionAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_SECTION@@@Z`
- size: `329`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_SECTION *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140037364`

## callees

- `0x140016808`
- `0x140030910`
- `0x14003694c`
- `0x140037050`
- `0x140037124`
- `0x140037214`
- `0x140041010`

## pseudocode

```c
unsigned int __fastcall SectionAttributesCheck(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_SECTION *a3)
{
  __int64 v4; // rcx
  struct _UNICODE_STRING v7; // xmm0
  char v9; // al
  struct _UNICODE_STRING v10; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v11; // [rsp+30h] [rbp-10h] BYREF
  int v12; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v13; // [rsp+68h] [rbp+28h] BYREF
  WCHAR *v14; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  v4 = *((_QWORD *)a1 + 3);
  v12 = 0;
  v10 = 0;
  (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 128LL))(v4, &v14, &v12);
  v7 = *a2;
  v10.Buffer = v14;
  v10.MaximumLength = 2 * v12;
  v10.Length = 2 * v12;
  v11 = v7;
  if ( EqualString(&v11, L"name", 0) )
    return SectionAttributeTitle(a1, &v10, a3);
  v11 = *a2;
  if ( EqualString(&v11, L"key", 0) )
    return SectionAttributeKey(a1, &v10, a3);
  v11 = *a2;
  if ( EqualString(&v11, L"note", 0) )
  {
    v9 = *((_BYTE *)a3 + 192);
    v13 = 0;
    if ( (v9 & 4) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v13);
      PrintMessage(0x40Fu, v13);
      return -1073222143;
    }
    *((_BYTE *)a3 + 192) = v9 | 4;
    *((_BYTE *)a3 + 184) = 1;
    RPT_STRING::operator=((__int64)a3 + 152, (const void **)&v10);
  }
  return 0;
}

```

## disassembly

```asm
0x140037214  mov     [rsp-18h+arg_10], rbx
0x140037219  push    rbp
0x14003721a  push    rsi
0x14003721b  push    rdi
0x14003721c  mov     rbp, rsp
0x14003721f  sub     rsp, 40h
0x140037223  mov     rdi, rcx
0x140037226  mov     [rbp+arg_18], 0
0x14003722e  mov     rcx, [rcx+18h]
0x140037232  xorps   xmm0, xmm0
0x140037235  mov     [rbp+arg_0], 0
0x14003723c  mov     rbx, r8
0x14003723f  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140037243  mov     rsi, rdx
0x140037246  lea     r8, [rbp+arg_0]
0x14003724a  mov     rax, [rcx]
0x14003724d  lea     rdx, [rbp+arg_18]
0x140037251  mov     rax, [rax+80h]
0x140037258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003725d  mov     rax, [rbp+arg_18]
0x140037261  lea     rdx, aName_0; "name"
0x140037268  movups  xmm0, xmmword ptr [rsi]
0x14003726b  mov     [rbp+var_20.Buffer], rax
0x14003726f  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140037273  movzx   eax, word ptr [rbp+arg_0]
0x140037277  xor     r8d, r8d; unsigned __int8
0x14003727a  add     ax, ax
0x14003727d  mov     [rbp+var_20.MaximumLength], ax
0x140037281  mov     [rbp+var_20.Length], ax
0x140037285  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003728a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003728f  test    al, al
0x140037291  jz      short loc_1400372A7
0x140037293  mov     r8, rbx; struct _TRACERPT_SECTION *
0x140037296  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x14003729a  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x14003729d  call    ?SectionAttributeTitle@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_SECTION@@@Z; SectionAttributeTitle(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_SECTION *)
0x1400372a2  jmp     loc_140037350
0x1400372a7  movups  xmm0, xmmword ptr [rsi]
0x1400372aa  xor     r8d, r8d; unsigned __int8
0x1400372ad  lea     rdx, aKey; "key"
0x1400372b4  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400372b8  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400372bd  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400372c2  test    al, al
0x1400372c4  jz      short loc_1400372D7
0x1400372c6  mov     r8, rbx; struct _TRACERPT_SECTION *
0x1400372c9  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x1400372cd  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x1400372d0  call    ?SectionAttributeKey@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_SECTION@@@Z; SectionAttributeKey(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_SECTION *)
0x1400372d5  jmp     short loc_140037350
0x1400372d7  movups  xmm0, xmmword ptr [rsi]
0x1400372da  xor     r8d, r8d; unsigned __int8
0x1400372dd  lea     rdx, aNote; "note"
0x1400372e4  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400372e8  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400372ed  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400372f2  test    al, al
0x1400372f4  jz      short loc_14003734E
0x1400372f6  mov     al, [rbx+0C0h]
0x1400372fc  mov     [rbp+arg_8], 0
0x140037303  test    al, 4
0x140037305  jz      short loc_140037332
0x140037307  mov     rcx, [rdi+18h]
0x14003730b  lea     rdx, [rbp+arg_8]
0x14003730f  mov     rax, [rcx]
0x140037312  mov     rax, [rax+0A8h]
0x140037319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003731e  mov     edx, [rbp+arg_8]
0x140037321  mov     ecx, 40Fh; unsigned int
0x140037326  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003732b  mov     eax, 0C007EE01h
0x140037330  jmp     short loc_140037350
0x140037332  or      al, 4
0x140037334  lea     rcx, [rbx+98h]
0x14003733b  lea     rdx, [rbp+var_20]
0x14003733f  mov     [rbx+0C0h], al
0x140037345  mov     byte ptr [rcx+20h], 1
0x140037349  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x14003734e  xor     eax, eax
0x140037350  mov     rbx, [rsp+40h+arg_10]
0x140037355  add     rsp, 40h
0x140037359  pop     rdi
0x14003735a  pop     rsi
0x14003735b  pop     rbp
0x14003735c  retn
```

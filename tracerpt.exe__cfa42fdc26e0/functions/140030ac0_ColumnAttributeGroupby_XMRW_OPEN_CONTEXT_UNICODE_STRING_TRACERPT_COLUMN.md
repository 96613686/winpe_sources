# ColumnAttributeGroupby(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)

- ea: `0x140030ac0`
- end: `0x140030bf0`
- name: `?ColumnAttributeGroupby@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COLUMN *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400315c8`

## callees

- `0x140016808`
- `0x140030ac0`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ColumnAttributeGroupby(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_COLUMN *a3)
{
  bool v3; // zf
  __int64 v5; // rdi
  char v8; // al
  struct _UNICODE_STRING v9; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF

  v3 = (*((_BYTE *)a3 + 370) & 2) == 0;
  v5 = *((_QWORD *)a1 + 3);
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v10);
    PrintMessage(0x437u, v10);
    return 3221745195LL;
  }
  v8 = *((_BYTE *)a3 + 369);
  if ( (v8 & 0x10) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v10);
    PrintMessage(0x438u, v10);
    return 3221745153LL;
  }
  *((_BYTE *)a3 + 369) = v8 | 0x10;
  v9 = *a2;
  if ( EqualString(&v9, L"true", 0) )
  {
    *((_BYTE *)a3 + 368) |= 0x10u;
    return 0;
  }
  v9 = *a2;
  if ( EqualString(&v9, L"false", 0) )
  {
    *((_BYTE *)a3 + 368) &= ~0x10u;
    return 0;
  }
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v10);
  PrintMessage(0x439u, v10, a2);
  return 3221745184LL;
}

```

## disassembly

```asm
0x140030ac0  mov     [rsp+arg_8], rbx
0x140030ac5  mov     [rsp+arg_10], rsi
0x140030aca  push    rdi
0x140030acb  sub     rsp, 30h
0x140030acf  test    byte ptr [r8+172h], 2
0x140030ad7  mov     rbx, r8
0x140030ada  mov     rdi, [rcx+18h]
0x140030ade  mov     rsi, rdx
0x140030ae1  mov     [rsp+38h+arg_0], 0
0x140030ae9  jz      short loc_140030B1A
0x140030aeb  mov     rax, [rdi]
0x140030aee  lea     rdx, [rsp+38h+arg_0]
0x140030af3  mov     rcx, rdi
0x140030af6  mov     rax, [rax+0A8h]
0x140030afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030b02  mov     edx, [rsp+38h+arg_0]
0x140030b06  mov     ecx, 437h; unsigned int
0x140030b0b  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140030b10  mov     eax, 0C007EE2Bh
0x140030b15  jmp     loc_140030BE0
0x140030b1a  mov     al, [r8+171h]
0x140030b21  test    al, 10h
0x140030b23  jz      short loc_140030B54
0x140030b25  mov     rax, [rdi]
0x140030b28  lea     rdx, [rsp+38h+arg_0]
0x140030b2d  mov     rcx, rdi
0x140030b30  mov     rax, [rax+0A8h]
0x140030b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030b3c  mov     edx, [rsp+38h+arg_0]
0x140030b40  mov     ecx, 438h; unsigned int
0x140030b45  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140030b4a  mov     eax, 0C007EE01h
0x140030b4f  jmp     loc_140030BE0
0x140030b54  or      al, 10h
0x140030b56  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING
0x140030b5b  mov     [r8+171h], al
0x140030b62  xor     r8d, r8d; unsigned __int8
0x140030b65  movups  xmm0, xmmword ptr [rdx]
0x140030b68  lea     rdx, aTrue; "true"
0x140030b6f  movdqu  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x140030b75  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030b7a  test    al, al
0x140030b7c  jz      short loc_140030B87
0x140030b7e  or      byte ptr [rbx+170h], 10h
0x140030b85  jmp     short loc_140030BAF
0x140030b87  movups  xmm0, xmmword ptr [rsi]
0x140030b8a  xor     r8d, r8d; unsigned __int8
0x140030b8d  lea     rdx, aFalse; "false"
0x140030b94  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING
0x140030b99  movdqu  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x140030b9f  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030ba4  test    al, al
0x140030ba6  jz      short loc_140030BB3
0x140030ba8  and     byte ptr [rbx+170h], 0EFh
0x140030baf  xor     eax, eax
0x140030bb1  jmp     short loc_140030BE0
0x140030bb3  mov     rax, [rdi]
0x140030bb6  lea     rdx, [rsp+38h+arg_0]
0x140030bbb  mov     rcx, rdi
0x140030bbe  mov     rax, [rax+0A8h]
0x140030bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030bca  mov     edx, [rsp+38h+arg_0]
0x140030bce  mov     r8, rsi
0x140030bd1  mov     ecx, 439h; unsigned int
0x140030bd6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140030bdb  mov     eax, 0C007EE20h
0x140030be0  mov     rbx, [rsp+38h+arg_8]
0x140030be5  mov     rsi, [rsp+38h+arg_10]
0x140030bea  add     rsp, 30h
0x140030bee  pop     rdi
0x140030bef  retn
```

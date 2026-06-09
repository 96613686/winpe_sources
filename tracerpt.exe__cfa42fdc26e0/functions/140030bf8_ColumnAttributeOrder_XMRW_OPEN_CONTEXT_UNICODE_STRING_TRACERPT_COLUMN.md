# ColumnAttributeOrder(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)

- ea: `0x140030bf8`
- end: `0x140030cef`
- name: `?ColumnAttributeOrder@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COLUMN *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400315c8`

## callees

- `0x140016808`
- `0x140030bf8`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ColumnAttributeOrder(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_COLUMN *a3)
{
  char v3; // al
  __int64 v5; // rdi
  struct _UNICODE_STRING v8; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v9; // [rsp+40h] [rbp+8h] BYREF

  v3 = *((_BYTE *)a3 + 369);
  v5 = *((_QWORD *)a1 + 3);
  v9 = 0;
  if ( (v3 & 0x40) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v9);
    PrintMessage(0x43Eu, v9);
    return 3221745153LL;
  }
  *((_BYTE *)a3 + 369) = v3 | 0x40;
  v8 = *a2;
  if ( EqualString(&v8, L"ascending", 0) )
  {
    *((_BYTE *)a3 + 368) &= ~0x40u;
    return 0;
  }
  v8 = *a2;
  if ( EqualString(&v8, L"descending", 0) )
  {
    *((_BYTE *)a3 + 368) |= 0x40u;
    return 0;
  }
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v9);
  PrintMessage(0x43Fu, v9, a2);
  return 3221745184LL;
}

```

## disassembly

```asm
0x140030bf8  mov     [rsp+arg_8], rbx
0x140030bfd  mov     [rsp+arg_10], rsi
0x140030c02  push    rdi
0x140030c03  sub     rsp, 30h
0x140030c07  mov     al, [r8+171h]
0x140030c0e  mov     rbx, r8
0x140030c11  mov     rdi, [rcx+18h]
0x140030c15  mov     rsi, rdx
0x140030c18  mov     [rsp+38h+arg_0], 0
0x140030c20  test    al, 40h
0x140030c22  jz      short loc_140030C53
0x140030c24  mov     rax, [rdi]
0x140030c27  lea     rdx, [rsp+38h+arg_0]
0x140030c2c  mov     rcx, rdi
0x140030c2f  mov     rax, [rax+0A8h]
0x140030c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030c3b  mov     edx, [rsp+38h+arg_0]
0x140030c3f  mov     ecx, 43Eh; unsigned int
0x140030c44  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140030c49  mov     eax, 0C007EE01h
0x140030c4e  jmp     loc_140030CDF
0x140030c53  or      al, 40h
0x140030c55  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING
0x140030c5a  mov     [r8+171h], al
0x140030c61  xor     r8d, r8d; unsigned __int8
0x140030c64  movups  xmm0, xmmword ptr [rdx]
0x140030c67  lea     rdx, aAscending; "ascending"
0x140030c6e  movdqu  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x140030c74  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030c79  test    al, al
0x140030c7b  jz      short loc_140030C86
0x140030c7d  and     byte ptr [rbx+170h], 0BFh
0x140030c84  jmp     short loc_140030CAE
0x140030c86  movups  xmm0, xmmword ptr [rsi]
0x140030c89  xor     r8d, r8d; unsigned __int8
0x140030c8c  lea     rdx, aDescending; "descending"
0x140030c93  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING
0x140030c98  movdqu  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x140030c9e  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030ca3  test    al, al
0x140030ca5  jz      short loc_140030CB2
0x140030ca7  or      byte ptr [rbx+170h], 40h
0x140030cae  xor     eax, eax
0x140030cb0  jmp     short loc_140030CDF
0x140030cb2  mov     rax, [rdi]
0x140030cb5  lea     rdx, [rsp+38h+arg_0]
0x140030cba  mov     rcx, rdi
0x140030cbd  mov     rax, [rax+0A8h]
0x140030cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030cc9  mov     edx, [rsp+38h+arg_0]
0x140030ccd  mov     r8, rsi
0x140030cd0  mov     ecx, 43Fh; unsigned int
0x140030cd5  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140030cda  mov     eax, 0C007EE20h
0x140030cdf  mov     rbx, [rsp+38h+arg_8]
0x140030ce4  mov     rsi, [rsp+38h+arg_10]
0x140030ce9  add     rsp, 30h
0x140030ced  pop     rdi
0x140030cee  retn
```

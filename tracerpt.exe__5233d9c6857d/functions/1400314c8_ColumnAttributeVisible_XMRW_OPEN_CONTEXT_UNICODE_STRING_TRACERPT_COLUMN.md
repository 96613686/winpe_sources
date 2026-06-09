# ColumnAttributeVisible(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)

- ea: `0x1400314c8`
- end: `0x1400315bf`
- name: `?ColumnAttributeVisible@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z`
- size: `247`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COLUMN *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400315c8`

## callees

- `0x140016808`
- `0x1400314c8`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ColumnAttributeVisible(
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
  if ( (v3 & 4) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v9);
    PrintMessage(0x433u, v9);
    return 3221745153LL;
  }
  *((_BYTE *)a3 + 369) = v3 | 4;
  v8 = *a2;
  if ( EqualString(&v8, L"true", 0) )
  {
    *((_BYTE *)a3 + 368) |= 8u;
    return 0;
  }
  v8 = *a2;
  if ( EqualString(&v8, L"false", 0) )
  {
    *((_BYTE *)a3 + 368) &= ~8u;
    return 0;
  }
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v9);
  PrintMessage(0x434u, v9, a2);
  return 3221745184LL;
}

```

## disassembly

```asm
0x1400314c8  mov     [rsp+arg_8], rbx
0x1400314cd  mov     [rsp+arg_10], rsi
0x1400314d2  push    rdi
0x1400314d3  sub     rsp, 30h
0x1400314d7  mov     al, [r8+171h]
0x1400314de  mov     rbx, r8
0x1400314e1  mov     rdi, [rcx+18h]
0x1400314e5  mov     rsi, rdx
0x1400314e8  mov     [rsp+38h+arg_0], 0
0x1400314f0  test    al, 4
0x1400314f2  jz      short loc_140031523
0x1400314f4  mov     rax, [rdi]
0x1400314f7  lea     rdx, [rsp+38h+arg_0]
0x1400314fc  mov     rcx, rdi
0x1400314ff  mov     rax, [rax+0A8h]
0x140031506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003150b  mov     edx, [rsp+38h+arg_0]
0x14003150f  mov     ecx, 433h; unsigned int
0x140031514  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031519  mov     eax, 0C007EE01h
0x14003151e  jmp     loc_1400315AF
0x140031523  or      al, 4
0x140031525  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING
0x14003152a  mov     [r8+171h], al
0x140031531  xor     r8d, r8d; unsigned __int8
0x140031534  movups  xmm0, xmmword ptr [rdx]
0x140031537  lea     rdx, aTrue; "true"
0x14003153e  movdqu  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x140031544  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031549  test    al, al
0x14003154b  jz      short loc_140031556
0x14003154d  or      byte ptr [rbx+170h], 8
0x140031554  jmp     short loc_14003157E
0x140031556  movups  xmm0, xmmword ptr [rsi]
0x140031559  xor     r8d, r8d; unsigned __int8
0x14003155c  lea     rdx, aFalse; "false"
0x140031563  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING
0x140031568  movdqu  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x14003156e  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031573  test    al, al
0x140031575  jz      short loc_140031582
0x140031577  and     byte ptr [rbx+170h], 0F7h
0x14003157e  xor     eax, eax
0x140031580  jmp     short loc_1400315AF
0x140031582  mov     rax, [rdi]
0x140031585  lea     rdx, [rsp+38h+arg_0]
0x14003158a  mov     rcx, rdi
0x14003158d  mov     rax, [rax+0A8h]
0x140031594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031599  mov     edx, [rsp+38h+arg_0]
0x14003159d  mov     r8, rsi
0x1400315a0  mov     ecx, 434h; unsigned int
0x1400315a5  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400315aa  mov     eax, 0C007EE20h
0x1400315af  mov     rbx, [rsp+38h+arg_8]
0x1400315b4  mov     rsi, [rsp+38h+arg_10]
0x1400315b9  add     rsp, 30h
0x1400315bd  pop     rdi
0x1400315be  retn
```

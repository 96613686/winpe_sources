# ColumnAttributeAlign(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)

- ea: `0x1400309c0`
- end: `0x140030ab7`
- name: `?ColumnAttributeAlign@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COLUMN *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400315c8`

## callees

- `0x140016808`
- `0x1400309c0`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ColumnAttributeAlign(
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
  if ( (v3 & 1) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v9);
    PrintMessage(0x430u, v9);
    return 3221745153LL;
  }
  *((_BYTE *)a3 + 369) = v3 | 1;
  v8 = *a2;
  if ( EqualString(&v8, L"left", 0) )
  {
    *((_BYTE *)a3 + 368) &= ~1u;
    return 0;
  }
  v8 = *a2;
  if ( EqualString(&v8, L"right", 0) )
  {
    *((_BYTE *)a3 + 368) |= 1u;
    return 0;
  }
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v9);
  PrintMessage(0x431u, v9, a2);
  return 3221745184LL;
}

```

## disassembly

```asm
0x1400309c0  mov     [rsp+arg_8], rbx
0x1400309c5  mov     [rsp+arg_10], rsi
0x1400309ca  push    rdi
0x1400309cb  sub     rsp, 30h
0x1400309cf  mov     al, [r8+171h]
0x1400309d6  mov     rbx, r8
0x1400309d9  mov     rdi, [rcx+18h]
0x1400309dd  mov     rsi, rdx
0x1400309e0  mov     [rsp+38h+arg_0], 0
0x1400309e8  test    al, 1
0x1400309ea  jz      short loc_140030A1B
0x1400309ec  mov     rax, [rdi]
0x1400309ef  lea     rdx, [rsp+38h+arg_0]
0x1400309f4  mov     rcx, rdi
0x1400309f7  mov     rax, [rax+0A8h]
0x1400309fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030a03  mov     edx, [rsp+38h+arg_0]
0x140030a07  mov     ecx, 430h; unsigned int
0x140030a0c  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140030a11  mov     eax, 0C007EE01h
0x140030a16  jmp     loc_140030AA7
0x140030a1b  or      al, 1
0x140030a1d  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING
0x140030a22  mov     [r8+171h], al
0x140030a29  xor     r8d, r8d; unsigned __int8
0x140030a2c  movups  xmm0, xmmword ptr [rdx]
0x140030a2f  lea     rdx, aLeft; "left"
0x140030a36  movdqu  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x140030a3c  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030a41  test    al, al
0x140030a43  jz      short loc_140030A4E
0x140030a45  and     byte ptr [rbx+170h], 0FEh
0x140030a4c  jmp     short loc_140030A76
0x140030a4e  movups  xmm0, xmmword ptr [rsi]
0x140030a51  xor     r8d, r8d; unsigned __int8
0x140030a54  lea     rdx, aRight; "right"
0x140030a5b  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING
0x140030a60  movdqu  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x140030a66  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030a6b  test    al, al
0x140030a6d  jz      short loc_140030A7A
0x140030a6f  or      byte ptr [rbx+170h], 1
0x140030a76  xor     eax, eax
0x140030a78  jmp     short loc_140030AA7
0x140030a7a  mov     rax, [rdi]
0x140030a7d  lea     rdx, [rsp+38h+arg_0]
0x140030a82  mov     rcx, rdi
0x140030a85  mov     rax, [rax+0A8h]
0x140030a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030a91  mov     edx, [rsp+38h+arg_0]
0x140030a95  mov     r8, rsi
0x140030a98  mov     ecx, 431h; unsigned int
0x140030a9d  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140030aa2  mov     eax, 0C007EE20h
0x140030aa7  mov     rbx, [rsp+38h+arg_8]
0x140030aac  mov     rsi, [rsp+38h+arg_10]
0x140030ab1  add     rsp, 30h
0x140030ab5  pop     rdi
0x140030ab6  retn
```

# ColumnAttributeSummary(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)

- ea: `0x1400313c4`
- end: `0x1400314c2`
- name: `?ColumnAttributeSummary@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COLUMN *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400315c8`

## callees

- `0x140016808`
- `0x1400313c4`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ColumnAttributeSummary(
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
  if ( (v3 & 8) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v9);
    PrintMessage(0x435u, v9);
    return 3221745153LL;
  }
  *((_BYTE *)a3 + 369) = v3 | 8;
  v8 = *a2;
  if ( EqualString(&v8, L"total", 0) )
  {
    *((_BYTE *)a3 + 368) &= 0xF9u;
    return 0;
  }
  v8 = *a2;
  if ( EqualString(&v8, L"average", 0) )
  {
    *((_BYTE *)a3 + 368) &= ~4u;
    *((_BYTE *)a3 + 368) |= 2u;
    return 0;
  }
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v9);
  PrintMessage(0x436u, v9, a2);
  return 3221745184LL;
}

```

## disassembly

```asm
0x1400313c4  mov     [rsp+arg_8], rbx
0x1400313c9  mov     [rsp+arg_10], rsi
0x1400313ce  push    rdi
0x1400313cf  sub     rsp, 30h
0x1400313d3  mov     al, [r8+171h]
0x1400313da  mov     rbx, r8
0x1400313dd  mov     rdi, [rcx+18h]
0x1400313e1  mov     rsi, rdx
0x1400313e4  mov     [rsp+38h+arg_0], 0
0x1400313ec  test    al, 8
0x1400313ee  jz      short loc_14003141F
0x1400313f0  mov     rax, [rdi]
0x1400313f3  lea     rdx, [rsp+38h+arg_0]
0x1400313f8  mov     rcx, rdi
0x1400313fb  mov     rax, [rax+0A8h]
0x140031402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031407  mov     edx, [rsp+38h+arg_0]
0x14003140b  mov     ecx, 435h; unsigned int
0x140031410  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031415  mov     eax, 0C007EE01h
0x14003141a  jmp     loc_1400314B2
0x14003141f  or      al, 8
0x140031421  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING
0x140031426  mov     [r8+171h], al
0x14003142d  xor     r8d, r8d; unsigned __int8
0x140031430  movups  xmm0, xmmword ptr [rdx]
0x140031433  lea     rdx, aTotal; "total"
0x14003143a  movdqu  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x140031440  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031445  test    al, al
0x140031447  jz      short loc_140031452
0x140031449  and     byte ptr [rbx+170h], 0F9h
0x140031450  jmp     short loc_140031481
0x140031452  movups  xmm0, xmmword ptr [rsi]
0x140031455  xor     r8d, r8d; unsigned __int8
0x140031458  lea     rdx, aAverage; "average"
0x14003145f  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING
0x140031464  movdqu  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x14003146a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003146f  test    al, al
0x140031471  jz      short loc_140031485
0x140031473  and     byte ptr [rbx+170h], 0FBh
0x14003147a  or      byte ptr [rbx+170h], 2
0x140031481  xor     eax, eax
0x140031483  jmp     short loc_1400314B2
0x140031485  mov     rax, [rdi]
0x140031488  lea     rdx, [rsp+38h+arg_0]
0x14003148d  mov     rcx, rdi
0x140031490  mov     rax, [rax+0A8h]
0x140031497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003149c  mov     edx, [rsp+38h+arg_0]
0x1400314a0  mov     r8, rsi
0x1400314a3  mov     ecx, 436h; unsigned int
0x1400314a8  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400314ad  mov     eax, 0C007EE20h
0x1400314b2  mov     rbx, [rsp+38h+arg_8]
0x1400314b7  mov     rsi, [rsp+38h+arg_10]
0x1400314bc  add     rsp, 30h
0x1400314c0  pop     rdi
0x1400314c1  retn
```

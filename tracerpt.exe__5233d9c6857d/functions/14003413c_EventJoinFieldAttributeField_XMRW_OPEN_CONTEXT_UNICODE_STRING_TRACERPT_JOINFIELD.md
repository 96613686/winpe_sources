# EventJoinFieldAttributeField(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_JOINFIELD *)

- ea: `0x14003413c`
- end: `0x140034227`
- name: `?EventJoinFieldAttributeField@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_JOINFIELD@@@Z`
- size: `235`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_JOINFIELD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14003451c`

## callees

- `0x140016808`
- `0x140030910`
- `0x14003413c`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventJoinFieldAttributeField(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_JOINFIELD *a3)
{
  char v3; // al
  __int64 v5; // rsi
  unsigned int v8; // edi
  struct _UNICODE_STRING v9; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v10; // [rsp+70h] [rbp+8h] BYREF

  v3 = *((_BYTE *)a3 + 176);
  v5 = *((_QWORD *)a1 + 3);
  v10 = 0;
  if ( (v3 & 8) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v10);
    PrintMessage(0x450u, v10);
    return 3221745153LL;
  }
  *((_BYTE *)a3 + 32) = 0;
  *((_BYTE *)a3 + 176) = v3 | 8;
  RPT_STRING::operator=(a3, a2);
  v8 = 0;
  while ( 1 )
  {
    v9 = *a2;
    if ( EqualString(&v9, (unsigned __int16 *)*(&g_EventSystemFields + 2 * v8), 0) )
      break;
LABEL_7:
    if ( ++v8 >= 0xD )
      return 0;
  }
  if ( *((_BYTE *)&g_EventSystemFields + 16 * v8 + 9) )
  {
    *((_BYTE *)a3 + 176) |= 0x10u;
    goto LABEL_7;
  }
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v10);
  PrintMessage(0x451u, v10);
  return 3221745188LL;
}

```

## disassembly

```asm
0x14003413c  push    rbx
0x14003413e  push    rbp
0x14003413f  push    rsi
0x140034140  push    rdi
0x140034141  push    r12
0x140034143  push    r14
0x140034145  sub     rsp, 38h
0x140034149  mov     al, [r8+0B0h]
0x140034150  mov     rbx, r8
0x140034153  mov     rsi, [rcx+18h]
0x140034157  mov     rbp, rdx
0x14003415a  mov     [rsp+68h+arg_0], 0
0x140034162  test    al, 8
0x140034164  jz      short loc_140034192
0x140034166  mov     rax, [rsi]
0x140034169  lea     rdx, [rsp+68h+arg_0]
0x14003416e  mov     rcx, rsi
0x140034171  mov     rax, [rax+0A8h]
0x140034178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003417d  mov     edx, [rsp+68h+arg_0]
0x140034181  mov     ecx, 450h; unsigned int
0x140034186  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003418b  mov     eax, 0C007EE01h
0x140034190  jmp     short loc_1400341EE
0x140034192  or      al, 8
0x140034194  mov     byte ptr [r8+20h], 0
0x140034199  mov     rcx, rbx
0x14003419c  mov     [r8+0B0h], al
0x1400341a3  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x1400341a8  xor     edi, edi
0x1400341aa  lea     r12, ?g_EventSystemFields@@3PAU_TRACERPT_SYSTEM_FIELD@@A; _TRACERPT_SYSTEM_FIELD near * g_EventSystemFields
0x1400341b1  movups  xmm0, xmmword ptr [rbp+0]
0x1400341b5  mov     r14d, edi
0x1400341b8  lea     rcx, [rsp+68h+var_48]; struct _UNICODE_STRING
0x1400341bd  add     r14, r14
0x1400341c0  xor     r8d, r8d; unsigned __int8
0x1400341c3  movdqu  xmmword ptr [rsp+68h+var_48.Length], xmm0
0x1400341c9  mov     rdx, [r12+r14*8]; unsigned __int16 *
0x1400341cd  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400341d2  test    al, al
0x1400341d4  jz      short loc_1400341E5
0x1400341d6  cmp     byte ptr [r12+r14*8+9], 0
0x1400341dc  jz      short loc_1400341FB
0x1400341de  or      byte ptr [rbx+0B0h], 10h
0x1400341e5  inc     edi
0x1400341e7  cmp     edi, 0Dh
0x1400341ea  jb      short loc_1400341B1
0x1400341ec  xor     eax, eax
0x1400341ee  add     rsp, 38h
0x1400341f2  pop     r14
0x1400341f4  pop     r12
0x1400341f6  pop     rdi
0x1400341f7  pop     rsi
0x1400341f8  pop     rbp
0x1400341f9  pop     rbx
0x1400341fa  retn
0x1400341fb  mov     rax, [rsi]
0x1400341fe  lea     rdx, [rsp+68h+arg_0]
0x140034203  mov     rcx, rsi
0x140034206  mov     rax, [rax+0A8h]
0x14003420d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034212  mov     edx, [rsp+68h+arg_0]
0x140034216  mov     ecx, 451h; unsigned int
0x14003421b  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034220  mov     eax, 0C007EE24h
0x140034225  jmp     short loc_1400341EE
```

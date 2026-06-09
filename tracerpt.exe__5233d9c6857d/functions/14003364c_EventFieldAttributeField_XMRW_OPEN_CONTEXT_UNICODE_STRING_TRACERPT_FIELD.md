# EventFieldAttributeField(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)

- ea: `0x14003364c`
- end: `0x14003380a`
- name: `?EventFieldAttributeField@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z`
- size: `446`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_FIELD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400339c8`

## callees

- `0x140016808`
- `0x140030910`
- `0x14003364c`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventFieldAttributeField(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_FIELD *a3)
{
  char v3; // al
  __int64 v5; // r14
  __int64 v8; // r15
  __int64 i; // rsi
  unsigned __int8 v10; // al
  __int64 v11; // r14
  struct _UNICODE_STRING v12; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v13; // [rsp+60h] [rbp+30h] BYREF
  __int64 v14; // [rsp+70h] [rbp+40h]

  v3 = *((_BYTE *)a3 + 216);
  v5 = *((_QWORD *)a1 + 3);
  v14 = v5;
  v13 = 0;
  if ( (v3 & 0x20) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v13);
    PrintMessage(0x442u, v13);
    return 3221745153LL;
  }
  else
  {
    v8 = *((_QWORD *)a1 + 10);
    *((_BYTE *)a3 + 216) = v3 | 0x20;
    *((_BYTE *)a3 + 72) = 0;
    RPT_STRING::operator=((char *)a3 + 40, a2);
    for ( i = 0; i != 13; ++i )
    {
      v12 = *a2;
      if ( EqualString(&v12, (unsigned __int16 *)*(&g_EventSystemFields + 2 * i), 0) )
      {
        *((_BYTE *)a3 + 217) |= 1u;
        *((_BYTE *)a3 + 217) ^= (*((_BYTE *)a3 + 217) ^ (2 * *((_BYTE *)&g_EventSystemFields + 16 * i + 8))) & 2;
      }
    }
    v12 = *a2;
    v10 = EqualString(&v12, L"sys:RequestRate", 0);
    v11 = v14;
    if ( v10 || (v12 = *a2, EqualString(&v12, L"sys:AggregateCount", 0)) )
      *((_BYTE *)a3 + 216) = *((_BYTE *)a3 + 216) & 0xBC | 0x40;
    v12 = *a2;
    if ( (EqualString(&v12, L"sys:CPUPercent", 0) || (v12 = *a2, EqualString(&v12, L"sys:ResponseTime", 0)))
      && ((*(_BYTE *)(v8 + 680) & 0x40) == 0 || !*(_BYTE *)(v8 + 208)) )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v11 + 168LL))(v11, &v13);
      PrintMessage(0x444u, v13, a2);
      return 3221745186LL;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x14003364c  mov     [rsp-28h+arg_8], rbx
0x140033651  mov     [rsp-28h+arg_18], rsi
0x140033656  push    rbp
0x140033657  push    rdi
0x140033658  push    r12
0x14003365a  push    r14
0x14003365c  push    r15
0x14003365e  mov     rbp, rsp
0x140033661  sub     rsp, 30h
0x140033665  mov     al, [r8+0D8h]
0x14003366c  mov     rbx, r8
0x14003366f  mov     r14, [rcx+18h]
0x140033673  mov     rdi, rdx
0x140033676  mov     [rbp+arg_10], r14
0x14003367a  mov     [rbp+arg_0], 0
0x140033681  test    al, 20h
0x140033683  jz      short loc_1400336B2
0x140033685  mov     rax, [r14]
0x140033688  lea     rdx, [rbp+arg_0]
0x14003368c  mov     rcx, r14
0x14003368f  mov     rax, [rax+0A8h]
0x140033696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003369b  mov     edx, [rbp+arg_0]
0x14003369e  mov     ecx, 442h; unsigned int
0x1400336a3  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400336a8  mov     eax, 0C007EE01h
0x1400336ad  jmp     loc_1400337F3
0x1400336b2  mov     r15, [rcx+50h]
0x1400336b6  or      al, 20h
0x1400336b8  lea     rcx, [r8+28h]
0x1400336bc  mov     [r8+0D8h], al
0x1400336c3  mov     byte ptr [rcx+20h], 0
0x1400336c7  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x1400336cc  xor     esi, esi
0x1400336ce  lea     r14, ?g_EventSystemFields@@3PAU_TRACERPT_SYSTEM_FIELD@@A; _TRACERPT_SYSTEM_FIELD near * g_EventSystemFields
0x1400336d5  movups  xmm0, xmmword ptr [rdi]
0x1400336d8  mov     r12, rsi
0x1400336db  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400336df  add     r12, r12
0x1400336e2  xor     r8d, r8d; unsigned __int8
0x1400336e5  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400336ea  mov     rdx, [r14+r12*8]; unsigned __int16 *
0x1400336ee  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400336f3  test    al, al
0x1400336f5  jz      short loc_140033717
0x1400336f7  or      byte ptr [rbx+0D9h], 1
0x1400336fe  mov     cl, [rbx+0D9h]
0x140033704  mov     al, [r14+r12*8+8]
0x140033709  add     al, al
0x14003370b  xor     al, cl
0x14003370d  and     al, 2
0x14003370f  xor     al, cl
0x140033711  mov     [rbx+0D9h], al
0x140033717  inc     rsi
0x14003371a  cmp     rsi, 0Dh
0x14003371e  jnz     short loc_1400336D5
0x140033720  movups  xmm0, xmmword ptr [rdi]
0x140033723  xor     r8d, r8d; unsigned __int8
0x140033726  lea     rdx, aSysRequestrate; "sys:RequestRate"
0x14003372d  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033731  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140033736  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003373b  mov     r14, [rbp+arg_10]
0x14003373f  test    al, al
0x140033741  jnz     short loc_140033762
0x140033743  movups  xmm0, xmmword ptr [rdi]
0x140033746  xor     r8d, r8d; unsigned __int8
0x140033749  lea     rdx, aSysAggregateco; "sys:AggregateCount"
0x140033750  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033754  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140033759  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003375e  test    al, al
0x140033760  jz      short loc_140033772
0x140033762  mov     al, [rbx+0D8h]
0x140033768  and     al, 0FCh
0x14003376a  or      al, 40h
0x14003376c  mov     [rbx+0D8h], al
0x140033772  movups  xmm0, xmmword ptr [rdi]
0x140033775  xor     r8d, r8d; unsigned __int8
0x140033778  lea     rdx, aSysCpupercent; "sys:CPUPercent"
0x14003377f  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033783  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140033788  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003378d  test    al, al
0x14003378f  jnz     short loc_1400337B0
0x140033791  movups  xmm0, xmmword ptr [rdi]
0x140033794  xor     r8d, r8d; unsigned __int8
0x140033797  lea     rdx, aSysResponsetim; "sys:ResponseTime"
0x14003379e  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400337a2  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400337a7  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400337ac  test    al, al
0x1400337ae  jz      short loc_1400337C4
0x1400337b0  test    byte ptr [r15+2A8h], 40h
0x1400337b8  jz      short loc_1400337C8
0x1400337ba  cmp     byte ptr [r15+0D0h], 0
0x1400337c2  jz      short loc_1400337C8
0x1400337c4  xor     eax, eax
0x1400337c6  jmp     short loc_1400337F3
0x1400337c8  mov     rax, [r14]
0x1400337cb  lea     rdx, [rbp+arg_0]
0x1400337cf  mov     rcx, r14
0x1400337d2  mov     rax, [rax+0A8h]
0x1400337d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400337de  mov     edx, [rbp+arg_0]
0x1400337e1  mov     r8, rdi
0x1400337e4  mov     ecx, 444h; unsigned int
0x1400337e9  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400337ee  mov     eax, 0C007EE22h
0x1400337f3  mov     rbx, [rsp+30h+arg_8]
0x1400337f8  mov     rsi, [rsp+30h+arg_18]
0x1400337fd  add     rsp, 30h
0x140033801  pop     r15
0x140033803  pop     r14
0x140033805  pop     r12
0x140033807  pop     rdi
0x140033808  pop     rbp
0x140033809  retn
```

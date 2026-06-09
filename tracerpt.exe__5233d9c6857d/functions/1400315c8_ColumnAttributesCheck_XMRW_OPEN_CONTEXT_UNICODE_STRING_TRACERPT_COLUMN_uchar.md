# ColumnAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *,uchar)

- ea: `0x1400315c8`
- end: `0x1400318ea`
- name: `?ColumnAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@E@Z`
- size: `802`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COLUMN *, unsigned __int8)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1400318f0`

## callees

- `0x140016808`
- `0x140030910`
- `0x1400309c0`
- `0x140030ac0`
- `0x140030bf8`
- `0x140030cf8`
- `0x14003123c`
- `0x1400313c4`
- `0x1400314c8`
- `0x1400315c8`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
unsigned int __fastcall ColumnAttributesCheck(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_COLUMN *a3,
        unsigned __int8 a4)
{
  __int64 v5; // rcx
  struct _UNICODE_STRING v9; // xmm0
  char v10; // al
  char *v12; // rcx
  char v13; // al
  char v14; // al
  struct _XMRW_OPEN_CONTEXT *v15; // rcx
  WCHAR *v16; // [rsp+20h] [rbp-30h] BYREF
  struct _UNICODE_STRING v17; // [rsp+28h] [rbp-28h] BYREF
  struct _UNICODE_STRING v18; // [rsp+40h] [rbp-10h] BYREF
  int v19; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v20; // [rsp+78h] [rbp+28h] BYREF

  v16 = 0;
  v5 = *((_QWORD *)a1 + 3);
  v19 = 0;
  v17 = 0;
  (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v5 + 128LL))(v5, &v16, &v19);
  v9 = *a2;
  v17.Buffer = v16;
  v17.MaximumLength = 2 * v19;
  v17.Length = 2 * v19;
  v18 = v9;
  if ( EqualString(&v18, L"name", 0) )
  {
    v10 = *((_BYTE *)a3 + 368);
    v20 = 0;
    if ( v10 < 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v20);
      PrintMessage(0x42Fu, v20);
      return -1073222143;
    }
    v12 = (char *)a3 + 16;
    *((_BYTE *)a3 + 368) = v10 | 0x80;
    goto LABEL_6;
  }
  v18 = *a2;
  if ( EqualString(&v18, L"align", 0) )
    return ColumnAttributeAlign(a1, &v17, a3);
  v18 = *a2;
  if ( EqualString(&v18, L"format", 0) )
  {
    v13 = *((_BYTE *)a3 + 369);
    v20 = 0;
    if ( (v13 & 2) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v20);
      PrintMessage(0x432u, v20);
      return -1073222143;
    }
    v12 = (char *)a3 + 56;
    *((_BYTE *)a3 + 369) = v13 | 2;
    *((_BYTE *)a3 + 88) = 0;
    goto LABEL_7;
  }
  v18 = *a2;
  if ( EqualString(&v18, L"visible", 0) )
    return ColumnAttributeVisible(a1, &v17, a3);
  v18 = *a2;
  if ( EqualString(&v18, L"summary", 0) )
    return ColumnAttributeSummary(a1, &v17, a3);
  v18 = *a2;
  if ( EqualString(&v18, L"groupby", 0) )
    return ColumnAttributeGroupby(a1, &v17, a3);
  v18 = *a2;
  if ( EqualString(&v18, L"sort", 0) )
    return ColumnAttributeSort(a1, &v17, a3, a4);
  v18 = *a2;
  if ( EqualString(&v18, L"order", 0) )
    return ColumnAttributeOrder(a1, &v17, a3);
  v18 = *a2;
  if ( EqualString(&v18, L"note", 0) )
  {
    v14 = *((_BYTE *)a3 + 369);
    v20 = 0;
    if ( v14 < 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v20);
      PrintMessage(0x440u, v20);
      return -1073222143;
    }
    v12 = (char *)a3 + 96;
    *((_BYTE *)a3 + 369) = v14 | 0x80;
LABEL_6:
    v12[32] = 1;
LABEL_7:
    RPT_STRING::operator=(v12, &v17);
    return 0;
  }
  v18 = *a2;
  if ( !EqualString(&v18, L"outType", 0) )
    return 0;
  return ColumnAttributeOutType(v15, &v17, a3);
}

```

## disassembly

```asm
0x1400315c8  mov     [rsp-18h+arg_10], rbx
0x1400315cd  mov     [rsp-18h+arg_18], rsi
0x1400315d2  push    rbp
0x1400315d3  push    rdi
0x1400315d4  push    r14
0x1400315d6  mov     rbp, rsp
0x1400315d9  sub     rsp, 50h
0x1400315dd  mov     rdi, rcx
0x1400315e0  mov     [rbp+var_30], 0
0x1400315e8  mov     rcx, [rcx+18h]
0x1400315ec  xorps   xmm0, xmm0
0x1400315ef  mov     [rbp+arg_0], 0
0x1400315f6  mov     rbx, r8
0x1400315f9  movups  xmmword ptr [rbp+var_28.Length], xmm0
0x1400315fd  mov     rsi, rdx
0x140031600  lea     r8, [rbp+arg_0]
0x140031604  mov     rax, [rcx]
0x140031607  lea     rdx, [rbp+var_30]
0x14003160b  mov     r14b, r9b
0x14003160e  mov     rax, [rax+80h]
0x140031615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003161a  mov     rax, [rbp+var_30]
0x14003161e  lea     rdx, aName_0; "name"
0x140031625  movups  xmm0, xmmword ptr [rsi]
0x140031628  mov     [rbp+var_28.Buffer], rax
0x14003162c  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140031630  movzx   eax, word ptr [rbp+arg_0]
0x140031634  xor     r8d, r8d; unsigned __int8
0x140031637  add     ax, ax
0x14003163a  mov     [rbp+var_28.MaximumLength], ax
0x14003163e  mov     [rbp+var_28.Length], ax
0x140031642  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140031647  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003164c  test    al, al
0x14003164e  jz      short loc_1400316BC
0x140031650  mov     al, [rbx+170h]
0x140031656  mov     [rbp+arg_8], 0
0x14003165d  test    al, al
0x14003165f  jns     short loc_14003168C
0x140031661  mov     rcx, [rdi+18h]
0x140031665  lea     rdx, [rbp+arg_8]
0x140031669  mov     rax, [rcx]
0x14003166c  mov     rax, [rax+0A8h]
0x140031673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031678  mov     ecx, 42Fh; unsigned int
0x14003167d  mov     edx, [rbp+arg_8]
0x140031680  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031685  mov     eax, 0C007EE01h
0x14003168a  jmp     short loc_1400316A7
0x14003168c  or      al, 80h
0x14003168e  lea     rcx, [rbx+10h]
0x140031692  mov     [rbx+170h], al
0x140031698  mov     byte ptr [rcx+20h], 1
0x14003169c  lea     rdx, [rbp+var_28]
0x1400316a0  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x1400316a5  xor     eax, eax
0x1400316a7  lea     r11, [rsp+50h+var_s0]
0x1400316ac  mov     rbx, [r11+30h]
0x1400316b0  mov     rsi, [r11+38h]
0x1400316b4  mov     rsp, r11
0x1400316b7  pop     r14
0x1400316b9  pop     rdi
0x1400316ba  pop     rbp
0x1400316bb  retn
0x1400316bc  movups  xmm0, xmmword ptr [rsi]
0x1400316bf  xor     r8d, r8d; unsigned __int8
0x1400316c2  lea     rdx, aAlign; "align"
0x1400316c9  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400316cd  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400316d2  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400316d7  test    al, al
0x1400316d9  jz      short loc_1400316EC
0x1400316db  mov     r8, rbx; struct _TRACERPT_COLUMN *
0x1400316de  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x1400316e2  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x1400316e5  call    ?ColumnAttributeAlign@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z; ColumnAttributeAlign(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)
0x1400316ea  jmp     short loc_1400316A7
0x1400316ec  movups  xmm0, xmmword ptr [rsi]
0x1400316ef  xor     r8d, r8d; unsigned __int8
0x1400316f2  lea     rdx, aFormat; "format"
0x1400316f9  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400316fd  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140031702  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031707  test    al, al
0x140031709  jz      short loc_140031752
0x14003170b  mov     al, [rbx+171h]
0x140031711  mov     [rbp+arg_8], 0
0x140031718  test    al, 2
0x14003171a  jz      short loc_14003173D
0x14003171c  mov     rcx, [rdi+18h]
0x140031720  lea     rdx, [rbp+arg_8]
0x140031724  mov     rax, [rcx]
0x140031727  mov     rax, [rax+0A8h]
0x14003172e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031733  mov     ecx, 432h
0x140031738  jmp     loc_14003167D
0x14003173d  or      al, 2
0x14003173f  lea     rcx, [rbx+38h]
0x140031743  mov     [rbx+171h], al
0x140031749  mov     byte ptr [rcx+20h], 0
0x14003174d  jmp     loc_14003169C
0x140031752  movups  xmm0, xmmword ptr [rsi]
0x140031755  xor     r8d, r8d; unsigned __int8
0x140031758  lea     rdx, aVisible; "visible"
0x14003175f  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140031763  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140031768  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003176d  test    al, al
0x14003176f  jz      short loc_140031785
0x140031771  mov     r8, rbx; struct _TRACERPT_COLUMN *
0x140031774  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x140031778  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x14003177b  call    ?ColumnAttributeVisible@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z; ColumnAttributeVisible(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)
0x140031780  jmp     loc_1400316A7
0x140031785  movups  xmm0, xmmword ptr [rsi]
0x140031788  xor     r8d, r8d; unsigned __int8
0x14003178b  lea     rdx, aSummary; "summary"
0x140031792  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140031796  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003179b  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400317a0  test    al, al
0x1400317a2  jz      short loc_1400317B8
0x1400317a4  mov     r8, rbx; struct _TRACERPT_COLUMN *
0x1400317a7  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x1400317ab  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x1400317ae  call    ?ColumnAttributeSummary@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z; ColumnAttributeSummary(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)
0x1400317b3  jmp     loc_1400316A7
0x1400317b8  movups  xmm0, xmmword ptr [rsi]
0x1400317bb  xor     r8d, r8d; unsigned __int8
0x1400317be  lea     rdx, aGroupby; "groupby"
0x1400317c5  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400317c9  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400317ce  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400317d3  test    al, al
0x1400317d5  jz      short loc_1400317EB
0x1400317d7  mov     r8, rbx; struct _TRACERPT_COLUMN *
0x1400317da  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x1400317de  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x1400317e1  call    ?ColumnAttributeGroupby@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z; ColumnAttributeGroupby(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)
0x1400317e6  jmp     loc_1400316A7
0x1400317eb  movups  xmm0, xmmword ptr [rsi]
0x1400317ee  xor     r8d, r8d; unsigned __int8
0x1400317f1  lea     rdx, aSort; "sort"
0x1400317f8  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400317fc  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140031801  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031806  test    al, al
0x140031808  jz      short loc_140031821
0x14003180a  mov     r9b, r14b; unsigned __int8
0x14003180d  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x140031811  mov     r8, rbx; struct _TRACERPT_COLUMN *
0x140031814  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140031817  call    ?ColumnAttributeSort@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@E@Z; ColumnAttributeSort(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *,uchar)
0x14003181c  jmp     loc_1400316A7
0x140031821  movups  xmm0, xmmword ptr [rsi]
0x140031824  xor     r8d, r8d; unsigned __int8
0x140031827  lea     rdx, aOrder; "order"
0x14003182e  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140031832  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140031837  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003183c  test    al, al
0x14003183e  jz      short loc_140031854
0x140031840  mov     r8, rbx; struct _TRACERPT_COLUMN *
0x140031843  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x140031847  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x14003184a  call    ?ColumnAttributeOrder@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z; ColumnAttributeOrder(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)
0x14003184f  jmp     loc_1400316A7
0x140031854  movups  xmm0, xmmword ptr [rsi]
0x140031857  xor     r8d, r8d; unsigned __int8
0x14003185a  lea     rdx, aNote; "note"
0x140031861  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140031865  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003186a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003186f  test    al, al
0x140031871  jz      short loc_1400318B6
0x140031873  mov     al, [rbx+171h]
0x140031879  mov     [rbp+arg_8], 0
0x140031880  test    al, al
0x140031882  jns     short loc_1400318A5
0x140031884  mov     rcx, [rdi+18h]
0x140031888  lea     rdx, [rbp+arg_8]
0x14003188c  mov     rax, [rcx]
0x14003188f  mov     rax, [rax+0A8h]
0x140031896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003189b  mov     ecx, 440h
0x1400318a0  jmp     loc_14003167D
0x1400318a5  or      al, 80h
0x1400318a7  lea     rcx, [rbx+60h]
0x1400318ab  mov     [rbx+171h], al
0x1400318b1  jmp     loc_140031698
0x1400318b6  movups  xmm0, xmmword ptr [rsi]
0x1400318b9  xor     r8d, r8d; unsigned __int8
0x1400318bc  lea     rdx, aOuttype; "outType"
0x1400318c3  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400318c7  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400318cc  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400318d1  test    al, al
0x1400318d3  jz      loc_1400316A5
0x1400318d9  mov     r8, rbx; struct _TRACERPT_COLUMN *
0x1400318dc  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x1400318e0  call    ?ColumnAttributeOutType@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z; ColumnAttributeOutType(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)
0x1400318e5  jmp     loc_1400316A7
```

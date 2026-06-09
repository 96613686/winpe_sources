# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18003248c`
- end: `0x18003266d`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `481`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180032398`

## callees

- `0x18003248c`
- `0x18003a0b4`
- `0x18003a4a8`
- `0x18003b9b4`
- `0x18003c694`
- `0x18003d4e4`
- `0x18003dbc4`
- `0x18003de74`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800325fc`
- `msvcrt!memmove_s` at `0x1800325fc`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        unsigned __int64 a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v10; // rdi
  char v11; // si
  bool v12; // al
  unsigned int v13; // r12d
  unsigned __int64 v14; // r13
  int v15; // eax
  unsigned __int64 Size; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r14
  __int16 v22; // [rsp+30h] [rbp-40h] BYREF
  char v23; // [rsp+32h] [rbp-3Eh]
  int v24; // [rsp+34h] [rbp-3Ch]
  __int16 v25; // [rsp+38h] [rbp-38h]
  __int128 v26; // [rsp+40h] [rbp-30h]
  __int16 v27; // [rsp+50h] [rbp-20h] BYREF
  char v28; // [rsp+52h] [rbp-1Eh]
  unsigned int v29; // [rsp+54h] [rbp-1Ch]
  __int16 v30; // [rsp+58h] [rbp-18h]
  __int64 v31; // [rsp+60h] [rbp-10h]
  void *v32; // [rsp+68h] [rbp-8h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+B0h] [rbp+40h] BYREF
  void *v34; // [rsp+C8h] [rbp+58h]

  v34 = a4;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v10 = (unsigned __int8 *)(v6 + 10);
    v22 = *((_WORD *)this + 1);
    v23 = *((_BYTE *)this + 4);
    v25 = 0;
    v11 = 0;
    InsertionPointOrIncrement = v10;
    v24 = 0;
    v26 = 0;
    while ( 1 )
    {
      v12 = wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v22,
              &InsertionPointOrIncrement,
              *((unsigned __int8 **)this + 4));
      v13 = a6;
      v14 = a5;
      if ( !v12 )
      {
        v10 = InsertionPointOrIncrement;
        *((_QWORD *)this + 4) = InsertionPointOrIncrement;
        goto LABEL_14;
      }
      v15 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v22, a2, a3);
      if ( v15 < 0 )
      {
        InsertionPointOrIncrement = v10;
        goto LABEL_11;
      }
      if ( !v15 )
        break;
      v10 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v22,
              InsertionPointOrIncrement);
      InsertionPointOrIncrement = v10;
    }
    InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                  this,
                                  (struct wil::details_abi::UsageIndexProperty *)&v22,
                                  InsertionPointOrIncrement,
                                  v34,
                                  v14,
                                  v13);
    v10 = InsertionPointOrIncrement;
    if ( !InsertionPointOrIncrement )
      return 1;
    v11 = 1;
LABEL_11:
    if ( v11 )
      goto LABEL_15;
LABEL_14:
    v24 = 1;
    v25 = a3;
    *(_QWORD *)&v26 = 0;
    *((_QWORD *)&v26 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
LABEL_15:
    v27 = *((_WORD *)this + 3);
    v28 = *((_BYTE *)this + 8);
    v29 = v13;
    v30 = v14;
    v31 = 0;
    v32 = v34;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    v21 = Size + v20;
    if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= Size + v20 )
    {
      memmove_s(&v10[v21], v18 - v21 - (_QWORD)v10, v10, v19 - (_QWORD)v10);
      *((_QWORD *)this + 4) += v21;
      if ( v11 )
      {
        if ( v23 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v22, v24 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v22,
          &InsertionPointOrIncrement,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v27,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003248c  mov     [rsp-38h+arg_8], rbx
0x180032491  mov     [rsp-38h+arg_18], r9
0x180032496  push    rbp
0x180032497  push    rsi
0x180032498  push    rdi
0x180032499  push    r12
0x18003249b  push    r13
0x18003249d  push    r14
0x18003249f  push    r15
0x1800324a1  mov     rbp, rsp
0x1800324a4  sub     rsp, 70h
0x1800324a8  mov     rdi, [rcx+18h]
0x1800324ac  mov     r14, r8
0x1800324af  mov     r15, rdx
0x1800324b2  mov     rbx, rcx
0x1800324b5  test    rdi, rdi
0x1800324b8  jz      loc_180032652
0x1800324be  movzx   eax, word ptr [rcx+2]
0x1800324c2  add     rdi, 0Ah
0x1800324c6  mov     [rbp+var_40], ax
0x1800324ca  xorps   xmm0, xmm0
0x1800324cd  mov     al, [rcx+4]
0x1800324d0  mov     [rbp+var_3E], al
0x1800324d3  xor     eax, eax
0x1800324d5  mov     [rbp+var_38], ax
0x1800324d9  xor     sil, sil
0x1800324dc  mov     [rbp+arg_0], rdi
0x1800324e0  mov     [rbp+var_3C], 0
0x1800324e7  movdqu  [rbp+var_30], xmm0
0x1800324ec  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800324f0  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800324f4  lea     rcx, [rbp+var_40]; this
0x1800324f8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800324fd  mov     r12d, [rbp+arg_28]
0x180032501  mov     r13, [rbp+arg_20]
0x180032505  test    al, al
0x180032507  jz      short loc_180032570
0x180032509  mov     r8, r14; unsigned __int64
0x18003250c  lea     rcx, [rbp+var_40]; this
0x180032510  mov     rdx, r15; void *
0x180032513  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180032518  test    eax, eax
0x18003251a  js      short loc_180032562
0x18003251c  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180032520  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180032524  mov     rcx, rbx; this
0x180032527  jz      short loc_180032537
0x180032529  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18003252e  mov     rdi, rax
0x180032531  mov     [rbp+arg_0], rax
0x180032535  jmp     short loc_1800324EC
0x180032537  mov     r9, [rbp+arg_18]; void *
0x18003253b  mov     [rsp+70h+var_48], r12d; unsigned int
0x180032540  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180032545  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18003254a  mov     [rbp+arg_0], rax
0x18003254e  mov     rdi, rax
0x180032551  test    rax, rax
0x180032554  jnz     short loc_18003255D
0x180032556  mov     al, 1
0x180032558  jmp     loc_180032654
0x18003255d  mov     sil, 1
0x180032560  jmp     short loc_180032566
0x180032562  mov     [rbp+arg_0], rdi
0x180032566  xor     r8d, r8d
0x180032569  test    sil, sil
0x18003256c  jnz     short loc_18003259C
0x18003256e  jmp     short loc_180032578
0x180032570  mov     rdi, [rbp+arg_0]
0x180032574  mov     [rbx+20h], rdi
0x180032578  lea     rcx, [rbp+var_40]; this
0x18003257c  mov     [rbp+var_3C], 1
0x180032583  mov     [rbp+var_38], r14w
0x180032588  mov     qword ptr [rbp+var_30], 0
0x180032590  mov     qword ptr [rbp+var_30+8], r15
0x180032594  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180032599  mov     r8, rax
0x18003259c  movzx   ecx, word ptr [rbx+6]
0x1800325a0  mov     rax, [rbp+arg_18]
0x1800325a4  mov     [rbp+var_20], cx
0x1800325a8  mov     cl, [rbx+8]
0x1800325ab  mov     [rbp+var_1E], cl
0x1800325ae  lea     rcx, [rbp+var_20]; this
0x1800325b2  mov     [rbp+var_1C], r12d
0x1800325b6  mov     [rbp+var_18], r13w
0x1800325bb  mov     [rbp+var_10], 0
0x1800325c3  mov     [rbp+var_8], rax
0x1800325c7  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800325cc  mov     rdx, [rbx+28h]
0x1800325d0  mov     r9, [rbx+20h]
0x1800325d4  mov     rcx, rdx
0x1800325d7  sub     rcx, r9
0x1800325da  lea     r14, [rax+r8]
0x1800325de  cmp     r9, rdx
0x1800325e1  sbb     rax, rax
0x1800325e4  and     rax, rcx
0x1800325e7  cmp     rax, r14
0x1800325ea  jb      short loc_180032652
0x1800325ec  sub     rdx, r14
0x1800325ef  lea     rcx, [r14+rdi]; Destination
0x1800325f3  sub     rdx, rdi; DestinationSize
0x1800325f6  sub     r9, rdi; SourceSize
0x1800325f9  mov     r8, rdi; Source
0x1800325fc  call    cs:__imp_memmove_s
0x180032603  nop     dword ptr [rax+rax+00h]
0x180032608  add     [rbx+20h], r14
0x18003260c  test    sil, sil
0x18003260f  jnz     short loc_180032624
0x180032611  mov     r8, [rbx+20h]; unsigned __int8 *
0x180032615  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180032619  lea     rcx, [rbp+var_40]; this
0x18003261d  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180032622  jmp     short loc_180032638
0x180032624  cmp     [rbp+var_3E], 0
0x180032628  jz      short loc_180032638
0x18003262a  mov     edx, [rbp+var_3C]
0x18003262d  lea     rcx, [rbp+var_40]; this
0x180032631  inc     edx; unsigned int
0x180032633  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180032638  mov     r8, [rbx+20h]; unsigned __int8 *
0x18003263c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180032640  lea     rcx, [rbp+var_20]; this
0x180032644  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180032649  mov     byte ptr [rbx+38h], 1
0x18003264d  jmp     loc_180032556
0x180032652  xor     al, al
0x180032654  mov     rbx, [rsp+70h+arg_8]
0x18003265c  add     rsp, 70h
0x180032660  pop     r15
0x180032662  pop     r14
0x180032664  pop     r13
0x180032666  pop     r12
0x180032668  pop     rdi
0x180032669  pop     rsi
0x18003266a  pop     rbp
0x18003266b  retn
```

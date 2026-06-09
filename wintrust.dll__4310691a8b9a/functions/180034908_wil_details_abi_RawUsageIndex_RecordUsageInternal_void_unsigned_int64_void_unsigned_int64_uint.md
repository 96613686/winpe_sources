# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180034908`
- end: `0x180034ae2`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003481c`

## callees

- `0x180022570`
- `0x18002cf70`
- `0x18002d770`
- `0x180033828`
- `0x180034908`
- `0x180034e38`
- `0x18003505c`
- `0x18003534c`

## import_xrefs

- `msvcrt!memmove_s` at `0x180034a78`
- `msvcrt!memmove_s` at `0x180034a78`

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
0x180034908  mov     [rsp-38h+arg_8], rbx
0x18003490d  mov     [rsp-38h+arg_18], r9
0x180034912  push    rbp
0x180034913  push    rsi
0x180034914  push    rdi
0x180034915  push    r12
0x180034917  push    r13
0x180034919  push    r14
0x18003491b  push    r15
0x18003491d  mov     rbp, rsp
0x180034920  sub     rsp, 70h
0x180034924  mov     rdi, [rcx+18h]
0x180034928  mov     r14, r8
0x18003492b  mov     r15, rdx
0x18003492e  mov     rbx, rcx
0x180034931  test    rdi, rdi
0x180034934  jz      loc_180034AC8
0x18003493a  movzx   eax, word ptr [rcx+2]
0x18003493e  add     rdi, 0Ah
0x180034942  mov     [rbp+var_40], ax
0x180034946  xorps   xmm0, xmm0
0x180034949  mov     al, [rcx+4]
0x18003494c  mov     [rbp+var_3E], al
0x18003494f  xor     eax, eax
0x180034951  mov     [rbp+var_38], ax
0x180034955  xor     sil, sil
0x180034958  mov     [rbp+arg_0], rdi
0x18003495c  mov     [rbp+var_3C], 0
0x180034963  movdqu  [rbp+var_30], xmm0
0x180034968  mov     r8, [rbx+20h]; unsigned __int8 *
0x18003496c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180034970  lea     rcx, [rbp+var_40]; this
0x180034974  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180034979  mov     r12d, [rbp+arg_28]
0x18003497d  mov     r13, [rbp+arg_20]
0x180034981  test    al, al
0x180034983  jz      short loc_1800349EC
0x180034985  mov     r8, r14; unsigned __int64
0x180034988  lea     rcx, [rbp+var_40]; this
0x18003498c  mov     rdx, r15; void *
0x18003498f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180034994  test    eax, eax
0x180034996  js      short loc_1800349DE
0x180034998  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18003499c  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x1800349a0  mov     rcx, rbx; this
0x1800349a3  jz      short loc_1800349B3
0x1800349a5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800349aa  mov     rdi, rax
0x1800349ad  mov     [rbp+arg_0], rax
0x1800349b1  jmp     short loc_180034968
0x1800349b3  mov     r9, [rbp+arg_18]; void *
0x1800349b7  mov     [rsp+70h+var_48], r12d; unsigned int
0x1800349bc  mov     [rsp+70h+var_50], r13; unsigned __int64
0x1800349c1  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800349c6  mov     [rbp+arg_0], rax
0x1800349ca  mov     rdi, rax
0x1800349cd  test    rax, rax
0x1800349d0  jnz     short loc_1800349D9
0x1800349d2  mov     al, 1
0x1800349d4  jmp     loc_180034ACA
0x1800349d9  mov     sil, 1
0x1800349dc  jmp     short loc_1800349E2
0x1800349de  mov     [rbp+arg_0], rdi
0x1800349e2  xor     r8d, r8d
0x1800349e5  test    sil, sil
0x1800349e8  jnz     short loc_180034A18
0x1800349ea  jmp     short loc_1800349F4
0x1800349ec  mov     rdi, [rbp+arg_0]
0x1800349f0  mov     [rbx+20h], rdi
0x1800349f4  lea     rcx, [rbp+var_40]; this
0x1800349f8  mov     [rbp+var_3C], 1
0x1800349ff  mov     [rbp+var_38], r14w
0x180034a04  mov     qword ptr [rbp+var_30], 0
0x180034a0c  mov     qword ptr [rbp+var_30+8], r15
0x180034a10  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180034a15  mov     r8, rax
0x180034a18  movzx   ecx, word ptr [rbx+6]
0x180034a1c  mov     rax, [rbp+arg_18]
0x180034a20  mov     [rbp+var_20], cx
0x180034a24  mov     cl, [rbx+8]
0x180034a27  mov     [rbp+var_1E], cl
0x180034a2a  lea     rcx, [rbp+var_20]; this
0x180034a2e  mov     [rbp+var_1C], r12d
0x180034a32  mov     [rbp+var_18], r13w
0x180034a37  mov     [rbp+var_10], 0
0x180034a3f  mov     [rbp+var_8], rax
0x180034a43  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180034a48  mov     rdx, [rbx+28h]
0x180034a4c  mov     r9, [rbx+20h]
0x180034a50  mov     rcx, rdx
0x180034a53  sub     rcx, r9
0x180034a56  lea     r14, [rax+r8]
0x180034a5a  cmp     r9, rdx
0x180034a5d  sbb     rax, rax
0x180034a60  and     rax, rcx
0x180034a63  cmp     rax, r14
0x180034a66  jb      short loc_180034AC8
0x180034a68  sub     rdx, r14
0x180034a6b  lea     rcx, [r14+rdi]; Destination
0x180034a6f  sub     rdx, rdi; DestinationSize
0x180034a72  sub     r9, rdi; SourceSize
0x180034a75  mov     r8, rdi; Source
0x180034a78  call    cs:__imp_memmove_s
0x180034a7e  add     [rbx+20h], r14
0x180034a82  test    sil, sil
0x180034a85  jnz     short loc_180034A9A
0x180034a87  mov     r8, [rbx+20h]; unsigned __int8 *
0x180034a8b  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180034a8f  lea     rcx, [rbp+var_40]; this
0x180034a93  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180034a98  jmp     short loc_180034AAE
0x180034a9a  cmp     [rbp+var_3E], 0
0x180034a9e  jz      short loc_180034AAE
0x180034aa0  mov     edx, [rbp+var_3C]
0x180034aa3  lea     rcx, [rbp+var_40]; this
0x180034aa7  inc     edx; unsigned int
0x180034aa9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180034aae  mov     r8, [rbx+20h]; unsigned __int8 *
0x180034ab2  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180034ab6  lea     rcx, [rbp+var_20]; this
0x180034aba  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180034abf  mov     byte ptr [rbx+38h], 1
0x180034ac3  jmp     loc_1800349D2
0x180034ac8  xor     al, al
0x180034aca  mov     rbx, [rsp+70h+arg_8]
0x180034ad2  add     rsp, 70h
0x180034ad6  pop     r15
0x180034ad8  pop     r14
0x180034ada  pop     r13
0x180034adc  pop     r12
0x180034ade  pop     rdi
0x180034adf  pop     rsi
0x180034ae0  pop     rbp
0x180034ae1  retn
```

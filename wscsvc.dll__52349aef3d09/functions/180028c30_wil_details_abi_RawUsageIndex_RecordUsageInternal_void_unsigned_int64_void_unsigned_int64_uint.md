# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180028c30`
- end: `0x180028e0a`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028b3c`

## callees

- `0x1800223b0`
- `0x180022fe0`
- `0x1800238b4`
- `0x180028c30`
- `0x18002c7ec`
- `0x18002e160`
- `0x18002e4e8`
- `0x18002e8a8`

## import_xrefs

- `msvcrt!memmove_s` at `0x180028da0`
- `msvcrt!memmove_s` at `0x180028da0`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
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
  const void *v22; // [rsp+30h] [rbp-40h] BYREF
  __int16 v23; // [rsp+38h] [rbp-38h]
  __int128 v24; // [rsp+40h] [rbp-30h]
  __int16 v25; // [rsp+50h] [rbp-20h] BYREF
  char v26; // [rsp+52h] [rbp-1Eh]
  unsigned int v27; // [rsp+54h] [rbp-1Ch]
  __int16 v28; // [rsp+58h] [rbp-18h]
  __int64 v29; // [rsp+60h] [rbp-10h]
  void *v30; // [rsp+68h] [rbp-8h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+B0h] [rbp+40h] BYREF
  void *v32; // [rsp+C8h] [rbp+58h]

  v32 = a4;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v10 = (unsigned __int8 *)(v6 + 10);
    LOWORD(v22) = *((_WORD *)this + 1);
    BYTE2(v22) = *((_BYTE *)this + 4);
    v23 = 0;
    v11 = 0;
    InsertionPointOrIncrement = v10;
    HIDWORD(v22) = 0;
    v24 = 0;
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
      v15 = wil::details_abi::UsageIndexProperty::Compare(&v22, a2, a3);
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
                                  v32,
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
    HIDWORD(v22) = 1;
    v23 = a3;
    *(_QWORD *)&v24 = 0;
    *((_QWORD *)&v24 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
LABEL_15:
    v25 = *((_WORD *)this + 3);
    v26 = *((_BYTE *)this + 8);
    v27 = v13;
    v28 = v14;
    v29 = 0;
    v30 = v32;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v25);
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    v21 = Size + v20;
    if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= Size + v20 )
    {
      memmove_s(&v10[v21], v18 - v21 - (_QWORD)v10, v10, v19 - (_QWORD)v10);
      *((_QWORD *)this + 4) += v21;
      if ( v11 )
      {
        if ( BYTE2(v22) )
          wil::details_abi::UsageIndexProperty::UpdateCount(
            (wil::details_abi::UsageIndexProperty *)&v22,
            HIDWORD(v22) + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v22,
          &InsertionPointOrIncrement,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v25,
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
0x180028c30  mov     [rsp-38h+arg_8], rbx
0x180028c35  mov     [rsp-38h+arg_18], r9
0x180028c3a  push    rbp
0x180028c3b  push    rsi
0x180028c3c  push    rdi
0x180028c3d  push    r12
0x180028c3f  push    r13
0x180028c41  push    r14
0x180028c43  push    r15
0x180028c45  mov     rbp, rsp
0x180028c48  sub     rsp, 70h
0x180028c4c  mov     rdi, [rcx+18h]
0x180028c50  mov     r14, r8
0x180028c53  mov     r15, rdx
0x180028c56  mov     rbx, rcx
0x180028c59  test    rdi, rdi
0x180028c5c  jz      loc_180028DF0
0x180028c62  movzx   eax, word ptr [rcx+2]
0x180028c66  add     rdi, 0Ah
0x180028c6a  mov     [rbp+var_40], ax
0x180028c6e  xorps   xmm0, xmm0
0x180028c71  mov     al, [rcx+4]
0x180028c74  mov     [rbp+var_3E], al
0x180028c77  xor     eax, eax
0x180028c79  mov     [rbp+var_38], ax
0x180028c7d  xor     sil, sil
0x180028c80  mov     [rbp+arg_0], rdi
0x180028c84  mov     [rbp+var_3C], 0
0x180028c8b  movdqu  [rbp+var_30], xmm0
0x180028c90  mov     r8, [rbx+20h]; unsigned __int8 *
0x180028c94  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180028c98  lea     rcx, [rbp+var_40]; this
0x180028c9c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180028ca1  mov     r12d, [rbp+arg_28]
0x180028ca5  mov     r13, [rbp+arg_20]
0x180028ca9  test    al, al
0x180028cab  jz      short loc_180028D14
0x180028cad  mov     r8, r14; unsigned __int64
0x180028cb0  lea     rcx, [rbp+var_40]; this
0x180028cb4  mov     rdx, r15; void *
0x180028cb7  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180028cbc  test    eax, eax
0x180028cbe  js      short loc_180028D06
0x180028cc0  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180028cc4  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180028cc8  mov     rcx, rbx; this
0x180028ccb  jz      short loc_180028CDB
0x180028ccd  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180028cd2  mov     rdi, rax
0x180028cd5  mov     [rbp+arg_0], rax
0x180028cd9  jmp     short loc_180028C90
0x180028cdb  mov     r9, [rbp+arg_18]; void *
0x180028cdf  mov     [rsp+70h+var_48], r12d; unsigned int
0x180028ce4  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180028ce9  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180028cee  mov     [rbp+arg_0], rax
0x180028cf2  mov     rdi, rax
0x180028cf5  test    rax, rax
0x180028cf8  jnz     short loc_180028D01
0x180028cfa  mov     al, 1
0x180028cfc  jmp     loc_180028DF2
0x180028d01  mov     sil, 1
0x180028d04  jmp     short loc_180028D0A
0x180028d06  mov     [rbp+arg_0], rdi
0x180028d0a  xor     r8d, r8d
0x180028d0d  test    sil, sil
0x180028d10  jnz     short loc_180028D40
0x180028d12  jmp     short loc_180028D1C
0x180028d14  mov     rdi, [rbp+arg_0]
0x180028d18  mov     [rbx+20h], rdi
0x180028d1c  lea     rcx, [rbp+var_40]; this
0x180028d20  mov     [rbp+var_3C], 1
0x180028d27  mov     [rbp+var_38], r14w
0x180028d2c  mov     qword ptr [rbp+var_30], 0
0x180028d34  mov     qword ptr [rbp+var_30+8], r15
0x180028d38  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180028d3d  mov     r8, rax
0x180028d40  movzx   ecx, word ptr [rbx+6]
0x180028d44  mov     rax, [rbp+arg_18]
0x180028d48  mov     [rbp+var_20], cx
0x180028d4c  mov     cl, [rbx+8]
0x180028d4f  mov     [rbp+var_1E], cl
0x180028d52  lea     rcx, [rbp+var_20]; this
0x180028d56  mov     [rbp+var_1C], r12d
0x180028d5a  mov     [rbp+var_18], r13w
0x180028d5f  mov     [rbp+var_10], 0
0x180028d67  mov     [rbp+var_8], rax
0x180028d6b  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180028d70  mov     rdx, [rbx+28h]
0x180028d74  mov     r9, [rbx+20h]
0x180028d78  mov     rcx, rdx
0x180028d7b  sub     rcx, r9
0x180028d7e  lea     r14, [rax+r8]
0x180028d82  cmp     r9, rdx
0x180028d85  sbb     rax, rax
0x180028d88  and     rax, rcx
0x180028d8b  cmp     rax, r14
0x180028d8e  jb      short loc_180028DF0
0x180028d90  sub     rdx, r14
0x180028d93  lea     rcx, [r14+rdi]; Destination
0x180028d97  sub     rdx, rdi; DestinationSize
0x180028d9a  sub     r9, rdi; SourceSize
0x180028d9d  mov     r8, rdi; Source
0x180028da0  call    cs:__imp_memmove_s
0x180028da6  add     [rbx+20h], r14
0x180028daa  test    sil, sil
0x180028dad  jnz     short loc_180028DC2
0x180028daf  mov     r8, [rbx+20h]; unsigned __int8 *
0x180028db3  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180028db7  lea     rcx, [rbp+var_40]; this
0x180028dbb  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180028dc0  jmp     short loc_180028DD6
0x180028dc2  cmp     [rbp+var_3E], 0
0x180028dc6  jz      short loc_180028DD6
0x180028dc8  mov     edx, [rbp+var_3C]
0x180028dcb  lea     rcx, [rbp+var_40]; this
0x180028dcf  inc     edx; unsigned int
0x180028dd1  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180028dd6  mov     r8, [rbx+20h]; unsigned __int8 *
0x180028dda  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180028dde  lea     rcx, [rbp+var_20]; this
0x180028de2  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180028de7  mov     byte ptr [rbx+38h], 1
0x180028deb  jmp     loc_180028CFA
0x180028df0  xor     al, al
0x180028df2  mov     rbx, [rsp+70h+arg_8]
0x180028dfa  add     rsp, 70h
0x180028dfe  pop     r15
0x180028e00  pop     r14
0x180028e02  pop     r13
0x180028e04  pop     r12
0x180028e06  pop     rdi
0x180028e07  pop     rsi
0x180028e08  pop     rbp
0x180028e09  retn
```

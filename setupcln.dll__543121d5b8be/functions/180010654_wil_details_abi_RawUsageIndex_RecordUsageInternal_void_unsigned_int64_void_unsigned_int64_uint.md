# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180010654`
- end: `0x180010838`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010560`

## callees

- `0x18000e174`
- `0x18000e4b4`
- `0x18000f094`
- `0x1800100b4`
- `0x180010654`
- `0x1800112e4`
- `0x180011a38`
- `0x180011cec`

## import_xrefs

- `msvcrt!memmove_s` at `0x180010796`
- `msvcrt!memmove_s` at `0x180010796`

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
  char *v11; // rdi
  unsigned __int8 *v12; // r8
  char v13; // r14
  int v14; // eax
  unsigned __int8 *v15; // rax
  char v17; // cl
  unsigned __int64 Size; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rsi
  const void *v24; // [rsp+30h] [rbp-48h] BYREF
  __int16 v25; // [rsp+38h] [rbp-40h]
  __int128 v26; // [rsp+40h] [rbp-38h]
  __int16 v27; // [rsp+50h] [rbp-28h] BYREF
  char v28; // [rsp+52h] [rbp-26h]
  unsigned int v29; // [rsp+54h] [rbp-24h]
  __int16 v30; // [rsp+58h] [rbp-20h]
  __int64 v31; // [rsp+60h] [rbp-18h]
  void *v32; // [rsp+68h] [rbp-10h]
  void *Source; // [rsp+C0h] [rbp+48h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (char *)(v6 + 10);
    v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
    LOWORD(v24) = *((_WORD *)this + 1);
    BYTE2(v24) = *((_BYTE *)this + 4);
    v25 = 0;
    v13 = 0;
    Source = v11;
    HIDWORD(v24) = 0;
    v26 = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v24,
              (unsigned __int8 **)&Source,
              v12) )
      {
        v11 = (char *)Source;
        *((_QWORD *)this + 4) = Source;
        goto LABEL_8;
      }
      v14 = wil::details_abi::UsageIndexProperty::Compare(&v24, a2, a3);
      if ( v14 < 0 )
      {
        Source = v11;
        goto LABEL_8;
      }
      if ( !v14 )
        break;
      v15 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v24,
              (unsigned __int8 *)Source);
      v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
      v11 = (char *)v15;
      Source = v15;
    }
    Source = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
               this,
               (struct wil::details_abi::UsageIndexProperty *)&v24,
               (unsigned __int8 *)Source,
               a4,
               a5,
               a6);
    v11 = (char *)Source;
    if ( !Source )
      return 1;
    v13 = 1;
LABEL_8:
    if ( !v13 )
    {
      HIDWORD(v24) = 1;
      v25 = a3;
      *(_QWORD *)&v26 = 0;
      *((_QWORD *)&v26 + 1) = a2;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v24);
    }
    v27 = *((_WORD *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v29 = a6;
    v28 = v17;
    v30 = a5;
    v31 = 0;
    v32 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v19 = *((_QWORD *)this + 5);
    v20 = *((_QWORD *)this + 4);
    v22 = Size + v21;
    if ( ((v19 - v20) & -(__int64)(v20 < v19)) >= Size + v21 )
    {
      memmove_s(&v11[v22], v19 - v22 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v22;
      if ( v13 )
      {
        if ( BYTE2(v24) )
          wil::details_abi::UsageIndexProperty::UpdateCount(
            (wil::details_abi::UsageIndexProperty *)&v24,
            HIDWORD(v24) + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v24,
          (unsigned __int8 **)&Source,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v27,
        (unsigned __int8 **)&Source,
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
0x180010654  push    rbp
0x180010656  push    rbx
0x180010657  push    rsi
0x180010658  push    rdi
0x180010659  push    r12
0x18001065b  push    r13
0x18001065d  push    r14
0x18001065f  push    r15
0x180010661  mov     rbp, rsp
0x180010664  sub     rsp, 78h
0x180010668  mov     rdi, [rcx+18h]
0x18001066c  mov     r13, r9
0x18001066f  mov     r15, r8
0x180010672  mov     r12, rdx
0x180010675  mov     rbx, rcx
0x180010678  test    rdi, rdi
0x18001067b  jz      loc_180010825
0x180010681  movzx   eax, word ptr [rcx+2]
0x180010685  add     rdi, 0Ah
0x180010689  mov     r8, [rcx+20h]
0x18001068d  xorps   xmm0, xmm0
0x180010690  mov     [rbp+var_48], ax
0x180010694  mov     al, [rcx+4]
0x180010697  mov     [rbp+var_46], al
0x18001069a  xor     eax, eax
0x18001069c  mov     [rbp+var_40], ax
0x1800106a0  xor     r14b, r14b
0x1800106a3  mov     [rbp+Source], rdi
0x1800106a7  mov     [rbp+var_44], 0
0x1800106ae  movdqu  [rbp+var_38], xmm0
0x1800106b3  jmp     short loc_1800106ED
0x1800106b5  mov     r8, r15; unsigned __int64
0x1800106b8  lea     rcx, [rbp+var_48]; this
0x1800106bc  mov     rdx, r12; void *
0x1800106bf  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800106c4  test    eax, eax
0x1800106c6  js      loc_1800107E8
0x1800106cc  mov     r8, [rbp+Source]; unsigned __int8 *
0x1800106d0  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x1800106d4  jz      loc_1800107B8
0x1800106da  mov     rcx, rbx; this
0x1800106dd  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800106e2  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800106e6  mov     rdi, rax
0x1800106e9  mov     [rbp+Source], rax
0x1800106ed  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800106f1  lea     rcx, [rbp+var_48]; this
0x1800106f5  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800106fa  mov     sil, al
0x1800106fd  test    al, al
0x1800106ff  jnz     short loc_1800106B5
0x180010701  mov     rdi, [rbp+Source]
0x180010705  mov     [rbx+20h], rdi
0x180010709  xor     r8d, r8d
0x18001070c  test    r14b, r14b
0x18001070f  jnz     short loc_180010731
0x180010711  lea     rcx, [rbp+var_48]; this
0x180010715  mov     [rbp+var_44], 1
0x18001071c  mov     [rbp+var_40], r15w
0x180010721  mov     qword ptr [rbp+var_38], r8
0x180010725  mov     qword ptr [rbp+var_38+8], r12
0x180010729  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001072e  mov     r8, rax
0x180010731  movzx   ecx, word ptr [rbx+6]
0x180010735  mov     eax, [rbp+arg_28]
0x180010738  mov     [rbp+var_28], cx
0x18001073c  mov     cl, [rbx+8]
0x18001073f  mov     [rbp+var_24], eax
0x180010742  mov     rax, [rbp+arg_20]
0x180010746  mov     [rbp+var_26], cl
0x180010749  lea     rcx, [rbp+var_28]; this
0x18001074d  mov     [rbp+var_20], ax
0x180010751  mov     [rbp+var_18], 0
0x180010759  mov     [rbp+var_10], r13
0x18001075d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180010762  mov     rdx, [rbx+28h]
0x180010766  mov     r9, [rbx+20h]
0x18001076a  mov     rcx, rdx
0x18001076d  sub     rcx, r9
0x180010770  lea     rsi, [rax+r8]
0x180010774  cmp     r9, rdx
0x180010777  sbb     rax, rax
0x18001077a  and     rax, rcx
0x18001077d  cmp     rax, rsi
0x180010780  jb      loc_180010825
0x180010786  sub     rdx, rsi
0x180010789  lea     rcx, [rsi+rdi]; Destination
0x18001078d  sub     rdx, rdi; DestinationSize
0x180010790  sub     r9, rdi; SourceSize
0x180010793  mov     r8, rdi; Source
0x180010796  call    cs:__imp_memmove_s
0x18001079c  add     [rbx+20h], rsi
0x1800107a0  test    r14b, r14b
0x1800107a3  jnz     short loc_1800107FA
0x1800107a5  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800107a9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800107ad  lea     rcx, [rbp+var_48]; this
0x1800107b1  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800107b6  jmp     short loc_18001080E
0x1800107b8  mov     ecx, [rbp+arg_28]
0x1800107bb  mov     r9, r13; void *
0x1800107be  mov     [rsp+78h+var_50], ecx; unsigned int
0x1800107c2  mov     rcx, [rbp+arg_20]
0x1800107c6  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x1800107cb  mov     rcx, rbx; this
0x1800107ce  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800107d3  mov     [rbp+Source], rax
0x1800107d7  mov     rdi, rax
0x1800107da  test    rax, rax
0x1800107dd  jnz     short loc_1800107E3
0x1800107df  mov     al, 1
0x1800107e1  jmp     short loc_180010827
0x1800107e3  mov     r14b, 1
0x1800107e6  jmp     short loc_1800107EC
0x1800107e8  mov     [rbp+Source], rdi
0x1800107ec  test    sil, sil
0x1800107ef  jnz     loc_180010709
0x1800107f5  jmp     loc_180010705
0x1800107fa  cmp     [rbp+var_46], 0
0x1800107fe  jz      short loc_18001080E
0x180010800  mov     edx, [rbp+var_44]
0x180010803  lea     rcx, [rbp+var_48]; this
0x180010807  inc     edx; unsigned int
0x180010809  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001080e  mov     r8, [rbx+20h]; unsigned __int8 *
0x180010812  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180010816  lea     rcx, [rbp+var_28]; this
0x18001081a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001081f  mov     byte ptr [rbx+38h], 1
0x180010823  jmp     short loc_1800107DF
0x180010825  xor     al, al
0x180010827  add     rsp, 78h
0x18001082b  pop     r15
0x18001082d  pop     r14
0x18001082f  pop     r13
0x180010831  pop     r12
0x180010833  pop     rdi
0x180010834  pop     rsi
0x180010835  pop     rbx
0x180010836  pop     rbp
0x180010837  retn
```

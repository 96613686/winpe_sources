# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180032c50`
- end: `0x180032e34`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180032b5c`

## callees

- `0x180030b88`
- `0x180030e44`
- `0x1800317a4`
- `0x1800326b4`
- `0x180032c50`
- `0x1800335fc`
- `0x180033c6c`
- `0x180033f1c`

## import_xrefs

- `msvcrt!memmove_s` at `0x180032d92`
- `msvcrt!memmove_s` at `0x180032d92`

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
0x180032c50  push    rbp
0x180032c52  push    rbx
0x180032c53  push    rsi
0x180032c54  push    rdi
0x180032c55  push    r12
0x180032c57  push    r13
0x180032c59  push    r14
0x180032c5b  push    r15
0x180032c5d  mov     rbp, rsp
0x180032c60  sub     rsp, 78h
0x180032c64  mov     rdi, [rcx+18h]
0x180032c68  mov     r13, r9
0x180032c6b  mov     r15, r8
0x180032c6e  mov     r12, rdx
0x180032c71  mov     rbx, rcx
0x180032c74  test    rdi, rdi
0x180032c77  jz      loc_180032E21
0x180032c7d  movzx   eax, word ptr [rcx+2]
0x180032c81  add     rdi, 0Ah
0x180032c85  mov     r8, [rcx+20h]
0x180032c89  xorps   xmm0, xmm0
0x180032c8c  mov     [rbp+var_48], ax
0x180032c90  mov     al, [rcx+4]
0x180032c93  mov     [rbp+var_46], al
0x180032c96  xor     eax, eax
0x180032c98  mov     [rbp+var_40], ax
0x180032c9c  xor     r14b, r14b
0x180032c9f  mov     [rbp+Source], rdi
0x180032ca3  mov     [rbp+var_44], 0
0x180032caa  movdqu  [rbp+var_38], xmm0
0x180032caf  jmp     short loc_180032CE9
0x180032cb1  mov     r8, r15; unsigned __int64
0x180032cb4  lea     rcx, [rbp+var_48]; this
0x180032cb8  mov     rdx, r12; void *
0x180032cbb  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180032cc0  test    eax, eax
0x180032cc2  js      loc_180032DE4
0x180032cc8  mov     r8, [rbp+Source]; unsigned __int8 *
0x180032ccc  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180032cd0  jz      loc_180032DB4
0x180032cd6  mov     rcx, rbx; this
0x180032cd9  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180032cde  mov     r8, [rbx+20h]; unsigned __int8 *
0x180032ce2  mov     rdi, rax
0x180032ce5  mov     [rbp+Source], rax
0x180032ce9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180032ced  lea     rcx, [rbp+var_48]; this
0x180032cf1  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180032cf6  mov     sil, al
0x180032cf9  test    al, al
0x180032cfb  jnz     short loc_180032CB1
0x180032cfd  mov     rdi, [rbp+Source]
0x180032d01  mov     [rbx+20h], rdi
0x180032d05  xor     r8d, r8d
0x180032d08  test    r14b, r14b
0x180032d0b  jnz     short loc_180032D2D
0x180032d0d  lea     rcx, [rbp+var_48]; this
0x180032d11  mov     [rbp+var_44], 1
0x180032d18  mov     [rbp+var_40], r15w
0x180032d1d  mov     qword ptr [rbp+var_38], r8
0x180032d21  mov     qword ptr [rbp+var_38+8], r12
0x180032d25  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180032d2a  mov     r8, rax
0x180032d2d  movzx   ecx, word ptr [rbx+6]
0x180032d31  mov     eax, [rbp+arg_28]
0x180032d34  mov     [rbp+var_28], cx
0x180032d38  mov     cl, [rbx+8]
0x180032d3b  mov     [rbp+var_24], eax
0x180032d3e  mov     rax, [rbp+arg_20]
0x180032d42  mov     [rbp+var_26], cl
0x180032d45  lea     rcx, [rbp+var_28]; this
0x180032d49  mov     [rbp+var_20], ax
0x180032d4d  mov     [rbp+var_18], 0
0x180032d55  mov     [rbp+var_10], r13
0x180032d59  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180032d5e  mov     rdx, [rbx+28h]
0x180032d62  mov     r9, [rbx+20h]
0x180032d66  mov     rcx, rdx
0x180032d69  sub     rcx, r9
0x180032d6c  lea     rsi, [rax+r8]
0x180032d70  cmp     r9, rdx
0x180032d73  sbb     rax, rax
0x180032d76  and     rax, rcx
0x180032d79  cmp     rax, rsi
0x180032d7c  jb      loc_180032E21
0x180032d82  sub     rdx, rsi
0x180032d85  lea     rcx, [rsi+rdi]; Destination
0x180032d89  sub     rdx, rdi; DestinationSize
0x180032d8c  sub     r9, rdi; SourceSize
0x180032d8f  mov     r8, rdi; Source
0x180032d92  call    cs:__imp_memmove_s
0x180032d98  add     [rbx+20h], rsi
0x180032d9c  test    r14b, r14b
0x180032d9f  jnz     short loc_180032DF6
0x180032da1  mov     r8, [rbx+20h]; unsigned __int8 *
0x180032da5  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180032da9  lea     rcx, [rbp+var_48]; this
0x180032dad  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180032db2  jmp     short loc_180032E0A
0x180032db4  mov     ecx, [rbp+arg_28]
0x180032db7  mov     r9, r13; void *
0x180032dba  mov     [rsp+78h+var_50], ecx; unsigned int
0x180032dbe  mov     rcx, [rbp+arg_20]
0x180032dc2  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180032dc7  mov     rcx, rbx; this
0x180032dca  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180032dcf  mov     [rbp+Source], rax
0x180032dd3  mov     rdi, rax
0x180032dd6  test    rax, rax
0x180032dd9  jnz     short loc_180032DDF
0x180032ddb  mov     al, 1
0x180032ddd  jmp     short loc_180032E23
0x180032ddf  mov     r14b, 1
0x180032de2  jmp     short loc_180032DE8
0x180032de4  mov     [rbp+Source], rdi
0x180032de8  test    sil, sil
0x180032deb  jnz     loc_180032D05
0x180032df1  jmp     loc_180032D01
0x180032df6  cmp     [rbp+var_46], 0
0x180032dfa  jz      short loc_180032E0A
0x180032dfc  mov     edx, [rbp+var_44]
0x180032dff  lea     rcx, [rbp+var_48]; this
0x180032e03  inc     edx; unsigned int
0x180032e05  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180032e0a  mov     r8, [rbx+20h]; unsigned __int8 *
0x180032e0e  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180032e12  lea     rcx, [rbp+var_28]; this
0x180032e16  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180032e1b  mov     byte ptr [rbx+38h], 1
0x180032e1f  jmp     short loc_180032DDB
0x180032e21  xor     al, al
0x180032e23  add     rsp, 78h
0x180032e27  pop     r15
0x180032e29  pop     r14
0x180032e2b  pop     r13
0x180032e2d  pop     r12
0x180032e2f  pop     rdi
0x180032e30  pop     rsi
0x180032e31  pop     rbx
0x180032e32  pop     rbp
0x180032e33  retn
```

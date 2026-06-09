# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001d7a8`
- end: `0x18001d98c`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d6b4`

## callees

- `0x180016f48`
- `0x180017f18`
- `0x180018d94`
- `0x18001d184`
- `0x18001d7a8`
- `0x18001ea34`
- `0x18001f1f0`
- `0x1800201ac`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001d8ea`
- `msvcrt!memmove_s` at `0x18001d8ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001d7a8  push    rbp
0x18001d7aa  push    rbx
0x18001d7ab  push    rsi
0x18001d7ac  push    rdi
0x18001d7ad  push    r12
0x18001d7af  push    r13
0x18001d7b1  push    r14
0x18001d7b3  push    r15
0x18001d7b5  mov     rbp, rsp
0x18001d7b8  sub     rsp, 78h
0x18001d7bc  mov     rdi, [rcx+18h]
0x18001d7c0  mov     r13, r9
0x18001d7c3  mov     r15, r8
0x18001d7c6  mov     r12, rdx
0x18001d7c9  mov     rbx, rcx
0x18001d7cc  test    rdi, rdi
0x18001d7cf  jz      loc_18001D979
0x18001d7d5  movzx   eax, word ptr [rcx+2]
0x18001d7d9  add     rdi, 0Ah
0x18001d7dd  mov     r8, [rcx+20h]
0x18001d7e1  xorps   xmm0, xmm0
0x18001d7e4  mov     [rbp+var_48], ax
0x18001d7e8  mov     al, [rcx+4]
0x18001d7eb  mov     [rbp+var_46], al
0x18001d7ee  xor     eax, eax
0x18001d7f0  mov     [rbp+var_40], ax
0x18001d7f4  xor     r14b, r14b
0x18001d7f7  mov     [rbp+Source], rdi
0x18001d7fb  mov     [rbp+var_44], 0
0x18001d802  movdqu  [rbp+var_38], xmm0
0x18001d807  jmp     short loc_18001D841
0x18001d809  mov     r8, r15; unsigned __int64
0x18001d80c  lea     rcx, [rbp+var_48]; this
0x18001d810  mov     rdx, r12; void *
0x18001d813  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001d818  test    eax, eax
0x18001d81a  js      loc_18001D93C
0x18001d820  mov     r8, [rbp+Source]; unsigned __int8 *
0x18001d824  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x18001d828  jz      loc_18001D90C
0x18001d82e  mov     rcx, rbx; this
0x18001d831  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001d836  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001d83a  mov     rdi, rax
0x18001d83d  mov     [rbp+Source], rax
0x18001d841  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001d845  lea     rcx, [rbp+var_48]; this
0x18001d849  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001d84e  mov     sil, al
0x18001d851  test    al, al
0x18001d853  jnz     short loc_18001D809
0x18001d855  mov     rdi, [rbp+Source]
0x18001d859  mov     [rbx+20h], rdi
0x18001d85d  xor     r8d, r8d
0x18001d860  test    r14b, r14b
0x18001d863  jnz     short loc_18001D885
0x18001d865  lea     rcx, [rbp+var_48]; this
0x18001d869  mov     [rbp+var_44], 1
0x18001d870  mov     [rbp+var_40], r15w
0x18001d875  mov     qword ptr [rbp+var_38], r8
0x18001d879  mov     qword ptr [rbp+var_38+8], r12
0x18001d87d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001d882  mov     r8, rax
0x18001d885  movzx   ecx, word ptr [rbx+6]
0x18001d889  mov     eax, [rbp+arg_28]
0x18001d88c  mov     [rbp+var_28], cx
0x18001d890  mov     cl, [rbx+8]
0x18001d893  mov     [rbp+var_24], eax
0x18001d896  mov     rax, [rbp+arg_20]
0x18001d89a  mov     [rbp+var_26], cl
0x18001d89d  lea     rcx, [rbp+var_28]; this
0x18001d8a1  mov     [rbp+var_20], ax
0x18001d8a5  mov     [rbp+var_18], 0
0x18001d8ad  mov     [rbp+var_10], r13
0x18001d8b1  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001d8b6  mov     rdx, [rbx+28h]
0x18001d8ba  mov     r9, [rbx+20h]
0x18001d8be  mov     rcx, rdx
0x18001d8c1  sub     rcx, r9
0x18001d8c4  lea     rsi, [rax+r8]
0x18001d8c8  cmp     r9, rdx
0x18001d8cb  sbb     rax, rax
0x18001d8ce  and     rax, rcx
0x18001d8d1  cmp     rax, rsi
0x18001d8d4  jb      loc_18001D979
0x18001d8da  sub     rdx, rsi
0x18001d8dd  lea     rcx, [rsi+rdi]; Destination
0x18001d8e1  sub     rdx, rdi; DestinationSize
0x18001d8e4  sub     r9, rdi; SourceSize
0x18001d8e7  mov     r8, rdi; Source
0x18001d8ea  call    cs:__imp_memmove_s
0x18001d8f0  add     [rbx+20h], rsi
0x18001d8f4  test    r14b, r14b
0x18001d8f7  jnz     short loc_18001D94E
0x18001d8f9  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001d8fd  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001d901  lea     rcx, [rbp+var_48]; this
0x18001d905  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001d90a  jmp     short loc_18001D962
0x18001d90c  mov     ecx, [rbp+arg_28]
0x18001d90f  mov     r9, r13; void *
0x18001d912  mov     [rsp+78h+var_50], ecx; unsigned int
0x18001d916  mov     rcx, [rbp+arg_20]
0x18001d91a  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18001d91f  mov     rcx, rbx; this
0x18001d922  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001d927  mov     [rbp+Source], rax
0x18001d92b  mov     rdi, rax
0x18001d92e  test    rax, rax
0x18001d931  jnz     short loc_18001D937
0x18001d933  mov     al, 1
0x18001d935  jmp     short loc_18001D97B
0x18001d937  mov     r14b, 1
0x18001d93a  jmp     short loc_18001D940
0x18001d93c  mov     [rbp+Source], rdi
0x18001d940  test    sil, sil
0x18001d943  jnz     loc_18001D85D
0x18001d949  jmp     loc_18001D859
0x18001d94e  cmp     [rbp+var_46], 0
0x18001d952  jz      short loc_18001D962
0x18001d954  mov     edx, [rbp+var_44]
0x18001d957  lea     rcx, [rbp+var_48]; this
0x18001d95b  inc     edx; unsigned int
0x18001d95d  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001d962  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001d966  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001d96a  lea     rcx, [rbp+var_28]; this
0x18001d96e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001d973  mov     byte ptr [rbx+38h], 1
0x18001d977  jmp     short loc_18001D933
0x18001d979  xor     al, al
0x18001d97b  add     rsp, 78h
0x18001d97f  pop     r15
0x18001d981  pop     r14
0x18001d983  pop     r13
0x18001d985  pop     r12
0x18001d987  pop     rdi
0x18001d988  pop     rsi
0x18001d989  pop     rbx
0x18001d98a  pop     rbp
0x18001d98b  retn
```

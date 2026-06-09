# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000a7b4`
- end: `0x18000a998`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a6c0`

## callees

- `0x18000822c`
- `0x180008628`
- `0x180008fb4`
- `0x18000a198`
- `0x18000a7b4`
- `0x18000b15c`
- `0x18000b7f4`
- `0x18000bbbc`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000a8f6`
- `msvcrt!memmove_s` at `0x18000a8f6`

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
0x18000a7b4  push    rbp
0x18000a7b6  push    rbx
0x18000a7b7  push    rsi
0x18000a7b8  push    rdi
0x18000a7b9  push    r12
0x18000a7bb  push    r13
0x18000a7bd  push    r14
0x18000a7bf  push    r15
0x18000a7c1  mov     rbp, rsp
0x18000a7c4  sub     rsp, 78h
0x18000a7c8  mov     rdi, [rcx+18h]
0x18000a7cc  mov     r13, r9
0x18000a7cf  mov     r15, r8
0x18000a7d2  mov     r12, rdx
0x18000a7d5  mov     rbx, rcx
0x18000a7d8  test    rdi, rdi
0x18000a7db  jz      loc_18000A985
0x18000a7e1  movzx   eax, word ptr [rcx+2]
0x18000a7e5  add     rdi, 0Ah
0x18000a7e9  mov     r8, [rcx+20h]
0x18000a7ed  xorps   xmm0, xmm0
0x18000a7f0  mov     [rbp+var_48], ax
0x18000a7f4  mov     al, [rcx+4]
0x18000a7f7  mov     [rbp+var_46], al
0x18000a7fa  xor     eax, eax
0x18000a7fc  mov     [rbp+var_40], ax
0x18000a800  xor     r14b, r14b
0x18000a803  mov     [rbp+Source], rdi
0x18000a807  mov     [rbp+var_44], 0
0x18000a80e  movdqu  [rbp+var_38], xmm0
0x18000a813  jmp     short loc_18000A84D
0x18000a815  mov     r8, r15; unsigned __int64
0x18000a818  lea     rcx, [rbp+var_48]; this
0x18000a81c  mov     rdx, r12; void *
0x18000a81f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18000a824  test    eax, eax
0x18000a826  js      loc_18000A948
0x18000a82c  mov     r8, [rbp+Source]; unsigned __int8 *
0x18000a830  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x18000a834  jz      loc_18000A918
0x18000a83a  mov     rcx, rbx; this
0x18000a83d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18000a842  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000a846  mov     rdi, rax
0x18000a849  mov     [rbp+Source], rax
0x18000a84d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18000a851  lea     rcx, [rbp+var_48]; this
0x18000a855  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000a85a  mov     sil, al
0x18000a85d  test    al, al
0x18000a85f  jnz     short loc_18000A815
0x18000a861  mov     rdi, [rbp+Source]
0x18000a865  mov     [rbx+20h], rdi
0x18000a869  xor     r8d, r8d
0x18000a86c  test    r14b, r14b
0x18000a86f  jnz     short loc_18000A891
0x18000a871  lea     rcx, [rbp+var_48]; this
0x18000a875  mov     [rbp+var_44], 1
0x18000a87c  mov     [rbp+var_40], r15w
0x18000a881  mov     qword ptr [rbp+var_38], r8
0x18000a885  mov     qword ptr [rbp+var_38+8], r12
0x18000a889  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000a88e  mov     r8, rax
0x18000a891  movzx   ecx, word ptr [rbx+6]
0x18000a895  mov     eax, [rbp+arg_28]
0x18000a898  mov     [rbp+var_28], cx
0x18000a89c  mov     cl, [rbx+8]
0x18000a89f  mov     [rbp+var_24], eax
0x18000a8a2  mov     rax, [rbp+arg_20]
0x18000a8a6  mov     [rbp+var_26], cl
0x18000a8a9  lea     rcx, [rbp+var_28]; this
0x18000a8ad  mov     [rbp+var_20], ax
0x18000a8b1  mov     [rbp+var_18], 0
0x18000a8b9  mov     [rbp+var_10], r13
0x18000a8bd  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000a8c2  mov     rdx, [rbx+28h]
0x18000a8c6  mov     r9, [rbx+20h]
0x18000a8ca  mov     rcx, rdx
0x18000a8cd  sub     rcx, r9
0x18000a8d0  lea     rsi, [rax+r8]
0x18000a8d4  cmp     r9, rdx
0x18000a8d7  sbb     rax, rax
0x18000a8da  and     rax, rcx
0x18000a8dd  cmp     rax, rsi
0x18000a8e0  jb      loc_18000A985
0x18000a8e6  sub     rdx, rsi
0x18000a8e9  lea     rcx, [rsi+rdi]; Destination
0x18000a8ed  sub     rdx, rdi; DestinationSize
0x18000a8f0  sub     r9, rdi; SourceSize
0x18000a8f3  mov     r8, rdi; Source
0x18000a8f6  call    cs:__imp_memmove_s
0x18000a8fc  add     [rbx+20h], rsi
0x18000a900  test    r14b, r14b
0x18000a903  jnz     short loc_18000A95A
0x18000a905  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000a909  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18000a90d  lea     rcx, [rbp+var_48]; this
0x18000a911  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000a916  jmp     short loc_18000A96E
0x18000a918  mov     ecx, [rbp+arg_28]
0x18000a91b  mov     r9, r13; void *
0x18000a91e  mov     [rsp+78h+var_50], ecx; unsigned int
0x18000a922  mov     rcx, [rbp+arg_20]
0x18000a926  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18000a92b  mov     rcx, rbx; this
0x18000a92e  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000a933  mov     [rbp+Source], rax
0x18000a937  mov     rdi, rax
0x18000a93a  test    rax, rax
0x18000a93d  jnz     short loc_18000A943
0x18000a93f  mov     al, 1
0x18000a941  jmp     short loc_18000A987
0x18000a943  mov     r14b, 1
0x18000a946  jmp     short loc_18000A94C
0x18000a948  mov     [rbp+Source], rdi
0x18000a94c  test    sil, sil
0x18000a94f  jnz     loc_18000A869
0x18000a955  jmp     loc_18000A865
0x18000a95a  cmp     [rbp+var_46], 0
0x18000a95e  jz      short loc_18000A96E
0x18000a960  mov     edx, [rbp+var_44]
0x18000a963  lea     rcx, [rbp+var_48]; this
0x18000a967  inc     edx; unsigned int
0x18000a969  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18000a96e  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000a972  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18000a976  lea     rcx, [rbp+var_28]; this
0x18000a97a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000a97f  mov     byte ptr [rbx+38h], 1
0x18000a983  jmp     short loc_18000A93F
0x18000a985  xor     al, al
0x18000a987  add     rsp, 78h
0x18000a98b  pop     r15
0x18000a98d  pop     r14
0x18000a98f  pop     r13
0x18000a991  pop     r12
0x18000a993  pop     rdi
0x18000a994  pop     rsi
0x18000a995  pop     rbx
0x18000a996  pop     rbp
0x18000a997  retn
```

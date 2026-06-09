# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000ba2c`
- end: `0x18000bc10`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000b938`

## callees

- `0x18000a60c`
- `0x18000ab38`
- `0x18000ad34`
- `0x18000b4fc`
- `0x18000ba2c`
- `0x18000c574`
- `0x18000cf48`
- `0x18000d3a4`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000bb6e`
- `msvcrt!memmove_s` at `0x18000bb6e`

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
  __int16 v24; // [rsp+30h] [rbp-48h] BYREF
  char v25; // [rsp+32h] [rbp-46h]
  int v26; // [rsp+34h] [rbp-44h]
  __int16 v27; // [rsp+38h] [rbp-40h]
  __int128 v28; // [rsp+40h] [rbp-38h]
  __int16 v29; // [rsp+50h] [rbp-28h] BYREF
  char v30; // [rsp+52h] [rbp-26h]
  unsigned int v31; // [rsp+54h] [rbp-24h]
  __int16 v32; // [rsp+58h] [rbp-20h]
  __int64 v33; // [rsp+60h] [rbp-18h]
  void *v34; // [rsp+68h] [rbp-10h]
  void *Source; // [rsp+C0h] [rbp+48h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (char *)(v6 + 10);
    v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
    v24 = *((_WORD *)this + 1);
    v25 = *((_BYTE *)this + 4);
    v27 = 0;
    v13 = 0;
    Source = v11;
    v26 = 0;
    v28 = 0;
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
      v14 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v24, a2, a3);
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
      v26 = 1;
      v27 = a3;
      *(_QWORD *)&v28 = 0;
      *((_QWORD *)&v28 + 1) = a2;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v24);
    }
    v29 = *((_WORD *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v31 = a6;
    v30 = v17;
    v32 = a5;
    v33 = 0;
    v34 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v29);
    v19 = *((_QWORD *)this + 5);
    v20 = *((_QWORD *)this + 4);
    v22 = Size + v21;
    if ( ((v19 - v20) & -(__int64)(v20 < v19)) >= Size + v21 )
    {
      memmove_s(&v11[v22], v19 - v22 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v22;
      if ( v13 )
      {
        if ( v25 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v24, v26 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v24,
          (unsigned __int8 **)&Source,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v29,
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
0x18000ba2c  push    rbp
0x18000ba2e  push    rbx
0x18000ba2f  push    rsi
0x18000ba30  push    rdi
0x18000ba31  push    r12
0x18000ba33  push    r13
0x18000ba35  push    r14
0x18000ba37  push    r15
0x18000ba39  mov     rbp, rsp
0x18000ba3c  sub     rsp, 78h
0x18000ba40  mov     rdi, [rcx+18h]
0x18000ba44  mov     r13, r9
0x18000ba47  mov     r15, r8
0x18000ba4a  mov     r12, rdx
0x18000ba4d  mov     rbx, rcx
0x18000ba50  test    rdi, rdi
0x18000ba53  jz      loc_18000BBFD
0x18000ba59  movzx   eax, word ptr [rcx+2]
0x18000ba5d  add     rdi, 0Ah
0x18000ba61  mov     r8, [rcx+20h]
0x18000ba65  xorps   xmm0, xmm0
0x18000ba68  mov     [rbp+var_48], ax
0x18000ba6c  mov     al, [rcx+4]
0x18000ba6f  mov     [rbp+var_46], al
0x18000ba72  xor     eax, eax
0x18000ba74  mov     [rbp+var_40], ax
0x18000ba78  xor     r14b, r14b
0x18000ba7b  mov     [rbp+Source], rdi
0x18000ba7f  mov     [rbp+var_44], 0
0x18000ba86  movdqu  [rbp+var_38], xmm0
0x18000ba8b  jmp     short loc_18000BAC5
0x18000ba8d  mov     r8, r15; unsigned __int64
0x18000ba90  lea     rcx, [rbp+var_48]; this
0x18000ba94  mov     rdx, r12; void *
0x18000ba97  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18000ba9c  test    eax, eax
0x18000ba9e  js      loc_18000BBC0
0x18000baa4  mov     r8, [rbp+Source]; unsigned __int8 *
0x18000baa8  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x18000baac  jz      loc_18000BB90
0x18000bab2  mov     rcx, rbx; this
0x18000bab5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18000baba  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000babe  mov     rdi, rax
0x18000bac1  mov     [rbp+Source], rax
0x18000bac5  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18000bac9  lea     rcx, [rbp+var_48]; this
0x18000bacd  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000bad2  mov     sil, al
0x18000bad5  test    al, al
0x18000bad7  jnz     short loc_18000BA8D
0x18000bad9  mov     rdi, [rbp+Source]
0x18000badd  mov     [rbx+20h], rdi
0x18000bae1  xor     r8d, r8d
0x18000bae4  test    r14b, r14b
0x18000bae7  jnz     short loc_18000BB09
0x18000bae9  lea     rcx, [rbp+var_48]; this
0x18000baed  mov     [rbp+var_44], 1
0x18000baf4  mov     [rbp+var_40], r15w
0x18000baf9  mov     qword ptr [rbp+var_38], r8
0x18000bafd  mov     qword ptr [rbp+var_38+8], r12
0x18000bb01  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000bb06  mov     r8, rax
0x18000bb09  movzx   ecx, word ptr [rbx+6]
0x18000bb0d  mov     eax, [rbp+arg_28]
0x18000bb10  mov     [rbp+var_28], cx
0x18000bb14  mov     cl, [rbx+8]
0x18000bb17  mov     [rbp+var_24], eax
0x18000bb1a  mov     rax, [rbp+arg_20]
0x18000bb1e  mov     [rbp+var_26], cl
0x18000bb21  lea     rcx, [rbp+var_28]; this
0x18000bb25  mov     [rbp+var_20], ax
0x18000bb29  mov     [rbp+var_18], 0
0x18000bb31  mov     [rbp+var_10], r13
0x18000bb35  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000bb3a  mov     rdx, [rbx+28h]
0x18000bb3e  mov     r9, [rbx+20h]
0x18000bb42  mov     rcx, rdx
0x18000bb45  sub     rcx, r9
0x18000bb48  lea     rsi, [rax+r8]
0x18000bb4c  cmp     r9, rdx
0x18000bb4f  sbb     rax, rax
0x18000bb52  and     rax, rcx
0x18000bb55  cmp     rax, rsi
0x18000bb58  jb      loc_18000BBFD
0x18000bb5e  sub     rdx, rsi
0x18000bb61  lea     rcx, [rsi+rdi]; Destination
0x18000bb65  sub     rdx, rdi; DestinationSize
0x18000bb68  sub     r9, rdi; SourceSize
0x18000bb6b  mov     r8, rdi; Source
0x18000bb6e  call    cs:__imp_memmove_s
0x18000bb74  add     [rbx+20h], rsi
0x18000bb78  test    r14b, r14b
0x18000bb7b  jnz     short loc_18000BBD2
0x18000bb7d  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000bb81  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18000bb85  lea     rcx, [rbp+var_48]; this
0x18000bb89  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000bb8e  jmp     short loc_18000BBE6
0x18000bb90  mov     ecx, [rbp+arg_28]
0x18000bb93  mov     r9, r13; void *
0x18000bb96  mov     [rsp+78h+var_50], ecx; unsigned int
0x18000bb9a  mov     rcx, [rbp+arg_20]
0x18000bb9e  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18000bba3  mov     rcx, rbx; this
0x18000bba6  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000bbab  mov     [rbp+Source], rax
0x18000bbaf  mov     rdi, rax
0x18000bbb2  test    rax, rax
0x18000bbb5  jnz     short loc_18000BBBB
0x18000bbb7  mov     al, 1
0x18000bbb9  jmp     short loc_18000BBFF
0x18000bbbb  mov     r14b, 1
0x18000bbbe  jmp     short loc_18000BBC4
0x18000bbc0  mov     [rbp+Source], rdi
0x18000bbc4  test    sil, sil
0x18000bbc7  jnz     loc_18000BAE1
0x18000bbcd  jmp     loc_18000BADD
0x18000bbd2  cmp     [rbp+var_46], 0
0x18000bbd6  jz      short loc_18000BBE6
0x18000bbd8  mov     edx, [rbp+var_44]
0x18000bbdb  lea     rcx, [rbp+var_48]; this
0x18000bbdf  inc     edx; unsigned int
0x18000bbe1  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18000bbe6  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000bbea  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18000bbee  lea     rcx, [rbp+var_28]; this
0x18000bbf2  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000bbf7  mov     byte ptr [rbx+38h], 1
0x18000bbfb  jmp     short loc_18000BBB7
0x18000bbfd  xor     al, al
0x18000bbff  add     rsp, 78h
0x18000bc03  pop     r15
0x18000bc05  pop     r14
0x18000bc07  pop     r13
0x18000bc09  pop     r12
0x18000bc0b  pop     rdi
0x18000bc0c  pop     rsi
0x18000bc0d  pop     rbx
0x18000bc0e  pop     rbp
0x18000bc0f  retn
```

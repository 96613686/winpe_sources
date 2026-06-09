# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001bf64`
- end: `0x18001c148`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001be70`

## callees

- `0x18001b108`
- `0x18001b2c0`
- `0x18001b4bc`
- `0x18001ba38`
- `0x18001bf64`
- `0x18001c564`
- `0x18001c950`
- `0x18001cab4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001c0a6`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001c0a6`

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
0x18001bf64  push    rbp
0x18001bf66  push    rbx
0x18001bf67  push    rsi
0x18001bf68  push    rdi
0x18001bf69  push    r12
0x18001bf6b  push    r13
0x18001bf6d  push    r14
0x18001bf6f  push    r15
0x18001bf71  mov     rbp, rsp
0x18001bf74  sub     rsp, 78h
0x18001bf78  mov     rdi, [rcx+18h]
0x18001bf7c  mov     r13, r9
0x18001bf7f  mov     r15, r8
0x18001bf82  mov     r12, rdx
0x18001bf85  mov     rbx, rcx
0x18001bf88  test    rdi, rdi
0x18001bf8b  jz      loc_18001C135
0x18001bf91  movzx   eax, word ptr [rcx+2]
0x18001bf95  add     rdi, 0Ah
0x18001bf99  mov     r8, [rcx+20h]
0x18001bf9d  xorps   xmm0, xmm0
0x18001bfa0  mov     [rbp+var_48], ax
0x18001bfa4  mov     al, [rcx+4]
0x18001bfa7  mov     [rbp+var_46], al
0x18001bfaa  xor     eax, eax
0x18001bfac  mov     [rbp+var_40], ax
0x18001bfb0  xor     r14b, r14b
0x18001bfb3  mov     [rbp+Source], rdi
0x18001bfb7  mov     [rbp+var_44], 0
0x18001bfbe  movdqu  [rbp+var_38], xmm0
0x18001bfc3  jmp     short loc_18001BFFD
0x18001bfc5  mov     r8, r15; unsigned __int64
0x18001bfc8  lea     rcx, [rbp+var_48]; this
0x18001bfcc  mov     rdx, r12; void *
0x18001bfcf  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001bfd4  test    eax, eax
0x18001bfd6  js      loc_18001C0F8
0x18001bfdc  mov     r8, [rbp+Source]; unsigned __int8 *
0x18001bfe0  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x18001bfe4  jz      loc_18001C0C8
0x18001bfea  mov     rcx, rbx; this
0x18001bfed  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001bff2  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001bff6  mov     rdi, rax
0x18001bff9  mov     [rbp+Source], rax
0x18001bffd  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001c001  lea     rcx, [rbp+var_48]; this
0x18001c005  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001c00a  mov     sil, al
0x18001c00d  test    al, al
0x18001c00f  jnz     short loc_18001BFC5
0x18001c011  mov     rdi, [rbp+Source]
0x18001c015  mov     [rbx+20h], rdi
0x18001c019  xor     r8d, r8d
0x18001c01c  test    r14b, r14b
0x18001c01f  jnz     short loc_18001C041
0x18001c021  lea     rcx, [rbp+var_48]; this
0x18001c025  mov     [rbp+var_44], 1
0x18001c02c  mov     [rbp+var_40], r15w
0x18001c031  mov     qword ptr [rbp+var_38], r8
0x18001c035  mov     qword ptr [rbp+var_38+8], r12
0x18001c039  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001c03e  mov     r8, rax
0x18001c041  movzx   ecx, word ptr [rbx+6]
0x18001c045  mov     eax, [rbp+arg_28]
0x18001c048  mov     [rbp+var_28], cx
0x18001c04c  mov     cl, [rbx+8]
0x18001c04f  mov     [rbp+var_24], eax
0x18001c052  mov     rax, [rbp+arg_20]
0x18001c056  mov     [rbp+var_26], cl
0x18001c059  lea     rcx, [rbp+var_28]; this
0x18001c05d  mov     [rbp+var_20], ax
0x18001c061  mov     [rbp+var_18], 0
0x18001c069  mov     [rbp+var_10], r13
0x18001c06d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001c072  mov     rdx, [rbx+28h]
0x18001c076  mov     r9, [rbx+20h]
0x18001c07a  mov     rcx, rdx
0x18001c07d  sub     rcx, r9
0x18001c080  lea     rsi, [rax+r8]
0x18001c084  cmp     r9, rdx
0x18001c087  sbb     rax, rax
0x18001c08a  and     rax, rcx
0x18001c08d  cmp     rax, rsi
0x18001c090  jb      loc_18001C135
0x18001c096  sub     rdx, rsi
0x18001c099  lea     rcx, [rsi+rdi]; Destination
0x18001c09d  sub     rdx, rdi; DestinationSize
0x18001c0a0  sub     r9, rdi; SourceSize
0x18001c0a3  mov     r8, rdi; Source
0x18001c0a6  call    cs:__imp_memmove_s
0x18001c0ac  add     [rbx+20h], rsi
0x18001c0b0  test    r14b, r14b
0x18001c0b3  jnz     short loc_18001C10A
0x18001c0b5  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001c0b9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001c0bd  lea     rcx, [rbp+var_48]; this
0x18001c0c1  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001c0c6  jmp     short loc_18001C11E
0x18001c0c8  mov     ecx, [rbp+arg_28]
0x18001c0cb  mov     r9, r13; void *
0x18001c0ce  mov     [rsp+78h+var_50], ecx; unsigned int
0x18001c0d2  mov     rcx, [rbp+arg_20]
0x18001c0d6  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18001c0db  mov     rcx, rbx; this
0x18001c0de  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001c0e3  mov     [rbp+Source], rax
0x18001c0e7  mov     rdi, rax
0x18001c0ea  test    rax, rax
0x18001c0ed  jnz     short loc_18001C0F3
0x18001c0ef  mov     al, 1
0x18001c0f1  jmp     short loc_18001C137
0x18001c0f3  mov     r14b, 1
0x18001c0f6  jmp     short loc_18001C0FC
0x18001c0f8  mov     [rbp+Source], rdi
0x18001c0fc  test    sil, sil
0x18001c0ff  jnz     loc_18001C019
0x18001c105  jmp     loc_18001C015
0x18001c10a  cmp     [rbp+var_46], 0
0x18001c10e  jz      short loc_18001C11E
0x18001c110  mov     edx, [rbp+var_44]
0x18001c113  lea     rcx, [rbp+var_48]; this
0x18001c117  inc     edx; unsigned int
0x18001c119  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001c11e  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001c122  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001c126  lea     rcx, [rbp+var_28]; this
0x18001c12a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001c12f  mov     byte ptr [rbx+38h], 1
0x18001c133  jmp     short loc_18001C0EF
0x18001c135  xor     al, al
0x18001c137  add     rsp, 78h
0x18001c13b  pop     r15
0x18001c13d  pop     r14
0x18001c13f  pop     r13
0x18001c141  pop     r12
0x18001c143  pop     rdi
0x18001c144  pop     rsi
0x18001c145  pop     rbx
0x18001c146  pop     rbp
0x18001c147  retn
```

# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18003f4b0`
- end: `0x18003f694`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003f3bc`

## callees

- `0x18003d198`
- `0x18003d4d4`
- `0x18003de34`
- `0x18003ef1c`
- `0x18003f4b0`
- `0x18003fe5c`
- `0x1800405fc`
- `0x1800408ac`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18003f5f2`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18003f5f2`

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
0x18003f4b0  push    rbp
0x18003f4b2  push    rbx
0x18003f4b3  push    rsi
0x18003f4b4  push    rdi
0x18003f4b5  push    r12
0x18003f4b7  push    r13
0x18003f4b9  push    r14
0x18003f4bb  push    r15
0x18003f4bd  mov     rbp, rsp
0x18003f4c0  sub     rsp, 78h
0x18003f4c4  mov     rdi, [rcx+18h]
0x18003f4c8  mov     r13, r9
0x18003f4cb  mov     r15, r8
0x18003f4ce  mov     r12, rdx
0x18003f4d1  mov     rbx, rcx
0x18003f4d4  test    rdi, rdi
0x18003f4d7  jz      loc_18003F681
0x18003f4dd  movzx   eax, word ptr [rcx+2]
0x18003f4e1  add     rdi, 0Ah
0x18003f4e5  mov     r8, [rcx+20h]
0x18003f4e9  xorps   xmm0, xmm0
0x18003f4ec  mov     [rbp+var_48], ax
0x18003f4f0  mov     al, [rcx+4]
0x18003f4f3  mov     [rbp+var_46], al
0x18003f4f6  xor     eax, eax
0x18003f4f8  mov     [rbp+var_40], ax
0x18003f4fc  xor     r14b, r14b
0x18003f4ff  mov     [rbp+Source], rdi
0x18003f503  mov     [rbp+var_44], 0
0x18003f50a  movdqu  [rbp+var_38], xmm0
0x18003f50f  jmp     short loc_18003F549
0x18003f511  mov     r8, r15; unsigned __int64
0x18003f514  lea     rcx, [rbp+var_48]; this
0x18003f518  mov     rdx, r12; void *
0x18003f51b  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18003f520  test    eax, eax
0x18003f522  js      loc_18003F644
0x18003f528  mov     r8, [rbp+Source]; unsigned __int8 *
0x18003f52c  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x18003f530  jz      loc_18003F614
0x18003f536  mov     rcx, rbx; this
0x18003f539  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18003f53e  mov     r8, [rbx+20h]; unsigned __int8 *
0x18003f542  mov     rdi, rax
0x18003f545  mov     [rbp+Source], rax
0x18003f549  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18003f54d  lea     rcx, [rbp+var_48]; this
0x18003f551  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18003f556  mov     sil, al
0x18003f559  test    al, al
0x18003f55b  jnz     short loc_18003F511
0x18003f55d  mov     rdi, [rbp+Source]
0x18003f561  mov     [rbx+20h], rdi
0x18003f565  xor     r8d, r8d
0x18003f568  test    r14b, r14b
0x18003f56b  jnz     short loc_18003F58D
0x18003f56d  lea     rcx, [rbp+var_48]; this
0x18003f571  mov     [rbp+var_44], 1
0x18003f578  mov     [rbp+var_40], r15w
0x18003f57d  mov     qword ptr [rbp+var_38], r8
0x18003f581  mov     qword ptr [rbp+var_38+8], r12
0x18003f585  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18003f58a  mov     r8, rax
0x18003f58d  movzx   ecx, word ptr [rbx+6]
0x18003f591  mov     eax, [rbp+arg_28]
0x18003f594  mov     [rbp+var_28], cx
0x18003f598  mov     cl, [rbx+8]
0x18003f59b  mov     [rbp+var_24], eax
0x18003f59e  mov     rax, [rbp+arg_20]
0x18003f5a2  mov     [rbp+var_26], cl
0x18003f5a5  lea     rcx, [rbp+var_28]; this
0x18003f5a9  mov     [rbp+var_20], ax
0x18003f5ad  mov     [rbp+var_18], 0
0x18003f5b5  mov     [rbp+var_10], r13
0x18003f5b9  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18003f5be  mov     rdx, [rbx+28h]
0x18003f5c2  mov     r9, [rbx+20h]
0x18003f5c6  mov     rcx, rdx
0x18003f5c9  sub     rcx, r9
0x18003f5cc  lea     rsi, [rax+r8]
0x18003f5d0  cmp     r9, rdx
0x18003f5d3  sbb     rax, rax
0x18003f5d6  and     rax, rcx
0x18003f5d9  cmp     rax, rsi
0x18003f5dc  jb      loc_18003F681
0x18003f5e2  sub     rdx, rsi
0x18003f5e5  lea     rcx, [rsi+rdi]; Destination
0x18003f5e9  sub     rdx, rdi; DestinationSize
0x18003f5ec  sub     r9, rdi; SourceSize
0x18003f5ef  mov     r8, rdi; Source
0x18003f5f2  call    cs:__imp_memmove_s
0x18003f5f8  add     [rbx+20h], rsi
0x18003f5fc  test    r14b, r14b
0x18003f5ff  jnz     short loc_18003F656
0x18003f601  mov     r8, [rbx+20h]; unsigned __int8 *
0x18003f605  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18003f609  lea     rcx, [rbp+var_48]; this
0x18003f60d  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18003f612  jmp     short loc_18003F66A
0x18003f614  mov     ecx, [rbp+arg_28]
0x18003f617  mov     r9, r13; void *
0x18003f61a  mov     [rsp+78h+var_50], ecx; unsigned int
0x18003f61e  mov     rcx, [rbp+arg_20]
0x18003f622  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18003f627  mov     rcx, rbx; this
0x18003f62a  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18003f62f  mov     [rbp+Source], rax
0x18003f633  mov     rdi, rax
0x18003f636  test    rax, rax
0x18003f639  jnz     short loc_18003F63F
0x18003f63b  mov     al, 1
0x18003f63d  jmp     short loc_18003F683
0x18003f63f  mov     r14b, 1
0x18003f642  jmp     short loc_18003F648
0x18003f644  mov     [rbp+Source], rdi
0x18003f648  test    sil, sil
0x18003f64b  jnz     loc_18003F565
0x18003f651  jmp     loc_18003F561
0x18003f656  cmp     [rbp+var_46], 0
0x18003f65a  jz      short loc_18003F66A
0x18003f65c  mov     edx, [rbp+var_44]
0x18003f65f  lea     rcx, [rbp+var_48]; this
0x18003f663  inc     edx; unsigned int
0x18003f665  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18003f66a  mov     r8, [rbx+20h]; unsigned __int8 *
0x18003f66e  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18003f672  lea     rcx, [rbp+var_28]; this
0x18003f676  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18003f67b  mov     byte ptr [rbx+38h], 1
0x18003f67f  jmp     short loc_18003F63B
0x18003f681  xor     al, al
0x18003f683  add     rsp, 78h
0x18003f687  pop     r15
0x18003f689  pop     r14
0x18003f68b  pop     r13
0x18003f68d  pop     r12
0x18003f68f  pop     rdi
0x18003f690  pop     rsi
0x18003f691  pop     rbx
0x18003f692  pop     rbp
0x18003f693  retn
```

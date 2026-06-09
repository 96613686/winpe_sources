# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001b25c`
- end: `0x18001b447`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `491`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b168`

## callees

- `0x180018eb8`
- `0x180019218`
- `0x180019bf8`
- `0x18001ac80`
- `0x18001b25c`
- `0x18001bc40`
- `0x18001c35c`
- `0x18001c618`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001b39e`
- `msvcrt!memmove_s` at `0x18001b39e`

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
0x18001b25c  push    rbp
0x18001b25e  push    rbx
0x18001b25f  push    rsi
0x18001b260  push    rdi
0x18001b261  push    r12
0x18001b263  push    r13
0x18001b265  push    r14
0x18001b267  push    r15
0x18001b269  mov     rbp, rsp
0x18001b26c  sub     rsp, 78h
0x18001b270  mov     rdi, [rcx+18h]
0x18001b274  mov     r13, r9
0x18001b277  mov     r15, r8
0x18001b27a  mov     r12, rdx
0x18001b27d  mov     rbx, rcx
0x18001b280  test    rdi, rdi
0x18001b283  jz      loc_18001B433
0x18001b289  movzx   eax, word ptr [rcx+2]
0x18001b28d  add     rdi, 0Ah
0x18001b291  mov     r8, [rcx+20h]
0x18001b295  xorps   xmm0, xmm0
0x18001b298  mov     [rbp+var_48], ax
0x18001b29c  mov     al, [rcx+4]
0x18001b29f  mov     [rbp+var_46], al
0x18001b2a2  xor     eax, eax
0x18001b2a4  mov     [rbp+var_40], ax
0x18001b2a8  xor     r14b, r14b
0x18001b2ab  mov     [rbp+Source], rdi
0x18001b2af  mov     [rbp+var_44], 0
0x18001b2b6  movdqu  [rbp+var_38], xmm0
0x18001b2bb  jmp     short loc_18001B2F5
0x18001b2bd  mov     r8, r15; unsigned __int64
0x18001b2c0  lea     rcx, [rbp+var_48]; this
0x18001b2c4  mov     rdx, r12; void *
0x18001b2c7  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001b2cc  test    eax, eax
0x18001b2ce  js      loc_18001B3F6
0x18001b2d4  mov     r8, [rbp+Source]; unsigned __int8 *
0x18001b2d8  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x18001b2dc  jz      loc_18001B3C6
0x18001b2e2  mov     rcx, rbx; this
0x18001b2e5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001b2ea  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001b2ee  mov     rdi, rax
0x18001b2f1  mov     [rbp+Source], rax
0x18001b2f5  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001b2f9  lea     rcx, [rbp+var_48]; this
0x18001b2fd  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001b302  mov     sil, al
0x18001b305  test    al, al
0x18001b307  jnz     short loc_18001B2BD
0x18001b309  mov     rdi, [rbp+Source]
0x18001b30d  mov     [rbx+20h], rdi
0x18001b311  xor     r8d, r8d
0x18001b314  test    r14b, r14b
0x18001b317  jnz     short loc_18001B339
0x18001b319  lea     rcx, [rbp+var_48]; this
0x18001b31d  mov     [rbp+var_44], 1
0x18001b324  mov     [rbp+var_40], r15w
0x18001b329  mov     qword ptr [rbp+var_38], r8
0x18001b32d  mov     qword ptr [rbp+var_38+8], r12
0x18001b331  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001b336  mov     r8, rax
0x18001b339  movzx   ecx, word ptr [rbx+6]
0x18001b33d  mov     eax, [rbp+arg_28]
0x18001b340  mov     [rbp+var_28], cx
0x18001b344  mov     cl, [rbx+8]
0x18001b347  mov     [rbp+var_24], eax
0x18001b34a  mov     rax, [rbp+arg_20]
0x18001b34e  mov     [rbp+var_26], cl
0x18001b351  lea     rcx, [rbp+var_28]; this
0x18001b355  mov     [rbp+var_20], ax
0x18001b359  mov     [rbp+var_18], 0
0x18001b361  mov     [rbp+var_10], r13
0x18001b365  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001b36a  mov     rdx, [rbx+28h]
0x18001b36e  mov     r9, [rbx+20h]
0x18001b372  mov     rcx, rdx
0x18001b375  sub     rcx, r9
0x18001b378  lea     rsi, [rax+r8]
0x18001b37c  cmp     r9, rdx
0x18001b37f  sbb     rax, rax
0x18001b382  and     rax, rcx
0x18001b385  cmp     rax, rsi
0x18001b388  jb      loc_18001B433
0x18001b38e  sub     rdx, rsi
0x18001b391  lea     rcx, [rsi+rdi]; Destination
0x18001b395  sub     rdx, rdi; DestinationSize
0x18001b398  sub     r9, rdi; SourceSize
0x18001b39b  mov     r8, rdi; Source
0x18001b39e  call    cs:__imp_memmove_s
0x18001b3a5  nop     dword ptr [rax+rax+00h]
0x18001b3aa  add     [rbx+20h], rsi
0x18001b3ae  test    r14b, r14b
0x18001b3b1  jnz     short loc_18001B408
0x18001b3b3  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001b3b7  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001b3bb  lea     rcx, [rbp+var_48]; this
0x18001b3bf  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001b3c4  jmp     short loc_18001B41C
0x18001b3c6  mov     ecx, [rbp+arg_28]
0x18001b3c9  mov     r9, r13; void *
0x18001b3cc  mov     [rsp+78h+var_50], ecx; unsigned int
0x18001b3d0  mov     rcx, [rbp+arg_20]
0x18001b3d4  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18001b3d9  mov     rcx, rbx; this
0x18001b3dc  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001b3e1  mov     [rbp+Source], rax
0x18001b3e5  mov     rdi, rax
0x18001b3e8  test    rax, rax
0x18001b3eb  jnz     short loc_18001B3F1
0x18001b3ed  mov     al, 1
0x18001b3ef  jmp     short loc_18001B435
0x18001b3f1  mov     r14b, 1
0x18001b3f4  jmp     short loc_18001B3FA
0x18001b3f6  mov     [rbp+Source], rdi
0x18001b3fa  test    sil, sil
0x18001b3fd  jnz     loc_18001B311
0x18001b403  jmp     loc_18001B30D
0x18001b408  cmp     [rbp+var_46], 0
0x18001b40c  jz      short loc_18001B41C
0x18001b40e  mov     edx, [rbp+var_44]
0x18001b411  lea     rcx, [rbp+var_48]; this
0x18001b415  inc     edx; unsigned int
0x18001b417  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001b41c  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001b420  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001b424  lea     rcx, [rbp+var_28]; this
0x18001b428  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001b42d  mov     byte ptr [rbx+38h], 1
0x18001b431  jmp     short loc_18001B3ED
0x18001b433  xor     al, al
0x18001b435  add     rsp, 78h
0x18001b439  pop     r15
0x18001b43b  pop     r14
0x18001b43d  pop     r13
0x18001b43f  pop     r12
0x18001b441  pop     rdi
0x18001b442  pop     rsi
0x18001b443  pop     rbx
0x18001b444  pop     rbp
0x18001b445  retn
```

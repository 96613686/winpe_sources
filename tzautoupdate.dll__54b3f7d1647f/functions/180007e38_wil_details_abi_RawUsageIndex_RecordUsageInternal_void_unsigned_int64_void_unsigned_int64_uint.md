# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007e38`
- end: `0x18000801c`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007d44`

## callees

- `0x180004fe0`
- `0x18000556c`
- `0x18000631c`
- `0x180007814`
- `0x180007e38`
- `0x180008eb4`
- `0x1800099ac`
- `0x18000ab1c`

## import_xrefs

- `msvcrt!memmove_s` at `0x180007f7a`
- `msvcrt!memmove_s` at `0x180007f7a`

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
0x180007e38  push    rbp
0x180007e3a  push    rbx
0x180007e3b  push    rsi
0x180007e3c  push    rdi
0x180007e3d  push    r12
0x180007e3f  push    r13
0x180007e41  push    r14
0x180007e43  push    r15
0x180007e45  mov     rbp, rsp
0x180007e48  sub     rsp, 78h
0x180007e4c  mov     rdi, [rcx+18h]
0x180007e50  mov     r13, r9
0x180007e53  mov     r15, r8
0x180007e56  mov     r12, rdx
0x180007e59  mov     rbx, rcx
0x180007e5c  test    rdi, rdi
0x180007e5f  jz      loc_180008009
0x180007e65  movzx   eax, word ptr [rcx+2]
0x180007e69  add     rdi, 0Ah
0x180007e6d  mov     r8, [rcx+20h]
0x180007e71  xorps   xmm0, xmm0
0x180007e74  mov     [rbp+var_48], ax
0x180007e78  mov     al, [rcx+4]
0x180007e7b  mov     [rbp+var_46], al
0x180007e7e  xor     eax, eax
0x180007e80  mov     [rbp+var_40], ax
0x180007e84  xor     r14b, r14b
0x180007e87  mov     [rbp+Source], rdi
0x180007e8b  mov     [rbp+var_44], 0
0x180007e92  movdqu  [rbp+var_38], xmm0
0x180007e97  jmp     short loc_180007ED1
0x180007e99  mov     r8, r15; unsigned __int64
0x180007e9c  lea     rcx, [rbp+var_48]; this
0x180007ea0  mov     rdx, r12; void *
0x180007ea3  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180007ea8  test    eax, eax
0x180007eaa  js      loc_180007FCC
0x180007eb0  mov     r8, [rbp+Source]; unsigned __int8 *
0x180007eb4  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180007eb8  jz      loc_180007F9C
0x180007ebe  mov     rcx, rbx; this
0x180007ec1  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180007ec6  mov     r8, [rbx+20h]; unsigned __int8 *
0x180007eca  mov     rdi, rax
0x180007ecd  mov     [rbp+Source], rax
0x180007ed1  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180007ed5  lea     rcx, [rbp+var_48]; this
0x180007ed9  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007ede  mov     sil, al
0x180007ee1  test    al, al
0x180007ee3  jnz     short loc_180007E99
0x180007ee5  mov     rdi, [rbp+Source]
0x180007ee9  mov     [rbx+20h], rdi
0x180007eed  xor     r8d, r8d
0x180007ef0  test    r14b, r14b
0x180007ef3  jnz     short loc_180007F15
0x180007ef5  lea     rcx, [rbp+var_48]; this
0x180007ef9  mov     [rbp+var_44], 1
0x180007f00  mov     [rbp+var_40], r15w
0x180007f05  mov     qword ptr [rbp+var_38], r8
0x180007f09  mov     qword ptr [rbp+var_38+8], r12
0x180007f0d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180007f12  mov     r8, rax
0x180007f15  movzx   ecx, word ptr [rbx+6]
0x180007f19  mov     eax, [rbp+arg_28]
0x180007f1c  mov     [rbp+var_28], cx
0x180007f20  mov     cl, [rbx+8]
0x180007f23  mov     [rbp+var_24], eax
0x180007f26  mov     rax, [rbp+arg_20]
0x180007f2a  mov     [rbp+var_26], cl
0x180007f2d  lea     rcx, [rbp+var_28]; this
0x180007f31  mov     [rbp+var_20], ax
0x180007f35  mov     [rbp+var_18], 0
0x180007f3d  mov     [rbp+var_10], r13
0x180007f41  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180007f46  mov     rdx, [rbx+28h]
0x180007f4a  mov     r9, [rbx+20h]
0x180007f4e  mov     rcx, rdx
0x180007f51  sub     rcx, r9
0x180007f54  lea     rsi, [rax+r8]
0x180007f58  cmp     r9, rdx
0x180007f5b  sbb     rax, rax
0x180007f5e  and     rax, rcx
0x180007f61  cmp     rax, rsi
0x180007f64  jb      loc_180008009
0x180007f6a  sub     rdx, rsi
0x180007f6d  lea     rcx, [rsi+rdi]; Destination
0x180007f71  sub     rdx, rdi; DestinationSize
0x180007f74  sub     r9, rdi; SourceSize
0x180007f77  mov     r8, rdi; Source
0x180007f7a  call    cs:__imp_memmove_s
0x180007f80  add     [rbx+20h], rsi
0x180007f84  test    r14b, r14b
0x180007f87  jnz     short loc_180007FDE
0x180007f89  mov     r8, [rbx+20h]; unsigned __int8 *
0x180007f8d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180007f91  lea     rcx, [rbp+var_48]; this
0x180007f95  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007f9a  jmp     short loc_180007FF2
0x180007f9c  mov     ecx, [rbp+arg_28]
0x180007f9f  mov     r9, r13; void *
0x180007fa2  mov     [rsp+78h+var_50], ecx; unsigned int
0x180007fa6  mov     rcx, [rbp+arg_20]
0x180007faa  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180007faf  mov     rcx, rbx; this
0x180007fb2  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180007fb7  mov     [rbp+Source], rax
0x180007fbb  mov     rdi, rax
0x180007fbe  test    rax, rax
0x180007fc1  jnz     short loc_180007FC7
0x180007fc3  mov     al, 1
0x180007fc5  jmp     short loc_18000800B
0x180007fc7  mov     r14b, 1
0x180007fca  jmp     short loc_180007FD0
0x180007fcc  mov     [rbp+Source], rdi
0x180007fd0  test    sil, sil
0x180007fd3  jnz     loc_180007EED
0x180007fd9  jmp     loc_180007EE9
0x180007fde  cmp     [rbp+var_46], 0
0x180007fe2  jz      short loc_180007FF2
0x180007fe4  mov     edx, [rbp+var_44]
0x180007fe7  lea     rcx, [rbp+var_48]; this
0x180007feb  inc     edx; unsigned int
0x180007fed  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180007ff2  mov     r8, [rbx+20h]; unsigned __int8 *
0x180007ff6  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180007ffa  lea     rcx, [rbp+var_28]; this
0x180007ffe  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180008003  mov     byte ptr [rbx+38h], 1
0x180008007  jmp     short loc_180007FC3
0x180008009  xor     al, al
0x18000800b  add     rsp, 78h
0x18000800f  pop     r15
0x180008011  pop     r14
0x180008013  pop     r13
0x180008015  pop     r12
0x180008017  pop     rdi
0x180008018  pop     rsi
0x180008019  pop     rbx
0x18000801a  pop     rbp
0x18000801b  retn
```

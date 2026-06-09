# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180012784`
- end: `0x180012974`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `496`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *Buf1@<rdx>, size_t Size@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18001600c`

## callees

- `0x180012620`
- `0x180012784`
- `0x180012b9c`
- `0x18001430c`
- `0x180014728`
- `0x180016a3c`
- `0x18001f6b8`
- `0x18002203b`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memmove_s` at `0x18001290a`
- `api-ms-win-core-crt-l1-1-0!memmove_s` at `0x18001290a`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
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
  int v15; // ecx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r14
  __int16 v22; // [rsp+30h] [rbp-40h] BYREF
  char v23; // [rsp+32h] [rbp-3Eh]
  int v24; // [rsp+34h] [rbp-3Ch]
  unsigned __int16 v25; // [rsp+38h] [rbp-38h]
  void *Buf2[2]; // [rsp+40h] [rbp-30h]
  __int16 v27; // [rsp+50h] [rbp-20h] BYREF
  char v28; // [rsp+52h] [rbp-1Eh]
  unsigned int v29; // [rsp+54h] [rbp-1Ch]
  __int16 v30; // [rsp+58h] [rbp-18h]
  __int64 v31; // [rsp+60h] [rbp-10h]
  void *v32; // [rsp+68h] [rbp-8h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+B0h] [rbp+40h] BYREF
  void *v34; // [rsp+C8h] [rbp+58h]

  v34 = a4;
  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v10 = (unsigned __int8 *)(v6 + 10);
  v22 = *((_WORD *)this + 1);
  v23 = *((_BYTE *)this + 4);
  v25 = 0;
  v11 = 0;
  InsertionPointOrIncrement = v10;
  v24 = 0;
  *(_OWORD *)Buf2 = 0;
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
LABEL_17:
      v24 = 1;
      v25 = Size;
      Buf2[0] = 0;
      Buf2[1] = Buf1;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
      goto LABEL_18;
    }
    v15 = Size == v25 ? memcmp_0(Buf1, Buf2[1], Size) : Size - v25;
    if ( v15 < 0 )
      break;
    if ( !v15 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v22,
                                    InsertionPointOrIncrement,
                                    v34,
                                    v14,
                                    v13);
      v10 = InsertionPointOrIncrement;
      if ( InsertionPointOrIncrement )
      {
        v11 = 1;
        goto LABEL_14;
      }
      return 1;
    }
    v10 = wil::details_abi::RawUsageIndex::SkipValues(
            this,
            (struct wil::details_abi::UsageIndexProperty *)&v22,
            InsertionPointOrIncrement);
    InsertionPointOrIncrement = v10;
  }
  InsertionPointOrIncrement = v10;
LABEL_14:
  if ( !v11 )
    goto LABEL_17;
LABEL_18:
  v27 = *((_WORD *)this + 3);
  v28 = *((_BYTE *)this + 8);
  v29 = v13;
  v30 = v14;
  v31 = 0;
  v32 = v34;
  v17 = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
  v18 = *((_QWORD *)this + 5);
  v19 = *((_QWORD *)this + 4);
  v21 = v17 + v20;
  if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= v17 + v20 )
  {
    memmove_s(&v10[v21], v18 - v21 - (_QWORD)v10, v10, v19 - (_QWORD)v10);
    *((_QWORD *)this + 4) += v21;
    if ( v11 )
    {
      if ( v23 )
        wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v22, v24 + 1);
    }
    else
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v22,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
    }
    wil::details_abi::UsageIndexProperty::Write(
      (wil::details_abi::UsageIndexProperty *)&v27,
      &InsertionPointOrIncrement,
      *((unsigned __int8 **)this + 4));
    *((_BYTE *)this + 56) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180012784  mov     [rsp-38h+arg_8], rbx
0x180012789  mov     [rsp-38h+arg_18], r9
0x18001278e  push    rbp
0x18001278f  push    rsi
0x180012790  push    rdi
0x180012791  push    r12
0x180012793  push    r13
0x180012795  push    r14
0x180012797  push    r15
0x180012799  mov     rbp, rsp
0x18001279c  sub     rsp, 70h
0x1800127a0  mov     rdi, [rcx+18h]
0x1800127a4  mov     r14, r8
0x1800127a7  mov     r15, rdx
0x1800127aa  mov     rbx, rcx
0x1800127ad  test    rdi, rdi
0x1800127b0  jz      loc_18001295A
0x1800127b6  movzx   eax, word ptr [rcx+2]
0x1800127ba  add     rdi, 0Ah
0x1800127be  mov     [rbp+var_40], ax
0x1800127c2  xorps   xmm0, xmm0
0x1800127c5  mov     al, [rcx+4]
0x1800127c8  mov     [rbp+var_3E], al
0x1800127cb  xor     eax, eax
0x1800127cd  mov     [rbp+var_38], ax
0x1800127d1  xor     sil, sil
0x1800127d4  mov     [rbp+arg_0], rdi
0x1800127d8  mov     [rbp+var_3C], 0
0x1800127df  movdqu  xmmword ptr [rbp+Buf2], xmm0
0x1800127e4  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800127e8  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800127ec  lea     rcx, [rbp+var_40]; this
0x1800127f0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800127f5  mov     r12d, [rbp+arg_28]
0x1800127f9  mov     r13, [rbp+arg_20]
0x1800127fd  test    al, al
0x1800127ff  jz      short loc_18001287E
0x180012801  movzx   eax, [rbp+var_38]
0x180012805  cmp     r14, rax
0x180012808  jnz     short loc_18001281D
0x18001280a  mov     rdx, [rbp+Buf2+8]; Buf2
0x18001280e  mov     r8, r14; Size
0x180012811  mov     rcx, r15; Buf1
0x180012814  call    memcmp_0
0x180012819  mov     ecx, eax
0x18001281b  jmp     short loc_180012826
0x18001281d  movzx   eax, [rbp+var_38]
0x180012821  mov     ecx, r14d
0x180012824  sub     ecx, eax
0x180012826  test    ecx, ecx
0x180012828  js      short loc_180012870
0x18001282a  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18001282e  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180012832  mov     rcx, rbx; this
0x180012835  jz      short loc_180012845
0x180012837  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001283c  mov     rdi, rax
0x18001283f  mov     [rbp+arg_0], rax
0x180012843  jmp     short loc_1800127E4
0x180012845  mov     r9, [rbp+arg_18]; void *
0x180012849  mov     [rsp+70h+var_48], r12d; unsigned int
0x18001284e  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180012853  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180012858  mov     [rbp+arg_0], rax
0x18001285c  mov     rdi, rax
0x18001285f  test    rax, rax
0x180012862  jnz     short loc_18001286B
0x180012864  mov     al, 1
0x180012866  jmp     loc_18001295C
0x18001286b  mov     sil, 1
0x18001286e  jmp     short loc_180012874
0x180012870  mov     [rbp+arg_0], rdi
0x180012874  xor     r8d, r8d
0x180012877  test    sil, sil
0x18001287a  jz      short loc_180012886
0x18001287c  jmp     short loc_1800128AA
0x18001287e  mov     rdi, [rbp+arg_0]
0x180012882  mov     [rbx+20h], rdi
0x180012886  lea     rcx, [rbp+var_40]; this
0x18001288a  mov     [rbp+var_3C], 1
0x180012891  mov     [rbp+var_38], r14w
0x180012896  mov     [rbp+Buf2], 0
0x18001289e  mov     [rbp+Buf2+8], r15
0x1800128a2  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800128a7  mov     r8, rax
0x1800128aa  movzx   ecx, word ptr [rbx+6]
0x1800128ae  mov     rax, [rbp+arg_18]
0x1800128b2  mov     [rbp+var_20], cx
0x1800128b6  mov     cl, [rbx+8]
0x1800128b9  mov     [rbp+var_1E], cl
0x1800128bc  lea     rcx, [rbp+var_20]; this
0x1800128c0  mov     [rbp+var_1C], r12d
0x1800128c4  mov     [rbp+var_18], r13w
0x1800128c9  mov     [rbp+var_10], 0
0x1800128d1  mov     [rbp+var_8], rax
0x1800128d5  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800128da  mov     rdx, [rbx+28h]
0x1800128de  mov     r9, [rbx+20h]
0x1800128e2  mov     rcx, rdx
0x1800128e5  sub     rcx, r9
0x1800128e8  lea     r14, [rax+r8]
0x1800128ec  cmp     r9, rdx
0x1800128ef  sbb     rax, rax
0x1800128f2  and     rax, rcx
0x1800128f5  cmp     rax, r14
0x1800128f8  jb      short loc_18001295A
0x1800128fa  sub     rdx, r14
0x1800128fd  lea     rcx, [r14+rdi]; Destination
0x180012901  sub     rdx, rdi; DestinationSize
0x180012904  sub     r9, rdi; SourceSize
0x180012907  mov     r8, rdi; Source
0x18001290a  call    cs:__imp_memmove_s
0x180012910  add     [rbx+20h], r14
0x180012914  test    sil, sil
0x180012917  jnz     short loc_18001292C
0x180012919  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001291d  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180012921  lea     rcx, [rbp+var_40]; this
0x180012925  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001292a  jmp     short loc_180012940
0x18001292c  cmp     [rbp+var_3E], 0
0x180012930  jz      short loc_180012940
0x180012932  mov     edx, [rbp+var_3C]
0x180012935  lea     rcx, [rbp+var_40]; this
0x180012939  inc     edx; unsigned int
0x18001293b  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180012940  mov     r8, [rbx+20h]; unsigned __int8 *
0x180012944  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180012948  lea     rcx, [rbp+var_20]; this
0x18001294c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180012951  mov     byte ptr [rbx+38h], 1
0x180012955  jmp     loc_180012864
0x18001295a  xor     al, al
0x18001295c  mov     rbx, [rsp+70h+arg_8]
0x180012964  add     rsp, 70h
0x180012968  pop     r15
0x18001296a  pop     r14
0x18001296c  pop     r13
0x18001296e  pop     r12
0x180012970  pop     rdi
0x180012971  pop     rsi
0x180012972  pop     rbp
0x180012973  retn
```

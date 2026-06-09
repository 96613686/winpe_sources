# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180012804`
- end: `0x1800129de`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012710`

## callees

- `0x180012804`
- `0x1800238cc`
- `0x180023e14`
- `0x1800248ac`
- `0x180025758`
- `0x180026638`
- `0x180026c38`
- `0x180026fc4`

## import_xrefs

- `msvcrt!memmove_s` at `0x180012974`
- `msvcrt!memmove_s` at `0x180012974`

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
  unsigned __int8 *v10; // rdi
  char v11; // si
  bool v12; // al
  unsigned int v13; // r12d
  unsigned __int64 v14; // r13
  int v15; // eax
  unsigned __int64 Size; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r14
  const void *v22; // [rsp+30h] [rbp-40h] BYREF
  __int16 v23; // [rsp+38h] [rbp-38h]
  __int128 v24; // [rsp+40h] [rbp-30h]
  __int16 v25; // [rsp+50h] [rbp-20h] BYREF
  char v26; // [rsp+52h] [rbp-1Eh]
  unsigned int v27; // [rsp+54h] [rbp-1Ch]
  __int16 v28; // [rsp+58h] [rbp-18h]
  __int64 v29; // [rsp+60h] [rbp-10h]
  void *v30; // [rsp+68h] [rbp-8h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+B0h] [rbp+40h] BYREF
  void *v32; // [rsp+C8h] [rbp+58h]

  v32 = a4;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v10 = (unsigned __int8 *)(v6 + 10);
    LOWORD(v22) = *((_WORD *)this + 1);
    BYTE2(v22) = *((_BYTE *)this + 4);
    v23 = 0;
    v11 = 0;
    InsertionPointOrIncrement = v10;
    HIDWORD(v22) = 0;
    v24 = 0;
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
        goto LABEL_14;
      }
      v15 = wil::details_abi::UsageIndexProperty::Compare(&v22, a2, a3);
      if ( v15 < 0 )
      {
        InsertionPointOrIncrement = v10;
        goto LABEL_11;
      }
      if ( !v15 )
        break;
      v10 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v22,
              InsertionPointOrIncrement);
      InsertionPointOrIncrement = v10;
    }
    InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                  this,
                                  (struct wil::details_abi::UsageIndexProperty *)&v22,
                                  InsertionPointOrIncrement,
                                  v32,
                                  v14,
                                  v13);
    v10 = InsertionPointOrIncrement;
    if ( !InsertionPointOrIncrement )
      return 1;
    v11 = 1;
LABEL_11:
    if ( v11 )
      goto LABEL_15;
LABEL_14:
    HIDWORD(v22) = 1;
    v23 = a3;
    *(_QWORD *)&v24 = 0;
    *((_QWORD *)&v24 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
LABEL_15:
    v25 = *((_WORD *)this + 3);
    v26 = *((_BYTE *)this + 8);
    v27 = v13;
    v28 = v14;
    v29 = 0;
    v30 = v32;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v25);
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    v21 = Size + v20;
    if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= Size + v20 )
    {
      memmove_s(&v10[v21], v18 - v21 - (_QWORD)v10, v10, v19 - (_QWORD)v10);
      *((_QWORD *)this + 4) += v21;
      if ( v11 )
      {
        if ( BYTE2(v22) )
          wil::details_abi::UsageIndexProperty::UpdateCount(
            (wil::details_abi::UsageIndexProperty *)&v22,
            HIDWORD(v22) + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v22,
          &InsertionPointOrIncrement,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v25,
        &InsertionPointOrIncrement,
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
0x180012804  mov     [rsp-38h+arg_8], rbx
0x180012809  mov     [rsp-38h+arg_18], r9
0x18001280e  push    rbp
0x18001280f  push    rsi
0x180012810  push    rdi
0x180012811  push    r12
0x180012813  push    r13
0x180012815  push    r14
0x180012817  push    r15
0x180012819  mov     rbp, rsp
0x18001281c  sub     rsp, 70h
0x180012820  mov     rdi, [rcx+18h]
0x180012824  mov     r14, r8
0x180012827  mov     r15, rdx
0x18001282a  mov     rbx, rcx
0x18001282d  test    rdi, rdi
0x180012830  jz      loc_1800129C4
0x180012836  movzx   eax, word ptr [rcx+2]
0x18001283a  add     rdi, 0Ah
0x18001283e  mov     [rbp+var_40], ax
0x180012842  xorps   xmm0, xmm0
0x180012845  mov     al, [rcx+4]
0x180012848  mov     [rbp+var_3E], al
0x18001284b  xor     eax, eax
0x18001284d  mov     [rbp+var_38], ax
0x180012851  xor     sil, sil
0x180012854  mov     [rbp+arg_0], rdi
0x180012858  mov     [rbp+var_3C], 0
0x18001285f  movdqu  [rbp+var_30], xmm0
0x180012864  mov     r8, [rbx+20h]; unsigned __int8 *
0x180012868  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001286c  lea     rcx, [rbp+var_40]; this
0x180012870  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180012875  mov     r12d, [rbp+arg_28]
0x180012879  mov     r13, [rbp+arg_20]
0x18001287d  test    al, al
0x18001287f  jz      short loc_1800128E8
0x180012881  mov     r8, r14; unsigned __int64
0x180012884  lea     rcx, [rbp+var_40]; this
0x180012888  mov     rdx, r15; void *
0x18001288b  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180012890  test    eax, eax
0x180012892  js      short loc_1800128DA
0x180012894  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180012898  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18001289c  mov     rcx, rbx; this
0x18001289f  jz      short loc_1800128AF
0x1800128a1  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800128a6  mov     rdi, rax
0x1800128a9  mov     [rbp+arg_0], rax
0x1800128ad  jmp     short loc_180012864
0x1800128af  mov     r9, [rbp+arg_18]; void *
0x1800128b3  mov     [rsp+70h+var_48], r12d; unsigned int
0x1800128b8  mov     [rsp+70h+var_50], r13; unsigned __int64
0x1800128bd  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800128c2  mov     [rbp+arg_0], rax
0x1800128c6  mov     rdi, rax
0x1800128c9  test    rax, rax
0x1800128cc  jnz     short loc_1800128D5
0x1800128ce  mov     al, 1
0x1800128d0  jmp     loc_1800129C6
0x1800128d5  mov     sil, 1
0x1800128d8  jmp     short loc_1800128DE
0x1800128da  mov     [rbp+arg_0], rdi
0x1800128de  xor     r8d, r8d
0x1800128e1  test    sil, sil
0x1800128e4  jnz     short loc_180012914
0x1800128e6  jmp     short loc_1800128F0
0x1800128e8  mov     rdi, [rbp+arg_0]
0x1800128ec  mov     [rbx+20h], rdi
0x1800128f0  lea     rcx, [rbp+var_40]; this
0x1800128f4  mov     [rbp+var_3C], 1
0x1800128fb  mov     [rbp+var_38], r14w
0x180012900  mov     qword ptr [rbp+var_30], 0
0x180012908  mov     qword ptr [rbp+var_30+8], r15
0x18001290c  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180012911  mov     r8, rax
0x180012914  movzx   ecx, word ptr [rbx+6]
0x180012918  mov     rax, [rbp+arg_18]
0x18001291c  mov     [rbp+var_20], cx
0x180012920  mov     cl, [rbx+8]
0x180012923  mov     [rbp+var_1E], cl
0x180012926  lea     rcx, [rbp+var_20]; this
0x18001292a  mov     [rbp+var_1C], r12d
0x18001292e  mov     [rbp+var_18], r13w
0x180012933  mov     [rbp+var_10], 0
0x18001293b  mov     [rbp+var_8], rax
0x18001293f  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180012944  mov     rdx, [rbx+28h]
0x180012948  mov     r9, [rbx+20h]
0x18001294c  mov     rcx, rdx
0x18001294f  sub     rcx, r9
0x180012952  lea     r14, [rax+r8]
0x180012956  cmp     r9, rdx
0x180012959  sbb     rax, rax
0x18001295c  and     rax, rcx
0x18001295f  cmp     rax, r14
0x180012962  jb      short loc_1800129C4
0x180012964  sub     rdx, r14
0x180012967  lea     rcx, [r14+rdi]; Destination
0x18001296b  sub     rdx, rdi; DestinationSize
0x18001296e  sub     r9, rdi; SourceSize
0x180012971  mov     r8, rdi; Source
0x180012974  call    cs:__imp_memmove_s
0x18001297a  add     [rbx+20h], r14
0x18001297e  test    sil, sil
0x180012981  jnz     short loc_180012996
0x180012983  mov     r8, [rbx+20h]; unsigned __int8 *
0x180012987  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001298b  lea     rcx, [rbp+var_40]; this
0x18001298f  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180012994  jmp     short loc_1800129AA
0x180012996  cmp     [rbp+var_3E], 0
0x18001299a  jz      short loc_1800129AA
0x18001299c  mov     edx, [rbp+var_3C]
0x18001299f  lea     rcx, [rbp+var_40]; this
0x1800129a3  inc     edx; unsigned int
0x1800129a5  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800129aa  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800129ae  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800129b2  lea     rcx, [rbp+var_20]; this
0x1800129b6  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800129bb  mov     byte ptr [rbx+38h], 1
0x1800129bf  jmp     loc_1800128CE
0x1800129c4  xor     al, al
0x1800129c6  mov     rbx, [rsp+70h+arg_8]
0x1800129ce  add     rsp, 70h
0x1800129d2  pop     r15
0x1800129d4  pop     r14
0x1800129d6  pop     r13
0x1800129d8  pop     r12
0x1800129da  pop     rdi
0x1800129db  pop     rsi
0x1800129dc  pop     rbp
0x1800129dd  retn
```

# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007188`
- end: `0x180007362`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007094`

## callees

- `0x180007188`
- `0x18000ab8c`
- `0x18000b200`
- `0x18000b3a8`
- `0x18000b960`
- `0x18000c0b4`
- `0x18000c5e4`
- `0x18000c754`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800072f8`
- `msvcrt!memmove_s` at `0x1800072f8`

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
0x180007188  mov     [rsp-38h+arg_8], rbx
0x18000718d  mov     [rsp-38h+arg_18], r9
0x180007192  push    rbp
0x180007193  push    rsi
0x180007194  push    rdi
0x180007195  push    r12
0x180007197  push    r13
0x180007199  push    r14
0x18000719b  push    r15
0x18000719d  mov     rbp, rsp
0x1800071a0  sub     rsp, 70h
0x1800071a4  mov     rdi, [rcx+18h]
0x1800071a8  mov     r14, r8
0x1800071ab  mov     r15, rdx
0x1800071ae  mov     rbx, rcx
0x1800071b1  test    rdi, rdi
0x1800071b4  jz      loc_180007348
0x1800071ba  movzx   eax, word ptr [rcx+2]
0x1800071be  add     rdi, 0Ah
0x1800071c2  mov     [rbp+var_40], ax
0x1800071c6  xorps   xmm0, xmm0
0x1800071c9  mov     al, [rcx+4]
0x1800071cc  mov     [rbp+var_3E], al
0x1800071cf  xor     eax, eax
0x1800071d1  mov     [rbp+var_38], ax
0x1800071d5  xor     sil, sil
0x1800071d8  mov     [rbp+arg_0], rdi
0x1800071dc  mov     [rbp+var_3C], 0
0x1800071e3  movdqu  [rbp+var_30], xmm0
0x1800071e8  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800071ec  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800071f0  lea     rcx, [rbp+var_40]; this
0x1800071f4  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800071f9  mov     r12d, [rbp+arg_28]
0x1800071fd  mov     r13, [rbp+arg_20]
0x180007201  test    al, al
0x180007203  jz      short loc_18000726C
0x180007205  mov     r8, r14; unsigned __int64
0x180007208  lea     rcx, [rbp+var_40]; this
0x18000720c  mov     rdx, r15; void *
0x18000720f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180007214  test    eax, eax
0x180007216  js      short loc_18000725E
0x180007218  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18000721c  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180007220  mov     rcx, rbx; this
0x180007223  jz      short loc_180007233
0x180007225  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18000722a  mov     rdi, rax
0x18000722d  mov     [rbp+arg_0], rax
0x180007231  jmp     short loc_1800071E8
0x180007233  mov     r9, [rbp+arg_18]; void *
0x180007237  mov     [rsp+70h+var_48], r12d; unsigned int
0x18000723c  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180007241  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180007246  mov     [rbp+arg_0], rax
0x18000724a  mov     rdi, rax
0x18000724d  test    rax, rax
0x180007250  jnz     short loc_180007259
0x180007252  mov     al, 1
0x180007254  jmp     loc_18000734A
0x180007259  mov     sil, 1
0x18000725c  jmp     short loc_180007262
0x18000725e  mov     [rbp+arg_0], rdi
0x180007262  xor     r8d, r8d
0x180007265  test    sil, sil
0x180007268  jnz     short loc_180007298
0x18000726a  jmp     short loc_180007274
0x18000726c  mov     rdi, [rbp+arg_0]
0x180007270  mov     [rbx+20h], rdi
0x180007274  lea     rcx, [rbp+var_40]; this
0x180007278  mov     [rbp+var_3C], 1
0x18000727f  mov     [rbp+var_38], r14w
0x180007284  mov     qword ptr [rbp+var_30], 0
0x18000728c  mov     qword ptr [rbp+var_30+8], r15
0x180007290  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180007295  mov     r8, rax
0x180007298  movzx   ecx, word ptr [rbx+6]
0x18000729c  mov     rax, [rbp+arg_18]
0x1800072a0  mov     [rbp+var_20], cx
0x1800072a4  mov     cl, [rbx+8]
0x1800072a7  mov     [rbp+var_1E], cl
0x1800072aa  lea     rcx, [rbp+var_20]; this
0x1800072ae  mov     [rbp+var_1C], r12d
0x1800072b2  mov     [rbp+var_18], r13w
0x1800072b7  mov     [rbp+var_10], 0
0x1800072bf  mov     [rbp+var_8], rax
0x1800072c3  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800072c8  mov     rdx, [rbx+28h]
0x1800072cc  mov     r9, [rbx+20h]
0x1800072d0  mov     rcx, rdx
0x1800072d3  sub     rcx, r9
0x1800072d6  lea     r14, [rax+r8]
0x1800072da  cmp     r9, rdx
0x1800072dd  sbb     rax, rax
0x1800072e0  and     rax, rcx
0x1800072e3  cmp     rax, r14
0x1800072e6  jb      short loc_180007348
0x1800072e8  sub     rdx, r14
0x1800072eb  lea     rcx, [r14+rdi]; Destination
0x1800072ef  sub     rdx, rdi; DestinationSize
0x1800072f2  sub     r9, rdi; SourceSize
0x1800072f5  mov     r8, rdi; Source
0x1800072f8  call    cs:__imp_memmove_s
0x1800072fe  add     [rbx+20h], r14
0x180007302  test    sil, sil
0x180007305  jnz     short loc_18000731A
0x180007307  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000730b  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18000730f  lea     rcx, [rbp+var_40]; this
0x180007313  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007318  jmp     short loc_18000732E
0x18000731a  cmp     [rbp+var_3E], 0
0x18000731e  jz      short loc_18000732E
0x180007320  mov     edx, [rbp+var_3C]
0x180007323  lea     rcx, [rbp+var_40]; this
0x180007327  inc     edx; unsigned int
0x180007329  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18000732e  mov     r8, [rbx+20h]; unsigned __int8 *
0x180007332  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180007336  lea     rcx, [rbp+var_20]; this
0x18000733a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000733f  mov     byte ptr [rbx+38h], 1
0x180007343  jmp     loc_180007252
0x180007348  xor     al, al
0x18000734a  mov     rbx, [rsp+70h+arg_8]
0x180007352  add     rsp, 70h
0x180007356  pop     r15
0x180007358  pop     r14
0x18000735a  pop     r13
0x18000735c  pop     r12
0x18000735e  pop     rdi
0x18000735f  pop     rsi
0x180007360  pop     rbp
0x180007361  retn
```

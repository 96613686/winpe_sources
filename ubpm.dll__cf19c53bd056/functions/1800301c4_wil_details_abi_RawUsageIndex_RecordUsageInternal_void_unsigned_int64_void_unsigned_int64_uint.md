# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800301c4`
- end: `0x18003039e`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800300d0`

## callees

- `0x1800301c4`
- `0x1800379b0`
- `0x180037d7c`
- `0x180039274`
- `0x180039eb8`
- `0x18003ac9c`
- `0x18003b340`
- `0x18003b5ec`

## import_xrefs

- `msvcrt!memmove_s` at `0x180030334`
- `msvcrt!memmove_s` at `0x180030334`

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
  __int16 v22; // [rsp+30h] [rbp-40h] BYREF
  char v23; // [rsp+32h] [rbp-3Eh]
  int v24; // [rsp+34h] [rbp-3Ch]
  __int16 v25; // [rsp+38h] [rbp-38h]
  __int128 v26; // [rsp+40h] [rbp-30h]
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
  if ( v6 )
  {
    v10 = (unsigned __int8 *)(v6 + 10);
    v22 = *((_WORD *)this + 1);
    v23 = *((_BYTE *)this + 4);
    v25 = 0;
    v11 = 0;
    InsertionPointOrIncrement = v10;
    v24 = 0;
    v26 = 0;
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
      v15 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v22, a2, a3);
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
                                  v34,
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
    v24 = 1;
    v25 = a3;
    *(_QWORD *)&v26 = 0;
    *((_QWORD *)&v26 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
LABEL_15:
    v27 = *((_WORD *)this + 3);
    v28 = *((_BYTE *)this + 8);
    v29 = v13;
    v30 = v14;
    v31 = 0;
    v32 = v34;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    v21 = Size + v20;
    if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= Size + v20 )
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
  }
  return 0;
}

```

## disassembly

```asm
0x1800301c4  mov     [rsp-38h+arg_8], rbx
0x1800301c9  mov     [rsp-38h+arg_18], r9
0x1800301ce  push    rbp
0x1800301cf  push    rsi
0x1800301d0  push    rdi
0x1800301d1  push    r12
0x1800301d3  push    r13
0x1800301d5  push    r14
0x1800301d7  push    r15
0x1800301d9  mov     rbp, rsp
0x1800301dc  sub     rsp, 70h
0x1800301e0  mov     rdi, [rcx+18h]
0x1800301e4  mov     r14, r8
0x1800301e7  mov     r15, rdx
0x1800301ea  mov     rbx, rcx
0x1800301ed  test    rdi, rdi
0x1800301f0  jz      loc_180030384
0x1800301f6  movzx   eax, word ptr [rcx+2]
0x1800301fa  add     rdi, 0Ah
0x1800301fe  mov     [rbp+var_40], ax
0x180030202  xorps   xmm0, xmm0
0x180030205  mov     al, [rcx+4]
0x180030208  mov     [rbp+var_3E], al
0x18003020b  xor     eax, eax
0x18003020d  mov     [rbp+var_38], ax
0x180030211  xor     sil, sil
0x180030214  mov     [rbp+arg_0], rdi
0x180030218  mov     [rbp+var_3C], 0
0x18003021f  movdqu  [rbp+var_30], xmm0
0x180030224  mov     r8, [rbx+20h]; unsigned __int8 *
0x180030228  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18003022c  lea     rcx, [rbp+var_40]; this
0x180030230  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180030235  mov     r12d, [rbp+arg_28]
0x180030239  mov     r13, [rbp+arg_20]
0x18003023d  test    al, al
0x18003023f  jz      short loc_1800302A8
0x180030241  mov     r8, r14; unsigned __int64
0x180030244  lea     rcx, [rbp+var_40]; this
0x180030248  mov     rdx, r15; void *
0x18003024b  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180030250  test    eax, eax
0x180030252  js      short loc_18003029A
0x180030254  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180030258  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18003025c  mov     rcx, rbx; this
0x18003025f  jz      short loc_18003026F
0x180030261  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180030266  mov     rdi, rax
0x180030269  mov     [rbp+arg_0], rax
0x18003026d  jmp     short loc_180030224
0x18003026f  mov     r9, [rbp+arg_18]; void *
0x180030273  mov     [rsp+70h+var_48], r12d; unsigned int
0x180030278  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18003027d  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180030282  mov     [rbp+arg_0], rax
0x180030286  mov     rdi, rax
0x180030289  test    rax, rax
0x18003028c  jnz     short loc_180030295
0x18003028e  mov     al, 1
0x180030290  jmp     loc_180030386
0x180030295  mov     sil, 1
0x180030298  jmp     short loc_18003029E
0x18003029a  mov     [rbp+arg_0], rdi
0x18003029e  xor     r8d, r8d
0x1800302a1  test    sil, sil
0x1800302a4  jnz     short loc_1800302D4
0x1800302a6  jmp     short loc_1800302B0
0x1800302a8  mov     rdi, [rbp+arg_0]
0x1800302ac  mov     [rbx+20h], rdi
0x1800302b0  lea     rcx, [rbp+var_40]; this
0x1800302b4  mov     [rbp+var_3C], 1
0x1800302bb  mov     [rbp+var_38], r14w
0x1800302c0  mov     qword ptr [rbp+var_30], 0
0x1800302c8  mov     qword ptr [rbp+var_30+8], r15
0x1800302cc  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800302d1  mov     r8, rax
0x1800302d4  movzx   ecx, word ptr [rbx+6]
0x1800302d8  mov     rax, [rbp+arg_18]
0x1800302dc  mov     [rbp+var_20], cx
0x1800302e0  mov     cl, [rbx+8]
0x1800302e3  mov     [rbp+var_1E], cl
0x1800302e6  lea     rcx, [rbp+var_20]; this
0x1800302ea  mov     [rbp+var_1C], r12d
0x1800302ee  mov     [rbp+var_18], r13w
0x1800302f3  mov     [rbp+var_10], 0
0x1800302fb  mov     [rbp+var_8], rax
0x1800302ff  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180030304  mov     rdx, [rbx+28h]
0x180030308  mov     r9, [rbx+20h]
0x18003030c  mov     rcx, rdx
0x18003030f  sub     rcx, r9
0x180030312  lea     r14, [rax+r8]
0x180030316  cmp     r9, rdx
0x180030319  sbb     rax, rax
0x18003031c  and     rax, rcx
0x18003031f  cmp     rax, r14
0x180030322  jb      short loc_180030384
0x180030324  sub     rdx, r14
0x180030327  lea     rcx, [r14+rdi]; Destination
0x18003032b  sub     rdx, rdi; DestinationSize
0x18003032e  sub     r9, rdi; SourceSize
0x180030331  mov     r8, rdi; Source
0x180030334  call    cs:__imp_memmove_s
0x18003033a  add     [rbx+20h], r14
0x18003033e  test    sil, sil
0x180030341  jnz     short loc_180030356
0x180030343  mov     r8, [rbx+20h]; unsigned __int8 *
0x180030347  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18003034b  lea     rcx, [rbp+var_40]; this
0x18003034f  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180030354  jmp     short loc_18003036A
0x180030356  cmp     [rbp+var_3E], 0
0x18003035a  jz      short loc_18003036A
0x18003035c  mov     edx, [rbp+var_3C]
0x18003035f  lea     rcx, [rbp+var_40]; this
0x180030363  inc     edx; unsigned int
0x180030365  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18003036a  mov     r8, [rbx+20h]; unsigned __int8 *
0x18003036e  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180030372  lea     rcx, [rbp+var_20]; this
0x180030376  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18003037b  mov     byte ptr [rbx+38h], 1
0x18003037f  jmp     loc_18003028E
0x180030384  xor     al, al
0x180030386  mov     rbx, [rsp+70h+arg_8]
0x18003038e  add     rsp, 70h
0x180030392  pop     r15
0x180030394  pop     r14
0x180030396  pop     r13
0x180030398  pop     r12
0x18003039a  pop     rdi
0x18003039b  pop     rsi
0x18003039c  pop     rbp
0x18003039d  retn
```

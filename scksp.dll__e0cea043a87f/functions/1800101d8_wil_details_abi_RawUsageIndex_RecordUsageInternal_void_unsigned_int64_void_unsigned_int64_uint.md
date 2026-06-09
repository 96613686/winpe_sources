# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800101d8`
- end: `0x1800103bc`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800100e4`

## callees

- `0x18000d32c`
- `0x18000d7c0`
- `0x18000e668`
- `0x18000fb6c`
- `0x1800101d8`
- `0x180011294`
- `0x180011bcc`
- `0x180012148`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001031a`
- `msvcrt!memmove_s` at `0x18001031a`

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
0x1800101d8  push    rbp
0x1800101da  push    rbx
0x1800101db  push    rsi
0x1800101dc  push    rdi
0x1800101dd  push    r12
0x1800101df  push    r13
0x1800101e1  push    r14
0x1800101e3  push    r15
0x1800101e5  mov     rbp, rsp
0x1800101e8  sub     rsp, 78h
0x1800101ec  mov     rdi, [rcx+18h]
0x1800101f0  mov     r13, r9
0x1800101f3  mov     r15, r8
0x1800101f6  mov     r12, rdx
0x1800101f9  mov     rbx, rcx
0x1800101fc  test    rdi, rdi
0x1800101ff  jz      loc_1800103A9
0x180010205  movzx   eax, word ptr [rcx+2]
0x180010209  add     rdi, 0Ah
0x18001020d  mov     r8, [rcx+20h]
0x180010211  xorps   xmm0, xmm0
0x180010214  mov     [rbp+var_48], ax
0x180010218  mov     al, [rcx+4]
0x18001021b  mov     [rbp+var_46], al
0x18001021e  xor     eax, eax
0x180010220  mov     [rbp+var_40], ax
0x180010224  xor     r14b, r14b
0x180010227  mov     [rbp+Source], rdi
0x18001022b  mov     [rbp+var_44], 0
0x180010232  movdqu  [rbp+var_38], xmm0
0x180010237  jmp     short loc_180010271
0x180010239  mov     r8, r15; unsigned __int64
0x18001023c  lea     rcx, [rbp+var_48]; this
0x180010240  mov     rdx, r12; void *
0x180010243  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180010248  test    eax, eax
0x18001024a  js      loc_18001036C
0x180010250  mov     r8, [rbp+Source]; unsigned __int8 *
0x180010254  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180010258  jz      loc_18001033C
0x18001025e  mov     rcx, rbx; this
0x180010261  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180010266  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001026a  mov     rdi, rax
0x18001026d  mov     [rbp+Source], rax
0x180010271  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180010275  lea     rcx, [rbp+var_48]; this
0x180010279  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001027e  mov     sil, al
0x180010281  test    al, al
0x180010283  jnz     short loc_180010239
0x180010285  mov     rdi, [rbp+Source]
0x180010289  mov     [rbx+20h], rdi
0x18001028d  xor     r8d, r8d
0x180010290  test    r14b, r14b
0x180010293  jnz     short loc_1800102B5
0x180010295  lea     rcx, [rbp+var_48]; this
0x180010299  mov     [rbp+var_44], 1
0x1800102a0  mov     [rbp+var_40], r15w
0x1800102a5  mov     qword ptr [rbp+var_38], r8
0x1800102a9  mov     qword ptr [rbp+var_38+8], r12
0x1800102ad  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800102b2  mov     r8, rax
0x1800102b5  movzx   ecx, word ptr [rbx+6]
0x1800102b9  mov     eax, [rbp+arg_28]
0x1800102bc  mov     [rbp+var_28], cx
0x1800102c0  mov     cl, [rbx+8]
0x1800102c3  mov     [rbp+var_24], eax
0x1800102c6  mov     rax, [rbp+arg_20]
0x1800102ca  mov     [rbp+var_26], cl
0x1800102cd  lea     rcx, [rbp+var_28]; this
0x1800102d1  mov     [rbp+var_20], ax
0x1800102d5  mov     [rbp+var_18], 0
0x1800102dd  mov     [rbp+var_10], r13
0x1800102e1  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800102e6  mov     rdx, [rbx+28h]
0x1800102ea  mov     r9, [rbx+20h]
0x1800102ee  mov     rcx, rdx
0x1800102f1  sub     rcx, r9
0x1800102f4  lea     rsi, [rax+r8]
0x1800102f8  cmp     r9, rdx
0x1800102fb  sbb     rax, rax
0x1800102fe  and     rax, rcx
0x180010301  cmp     rax, rsi
0x180010304  jb      loc_1800103A9
0x18001030a  sub     rdx, rsi
0x18001030d  lea     rcx, [rsi+rdi]; Destination
0x180010311  sub     rdx, rdi; DestinationSize
0x180010314  sub     r9, rdi; SourceSize
0x180010317  mov     r8, rdi; Source
0x18001031a  call    cs:__imp_memmove_s
0x180010320  add     [rbx+20h], rsi
0x180010324  test    r14b, r14b
0x180010327  jnz     short loc_18001037E
0x180010329  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001032d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180010331  lea     rcx, [rbp+var_48]; this
0x180010335  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001033a  jmp     short loc_180010392
0x18001033c  mov     ecx, [rbp+arg_28]
0x18001033f  mov     r9, r13; void *
0x180010342  mov     [rsp+78h+var_50], ecx; unsigned int
0x180010346  mov     rcx, [rbp+arg_20]
0x18001034a  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18001034f  mov     rcx, rbx; this
0x180010352  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180010357  mov     [rbp+Source], rax
0x18001035b  mov     rdi, rax
0x18001035e  test    rax, rax
0x180010361  jnz     short loc_180010367
0x180010363  mov     al, 1
0x180010365  jmp     short loc_1800103AB
0x180010367  mov     r14b, 1
0x18001036a  jmp     short loc_180010370
0x18001036c  mov     [rbp+Source], rdi
0x180010370  test    sil, sil
0x180010373  jnz     loc_18001028D
0x180010379  jmp     loc_180010289
0x18001037e  cmp     [rbp+var_46], 0
0x180010382  jz      short loc_180010392
0x180010384  mov     edx, [rbp+var_44]
0x180010387  lea     rcx, [rbp+var_48]; this
0x18001038b  inc     edx; unsigned int
0x18001038d  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180010392  mov     r8, [rbx+20h]; unsigned __int8 *
0x180010396  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001039a  lea     rcx, [rbp+var_28]; this
0x18001039e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800103a3  mov     byte ptr [rbx+38h], 1
0x1800103a7  jmp     short loc_180010363
0x1800103a9  xor     al, al
0x1800103ab  add     rsp, 78h
0x1800103af  pop     r15
0x1800103b1  pop     r14
0x1800103b3  pop     r13
0x1800103b5  pop     r12
0x1800103b7  pop     rdi
0x1800103b8  pop     rsi
0x1800103b9  pop     rbx
0x1800103ba  pop     rbp
0x1800103bb  retn
```

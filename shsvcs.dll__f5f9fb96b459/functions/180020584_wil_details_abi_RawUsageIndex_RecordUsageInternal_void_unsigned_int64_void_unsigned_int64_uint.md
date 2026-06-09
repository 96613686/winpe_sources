# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180020584`
- end: `0x180020768`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180020490`

## callees

- `0x18001dd40`
- `0x18001e268`
- `0x18001ed00`
- `0x18001ff68`
- `0x180020584`
- `0x180021234`
- `0x180021b28`
- `0x180021f68`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800206c6`
- `msvcrt!memmove_s` at `0x1800206c6`

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
0x180020584  push    rbp
0x180020586  push    rbx
0x180020587  push    rsi
0x180020588  push    rdi
0x180020589  push    r12
0x18002058b  push    r13
0x18002058d  push    r14
0x18002058f  push    r15
0x180020591  mov     rbp, rsp
0x180020594  sub     rsp, 78h
0x180020598  mov     rdi, [rcx+18h]
0x18002059c  mov     r13, r9
0x18002059f  mov     r15, r8
0x1800205a2  mov     r12, rdx
0x1800205a5  mov     rbx, rcx
0x1800205a8  test    rdi, rdi
0x1800205ab  jz      loc_180020755
0x1800205b1  movzx   eax, word ptr [rcx+2]
0x1800205b5  add     rdi, 0Ah
0x1800205b9  mov     r8, [rcx+20h]
0x1800205bd  xorps   xmm0, xmm0
0x1800205c0  mov     [rbp+var_48], ax
0x1800205c4  mov     al, [rcx+4]
0x1800205c7  mov     [rbp+var_46], al
0x1800205ca  xor     eax, eax
0x1800205cc  mov     [rbp+var_40], ax
0x1800205d0  xor     r14b, r14b
0x1800205d3  mov     [rbp+Source], rdi
0x1800205d7  mov     [rbp+var_44], 0
0x1800205de  movdqu  [rbp+var_38], xmm0
0x1800205e3  jmp     short loc_18002061D
0x1800205e5  mov     r8, r15; unsigned __int64
0x1800205e8  lea     rcx, [rbp+var_48]; this
0x1800205ec  mov     rdx, r12; void *
0x1800205ef  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800205f4  test    eax, eax
0x1800205f6  js      loc_180020718
0x1800205fc  mov     r8, [rbp+Source]; unsigned __int8 *
0x180020600  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180020604  jz      loc_1800206E8
0x18002060a  mov     rcx, rbx; this
0x18002060d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180020612  mov     r8, [rbx+20h]; unsigned __int8 *
0x180020616  mov     rdi, rax
0x180020619  mov     [rbp+Source], rax
0x18002061d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180020621  lea     rcx, [rbp+var_48]; this
0x180020625  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002062a  mov     sil, al
0x18002062d  test    al, al
0x18002062f  jnz     short loc_1800205E5
0x180020631  mov     rdi, [rbp+Source]
0x180020635  mov     [rbx+20h], rdi
0x180020639  xor     r8d, r8d
0x18002063c  test    r14b, r14b
0x18002063f  jnz     short loc_180020661
0x180020641  lea     rcx, [rbp+var_48]; this
0x180020645  mov     [rbp+var_44], 1
0x18002064c  mov     [rbp+var_40], r15w
0x180020651  mov     qword ptr [rbp+var_38], r8
0x180020655  mov     qword ptr [rbp+var_38+8], r12
0x180020659  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18002065e  mov     r8, rax
0x180020661  movzx   ecx, word ptr [rbx+6]
0x180020665  mov     eax, [rbp+arg_28]
0x180020668  mov     [rbp+var_28], cx
0x18002066c  mov     cl, [rbx+8]
0x18002066f  mov     [rbp+var_24], eax
0x180020672  mov     rax, [rbp+arg_20]
0x180020676  mov     [rbp+var_26], cl
0x180020679  lea     rcx, [rbp+var_28]; this
0x18002067d  mov     [rbp+var_20], ax
0x180020681  mov     [rbp+var_18], 0
0x180020689  mov     [rbp+var_10], r13
0x18002068d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180020692  mov     rdx, [rbx+28h]
0x180020696  mov     r9, [rbx+20h]
0x18002069a  mov     rcx, rdx
0x18002069d  sub     rcx, r9
0x1800206a0  lea     rsi, [rax+r8]
0x1800206a4  cmp     r9, rdx
0x1800206a7  sbb     rax, rax
0x1800206aa  and     rax, rcx
0x1800206ad  cmp     rax, rsi
0x1800206b0  jb      loc_180020755
0x1800206b6  sub     rdx, rsi
0x1800206b9  lea     rcx, [rsi+rdi]; Destination
0x1800206bd  sub     rdx, rdi; DestinationSize
0x1800206c0  sub     r9, rdi; SourceSize
0x1800206c3  mov     r8, rdi; Source
0x1800206c6  call    cs:__imp_memmove_s
0x1800206cc  add     [rbx+20h], rsi
0x1800206d0  test    r14b, r14b
0x1800206d3  jnz     short loc_18002072A
0x1800206d5  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800206d9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800206dd  lea     rcx, [rbp+var_48]; this
0x1800206e1  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800206e6  jmp     short loc_18002073E
0x1800206e8  mov     ecx, [rbp+arg_28]
0x1800206eb  mov     r9, r13; void *
0x1800206ee  mov     [rsp+78h+var_50], ecx; unsigned int
0x1800206f2  mov     rcx, [rbp+arg_20]
0x1800206f6  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x1800206fb  mov     rcx, rbx; this
0x1800206fe  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180020703  mov     [rbp+Source], rax
0x180020707  mov     rdi, rax
0x18002070a  test    rax, rax
0x18002070d  jnz     short loc_180020713
0x18002070f  mov     al, 1
0x180020711  jmp     short loc_180020757
0x180020713  mov     r14b, 1
0x180020716  jmp     short loc_18002071C
0x180020718  mov     [rbp+Source], rdi
0x18002071c  test    sil, sil
0x18002071f  jnz     loc_180020639
0x180020725  jmp     loc_180020635
0x18002072a  cmp     [rbp+var_46], 0
0x18002072e  jz      short loc_18002073E
0x180020730  mov     edx, [rbp+var_44]
0x180020733  lea     rcx, [rbp+var_48]; this
0x180020737  inc     edx; unsigned int
0x180020739  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18002073e  mov     r8, [rbx+20h]; unsigned __int8 *
0x180020742  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180020746  lea     rcx, [rbp+var_28]; this
0x18002074a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18002074f  mov     byte ptr [rbx+38h], 1
0x180020753  jmp     short loc_18002070F
0x180020755  xor     al, al
0x180020757  add     rsp, 78h
0x18002075b  pop     r15
0x18002075d  pop     r14
0x18002075f  pop     r13
0x180020761  pop     r12
0x180020763  pop     rdi
0x180020764  pop     rsi
0x180020765  pop     rbx
0x180020766  pop     rbp
0x180020767  retn
```

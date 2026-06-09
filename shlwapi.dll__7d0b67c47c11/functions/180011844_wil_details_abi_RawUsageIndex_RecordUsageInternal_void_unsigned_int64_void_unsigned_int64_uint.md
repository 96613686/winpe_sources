# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180011844`
- end: `0x180011a42`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `510`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011734`

## callees

- `0x180011844`
- `0x180012550`
- `0x18001a0d4`
- `0x18001a780`
- `0x18001a9a0`
- `0x18001b14c`
- `0x18001bd70`
- `0x18001c1b4`
- `0x18001c4d0`

## import_xrefs

- `ntdll!memmove_s` at `0x1800119c9`
- `ntdll!memmove_s` at `0x1800119c9`

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
  unsigned __int8 *v11; // rdi
  char v12; // si
  int v13; // eax
  unsigned __int64 Size; // rax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r14
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v21; // [rsp+38h] [rbp-41h]
  __int16 v22; // [rsp+40h] [rbp-39h] BYREF
  char v23; // [rsp+42h] [rbp-37h]
  int v24; // [rsp+44h] [rbp-35h]
  __int16 v25; // [rsp+48h] [rbp-31h]
  __int128 v26; // [rsp+50h] [rbp-29h]
  __int16 v27; // [rsp+60h] [rbp-19h] BYREF
  char v28; // [rsp+62h] [rbp-17h]
  unsigned int v29; // [rsp+64h] [rbp-15h]
  __int16 v30; // [rsp+68h] [rbp-11h]
  __int64 v31; // [rsp+70h] [rbp-9h]
  void *v32; // [rsp+78h] [rbp-1h]

  v6 = *((_QWORD *)this + 3);
  v21 = a6;
  if ( v6 )
  {
    v11 = (unsigned __int8 *)(v6 + 10);
    v22 = *((_WORD *)this + 1);
    v23 = *((_BYTE *)this + 4);
    v25 = 0;
    v12 = 0;
    InsertionPointOrIncrement = v11;
    v24 = 0;
    v26 = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v22,
              &InsertionPointOrIncrement,
              *((unsigned __int8 **)this + 4)) )
      {
        v11 = InsertionPointOrIncrement;
        *((_QWORD *)this + 4) = InsertionPointOrIncrement;
        goto LABEL_14;
      }
      v13 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v22, a2, a3);
      if ( v13 < 0 )
      {
        InsertionPointOrIncrement = v11;
        goto LABEL_11;
      }
      if ( !v13 )
        break;
      v11 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v22,
              InsertionPointOrIncrement);
      InsertionPointOrIncrement = v11;
    }
    InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                  this,
                                  (struct wil::details_abi::UsageIndexProperty *)&v22,
                                  InsertionPointOrIncrement,
                                  a4,
                                  a5,
                                  v21);
    v11 = InsertionPointOrIncrement;
    if ( !InsertionPointOrIncrement )
      return 1;
    v12 = 1;
LABEL_11:
    if ( v12 )
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
    v29 = v21;
    v30 = a5;
    v31 = 0;
    v32 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v16 = *((_QWORD *)this + 5);
    v17 = *((_QWORD *)this + 4);
    v19 = Size + v18;
    if ( ((v16 - v17) & -(__int64)(v17 < v16)) >= Size + v18 )
    {
      memmove_s(&v11[v19], v16 - v19 - (_QWORD)v11, v11, v17 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v19;
      if ( v12 )
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
0x180011844  mov     [rsp-8+arg_8], rbx
0x180011849  push    rbp
0x18001184a  push    rsi
0x18001184b  push    rdi
0x18001184c  push    r12
0x18001184e  push    r13
0x180011850  push    r14
0x180011852  push    r15
0x180011854  lea     rbp, [rsp-17h]
0x180011859  sub     rsp, 90h
0x180011860  mov     rax, cs:__security_cookie
0x180011867  xor     rax, rsp
0x18001186a  mov     [rbp+47h+var_40], rax
0x18001186e  mov     rdi, [rcx+18h]
0x180011872  mov     r12, r9
0x180011875  mov     eax, [rbp+47h+arg_28]
0x180011878  mov     r14, r8
0x18001187b  mov     r13, [rbp+47h+arg_20]
0x18001187f  mov     r15, rdx
0x180011882  mov     [rbp+47h+var_88], eax
0x180011885  mov     rbx, rcx
0x180011888  test    rdi, rdi
0x18001188b  jz      loc_180011A19
0x180011891  movzx   eax, word ptr [rcx+2]
0x180011895  add     rdi, 0Ah
0x180011899  mov     [rbp+47h+var_80], ax
0x18001189d  xorps   xmm0, xmm0
0x1800118a0  mov     al, [rcx+4]
0x1800118a3  mov     [rbp+47h+var_7E], al
0x1800118a6  xor     eax, eax
0x1800118a8  mov     [rbp+47h+var_78], ax
0x1800118ac  xor     sil, sil
0x1800118af  mov     [rbp+47h+var_90], rdi
0x1800118b3  mov     [rbp+47h+var_7C], 0
0x1800118ba  movdqu  [rbp+47h+var_70], xmm0
0x1800118bf  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800118c3  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x1800118c7  lea     rcx, [rbp+47h+var_80]; this
0x1800118cb  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800118d0  test    al, al
0x1800118d2  jz      short loc_18001193F
0x1800118d4  mov     r8, r14; unsigned __int64
0x1800118d7  lea     rcx, [rbp+47h+var_80]; this
0x1800118db  mov     rdx, r15; void *
0x1800118de  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800118e3  test    eax, eax
0x1800118e5  js      short loc_180011931
0x1800118e7  mov     r8, [rbp+47h+var_90]; unsigned __int8 *
0x1800118eb  lea     rdx, [rbp+47h+var_80]; struct wil::details_abi::UsageIndexProperty *
0x1800118ef  jz      short loc_180011902
0x1800118f1  mov     rcx, rbx; this
0x1800118f4  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800118f9  mov     rdi, rax
0x1800118fc  mov     [rbp+47h+var_90], rax
0x180011900  jmp     short loc_1800118BF
0x180011902  mov     ecx, [rbp+47h+var_88]
0x180011905  mov     r9, r12; void *
0x180011908  mov     [rsp+0C0h+var_98], ecx; unsigned int
0x18001190c  mov     rcx, rbx; this
0x18001190f  mov     [rsp+0C0h+var_A0], r13; unsigned __int64
0x180011914  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180011919  mov     [rbp+47h+var_90], rax
0x18001191d  mov     rdi, rax
0x180011920  test    rax, rax
0x180011923  jnz     short loc_18001192C
0x180011925  mov     al, 1
0x180011927  jmp     loc_180011A1B
0x18001192c  mov     sil, 1
0x18001192f  jmp     short loc_180011935
0x180011931  mov     [rbp+47h+var_90], rdi
0x180011935  xor     r8d, r8d
0x180011938  test    sil, sil
0x18001193b  jnz     short loc_18001196B
0x18001193d  jmp     short loc_180011947
0x18001193f  mov     rdi, [rbp+47h+var_90]
0x180011943  mov     [rbx+20h], rdi
0x180011947  lea     rcx, [rbp+47h+var_80]; this
0x18001194b  mov     [rbp+47h+var_7C], 1
0x180011952  mov     [rbp+47h+var_78], r14w
0x180011957  mov     qword ptr [rbp+47h+var_70], 0
0x18001195f  mov     qword ptr [rbp+47h+var_70+8], r15
0x180011963  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180011968  mov     r8, rax
0x18001196b  movzx   ecx, word ptr [rbx+6]
0x18001196f  mov     eax, [rbp+47h+var_88]
0x180011972  mov     [rbp+47h+var_60], cx
0x180011976  mov     cl, [rbx+8]
0x180011979  mov     [rbp+47h+var_5E], cl
0x18001197c  lea     rcx, [rbp+47h+var_60]; this
0x180011980  mov     [rbp+47h+var_5C], eax
0x180011983  mov     [rbp+47h+var_58], r13w
0x180011988  mov     [rbp+47h+var_50], 0
0x180011990  mov     [rbp+47h+var_48], r12
0x180011994  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180011999  mov     rdx, [rbx+28h]
0x18001199d  mov     r9, [rbx+20h]
0x1800119a1  mov     rcx, rdx
0x1800119a4  sub     rcx, r9
0x1800119a7  lea     r14, [rax+r8]
0x1800119ab  cmp     r9, rdx
0x1800119ae  sbb     rax, rax
0x1800119b1  and     rax, rcx
0x1800119b4  cmp     rax, r14
0x1800119b7  jb      short loc_180011A19
0x1800119b9  sub     rdx, r14
0x1800119bc  lea     rcx, [r14+rdi]; Destination
0x1800119c0  sub     rdx, rdi; DestinationSize
0x1800119c3  sub     r9, rdi; SourceSize
0x1800119c6  mov     r8, rdi; Source
0x1800119c9  call    cs:__imp_memmove_s
0x1800119cf  add     [rbx+20h], r14
0x1800119d3  test    sil, sil
0x1800119d6  jnz     short loc_1800119EB
0x1800119d8  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800119dc  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x1800119e0  lea     rcx, [rbp+47h+var_80]; this
0x1800119e4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800119e9  jmp     short loc_1800119FF
0x1800119eb  cmp     [rbp+47h+var_7E], 0
0x1800119ef  jz      short loc_1800119FF
0x1800119f1  mov     edx, [rbp+47h+var_7C]
0x1800119f4  lea     rcx, [rbp+47h+var_80]; this
0x1800119f8  inc     edx; unsigned int
0x1800119fa  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800119ff  mov     r8, [rbx+20h]; unsigned __int8 *
0x180011a03  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x180011a07  lea     rcx, [rbp+47h+var_60]; this
0x180011a0b  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180011a10  mov     byte ptr [rbx+38h], 1
0x180011a14  jmp     loc_180011925
0x180011a19  xor     al, al
0x180011a1b  mov     rcx, [rbp+47h+var_40]
0x180011a1f  xor     rcx, rsp; StackCookie
0x180011a22  call    __security_check_cookie
0x180011a27  mov     rbx, [rsp+0C0h+arg_8]
0x180011a2f  add     rsp, 90h
0x180011a36  pop     r15
0x180011a38  pop     r14
0x180011a3a  pop     r13
0x180011a3c  pop     r12
0x180011a3e  pop     rdi
0x180011a3f  pop     rsi
0x180011a40  pop     rbp
0x180011a41  retn
```

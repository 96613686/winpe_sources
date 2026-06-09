# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800233bc`
- end: `0x180023596`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800232c8`

## callees

- `0x1800233bc`
- `0x180028f38`
- `0x180029218`
- `0x1800299a8`
- `0x18002a920`
- `0x18002b800`
- `0x18002be78`
- `0x18002c26c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18002352c`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18002352c`

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
0x1800233bc  mov     [rsp-38h+arg_8], rbx
0x1800233c1  mov     [rsp-38h+arg_18], r9
0x1800233c6  push    rbp
0x1800233c7  push    rsi
0x1800233c8  push    rdi
0x1800233c9  push    r12
0x1800233cb  push    r13
0x1800233cd  push    r14
0x1800233cf  push    r15
0x1800233d1  mov     rbp, rsp
0x1800233d4  sub     rsp, 70h
0x1800233d8  mov     rdi, [rcx+18h]
0x1800233dc  mov     r14, r8
0x1800233df  mov     r15, rdx
0x1800233e2  mov     rbx, rcx
0x1800233e5  test    rdi, rdi
0x1800233e8  jz      loc_18002357C
0x1800233ee  movzx   eax, word ptr [rcx+2]
0x1800233f2  add     rdi, 0Ah
0x1800233f6  mov     [rbp+var_40], ax
0x1800233fa  xorps   xmm0, xmm0
0x1800233fd  mov     al, [rcx+4]
0x180023400  mov     [rbp+var_3E], al
0x180023403  xor     eax, eax
0x180023405  mov     [rbp+var_38], ax
0x180023409  xor     sil, sil
0x18002340c  mov     [rbp+arg_0], rdi
0x180023410  mov     [rbp+var_3C], 0
0x180023417  movdqu  [rbp+var_30], xmm0
0x18002341c  mov     r8, [rbx+20h]; unsigned __int8 *
0x180023420  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180023424  lea     rcx, [rbp+var_40]; this
0x180023428  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002342d  mov     r12d, [rbp+arg_28]
0x180023431  mov     r13, [rbp+arg_20]
0x180023435  test    al, al
0x180023437  jz      short loc_1800234A0
0x180023439  mov     r8, r14; unsigned __int64
0x18002343c  lea     rcx, [rbp+var_40]; this
0x180023440  mov     rdx, r15; void *
0x180023443  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180023448  test    eax, eax
0x18002344a  js      short loc_180023492
0x18002344c  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180023450  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180023454  mov     rcx, rbx; this
0x180023457  jz      short loc_180023467
0x180023459  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18002345e  mov     rdi, rax
0x180023461  mov     [rbp+arg_0], rax
0x180023465  jmp     short loc_18002341C
0x180023467  mov     r9, [rbp+arg_18]; void *
0x18002346b  mov     [rsp+70h+var_48], r12d; unsigned int
0x180023470  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180023475  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18002347a  mov     [rbp+arg_0], rax
0x18002347e  mov     rdi, rax
0x180023481  test    rax, rax
0x180023484  jnz     short loc_18002348D
0x180023486  mov     al, 1
0x180023488  jmp     loc_18002357E
0x18002348d  mov     sil, 1
0x180023490  jmp     short loc_180023496
0x180023492  mov     [rbp+arg_0], rdi
0x180023496  xor     r8d, r8d
0x180023499  test    sil, sil
0x18002349c  jnz     short loc_1800234CC
0x18002349e  jmp     short loc_1800234A8
0x1800234a0  mov     rdi, [rbp+arg_0]
0x1800234a4  mov     [rbx+20h], rdi
0x1800234a8  lea     rcx, [rbp+var_40]; this
0x1800234ac  mov     [rbp+var_3C], 1
0x1800234b3  mov     [rbp+var_38], r14w
0x1800234b8  mov     qword ptr [rbp+var_30], 0
0x1800234c0  mov     qword ptr [rbp+var_30+8], r15
0x1800234c4  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800234c9  mov     r8, rax
0x1800234cc  movzx   ecx, word ptr [rbx+6]
0x1800234d0  mov     rax, [rbp+arg_18]
0x1800234d4  mov     [rbp+var_20], cx
0x1800234d8  mov     cl, [rbx+8]
0x1800234db  mov     [rbp+var_1E], cl
0x1800234de  lea     rcx, [rbp+var_20]; this
0x1800234e2  mov     [rbp+var_1C], r12d
0x1800234e6  mov     [rbp+var_18], r13w
0x1800234eb  mov     [rbp+var_10], 0
0x1800234f3  mov     [rbp+var_8], rax
0x1800234f7  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800234fc  mov     rdx, [rbx+28h]
0x180023500  mov     r9, [rbx+20h]
0x180023504  mov     rcx, rdx
0x180023507  sub     rcx, r9
0x18002350a  lea     r14, [rax+r8]
0x18002350e  cmp     r9, rdx
0x180023511  sbb     rax, rax
0x180023514  and     rax, rcx
0x180023517  cmp     rax, r14
0x18002351a  jb      short loc_18002357C
0x18002351c  sub     rdx, r14
0x18002351f  lea     rcx, [r14+rdi]; Destination
0x180023523  sub     rdx, rdi; DestinationSize
0x180023526  sub     r9, rdi; SourceSize
0x180023529  mov     r8, rdi; Source
0x18002352c  call    cs:__imp_memmove_s
0x180023532  add     [rbx+20h], r14
0x180023536  test    sil, sil
0x180023539  jnz     short loc_18002354E
0x18002353b  mov     r8, [rbx+20h]; unsigned __int8 *
0x18002353f  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180023543  lea     rcx, [rbp+var_40]; this
0x180023547  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18002354c  jmp     short loc_180023562
0x18002354e  cmp     [rbp+var_3E], 0
0x180023552  jz      short loc_180023562
0x180023554  mov     edx, [rbp+var_3C]
0x180023557  lea     rcx, [rbp+var_40]; this
0x18002355b  inc     edx; unsigned int
0x18002355d  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180023562  mov     r8, [rbx+20h]; unsigned __int8 *
0x180023566  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18002356a  lea     rcx, [rbp+var_20]; this
0x18002356e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180023573  mov     byte ptr [rbx+38h], 1
0x180023577  jmp     loc_180023486
0x18002357c  xor     al, al
0x18002357e  mov     rbx, [rsp+70h+arg_8]
0x180023586  add     rsp, 70h
0x18002358a  pop     r15
0x18002358c  pop     r14
0x18002358e  pop     r13
0x180023590  pop     r12
0x180023592  pop     rdi
0x180023593  pop     rsi
0x180023594  pop     rbp
0x180023595  retn
```

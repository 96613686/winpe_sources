# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180024e38`
- end: `0x180025019`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `481`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024d44`

## callees

- `0x180024e38`
- `0x18002adc4`
- `0x18002b0c4`
- `0x18002b894`
- `0x18002c8fc`
- `0x18002d790`
- `0x18002ddac`
- `0x18002e208`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180024fa8`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180024fa8`

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
0x180024e38  mov     [rsp-38h+arg_8], rbx
0x180024e3d  mov     [rsp-38h+arg_18], r9
0x180024e42  push    rbp
0x180024e43  push    rsi
0x180024e44  push    rdi
0x180024e45  push    r12
0x180024e47  push    r13
0x180024e49  push    r14
0x180024e4b  push    r15
0x180024e4d  mov     rbp, rsp
0x180024e50  sub     rsp, 70h
0x180024e54  mov     rdi, [rcx+18h]
0x180024e58  mov     r14, r8
0x180024e5b  mov     r15, rdx
0x180024e5e  mov     rbx, rcx
0x180024e61  test    rdi, rdi
0x180024e64  jz      loc_180024FFE
0x180024e6a  movzx   eax, word ptr [rcx+2]
0x180024e6e  add     rdi, 0Ah
0x180024e72  mov     [rbp+var_40], ax
0x180024e76  xorps   xmm0, xmm0
0x180024e79  mov     al, [rcx+4]
0x180024e7c  mov     [rbp+var_3E], al
0x180024e7f  xor     eax, eax
0x180024e81  mov     [rbp+var_38], ax
0x180024e85  xor     sil, sil
0x180024e88  mov     [rbp+arg_0], rdi
0x180024e8c  mov     [rbp+var_3C], 0
0x180024e93  movdqu  [rbp+var_30], xmm0
0x180024e98  mov     r8, [rbx+20h]; unsigned __int8 *
0x180024e9c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180024ea0  lea     rcx, [rbp+var_40]; this
0x180024ea4  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180024ea9  mov     r12d, [rbp+arg_28]
0x180024ead  mov     r13, [rbp+arg_20]
0x180024eb1  test    al, al
0x180024eb3  jz      short loc_180024F1C
0x180024eb5  mov     r8, r14; unsigned __int64
0x180024eb8  lea     rcx, [rbp+var_40]; this
0x180024ebc  mov     rdx, r15; void *
0x180024ebf  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180024ec4  test    eax, eax
0x180024ec6  js      short loc_180024F0E
0x180024ec8  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180024ecc  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180024ed0  mov     rcx, rbx; this
0x180024ed3  jz      short loc_180024EE3
0x180024ed5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180024eda  mov     rdi, rax
0x180024edd  mov     [rbp+arg_0], rax
0x180024ee1  jmp     short loc_180024E98
0x180024ee3  mov     r9, [rbp+arg_18]; void *
0x180024ee7  mov     [rsp+70h+var_48], r12d; unsigned int
0x180024eec  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180024ef1  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180024ef6  mov     [rbp+arg_0], rax
0x180024efa  mov     rdi, rax
0x180024efd  test    rax, rax
0x180024f00  jnz     short loc_180024F09
0x180024f02  mov     al, 1
0x180024f04  jmp     loc_180025000
0x180024f09  mov     sil, 1
0x180024f0c  jmp     short loc_180024F12
0x180024f0e  mov     [rbp+arg_0], rdi
0x180024f12  xor     r8d, r8d
0x180024f15  test    sil, sil
0x180024f18  jnz     short loc_180024F48
0x180024f1a  jmp     short loc_180024F24
0x180024f1c  mov     rdi, [rbp+arg_0]
0x180024f20  mov     [rbx+20h], rdi
0x180024f24  lea     rcx, [rbp+var_40]; this
0x180024f28  mov     [rbp+var_3C], 1
0x180024f2f  mov     [rbp+var_38], r14w
0x180024f34  mov     qword ptr [rbp+var_30], 0
0x180024f3c  mov     qword ptr [rbp+var_30+8], r15
0x180024f40  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180024f45  mov     r8, rax
0x180024f48  movzx   ecx, word ptr [rbx+6]
0x180024f4c  mov     rax, [rbp+arg_18]
0x180024f50  mov     [rbp+var_20], cx
0x180024f54  mov     cl, [rbx+8]
0x180024f57  mov     [rbp+var_1E], cl
0x180024f5a  lea     rcx, [rbp+var_20]; this
0x180024f5e  mov     [rbp+var_1C], r12d
0x180024f62  mov     [rbp+var_18], r13w
0x180024f67  mov     [rbp+var_10], 0
0x180024f6f  mov     [rbp+var_8], rax
0x180024f73  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180024f78  mov     rdx, [rbx+28h]
0x180024f7c  mov     r9, [rbx+20h]
0x180024f80  mov     rcx, rdx
0x180024f83  sub     rcx, r9
0x180024f86  lea     r14, [rax+r8]
0x180024f8a  cmp     r9, rdx
0x180024f8d  sbb     rax, rax
0x180024f90  and     rax, rcx
0x180024f93  cmp     rax, r14
0x180024f96  jb      short loc_180024FFE
0x180024f98  sub     rdx, r14
0x180024f9b  lea     rcx, [r14+rdi]; Destination
0x180024f9f  sub     rdx, rdi; DestinationSize
0x180024fa2  sub     r9, rdi; SourceSize
0x180024fa5  mov     r8, rdi; Source
0x180024fa8  call    cs:__imp_memmove_s
0x180024faf  nop     dword ptr [rax+rax+00h]
0x180024fb4  add     [rbx+20h], r14
0x180024fb8  test    sil, sil
0x180024fbb  jnz     short loc_180024FD0
0x180024fbd  mov     r8, [rbx+20h]; unsigned __int8 *
0x180024fc1  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180024fc5  lea     rcx, [rbp+var_40]; this
0x180024fc9  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180024fce  jmp     short loc_180024FE4
0x180024fd0  cmp     [rbp+var_3E], 0
0x180024fd4  jz      short loc_180024FE4
0x180024fd6  mov     edx, [rbp+var_3C]
0x180024fd9  lea     rcx, [rbp+var_40]; this
0x180024fdd  inc     edx; unsigned int
0x180024fdf  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180024fe4  mov     r8, [rbx+20h]; unsigned __int8 *
0x180024fe8  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180024fec  lea     rcx, [rbp+var_20]; this
0x180024ff0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180024ff5  mov     byte ptr [rbx+38h], 1
0x180024ff9  jmp     loc_180024F02
0x180024ffe  xor     al, al
0x180025000  mov     rbx, [rsp+70h+arg_8]
0x180025008  add     rsp, 70h
0x18002500c  pop     r15
0x18002500e  pop     r14
0x180025010  pop     r13
0x180025012  pop     r12
0x180025014  pop     rdi
0x180025015  pop     rsi
0x180025016  pop     rbp
0x180025017  retn
```

# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180028cf4`
- end: `0x180028f12`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `542`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028be4`

## callees

- `0x1800050f0`
- `0x180027530`
- `0x1800277a4`
- `0x180027a00`
- `0x180028724`
- `0x180028cf4`
- `0x180029878`
- `0x18002a0cc`
- `0x18002a274`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180028e5a`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180028e5a`

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
  __int64 v7; // rdi
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
  void *Source; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v25; // [rsp+38h] [rbp-41h]
  unsigned __int64 v26; // [rsp+40h] [rbp-39h]
  __int16 v27; // [rsp+48h] [rbp-31h] BYREF
  char v28; // [rsp+4Ah] [rbp-2Fh]
  int v29; // [rsp+4Ch] [rbp-2Dh]
  __int16 v30; // [rsp+50h] [rbp-29h]
  __int128 v31; // [rsp+58h] [rbp-21h]
  __int16 v32; // [rsp+68h] [rbp-11h] BYREF
  char v33; // [rsp+6Ah] [rbp-Fh]
  unsigned int v34; // [rsp+6Ch] [rbp-Dh]
  __int16 v35; // [rsp+70h] [rbp-9h]
  __int64 v36; // [rsp+78h] [rbp-1h]
  void *v37; // [rsp+80h] [rbp+7h]

  v7 = *((_QWORD *)this + 3);
  v26 = a5;
  v25 = a6;
  if ( v7 )
  {
    v11 = (char *)(v7 + 10);
    v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
    v27 = *((_WORD *)this + 1);
    v28 = *((_BYTE *)this + 4);
    v30 = 0;
    v13 = 0;
    Source = v11;
    v29 = 0;
    v31 = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v27,
              (unsigned __int8 **)&Source,
              v12) )
      {
        v11 = (char *)Source;
        *((_QWORD *)this + 4) = Source;
        goto LABEL_8;
      }
      v14 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v27, a2, a3);
      if ( v14 < 0 )
      {
        Source = v11;
        goto LABEL_8;
      }
      if ( !v14 )
        break;
      v15 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v27,
              (unsigned __int8 *)Source);
      v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
      v11 = (char *)v15;
      Source = v15;
    }
    Source = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
               this,
               (struct wil::details_abi::UsageIndexProperty *)&v27,
               (unsigned __int8 *)Source,
               a4,
               v26,
               v25);
    v11 = (char *)Source;
    if ( !Source )
      return 1;
    v13 = 1;
LABEL_8:
    if ( !v13 )
    {
      v29 = 1;
      v30 = a3;
      *(_QWORD *)&v31 = 0;
      *((_QWORD *)&v31 + 1) = a2;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    }
    v32 = *((_WORD *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v34 = v25;
    v33 = v17;
    v35 = v26;
    v36 = 0;
    v37 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v32);
    v19 = *((_QWORD *)this + 5);
    v20 = *((_QWORD *)this + 4);
    v22 = Size + v21;
    if ( ((v19 - v20) & -(__int64)(v20 < v19)) >= Size + v21 )
    {
      memmove_s(&v11[v22], v19 - v22 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v22;
      if ( v13 )
      {
        if ( v28 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v27, v29 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v27,
          (unsigned __int8 **)&Source,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v32,
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
0x180028cf4  mov     [rsp-8+arg_8], rbx
0x180028cf9  push    rbp
0x180028cfa  push    rsi
0x180028cfb  push    rdi
0x180028cfc  push    r12
0x180028cfe  push    r13
0x180028d00  push    r14
0x180028d02  push    r15
0x180028d04  lea     rbp, [rsp-17h]
0x180028d09  sub     rsp, 90h
0x180028d10  mov     rax, cs:__security_cookie
0x180028d17  xor     rax, rsp
0x180028d1a  mov     [rbp+47h+var_38], rax
0x180028d1e  mov     rax, [rbp+47h+arg_20]
0x180028d22  mov     r13, r9
0x180028d25  mov     rdi, [rcx+18h]
0x180028d29  mov     r15, r8
0x180028d2c  mov     [rbp+47h+var_80], rax
0x180028d30  mov     r12, rdx
0x180028d33  mov     eax, [rbp+47h+arg_28]
0x180028d36  mov     rbx, rcx
0x180028d39  mov     [rbp+47h+var_88], eax
0x180028d3c  test    rdi, rdi
0x180028d3f  jz      loc_180028EE9
0x180028d45  movzx   eax, word ptr [rcx+2]
0x180028d49  add     rdi, 0Ah
0x180028d4d  mov     r8, [rcx+20h]
0x180028d51  xorps   xmm0, xmm0
0x180028d54  mov     [rbp+47h+var_78], ax
0x180028d58  mov     al, [rcx+4]
0x180028d5b  mov     [rbp+47h+var_76], al
0x180028d5e  xor     eax, eax
0x180028d60  mov     [rbp+47h+var_70], ax
0x180028d64  xor     r14b, r14b
0x180028d67  mov     [rbp+47h+Source], rdi
0x180028d6b  mov     [rbp+47h+var_74], 0
0x180028d72  movdqu  [rbp+47h+var_68], xmm0
0x180028d77  jmp     short loc_180028DB1
0x180028d79  mov     r8, r15; unsigned __int64
0x180028d7c  lea     rcx, [rbp+47h+var_78]; this
0x180028d80  mov     rdx, r12; void *
0x180028d83  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180028d88  test    eax, eax
0x180028d8a  js      loc_180028EAC
0x180028d90  mov     r8, [rbp+47h+Source]; unsigned __int8 *
0x180028d94  lea     rdx, [rbp+47h+var_78]; struct wil::details_abi::UsageIndexProperty *
0x180028d98  jz      loc_180028E7C
0x180028d9e  mov     rcx, rbx; this
0x180028da1  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180028da6  mov     r8, [rbx+20h]; unsigned __int8 *
0x180028daa  mov     rdi, rax
0x180028dad  mov     [rbp+47h+Source], rax
0x180028db1  lea     rdx, [rbp+47h+Source]; unsigned __int8 **
0x180028db5  lea     rcx, [rbp+47h+var_78]; this
0x180028db9  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180028dbe  mov     sil, al
0x180028dc1  test    al, al
0x180028dc3  jnz     short loc_180028D79
0x180028dc5  mov     rdi, [rbp+47h+Source]
0x180028dc9  mov     [rbx+20h], rdi
0x180028dcd  xor     r8d, r8d
0x180028dd0  test    r14b, r14b
0x180028dd3  jnz     short loc_180028DF5
0x180028dd5  lea     rcx, [rbp+47h+var_78]; this
0x180028dd9  mov     [rbp+47h+var_74], 1
0x180028de0  mov     [rbp+47h+var_70], r15w
0x180028de5  mov     qword ptr [rbp+47h+var_68], r8
0x180028de9  mov     qword ptr [rbp+47h+var_68+8], r12
0x180028ded  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180028df2  mov     r8, rax
0x180028df5  movzx   ecx, word ptr [rbx+6]
0x180028df9  mov     eax, [rbp+47h+var_88]
0x180028dfc  mov     [rbp+47h+var_58], cx
0x180028e00  mov     cl, [rbx+8]
0x180028e03  mov     [rbp+47h+var_54], eax
0x180028e06  mov     rax, [rbp+47h+var_80]
0x180028e0a  mov     [rbp+47h+var_56], cl
0x180028e0d  lea     rcx, [rbp+47h+var_58]; this
0x180028e11  mov     [rbp+47h+var_50], ax
0x180028e15  mov     [rbp+47h+var_48], 0
0x180028e1d  mov     [rbp+47h+var_40], r13
0x180028e21  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180028e26  mov     rdx, [rbx+28h]
0x180028e2a  mov     r9, [rbx+20h]
0x180028e2e  mov     rcx, rdx
0x180028e31  sub     rcx, r9
0x180028e34  lea     rsi, [rax+r8]
0x180028e38  cmp     r9, rdx
0x180028e3b  sbb     rax, rax
0x180028e3e  and     rax, rcx
0x180028e41  cmp     rax, rsi
0x180028e44  jb      loc_180028EE9
0x180028e4a  sub     rdx, rsi
0x180028e4d  lea     rcx, [rsi+rdi]; Destination
0x180028e51  sub     rdx, rdi; DestinationSize
0x180028e54  sub     r9, rdi; SourceSize
0x180028e57  mov     r8, rdi; Source
0x180028e5a  call    cs:__imp_memmove_s
0x180028e60  add     [rbx+20h], rsi
0x180028e64  test    r14b, r14b
0x180028e67  jnz     short loc_180028EBE
0x180028e69  mov     r8, [rbx+20h]; unsigned __int8 *
0x180028e6d  lea     rdx, [rbp+47h+Source]; unsigned __int8 **
0x180028e71  lea     rcx, [rbp+47h+var_78]; this
0x180028e75  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180028e7a  jmp     short loc_180028ED2
0x180028e7c  mov     ecx, [rbp+47h+var_88]
0x180028e7f  mov     r9, r13; void *
0x180028e82  mov     [rsp+0C0h+var_98], ecx; unsigned int
0x180028e86  mov     rcx, [rbp+47h+var_80]
0x180028e8a  mov     [rsp+0C0h+var_A0], rcx; unsigned __int64
0x180028e8f  mov     rcx, rbx; this
0x180028e92  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180028e97  mov     [rbp+47h+Source], rax
0x180028e9b  mov     rdi, rax
0x180028e9e  test    rax, rax
0x180028ea1  jnz     short loc_180028EA7
0x180028ea3  mov     al, 1
0x180028ea5  jmp     short loc_180028EEB
0x180028ea7  mov     r14b, 1
0x180028eaa  jmp     short loc_180028EB0
0x180028eac  mov     [rbp+47h+Source], rdi
0x180028eb0  test    sil, sil
0x180028eb3  jnz     loc_180028DCD
0x180028eb9  jmp     loc_180028DC9
0x180028ebe  cmp     [rbp+47h+var_76], 0
0x180028ec2  jz      short loc_180028ED2
0x180028ec4  mov     edx, [rbp+47h+var_74]
0x180028ec7  lea     rcx, [rbp+47h+var_78]; this
0x180028ecb  inc     edx; unsigned int
0x180028ecd  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180028ed2  mov     r8, [rbx+20h]; unsigned __int8 *
0x180028ed6  lea     rdx, [rbp+47h+Source]; unsigned __int8 **
0x180028eda  lea     rcx, [rbp+47h+var_58]; this
0x180028ede  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180028ee3  mov     byte ptr [rbx+38h], 1
0x180028ee7  jmp     short loc_180028EA3
0x180028ee9  xor     al, al
0x180028eeb  mov     rcx, [rbp+47h+var_38]
0x180028eef  xor     rcx, rsp; StackCookie
0x180028ef2  call    __security_check_cookie
0x180028ef7  mov     rbx, [rsp+0C0h+arg_8]
0x180028eff  add     rsp, 90h
0x180028f06  pop     r15
0x180028f08  pop     r14
0x180028f0a  pop     r13
0x180028f0c  pop     r12
0x180028f0e  pop     rdi
0x180028f0f  pop     rsi
0x180028f10  pop     rbp
0x180028f11  retn
```

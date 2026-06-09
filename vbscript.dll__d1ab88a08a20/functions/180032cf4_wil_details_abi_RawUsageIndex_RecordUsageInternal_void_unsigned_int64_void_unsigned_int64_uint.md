# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180032cf4`
- end: `0x1800331b8`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `1220`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180032bfc`

## callees

- `0x180032cf4`
- `0x1800331c0`
- `0x18003338c`
- `0x180033b3c`
- `0x18003b0ec`
- `0x18003ead0`
- `0x180049b1c`
- `0x180079412`

## import_xrefs

- `msvcrt!memmove_s` at `0x180032edb`
- `msvcrt!memmove_s` at `0x180032edb`
- `msvcrt!memcpy_s` at `0x180032f51`
- `msvcrt!memcpy_s` at `0x180033028`
- `msvcrt!memcpy_s` at `0x1800330d3`
- `msvcrt!memcpy_s` at `0x180032f51`
- `msvcrt!memcpy_s` at `0x180033028`
- `msvcrt!memcpy_s` at `0x1800330d3`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        size_t a5,
        unsigned int a6)
{
  __int64 v6; // rsi
  unsigned __int16 v8; // r12
  unsigned __int8 *v9; // rsi
  char v10; // r14
  unsigned __int8 *v11; // rcx
  unsigned __int64 v12; // rdx
  size_t v13; // r13
  unsigned __int8 *v14; // rbx
  unsigned __int16 v15; // ax
  unsigned __int8 *v16; // r15
  int v17; // ecx
  unsigned __int64 v18; // rdx
  void *v19; // r12
  unsigned __int8 *v20; // rbx
  unsigned __int8 *v21; // rax
  char v22; // r14
  __int64 v23; // rcx
  unsigned int v24; // r8d
  char v25; // dl
  __int64 v26; // rax
  unsigned __int64 v27; // rdx
  __int64 v28; // rbx
  unsigned __int64 v29; // r9
  unsigned __int8 *v31; // r8
  int v32; // ebx
  char *v33; // rdi
  char v34; // al
  unsigned __int8 *v35; // rax
  unsigned int v36; // r14d
  unsigned __int8 *v37; // r8
  unsigned __int16 Destination; // [rsp+38h] [rbp-79h] BYREF
  unsigned __int16 v39; // [rsp+40h] [rbp-71h] BYREF
  char v40; // [rsp+42h] [rbp-6Fh]
  unsigned int v41; // [rsp+44h] [rbp-6Dh] BYREF
  unsigned __int16 v42; // [rsp+48h] [rbp-69h] BYREF
  __int128 v43; // [rsp+50h] [rbp-61h]
  unsigned __int8 *v44; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int64 v45; // [rsp+68h] [rbp-49h]
  __int16 v46; // [rsp+70h] [rbp-41h] BYREF
  char v47; // [rsp+72h] [rbp-3Fh]
  int v48; // [rsp+74h] [rbp-3Dh]
  unsigned __int16 v49; // [rsp+78h] [rbp-39h]
  void *Buf2[2]; // [rsp+80h] [rbp-31h]
  unsigned __int8 *v51; // [rsp+90h] [rbp-21h]
  __int16 v52; // [rsp+98h] [rbp-19h] BYREF
  char v53; // [rsp+9Ah] [rbp-17h]
  unsigned int v54; // [rsp+9Ch] [rbp-15h]
  __int16 v55; // [rsp+A0h] [rbp-11h]
  __int64 v56; // [rsp+A8h] [rbp-9h]
  void *v57; // [rsp+B0h] [rbp-1h]
  unsigned __int8 *v58; // [rsp+108h] [rbp+57h] BYREF
  void *Buf1; // [rsp+110h] [rbp+5Fh]
  size_t Size; // [rsp+118h] [rbp+67h]
  void *v61; // [rsp+120h] [rbp+6Fh]

  v61 = a4;
  Size = a3;
  Buf1 = a2;
  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v8 = *((_WORD *)this + 1);
  v9 = (unsigned __int8 *)(v6 + 10);
  v10 = *((_BYTE *)this + 4);
  v39 = v8;
  v11 = v9;
  v40 = v10;
  v43 = 0;
  v41 = 0;
  v42 = 0;
  LOBYTE(v58) = 0;
  while ( 1 )
  {
    v12 = *((_QWORD *)this + 4);
    v13 = a5;
    v45 = v12;
    v51 = v9;
    v44 = v9;
    if ( v10 == 1 )
    {
      v14 = v11 + 2;
      if ( (unsigned __int64)(v11 + 2) > v12 )
        break;
      Destination = 0;
      *(_QWORD *)&v43 = v11;
      memcpy_s(&Destination, 2u, v11, 2u);
      v41 = Destination;
      goto LABEL_32;
    }
    if ( v10 != 2 )
    {
      v14 = v11;
      goto LABEL_6;
    }
    v14 = v11 + 4;
    if ( (unsigned __int64)(v11 + 4) > v12 )
      break;
    *(_QWORD *)&v43 = v11;
    memcpy_s(&v41, 4u, v11, 4u);
LABEL_32:
    v10 = v40;
    v8 = v39;
    v12 = v45;
LABEL_6:
    v15 = v8;
    v42 = v8;
    if ( !v8 )
    {
      if ( (unsigned __int64)(v14 + 2) > v12 )
        break;
      memcpy_s(&v42, 2u, v14, 2u);
      v15 = v42;
      v10 = v40;
      v14 += 2;
      v8 = v39;
    }
    v16 = &v14[v15];
    if ( (unsigned __int64)v16 > v45 )
      break;
    *((_QWORD *)&v43 + 1) = v14;
    if ( Size == v15 )
      v17 = memcmp_0(Buf1, v14, Size);
    else
      v17 = Size - v15;
    if ( v17 < 0 )
    {
      v9 = v51;
      v44 = v51;
      goto LABEL_36;
    }
    if ( !v17 )
    {
      v46 = *((_WORD *)this + 3);
      v47 = *((_BYTE *)this + 8);
      v48 = 0;
      v49 = 0;
      *(_OWORD *)Buf2 = 0;
      if ( *((_QWORD *)this + 2) )
      {
        v18 = (*((_QWORD *)this + 4) - (_QWORD)v16) / *((_QWORD *)this + 2);
        if ( v41 > v18 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v39, v18);
        v19 = v61;
        v20 = &v16[*((_QWORD *)this + 2) * v41];
        v21 = wil::details_abi::RawUsageIndex::LowerBound(this, v16, v41, v61, v13);
        v9 = v21;
        if ( v21 >= v20 )
        {
LABEL_16:
          v44 = v9;
          if ( v9 )
          {
            v22 = 1;
            v23 = 0;
            goto LABEL_18;
          }
          return 1;
        }
        v31 = (unsigned __int8 *)*((_QWORD *)this + 4);
        v58 = v21;
        wil::details_abi::UsageIndexProperty::Read((wil::details_abi::UsageIndexProperty *)&v46, &v58, v31);
        if ( v13 == v49 )
          v32 = memcmp_0(v19, Buf2[1], v13);
        else
          v32 = v13 - v49;
      }
      else
      {
        v19 = v61;
        v32 = -1;
        v36 = 0;
        v9 = v16;
        while ( v36 < v41 )
        {
          v37 = (unsigned __int8 *)*((_QWORD *)this + 4);
          v58 = v9;
          if ( !wil::details_abi::UsageIndexProperty::Read((wil::details_abi::UsageIndexProperty *)&v46, &v58, v37) )
          {
            wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v39, v36);
            break;
          }
          v32 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v46, v19, v13);
          if ( v32 <= 0 )
            break;
          v9 = v58;
          ++v36;
        }
      }
      if ( v32 )
        goto LABEL_16;
      if ( v47 )
      {
        wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v46, a6 + v48);
        v33 = (char *)this + 56;
      }
      else
      {
        v33 = (char *)this + 56;
        v34 = 0;
        if ( !*v33 )
        {
LABEL_53:
          *v33 = v34;
          return 1;
        }
      }
      v34 = 1;
      goto LABEL_53;
    }
    v35 = wil::details_abi::RawUsageIndex::SkipValues(this, (struct wil::details_abi::UsageIndexProperty *)&v39, v16);
    v10 = v40;
    v9 = v35;
    v8 = v39;
    v11 = v35;
  }
  v23 = 0;
  *((_QWORD *)this + 4) = v9;
  if ( !(_BYTE)v58 )
  {
LABEL_36:
    v42 = Size;
    *((_QWORD *)&v43 + 1) = Buf1;
    v41 = 1;
    *(_QWORD *)&v43 = 0;
    if ( v8 )
      v23 = v8;
    else
      v23 = (unsigned __int16)Size + 2LL;
    if ( v10 == 1 )
    {
      v23 += 2;
    }
    else if ( v10 == 2 )
    {
      v23 += 4;
    }
  }
  v22 = (char)v58;
  v19 = v61;
LABEL_18:
  v24 = *((unsigned __int16 *)this + 3);
  v25 = *((_BYTE *)this + 8);
  v52 = v24;
  v53 = v25;
  v54 = a6;
  v55 = v13;
  v56 = 0;
  v57 = v19;
  if ( (_WORD)v24 )
    v26 = v24;
  else
    v26 = (unsigned __int16)v13 + 2LL;
  if ( v25 == 1 )
  {
    v26 += 2;
  }
  else if ( v25 == 2 )
  {
    v26 += 4;
  }
  v27 = *((_QWORD *)this + 5);
  v28 = v26 + v23;
  v29 = *((_QWORD *)this + 4);
  if ( ((v27 - v29) & -(__int64)(v29 < v27)) >= v26 + v23 )
  {
    memmove_s(&v9[v28], v27 - v28 - (_QWORD)v9, v9, v29 - (_QWORD)v9);
    *((_QWORD *)this + 4) += v28;
    if ( v22 )
    {
      if ( v40 )
        wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v39, v41 + 1);
    }
    else
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v39,
        &v44,
        *((unsigned __int8 **)this + 4));
    }
    wil::details_abi::UsageIndexProperty::Write(
      (wil::details_abi::UsageIndexProperty *)&v52,
      &v44,
      *((unsigned __int8 **)this + 4));
    *((_BYTE *)this + 56) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180032cf4  mov     rax, rsp
0x180032cf7  mov     [rax+20h], r9
0x180032cfb  mov     [rax+18h], r8
0x180032cff  mov     [rax+10h], rdx
0x180032d03  push    rbp
0x180032d04  push    rbx
0x180032d05  push    rsi
0x180032d06  push    rdi
0x180032d07  push    r12
0x180032d09  push    r13
0x180032d0b  push    r14
0x180032d0d  push    r15
0x180032d0f  lea     rbp, [rax-4Fh]
0x180032d13  sub     rsp, 0B8h
0x180032d1a  mov     rsi, [rcx+18h]
0x180032d1e  xor     r9d, r9d
0x180032d21  mov     rdi, rcx
0x180032d24  test    rsi, rsi
0x180032d27  jz      loc_180032F2B
0x180032d2d  movzx   r12d, word ptr [rcx+2]
0x180032d32  add     rsi, 0Ah
0x180032d36  mov     r14b, [rcx+4]
0x180032d3a  xorps   xmm0, xmm0
0x180032d3d  mov     [rbp+47h+var_B8], r12w
0x180032d42  mov     rcx, rsi
0x180032d45  mov     [rbp+47h+var_B6], r14b
0x180032d49  movdqu  [rbp+47h+var_A8], xmm0
0x180032d4e  mov     dword ptr [rbp+47h+var_B4], r9d
0x180032d52  mov     word ptr [rbp+47h+var_B4+4], r9w
0x180032d57  mov     byte ptr [rbp+47h+arg_0], r9b
0x180032d5b  mov     rdx, [rdi+20h]
0x180032d5f  mov     r13, [rbp+47h+arg_20]
0x180032d63  mov     [rbp+47h+var_90], rdx
0x180032d67  mov     [rbp+47h+var_68], rsi
0x180032d6b  mov     [rbp+47h+var_98], rsi
0x180032d6f  cmp     r14b, 1
0x180032d73  jz      loc_180032F2F
0x180032d79  cmp     r14b, 2
0x180032d7d  jz      loc_1800330B2
0x180032d83  mov     rbx, rcx
0x180032d86  movzx   eax, r12w
0x180032d8a  mov     word ptr [rbp+47h+var_B4+4], ax
0x180032d8e  test    r12w, r12w
0x180032d92  jz      loc_18003300F
0x180032d98  movzx   edx, ax
0x180032d9b  lea     r15, [rdx+rbx]
0x180032d9f  cmp     r15, [rbp+47h+var_90]
0x180032da3  ja      loc_180032F98
0x180032da9  mov     rcx, [rbp+47h+Size]
0x180032dad  mov     qword ptr [rbp+47h+var_A8+8], rbx
0x180032db1  cmp     rcx, rdx
0x180032db4  jnz     loc_180033005
0x180032dba  mov     r8, rcx; Size
0x180032dbd  mov     rdx, rbx; Buf2
0x180032dc0  mov     rcx, [rbp+47h+Buf1]; Buf1
0x180032dc4  call    memcmp_0
0x180032dc9  mov     ecx, eax
0x180032dcb  xor     r9d, r9d
0x180032dce  test    ecx, ecx
0x180032dd0  js      loc_180033198
0x180032dd6  jnz     loc_1800330E4
0x180032ddc  xorps   xmm0, xmm0
0x180032ddf  movzx   eax, word ptr [rdi+6]
0x180032de3  mov     [rbp+47h+var_88], ax
0x180032de7  mov     al, [rdi+8]
0x180032dea  mov     [rbp+47h+var_86], al
0x180032ded  mov     [rbp+47h+var_84], r9d
0x180032df1  mov     [rbp+47h+var_80], r9w
0x180032df6  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180032dfb  cmp     [rdi+10h], r9
0x180032dff  jbe     loc_180033118
0x180032e05  mov     rax, [rdi+20h]
0x180032e09  xor     edx, edx
0x180032e0b  sub     rax, r15
0x180032e0e  div     qword ptr [rdi+10h]
0x180032e12  mov     rdx, rax; unsigned int
0x180032e15  mov     eax, dword ptr [rbp+47h+var_B4]
0x180032e18  cmp     rax, rdx
0x180032e1b  ja      loc_18003310A
0x180032e21  mov     r8d, dword ptr [rbp+47h+var_B4]; unsigned __int64
0x180032e25  mov     rdx, r15; unsigned __int8 *
0x180032e28  mov     r12, [rbp+47h+arg_18]
0x180032e2c  mov     ebx, r8d
0x180032e2f  imul    rbx, [rdi+10h]
0x180032e34  mov     r9, r12; void *
0x180032e37  mov     [rsp+20h], r13; Size
0x180032e3c  mov     rcx, rdi; this
0x180032e3f  add     rbx, r15
0x180032e42  call    ?LowerBound@RawUsageIndex@details_abi@wil@@AEAAPEAEPEAE_KPEAX1@Z; wil::details_abi::RawUsageIndex::LowerBound(uchar *,unsigned __int64,void *,unsigned __int64)
0x180032e47  mov     rsi, rax
0x180032e4a  cmp     rax, rbx
0x180032e4d  jb      loc_18003304C
0x180032e53  xor     r9d, r9d
0x180032e56  mov     [rbp+47h+var_98], rsi
0x180032e5a  test    rsi, rsi
0x180032e5d  jz      loc_180032F14
0x180032e63  mov     r14b, 1
0x180032e66  mov     rcx, r9
0x180032e69  movzx   r8d, word ptr [rdi+6]
0x180032e6e  mov     dl, [rdi+8]
0x180032e71  mov     eax, [rbp+47h+arg_28]
0x180032e74  mov     [rbp+47h+var_60], r8w
0x180032e79  mov     [rbp+47h+var_5E], dl
0x180032e7c  mov     [rbp+47h+var_5C], eax
0x180032e7f  mov     [rbp+47h+var_58], r13w
0x180032e84  mov     [rbp+47h+var_50], r9
0x180032e88  mov     [rbp+47h+var_48], r12
0x180032e8c  test    r8w, r8w
0x180032e90  jz      loc_180032FEE
0x180032e96  mov     eax, r8d
0x180032e99  cmp     dl, 1
0x180032e9c  jz      loc_180032F8F
0x180032ea2  cmp     dl, 2
0x180032ea5  jnz     short loc_180032EAB
0x180032ea7  add     rax, 4
0x180032eab  mov     rdx, [rdi+28h]
0x180032eaf  lea     rbx, [rax+rcx]
0x180032eb3  mov     r9, [rdi+20h]
0x180032eb7  mov     rcx, rdx
0x180032eba  sub     rcx, r9
0x180032ebd  cmp     r9, rdx
0x180032ec0  sbb     rax, rax
0x180032ec3  and     rax, rcx
0x180032ec6  cmp     rax, rbx
0x180032ec9  jb      short loc_180032F2B
0x180032ecb  sub     rdx, rbx
0x180032ece  lea     rcx, [rbx+rsi]; Destination
0x180032ed2  sub     rdx, rsi; DestinationSize
0x180032ed5  sub     r9, rsi; SourceSize
0x180032ed8  mov     r8, rsi; Source
0x180032edb  call    cs:__imp_memmove_s
0x180032ee2  nop     dword ptr [rax+rax+00h]
0x180032ee7  add     [rdi+20h], rbx
0x180032eeb  xor     ecx, ecx
0x180032eed  test    r14b, r14b
0x180032ef0  jz      loc_180032F79
0x180032ef6  cmp     [rbp+47h+var_B6], cl
0x180032ef9  jnz     loc_1800331A5
0x180032eff  mov     r8, [rdi+20h]; unsigned __int8 *
0x180032f03  lea     rdx, [rbp+47h+var_98]; unsigned __int8 **
0x180032f07  lea     rcx, [rbp+47h+var_60]; this
0x180032f0b  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180032f10  mov     byte ptr [rdi+38h], 1
0x180032f14  mov     al, 1
0x180032f16  add     rsp, 0B8h
0x180032f1d  pop     r15
0x180032f1f  pop     r14
0x180032f21  pop     r13
0x180032f23  pop     r12
0x180032f25  pop     rdi
0x180032f26  pop     rsi
0x180032f27  pop     rbx
0x180032f28  pop     rbp
0x180032f29  retn
0x180032f2b  xor     al, al
0x180032f2d  jmp     short loc_180032F16
0x180032f2f  lea     rbx, [rcx+2]
0x180032f33  cmp     rbx, rdx
0x180032f36  ja      short loc_180032F98
0x180032f38  mov     [rbp+47h+Destination], r9w
0x180032f3d  mov     r8, rcx; Source
0x180032f40  mov     r9d, 2; SourceSize
0x180032f46  mov     qword ptr [rbp+47h+var_A8], rcx
0x180032f4a  mov     edx, r9d; DestinationSize
0x180032f4d  lea     rcx, [rbp+47h+Destination]; Destination
0x180032f51  call    cs:__imp_memcpy_s
0x180032f58  nop     dword ptr [rax+rax+00h]
0x180032f5d  movzx   eax, [rbp+47h+Destination]
0x180032f61  mov     dword ptr [rbp+47h+var_B4], eax
0x180032f64  mov     r14b, [rbp+47h+var_B6]
0x180032f68  xor     r9d, r9d
0x180032f6b  movzx   r12d, [rbp+47h+var_B8]
0x180032f70  mov     rdx, [rbp+47h+var_90]
0x180032f74  jmp     loc_180032D86
0x180032f79  mov     r8, [rdi+20h]; unsigned __int8 *
0x180032f7d  lea     rdx, [rbp+47h+var_98]; unsigned __int8 **
0x180032f81  lea     rcx, [rbp+47h+var_B8]; this
0x180032f85  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180032f8a  jmp     loc_180032EFF
0x180032f8f  add     rax, 2
0x180032f93  jmp     loc_180032EAB
0x180032f98  mov     rcx, r9
0x180032f9b  mov     [rdi+20h], rsi
0x180032f9f  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180032fa3  jnz     short loc_180032FDB
0x180032fa5  mov     r8, [rbp+47h+Size]
0x180032fa9  mov     rax, [rbp+47h+Buf1]
0x180032fad  mov     word ptr [rbp+47h+var_B4+4], r8w
0x180032fb2  mov     qword ptr [rbp+47h+var_A8+8], rax
0x180032fb6  mov     dword ptr [rbp+47h+var_B4], 1
0x180032fbd  mov     qword ptr [rbp+47h+var_A8], r9
0x180032fc1  test    r12w, r12w
0x180032fc5  jz      short loc_180032FFB
0x180032fc7  movzx   ecx, r12w
0x180032fcb  cmp     r14b, 1
0x180032fcf  jz      short loc_180032FE8
0x180032fd1  cmp     r14b, 2
0x180032fd5  jnz     short loc_180032FDB
0x180032fd7  add     rcx, 4
0x180032fdb  mov     r14b, byte ptr [rbp+47h+arg_0]
0x180032fdf  mov     r12, [rbp+47h+arg_18]
0x180032fe3  jmp     loc_180032E69
0x180032fe8  add     rcx, 2
0x180032fec  jmp     short loc_180032FDB
0x180032fee  movzx   eax, r13w
0x180032ff2  add     rax, 2
0x180032ff6  jmp     loc_180032E99
0x180032ffb  movzx   ecx, r8w
0x180032fff  add     rcx, 2
0x180033003  jmp     short loc_180032FCB
0x180033005  movzx   eax, ax
0x180033008  sub     ecx, eax
0x18003300a  jmp     loc_180032DCE
0x18003300f  lea     r15, [rbx+2]
0x180033013  cmp     r15, rdx
0x180033016  ja      short loc_180032F98
0x180033018  mov     r9d, 2; SourceSize
0x18003301e  lea     rcx, [rbp+47h+var_B4+4]; Destination
0x180033022  mov     edx, r9d; DestinationSize
0x180033025  mov     r8, rbx; Source
0x180033028  call    cs:__imp_memcpy_s
0x18003302f  nop     dword ptr [rax+rax+00h]
0x180033034  movzx   eax, word ptr [rbp+47h+var_B4+4]
0x180033038  xor     r9d, r9d
0x18003303b  mov     r14b, [rbp+47h+var_B6]
0x18003303f  mov     rbx, r15
0x180033042  movzx   r12d, [rbp+47h+var_B8]
0x180033047  jmp     loc_180032D98
0x18003304c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180033050  lea     rdx, [rbp+47h+arg_0]; unsigned __int8 **
0x180033054  lea     rcx, [rbp+47h+var_88]; this
0x180033058  mov     [rbp+47h+arg_0], rax
0x18003305c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180033061  movzx   eax, [rbp+47h+var_80]
0x180033065  cmp     r13, rax
0x180033068  jnz     short loc_1800330A7
0x18003306a  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18003306e  mov     r8, r13; Size
0x180033071  mov     rcx, r12; Buf1
0x180033074  call    memcmp_0
0x180033079  mov     ebx, eax
0x18003307b  xor     r9d, r9d
0x18003307e  test    ebx, ebx
0x180033080  jnz     loc_180032E56
0x180033086  cmp     [rbp+47h+var_86], r9b
0x18003308a  jnz     loc_18003317E
0x180033090  add     rdi, 38h ; '8'
0x180033094  mov     al, r9b
0x180033097  cmp     [rdi], r9b
0x18003309a  jnz     loc_180033191
0x1800330a0  mov     [rdi], al
0x1800330a2  jmp     loc_180032F14
0x1800330a7  movzx   eax, [rbp+47h+var_80]
0x1800330ab  mov     ebx, r13d
0x1800330ae  sub     ebx, eax
0x1800330b0  jmp     short loc_18003307B
0x1800330b2  lea     rbx, [rcx+4]
0x1800330b6  cmp     rbx, rdx
0x1800330b9  ja      loc_180032F98
0x1800330bf  mov     r9d, 4; SourceSize
0x1800330c5  mov     qword ptr [rbp+47h+var_A8], rcx
0x1800330c9  mov     r8, rcx; Source
0x1800330cc  mov     edx, r9d; DestinationSize
0x1800330cf  lea     rcx, [rbp+47h+var_B4]; Destination
0x1800330d3  call    cs:__imp_memcpy_s
0x1800330da  nop     dword ptr [rax+rax+00h]
0x1800330df  jmp     loc_180032F64
0x1800330e4  mov     r8, r15; unsigned __int8 *
0x1800330e7  lea     rdx, [rbp+47h+var_B8]; struct wil::details_abi::UsageIndexProperty *
0x1800330eb  mov     rcx, rdi; this
0x1800330ee  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800330f3  mov     r14b, [rbp+47h+var_B6]
0x1800330f7  mov     rsi, rax
0x1800330fa  movzx   r12d, [rbp+47h+var_B8]
0x1800330ff  mov     rcx, rax
0x180033102  xor     r9d, r9d
0x180033105  jmp     loc_180032D5B
0x18003310a  lea     rcx, [rbp+47h+var_B8]; this
0x18003310e  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180033113  jmp     loc_180032E21
0x180033118  mov     r12, [rbp+47h+arg_18]
0x18003311c  or      ebx, 0FFFFFFFFh
0x18003311f  mov     r14d, r9d
0x180033122  mov     rsi, r15
0x180033125  cmp     r14d, dword ptr [rbp+47h+var_B4]
0x180033129  jnb     loc_18003307E
0x18003312f  mov     r8, [rdi+20h]; unsigned __int8 *
0x180033133  lea     rdx, [rbp+47h+arg_0]; unsigned __int8 **
0x180033137  lea     rcx, [rbp+47h+var_88]; this
0x18003313b  mov     [rbp+47h+arg_0], rsi
0x18003313f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180033144  test    al, al
0x180033146  jz      short loc_18003316D
0x180033148  mov     r8, r13; unsigned __int64
0x18003314b  lea     rcx, [rbp+47h+var_88]; this
0x18003314f  mov     rdx, r12; void *
0x180033152  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180033157  xor     r9d, r9d
0x18003315a  mov     ebx, eax
0x18003315c  test    eax, eax
  ... truncated ...
```

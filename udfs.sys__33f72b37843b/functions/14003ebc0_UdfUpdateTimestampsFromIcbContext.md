# UdfUpdateTimestampsFromIcbContext

- ea: `0x14003ebc0`
- end: `0x14003f190`
- name: `UdfUpdateTimestampsFromIcbContext`
- size: `1488`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003dec8`
- `0x14003f4c8`

## callees

- `0x1400041e0`
- `0x14001bc30`
- `0x14003ebc0`
- `0x14003f198`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14003f183`
- `ntoskrnl!ExRaiseStatus` at `0x14003f183`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14003eca1`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14003edaa`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14003eeb3`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14003efc1`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14003eca1`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14003edaa`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14003eeb3`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14003efc1`

## pseudocode

```c
char __fastcall UdfUpdateTimestampsFromIcbContext(__int64 a1, __int64 a2, union _LARGE_INTEGER *a3)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int16 *v5; // rdi
  __int16 v7; // cx
  __int16 v8; // cx
  union _LARGE_INTEGER v9; // r8
  __int64 v10; // rdx
  __int16 *v11; // rdi
  __int16 v12; // cx
  __int16 v13; // cx
  union _LARGE_INTEGER v14; // r8
  __int64 v15; // rdx
  __int16 *v16; // rdi
  __int16 v17; // cx
  __int16 v18; // cx
  union _LARGE_INTEGER v19; // r8
  __int64 v20; // rdx
  __int16 v21; // cx
  union _LARGE_INTEGER v22; // rax
  __int16 v23; // cx
  union _LARGE_INTEGER v24; // r8
  __int64 v25; // rdx
  __int16 v26; // cx
  __int16 v27; // cx
  __int16 *v28; // rdx
  __int64 v29; // rax
  __int16 v30; // cx
  int v31; // eax
  __int64 v32; // rbx
  unsigned __int64 v33; // rcx
  __int64 v35; // [rsp+20h] [rbp-50h] BYREF
  __int16 *v36; // [rsp+28h] [rbp-48h]
  int v37; // [rsp+30h] [rbp-40h]
  int v38; // [rsp+34h] [rbp-3Ch]
  __int16 v39; // [rsp+38h] [rbp-38h]
  int v40; // [rsp+3Ah] [rbp-36h]
  __int16 v41; // [rsp+3Eh] [rbp-32h]
  __int64 v42; // [rsp+40h] [rbp-30h]
  __int64 v43; // [rsp+48h] [rbp-28h]
  struct _TIME_FIELDS TimeFields; // [rsp+50h] [rbp-20h] BYREF

  v3 = *(_QWORD *)(a2 + 16);
  v41 = 0;
  *(_DWORD *)&TimeFields.Milliseconds = 0;
  v4 = 72;
  v43 = a1;
  if ( *(_WORD *)v3 != 261 )
    v4 = 80;
  v42 = a2;
  v5 = (__int16 *)(v3 + v4);
  v40 = 0;
  v7 = *v5;
  TimeFields.Year = v5[1];
  TimeFields.Month = *((unsigned __int8 *)v5 + 4);
  TimeFields.Day = *((unsigned __int8 *)v5 + 5);
  TimeFields.Hour = *((unsigned __int8 *)v5 + 6);
  TimeFields.Minute = *((unsigned __int8 *)v5 + 7);
  TimeFields.Second = *((unsigned __int8 *)v5 + 8);
  if ( (v7 & 0xF000u) <= 0x1000
    && ((v8 = (__int16)(16 * v7) >> 4, (unsigned __int16)(v8 + 1440) <= 0xB40u) || v8 == -2047)
    && RtlTimeFieldsToTime(&TimeFields, a3 + 1) )
  {
    v9 = a3[1];
    v10 = 10
        * (*((unsigned __int8 *)v5 + 11) + 100 * (*((unsigned __int8 *)v5 + 10) + 100LL * *((unsigned __int8 *)v5 + 9)));
    a3[1].QuadPart = v10 + v9.QuadPart;
    if ( (*v5 & 0xF000) == 0x1000 && 16 * *v5 != 0x8010 )
      a3[1].QuadPart = v9.QuadPart + v10 + 600000000LL * -((__int16)(16 * *v5) >> 4);
  }
  else
  {
    a3[1].QuadPart = 0;
  }
  v11 = (__int16 *)(v3 + 84);
  if ( *(_WORD *)v3 != 261 )
    v11 = (__int16 *)(v3 + 92);
  v12 = *v11;
  *(_DWORD *)&TimeFields.Milliseconds = 0;
  TimeFields.Year = v11[1];
  TimeFields.Month = *((unsigned __int8 *)v11 + 4);
  TimeFields.Day = *((unsigned __int8 *)v11 + 5);
  TimeFields.Hour = *((unsigned __int8 *)v11 + 6);
  TimeFields.Minute = *((unsigned __int8 *)v11 + 7);
  TimeFields.Second = *((unsigned __int8 *)v11 + 8);
  if ( (v12 & 0xF000u) <= 0x1000
    && ((v13 = (__int16)(16 * v12) >> 4, (unsigned __int16)(v13 + 1440) <= 0xB40u) || v13 == -2047)
    && RtlTimeFieldsToTime(&TimeFields, a3 + 2) )
  {
    v14 = a3[2];
    v15 = 10
        * (*((unsigned __int8 *)v11 + 11)
         + 100 * (*((unsigned __int8 *)v11 + 10) + 100LL * *((unsigned __int8 *)v11 + 9)));
    a3[2].QuadPart = v15 + v14.QuadPart;
    if ( (*v11 & 0xF000) == 0x1000 && 16 * *v11 != 0x8010 )
      a3[2].QuadPart = v14.QuadPart + v15 + 600000000LL * -((__int16)(16 * *v11) >> 4);
  }
  else
  {
    a3[2].QuadPart = 0;
  }
  v16 = (__int16 *)(v3 + 96);
  if ( *(_WORD *)v3 != 261 )
    v16 = (__int16 *)(v3 + 116);
  v17 = *v16;
  *(_DWORD *)&TimeFields.Milliseconds = 0;
  TimeFields.Year = v16[1];
  TimeFields.Month = *((unsigned __int8 *)v16 + 4);
  TimeFields.Day = *((unsigned __int8 *)v16 + 5);
  TimeFields.Hour = *((unsigned __int8 *)v16 + 6);
  TimeFields.Minute = *((unsigned __int8 *)v16 + 7);
  TimeFields.Second = *((unsigned __int8 *)v16 + 8);
  if ( (v17 & 0xF000u) <= 0x1000
    && ((v18 = (__int16)(16 * v17) >> 4, (unsigned __int16)(v18 + 1440) <= 0xB40u) || v18 == -2047)
    && RtlTimeFieldsToTime(&TimeFields, a3 + 3) )
  {
    v19 = a3[3];
    v20 = 10
        * (*((unsigned __int8 *)v16 + 11)
         + 100 * (*((unsigned __int8 *)v16 + 10) + 100LL * *((unsigned __int8 *)v16 + 9)));
    a3[3].QuadPart = v20 + v19.QuadPart;
    if ( (*v16 & 0xF000) == 0x1000 && 16 * *v16 != 0x8010 )
      a3[3].QuadPart = v19.QuadPart + v20 + 600000000LL * -((__int16)(16 * *v16) >> 4);
  }
  else
  {
    a3[3].QuadPart = 0;
  }
  if ( *(_WORD *)v3 == 266 )
  {
    v21 = *(_WORD *)(v3 + 104);
    *(_DWORD *)&TimeFields.Milliseconds = 0;
    TimeFields.Year = *(_WORD *)(v3 + 106);
    TimeFields.Month = *(unsigned __int8 *)(v3 + 108);
    TimeFields.Day = *(unsigned __int8 *)(v3 + 109);
    TimeFields.Hour = *(unsigned __int8 *)(v3 + 110);
    TimeFields.Minute = *(unsigned __int8 *)(v3 + 111);
    TimeFields.Second = *(unsigned __int8 *)(v3 + 112);
    LOBYTE(v22.LowPart) = 0;
    if ( (v21 & 0xF000u) <= 0x1000
      && ((v23 = (__int16)(16 * v21) >> 4, (unsigned __int16)(v23 + 1440) <= 0xB40u)
       || (LOBYTE(v22.LowPart) = 1, v23 == -2047))
      && (LOBYTE(v22.LowPart) = RtlTimeFieldsToTime(&TimeFields, a3)) != 0 )
    {
      v24 = *a3;
      v25 = 10
          * (*(unsigned __int8 *)(v3 + 115)
           + 100 * (*(unsigned __int8 *)(v3 + 114) + 100LL * *(unsigned __int8 *)(v3 + 113)));
      a3->QuadPart += v25;
      v26 = *(_WORD *)(v3 + 104);
      LOBYTE(v22.LowPart) = 0;
      if ( (v26 & 0xF000) == 0x1000 )
      {
        v27 = 16 * v26;
        LOBYTE(v22.LowPart) = v27 & 0xF0;
        if ( (v27 & 0xFFF0) != 0x8010 )
        {
          v22.QuadPart = -(v27 >> 4);
          a3->QuadPart = v24.QuadPart + v25 + 600000000 * v22.QuadPart;
        }
      }
    }
    else
    {
      a3->QuadPart = 0;
    }
  }
  else
  {
    v35 = v42;
    v28 = *(__int16 **)(v42 + 16);
    v29 = 88;
    v30 = *v28;
    if ( *v28 != 261 )
      v29 = 108;
    v36 = &v28[v29];
    if ( v30 == 261 )
      v31 = *((_DWORD *)v28 + 42);
    else
      v31 = *((_DWORD *)v28 + 52);
    v32 = v43;
    v37 = v31;
    v38 = 5;
    v39 = 1;
    LOBYTE(v22.LowPart) = UdfLookupEa(v43, (__int64)&v35);
    if ( LOBYTE(v22.LowPart) )
    {
      if ( (v36[8] & 1) != 0 )
      {
        v33 = (unsigned __int64)v36 + *((unsigned int *)v36 + 2);
        if ( (unsigned __int64)(v36 + 16) > v33 )
        {
          *(_DWORD *)(v32 + 24) = -1073741566;
          ExRaiseStatus(-1073741566);
        }
        LOBYTE(v22.LowPart) = UdfConvertUdfTimeToNtTime(v33, v36 + 10, a3);
      }
    }
    else
    {
      v22 = a3[2];
      *a3 = v22;
    }
  }
  return v22.LowPart;
}

```

## disassembly

```asm
0x14003ebc0  push    rbp
0x14003ebc2  push    rbx
0x14003ebc3  push    rdi
0x14003ebc4  push    r12
0x14003ebc6  push    r13
0x14003ebc8  push    r14
0x14003ebca  push    r15
0x14003ebcc  mov     rbp, rsp
0x14003ebcf  sub     rsp, 70h
0x14003ebd3  mov     rax, cs:__security_cookie
0x14003ebda  xor     rax, rsp
0x14003ebdd  mov     [rbp+var_10], rax
0x14003ebe1  mov     rbx, [rdx+10h]
0x14003ebe5  xor     eax, eax
0x14003ebe7  mov     [rbp+var_32], ax
0x14003ebeb  mov     r13d, 105h
0x14003ebf1  mov     dword ptr [rbp+TimeFields.Milliseconds], eax
0x14003ebf4  mov     edi, 48h ; 'H'
0x14003ebf9  mov     [rbp+var_28], rcx
0x14003ebfd  mov     r9d, 0F000h
0x14003ec03  cmp     [rbx], r13w
0x14003ec07  mov     ecx, 50h ; 'P'
0x14003ec0c  mov     r10d, 1000h
0x14003ec12  mov     [rsp+70h+arg_18], rsi
0x14003ec1a  cmovnz  edi, ecx
0x14003ec1d  mov     [rbp+var_30], rdx
0x14003ec21  add     rdi, rbx
0x14003ec24  mov     [rbp+var_36], 0
0x14003ec2b  mov     r12, r8
0x14003ec2e  mov     r14d, 5A0h
0x14003ec34  mov     r15d, 0B40h
0x14003ec3a  movzx   eax, word ptr [rdi+2]
0x14003ec3e  movzx   ecx, word ptr [rdi]
0x14003ec41  mov     [rbp+TimeFields.Year], ax
0x14003ec45  movzx   eax, byte ptr [rdi+4]
0x14003ec49  mov     [rbp+TimeFields.Month], ax
0x14003ec4d  movzx   eax, byte ptr [rdi+5]
0x14003ec51  mov     [rbp+TimeFields.Day], ax
0x14003ec55  movzx   eax, byte ptr [rdi+6]
0x14003ec59  mov     [rbp+TimeFields.Hour], ax
0x14003ec5d  movzx   eax, byte ptr [rdi+7]
0x14003ec61  mov     [rbp+TimeFields.Minute], ax
0x14003ec65  movzx   eax, byte ptr [rdi+8]
0x14003ec69  mov     [rbp+TimeFields.Second], ax
0x14003ec6d  movzx   eax, cx
0x14003ec70  and     ax, r9w
0x14003ec74  cmp     ax, r10w
0x14003ec78  ja      loc_14003F071
0x14003ec7e  shl     cx, 4
0x14003ec82  mov     edx, 0FFFFF801h
0x14003ec87  sar     cx, 4
0x14003ec8b  lea     eax, [r14+rcx]
0x14003ec8f  cmp     ax, r15w
0x14003ec93  ja      loc_14003F068
0x14003ec99  lea     rdx, [r8+8]; Time
0x14003ec9d  lea     rcx, [rbp+TimeFields]; TimeFields
0x14003eca1  call    cs:__imp_RtlTimeFieldsToTime
0x14003eca8  nop     dword ptr [rax+rax+00h]
0x14003ecad  mov     r9d, 0F000h
0x14003ecb3  mov     r10d, 1000h
0x14003ecb9  test    al, al
0x14003ecbb  jz      loc_14003F071
0x14003ecc1  movzx   eax, byte ptr [rdi+9]
0x14003ecc5  mov     r8, [r12+8]
0x14003ecca  imul    rcx, rax, 64h ; 'd'
0x14003ecce  movzx   eax, byte ptr [rdi+0Ah]
0x14003ecd2  add     rcx, rax
0x14003ecd5  movzx   eax, byte ptr [rdi+0Bh]
0x14003ecd9  imul    rdx, rcx, 64h ; 'd'
0x14003ecdd  add     rdx, rax
0x14003ece0  lea     rax, [rdx+rdx*4]
0x14003ece4  lea     rdx, [rax+rax]
0x14003ece8  lea     rax, [rdx+r8]
0x14003ecec  mov     [r12+8], rax
0x14003ecf1  movzx   ecx, word ptr [rdi]
0x14003ecf4  movzx   eax, cx
0x14003ecf7  and     ax, r9w
0x14003ecfb  cmp     ax, r10w
0x14003ecff  jnz     short loc_14003ED34
0x14003ed01  shl     cx, 4
0x14003ed05  mov     r11d, 0FFFF8010h
0x14003ed0b  movzx   eax, cx
0x14003ed0e  and     ax, 0FFF0h
0x14003ed12  cmp     ax, r11w
0x14003ed16  jz      short loc_14003ED34
0x14003ed18  movsx   eax, cx
0x14003ed1b  sar     eax, 4
0x14003ed1e  neg     eax
0x14003ed20  cdqe
0x14003ed22  imul    rcx, rax, 23C34600h
0x14003ed29  add     rcx, rdx
0x14003ed2c  add     rcx, r8
0x14003ed2f  mov     [r12+8], rcx
0x14003ed34  lea     rdi, [rbx+54h]
0x14003ed38  cmp     [rbx], r13w
0x14003ed3c  jz      short loc_14003ED42
0x14003ed3e  lea     rdi, [rbx+5Ch]
0x14003ed42  movzx   ecx, word ptr [rdi]
0x14003ed45  xor     eax, eax
0x14003ed47  mov     dword ptr [rbp+TimeFields.Milliseconds], eax
0x14003ed4a  movzx   eax, word ptr [rdi+2]
0x14003ed4e  mov     [rbp+TimeFields.Year], ax
0x14003ed52  movzx   eax, byte ptr [rdi+4]
0x14003ed56  mov     [rbp+TimeFields.Month], ax
0x14003ed5a  movzx   eax, byte ptr [rdi+5]
0x14003ed5e  mov     [rbp+TimeFields.Day], ax
0x14003ed62  movzx   eax, byte ptr [rdi+6]
0x14003ed66  mov     [rbp+TimeFields.Hour], ax
0x14003ed6a  movzx   eax, byte ptr [rdi+7]
0x14003ed6e  mov     [rbp+TimeFields.Minute], ax
0x14003ed72  movzx   eax, byte ptr [rdi+8]
0x14003ed76  mov     [rbp+TimeFields.Second], ax
0x14003ed7a  movzx   eax, cx
0x14003ed7d  and     ax, r9w
0x14003ed81  cmp     ax, r10w
0x14003ed85  ja      loc_14003F08D
0x14003ed8b  shl     cx, 4
0x14003ed8f  sar     cx, 4
0x14003ed93  lea     eax, [r14+rcx]
0x14003ed97  cmp     ax, r15w
0x14003ed9b  ja      loc_14003F07F
0x14003eda1  lea     rdx, [r12+10h]; Time
0x14003eda6  lea     rcx, [rbp+TimeFields]; TimeFields
0x14003edaa  call    cs:__imp_RtlTimeFieldsToTime
0x14003edb1  nop     dword ptr [rax+rax+00h]
0x14003edb6  mov     r9d, 0F000h
0x14003edbc  mov     r10d, 1000h
0x14003edc2  test    al, al
0x14003edc4  jz      loc_14003F08D
0x14003edca  movzx   eax, byte ptr [rdi+9]
0x14003edce  mov     r8, [r12+10h]
0x14003edd3  imul    rcx, rax, 64h ; 'd'
0x14003edd7  movzx   eax, byte ptr [rdi+0Ah]
0x14003eddb  add     rcx, rax
0x14003edde  movzx   eax, byte ptr [rdi+0Bh]
0x14003ede2  imul    rdx, rcx, 64h ; 'd'
0x14003ede6  add     rdx, rax
0x14003ede9  lea     rax, [rdx+rdx*4]
0x14003eded  lea     rdx, [rax+rax]
0x14003edf1  lea     rax, [rdx+r8]
0x14003edf5  mov     [r12+10h], rax
0x14003edfa  movzx   ecx, word ptr [rdi]
0x14003edfd  movzx   eax, cx
0x14003ee00  and     ax, r9w
0x14003ee04  cmp     ax, r10w
0x14003ee08  jnz     short loc_14003EE3D
0x14003ee0a  shl     cx, 4
0x14003ee0e  mov     r11d, 0FFFF8010h
0x14003ee14  movzx   eax, cx
0x14003ee17  and     ax, 0FFF0h
0x14003ee1b  cmp     ax, r11w
0x14003ee1f  jz      short loc_14003EE3D
0x14003ee21  movsx   eax, cx
0x14003ee24  sar     eax, 4
0x14003ee27  neg     eax
0x14003ee29  cdqe
0x14003ee2b  imul    rcx, rax, 23C34600h
0x14003ee32  add     rcx, rdx
0x14003ee35  add     rcx, r8
0x14003ee38  mov     [r12+10h], rcx
0x14003ee3d  lea     rdi, [rbx+60h]
0x14003ee41  cmp     [rbx], r13w
0x14003ee45  jz      short loc_14003EE4B
0x14003ee47  lea     rdi, [rbx+74h]
0x14003ee4b  movzx   ecx, word ptr [rdi]
0x14003ee4e  xor     eax, eax
0x14003ee50  mov     dword ptr [rbp+TimeFields.Milliseconds], eax
0x14003ee53  movzx   eax, word ptr [rdi+2]
0x14003ee57  mov     [rbp+TimeFields.Year], ax
0x14003ee5b  movzx   eax, byte ptr [rdi+4]
0x14003ee5f  mov     [rbp+TimeFields.Month], ax
0x14003ee63  movzx   eax, byte ptr [rdi+5]
0x14003ee67  mov     [rbp+TimeFields.Day], ax
0x14003ee6b  movzx   eax, byte ptr [rdi+6]
0x14003ee6f  mov     [rbp+TimeFields.Hour], ax
0x14003ee73  movzx   eax, byte ptr [rdi+7]
0x14003ee77  mov     [rbp+TimeFields.Minute], ax
0x14003ee7b  movzx   eax, byte ptr [rdi+8]
0x14003ee7f  mov     [rbp+TimeFields.Second], ax
0x14003ee83  movzx   eax, cx
0x14003ee86  and     ax, r9w
0x14003ee8a  cmp     ax, r10w
0x14003ee8e  ja      loc_14003F0A9
0x14003ee94  shl     cx, 4
0x14003ee98  sar     cx, 4
0x14003ee9c  lea     eax, [r14+rcx]
0x14003eea0  cmp     ax, r15w
0x14003eea4  ja      loc_14003F09B
0x14003eeaa  lea     rdx, [r12+18h]; Time
0x14003eeaf  lea     rcx, [rbp+TimeFields]; TimeFields
0x14003eeb3  call    cs:__imp_RtlTimeFieldsToTime
0x14003eeba  nop     dword ptr [rax+rax+00h]
0x14003eebf  mov     r9d, 0F000h
0x14003eec5  mov     r10d, 1000h
0x14003eecb  test    al, al
0x14003eecd  jz      loc_14003F0A9
0x14003eed3  movzx   eax, byte ptr [rdi+9]
0x14003eed7  mov     r8, [r12+18h]
0x14003eedc  imul    rcx, rax, 64h ; 'd'
0x14003eee0  movzx   eax, byte ptr [rdi+0Ah]
0x14003eee4  add     rcx, rax
0x14003eee7  movzx   eax, byte ptr [rdi+0Bh]
0x14003eeeb  imul    rdx, rcx, 64h ; 'd'
0x14003eeef  add     rdx, rax
0x14003eef2  lea     rax, [rdx+rdx*4]
0x14003eef6  lea     rdx, [rax+rax]
0x14003eefa  lea     rax, [rdx+r8]
0x14003eefe  mov     [r12+18h], rax
0x14003ef03  movzx   ecx, word ptr [rdi]
0x14003ef06  mov     edi, 0FFFF8010h
0x14003ef0b  movzx   eax, cx
0x14003ef0e  and     ax, r9w
0x14003ef12  cmp     ax, r10w
0x14003ef16  jnz     short loc_14003EF44
0x14003ef18  shl     cx, 4
0x14003ef1c  movzx   eax, cx
0x14003ef1f  and     ax, 0FFF0h
0x14003ef23  cmp     ax, di
0x14003ef26  jz      short loc_14003EF44
0x14003ef28  movsx   eax, cx
0x14003ef2b  sar     eax, 4
0x14003ef2e  neg     eax
0x14003ef30  cdqe
0x14003ef32  imul    rcx, rax, 23C34600h
0x14003ef39  add     rcx, rdx
0x14003ef3c  add     rcx, r8
0x14003ef3f  mov     [r12+18h], rcx
0x14003ef44  mov     rsi, [rsp+70h+arg_18]
0x14003ef4c  mov     eax, 10Ah
0x14003ef51  cmp     [rbx], ax
0x14003ef54  jnz     loc_14003F0D7
0x14003ef5a  movzx   ecx, word ptr [rbx+68h]
0x14003ef5e  xor     eax, eax
0x14003ef60  mov     dword ptr [rbp+TimeFields.Milliseconds], eax
0x14003ef63  movzx   eax, word ptr [rbx+6Ah]
0x14003ef67  mov     [rbp+TimeFields.Year], ax
0x14003ef6b  movzx   eax, byte ptr [rbx+6Ch]
0x14003ef6f  mov     [rbp+TimeFields.Month], ax
0x14003ef73  movzx   eax, byte ptr [rbx+6Dh]
0x14003ef77  mov     [rbp+TimeFields.Day], ax
0x14003ef7b  movzx   eax, byte ptr [rbx+6Eh]
0x14003ef7f  mov     [rbp+TimeFields.Hour], ax
0x14003ef83  movzx   eax, byte ptr [rbx+6Fh]
0x14003ef87  mov     [rbp+TimeFields.Minute], ax
0x14003ef8b  movzx   eax, byte ptr [rbx+70h]
0x14003ef8f  mov     [rbp+TimeFields.Second], ax
0x14003ef93  movzx   eax, cx
0x14003ef96  and     ax, r9w
0x14003ef9a  cmp     ax, r10w
0x14003ef9e  ja      loc_14003F0CA
0x14003efa4  shl     cx, 4
0x14003efa8  sar     cx, 4
0x14003efac  lea     eax, [r14+rcx]
0x14003efb0  cmp     ax, r15w
0x14003efb4  ja      loc_14003F0BC
0x14003efba  mov     rdx, r12; Time
0x14003efbd  lea     rcx, [rbp+TimeFields]; TimeFields
0x14003efc1  call    cs:__imp_RtlTimeFieldsToTime
0x14003efc8  nop     dword ptr [rax+rax+00h]
0x14003efcd  test    al, al
0x14003efcf  jz      loc_14003F0CA
0x14003efd5  movzx   eax, byte ptr [rbx+71h]
0x14003efd9  mov     r9d, 0F000h
0x14003efdf  mov     r8, [r12]
0x14003efe3  imul    rcx, rax, 64h ; 'd'
0x14003efe7  movzx   eax, byte ptr [rbx+72h]
0x14003efeb  add     rcx, rax
0x14003efee  movzx   eax, byte ptr [rbx+73h]
0x14003eff2  imul    rdx, rcx, 64h ; 'd'
0x14003eff6  add     rdx, rax
0x14003eff9  lea     rax, [rdx+rdx*4]
0x14003effd  lea     rdx, [rax+rax]
0x14003f001  lea     rax, [rdx+r8]
0x14003f005  mov     [r12], rax
0x14003f009  movzx   ecx, word ptr [rbx+68h]
0x14003f00d  movzx   eax, cx
0x14003f010  and     ax, r9w
0x14003f014  mov     r9d, 1000h
0x14003f01a  cmp     ax, r9w
0x14003f01e  jnz     short loc_14003F04B
0x14003f020  shl     cx, 4
0x14003f024  movzx   eax, cx
0x14003f027  and     ax, 0FFF0h
0x14003f02b  cmp     ax, di
0x14003f02e  jz      short loc_14003F04B
0x14003f030  movsx   eax, cx
0x14003f033  sar     eax, 4
0x14003f036  neg     eax
0x14003f038  cdqe
0x14003f03a  imul    rcx, rax, 23C34600h
0x14003f041  add     rcx, rdx
0x14003f044  add     rcx, r8
0x14003f047  mov     [r12], rcx
0x14003f04b  mov     rcx, [rbp+var_10]
0x14003f04f  xor     rcx, rsp; StackCookie
0x14003f052  call    __security_check_cookie
0x14003f057  add     rsp, 70h
0x14003f05b  pop     r15
0x14003f05d  pop     r14
0x14003f05f  pop     r13
  ... truncated ...
```

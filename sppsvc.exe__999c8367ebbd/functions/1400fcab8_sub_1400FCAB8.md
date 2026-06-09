# sub_1400FCAB8

- ea: `0x1400fcab8`
- end: `0x1400fd265`
- name: `sub_1400FCAB8`
- size: `1965`
- prototype: ``
- caller_count: `2`
- callee_count: `37`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140089194`
- `0x1400ca8f0`

## callees

- `0x140056160`
- `0x1400564b0`
- `0x1400567f0`
- `0x140056b40`
- `0x140056e80`
- `0x1400571c0`
- `0x140057510`
- `0x140057850`
- `0x140057bf0`
- `0x140057fc0`
- `0x140059870`
- `0x14006ad34`
- `0x14006adb4`
- `0x14006c298`
- `0x14006de60`
- `0x14007b174`
- `0x14007cfb4`
- `0x1400a0fd4`
- `0x1400f6f88`
- `0x1400f70a4`
- `0x1400f70c8`
- `0x1400f738c`
- `0x1400f7484`
- `0x1400f7a9c`
- `0x1400f855c`
- `0x1400f86e4`
- `0x1400fcab8`
- `0x1400fe824`
- `0x1400feacc`
- `0x140100260`
- `0x140101258`
- `0x1401013f0`
- `0x14010147c`
- `0x140101594`
- `0x140101c84`
- `0x140101d68`
- `0x140101f88`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x1400fd001`
- `KERNEL32!CompareFileTime` at `0x1400fd001`

## string_xrefs

- `0x1400fcc96`: `msft:spp/stockobjects/plugins/params/named`
- `0x1400fcd22`: `msft:spp/stockobjects/plugins/params/named`

## pseudocode

```c
__int64 __fastcall sub_1400FCAB8(__int64 a1, __int64 a2, __int64 a3, __int64 *a4, _QWORD *a5)
{
  void *v7; // r14
  int v10; // ecx
  int v11; // edi
  int v12; // eax
  __int64 v13; // rdi
  void *v14; // r12
  __int64 (__fastcall *v15)(__int64, void *, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, _QWORD, __int128 *); // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, const wchar_t *, __int64 *, _QWORD, __int64 *); // rbx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int128 *, _QWORD); // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, const wchar_t *, __int64 *, _QWORD, __int64 *); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int128 *, __int64); // rbx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int128 *, __int64); // rbx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, __int64, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  int v31; // eax
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v33)(_QWORD, __int64 *, __int64 *); // rbx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int128 *, FILETIME *); // rbx
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, unsigned int *); // rbx
  unsigned int v38; // r14d
  const FILETIME **v39; // rbx
  __int64 v40; // rsi
  __int64 (__fastcall *v41)(__int64, _QWORD, __int128 *); // rdi
  __int64 *v42; // r14
  int v43; // esi
  __int64 v44; // r12
  __int64 v45; // r13
  int v46; // ebx
  int v47; // r13d
  unsigned int v48; // ebx
  _QWORD *v49; // rcx
  __int64 v50; // rax
  __int64 v52; // [rsp+30h] [rbp-91h] BYREF
  __int64 v53; // [rsp+38h] [rbp-89h] BYREF
  int v54; // [rsp+40h] [rbp-81h] BYREF
  __int64 v55; // [rsp+48h] [rbp-79h] BYREF
  __int64 v56; // [rsp+50h] [rbp-71h] BYREF
  __int64 v57; // [rsp+58h] [rbp-69h] BYREF
  __int64 v58; // [rsp+60h] [rbp-61h] BYREF
  __int128 v59; // [rsp+68h] [rbp-59h] BYREF
  __int128 v60; // [rsp+78h] [rbp-49h]
  __int64 v61; // [rsp+88h] [rbp-39h] BYREF
  __int64 v62; // [rsp+90h] [rbp-31h]
  __int64 v63; // [rsp+98h] [rbp-29h] BYREF
  __int64 *v64; // [rsp+A0h] [rbp-21h]
  __int64 (__fastcall ***v65)(_QWORD, __int64 *, __int64 *); // [rsp+A8h] [rbp-19h] BYREF
  const FILETIME **v66; // [rsp+B0h] [rbp-11h] BYREF
  void *v67; // [rsp+B8h] [rbp-9h] BYREF
  void *v68; // [rsp+C0h] [rbp-1h] BYREF
  FILETIME FileTime2; // [rsp+C8h] [rbp+7h] BYREF
  __int128 v70; // [rsp+D0h] [rbp+Fh] BYREF
  unsigned int v71; // [rsp+128h] [rbp+67h] BYREF
  __int64 *v72; // [rsp+138h] [rbp+77h]

  v72 = a4;
  v68 = 0;
  v67 = 0;
  v7 = 0;
  sub_140056160(&dword_1404213EC, &dword_1404424E4);
  v58 = 0;
  v57 = 0;
  v53 = 0;
  v71 = 0;
  v63 = 0;
  v64 = 0;
  v66 = 0;
  FileTime2 = 0;
  v52 = 0;
  v61 = 0;
  v62 = 0;
  v56 = 0;
  v54 = 0;
  v55 = 0;
  v65 = 0;
  v70 = 0;
  v59 = 0;
  v60 = 0;
  if ( !a2 )
  {
    sub_1400564B0(dword_140422914, dword_14043C244);
LABEL_3:
    v10 = -2147024809;
    v11 = -2147024809;
LABEL_4:
    sub_14006DE60(v10);
    goto LABEL_65;
  }
  if ( !a4 || !a3 && a5 )
    goto LABEL_3;
  v12 = sub_1400A0FD4(&qword_1403C4AB0, 0, &v56);
  v11 = v12;
  if ( v12 < 0 )
    goto LABEL_9;
  v12 = sub_14007B174(a2, &v67);
  v11 = v12;
  if ( v12 < 0 )
    goto LABEL_9;
  v13 = qword_1404462A0;
  v14 = v67;
  v15 = *(__int64 (__fastcall **)(__int64, void *, __int64 *))(*(_QWORD *)qword_1404462A0 + 344LL);
  _guard_check_icall_fptr();
  v16 = v15(v13, v14, &v58);
  v11 = v16;
  if ( v16 == -1073418222 )
  {
    v11 = -1073418219;
LABEL_14:
    sub_14006DE60(v11);
    sub_1400567F0(dword_1404234A8, dword_14043D200);
    goto LABEL_65;
  }
  if ( v16 < 0 )
    goto LABEL_14;
  v17 = v58;
  v18 = *(int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v58 + 32LL);
  _guard_check_icall_fptr();
  if ( v18(v17, 0, &v59) >= 0 )
  {
    v12 = sub_14006C298(v59, &v68, 0x7FFFFFFF);
    v11 = v12;
    if ( v12 < 0 )
      goto LABEL_9;
    v7 = v68;
  }
  v19 = qword_140446270;
  v20 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, __int64 *))(*(_QWORD *)qword_140446270
                                                                                         + 24LL);
  _guard_check_icall_fptr();
  v12 = v20(v19, L"msft:spp/stockobjects/plugins/params/named", &qword_1403C4AB0, 0, &v57);
  v11 = v12;
  if ( v12 < 0 )
    goto LABEL_9;
  v21 = v57;
  *(_QWORD *)&v59 = v14;
  DWORD2(v59) = 2;
  *(_QWORD *)&v60 = v14;
  v22 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v57 + 72LL);
  _guard_check_icall_fptr();
  v12 = v22(v21, &v59, 0);
  v11 = v12;
  if ( v12 < 0 )
    goto LABEL_9;
  sub_140056E80(dword_140421DD8, &dword_1404456E0);
  v23 = qword_140446270;
  v24 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, __int64 *))(*(_QWORD *)qword_140446270
                                                                                         + 24LL);
  _guard_check_icall_fptr();
  if ( a3 )
  {
    v11 = v24(v23, L"msft:spp/stockobjects/plugins/params/named", &qword_1403C4AB0, 0, &v53);
    sub_140057510(&dword_140418B40, dword_14043B95C);
    if ( v11 < 0 )
    {
LABEL_22:
      v10 = v11;
      goto LABEL_4;
    }
    v25 = v53;
    *(_QWORD *)&v59 = a3;
    DWORD2(v59) = 2;
    *(_QWORD *)&v60 = a3;
    v26 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v53 + 72LL);
    _guard_check_icall_fptr();
    v12 = v26(v25, &v59, 1);
    v11 = v12;
    if ( v12 < 0 )
      goto LABEL_9;
  }
  else
  {
    v11 = v24(v23, L"msft:spp/stockobjects/plugins/params/named", &qword_1403C4AB0, 0, &v55);
    sub_140057850(dword_1404119C8, dword_14043F6CC);
    if ( v11 < 0 )
    {
      sub_140057FC0(&dword_140425564, &dword_14043F5A8);
      goto LABEL_22;
    }
    v27 = v55;
    *(_QWORD *)&v59 = L"licenseType";
    *(_QWORD *)&v60 = L"msft:sl/STIL";
    DWORD2(v59) = 2;
    v28 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v55 + 72LL);
    _guard_check_icall_fptr();
    v12 = v28(v27, &v59, 1);
    v11 = v12;
    if ( v12 < 0 )
    {
LABEL_9:
      v10 = v12;
      goto LABEL_4;
    }
    v29 = qword_1404462A0;
    v30 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)qword_1404462A0 + 160LL);
    _guard_check_icall_fptr();
    v31 = v30(v29, 1, v55, (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v65);
    v11 = v31;
    if ( v31 == -1073418222 )
    {
      v11 = -1073418223;
      goto LABEL_22;
    }
    if ( v31 < 0 )
      goto LABEL_22;
    v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v65;
    v33 = **v65;
    _guard_check_icall_fptr();
    v11 = v33(v32, &qword_1403C4AB0, &v53);
    sub_1400567F0(&dword_140423BF8, dword_14043D978);
    if ( v11 < 0 )
      goto LABEL_22;
  }
  v34 = qword_140446258;
  *(_QWORD *)&v70 = v7;
  *((_QWORD *)&v70 + 1) = v14;
  v35 = *(__int64 (__fastcall **)(__int64, __int128 *, FILETIME *))(*(_QWORD *)qword_140446258 + 48LL);
  _guard_check_icall_fptr();
  v11 = v35(v34, &v70, &FileTime2);
  sub_1400571C0(dword_140415458, dword_140442F74);
  if ( (int)(v11 + 0x80000000) >= 0 )
  {
    sub_1400571C0(&dword_1404288B8, &dword_140443048);
    if ( v11 != -2147167998 )
      goto LABEL_22;
  }
  v12 = sub_1400F86E4(qword_1404462A0, *(_QWORD *)(a1 + 216), &v66);
  v11 = v12;
  if ( v12 < 0 )
    goto LABEL_9;
  v36 = v53;
  v37 = *(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v53 + 24LL);
  _guard_check_icall_fptr();
  v12 = v37(v36, &v71);
  v11 = v12;
  if ( v12 < 0 )
    goto LABEL_9;
  v38 = 0;
  if ( v71 )
  {
    v39 = v66;
    do
    {
      v40 = v53;
      v41 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v53 + 32LL);
      _guard_check_icall_fptr();
      v12 = v41(v40, v38, &v59);
      v11 = v12;
      if ( v12 < 0 )
        goto LABEL_9;
      v12 = sub_140101594(v39, v59);
      v11 = v12;
      if ( v12 < 0 )
        goto LABEL_9;
      if ( (int)sub_1400F7A9C(v39, v59) >= 0 )
      {
        if ( CompareFileTime(*v39 + 8, &FileTime2) < 0 )
          sub_140101D68(*(_QWORD *)&(*v39)[7], 0);
        v12 = sub_1400FEACC(&v63, v39);
        v11 = v12;
        if ( v12 < 0 )
          goto LABEL_9;
      }
    }
    while ( ++v38 < v71 );
  }
  v11 = sub_140101258(&v63);
  if ( v11 < 0 )
  {
    sub_140056B40(&dword_14042B038, &dword_140444ED0);
    goto LABEL_22;
  }
  v42 = v64;
  v43 = 0;
  v44 = v56;
  if ( SHIDWORD(v63) > 0 )
  {
    while ( 1 )
    {
      v45 = *(_QWORD *)(v42[v43] + 56);
      sub_1401013F0(&v52);
      sub_140101F88(&v61, 0);
      v46 = 0;
      if ( *(int *)(v45 + 4) > 0 )
        break;
LABEL_54:
      v47 = HIDWORD(v61);
      v48 = 0;
      if ( SHIDWORD(v61) > 0 )
      {
        do
        {
          sub_1400F738C(&v52, v62 + 8LL * (int)v48);
          v12 = sub_140100260(v52, v58, v57, &v54);
          v11 = v12;
          if ( v12 < 0 )
            goto LABEL_9;
          if ( v54 )
          {
            v12 = sub_1400F7484(v44, v48, v42[v43], v52);
            v11 = v12;
            if ( v12 < 0 )
              goto LABEL_9;
          }
        }
        while ( (int)++v48 < v47 );
      }
LABEL_59:
      if ( ++v43 >= SHIDWORD(v63) )
        goto LABEL_60;
    }
    while ( 1 )
    {
      v12 = sub_1400F6F88(&v52);
      v11 = v12;
      if ( v12 < 0 )
        goto LABEL_9;
      v12 = sub_140101C84(
              v52,
              *(_QWORD *)(*(_QWORD *)(v45 + 8) + 16LL * v46),
              *(unsigned int *)(*(_QWORD *)(v45 + 8) + 16LL * v46 + 8));
      if ( v12 == -1073417465 )
        goto LABEL_59;
      v11 = v12;
      if ( v12 < 0 )
        goto LABEL_9;
      v12 = sub_1400FE824(&v61, HIDWORD(v61), &v52);
      v11 = v12;
      if ( v12 < 0 )
        goto LABEL_9;
      if ( ++v46 >= *(_DWORD *)(v45 + 4) )
        goto LABEL_54;
    }
  }
LABEL_60:
  if ( !(unsigned int)sub_1400F855C(v44) )
  {
    v11 = -1073417468;
    goto LABEL_22;
  }
  v49 = a5;
  if ( a5 )
  {
    v50 = *v42;
    *v42 = 0;
    *v49 = v50;
  }
  v56 = 0;
  *v72 = v44;
  sub_140057BF0(dword_14041C7A4, dword_1404405F8);
LABEL_65:
  sub_14007CFB4(v11);
  sub_14006AD34((__int64 *)&v65);
  sub_14006AD34(&v55);
  sub_14006AD34(&v56);
  sub_1400F70A4(&v61);
  sub_1401013F0(&v52);
  sub_14010147C(&v66);
  sub_1400F70C8(&v63);
  sub_14006AD34(&v53);
  sub_14006AD34(&v57);
  sub_14006AD34(&v58);
  sub_14006ADB4(&v67);
  sub_14006ADB4(&v68);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400fcab8  mov     [rsp-8+arg_0], rbx
0x1400fcabd  mov     [rsp-8+arg_18], r9
0x1400fcac2  push    rbp
0x1400fcac3  push    rsi
0x1400fcac4  push    rdi
0x1400fcac5  push    r12
0x1400fcac7  push    r13
0x1400fcac9  push    r14
0x1400fcacb  push    r15
0x1400fcacd  lea     rbp, [rsp-1Fh]
0x1400fcad2  sub     rsp, 0E0h
0x1400fcad9  xor     r15d, r15d
0x1400fcadc  mov     rbx, rdx
0x1400fcadf  mov     r13, rcx
0x1400fcae2  mov     [rbp+4Fh+var_50], r15
0x1400fcae6  lea     rdx, dword_1404424E4
0x1400fcaed  mov     [rbp+4Fh+var_58], r15
0x1400fcaf1  lea     rcx, dword_1404213EC
0x1400fcaf8  mov     r14d, r15d
0x1400fcafb  mov     rdi, r9
0x1400fcafe  mov     rsi, r8
0x1400fcb01  call    sub_140056160
0x1400fcb06  mov     [rbp+4Fh+var_B0], r15
0x1400fcb0a  xorps   xmm0, xmm0
0x1400fcb0d  mov     [rbp+4Fh+var_B8], r15
0x1400fcb11  mov     [rsp+110h+var_D8], r15
0x1400fcb16  mov     [rbp+4Fh+arg_8], r15d
0x1400fcb1a  mov     [rbp+4Fh+var_78], r15
0x1400fcb1e  mov     [rbp+4Fh+var_70], r15
0x1400fcb22  mov     [rbp+4Fh+var_60], r15
0x1400fcb26  mov     qword ptr [rbp+4Fh+FileTime2.dwLowDateTime], r15
0x1400fcb2a  mov     [rsp+110h+var_E0], r15
0x1400fcb2f  mov     [rbp+4Fh+var_88], r15
0x1400fcb33  mov     [rbp+4Fh+var_80], r15
0x1400fcb37  mov     [rbp+4Fh+var_C0], r15
0x1400fcb3b  mov     [rsp+110h+var_D0], r15d
0x1400fcb40  mov     [rbp+4Fh+var_C8], r15
0x1400fcb44  mov     [rbp+4Fh+var_68], r15
0x1400fcb48  movups  [rbp+4Fh+var_40], xmm0
0x1400fcb4c  movups  [rbp+4Fh+var_A8], xmm0
0x1400fcb50  movups  [rbp+4Fh+var_98], xmm0
0x1400fcb54  test    rbx, rbx
0x1400fcb57  jnz     short loc_1400FCB7D
0x1400fcb59  lea     rdx, dword_14043C244
0x1400fcb60  lea     rcx, dword_140422914
0x1400fcb67  call    sub_1400564B0
0x1400fcb6c  mov     ecx, 80070057h
0x1400fcb71  mov     edi, ecx
0x1400fcb73  call    sub_14006DE60
0x1400fcb78  jmp     loc_1400FD1D2
0x1400fcb7d  test    rdi, rdi
0x1400fcb80  jz      short loc_1400FCB6C
0x1400fcb82  test    rsi, rsi
0x1400fcb85  jnz     short loc_1400FCB8D
0x1400fcb87  cmp     [rbp+4Fh+arg_20], r15
0x1400fcb8b  jnz     short loc_1400FCB6C
0x1400fcb8d  lea     r8, [rbp+4Fh+var_C0]
0x1400fcb91  xor     edx, edx
0x1400fcb93  lea     rcx, qword_1403C4AB0
0x1400fcb9a  call    sub_1400A0FD4
0x1400fcb9f  mov     edi, eax
0x1400fcba1  test    eax, eax
0x1400fcba3  jns     short loc_1400FCBA9
0x1400fcba5  mov     ecx, eax
0x1400fcba7  jmp     short loc_1400FCB73
0x1400fcba9  lea     rdx, [rbp+4Fh+var_58]
0x1400fcbad  mov     rcx, rbx
0x1400fcbb0  call    sub_14007B174
0x1400fcbb5  mov     edi, eax
0x1400fcbb7  test    eax, eax
0x1400fcbb9  js      short loc_1400FCBA5
0x1400fcbbb  mov     rdi, cs:qword_1404462A0
0x1400fcbc2  mov     r12, [rbp+4Fh+var_58]
0x1400fcbc6  mov     rax, [rdi]
0x1400fcbc9  mov     rbx, [rax+158h]
0x1400fcbd0  mov     rax, cs:__guard_check_icall_fptr
0x1400fcbd7  mov     rcx, rbx
0x1400fcbda  call    rax ; _guard_check_icall_nop
0x1400fcbdc  mov     rax, rbx
0x1400fcbdf  lea     r8, [rbp+4Fh+var_B0]
0x1400fcbe3  mov     rdx, r12
0x1400fcbe6  mov     rcx, rdi
0x1400fcbe9  call    rax
0x1400fcbeb  mov     edi, eax
0x1400fcbed  cmp     eax, 0C004F012h
0x1400fcbf2  jnz     short loc_1400FCBF9
0x1400fcbf4  lea     edi, [rax+3]
0x1400fcbf7  jmp     short loc_1400FCBFD
0x1400fcbf9  test    eax, eax
0x1400fcbfb  jns     short loc_1400FCC1C
0x1400fcbfd  mov     ecx, edi
0x1400fcbff  call    sub_14006DE60
0x1400fcc04  lea     rdx, dword_14043D200
0x1400fcc0b  lea     rcx, dword_1404234A8
0x1400fcc12  call    sub_1400567F0
0x1400fcc17  jmp     loc_1400FD1D2
0x1400fcc1c  mov     rdi, [rbp+4Fh+var_B0]
0x1400fcc20  mov     rax, [rdi]
0x1400fcc23  mov     rbx, [rax+20h]
0x1400fcc27  mov     rax, cs:__guard_check_icall_fptr
0x1400fcc2e  mov     rcx, rbx
0x1400fcc31  call    rax ; _guard_check_icall_nop
0x1400fcc33  mov     rax, rbx
0x1400fcc36  lea     r8, [rbp+4Fh+var_A8]
0x1400fcc3a  xor     edx, edx
0x1400fcc3c  mov     rcx, rdi
0x1400fcc3f  call    rax
0x1400fcc41  test    eax, eax
0x1400fcc43  js      short loc_1400FCC66
0x1400fcc45  mov     rcx, qword ptr [rbp+4Fh+var_A8]
0x1400fcc49  lea     rdx, [rbp+4Fh+var_50]
0x1400fcc4d  mov     r8d, 7FFFFFFFh
0x1400fcc53  call    sub_14006C298
0x1400fcc58  mov     edi, eax
0x1400fcc5a  test    eax, eax
0x1400fcc5c  js      loc_1400FCBA5
0x1400fcc62  mov     r14, [rbp+4Fh+var_50]
0x1400fcc66  mov     rdi, cs:qword_140446270
0x1400fcc6d  mov     rax, [rdi]
0x1400fcc70  mov     rbx, [rax+18h]
0x1400fcc74  mov     rax, cs:__guard_check_icall_fptr
0x1400fcc7b  mov     rcx, rbx
0x1400fcc7e  call    rax ; _guard_check_icall_nop
0x1400fcc80  lea     rcx, [rbp+4Fh+var_B8]
0x1400fcc84  mov     rax, rbx
0x1400fcc87  mov     [rsp+110h+var_F0], rcx
0x1400fcc8c  lea     r8, qword_1403C4AB0
0x1400fcc93  mov     rcx, rdi
0x1400fcc96  lea     rdx, aMsftSppStockob; "msft:spp/stockobjects/plugins/params/na"...
0x1400fcc9d  xor     r9d, r9d
0x1400fcca0  call    rax
0x1400fcca2  mov     edi, eax
0x1400fcca4  test    eax, eax
0x1400fcca6  js      loc_1400FCBA5
0x1400fccac  mov     rdi, [rbp+4Fh+var_B8]
0x1400fccb0  mov     qword ptr [rbp+4Fh+var_A8], r12
0x1400fccb4  mov     dword ptr [rbp+4Fh+var_A8+8], 2
0x1400fccbb  mov     qword ptr [rbp+4Fh+var_98], r12
0x1400fccbf  mov     rax, [rdi]
0x1400fccc2  mov     rbx, [rax+48h]
0x1400fccc6  mov     rax, cs:__guard_check_icall_fptr
0x1400fcccd  mov     rcx, rbx
0x1400fccd0  call    rax ; _guard_check_icall_nop
0x1400fccd2  mov     rax, rbx
0x1400fccd5  lea     rdx, [rbp+4Fh+var_A8]
0x1400fccd9  xor     r8d, r8d
0x1400fccdc  mov     rcx, rdi
0x1400fccdf  call    rax
0x1400fcce1  mov     edi, eax
0x1400fcce3  test    eax, eax
0x1400fcce5  js      loc_1400FCBA5
0x1400fcceb  lea     rdx, dword_1404456E0
0x1400fccf2  lea     rcx, dword_140421DD8
0x1400fccf9  call    sub_140056E80
0x1400fccfe  mov     rdi, cs:qword_140446270
0x1400fcd05  mov     rax, [rdi]
0x1400fcd08  mov     rbx, [rax+18h]
0x1400fcd0c  mov     rax, cs:__guard_check_icall_fptr
0x1400fcd13  mov     rcx, rbx
0x1400fcd16  call    rax ; _guard_check_icall_nop
0x1400fcd18  xor     r9d, r9d
0x1400fcd1b  lea     r8, qword_1403C4AB0
0x1400fcd22  lea     rdx, aMsftSppStockob; "msft:spp/stockobjects/plugins/params/na"...
0x1400fcd29  mov     rax, rbx
0x1400fcd2c  test    rsi, rsi
0x1400fcd2f  jz      short loc_1400FCDAB
0x1400fcd31  lea     rcx, [rsp+110h+var_D8]
0x1400fcd36  mov     [rsp+110h+var_F0], rcx
0x1400fcd3b  mov     rcx, rdi
0x1400fcd3e  call    rax
0x1400fcd40  lea     rdx, dword_14043B95C
0x1400fcd47  mov     edi, eax
0x1400fcd49  lea     rcx, dword_140418B40
0x1400fcd50  call    sub_140057510
0x1400fcd55  test    edi, edi
0x1400fcd57  jns     short loc_1400FCD60
0x1400fcd59  mov     ecx, edi
0x1400fcd5b  jmp     loc_1400FCB73
0x1400fcd60  mov     rdi, [rsp+110h+var_D8]
0x1400fcd65  mov     qword ptr [rbp+4Fh+var_A8], rsi
0x1400fcd69  mov     dword ptr [rbp+4Fh+var_A8+8], 2
0x1400fcd70  mov     qword ptr [rbp+4Fh+var_98], rsi
0x1400fcd74  mov     rax, [rdi]
0x1400fcd77  mov     rbx, [rax+48h]
0x1400fcd7b  mov     rax, cs:__guard_check_icall_fptr
0x1400fcd82  mov     rcx, rbx
0x1400fcd85  call    rax ; _guard_check_icall_nop
0x1400fcd87  mov     r15d, 1
0x1400fcd8d  lea     rdx, [rbp+4Fh+var_A8]
0x1400fcd91  mov     r8d, r15d
0x1400fcd94  mov     rax, rbx
0x1400fcd97  mov     rcx, rdi
0x1400fcd9a  call    rax
0x1400fcd9c  mov     edi, eax
0x1400fcd9e  test    eax, eax
0x1400fcda0  jns     loc_1400FCECD
0x1400fcda6  jmp     loc_1400FCBA5
0x1400fcdab  lea     rcx, [rbp+4Fh+var_C8]
0x1400fcdaf  mov     [rsp+110h+var_F0], rcx
0x1400fcdb4  mov     rcx, rdi
0x1400fcdb7  call    rax
0x1400fcdb9  lea     rdx, dword_14043F6CC
0x1400fcdc0  mov     edi, eax
0x1400fcdc2  lea     rcx, dword_1404119C8
0x1400fcdc9  call    sub_140057850
0x1400fcdce  test    edi, edi
0x1400fcdd0  jns     short loc_1400FCDEA
0x1400fcdd2  lea     rdx, dword_14043F5A8
0x1400fcdd9  lea     rcx, dword_140425564
0x1400fcde0  call    sub_140057FC0
0x1400fcde5  jmp     loc_1400FCD59
0x1400fcdea  mov     rdi, [rbp+4Fh+var_C8]
0x1400fcdee  lea     rax, aLicensetype_0; "licenseType"
0x1400fcdf5  mov     qword ptr [rbp+4Fh+var_A8], rax
0x1400fcdf9  lea     rax, aMsftSlStil; "msft:sl/STIL"
0x1400fce00  mov     qword ptr [rbp+4Fh+var_98], rax
0x1400fce04  mov     dword ptr [rbp+4Fh+var_A8+8], 2
0x1400fce0b  mov     rax, [rdi]
0x1400fce0e  mov     rbx, [rax+48h]
0x1400fce12  mov     rax, cs:__guard_check_icall_fptr
0x1400fce19  mov     rcx, rbx
0x1400fce1c  call    rax ; _guard_check_icall_nop
0x1400fce1e  mov     r15d, 1
0x1400fce24  lea     rdx, [rbp+4Fh+var_A8]
0x1400fce28  mov     r8d, r15d
0x1400fce2b  mov     rax, rbx
0x1400fce2e  mov     rcx, rdi
0x1400fce31  call    rax
0x1400fce33  mov     edi, eax
0x1400fce35  test    eax, eax
0x1400fce37  js      loc_1400FCBA5
0x1400fce3d  mov     rdi, cs:qword_1404462A0
0x1400fce44  mov     rax, [rdi]
0x1400fce47  mov     rbx, [rax+0A0h]
0x1400fce4e  mov     rax, cs:__guard_check_icall_fptr
0x1400fce55  mov     rcx, rbx
0x1400fce58  call    rax ; _guard_check_icall_nop
0x1400fce5a  mov     r8, [rbp+4Fh+var_C8]
0x1400fce5e  lea     r9, [rbp+4Fh+var_68]
0x1400fce62  mov     rax, rbx
0x1400fce65  mov     edx, r15d
0x1400fce68  mov     rcx, rdi
0x1400fce6b  call    rax
0x1400fce6d  mov     edi, eax
0x1400fce6f  cmp     eax, 0C004F012h
0x1400fce74  jnz     short loc_1400FCE7E
0x1400fce76  lea     edi, [rax-1]
0x1400fce79  jmp     loc_1400FCD59
0x1400fce7e  test    eax, eax
0x1400fce80  js      loc_1400FCD59
0x1400fce86  mov     rdi, [rbp+4Fh+var_68]
0x1400fce8a  mov     rax, [rdi]
0x1400fce8d  mov     rbx, [rax]
0x1400fce90  mov     rax, cs:__guard_check_icall_fptr
0x1400fce97  mov     rcx, rbx
0x1400fce9a  call    rax ; _guard_check_icall_nop
0x1400fce9c  mov     rax, rbx
0x1400fce9f  lea     r8, [rsp+110h+var_D8]
0x1400fcea4  lea     rdx, qword_1403C4AB0
0x1400fceab  mov     rcx, rdi
0x1400fceae  call    rax
0x1400fceb0  lea     rdx, dword_14043D978
0x1400fceb7  mov     edi, eax
0x1400fceb9  lea     rcx, dword_140423BF8
0x1400fcec0  call    sub_1400567F0
0x1400fcec5  test    edi, edi
0x1400fcec7  js      loc_1400FCD59
0x1400fcecd  mov     rdi, cs:qword_140446258
0x1400fced4  mov     qword ptr [rbp+4Fh+var_40], r14
0x1400fced8  mov     qword ptr [rbp+4Fh+var_40+8], r12
0x1400fcedc  mov     rax, [rdi]
0x1400fcedf  mov     rbx, [rax+30h]
0x1400fcee3  mov     rax, cs:__guard_check_icall_fptr
0x1400fceea  mov     rcx, rbx
0x1400fceed  call    rax ; _guard_check_icall_nop
0x1400fceef  mov     rax, rbx
0x1400fcef2  lea     r8, [rbp+4Fh+FileTime2]
0x1400fcef6  lea     rdx, [rbp+4Fh+var_40]
0x1400fcefa  mov     rcx, rdi
0x1400fcefd  call    rax
0x1400fceff  lea     rdx, dword_140442F74
0x1400fcf06  mov     edi, eax
0x1400fcf08  lea     rcx, dword_140415458
0x1400fcf0f  call    sub_1400571C0
0x1400fcf14  mov     ecx, 80000000h
0x1400fcf19  lea     eax, [rdi+rcx]
0x1400fcf1c  test    ecx, eax
0x1400fcf1e  jnz     short loc_1400FCF3F
0x1400fcf20  lea     rdx, dword_140443048
0x1400fcf27  lea     rcx, dword_1404288B8
0x1400fcf2e  call    sub_1400571C0
0x1400fcf33  cmp     edi, 8004D102h
0x1400fcf39  jnz     loc_1400FCD59
0x1400fcf3f  mov     rdx, [r13+0D8h]
0x1400fcf46  lea     r8, [rbp+4Fh+var_60]
0x1400fcf4a  mov     rcx, cs:qword_1404462A0
0x1400fcf51  call    sub_1400F86E4
0x1400fcf56  mov     edi, eax
0x1400fcf58  test    eax, eax
0x1400fcf5a  js      loc_1400FCBA5
  ... truncated ...
```

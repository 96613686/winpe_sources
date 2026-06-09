# CImage::LoadImageInfo(ulong)

- ea: `0x18000b17c`
- end: `0x18000b8aa`
- name: `?LoadImageInfo@CImage@@QEAAJK@Z`
- size: `1838`
- prototype: `__int64 __fastcall(CImage *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000ba2c`

## callees

- `0x1800027d0`
- `0x180003680`
- `0x180009198`
- `0x18000b17c`
- `0x18000d5b0`
- `0x18000d6b0`
- `0x18000ff10`
- `0x180011010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000b586`
- `RPCRT4!UuidCreate` at `0x18000b586`
- `ImageLib!DepImgFreeBuffer` at `0x18000b81c`
- `ImageLib!DepImgFreeBuffer` at `0x18000b81c`
- `WdsCommonLib!?ParseGuid@@YAKPEBGPEAU_GUID@@@Z` at `0x18000b86b`
- `WdsCommonLib!?ParseGuid@@YAKPEBGPEAU_GUID@@@Z` at `0x18000b86b`

## pseudocode

```c
__int64 __fastcall CImage::LoadImageInfo(CImage *this, __int64 a2)
{
  int v2; // edi
  int v4; // esi
  __int64 v5; // rbx
  __int64 v6; // rdx
  _QWORD *v7; // r15
  __int64 v8; // rdx
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  UUID v17; // xmm0
  __int64 v18; // rdx
  __int64 v19; // rdx
  _QWORD *v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  _QWORD *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rdx
  int v38; // eax
  __int64 v39; // rdx
  int v40; // edi
  int v41; // esi
  _OWORD *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v53; // rdi
  __int64 v54; // rdx
  __int64 v55; // r8
  _QWORD *v56; // [rsp+78h] [rbp-90h] BYREF
  int v57; // [rsp+80h] [rbp-88h] BYREF
  _QWORD *v58; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int16 *v59; // [rsp+90h] [rbp-78h] BYREF
  __int64 v60; // [rsp+98h] [rbp-70h] BYREF
  UUID Uuid; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 v62[8]; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v63; // [rsp+C8h] [rbp-40h]
  __int128 v64; // [rsp+D8h] [rbp-30h]
  __int128 v65; // [rsp+E8h] [rbp-20h]
  __int64 v66; // [rsp+F8h] [rbp-10h]
  int v67; // [rsp+100h] [rbp-8h]
  wchar_t v68; // [rsp+104h] [rbp-4h]

  v57 = 0;
  v2 = a2;
  v58 = 0;
  v60 = 0;
  v4 = 0;
  v56 = 0;
  v59 = 0;
  if ( !(_DWORD)a2 || (unsigned int)a2 > *((_DWORD *)this + 32) )
  {
    LODWORD(v5) = -1056833013;
    if ( (int)ElValidateHr_5(3238134283LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 846) < 0 )
      goto LABEL_49;
  }
  *((_DWORD *)this + 33) = v2;
  CImage::CleanupImageInfo(this);
  v5 = (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD **))(**((_QWORD **)this + 48) + 24LL))(
         *((_QWORD *)this + 48),
         *((unsigned int *)this + 33),
         &v58);
  if ( (int)ElValidateHr_5(v5, v6, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 863) < 0 )
    goto LABEL_49;
  v7 = (_QWORD *)((char *)this + 392);
  v5 = (*(unsigned int (__fastcall **)(_QWORD *, char *))(*v58 + 32LL))(v58, (char *)this + 392);
  if ( (int)ElValidateHr_5(v5, v8, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 869) < 0 )
    goto LABEL_49;
  v5 = (**(unsigned int (__fastcall ***)(_QWORD, char *, int *))*v7)(*v7, (char *)this + 368, &v57);
  if ( (int)ElValidateHr_5(v5, v9, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 877) < 0 )
    goto LABEL_49;
  *((_DWORD *)this + 91) = v57;
  v10 = *((_DWORD *)this + 6);
  if ( (v10 & 8) != 0 )
  {
    v11 = *v7;
    *((_DWORD *)this + 6) = v10 & 0xFFFFFFF7;
    v5 = (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 8LL))(v11, &v60);
    if ( (int)ElValidateHr_5(v5, v12, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 887) < 0 )
      goto LABEL_49;
    v4 = 1;
    *((_DWORD *)this + 88) = 1;
  }
  v13 = *((_DWORD *)this + 6);
  if ( (v13 & 0x100) != 0 )
  {
    v14 = *v7;
    Uuid = 0;
    v67 = *(_DWORD *)L"0}";
    v63 = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
    v65 = *(_OWORD *)L"-000000000000}";
    *(_OWORD *)v62 = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
    v68 = a00000000000000[38];
    *((_DWORD *)this + 6) = v13 & 0xFFFFFEFF;
    v66 = *(_QWORD *)L"00000}";
    v64 = *(_OWORD *)L"000-0000-000000000000}";
    v15 = v14 + 8 + *(int *)(*(_QWORD *)(v14 + 8) + 8LL);
    v5 = (*(unsigned int (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v15 + 16LL))(v15, &v56);
    if ( (int)ElValidateHr_5(v5, v16, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 905) < 0 )
      goto LABEL_49;
    if ( *((_DWORD *)this + 17) )
    {
      v17 = *(UUID *)((char *)this + 72);
      *((_DWORD *)this + 17) = 0;
      Uuid = v17;
      *(_OWORD *)((char *)this + 72) = 0;
    }
    else
    {
      v5 = (unsigned int)UuidCreate(&Uuid);
      if ( (unsigned int)ElValidateWin32_4(v5, v29, v30, 926) )
      {
        if ( (int)v5 <= 0 )
          goto LABEL_49;
        LODWORD(v5) = (unsigned __int16)v5;
        goto LABEL_26;
      }
    }
    v5 = (unsigned int)StringCchPrintfW(
                         v62,
                         0x27u,
                         L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
                         Uuid.Data1,
                         Uuid.Data2,
                         Uuid.Data3,
                         Uuid.Data4[0],
                         Uuid.Data4[1],
                         Uuid.Data4[2],
                         Uuid.Data4[3],
                         Uuid.Data4[4],
                         Uuid.Data4[5],
                         Uuid.Data4[6],
                         Uuid.Data4[7]);
    if ( (int)ElValidateHr_5(v5, v18, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 933) < 0 )
      goto LABEL_49;
    v5 = (*(unsigned int (__fastcall **)(_QWORD *, const wchar_t *, unsigned __int16 *))(*v56 + 16LL))(
           v56,
           L"WdsImageId",
           v62);
    if ( (int)ElValidateHr_5(v5, v19, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 937) < 0 )
      goto LABEL_49;
    v20 = v56;
    v4 = 1;
    *((_DWORD *)this + 88) = 1;
    if ( v20 )
    {
      v21 = (__int64)v20 + *(int *)(v20[1] + 4LL) + 8;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v56 = 0;
    }
  }
  v22 = *((_DWORD *)this + 6);
  if ( (v22 & 0x400) != 0 )
  {
    v23 = *v7;
    *((_DWORD *)this + 6) = v22 & 0xFFFFFBFF;
    v24 = v23 + 8 + *(int *)(*(_QWORD *)(v23 + 8) + 8LL);
    v5 = (*(unsigned int (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v24 + 16LL))(v24, &v56);
    if ( (int)ElValidateHr_5(v5, v25, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 952) < 0 )
      goto LABEL_49;
    v5 = (*(unsigned int (__fastcall **)(_QWORD *, const wchar_t *, const wchar_t *))(*v56 + 16LL))(
           v56,
           L"WdsImageId",
           &pszSrc);
    if ( (int)ElValidateHr_5(v5, v26, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 963) < 0 )
      goto LABEL_49;
    v27 = v56;
    *((_DWORD *)this + 88) = 1;
    if ( v27 )
    {
      v28 = (__int64)v27 + *(int *)(v27[1] + 4LL) + 8;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v56 = 0;
    }
  }
  else if ( !v4 )
  {
    goto LABEL_31;
  }
  v31 = *((_DWORD *)this + 6);
  if ( (v31 & 0x20) != 0 )
  {
    v32 = *((_QWORD *)this + 49);
    *((_DWORD *)this + 6) = v31 & 0xFFFFFFDF;
    v33 = v32 + 8 + *(int *)(*(_QWORD *)(v32 + 8) + 8LL);
    v5 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v33 + 24LL))(v33);
    if ( (int)ElValidateHr_5(v5, v34, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 979) < 0 )
      goto LABEL_49;
    *((_DWORD *)this + 88) = 0;
  }
LABEL_31:
  if ( (*((_BYTE *)this + 24) & 0x10) != 0 )
    goto LABEL_42;
  v35 = *((_QWORD *)this + 49) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 49) + 8LL) + 8LL);
  v5 = (*(unsigned int (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v35 + 16LL))(v35, &v56);
  if ( (int)ElValidateHr_5(v5, v36, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 994) >= 0 )
  {
    v5 = (unsigned int)WDSGetImageInformation(*((_QWORD *)this + 49), (CImage *)((char *)this + 136));
    if ( (int)ElValidateHr_5(v5, v37, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 997) >= 0 )
    {
      v38 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, unsigned __int16 **))(*v56 + 8LL))(
              v56,
              L"WdsImageId",
              &v59);
      LODWORD(v5) = 0;
      v40 = 0;
      if ( v38 != -2147023728 )
        LODWORD(v5) = v38;
      v41 = v38;
      LOBYTE(v40) = v38 != -2147023728;
      if ( (int)ElValidateHr_5((unsigned int)v5, v39, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1006) >= 0 )
      {
        if ( v41 != -2147023728 && (!v59 || !*v59) )
        {
          v42 = (_OWORD *)((char *)this + 52);
LABEL_41:
          *((_DWORD *)this + 12) = 0;
          *v42 = 0;
          goto LABEL_42;
        }
        v42 = (_OWORD *)((char *)this + 52);
        if ( !v40 )
          goto LABEL_41;
        v53 = ParseGuid(v59, (struct _GUID *)((char *)this + 52));
        if ( !(unsigned int)ElValidateWin32_4(v53, v54, v55, 1024) )
        {
          *((_DWORD *)this + 12) = 1;
LABEL_42:
          if ( *((char *)this + 24) < 0 )
          {
            v43 = *((_QWORD *)this + 49);
            if ( v43 )
            {
              v44 = v43 + 8 + *(int *)(*(_QWORD *)(v43 + 8) + 4LL);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
              *((_QWORD *)this + 49) = 0;
            }
            v45 = *((_QWORD *)this + 48);
            if ( v45 )
            {
              v46 = v45 + 8 + *(int *)(*(_QWORD *)(v45 + 8) + 4LL);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
              *((_QWORD *)this + 48) = 0;
            }
            v47 = *((_QWORD *)this + 47);
            if ( v47 )
            {
              v48 = v47 + 8 + *(int *)(*(_QWORD *)(v47 + 8) + 4LL);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
              *((_QWORD *)this + 47) = 0;
            }
          }
          goto LABEL_49;
        }
        if ( (int)v53 <= 0 )
        {
          LODWORD(v5) = v53;
          goto LABEL_49;
        }
        LODWORD(v5) = (unsigned __int16)v53;
LABEL_26:
        LODWORD(v5) = v5 | 0x80070000;
      }
    }
  }
LABEL_49:
  if ( v60 )
  {
    v49 = v60 + 8 + *(int *)(*(_QWORD *)(v60 + 8) + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v60 = 0;
  }
  if ( v56 )
  {
    v50 = (__int64)v56 + *(int *)(v56[1] + 4LL) + 8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v56 = 0;
  }
  if ( v58 )
  {
    v51 = (__int64)v58 + *(int *)(v58[1] + 4LL) + 8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v58 = 0;
  }
  DepImgFreeBuffer(v59);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b17c  mov     rax, rsp
0x18000b17f  mov     [rax+10h], rbx
0x18000b183  mov     [rax+18h], rsi
0x18000b187  mov     [rax+20h], rdi
0x18000b18b  push    rbp
0x18000b18c  push    r12
0x18000b18e  push    r13
0x18000b190  push    r14
0x18000b192  push    r15
0x18000b194  lea     rbp, [rax-38h]
0x18000b198  sub     rsp, 110h
0x18000b19f  mov     rax, cs:__security_cookie
0x18000b1a6  xor     rax, rsp
0x18000b1a9  mov     [rbp+30h+var_30], rax
0x18000b1ad  xor     r12d, r12d
0x18000b1b0  lea     r13, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000b1b7  mov     [rsp+130h+var_B8], r12d
0x18000b1bc  mov     edi, edx
0x18000b1be  mov     [rbp+30h+var_B0], r12
0x18000b1c2  mov     r14, rcx
0x18000b1c5  mov     [rbp+30h+var_A0], r12
0x18000b1c9  mov     esi, r12d
0x18000b1cc  mov     [rsp+130h+var_C0], r12
0x18000b1d1  mov     [rbp+30h+var_A8], r12
0x18000b1d5  cmp     edx, 1
0x18000b1d8  jb      short loc_18000B1E2
0x18000b1da  cmp     edx, [rcx+80h]
0x18000b1e0  jbe     short loc_18000B1FF
0x18000b1e2  mov     ebx, 0C102020Bh
0x18000b1e7  mov     r9d, 34Eh
0x18000b1ed  mov     ecx, ebx
0x18000b1ef  mov     r8, r13
0x18000b1f2  call    ElValidateHr_5
0x18000b1f7  test    eax, eax
0x18000b1f9  js      loc_18000B79E
0x18000b1ff  mov     rcx, r14; this
0x18000b202  mov     [r14+84h], edi
0x18000b209  call    ?CleanupImageInfo@CImage@@AEAAXXZ; CImage::CleanupImageInfo(void)
0x18000b20e  mov     rcx, [r14+180h]
0x18000b215  lea     r8, [rbp+30h+var_B0]
0x18000b219  mov     edx, [r14+84h]
0x18000b220  mov     rax, [rcx]
0x18000b223  mov     rax, [rax+18h]
0x18000b227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b22c  mov     r9d, 35Fh
0x18000b232  mov     r8, r13
0x18000b235  mov     ecx, eax
0x18000b237  mov     ebx, eax
0x18000b239  call    ElValidateHr_5
0x18000b23e  test    eax, eax
0x18000b240  js      loc_18000B79E
0x18000b246  mov     rcx, [rbp+30h+var_B0]
0x18000b24a  lea     r15, [r14+188h]
0x18000b251  mov     rdx, r15
0x18000b254  mov     rax, [rcx]
0x18000b257  mov     rax, [rax+20h]
0x18000b25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b260  mov     r9d, 365h
0x18000b266  mov     r8, r13
0x18000b269  mov     ecx, eax
0x18000b26b  mov     ebx, eax
0x18000b26d  call    ElValidateHr_5
0x18000b272  test    eax, eax
0x18000b274  js      loc_18000B79E
0x18000b27a  mov     rcx, [r15]
0x18000b27d  lea     rdx, [r14+170h]
0x18000b284  lea     r8, [rsp+130h+var_B8]
0x18000b289  mov     rax, [rcx]
0x18000b28c  mov     rax, [rax]
0x18000b28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b294  mov     r9d, 36Dh
0x18000b29a  mov     r8, r13
0x18000b29d  mov     ecx, eax
0x18000b29f  mov     ebx, eax
0x18000b2a1  call    ElValidateHr_5
0x18000b2a6  test    eax, eax
0x18000b2a8  js      loc_18000B79E
0x18000b2ae  mov     eax, [rsp+130h+var_B8]
0x18000b2b2  mov     [r14+16Ch], eax
0x18000b2b9  mov     eax, [r14+18h]
0x18000b2bd  test    al, 8
0x18000b2bf  jz      short loc_18000B301
0x18000b2c1  mov     rcx, [r15]
0x18000b2c4  lea     rdx, [rbp+30h+var_A0]
0x18000b2c8  and     eax, 0FFFFFFF7h
0x18000b2cb  mov     [r14+18h], eax
0x18000b2cf  mov     rax, [rcx]
0x18000b2d2  mov     rax, [rax+8]
0x18000b2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2db  mov     r9d, 377h
0x18000b2e1  mov     r8, r13
0x18000b2e4  mov     ecx, eax
0x18000b2e6  mov     ebx, eax
0x18000b2e8  call    ElValidateHr_5
0x18000b2ed  test    eax, eax
0x18000b2ef  js      loc_18000B79E
0x18000b2f5  mov     esi, 1
0x18000b2fa  mov     [r14+160h], esi
0x18000b301  mov     ecx, [r14+18h]
0x18000b305  bt      ecx, 8
0x18000b309  jnb     loc_18000B4BF
0x18000b30f  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x18000b315  xorps   xmm0, xmm0
0x18000b318  movaps  xmm1, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18000b31f  btr     ecx, 8
0x18000b323  mov     rdx, [r15]
0x18000b326  movups  xmmword ptr [rbp+30h+Uuid.Data1], xmm0
0x18000b32a  mov     [rbp+30h+var_38], eax
0x18000b32d  movaps  xmm0, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18000b334  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x18000b33b  movaps  [rbp+30h+var_70], xmm0
0x18000b33f  movaps  xmm0, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x18000b346  movaps  [rbp+30h+var_50], xmm0
0x18000b34a  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x18000b352  movaps  xmmword ptr [rbp+30h+var_80], xmm1
0x18000b356  movaps  xmm1, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18000b35d  mov     [rbp+30h+var_34], ax
0x18000b361  mov     [r14+18h], ecx
0x18000b365  movsd   [rbp+30h+var_40], xmm0
0x18000b36a  movaps  [rbp+30h+var_60], xmm1
0x18000b36e  mov     rax, [rdx+8]
0x18000b372  add     rdx, 8
0x18000b376  movsxd  rcx, dword ptr [rax+8]
0x18000b37a  add     rcx, rdx
0x18000b37d  lea     rdx, [rsp+130h+var_C0]
0x18000b382  mov     rax, [rcx]
0x18000b385  mov     rax, [rax+10h]
0x18000b389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b38e  mov     r9d, 389h
0x18000b394  mov     r8, r13
0x18000b397  mov     ecx, eax
0x18000b399  mov     ebx, eax
0x18000b39b  call    ElValidateHr_5
0x18000b3a0  test    eax, eax
0x18000b3a2  js      loc_18000B79E
0x18000b3a8  cmp     [r14+44h], r12d
0x18000b3ac  jz      loc_18000B582
0x18000b3b2  movups  xmm0, xmmword ptr [r14+48h]
0x18000b3b7  mov     [r14+44h], r12d
0x18000b3bb  xorps   xmm1, xmm1
0x18000b3be  movdqu  xmmword ptr [rbp+30h+Uuid.Data1], xmm0
0x18000b3c3  movups  xmmword ptr [r14+48h], xmm1
0x18000b3c8  movzx   ecx, [rbp+30h+Uuid.Data4+6]
0x18000b3cc  movzx   edx, [rbp+30h+Uuid.Data4+5]
0x18000b3d0  movzx   r8d, [rbp+30h+Uuid.Data4+4]
0x18000b3d5  movzx   r9d, [rbp+30h+Uuid.Data4+3]
0x18000b3da  movzx   eax, [rbp+30h+Uuid.Data4+7]
0x18000b3de  movzx   r10d, [rbp+30h+Uuid.Data4+2]
0x18000b3e3  movzx   r11d, [rbp+30h+Uuid.Data4+1]
0x18000b3e8  movzx   ebx, [rbp+30h+Uuid.Data4]
0x18000b3ec  movzx   edi, [rbp+30h+Uuid.Data3]
0x18000b3f0  movzx   esi, [rbp+30h+Uuid.Data2]
0x18000b3f4  mov     dword ptr [rsp+130h+var_C8], eax
0x18000b3f8  mov     [rsp+130h+var_D0], ecx
0x18000b3fc  lea     rcx, [rbp+30h+var_80]; unsigned __int16 *
0x18000b400  mov     [rsp+130h+var_D8], edx
0x18000b404  mov     edx, 27h ; '''; unsigned __int64
0x18000b409  mov     [rsp+130h+var_E0], r8d
0x18000b40e  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x18000b415  mov     [rsp+130h+var_E8], r9d
0x18000b41a  mov     r9d, [rbp+30h+Uuid.Data1]
0x18000b41e  mov     [rsp+130h+var_F0], r10d
0x18000b423  mov     [rsp+130h+var_F8], r11d
0x18000b428  mov     [rsp+130h+var_100], ebx
0x18000b42c  mov     [rsp+130h+var_108], edi
0x18000b430  mov     [rsp+130h+var_110], esi
0x18000b434  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b439  mov     r9d, 3A5h
0x18000b43f  mov     r8, r13
0x18000b442  mov     ecx, eax
0x18000b444  mov     ebx, eax
0x18000b446  call    ElValidateHr_5
0x18000b44b  test    eax, eax
0x18000b44d  js      loc_18000B79E
0x18000b453  mov     rcx, [rsp+130h+var_C0]
0x18000b458  lea     r8, [rbp+30h+var_80]
0x18000b45c  lea     rdx, aWdsimageid; "WdsImageId"
0x18000b463  mov     rax, [rcx]
0x18000b466  mov     rax, [rax+10h]
0x18000b46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b46f  mov     r9d, 3A9h
0x18000b475  mov     r8, r13
0x18000b478  mov     ecx, eax
0x18000b47a  mov     ebx, eax
0x18000b47c  call    ElValidateHr_5
0x18000b481  test    eax, eax
0x18000b483  js      loc_18000B79E
0x18000b489  mov     rdx, [rsp+130h+var_C0]
0x18000b48e  mov     esi, 1
0x18000b493  mov     [r14+160h], esi
0x18000b49a  test    rdx, rdx
0x18000b49d  jz      short loc_18000B4BF
0x18000b49f  mov     rax, [rdx+8]
0x18000b4a3  add     rdx, 8
0x18000b4a7  movsxd  rcx, dword ptr [rax+4]
0x18000b4ab  add     rcx, rdx
0x18000b4ae  mov     rax, [rcx]
0x18000b4b1  mov     rax, [rax+10h]
0x18000b4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4ba  mov     [rsp+130h+var_C0], r12
0x18000b4bf  mov     eax, [r14+18h]
0x18000b4c3  bt      eax, 0Ah
0x18000b4c7  jnb     loc_18000B5BF
0x18000b4cd  mov     rdx, [r15]
0x18000b4d0  btr     eax, 0Ah
0x18000b4d4  mov     [r14+18h], eax
0x18000b4d8  mov     rax, [rdx+8]
0x18000b4dc  add     rdx, 8
0x18000b4e0  movsxd  rcx, dword ptr [rax+8]
0x18000b4e4  add     rcx, rdx
0x18000b4e7  lea     rdx, [rsp+130h+var_C0]
0x18000b4ec  mov     rax, [rcx]
0x18000b4ef  mov     rax, [rax+10h]
0x18000b4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f8  mov     r9d, 3B8h
0x18000b4fe  mov     r8, r13
0x18000b501  mov     ecx, eax
0x18000b503  mov     ebx, eax
0x18000b505  call    ElValidateHr_5
0x18000b50a  test    eax, eax
0x18000b50c  js      loc_18000B79E
0x18000b512  mov     rcx, [rsp+130h+var_C0]
0x18000b517  lea     r8, pszSrc
0x18000b51e  lea     rdx, aWdsimageid; "WdsImageId"
0x18000b525  mov     rax, [rcx]
0x18000b528  mov     rax, [rax+10h]
0x18000b52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b531  mov     r9d, 3C3h
0x18000b537  mov     r8, r13
0x18000b53a  mov     ecx, eax
0x18000b53c  mov     ebx, eax
0x18000b53e  call    ElValidateHr_5
0x18000b543  test    eax, eax
0x18000b545  js      loc_18000B79E
0x18000b54b  mov     rdx, [rsp+130h+var_C0]
0x18000b550  mov     dword ptr [r14+160h], 1
0x18000b55b  test    rdx, rdx
0x18000b55e  jz      short loc_18000B5C3
0x18000b560  mov     rax, [rdx+8]
0x18000b564  add     rdx, 8
0x18000b568  movsxd  rcx, dword ptr [rax+4]
0x18000b56c  add     rcx, rdx
0x18000b56f  mov     rax, [rcx]
0x18000b572  mov     rax, [rax+10h]
0x18000b576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b57b  mov     [rsp+130h+var_C0], r12
0x18000b580  jmp     short loc_18000B5C3
0x18000b582  lea     rcx, [rbp+30h+Uuid]; Uuid
0x18000b586  call    cs:__imp_UuidCreate
0x18000b58d  nop     dword ptr [rax+rax+00h]
0x18000b592  mov     ecx, eax
0x18000b594  mov     r9d, 39Eh
0x18000b59a  mov     ebx, eax
0x18000b59c  call    ElValidateWin32_4
0x18000b5a1  test    eax, eax
0x18000b5a3  jz      loc_18000B3C8
0x18000b5a9  test    ebx, ebx
0x18000b5ab  jle     loc_18000B79E
0x18000b5b1  movzx   ebx, bx
0x18000b5b4  or      ebx, 80070000h
0x18000b5ba  jmp     loc_18000B79E
0x18000b5bf  test    esi, esi
0x18000b5c1  jz      short loc_18000B615
0x18000b5c3  mov     eax, [r14+18h]
0x18000b5c7  test    al, 20h
0x18000b5c9  jz      short loc_18000B615
0x18000b5cb  mov     rdx, [r14+188h]
0x18000b5d2  and     eax, 0FFFFFFDFh
0x18000b5d5  mov     [r14+18h], eax
0x18000b5d9  mov     rax, [rdx+8]
0x18000b5dd  add     rdx, 8
0x18000b5e1  movsxd  rcx, dword ptr [rax+8]
0x18000b5e5  add     rcx, rdx
0x18000b5e8  mov     rax, [rcx]
0x18000b5eb  mov     rax, [rax+18h]
0x18000b5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5f4  mov     r9d, 3D3h
0x18000b5fa  mov     r8, r13
0x18000b5fd  mov     ecx, eax
0x18000b5ff  mov     ebx, eax
0x18000b601  call    ElValidateHr_5
0x18000b606  test    eax, eax
0x18000b608  js      loc_18000B79E
0x18000b60e  mov     [r14+160h], r12d
0x18000b615  test    byte ptr [r14+18h], 10h
0x18000b61a  jnz     loc_18000B709
0x18000b620  mov     rdx, [r14+188h]
0x18000b627  mov     rax, [rdx+8]
0x18000b62b  add     rdx, 8
0x18000b62f  movsxd  rcx, dword ptr [rax+8]
0x18000b633  add     rcx, rdx
0x18000b636  lea     rdx, [rsp+130h+var_C0]
0x18000b63b  mov     rax, [rcx]
0x18000b63e  mov     rax, [rax+10h]
0x18000b642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b647  mov     r9d, 3E2h
0x18000b64d  mov     r8, r13
0x18000b650  mov     ecx, eax
0x18000b652  mov     ebx, eax
0x18000b654  call    ElValidateHr_5
  ... truncated ...
```

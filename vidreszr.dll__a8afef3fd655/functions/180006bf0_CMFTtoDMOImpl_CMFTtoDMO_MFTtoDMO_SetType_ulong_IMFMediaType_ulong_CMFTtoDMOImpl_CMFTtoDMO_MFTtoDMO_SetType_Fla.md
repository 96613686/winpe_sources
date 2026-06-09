# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType(ulong,IMFMediaType *,ulong,CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType_Flag)

- ea: `0x180006bf0`
- end: `0x1800070cd`
- name: `?MFTtoDMO_SetType@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJKPEAUIMFMediaType@@KW4MFTtoDMO_SetType_Flag@1@@Z`
- size: `1245`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180006a60`
- `0x180006a80`
- `0x180006b30`

## callees

- `0x180001dc0`
- `0x180003670`
- `0x1800037e0`
- `0x180006bf0`
- `0x1800158f9`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        unsigned int a4,
        int a5)
{
  __int64 v9; // rax
  __int64 *v10; // rsi
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  int v14; // ecx
  __int64 v15; // rax
  unsigned int v16; // eax
  char v17; // di
  bool v18; // zf
  __int64 *v19; // rcx
  __int64 (__fastcall *v20)(__int64 *, GUID *, __int64 *); // rax
  __int64 v21; // rcx
  int v22; // ebx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // r9
  int v27; // esi
  __int64 v28; // rax
  __int64 (__fastcall *v29)(__int64 *, GUID *, __int64 *); // rax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  __int64 (__fastcall *v33)(__int64 *, GUID *, __int64 *); // rax
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rax
  unsigned int v40; // r8d
  int v41; // ecx
  __int64 v42; // rax
  __int64 v43; // [rsp+30h] [rbp-41h] BYREF
  unsigned int v44; // [rsp+38h] [rbp-39h] BYREF
  unsigned int v45; // [rsp+3Ch] [rbp-35h] BYREF
  __int64 v46; // [rsp+40h] [rbp-31h]
  GUID Buf1; // [rsp+50h] [rbp-21h] BYREF
  GUID Buf2; // [rsp+60h] [rbp-11h] BYREF

  v46 = a1;
  v43 = 0;
  Buf2 = GUID_00000000_0000_0000_0000_000000000000;
  if ( (a4 & 0xFFFFFFFE) != 0 )
    return 2147942487LL;
  v9 = *(_QWORD *)(a1 + 48);
  v10 = (__int64 *)(a1 + 48);
  v45 = 0;
  v44 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned int *))(v9 + 24))(a1 + 48, &v45, &v44);
  v13 = (unsigned int)v11;
  if ( v11 >= 0 )
  {
    v16 = v44;
    if ( !a5 )
      v16 = v45;
    if ( a2 >= v16 )
      return 3222091443LL;
    Buf1 = GUID_00000000_0000_0000_0000_000000000000;
    if ( a3
      && (((*(void (__fastcall **)(__int64 *, const GUID *, GUID *))(*a3 + 80))(a3, &MF_MT_SUBTYPE, &Buf1),
           !memcmp_0(&Buf1, &MEDIASUBTYPE_ARGB32, 0x10u))
       || !memcmp_0(&Buf1, &MEDIASUBTYPE_RGB24, 0x10u)
       || !memcmp_0(&Buf1, &MEDIASUBTYPE_RGB32, 0x10u)
       || !memcmp_0(&Buf1, &MEDIASUBTYPE_RGB555, 0x10u)
       || !memcmp_0(&Buf1, &MEDIASUBTYPE_RGB565, 0x10u)) )
    {
      v17 = 1;
    }
    else
    {
      CMFTtoDMOImpl<CMFTtoDMO>::ConvertMFRGBFormatToDMORGBFormat(v12, a3, v13);
      v17 = 0;
      if ( !a3 )
      {
        v25 = *v10;
        v26 = a4 | 2;
        if ( a5 )
          v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64))(v25 + 72))(v10, a2, 0, v26);
        else
          v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64))(v25 + 64))(v10, a2, 0, v26);
        v27 = v22;
LABEL_56:
        CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(v21, a3);
LABEL_57:
        if ( v22 == 1 )
        {
          v27 = -1072875852;
          v40 = -1072875852;
        }
        else
        {
          v40 = v27;
          if ( !v27 )
            return v40;
        }
        v41 = 0;
        while ( 1 )
        {
          v42 = v41;
          if ( LODWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v42]) == v27 )
            break;
          if ( (unsigned int)++v41 >= 6 )
            return v40;
        }
        return HIDWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v42]);
      }
    }
    (*(void (__fastcall **)(__int64 *, GUID *))(*a3 + 264))(a3, &Buf2);
    v18 = memcmp_0(&MEDIATYPE_Video, &Buf2, 0x10u) == 0;
    v19 = a3;
    v20 = *(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(*a3 + 288);
    if ( v18 )
    {
      Buf1 = FORMAT_MFVideoFormat;
      v22 = v20(a3, &Buf1, &v43);
      if ( v22 >= 0 )
      {
        v23 = *v10;
        v24 = a5
            ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v23 + 72))(v10, a2, v43, a4)
            : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v23 + 64))(v10, a2, v43, a4);
        v22 = v24;
        v28 = *a3;
        Buf1 = FORMAT_MFVideoFormat;
        (*(void (__fastcall **)(__int64 *, GUID *, __int64))(v28 + 296))(a3, &Buf1, v43);
        if ( v22 >= 0 )
          goto LABEL_51;
      }
      if ( v22 == -1072861834 )
        goto LABEL_50;
      v29 = *(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(*a3 + 288);
      Buf1 = FORMAT_VideoInfo2;
      v22 = v29(a3, &Buf1, &v43);
      if ( v22 >= 0 )
      {
        v30 = *v10;
        v31 = a5
            ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v30 + 72))(v10, a2, v43, a4)
            : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v30 + 64))(v10, a2, v43, a4);
        v22 = v31;
        v32 = *a3;
        Buf1 = FORMAT_VideoInfo2;
        (*(void (__fastcall **)(__int64 *, GUID *, __int64))(v32 + 296))(a3, &Buf1, v43);
        if ( v22 >= 0 )
          goto LABEL_51;
      }
      if ( v22 == -1072861834 )
        goto LABEL_50;
      v33 = *(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(*a3 + 288);
      Buf1 = FORMAT_VideoInfo;
      v22 = v33(a3, &Buf1, &v43);
      if ( v22 >= 0 )
      {
        v34 = *v10;
        v35 = a5
            ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v34 + 72))(v10, a2, v43, a4)
            : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v34 + 64))(v10, a2, v43, a4);
        v22 = v35;
        v36 = *a3;
        Buf1 = FORMAT_VideoInfo;
        (*(void (__fastcall **)(__int64 *, GUID *, __int64))(v36 + 296))(a3, &Buf1, v43);
        if ( v22 >= 0 )
        {
LABEL_51:
          if ( (a4 & 1) == 0 )
          {
            if ( a5 )
              *(_BYTE *)(v46 + 41) = v17;
            else
              *(_BYTE *)(v46 + 40) = v17;
          }
LABEL_55:
          v27 = v22;
          if ( v17 )
            goto LABEL_57;
          goto LABEL_56;
        }
      }
      if ( v22 == -1072861834 )
      {
LABEL_50:
        if ( v22 < 0 )
          goto LABEL_55;
        goto LABEL_51;
      }
      v19 = a3;
      v20 = *(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(*a3 + 288);
    }
    Buf1 = AM_MEDIA_TYPE_REPRESENTATION;
    v22 = v20(v19, &Buf1, &v43);
    if ( v22 < 0 )
      goto LABEL_55;
    v37 = *v10;
    if ( a5 )
      v38 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v37 + 72))(v10, a2, v43, a4);
    else
      v38 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v37 + 64))(v10, a2, v43, a4);
    v22 = v38;
    v39 = *a3;
    Buf1 = AM_MEDIA_TYPE_REPRESENTATION;
    (*(void (__fastcall **)(__int64 *, GUID *, __int64))(v39 + 296))(a3, &Buf1, v43);
    goto LABEL_50;
  }
  v14 = 0;
  while ( 1 )
  {
    v15 = v14;
    if ( LODWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v15]) == (_DWORD)v13 )
      break;
    if ( (unsigned int)++v14 >= 6 )
      return (unsigned int)v13;
  }
  return HIDWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v15]);
}

```

## disassembly

```asm
0x180006bf0  push    rbp
0x180006bf2  push    rbx
0x180006bf3  push    r12
0x180006bf5  push    r14
0x180006bf7  push    r15
0x180006bf9  lea     rbp, [rsp-2Fh]
0x180006bfe  sub     rsp, 0A0h
0x180006c05  mov     rax, cs:__security_cookie
0x180006c0c  xor     rax, rsp
0x180006c0f  mov     [rbp+4Fh+var_50], rax
0x180006c13  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180006c1a  xor     ebx, ebx
0x180006c1c  mov     [rbp+4Fh+var_80], rcx
0x180006c20  mov     [rbp+4Fh+var_90], rbx
0x180006c24  mov     r15d, r9d
0x180006c27  mov     r14, r8
0x180006c2a  mov     r12d, edx
0x180006c2d  movups  [rbp+4Fh+Buf2], xmm0
0x180006c31  test    r9d, 0FFFFFFFEh
0x180006c38  jz      short loc_180006C44
0x180006c3a  mov     eax, 80070057h
0x180006c3f  jmp     loc_1800070B1
0x180006c44  mov     rax, [rcx+30h]
0x180006c48  lea     r8, [rbp+4Fh+var_88]
0x180006c4c  mov     [rsp+0C0h+var_28], rsi
0x180006c54  lea     rdx, [rbp+4Fh+var_84]
0x180006c58  lea     rsi, [rcx+30h]
0x180006c5c  mov     [rbp+4Fh+var_84], ebx
0x180006c5f  mov     rcx, rsi
0x180006c62  mov     [rbp+4Fh+var_88], ebx
0x180006c65  mov     rax, [rax+18h]
0x180006c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c6e  mov     r8d, eax
0x180006c71  test    eax, eax
0x180006c73  jns     short loc_180006CAD
0x180006c75  mov     ecx, ebx
0x180006c77  lea     rdx, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x180006c7e  xchg    ax, ax
0x180006c80  movsxd  rax, ecx
0x180006c83  lea     rax, ds:0[rax*8]
0x180006c8b  cmp     [rax+rdx], r8d
0x180006c8f  jz      short loc_180006CA0
0x180006c91  inc     ecx
0x180006c93  cmp     ecx, 6
0x180006c96  jb      short loc_180006C80
0x180006c98  mov     eax, r8d
0x180006c9b  jmp     loc_1800070A9
0x180006ca0  mov     r8d, [rax+rdx+4]
0x180006ca5  mov     eax, r8d
0x180006ca8  jmp     loc_1800070A9
0x180006cad  mov     eax, [rbp+4Fh+var_88]
0x180006cb0  mov     [rsp+0C0h+var_38], r13
0x180006cb8  mov     r13d, [rbp+4Fh+arg_20]
0x180006cbc  test    r13d, r13d
0x180006cbf  cmovz   eax, [rbp+4Fh+var_84]
0x180006cc3  cmp     r12d, eax
0x180006cc6  jb      short loc_180006CD2
0x180006cc8  mov     eax, 0C00D36B3h
0x180006ccd  jmp     loc_1800070A1
0x180006cd2  mov     [rsp+0C0h+var_30], rdi
0x180006cda  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180006ce1  movups  [rbp+4Fh+Buf1], xmm0
0x180006ce5  test    r14, r14
0x180006ce8  jz      loc_180006E0F
0x180006cee  mov     rax, [r14]
0x180006cf1  lea     r8, [rbp+4Fh+Buf1]
0x180006cf5  lea     rdx, MF_MT_SUBTYPE
0x180006cfc  mov     rcx, r14
0x180006cff  mov     rax, [rax+50h]
0x180006d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d08  mov     r8d, 10h; Size
0x180006d0e  lea     rdx, MEDIASUBTYPE_ARGB32; Buf2
0x180006d15  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x180006d19  call    memcmp_0
0x180006d1e  test    eax, eax
0x180006d20  jz      short loc_180006D8E
0x180006d22  mov     r8d, 10h; Size
0x180006d28  lea     rdx, MEDIASUBTYPE_RGB24; Buf2
0x180006d2f  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x180006d33  call    memcmp_0
0x180006d38  test    eax, eax
0x180006d3a  jz      short loc_180006D8E
0x180006d3c  mov     r8d, 10h; Size
0x180006d42  lea     rdx, MEDIASUBTYPE_RGB32; Buf2
0x180006d49  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x180006d4d  call    memcmp_0
0x180006d52  test    eax, eax
0x180006d54  jz      short loc_180006D8E
0x180006d56  mov     r8d, 10h; Size
0x180006d5c  lea     rdx, MEDIASUBTYPE_RGB555; Buf2
0x180006d63  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x180006d67  call    memcmp_0
0x180006d6c  test    eax, eax
0x180006d6e  jz      short loc_180006D8E
0x180006d70  mov     r8d, 10h; Size
0x180006d76  lea     rdx, MEDIASUBTYPE_RGB565; Buf2
0x180006d7d  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x180006d81  call    memcmp_0
0x180006d86  test    eax, eax
0x180006d88  jnz     loc_180006E0F
0x180006d8e  mov     dil, 1
0x180006d91  mov     rax, [r14]
0x180006d94  lea     rdx, [rbp+4Fh+Buf2]
0x180006d98  mov     rcx, r14
0x180006d9b  mov     rax, [rax+108h]
0x180006da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da7  mov     r8d, 10h; Size
0x180006dad  lea     rdx, [rbp+4Fh+Buf2]; Buf2
0x180006db1  lea     rcx, MEDIATYPE_Video; Buf1
0x180006db8  call    memcmp_0
0x180006dbd  test    eax, eax
0x180006dbf  lea     r8, [rbp+4Fh+var_90]
0x180006dc3  mov     rax, [r14]
0x180006dc6  lea     rdx, [rbp+4Fh+Buf1]
0x180006dca  mov     rcx, r14
0x180006dcd  mov     rax, [rax+120h]
0x180006dd4  jnz     loc_180006FC8
0x180006dda  movups  xmm0, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x180006de1  movaps  [rbp+4Fh+Buf1], xmm0
0x180006de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dea  mov     ebx, eax
0x180006dec  test    eax, eax
0x180006dee  js      loc_180006E97
0x180006df4  mov     rax, [rsi]
0x180006df7  mov     r9d, r15d
0x180006dfa  mov     r8, [rbp+4Fh+var_90]
0x180006dfe  mov     edx, r12d
0x180006e01  mov     rcx, rsi
0x180006e04  test    r13d, r13d
0x180006e07  jnz     short loc_180006E5F
0x180006e09  mov     rax, [rax+40h]
0x180006e0d  jmp     short loc_180006E63
0x180006e0f  mov     rdx, r14
0x180006e12  call    ?ConvertMFRGBFormatToDMORGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z; CMFTtoDMOImpl<CMFTtoDMO>::ConvertMFRGBFormatToDMORGBFormat(IMFMediaType *)
0x180006e17  xor     dil, dil
0x180006e1a  test    r14, r14
0x180006e1d  jnz     loc_180006D91
0x180006e23  mov     rax, [rsi]
0x180006e26  or      r15d, 2
0x180006e2a  xor     r8d, r8d
0x180006e2d  mov     r9d, r15d
0x180006e30  mov     edx, r12d
0x180006e33  mov     rcx, rsi
0x180006e36  test    r13d, r13d
0x180006e39  jnz     short loc_180006E4D
0x180006e3b  mov     rax, [rax+40h]
0x180006e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e44  mov     ebx, eax
0x180006e46  mov     esi, eax
0x180006e48  jmp     loc_18000704D
0x180006e4d  mov     rax, [rax+48h]
0x180006e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e56  mov     ebx, eax
0x180006e58  mov     esi, eax
0x180006e5a  jmp     loc_18000704D
0x180006e5f  mov     rax, [rax+48h]
0x180006e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e68  movups  xmm0, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x180006e6f  mov     r8, [rbp+4Fh+var_90]
0x180006e73  lea     rdx, [rbp+4Fh+Buf1]
0x180006e77  mov     ebx, eax
0x180006e79  mov     rcx, r14
0x180006e7c  mov     rax, [r14]
0x180006e7f  movaps  [rbp+4Fh+Buf1], xmm0
0x180006e83  mov     rax, [rax+128h]
0x180006e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e8f  test    ebx, ebx
0x180006e91  jns     loc_18000702D
0x180006e97  cmp     ebx, 0C00D6D76h
0x180006e9d  jz      loc_180007029
0x180006ea3  mov     rax, [r14]
0x180006ea6  lea     r8, [rbp+4Fh+var_90]
0x180006eaa  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x180006eb1  lea     rdx, [rbp+4Fh+Buf1]
0x180006eb5  mov     rcx, r14
0x180006eb8  mov     rax, [rax+120h]
0x180006ebf  movaps  [rbp+4Fh+Buf1], xmm0
0x180006ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec8  mov     ebx, eax
0x180006eca  test    eax, eax
0x180006ecc  js      short loc_180006F21
0x180006ece  mov     rax, [rsi]
0x180006ed1  mov     r9d, r15d
0x180006ed4  mov     r8, [rbp+4Fh+var_90]
0x180006ed8  mov     edx, r12d
0x180006edb  mov     rcx, rsi
0x180006ede  test    r13d, r13d
0x180006ee1  jnz     short loc_180006EE9
0x180006ee3  mov     rax, [rax+40h]
0x180006ee7  jmp     short loc_180006EED
0x180006ee9  mov     rax, [rax+48h]
0x180006eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ef2  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x180006ef9  mov     r8, [rbp+4Fh+var_90]
0x180006efd  lea     rdx, [rbp+4Fh+Buf1]
0x180006f01  mov     ebx, eax
0x180006f03  mov     rcx, r14
0x180006f06  mov     rax, [r14]
0x180006f09  movaps  [rbp+4Fh+Buf1], xmm0
0x180006f0d  mov     rax, [rax+128h]
0x180006f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f19  test    ebx, ebx
0x180006f1b  jns     loc_18000702D
0x180006f21  cmp     ebx, 0C00D6D76h
0x180006f27  jz      loc_180007029
0x180006f2d  mov     rax, [r14]
0x180006f30  lea     r8, [rbp+4Fh+var_90]
0x180006f34  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180006f3b  lea     rdx, [rbp+4Fh+Buf1]
0x180006f3f  mov     rcx, r14
0x180006f42  mov     rax, [rax+120h]
0x180006f49  movaps  [rbp+4Fh+Buf1], xmm0
0x180006f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f52  mov     ebx, eax
0x180006f54  test    eax, eax
0x180006f56  js      short loc_180006FAB
0x180006f58  mov     rax, [rsi]
0x180006f5b  mov     r9d, r15d
0x180006f5e  mov     r8, [rbp+4Fh+var_90]
0x180006f62  mov     edx, r12d
0x180006f65  mov     rcx, rsi
0x180006f68  test    r13d, r13d
0x180006f6b  jnz     short loc_180006F73
0x180006f6d  mov     rax, [rax+40h]
0x180006f71  jmp     short loc_180006F77
0x180006f73  mov     rax, [rax+48h]
0x180006f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f7c  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180006f83  mov     r8, [rbp+4Fh+var_90]
0x180006f87  lea     rdx, [rbp+4Fh+Buf1]
0x180006f8b  mov     ebx, eax
0x180006f8d  mov     rcx, r14
0x180006f90  mov     rax, [r14]
0x180006f93  movaps  [rbp+4Fh+Buf1], xmm0
0x180006f97  mov     rax, [rax+128h]
0x180006f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa3  test    ebx, ebx
0x180006fa5  jns     loc_18000702D
0x180006fab  cmp     ebx, 0C00D6D76h
0x180006fb1  jz      short loc_180007029
0x180006fb3  mov     rax, [r14]
0x180006fb6  lea     r8, [rbp+4Fh+var_90]
0x180006fba  lea     rdx, [rbp+4Fh+Buf1]
0x180006fbe  mov     rcx, r14
0x180006fc1  mov     rax, [rax+120h]
0x180006fc8  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x180006fcf  movaps  [rbp+4Fh+Buf1], xmm0
0x180006fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd8  mov     ebx, eax
0x180006fda  test    eax, eax
0x180006fdc  js      short loc_180007046
0x180006fde  mov     rax, [rsi]
0x180006fe1  mov     r9d, r15d
0x180006fe4  mov     r8, [rbp+4Fh+var_90]
0x180006fe8  mov     edx, r12d
0x180006feb  mov     rcx, rsi
0x180006fee  test    r13d, r13d
0x180006ff1  jnz     short loc_180006FF9
0x180006ff3  mov     rax, [rax+40h]
0x180006ff7  jmp     short loc_180006FFD
0x180006ff9  mov     rax, [rax+48h]
0x180006ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007002  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x180007009  mov     r8, [rbp+4Fh+var_90]
0x18000700d  lea     rdx, [rbp+4Fh+Buf1]
0x180007011  mov     ebx, eax
0x180007013  mov     rcx, r14
0x180007016  mov     rax, [r14]
0x180007019  movaps  [rbp+4Fh+Buf1], xmm0
0x18000701d  mov     rax, [rax+128h]
0x180007024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007029  test    ebx, ebx
0x18000702b  js      short loc_180007046
0x18000702d  test    r15b, 1
0x180007031  jnz     short loc_180007046
0x180007033  mov     rax, [rbp+4Fh+var_80]
0x180007037  test    r13d, r13d
0x18000703a  jnz     short loc_180007042
0x18000703c  mov     [rax+28h], dil
0x180007040  jmp     short loc_180007046
0x180007042  mov     [rax+29h], dil
0x180007046  mov     esi, ebx
0x180007048  test    dil, dil
0x18000704b  jnz     short loc_180007055
0x18000704d  mov     rdx, r14
0x180007050  call    ?ConvertDMORGBFormatToMFRGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z; CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(IMFMediaType *)
0x180007055  mov     rdi, [rsp+0C0h+var_30]
0x18000705d  cmp     ebx, 1
0x180007060  jnz     short loc_18000706C
0x180007062  mov     esi, 0C00D36B4h
0x180007067  mov     r8d, esi
0x18000706a  jmp     short loc_180007073
0x18000706c  mov     r8d, esi
0x18000706f  test    esi, esi
0x180007071  jz      short loc_18000709E
0x180007073  xor     ecx, ecx
0x180007075  lea     rdx, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x18000707c  nop     dword ptr [rax+00h]
0x180007080  movsxd  rax, ecx
0x180007083  lea     rax, ds:0[rax*8]
  ... truncated ...
```

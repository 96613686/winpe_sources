# CImgSrvPacket::AddImageAt(CImgSrvPacket *,ulong,ushort const *,ushort const *,void *,_GUID)

- ea: `0x1800102a0`
- end: `0x180010858`
- name: `?AddImageAt@CImgSrvPacket@@QEAAKPEAV1@KPEBG1PEAXU_GUID@@@Z`
- size: `1464`
- prototype: `__int64 __fastcall(CImgSrvPacket *this, struct CImgSrvPacket *, unsigned int, const unsigned __int16 *, unsigned __int16 *, void *, struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007c28`

## callees

- `0x1800016b8`
- `0x1800101a4`
- `0x1800102a0`
- `0x180010860`
- `0x180010b84`
- `0x180010c24`
- `0x180010d70`
- `0x180010f6c`
- `0x180011090`
- `0x180016020`
- `0x180017010`

## import_xrefs

- `WdsCommonLib!WdsGetFileSize` at `0x180010675`
- `WdsCommonLib!WdsGetFileSize` at `0x180010675`
- `WdsCommonLib!GetFileNameFromPath` at `0x180010437`
- `WdsCommonLib!GetFileNameFromPath` at `0x180010437`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18001039f`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18001039f`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180010354`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800103e6`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180010465`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800104cf`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800104ee`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18001050d`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180010631`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180010354`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800103e6`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180010465`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800104cf`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800104ee`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18001050d`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180010631`
- `WdsImage!WdsImgGetPath` at `0x180010410`
- `WdsImage!WdsImgGetPath` at `0x180010410`
- `WdsImage!WdsImgGetIndex` at `0x180010537`
- `WdsImage!WdsImgGetIndex` at `0x180010537`
- `WdsImage!WdsImgGetImageFormat` at `0x18001037e`
- `WdsImage!WdsImgGetImageFormat` at `0x18001037e`
- `WdsImage!WdsImgGetName` at `0x180010561`
- `WdsImage!WdsImgGetName` at `0x180010561`
- `WdsImage!WdsImgGetResourcePath` at `0x180010495`
- `WdsImage!WdsImgGetResourcePath` at `0x180010495`
- `WdsImage!WdsImgGetXml` at `0x1800103bf`
- `WdsImage!WdsImgGetXml` at `0x1800103bf`
- `WdsImage!WdsImgGetDependantFiles` at `0x1800105be`
- `WdsImage!WdsImgGetDependantFiles` at `0x1800105be`

## string_xrefs

- `0x1800107be`: `Image Info: ImagePath=[%s], Group=[%s], Index=[%u], Format=[%u], Namespace=[%s], ContentSize=[%I64u], ExFlags=[%u], MetadataId=[{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}]`

## pseudocode

```c
__int64 __fastcall CImgSrvPacket::AddImageAt(
        CImgSrvPacket *this,
        struct CImgSrvPacket *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        void *a6,
        struct _GUID *a7)
{
  unsigned __int64 v7; // r12
  __int64 v8; // rsi
  __int64 ImageFormat; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  const unsigned __int16 *FileNameFromPath; // rax
  const unsigned __int16 *v21; // r14
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  CImgSrvPacket *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned __int64 v39; // rax
  unsigned __int16 **v40; // rdx
  unsigned int i; // edi
  unsigned int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdi
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rax
  __int128 v51; // xmm0
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  unsigned __int16 **v59; // [rsp+20h] [rbp-100h]
  int v60; // [rsp+A0h] [rbp-80h] BYREF
  unsigned int v61; // [rsp+A4h] [rbp-7Ch] BYREF
  unsigned int v62; // [rsp+A8h] [rbp-78h]
  unsigned int v63; // [rsp+ACh] [rbp-74h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-70h] BYREF
  __int64 v65; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v66; // [rsp+C0h] [rbp-60h] BYREF
  const unsigned __int16 *v67; // [rsp+C8h] [rbp-58h] BYREF
  _WORD *v68; // [rsp+D0h] [rbp-50h] BYREF
  CImgSrvPacket *v69; // [rsp+D8h] [rbp-48h]
  __int64 v70; // [rsp+E0h] [rbp-40h] BYREF
  CImgSrvPacket *v71; // [rsp+E8h] [rbp-38h]
  __int128 v72; // [rsp+F0h] [rbp-30h] BYREF
  __int128 v73; // [rsp+100h] [rbp-20h] BYREF
  unsigned int v74; // [rsp+110h] [rbp-10h] BYREF
  unsigned __int16 *v75; // [rsp+118h] [rbp-8h] BYREF
  unsigned __int64 v76; // [rsp+120h] [rbp+0h]
  int v77; // [rsp+128h] [rbp+8h]
  unsigned __int16 **v78; // [rsp+130h] [rbp+10h]
  __int64 v79; // [rsp+138h] [rbp+18h]
  int v80; // [rsp+140h] [rbp+20h]
  __int128 v81; // [rsp+144h] [rbp+24h]

  v7 = 0;
  v67 = 0;
  v8 = -1;
  v64 = 0;
  v68 = 0;
  v70 = 0;
  v65 = 0;
  v61 = 0;
  v66 = 0;
  v63 = 0;
  v60 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v62 = a3;
  v71 = a2;
  v69 = this;
  do
    ++v8;
  while ( a4[v8] );
  ImageFormat = DuplicateStringW(a5, (unsigned __int16 **)&v73 + 1);
  if ( (unsigned int)ElValidateWin32_3(ImageFormat, v10, v11, 145) )
    goto LABEL_45;
  ImageFormat = (unsigned int)WdsImgGetImageFormat(a6, &v60);
  if ( (int)ElValidateHr_4(ImageFormat, v12, v13, 151) < 0 )
    goto LABEL_5;
  v77 = v60;
  LODWORD(ImageFormat) = WdsImgGetXml(a6, &v67);
  if ( (int)ElValidateHr_4((unsigned int)ImageFormat, v14, v15, 159) < 0 )
    goto LABEL_5;
  ImageFormat = DuplicateStringW(v67, (unsigned __int16 **)&v72);
  if ( (unsigned int)ElValidateWin32_3(ImageFormat, v16, v17, 166) )
    goto LABEL_45;
  ImageFormat = (unsigned int)WdsImgGetPath(a6, &v64);
  if ( (int)ElValidateHr_4(ImageFormat, v18, v19, 172) < 0 )
    goto LABEL_5;
  FileNameFromPath = (const unsigned __int16 *)GetFileNameFromPath(v64);
  v21 = FileNameFromPath;
  if ( !FileNameFromPath || !*FileNameFromPath )
  {
    LODWORD(ImageFormat) = 123;
    goto LABEL_45;
  }
  ImageFormat = DuplicateStringW((const unsigned __int16 *)(v64 + 2 * v8), (unsigned __int16 **)&v72 + 1);
  if ( !(unsigned int)ElValidateWin32_3(ImageFormat, v22, v23, 192) )
  {
    if ( v60 == 2 )
    {
      LODWORD(ImageFormat) = WdsImgGetResourcePath(a6, &v68);
      if ( (int)ElValidateHr_4((unsigned int)ImageFormat, v24, v25, 200) < 0 )
        goto LABEL_5;
      if ( v68 && *v68 )
      {
        v26 = DuplicateStringW(&v68[v8], (unsigned __int16 **)&v73);
        v29 = 211;
      }
      else
      {
        v26 = DuplicateStringW(&pszSrch, (unsigned __int16 **)&v73);
        v29 = 216;
      }
    }
    else
    {
      v26 = DuplicateStringW(&pszSrch, (unsigned __int16 **)&v73);
      v29 = 222;
    }
    LODWORD(ImageFormat) = v26;
    if ( (unsigned int)ElValidateWin32_3(v26, v27, v28, v29) )
      goto LABEL_45;
    ImageFormat = (unsigned int)WdsImgGetIndex(a6, &v74);
    if ( (int)ElValidateHr_4(ImageFormat, v30, v31, 229) >= 0 )
    {
      LODWORD(ImageFormat) = WdsImgGetName(a6, &v70);
      if ( (int)ElValidateHr_4((unsigned int)ImageFormat, v32, v33, 235) >= 0 )
      {
        ImageFormat = CImgSrvPacket::GetNamespaceName(v34, a5, v21, v74, &v75);
        if ( (unsigned int)ElValidateWin32_3(ImageFormat, v35, v36, 244) )
          goto LABEL_45;
        LODWORD(ImageFormat) = WdsImgGetDependantFiles(a6, &v65, &v61);
        if ( (int)ElValidateHr_4((unsigned int)ImageFormat, v37, v38, 253) >= 0 )
        {
          LODWORD(ImageFormat) = 8;
          v39 = 8LL * v61;
          if ( !is_mul_ok(v61, 8u) )
            v39 = -1;
          v78 = (unsigned __int16 **)operator new[](v39, (const struct std::nothrow_t *)&std::nothrow);
          v40 = v78;
          if ( v78 )
          {
            for ( i = 0; ; ++i )
            {
              v42 = v61;
              if ( i >= v61 )
                break;
              ImageFormat = DuplicateStringW((const unsigned __int16 *)(*(_QWORD *)(v65 + 8LL * i) + 2 * v8), &v40[i]);
              if ( (unsigned int)ElValidateWin32_3(ImageFormat, v43, v44, 267) )
                goto LABEL_45;
              v40 = v78;
            }
            LODWORD(v79) = v61;
            v45 = 0;
            v76 = 0;
            while ( (unsigned int)v45 < v42 )
            {
              ImageFormat = (unsigned int)WdsGetFileSize(*(_QWORD *)(v65 + 8 * v45), &v66);
              if ( (unsigned int)ElValidateWin32_3(ImageFormat, v46, v47, 279) )
                goto LABEL_45;
              v50 = -1;
              if ( v76 + v66 >= v76 )
                v50 = v76 + v66;
              LODWORD(ImageFormat) = v76 + v66 < v76 ? 0x80070216 : 0;
              v76 = v50;
              if ( (int)ElValidateHr_4((unsigned int)ImageFormat, v48, v49, 285) < 0 )
                goto LABEL_5;
              v42 = v79;
              v45 = (unsigned int)(v45 + 1);
              v7 = v76;
            }
            v51 = (__int128)*a7;
            v80 = 1;
            v81 = v51;
            if ( g_ErrLibTraceFunction )
            {
              LODWORD(v59) = v77;
              g_ErrLibTraceFunction(
                L"Image Info: ImagePath=[%s], Group=[%s], Index=[%u], Format=[%u], Namespace=[%s], ContentSize=[%I64u], Ex"
                 "Flags=[%u], MetadataId=[{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}]",
                *((_QWORD *)&v72 + 1),
                *((_QWORD *)&v73 + 1),
                v74,
                v59,
                v75,
                v7,
                HIDWORD(v79),
                (_DWORD)v81,
                WORD2(v81),
                WORD3(v81),
                BYTE8(v81),
                BYTE9(v81),
                BYTE10(v81),
                BYTE11(v81),
                BYTE12(v81),
                BYTE13(v81),
                BYTE14(v81),
                HIBYTE(*((_QWORD *)&v81 + 1)));
            }
            ImageFormat = CImgSrvPacket::GetClientCapabilities(v71, &v63);
            if ( !(unsigned int)ElValidateWin32_3(ImageFormat, v52, v53, 312) )
            {
              if ( (v63 & 1) != 0 )
              {
                ImageFormat = CImgSrvPacket::AddImageAt_v2(v69, v62, (struct _IMGSRV_IMAGE *)&v72);
                ElValidateWin32_3(ImageFormat, v54, v55, 317);
              }
              else
              {
                ImageFormat = (unsigned int)CImgSrvPacket::AddImageAt_v1(
                                              (void **)v69,
                                              v62,
                                              (struct _IMGSRV_IMAGE *)&v72);
                ElValidateWin32_3(ImageFormat, v56, v57, 322);
              }
            }
          }
          goto LABEL_45;
        }
      }
    }
LABEL_5:
    LODWORD(ImageFormat) = WIN32_FROM_HRESULT(ImageFormat);
  }
LABEL_45:
  _IMGSRV_IMAGE::~_IMGSRV_IMAGE((_IMGSRV_IMAGE *)&v72);
  return (unsigned int)ImageFormat;
}

```

## disassembly

```asm
0x1800102a0  push    rbp
0x1800102a2  push    rbx
0x1800102a3  push    rsi
0x1800102a4  push    rdi
0x1800102a5  push    r12
0x1800102a7  push    r13
0x1800102a9  push    r14
0x1800102ab  push    r15
0x1800102ad  lea     rbp, [rsp-58h]
0x1800102b2  sub     rsp, 178h
0x1800102b9  mov     rax, cs:__security_cookie
0x1800102c0  xor     rax, rsp
0x1800102c3  mov     [rbp+90h+var_50], rax
0x1800102c7  mov     r15, [rbp+90h+arg_20]
0x1800102ce  xor     r12d, r12d
0x1800102d1  mov     rdi, [rbp+90h+arg_28]
0x1800102d8  xorps   xmm0, xmm0
0x1800102db  mov     r13, [rbp+90h+arg_30]
0x1800102e2  xorps   xmm1, xmm1
0x1800102e5  mov     [rbp+90h+var_E8], r12
0x1800102e9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800102ed  mov     [rbp+90h+var_100], r12
0x1800102f1  mov     [rbp+90h+var_E0], r12
0x1800102f5  mov     [rbp+90h+var_D0], r12
0x1800102f9  mov     [rbp+90h+var_F8], r12
0x1800102fd  mov     [rbp+90h+var_10C], r12d
0x180010301  mov     [rbp+90h+var_F0], r12
0x180010305  mov     [rbp+90h+var_104], r12d
0x180010309  mov     [rbp+90h+var_110], r12d
0x18001030d  movdqa  [rbp+90h+var_C0], xmm0
0x180010312  movdqa  [rbp+90h+var_B0], xmm1
0x180010317  mov     [rbp+90h+var_A0], r12d
0x18001031b  mov     [rbp+90h+var_98], r12
0x18001031f  mov     [rbp+90h+var_90], r12
0x180010323  mov     [rbp+90h+var_88], r12d
0x180010327  mov     [rbp+90h+var_80], r12
0x18001032b  mov     [rbp+90h+var_78], r12
0x18001032f  mov     [rbp+90h+var_70], r12d
0x180010333  movups  [rbp+90h+var_6C], xmm0
0x180010337  mov     [rbp+90h+var_108], r8d
0x18001033b  mov     [rbp+90h+var_C8], rdx
0x18001033f  mov     [rbp+90h+var_D8], rcx
0x180010343  inc     rsi
0x180010346  cmp     [r9+rsi*2], r12w
0x18001034b  jnz     short loc_180010343
0x18001034d  lea     rdx, [rbp+90h+var_B0+8]
0x180010351  mov     rcx, r15
0x180010354  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18001035b  nop     dword ptr [rax+rax+00h]
0x180010360  mov     ecx, eax
0x180010362  mov     r9d, 91h
0x180010368  mov     ebx, eax
0x18001036a  call    ElValidateWin32_3
0x18001036f  test    eax, eax
0x180010371  jnz     loc_18001082C
0x180010377  lea     rdx, [rbp+90h+var_110]
0x18001037b  mov     rcx, rdi
0x18001037e  call    cs:__imp_WdsImgGetImageFormat
0x180010385  nop     dword ptr [rax+rax+00h]
0x18001038a  mov     ecx, eax
0x18001038c  mov     r9d, 97h
0x180010392  mov     ebx, eax
0x180010394  call    ElValidateHr_4
0x180010399  test    eax, eax
0x18001039b  jns     short loc_1800103B2
0x18001039d  mov     ecx, ebx
0x18001039f  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800103a6  nop     dword ptr [rax+rax+00h]
0x1800103ab  mov     ebx, eax
0x1800103ad  jmp     loc_18001082C
0x1800103b2  mov     eax, [rbp+90h+var_110]
0x1800103b5  lea     rdx, [rbp+90h+var_E8]
0x1800103b9  mov     rcx, rdi
0x1800103bc  mov     [rbp+90h+var_88], eax
0x1800103bf  call    cs:__imp_WdsImgGetXml
0x1800103c6  nop     dword ptr [rax+rax+00h]
0x1800103cb  mov     ecx, eax
0x1800103cd  mov     r9d, 9Fh
0x1800103d3  mov     ebx, eax
0x1800103d5  call    ElValidateHr_4
0x1800103da  test    eax, eax
0x1800103dc  js      short loc_18001039D
0x1800103de  mov     rcx, [rbp+90h+var_E8]
0x1800103e2  lea     rdx, [rbp+90h+var_C0]
0x1800103e6  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800103ed  nop     dword ptr [rax+rax+00h]
0x1800103f2  mov     ecx, eax
0x1800103f4  mov     r9d, 0A6h
0x1800103fa  mov     ebx, eax
0x1800103fc  call    ElValidateWin32_3
0x180010401  test    eax, eax
0x180010403  jnz     loc_18001082C
0x180010409  lea     rdx, [rbp+90h+var_100]
0x18001040d  mov     rcx, rdi
0x180010410  call    cs:__imp_WdsImgGetPath
0x180010417  nop     dword ptr [rax+rax+00h]
0x18001041c  mov     ecx, eax
0x18001041e  mov     r9d, 0ACh
0x180010424  mov     ebx, eax
0x180010426  call    ElValidateHr_4
0x18001042b  test    eax, eax
0x18001042d  js      loc_18001039D
0x180010433  mov     rcx, [rbp+90h+var_100]
0x180010437  call    cs:__imp_GetFileNameFromPath
0x18001043e  nop     dword ptr [rax+rax+00h]
0x180010443  mov     r14, rax
0x180010446  test    rax, rax
0x180010449  jz      loc_180010827
0x18001044f  cmp     [rax], r12w
0x180010453  jz      loc_180010827
0x180010459  mov     rcx, [rbp+90h+var_100]
0x18001045d  lea     rdx, [rbp+90h+var_C0+8]
0x180010461  lea     rcx, [rcx+rsi*2]
0x180010465  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18001046c  nop     dword ptr [rax+rax+00h]
0x180010471  mov     ecx, eax
0x180010473  mov     r9d, 0C0h
0x180010479  mov     ebx, eax
0x18001047b  call    ElValidateWin32_3
0x180010480  test    eax, eax
0x180010482  jnz     loc_18001082C
0x180010488  cmp     [rbp+90h+var_110], 2
0x18001048c  jnz     short loc_180010502
0x18001048e  lea     rdx, [rbp+90h+var_E0]
0x180010492  mov     rcx, rdi
0x180010495  call    cs:__imp_WdsImgGetResourcePath
0x18001049c  nop     dword ptr [rax+rax+00h]
0x1800104a1  mov     ecx, eax
0x1800104a3  mov     r9d, 0C8h
0x1800104a9  mov     ebx, eax
0x1800104ab  call    ElValidateHr_4
0x1800104b0  test    eax, eax
0x1800104b2  js      loc_18001039D
0x1800104b8  mov     rax, [rbp+90h+var_E0]
0x1800104bc  test    rax, rax
0x1800104bf  jz      short loc_1800104E3
0x1800104c1  cmp     [rax], r12w
0x1800104c5  jz      short loc_1800104E3
0x1800104c7  lea     rcx, [rax+rsi*2]
0x1800104cb  lea     rdx, [rbp+90h+var_B0]
0x1800104cf  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800104d6  nop     dword ptr [rax+rax+00h]
0x1800104db  mov     r9d, 0D3h
0x1800104e1  jmp     short loc_18001051F
0x1800104e3  lea     rdx, [rbp+90h+var_B0]
0x1800104e7  lea     rcx, pszSrch
0x1800104ee  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800104f5  nop     dword ptr [rax+rax+00h]
0x1800104fa  mov     r9d, 0D8h
0x180010500  jmp     short loc_18001051F
0x180010502  lea     rdx, [rbp+90h+var_B0]
0x180010506  lea     rcx, pszSrch
0x18001050d  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180010514  nop     dword ptr [rax+rax+00h]
0x180010519  mov     r9d, 0DEh
0x18001051f  mov     ecx, eax
0x180010521  mov     ebx, eax
0x180010523  call    ElValidateWin32_3
0x180010528  test    eax, eax
0x18001052a  jnz     loc_18001082C
0x180010530  lea     rdx, [rbp+90h+var_A0]
0x180010534  mov     rcx, rdi
0x180010537  call    cs:__imp_WdsImgGetIndex
0x18001053e  nop     dword ptr [rax+rax+00h]
0x180010543  mov     ecx, eax
0x180010545  mov     r9d, 0E5h
0x18001054b  mov     ebx, eax
0x18001054d  call    ElValidateHr_4
0x180010552  test    eax, eax
0x180010554  js      loc_18001039D
0x18001055a  lea     rdx, [rbp+90h+var_D0]
0x18001055e  mov     rcx, rdi
0x180010561  call    cs:__imp_WdsImgGetName
0x180010568  nop     dword ptr [rax+rax+00h]
0x18001056d  mov     ecx, eax
0x18001056f  mov     r9d, 0EBh
0x180010575  mov     ebx, eax
0x180010577  call    ElValidateHr_4
0x18001057c  test    eax, eax
0x18001057e  js      loc_18001039D
0x180010584  mov     r9d, [rbp+90h+var_A0]; unsigned int
0x180010588  lea     rax, [rbp+90h+var_98]
0x18001058c  mov     r8, r14; unsigned __int16 *
0x18001058f  mov     [rsp+1B0h+var_190], rax; unsigned __int16 **
0x180010594  mov     rdx, r15; unsigned __int16 *
0x180010597  call    ?GetNamespaceName@CImgSrvPacket@@AEAAKPEBG0KPEAPEAG@Z; CImgSrvPacket::GetNamespaceName(ushort const *,ushort const *,ulong,ushort * *)
0x18001059c  mov     r9d, 0F4h
0x1800105a2  mov     ecx, eax
0x1800105a4  mov     ebx, eax
0x1800105a6  call    ElValidateWin32_3
0x1800105ab  test    eax, eax
0x1800105ad  jnz     loc_18001082C
0x1800105b3  lea     r8, [rbp+90h+var_10C]
0x1800105b7  mov     rcx, rdi
0x1800105ba  lea     rdx, [rbp+90h+var_F8]
0x1800105be  call    cs:__imp_WdsImgGetDependantFiles
0x1800105c5  nop     dword ptr [rax+rax+00h]
0x1800105ca  mov     ecx, eax
0x1800105cc  mov     r9d, 0FDh
0x1800105d2  mov     ebx, eax
0x1800105d4  call    ElValidateHr_4
0x1800105d9  test    eax, eax
0x1800105db  js      loc_18001039D
0x1800105e1  mov     ecx, [rbp+90h+var_10C]
0x1800105e4  mov     ebx, 8
0x1800105e9  mov     eax, ebx
0x1800105eb  mul     rcx
0x1800105ee  lea     r14, [rbx-9]
0x1800105f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800105f9  cmovo   rax, r14
0x1800105fd  mov     rcx, rax; unsigned __int64
0x180010600  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010605  mov     [rbp+90h+var_80], rax
0x180010609  mov     rdx, rax
0x18001060c  test    rax, rax
0x18001060f  jz      loc_18001082C
0x180010615  mov     edi, r12d
0x180010618  mov     eax, [rbp+90h+var_10C]
0x18001061b  cmp     edi, eax
0x18001061d  jnb     short loc_18001065C
0x18001061f  mov     rax, [rbp+90h+var_F8]
0x180010623  mov     ecx, edi
0x180010625  lea     rdx, [rdx+rcx*8]
0x180010629  mov     rcx, [rax+rcx*8]
0x18001062d  lea     rcx, [rcx+rsi*2]
0x180010631  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180010638  nop     dword ptr [rax+rax+00h]
0x18001063d  mov     ecx, eax
0x18001063f  mov     r9d, 10Bh
0x180010645  mov     ebx, eax
0x180010647  call    ElValidateWin32_3
0x18001064c  test    eax, eax
0x18001064e  jnz     loc_18001082C
0x180010654  mov     rdx, [rbp+90h+var_80]
0x180010658  inc     edi
0x18001065a  jmp     short loc_180010618
0x18001065c  mov     dword ptr [rbp+90h+var_78], eax
0x18001065f  xor     edi, edi
0x180010661  mov     [rbp+90h+var_90], r12
0x180010665  cmp     edi, eax
0x180010667  jnb     short loc_1800106D7
0x180010669  mov     rcx, [rbp+90h+var_F8]
0x18001066d  lea     rdx, [rbp+90h+var_F0]
0x180010671  mov     rcx, [rcx+rdi*8]
0x180010675  call    cs:__imp_WdsGetFileSize
0x18001067c  nop     dword ptr [rax+rax+00h]
0x180010681  mov     ecx, eax
0x180010683  mov     r9d, 117h
0x180010689  mov     ebx, eax
0x18001068b  call    ElValidateWin32_3
0x180010690  test    eax, eax
0x180010692  jnz     loc_18001082C
0x180010698  mov     rcx, [rbp+90h+var_F0]
0x18001069c  mov     rax, r14
0x18001069f  add     rcx, [rbp+90h+var_90]
0x1800106a3  mov     r9d, 11Dh
0x1800106a9  cmp     rcx, [rbp+90h+var_90]
0x1800106ad  cmovnb  rax, rcx
0x1800106b1  sbb     ebx, ebx
0x1800106b3  and     ebx, 80070216h
0x1800106b9  mov     [rbp+90h+var_90], rax
0x1800106bd  mov     ecx, ebx
0x1800106bf  call    ElValidateHr_4
0x1800106c4  test    eax, eax
0x1800106c6  js      loc_18001039D
0x1800106cc  mov     eax, dword ptr [rbp+90h+var_78]
0x1800106cf  inc     edi
0x1800106d1  mov     r12, [rbp+90h+var_90]
0x1800106d5  jmp     short loc_180010665
0x1800106d7  movaps  xmm0, xmmword ptr [r13+0]
0x1800106dc  mov     r13, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800106e3  mov     [rbp+90h+var_70], 1
0x1800106ea  movdqu  [rbp+90h+var_6C], xmm0
0x1800106ef  test    r13, r13
0x1800106f2  jz      loc_1800107CA
0x1800106f8  mov     rcx, qword ptr [rbp+90h+var_6C+8]
0x1800106fc  mov     r11, qword ptr [rbp+90h+var_6C]
0x180010700  mov     rax, rcx
0x180010703  shr     rax, 30h
0x180010707  mov     r15, rcx
0x18001070a  movzx   r14d, al
0x18001070e  mov     rdx, r11
0x180010711  movzx   r8d, cl
0x180010715  mov     rax, rcx
0x180010718  shr     rax, 28h
0x18001071c  movzx   esi, al
0x18001071f  mov     rax, rcx
0x180010722  shr     rax, 20h
0x180010726  movzx   edi, al
0x180010729  mov     eax, ecx
0x18001072b  shr     rax, 18h
0x18001072f  movzx   ebx, al
0x180010732  mov     eax, ecx
0x180010734  shr     rax, 10h
0x180010738  movzx   r10d, al
0x18001073c  mov     eax, ecx
0x18001073e  shr     rax, 8
0x180010742  movzx   r9d, al
0x180010746  mov     rax, r11
0x180010749  shr     rax, 20h
  ... truncated ...
```

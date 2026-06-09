# CImageCache::EnumImages(void *,ushort const *)

- ea: `0x180008494`
- end: `0x180008913`
- name: `?EnumImages@CImageCache@@AEAAKPEAXPEBG@Z`
- size: `1151`
- prototype: `__int64 __fastcall(CImageCache *this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180008364`

## callees

- `0x1800015d8`
- `0x180002878`
- `0x180008494`
- `0x1800092ec`
- `0x1800096e8`
- `0x18000ad88`
- `0x18000aeac`
- `0x180017010`

## import_xrefs

- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x1800088ad`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x1800088f2`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x1800088ad`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x1800088f2`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800085a3`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800086ae`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180008709`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800085a3`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800086ae`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180008709`
- `WdsImage!WdsImgGetHandleFromFindHandle` at `0x1800085d3`
- `WdsImage!WdsImgGetHandleFromFindHandle` at `0x1800085d3`
- `WdsImage!WdsImgGetSecurity` at `0x1800086dd`
- `WdsImage!WdsImgGetSecurity` at `0x1800086dd`
- `WdsImage!WdsImgGetEnabled` at `0x180008657`
- `WdsImage!WdsImgGetEnabled` at `0x180008657`
- `WdsImage!WdsImgGetIndex` at `0x18000862b`
- `WdsImage!WdsImgGetIndex` at `0x18000862b`
- `WdsImage!WdsImgGetBootIndex` at `0x18000852f`
- `WdsImage!WdsImgGetBootIndex` at `0x18000852f`
- `WdsImage!WdsImgGetImageFormat` at `0x1800085ff`
- `WdsImage!WdsImgGetImageFormat` at `0x1800085ff`
- `WdsImage!WdsImgGetName` at `0x180008682`
- `WdsImage!WdsImgGetName` at `0x180008682`
- `WdsImage!WdsImgFindFirstImage` at `0x1800084e7`
- `WdsImage!WdsImgFindFirstImage` at `0x1800084e7`
- `WdsImage!WdsImgFindNextImage` at `0x18000887d`
- `WdsImage!WdsImgFindNextImage` at `0x18000887d`
- `WdsImage!WdsImgClose` at `0x1800088c5`
- `WdsImage!WdsImgClose` at `0x1800088c5`

## string_xrefs

- `0x180008520`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000886b`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000885b`: `Image Cache: Group=[%s], Image=[%s], Index=[%u], Type=[%u] Priority=[%u] GUID={%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X} (%s), Enabled=[%u].`

## pseudocode

```c
__int64 __fastcall CImageCache::EnumImages(CImageCache *this, void *a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // rsi
  CImageCache *v4; // rdi
  __int64 inserted; // r13
  unsigned int FirstImage; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 BootIndex; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned __int16 **v12; // rax
  unsigned __int16 **v13; // r12
  __int64 v14; // rdx
  unsigned int v15; // edx
  __int64 Handle; // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  const wchar_t *v33; // r8
  int NextImage; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v38; // [rsp+28h] [rbp-79h]
  __int64 v39; // [rsp+30h] [rbp-71h]
  __int64 v40; // [rsp+38h] [rbp-69h]
  __int64 v41; // [rsp+40h] [rbp-61h]
  __int64 v42; // [rsp+48h] [rbp-59h]
  __int64 v43; // [rsp+50h] [rbp-51h]
  __int64 v44; // [rsp+58h] [rbp-49h]
  __int64 v45; // [rsp+60h] [rbp-41h]
  __int64 v46; // [rsp+68h] [rbp-39h]
  __int64 v47; // [rsp+70h] [rbp-31h]
  __int64 v48; // [rsp+78h] [rbp-29h]
  __int64 v49; // [rsp+80h] [rbp-21h]
  __int64 v50; // [rsp+88h] [rbp-19h]
  __int64 v51; // [rsp+98h] [rbp-9h]
  void *v52; // [rsp+A8h] [rbp+7h] BYREF
  const unsigned __int16 *v53; // [rsp+B0h] [rbp+Fh] BYREF
  const unsigned __int16 *v54; // [rsp+B8h] [rbp+17h] BYREF
  int v57; // [rsp+120h] [rbp+7Fh] BYREF

  v53 = 0;
  v3 = a3;
  v54 = 0;
  v4 = this;
  v57 = 0;
  v52 = 0;
  LODWORD(inserted) = 0;
  FirstImage = WdsImgFindFirstImage(a2, 0, 128, &v52);
  LODWORD(BootIndex) = FirstImage;
  if ( FirstImage != -1056833022 && FirstImage != -1056833016 )
  {
    if ( (int)ElValidateHr_0(FirstImage, v7, v8, 1095) >= 0 )
    {
      while ( 1 )
      {
        BootIndex = (unsigned int)WdsImgGetBootIndex(v52, &v57);
        if ( (int)ElValidateHr_0(BootIndex, v10, v11, 1101) < 0 )
          break;
        if ( !v57 )
        {
          v12 = (unsigned __int16 **)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
          v13 = v12;
          if ( !v12 )
          {
            LODWORD(inserted) = 8;
            goto LABEL_27;
          }
          v12[4] = 0;
          v12[5] = 0;
          *v12 = 0;
          v12[2] = 0;
          v12[3] = 0;
          v12[1] = 0;
          *((_OWORD *)v12 + 3) = 0;
          *((_DWORD *)v12 + 16) = 0;
          inserted = DuplicateStringW(v3, v12);
          if ( (unsigned int)ElValidateWin32_0(
                               inserted,
                               v14,
                               "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                               1112) )
            goto LABEL_31;
          Handle = (unsigned int)WdsImgGetHandleFromFindHandle(v52, v13 + 1);
          if ( (int)ElValidateHr_0(Handle, v17, v18, 1115) < 0 )
            goto LABEL_30;
          Handle = (unsigned int)WdsImgGetImageFormat(v52, v13 + 4);
          if ( (int)ElValidateHr_0(Handle, v19, v20, 1118) < 0 )
            goto LABEL_30;
          Handle = (unsigned int)WdsImgGetIndex(v52, (char *)v13 + 36);
          if ( (int)ElValidateHr_0(Handle, v21, v22, 1121) < 0 )
            goto LABEL_30;
          Handle = (unsigned int)WdsImgGetEnabled(v52, v13 + 5);
          if ( (int)ElValidateHr_0(Handle, v23, v24, 1124) < 0 )
            goto LABEL_30;
          Handle = (unsigned int)WdsImgGetName(v52, &v53);
          if ( (int)ElValidateHr_0(Handle, v25, v26, 1127) < 0 )
            goto LABEL_30;
          inserted = DuplicateStringW(v53, v13 + 2);
          if ( (unsigned int)ElValidateWin32_0(
                               inserted,
                               v27,
                               "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                               1130) )
            goto LABEL_31;
          Handle = (unsigned int)WdsImgGetSecurity(v52, &v54);
          if ( (int)ElValidateHr_0(Handle, v28, v29, 1133) < 0 )
          {
LABEL_30:
            LODWORD(inserted) = WIN32_FROM_HRESULT(Handle);
LABEL_31:
            CImageCache::Image::`scalar deleting destructor'((CImageCache::Image *)v13, v15);
            goto LABEL_27;
          }
          inserted = DuplicateStringW(v54, v13 + 3);
          if ( (unsigned int)ElValidateWin32_0(
                               inserted,
                               v30,
                               "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                               1136) )
            goto LABEL_31;
          inserted = CImageCache::RegisterImageMetadata(v4, v52, (struct Image *)v13);
          if ( (unsigned int)ElValidateWin32_0(
                               inserted,
                               v31,
                               "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                               1139) )
            goto LABEL_31;
          inserted = CImageCache::InsertImageByPriorityOrder(v4, (struct Image *)v13);
          if ( (unsigned int)ElValidateWin32_0(
                               inserted,
                               v32,
                               "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                               1142) )
            goto LABEL_31;
          if ( g_ErrLibTraceFunction )
          {
            v33 = L"Present";
            if ( !*((_DWORD *)v13 + 11) )
              v33 = L"Not Present";
            LODWORD(v51) = *((_DWORD *)v13 + 10) != 0;
            LODWORD(v50) = *((unsigned __int8 *)v13 + 63);
            LODWORD(v49) = *((unsigned __int8 *)v13 + 62);
            LODWORD(v48) = *((unsigned __int8 *)v13 + 61);
            LODWORD(v47) = *((unsigned __int8 *)v13 + 60);
            LODWORD(v46) = *((unsigned __int8 *)v13 + 59);
            LODWORD(v45) = *((unsigned __int8 *)v13 + 58);
            LODWORD(v44) = *((unsigned __int8 *)v13 + 57);
            LODWORD(v43) = *((unsigned __int8 *)v13 + 56);
            LODWORD(v42) = *((unsigned __int16 *)v13 + 27);
            LODWORD(v41) = *((unsigned __int16 *)v13 + 26);
            LODWORD(v40) = *((_DWORD *)v13 + 12);
            LODWORD(v39) = *((_DWORD *)v13 + 16);
            LODWORD(v38) = *((_DWORD *)v13 + 8);
            g_ErrLibTraceFunction(
              L"Image Cache: Group=[%s], Image=[%s], Index=[%u], Type=[%u] Priority=[%u] GUID={%08X-%04X-%04X-%02X%02X-%02"
               "X%02X%02X%02X%02X%02X} (%s), Enabled=[%u].",
              *v13,
              v13[2],
              *((unsigned int *)v13 + 9),
              v38,
              v39,
              v40,
              v41,
              v42,
              v43,
              v44,
              v45,
              v46,
              v47,
              v48,
              v49,
              v50,
              v33,
              v51);
            v4 = this;
          }
          v3 = a3;
        }
        NextImage = WdsImgFindNextImage(v52);
        LODWORD(BootIndex) = NextImage;
        if ( NextImage < 0 )
        {
          if ( NextImage == -1056833021 || (int)ElValidateHr_0((unsigned int)NextImage, v35, v36, 1160) >= 0 )
            goto LABEL_27;
          break;
        }
      }
    }
    LODWORD(inserted) = WIN32_FROM_HRESULT(BootIndex);
  }
LABEL_27:
  if ( v52 )
    WdsImgClose();
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180008494  mov     rax, rsp
0x180008497  mov     [rax+10h], rbx
0x18000849b  mov     [rax+18h], r8
0x18000849f  mov     [rax+8], rcx
0x1800084a3  push    rbp
0x1800084a4  push    rsi
0x1800084a5  push    rdi
0x1800084a6  push    r12
0x1800084a8  push    r13
0x1800084aa  push    r14
0x1800084ac  push    r15
0x1800084ae  lea     rbp, [rax-5Fh]
0x1800084b2  sub     rsp, 0C0h
0x1800084b9  xor     r14d, r14d
0x1800084bc  lea     r9, [rbp+57h+var_50]
0x1800084c0  mov     rax, rdx
0x1800084c3  mov     [rbp+57h+var_48], r14
0x1800084c7  mov     rsi, r8
0x1800084ca  mov     [rbp+57h+var_40], r14
0x1800084ce  mov     rdi, rcx
0x1800084d1  mov     [rbp+57h+arg_18], r14d
0x1800084d5  mov     rcx, rax
0x1800084d8  mov     [rbp+57h+var_50], r14
0x1800084dc  xor     edx, edx
0x1800084de  mov     r8d, 80h
0x1800084e4  mov     r13d, r14d
0x1800084e7  call    cs:__imp_WdsImgFindFirstImage
0x1800084ee  nop     dword ptr [rax+rax+00h]
0x1800084f3  mov     ebx, eax
0x1800084f5  cmp     eax, 0C1020202h
0x1800084fa  jz      loc_1800088BC
0x180008500  cmp     eax, 0C1020208h
0x180008505  jz      loc_1800088BC
0x18000850b  mov     r9d, 447h
0x180008511  mov     ecx, eax
0x180008513  call    ElValidateHr_0
0x180008518  test    eax, eax
0x18000851a  js      loc_1800088AB
0x180008520  lea     r15, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180008527  mov     rcx, [rbp+57h+var_50]
0x18000852b  lea     rdx, [rbp+57h+arg_18]
0x18000852f  call    cs:__imp_WdsImgGetBootIndex
0x180008536  nop     dword ptr [rax+rax+00h]
0x18000853b  mov     ecx, eax
0x18000853d  mov     r9d, 44Dh
0x180008543  mov     ebx, eax
0x180008545  call    ElValidateHr_0
0x18000854a  test    eax, eax
0x18000854c  js      loc_1800088AB
0x180008552  cmp     [rbp+57h+arg_18], r14d
0x180008556  jnz     loc_180008879
0x18000855c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008563  mov     ecx, 48h ; 'H'; unsigned __int64
0x180008568  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000856d  mov     r12, rax
0x180008570  test    rax, rax
0x180008573  jz      loc_18000890B
0x180008579  and     qword ptr [rax+20h], 0
0x18000857e  xorps   xmm0, xmm0
0x180008581  and     qword ptr [rax+28h], 0
0x180008586  mov     rdx, rax
0x180008589  mov     [rax], r14
0x18000858c  mov     rcx, rsi
0x18000858f  mov     [rax+10h], r14
0x180008593  mov     [rax+18h], r14
0x180008597  mov     [rax+8], r14
0x18000859b  movups  xmmword ptr [rax+30h], xmm0
0x18000859f  mov     [rax+40h], r14d
0x1800085a3  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800085aa  nop     dword ptr [rax+rax+00h]
0x1800085af  mov     r9d, 458h
0x1800085b5  mov     r8, r15
0x1800085b8  mov     ecx, eax
0x1800085ba  mov     r13d, eax
0x1800085bd  call    ElValidateWin32_0
0x1800085c2  test    eax, eax
0x1800085c4  jnz     loc_180008901
0x1800085ca  mov     rcx, [rbp+57h+var_50]
0x1800085ce  lea     rdx, [r12+8]
0x1800085d3  call    cs:__imp_WdsImgGetHandleFromFindHandle
0x1800085da  nop     dword ptr [rax+rax+00h]
0x1800085df  mov     ecx, eax
0x1800085e1  mov     r9d, 45Bh
0x1800085e7  mov     ebx, eax
0x1800085e9  call    ElValidateHr_0
0x1800085ee  test    eax, eax
0x1800085f0  js      loc_1800088F0
0x1800085f6  mov     rcx, [rbp+57h+var_50]
0x1800085fa  lea     rdx, [r12+20h]
0x1800085ff  call    cs:__imp_WdsImgGetImageFormat
0x180008606  nop     dword ptr [rax+rax+00h]
0x18000860b  mov     ecx, eax
0x18000860d  mov     r9d, 45Eh
0x180008613  mov     ebx, eax
0x180008615  call    ElValidateHr_0
0x18000861a  test    eax, eax
0x18000861c  js      loc_1800088F0
0x180008622  mov     rcx, [rbp+57h+var_50]
0x180008626  lea     rdx, [r12+24h]
0x18000862b  call    cs:__imp_WdsImgGetIndex
0x180008632  nop     dword ptr [rax+rax+00h]
0x180008637  mov     ecx, eax
0x180008639  mov     r9d, 461h
0x18000863f  mov     ebx, eax
0x180008641  call    ElValidateHr_0
0x180008646  test    eax, eax
0x180008648  js      loc_1800088F0
0x18000864e  mov     rcx, [rbp+57h+var_50]
0x180008652  lea     rdx, [r12+28h]
0x180008657  call    cs:__imp_WdsImgGetEnabled
0x18000865e  nop     dword ptr [rax+rax+00h]
0x180008663  mov     ecx, eax
0x180008665  mov     r9d, 464h
0x18000866b  mov     ebx, eax
0x18000866d  call    ElValidateHr_0
0x180008672  test    eax, eax
0x180008674  js      loc_1800088F0
0x18000867a  mov     rcx, [rbp+57h+var_50]
0x18000867e  lea     rdx, [rbp+57h+var_48]
0x180008682  call    cs:__imp_WdsImgGetName
0x180008689  nop     dword ptr [rax+rax+00h]
0x18000868e  mov     ecx, eax
0x180008690  mov     r9d, 467h
0x180008696  mov     ebx, eax
0x180008698  call    ElValidateHr_0
0x18000869d  test    eax, eax
0x18000869f  js      loc_1800088F0
0x1800086a5  mov     rcx, [rbp+57h+var_48]
0x1800086a9  lea     rdx, [r12+10h]
0x1800086ae  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800086b5  nop     dword ptr [rax+rax+00h]
0x1800086ba  mov     r9d, 46Ah
0x1800086c0  mov     r8, r15
0x1800086c3  mov     ecx, eax
0x1800086c5  mov     r13d, eax
0x1800086c8  call    ElValidateWin32_0
0x1800086cd  test    eax, eax
0x1800086cf  jnz     loc_180008901
0x1800086d5  mov     rcx, [rbp+57h+var_50]
0x1800086d9  lea     rdx, [rbp+57h+var_40]
0x1800086dd  call    cs:__imp_WdsImgGetSecurity
0x1800086e4  nop     dword ptr [rax+rax+00h]
0x1800086e9  mov     ecx, eax
0x1800086eb  mov     r9d, 46Dh
0x1800086f1  mov     ebx, eax
0x1800086f3  call    ElValidateHr_0
0x1800086f8  test    eax, eax
0x1800086fa  js      loc_1800088F0
0x180008700  mov     rcx, [rbp+57h+var_40]
0x180008704  lea     rdx, [r12+18h]
0x180008709  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180008710  nop     dword ptr [rax+rax+00h]
0x180008715  mov     r9d, 470h
0x18000871b  mov     r8, r15
0x18000871e  mov     ecx, eax
0x180008720  mov     r13d, eax
0x180008723  call    ElValidateWin32_0
0x180008728  test    eax, eax
0x18000872a  jnz     loc_180008901
0x180008730  mov     rdx, [rbp+57h+var_50]; void *
0x180008734  mov     r8, r12; struct Image *
0x180008737  mov     rcx, rdi; this
0x18000873a  call    ?RegisterImageMetadata@CImageCache@@AEAAKPEAXPEAUImage@1@@Z; CImageCache::RegisterImageMetadata(void *,CImageCache::Image *)
0x18000873f  mov     r9d, 473h
0x180008745  mov     r8, r15
0x180008748  mov     ecx, eax
0x18000874a  mov     r13d, eax
0x18000874d  call    ElValidateWin32_0
0x180008752  test    eax, eax
0x180008754  jnz     loc_180008901
0x18000875a  mov     rdx, r12; struct Image *
0x18000875d  mov     rcx, rdi; this
0x180008760  call    ?InsertImageByPriorityOrder@CImageCache@@AEAAKPEAUImage@1@@Z; CImageCache::InsertImageByPriorityOrder(CImageCache::Image *)
0x180008765  mov     r9d, 476h
0x18000876b  mov     r8, r15
0x18000876e  mov     ecx, eax
0x180008770  mov     r13d, eax
0x180008773  call    ElValidateWin32_0
0x180008778  test    eax, eax
0x18000877a  jnz     loc_180008901
0x180008780  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, r14; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180008787  jz      loc_180008875
0x18000878d  cmp     [r12+28h], r14d
0x180008792  lea     rax, aNotPresent; "Not Present"
0x180008799  movzx   ecx, byte ptr [r12+3Eh]
0x18000879f  lea     r8, aPresent; "Present"
0x1800087a6  movzx   edx, byte ptr [r12+3Dh]
0x1800087ac  mov     r9d, r14d
0x1800087af  movzx   r10d, byte ptr [r12+3Ch]
0x1800087b5  setnz   r9b
0x1800087b9  cmp     [r12+2Ch], r14d
0x1800087be  movzx   r11d, byte ptr [r12+3Bh]
0x1800087c4  movzx   ebx, byte ptr [r12+3Ah]
0x1800087ca  cmovz   r8, rax
0x1800087ce  movzx   eax, byte ptr [r12+3Fh]
0x1800087d4  movzx   edi, byte ptr [r12+39h]
0x1800087da  movzx   esi, byte ptr [r12+38h]
0x1800087e0  movzx   r14d, word ptr [r12+36h]
0x1800087e6  movzx   r15d, word ptr [r12+34h]
0x1800087ec  mov     [rsp+90h], r9d
0x1800087f4  mov     r9d, [r12+24h]
0x1800087f9  mov     qword ptr [rsp+0F0h+var_68], r8
0x180008801  mov     r8, [r12+10h]
0x180008806  mov     dword ptr [rsp+0F0h+var_70], eax
0x18000880d  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180008814  mov     dword ptr [rsp+0F0h+var_78], ecx
0x180008818  mov     ecx, [r12+30h]
0x18000881d  mov     dword ptr [rsp+0F0h+var_80], edx
0x180008821  mov     rdx, [r12]
0x180008825  mov     dword ptr [rsp+0F0h+var_88], r10d
0x18000882a  mov     dword ptr [rsp+0F0h+var_90], r11d
0x18000882f  mov     dword ptr [rsp+0F0h+var_98], ebx
0x180008833  mov     dword ptr [rsp+0F0h+var_A0], edi
0x180008837  mov     dword ptr [rsp+0F0h+var_A8], esi
0x18000883b  mov     dword ptr [rsp+0F0h+var_B0], r14d
0x180008840  mov     dword ptr [rsp+0F0h+var_B8], r15d
0x180008845  mov     dword ptr [rsp+0F0h+var_C0], ecx
0x180008849  mov     ecx, [r12+40h]
0x18000884e  mov     dword ptr [rsp+0F0h+var_C8], ecx
0x180008852  mov     ecx, [r12+20h]
0x180008857  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x18000885b  lea     rcx, aImageCacheGrou; "Image Cache: Group=[%s], Image=[%s], In"...
0x180008862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008867  mov     rdi, [rbp+57h+arg_0]
0x18000886b  lea     r15, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180008872  xor     r14d, r14d
0x180008875  mov     rsi, [rbp+57h+arg_10]
0x180008879  mov     rcx, [rbp+57h+var_50]
0x18000887d  call    cs:__imp_WdsImgFindNextImage
0x180008884  nop     dword ptr [rax+rax+00h]
0x180008889  mov     ebx, eax
0x18000888b  test    eax, eax
0x18000888d  jns     loc_180008527
0x180008893  cmp     eax, 0C1020203h
0x180008898  jz      short loc_1800088BC
0x18000889a  mov     r9d, 488h
0x1800088a0  mov     ecx, eax
0x1800088a2  call    ElValidateHr_0
0x1800088a7  test    eax, eax
0x1800088a9  jns     short loc_1800088BC
0x1800088ab  mov     ecx, ebx
0x1800088ad  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800088b4  nop     dword ptr [rax+rax+00h]
0x1800088b9  mov     r13d, eax
0x1800088bc  mov     rcx, [rbp+57h+var_50]
0x1800088c0  test    rcx, rcx
0x1800088c3  jz      short loc_1800088D1
0x1800088c5  call    cs:__imp_WdsImgClose
0x1800088cc  nop     dword ptr [rax+rax+00h]
0x1800088d1  mov     rbx, [rsp+0F0h+arg_8]
0x1800088d9  mov     eax, r13d
0x1800088dc  add     rsp, 0C0h
0x1800088e3  pop     r15
0x1800088e5  pop     r14
0x1800088e7  pop     r13
0x1800088e9  pop     r12
0x1800088eb  pop     rdi
0x1800088ec  pop     rsi
0x1800088ed  pop     rbp
0x1800088ee  retn
0x1800088f0  mov     ecx, ebx
0x1800088f2  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800088f9  nop     dword ptr [rax+rax+00h]
0x1800088fe  mov     r13d, eax
0x180008901  mov     rcx, r12; this
0x180008904  call    ??_GImage@CImageCache@@QEAAPEAXI@Z; CImageCache::Image::`scalar deleting destructor'(uint)
0x180008909  jmp     short loc_1800088BC
0x18000890b  mov     r13d, 8
0x180008911  jmp     short loc_1800088BC
```

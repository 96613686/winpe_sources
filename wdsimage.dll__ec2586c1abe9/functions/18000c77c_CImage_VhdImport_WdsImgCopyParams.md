# CImage::VhdImport(WdsImgCopyParams *)

- ea: `0x18000c77c`
- end: `0x18000c9e9`
- name: `?VhdImport@CImage@@AEAAJPEAUWdsImgCopyParams@@@Z`
- size: `621`
- prototype: `__int64 __fastcall(CImage *__hidden this, struct WdsImgCopyParams *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18000abe0`

## callees

- `0x180001588`
- `0x1800039a8`
- `0x180008bb4`
- `0x1800092fc`
- `0x18000a570`
- `0x18000a948`
- `0x18000ae64`
- `0x18000b8b0`
- `0x18000be68`
- `0x18000c77c`
- `0x18000d5b0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CImage::VhdImport(CImage *this, struct WdsImgCopyParams *a2, __int64 a3, struct CImage **a4)
{
  unsigned int v4; // edi
  bool v5; // zf
  __int64 ParentImages; // rbx
  const WCHAR *v9; // rcx
  int ImageById; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned int v16; // edx
  __int64 i; // rdi
  __int64 v18; // r15
  CImage *v19; // rax
  CImage *v20; // rax
  CImage *v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rdx
  struct _GUID v25; // [rsp+38h] [rbp-19h] BYREF
  __int64 v26; // [rsp+48h] [rbp-9h] BYREF
  int v27; // [rsp+50h] [rbp-1h]
  unsigned int v28; // [rsp+54h] [rbp+3h]
  _OWORD v29[3]; // [rsp+60h] [rbp+Fh] BYREF
  __int64 v30; // [rsp+90h] [rbp+3Fh]

  v26 = 0;
  v27 = 0;
  v28 = 0;
  v4 = 0;
  v5 = *((_DWORD *)this + 7) == 1;
  v30 = 0;
  memset(v29, 0, sizeof(v29));
  if ( v5 )
  {
    v4 = 4;
  }
  else if ( *((_DWORD *)this + 7) == 3 )
  {
    v4 = 512;
  }
  else
  {
    LODWORD(ParentImages) = -2147024883;
    if ( (int)ElValidateHr_5(2147942413LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2392) < 0 )
      goto LABEL_25;
  }
  v9 = (const WCHAR *)*((_QWORD *)a2 + 1);
  v25 = (struct _GUID)*((_OWORD *)this + 2);
  ImageById = CImage::FindImageById(v9, v4, &v25, a4);
  LODWORD(ParentImages) = ImageById;
  if ( !ImageById )
  {
    LODWORD(ParentImages) = -1056832997;
    v12 = 2406;
    goto LABEL_10;
  }
  if ( ((ImageById + 1056833021) & 0xFFFFFFF7) != 0 )
  {
    v12 = 2410;
LABEL_10:
    if ( (int)ElValidateHr_5((unsigned int)ParentImages, v11, "base\\eco\\wds\\wdsimage\\src\\image.cpp", v12) < 0 )
      goto LABEL_25;
  }
  ParentImages = (unsigned int)CImage::GetParentImages((__int64)this, (__int64)&v26);
  if ( (int)ElValidateHr_5(ParentImages, v13, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2418) >= 0 )
  {
    ParentImages = (unsigned int)CImage::MatchImagesById(*((LPCWSTR *)a2 + 1));
    if ( (int)ElValidateHr_5(ParentImages, v14, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2428) >= 0 )
    {
      *((_QWORD *)a2 + 8) = &v26;
      ParentImages = (unsigned int)CDepCopyConnector<&public: long CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::Copy(
                                     (__int64)this,
                                     *((_QWORD *)this + 49),
                                     (__int64)a2,
                                     (__int64)v29);
      if ( (int)ElValidateHr_5(ParentImages, v15, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2453) >= 0 )
      {
        v16 = v28;
        for ( i = 0; (unsigned int)i < v16; i = (unsigned int)(i + 1) )
        {
          v18 = *(_QWORD *)(v26 + 8 * i);
          if ( !*(_QWORD *)(v18 + 24) )
          {
            v19 = (CImage *)operator new(0x190u, (const struct std::nothrow_t *)&std::nothrow);
            if ( !v19 || (v20 = CImage::CImage(v19), (v21 = v20) == 0) )
            {
              LODWORD(ParentImages) = -2147024882;
              break;
            }
            ParentImages = (unsigned int)CImage::Initialize(v20, *(const unsigned __int16 **)(v18 + 40), 1, 312);
            if ( (int)ElValidateHr_5(ParentImages, v22, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2474) < 0
              || (ParentImages = (unsigned int)CImage::SetEnabled(v21, 0),
                  (int)ElValidateHr_5(ParentImages, v23, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2477) < 0) )
            {
              (*(void (__fastcall **)(CImage *, __int64))(*(_QWORD *)v21 + 16LL))(v21, 1);
              break;
            }
            (*(void (__fastcall **)(CImage *, __int64))(*(_QWORD *)v21 + 16LL))(v21, 1);
            v16 = v28;
          }
        }
      }
    }
  }
LABEL_25:
  CDynArray<WdsImgParentImage *,CDeallocatePointer>::~CDynArray<WdsImgParentImage *,CDeallocatePointer>(&v26);
  return (unsigned int)ParentImages;
}

```

## disassembly

```asm
0x18000c77c  mov     rax, rsp
0x18000c77f  mov     [rax+8], rbx
0x18000c783  mov     [rax+10h], rsi
0x18000c787  mov     [rax+18h], rdi
0x18000c78b  mov     [rax+20h], r13
0x18000c78f  push    rbp
0x18000c790  push    r14
0x18000c792  push    r15
0x18000c794  lea     rbp, [rax-5Fh]
0x18000c798  sub     rsp, 90h
0x18000c79f  xor     eax, eax
0x18000c7a1  lea     r13, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c7a8  and     [rbp+57h+var_60], rax
0x18000c7ac  xorps   xmm0, xmm0
0x18000c7af  and     [rbp+57h+var_58], eax
0x18000c7b2  xor     r15d, r15d
0x18000c7b5  and     [rbp+57h+var_54], eax
0x18000c7b8  xor     edi, edi
0x18000c7ba  cmp     dword ptr [rcx+1Ch], 1
0x18000c7be  mov     r14, rdx
0x18000c7c1  mov     rsi, rcx
0x18000c7c4  mov     [rbp+57h+var_18], rax
0x18000c7c8  movups  [rbp+57h+var_48], xmm0
0x18000c7cc  movups  [rbp+57h+var_38], xmm0
0x18000c7d0  movups  [rbp+57h+var_28], xmm0
0x18000c7d4  jnz     short loc_18000C7DB
0x18000c7d6  lea     edi, [rax+4]
0x18000c7d9  jmp     short loc_18000C805
0x18000c7db  cmp     dword ptr [rcx+1Ch], 3
0x18000c7df  jnz     short loc_18000C7E8
0x18000c7e1  mov     edi, 200h
0x18000c7e6  jmp     short loc_18000C805
0x18000c7e8  mov     ebx, 8007000Dh
0x18000c7ed  mov     r9d, 958h
0x18000c7f3  mov     ecx, ebx
0x18000c7f5  mov     r8, r13
0x18000c7f8  call    ElValidateHr_5
0x18000c7fd  test    eax, eax
0x18000c7ff  js      loc_18000C9BC
0x18000c805  movups  xmm0, xmmword ptr [rsi+20h]
0x18000c809  mov     rcx, [r14+8]; lpFileName
0x18000c80d  lea     r8, [rbp+57h+var_70]; struct _GUID
0x18000c811  mov     edx, edi; unsigned int
0x18000c813  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x18000c818  call    ?FindImageById@CImage@@SAJPEBGKU_GUID@@PEAPEAV1@@Z; CImage::FindImageById(ushort const *,ulong,_GUID,CImage * *)
0x18000c81d  mov     ebx, eax
0x18000c81f  test    eax, eax
0x18000c821  jnz     short loc_18000C830
0x18000c823  mov     ebx, 0C102021Bh
0x18000c828  mov     r9d, 966h
0x18000c82e  jmp     short loc_18000C842
0x18000c830  add     eax, 3EFDFDFDh
0x18000c835  test    eax, 0FFFFFFF7h
0x18000c83a  jz      short loc_18000C854
0x18000c83c  mov     r9d, 96Ah
0x18000c842  mov     r8, r13
0x18000c845  mov     ecx, ebx
0x18000c847  call    ElValidateHr_5
0x18000c84c  test    eax, eax
0x18000c84e  js      loc_18000C9BC
0x18000c854  lea     rdx, [rbp+57h+var_60]
0x18000c858  mov     rcx, rsi
0x18000c85b  call    ?GetParentImages@CImage@@AEAAJPEAV?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@@Z; CImage::GetParentImages(CDynArray<WdsImgParentImage *,CDeallocatePointer> *)
0x18000c860  mov     r9d, 972h
0x18000c866  mov     r8, r13
0x18000c869  mov     ecx, eax
0x18000c86b  mov     ebx, eax
0x18000c86d  call    ElValidateHr_5
0x18000c872  test    eax, eax
0x18000c874  js      loc_18000C9BC
0x18000c87a  mov     rcx, [r14+8]; lpFileName
0x18000c87e  lea     r8, [rbp+57h+var_60]
0x18000c882  mov     edx, edi
0x18000c884  call    ?MatchImagesById@CImage@@SAJPEBGKPEAV?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@@Z; CImage::MatchImagesById(ushort const *,ulong,CDynArray<WdsImgParentImage *,CDeallocatePointer> *)
0x18000c889  mov     r9d, 97Ch
0x18000c88f  mov     r8, r13
0x18000c892  mov     ecx, eax
0x18000c894  mov     ebx, eax
0x18000c896  call    ElValidateHr_5
0x18000c89b  test    eax, eax
0x18000c89d  js      loc_18000C9BC
0x18000c8a3  lea     rax, [rbp+57h+var_60]
0x18000c8a7  mov     r8, r14
0x18000c8aa  mov     [r14+40h], rax
0x18000c8ae  lea     r9, [rbp+57h+var_48]
0x18000c8b2  mov     rdx, [rsi+188h]
0x18000c8b9  mov     rcx, rsi
0x18000c8bc  call    ?Copy@?$CDepCopyConnector@$1?VhdImportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAJPEAVCImage@@PEAVIDepImageResolved@@PEAUWdsImgCopyParams@@PEAU_DEP_IMAGE_COPY_PARAMS@@PEAPEAVIDepImage@@@Z; CDepCopyConnector<&CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::Copy(CImage *,IDepImageResolved *,WdsImgCopyParams *,_DEP_IMAGE_COPY_PARAMS *,IDepImage * *)
0x18000c8c1  mov     r9d, 995h
0x18000c8c7  mov     r8, r13
0x18000c8ca  mov     ecx, eax
0x18000c8cc  mov     ebx, eax
0x18000c8ce  call    ElValidateHr_5
0x18000c8d3  test    eax, eax
0x18000c8d5  js      loc_18000C9BC
0x18000c8db  mov     edx, [rbp+57h+var_54]
0x18000c8de  xor     edi, edi
0x18000c8e0  test    edx, edx
0x18000c8e2  jz      loc_18000C9BC
0x18000c8e8  cmp     edi, edx
0x18000c8ea  jnb     short loc_18000C8F4
0x18000c8ec  mov     rax, [rbp+57h+var_60]
0x18000c8f0  mov     r15, [rax+rdi*8]
0x18000c8f4  cmp     qword ptr [r15+18h], 0
0x18000c8f9  jnz     loc_18000C995
0x18000c8ff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c906  mov     ecx, 190h; unsigned __int64
0x18000c90b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c910  test    rax, rax
0x18000c913  jz      loc_18000C9B7
0x18000c919  mov     rcx, rax; this
0x18000c91c  call    ??0CImage@@QEAA@XZ; CImage::CImage(void)
0x18000c921  mov     rsi, rax
0x18000c924  test    rax, rax
0x18000c927  jz      loc_18000C9B7
0x18000c92d  mov     rdx, [r15+28h]; unsigned __int16 *
0x18000c931  mov     r9d, 138h; unsigned int
0x18000c937  mov     r8d, 1; unsigned int
0x18000c93d  mov     rcx, rax; this
0x18000c940  call    ?Initialize@CImage@@QEAAJPEBGKK@Z; CImage::Initialize(ushort const *,ulong,ulong)
0x18000c945  mov     r9d, 9AAh
0x18000c94b  mov     r8, r13
0x18000c94e  mov     ecx, eax
0x18000c950  mov     ebx, eax
0x18000c952  mov     r14, rsi
0x18000c955  call    ElValidateHr_5
0x18000c95a  test    eax, eax
0x18000c95c  js      short loc_18000C9A1
0x18000c95e  xor     edx, edx; int
0x18000c960  mov     rcx, rsi; this
0x18000c963  call    ?SetEnabled@CImage@@QEAAJH@Z; CImage::SetEnabled(int)
0x18000c968  mov     r9d, 9ADh
0x18000c96e  mov     r8, r13
0x18000c971  mov     ecx, eax
0x18000c973  mov     ebx, eax
0x18000c975  call    ElValidateHr_5
0x18000c97a  test    eax, eax
0x18000c97c  js      short loc_18000C9A1
0x18000c97e  mov     rax, [rsi]
0x18000c981  mov     edx, 1
0x18000c986  mov     rcx, rsi
0x18000c989  mov     rax, [rax+10h]
0x18000c98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c992  mov     edx, [rbp+57h+var_54]
0x18000c995  inc     edi
0x18000c997  cmp     edi, edx
0x18000c999  jb      loc_18000C8EC
0x18000c99f  jmp     short loc_18000C9BC
0x18000c9a1  mov     rax, [r14]
0x18000c9a4  mov     edx, 1
0x18000c9a9  mov     rcx, r14
0x18000c9ac  mov     rax, [rax+10h]
0x18000c9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9b5  jmp     short loc_18000C9BC
0x18000c9b7  mov     ebx, 8007000Eh
0x18000c9bc  lea     rcx, [rbp+57h+var_60]
0x18000c9c0  call    ??1?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@QEAA@XZ; CDynArray<WdsImgParentImage *,CDeallocatePointer>::~CDynArray<WdsImgParentImage *,CDeallocatePointer>(void)
0x18000c9c5  lea     r11, [rsp+0A0h+var_10]
0x18000c9cd  mov     eax, ebx
0x18000c9cf  mov     rbx, [r11+20h]
0x18000c9d3  mov     rsi, [r11+28h]
0x18000c9d7  mov     rdi, [r11+30h]
0x18000c9db  mov     r13, [r11+38h]
0x18000c9df  mov     rsp, r11
0x18000c9e2  pop     r15
0x18000c9e4  pop     r14
0x18000c9e6  pop     rbp
0x18000c9e7  retn
```

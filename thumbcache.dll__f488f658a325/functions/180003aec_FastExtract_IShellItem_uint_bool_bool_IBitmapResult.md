# FastExtract(IShellItem *,uint,bool *,bool *,IBitmapResult * *)

- ea: `0x180003aec`
- end: `0x180004401`
- name: `?FastExtract@@YAJPEAUIShellItem@@IPEA_N1PEAPEAUIBitmapResult@@@Z`
- size: `2325`
- prototype: `__int64 __usercall@<rax>(struct IShellItem *@<rcx>, unsigned int@<edx>, bool *@<r8>, bool *@<r9>, struct IBitmapResult **)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ffcc`
- `0x18002d090`

## callees

- `0x180003624`
- `0x1800039a8`
- `0x180003aec`
- `0x180004408`
- `0x180004488`
- `0x180005138`
- `0x180005228`
- `0x1800053f0`
- `0x180005410`
- `0x180005480`
- `0x180006c70`
- `0x180006f4c`
- `0x18002b024`
- `0x18002b11c`
- `0x18002e80c`
- `0x180033d54`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c43`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800040d2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800040d2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800040c8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800040c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003bde`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003bde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003b84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003b84`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall FastExtract(struct IShellItem *a1, unsigned int a2, bool *a3, bool *a4, struct _GUID *a5)
{
  HRESULT Instance; // edi
  __int64 v11; // rcx
  __int64 v12; // r8
  struct IWICBitmapDecoder *v13; // rcx
  char v14; // si
  HLOCAL v15; // rax
  void *v16; // rbx
  struct IWICImagingFactory *v17; // rdi
  HRESULT (__stdcall *CreateDecoderFromStream)(IWICImagingFactory *, IStream *, const GUID *, WICDecodeOptions, IWICBitmapDecoder **); // rbx
  struct IWICBitmapDecoder *v19; // rdi
  HRESULT (__stdcall *GetFrame)(IWICBitmapDecoder *, UINT, IWICBitmapFrameDecode **); // rbx
  struct IWICBitmapSource *v21; // rdi
  ULONG (__stdcall *Release)(IWICBitmapSource *); // rbx
  int v23; // eax
  struct IWICBitmapSource *v24; // rdi
  HRESULT (__stdcall *QueryInterface)(IWICBitmapSource *, const IID *const, void **); // rbx
  Windows::Internal::Thumbnails *v26; // rbx
  struct IWICMetadataQueryReader *v27; // rcx
  double v28; // xmm4_8
  double v29; // xmm6_8
  int v30; // edx
  int v31; // r10d
  double v32; // xmm4_8
  unsigned int v33; // esi
  unsigned int v34; // r14d
  bool HaveBlackBars; // al
  struct IWICImagingFactory *v36; // rdi
  HRESULT (__stdcall *CreateBitmapScaler)(IWICImagingFactory *, IWICBitmapScaler **); // rbx
  struct IWICBitmapSource *v38; // rcx
  struct IWICBitmapSource *v39; // rcx
  struct IWICBitmapSource *v40; // rcx
  struct IWICBitmapSource *v41; // rcx
  IStream *v42; // rcx
  struct IWICImagingFactory *v43; // rcx
  struct IWICBitmapSource *v44; // rbx
  struct IWICBitmapDecoder *v45; // rdi
  HRESULT (__stdcall *GetPreview)(IWICBitmapDecoder *, IWICBitmapSource **); // rbx
  struct IWICBitmapSource *v47; // rdi
  HRESULT (__stdcall *v48)(IWICBitmapSource *, const IID *const, void **); // rbx
  const struct _GUID *v49; // r8
  const struct tagSIZE *v50; // r9
  struct IWICImagingFactory *v51; // rdi
  HRESULT (__stdcall *CreateBitmapClipper)(IWICImagingFactory *, IWICBitmapClipper **); // rbx
  __int64 v53; // rdx
  struct IWICBitmapDecoder **ppv; // [rsp+28h] [rbp-A1h]
  struct IWICBitmapSource *v55; // [rsp+38h] [rbp-91h] BYREF
  struct IWICBitmapSource *v56; // [rsp+40h] [rbp-89h] BYREF
  struct IWICBitmapSource *v57; // [rsp+48h] [rbp-81h] BYREF
  unsigned int v58[2]; // [rsp+50h] [rbp-79h] BYREF
  struct IWICImagingFactory *v59; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v60; // [rsp+60h] [rbp-69h] BYREF
  unsigned int v61; // [rsp+64h] [rbp-65h] BYREF
  struct IWICBitmapSource *v62; // [rsp+68h] [rbp-61h] BYREF
  struct IWICBitmapDecoder *v63; // [rsp+70h] [rbp-59h] BYREF
  unsigned int v64; // [rsp+78h] [rbp-51h] BYREF
  IStream *pstm; // [rsp+80h] [rbp-49h] BYREF
  struct IWICMetadataQueryReader *v66; // [rsp+88h] [rbp-41h] BYREF
  unsigned int v67; // [rsp+90h] [rbp-39h]
  unsigned int v68; // [rsp+94h] [rbp-35h]
  LPVOID pv[3]; // [rsp+98h] [rbp-31h] BYREF
  IWICBitmapSource v70[2]; // [rsp+B0h] [rbp-19h] BYREF

  *(_QWORD *)&a5->Data1 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  Instance = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a1->lpVtbl->GetDisplayName)(
               a1,
               2147647488LL,
               pv);
  if ( Instance >= 0 )
  {
    if ( !(unsigned int)CheckForFastExtractExtension((const unsigned __int16 *)pv[0]) )
    {
      Instance = -2147175933;
      goto LABEL_8;
    }
    v59 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)&v59);
    if ( Instance < 0 )
      goto LABEL_67;
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v11, &Thumbnails_FastExtract_Start, v12, 1, v70);
    pstm = 0;
    v58[0] = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pstm);
    Instance = _GetStreamForFastThumbnail(a1, &pstm, (enum THUMBNAIL_STREAM_INFO *)v58);
    if ( Instance < 0 )
    {
LABEL_63:
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(v13, &Thumbnails_FastExtract_Stop, (unsigned int)Instance);
      v42 = pstm;
      if ( pstm )
      {
        pstm = 0;
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v42 + 16LL))(v42);
      }
LABEL_67:
      v43 = v59;
      if ( v59 )
      {
        v59 = 0;
        ((void (__fastcall *)(struct IWICImagingFactory *))v43->lpVtbl->Release)(v43);
      }
      goto LABEL_8;
    }
    v14 = v58[0];
    if ( (v58[0] & 1) == 0 )
    {
      v55 = 0;
      v15 = LocalAlloc(0x40u, 0x8000u);
      v16 = v15;
      if ( v15 )
      {
        IStream_Read(pstm, v15, 0x8000u);
        IStream_Reset(pstm);
      }
      CTContainer_PolicyLocalMem::DestroyMem(v16);
    }
    v63 = 0;
    *(_OWORD *)&v70[0].lpVtbl = 0;
    v17 = v59;
    CreateDecoderFromStream = v59->lpVtbl->CreateDecoderFromStream;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
    ppv = &v63;
    Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, IStream *, GUID *, _QWORD))CreateDecoderFromStream)(
                 v17,
                 pstm,
                 &GUID_VendorMicrosoft,
                 0);
    if ( Instance < 0
      || (Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, IWICBitmapSource *))v63->lpVtbl->GetContainerFormat)(
                       v63,
                       v70),
          Instance < 0) )
    {
LABEL_61:
      v13 = v63;
      if ( v63 )
      {
        v63 = 0;
        ((void (__fastcall *)(struct IWICBitmapDecoder *))v13->lpVtbl->Release)(v13);
      }
      goto LABEL_63;
    }
    v62 = 0;
    v19 = v63;
    GetFrame = v63->lpVtbl->GetFrame;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, struct IWICBitmapSource **))GetFrame)(
                 v19,
                 0,
                 &v62);
    if ( Instance < 0 )
    {
LABEL_59:
      v41 = v62;
      if ( v62 )
      {
        v62 = 0;
        ((void (__fastcall *)(struct IWICBitmapSource *))v41->lpVtbl->Release)(v41);
      }
      goto LABEL_61;
    }
    v57 = 0;
    if ( (v14 & 2) != 0 )
    {
      Microsoft::WRL::ComPtr<IWICBitmapSource>::operator=<IWICBitmapFrameDecode>(&v57, &v62);
      goto LABEL_25;
    }
    v21 = v62;
    Release = v62->lpVtbl[1].Release;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    v23 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource **))Release)(v21, &v57);
    Instance = v23;
    if ( v23 == -2003292348 )
    {
      v45 = v63;
      GetPreview = v63->lpVtbl->GetPreview;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
      Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, struct IWICBitmapSource **))GetPreview)(v45, &v57);
      if ( Instance >= 0 )
        goto LABEL_25;
      Instance = -2147175933;
    }
    else if ( v23 >= 0 )
    {
LABEL_25:
      v55 = 0;
      if ( (v14 & 4) != 0 || !WICIsOrientationSupported(v63) )
      {
        v44 = v62;
        if ( v62 )
          ((void (__fastcall *)(struct IWICBitmapSource *))v62->lpVtbl->AddRef)(v62);
        v55 = v44;
      }
      else
      {
        v66 = 0;
        v24 = v62;
        QueryInterface = v62->lpVtbl[1].QueryInterface;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66);
        Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICMetadataQueryReader **))QueryInterface)(
                     v24,
                     &v66);
        if ( Instance >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
          Instance = WICCreateOrientedBitmapSource(v59, v62, v66, &v55);
          if ( Instance >= 0 )
          {
            v56 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
            Instance = WICCreateCachedOrientedBitmapSource(v59, v57, v66, &v56);
            v26 = (Windows::Internal::Thumbnails *)v56;
            if ( Instance >= 0 && v57 != v56 )
            {
              *(_QWORD *)v58 = v56;
              Microsoft::WRL::ComPtr<IBitmapResult>::InternalAddRef(v58);
              *(_QWORD *)v58 = v57;
              v57 = (struct IWICBitmapSource *)v26;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v58);
              v26 = (Windows::Internal::Thumbnails *)v56;
            }
            if ( v26 )
            {
              v56 = 0;
              (*(void (__fastcall **)(Windows::Internal::Thumbnails *))(*(_QWORD *)v26 + 16LL))(v26);
            }
          }
        }
        v27 = v66;
        if ( v66 )
        {
          v66 = 0;
          ((void (__fastcall *)(struct IWICMetadataQueryReader *))v27->lpVtbl->Release)(v27);
        }
      }
      if ( Instance < 0 )
        goto LABEL_55;
      v60 = 0;
      v61 = 0;
      v58[0] = 0;
      v64 = 0;
      Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))v57->lpVtbl->GetSize)(
                   v57,
                   &v60,
                   &v61);
      if ( Instance < 0 )
        goto LABEL_55;
      Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))v55->lpVtbl->GetSize)(
                   v55,
                   v58,
                   &v64);
      if ( Instance < 0 )
        goto LABEL_55;
      if ( !v60
        || !v61
        || !v58[0]
        || !v64
        || ((v28 = (double)(int)v60 / (double)(int)v61, v29 = (double)(int)v58[0] / (double)(int)v64, v28 < 1.0)
         || v29 < 1.0)
        && (v28 > 1.0 || v29 > 1.0) )
      {
        Instance = -2147175933;
LABEL_55:
        v39 = v55;
        if ( v55 )
        {
          v55 = 0;
          ((void (__fastcall *)(struct IWICBitmapSource *))v39->lpVtbl->Release)(v39);
        }
        goto LABEL_57;
      }
      if ( DoesThumbnailMatchImageAspectRatio(v60, v61, v58[0], v64) )
      {
        if ( a3 )
          *a3 = 1;
      }
      else
      {
        v33 = v31;
        if ( v32 <= v29 )
        {
          v34 = (int)((double)v31 / v29 + 0.5);
        }
        else
        {
          v33 = (int)((double)v30 * v29 + 0.5);
          v34 = v30;
          if ( v33 != v31 )
          {
LABEL_48:
            HaveBlackBars = DoesThumbnailHaveBlackBars(v57);
            v56 = 0;
            if ( HaveBlackBars )
            {
              v51 = v59;
              CreateBitmapClipper = v59->lpVtbl->CreateBitmapClipper;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
              Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICBitmapSource **))CreateBitmapClipper)(
                           v51,
                           &v56);
              if ( Instance >= 0 )
              {
                LODWORD(v66) = (v60 - v33 + 1) >> 1;
                HIDWORD(v66) = (v61 - v34 + 1) >> 1;
                v67 = v33;
                v68 = v34;
                Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource *, struct IWICMetadataQueryReader **))v56->lpVtbl[1].QueryInterface)(
                             v56,
                             v57,
                             &v66);
                if ( Instance >= 0 )
                {
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
                  Instance = Microsoft::WRL::ComPtr<IWICBitmapScaler>::CopyTo(&v56, v53, &v57);
                }
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
            }
            else
            {
              v36 = v59;
              CreateBitmapScaler = v59->lpVtbl->CreateBitmapScaler;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
              Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICBitmapSource **))CreateBitmapScaler)(
                           v36,
                           &v56);
              if ( Instance >= 0 )
              {
                LODWORD(ppv) = 3;
                Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource *, _QWORD, _QWORD))v56->lpVtbl[1].QueryInterface)(
                             v56,
                             v57,
                             v33,
                             v34);
                if ( Instance >= 0 )
                {
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
                  Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *, struct IWICBitmapSource **))v56->lpVtbl->QueryInterface)(
                               v56,
                               &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
                               &v57);
                }
              }
              v38 = v56;
              if ( v56 )
              {
                v56 = 0;
                ((void (__fastcall *)(struct IWICBitmapSource *))v38->lpVtbl->Release)(v38);
              }
            }
            if ( Instance < 0 )
              goto LABEL_55;
            v31 = v33;
            v60 = v33;
            v30 = v34;
            v61 = v34;
            goto LABEL_79;
          }
        }
        if ( v34 != v30 )
          goto LABEL_48;
      }
LABEL_79:
      if ( v31 < a2 && v30 < a2 )
      {
        v56 = 0;
        Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICBitmapSource **))v59->lpVtbl->CreateBitmapScaler)(
                     v59,
                     &v56);
        if ( Instance >= 0 )
        {
          LODWORD(ppv) = 3;
          Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource *))v56->lpVtbl[1].QueryInterface)(
                       v56,
                       v57);
          if ( Instance >= 0 )
          {
            if ( a4 )
              *a4 = 1;
            v47 = v56;
            v48 = v56->lpVtbl->QueryInterface;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
            Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *, struct IWICBitmapSource **))v48)(
                         v47,
                         &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
                         &v57);
          }
        }
        if ( v56 )
          ((void (__fastcall *)(struct IWICBitmapSource *))v56->lpVtbl->Release)(v56);
      }
      if ( Instance >= 0 )
      {
        LODWORD(v56) = 0;
        LODWORD(v66) = 0;
        Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource **, struct IWICMetadataQueryReader **))v57->lpVtbl->GetSize)(
                     v57,
                     &v56,
                     &v66);
        if ( Instance >= 0 )
          Instance = Windows::Internal::Thumbnails::CreateBitmapResult(
                       (Windows::Internal::Thumbnails *)v57,
                       v70,
                       v49,
                       v50,
                       (const int *)ppv,
                       a5,
                       (void **)&v55->lpVtbl);
      }
      goto LABEL_55;
    }
LABEL_57:
    v40 = v57;
    if ( v57 )
    {
      v57 = 0;
      ((void (__fastcall *)(struct IWICBitmapSource *))v40->lpVtbl->Release)(v40);
    }
    goto LABEL_59;
  }
LABEL_8:
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180003aec  mov     rax, rsp
0x180003aef  push    rbp
0x180003af0  push    rbx
0x180003af1  push    rsi
0x180003af2  push    rdi
0x180003af3  push    r12
0x180003af5  push    r13
0x180003af7  push    r14
0x180003af9  push    r15
0x180003afb  lea     rbp, [rax-57h]
0x180003aff  sub     rsp, 0D8h
0x180003b06  movaps  xmmword ptr [rax-58h], xmm6
0x180003b0a  mov     rax, cs:__security_cookie
0x180003b11  xor     rax, rsp
0x180003b14  mov     qword ptr [rbp+4Fh+var_58], rax
0x180003b18  mov     r12, r9
0x180003b1b  mov     r14, r8
0x180003b1e  mov     r15d, edx
0x180003b21  mov     rbx, rcx
0x180003b24  mov     r13, [rbp+4Fh+arg_20]
0x180003b28  xor     esi, esi
0x180003b2a  mov     [r13+0], rsi
0x180003b2e  test    r8, r8
0x180003b31  jz      short loc_180003B36
0x180003b33  mov     [r8], sil
0x180003b36  test    r12, r12
0x180003b39  jz      short loc_180003B3E
0x180003b3b  mov     [r9], sil
0x180003b3e  mov     [rbp+4Fh+pv], rsi
0x180003b42  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003b46  mov     [rbp+4Fh+var_78], rax
0x180003b4a  mov     [rbp+4Fh+var_70], rax
0x180003b4e  mov     rax, [rcx]
0x180003b51  lea     r8, [rbp+4Fh+pv]
0x180003b55  mov     edx, 80028000h
0x180003b5a  mov     rax, [rax+28h]
0x180003b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b63  mov     edi, eax
0x180003b65  test    eax, eax
0x180003b67  js      short loc_180003B7B
0x180003b69  mov     rcx, [rbp+4Fh+pv]; unsigned __int16 *
0x180003b6d  call    ?CheckForFastExtractExtension@@YAHPEBG@Z; CheckForFastExtractExtension(ushort const *)
0x180003b72  test    eax, eax
0x180003b74  jnz     short loc_180003BB4
0x180003b76  mov     edi, 8004B203h
0x180003b7b  mov     rcx, [rbp+4Fh+pv]; pv
0x180003b7f  test    rcx, rcx
0x180003b82  jz      short loc_180003B8A
0x180003b84  call    cs:__imp_CoTaskMemFree
0x180003b8a  mov     eax, edi
0x180003b8c  mov     rcx, qword ptr [rbp+4Fh+var_58]
0x180003b90  xor     rcx, rsp; StackCookie
0x180003b93  call    __security_check_cookie
0x180003b98  movaps  xmm6, [rsp+110h+var_58+8]
0x180003ba0  add     rsp, 0D8h
0x180003ba7  pop     r15
0x180003ba9  pop     r14
0x180003bab  pop     r13
0x180003bad  pop     r12
0x180003baf  pop     rdi
0x180003bb0  pop     rsi
0x180003bb1  pop     rbx
0x180003bb2  pop     rbp
0x180003bb3  retn
0x180003bb4  mov     [rbp+4Fh+var_C0], rsi
0x180003bb8  lea     rcx, [rbp+4Fh+var_C0]
0x180003bbc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003bc1  lea     rax, [rbp+4Fh+var_C0]
0x180003bc5  mov     [rsp+110h+ppv], rax; ppv
0x180003bca  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180003bd1  xor     edx, edx; pUnkOuter
0x180003bd3  lea     r8d, [rdx+1]; dwClsContext
0x180003bd7  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180003bde  call    cs:__imp_CoCreateInstance
0x180003be4  mov     edi, eax
0x180003be6  test    eax, eax
0x180003be8  js      loc_18000409F
0x180003bee  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180003bf5  jnz     loc_1800042D9
0x180003bfb  mov     [rbp+4Fh+pstm], rsi
0x180003bff  mov     [rbp+4Fh+var_C8], esi
0x180003c02  lea     rcx, [rbp+4Fh+pstm]
0x180003c06  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003c0b  lea     r8, [rbp+4Fh+var_C8]; enum THUMBNAIL_STREAM_INFO *
0x180003c0f  lea     rdx, [rbp+4Fh+pstm]; struct IStream **
0x180003c13  mov     rcx, rbx; struct IShellItem *
0x180003c16  call    ?_GetStreamForFastThumbnail@@YAJPEAUIShellItem@@PEAPEAUIStream@@PEAW4THUMBNAIL_STREAM_INFO@@@Z; _GetStreamForFastThumbnail(IShellItem *,IStream * *,THUMBNAIL_STREAM_INFO *)
0x180003c1b  mov     edi, eax
0x180003c1d  test    eax, eax
0x180003c1f  js      loc_180004078
0x180003c25  mov     esi, [rbp+4Fh+var_C8]
0x180003c28  test    sil, 1
0x180003c2c  jnz     short loc_180003C5D
0x180003c2e  mov     [rsp+110h+var_E0], 0
0x180003c37  mov     edi, 8000h
0x180003c3c  mov     edx, edi; uBytes
0x180003c3e  mov     ecx, 40h ; '@'; uFlags
0x180003c43  call    cs:__imp_LocalAlloc
0x180003c49  mov     rbx, rax
0x180003c4c  test    rax, rax
0x180003c4f  jnz     loc_1800040BE
0x180003c55  mov     rcx, rbx; void *
0x180003c58  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180003c5d  mov     [rbp+4Fh+var_A8], 0
0x180003c65  xorps   xmm0, xmm0
0x180003c68  movups  xmmword ptr [rbp+4Fh+var_68.lpVtbl], xmm0
0x180003c6c  mov     rdi, [rbp+4Fh+var_C0]
0x180003c70  mov     rax, [rdi]
0x180003c73  mov     rbx, [rax+20h]
0x180003c77  lea     rcx, [rbp+4Fh+var_A8]
0x180003c7b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003c80  lea     rax, [rbp+4Fh+var_A8]
0x180003c84  mov     [rsp+110h+ppv], rax
0x180003c89  xor     r9d, r9d
0x180003c8c  lea     r8, GUID_VendorMicrosoft
0x180003c93  mov     rdx, [rbp+4Fh+pstm]
0x180003c97  mov     rcx, rdi
0x180003c9a  mov     rax, rbx
0x180003c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca2  mov     edi, eax
0x180003ca4  test    eax, eax
0x180003ca6  js      loc_180004119
0x180003cac  mov     rcx, [rbp+4Fh+var_A8]
0x180003cb0  mov     rax, [rcx]
0x180003cb3  lea     rdx, [rbp+4Fh+var_68]
0x180003cb7  mov     rax, [rax+28h]
0x180003cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cc0  mov     edi, eax
0x180003cc2  test    eax, eax
0x180003cc4  js      loc_180004119
0x180003cca  mov     [rbp+4Fh+var_B0], 0
0x180003cd2  mov     rdi, [rbp+4Fh+var_A8]
0x180003cd6  mov     rax, [rdi]
0x180003cd9  mov     rbx, [rax+68h]
0x180003cdd  lea     rcx, [rbp+4Fh+var_B0]
0x180003ce1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003ce6  lea     r8, [rbp+4Fh+var_B0]
0x180003cea  xor     edx, edx
0x180003cec  mov     rcx, rdi
0x180003cef  mov     rax, rbx
0x180003cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cf7  mov     edi, eax
0x180003cf9  test    eax, eax
0x180003cfb  js      loc_1800042AC
0x180003d01  mov     [rsp+110h+var_D0], 0
0x180003d0a  lea     rcx, [rsp+110h+var_D0]
0x180003d0f  test    sil, 2
0x180003d13  jnz     loc_1800042F9
0x180003d19  mov     rdi, [rbp+4Fh+var_B0]
0x180003d1d  mov     rax, [rdi]
0x180003d20  mov     rbx, [rax+50h]
0x180003d24  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003d29  lea     rdx, [rsp+110h+var_D0]
0x180003d2e  mov     rcx, rdi
0x180003d31  mov     rax, rbx
0x180003d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d39  mov     edi, eax
0x180003d3b  cmp     eax, 88982F44h
0x180003d40  jz      loc_180004120
0x180003d46  test    eax, eax
0x180003d48  js      loc_180004154
0x180003d4e  mov     [rsp+110h+var_E0], 0; void **
0x180003d57  test    sil, 4
0x180003d5b  jnz     loc_1800040DD
0x180003d61  mov     rcx, [rbp+4Fh+var_A8]; struct IWICBitmapDecoder *
0x180003d65  call    ?WICIsOrientationSupported@@YA_NPEAUIWICBitmapDecoder@@@Z; WICIsOrientationSupported(IWICBitmapDecoder *)
0x180003d6a  xor     esi, esi
0x180003d6c  test    al, al
0x180003d6e  jz      loc_1800040DF
0x180003d74  mov     [rbp+4Fh+var_90], rsi
0x180003d78  mov     rdi, [rbp+4Fh+var_B0]
0x180003d7c  mov     rax, [rdi]
0x180003d7f  mov     rbx, [rax+40h]
0x180003d83  lea     rcx, [rbp+4Fh+var_90]
0x180003d87  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003d8c  lea     rdx, [rbp+4Fh+var_90]
0x180003d90  mov     rcx, rdi
0x180003d93  mov     rax, rbx
0x180003d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d9b  mov     edi, eax
0x180003d9d  test    eax, eax
0x180003d9f  js      short loc_180003E1D
0x180003da1  lea     rcx, [rsp+110h+var_E0]
0x180003da6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003dab  lea     r9, [rsp+110h+var_E0]; struct IWICBitmapSource **
0x180003db0  mov     r8, [rbp+4Fh+var_90]; struct IWICMetadataQueryReader *
0x180003db4  mov     rdx, [rbp+4Fh+var_B0]; struct IWICBitmapSource *
0x180003db8  mov     rcx, [rbp+4Fh+var_C0]; struct IWICImagingFactory *
0x180003dbc  call    ?WICCreateOrientedBitmapSource@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAUIWICMetadataQueryReader@@PEAPEAU2@@Z; WICCreateOrientedBitmapSource(IWICImagingFactory *,IWICBitmapSource *,IWICMetadataQueryReader *,IWICBitmapSource * *)
0x180003dc1  mov     edi, eax
0x180003dc3  test    eax, eax
0x180003dc5  js      short loc_180003E1D
0x180003dc7  mov     [rsp+110h+var_D8], rsi
0x180003dcc  lea     rcx, [rsp+110h+var_D8]
0x180003dd1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003dd6  lea     r9, [rsp+110h+var_D8]; struct IWICBitmapSource **
0x180003ddb  mov     r8, [rbp+4Fh+var_90]; struct IWICMetadataQueryReader *
0x180003ddf  mov     rdx, [rsp+110h+var_D0]; struct IWICBitmapSource *
0x180003de4  mov     rcx, [rbp+4Fh+var_C0]; struct IWICImagingFactory *
0x180003de8  call    ?WICCreateCachedOrientedBitmapSource@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAUIWICMetadataQueryReader@@PEAPEAU2@@Z; WICCreateCachedOrientedBitmapSource(IWICImagingFactory *,IWICBitmapSource *,IWICMetadataQueryReader *,IWICBitmapSource * *)
0x180003ded  mov     edi, eax
0x180003def  mov     rbx, [rsp+110h+var_D8]
0x180003df4  test    eax, eax
0x180003df6  js      short loc_180003E03
0x180003df8  cmp     [rsp+110h+var_D0], rbx
0x180003dfd  jnz     loc_180004307
0x180003e03  test    rbx, rbx
0x180003e06  jz      short loc_180003E1D
0x180003e08  mov     [rsp+110h+var_D8], rsi
0x180003e0d  mov     rax, [rbx]
0x180003e10  mov     rcx, rbx
0x180003e13  mov     rax, [rax+10h]
0x180003e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1c  nop
0x180003e1d  mov     rcx, [rbp+4Fh+var_90]
0x180003e21  test    rcx, rcx
0x180003e24  jz      short loc_180003E37
0x180003e26  mov     [rbp+4Fh+var_90], rsi
0x180003e2a  mov     rax, [rcx]
0x180003e2d  mov     rax, [rax+10h]
0x180003e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e36  nop
0x180003e37  test    edi, edi
0x180003e39  js      loc_18000400C
0x180003e3f  mov     [rbp+4Fh+var_B8], esi
0x180003e42  mov     [rbp+4Fh+var_B4], esi
0x180003e45  mov     [rbp+4Fh+var_C8], esi
0x180003e48  mov     [rbp+4Fh+var_A0], esi
0x180003e4b  mov     rcx, [rsp+110h+var_D0]
0x180003e50  mov     rax, [rcx]
0x180003e53  lea     r8, [rbp+4Fh+var_B4]
0x180003e57  lea     rdx, [rbp+4Fh+var_B8]
0x180003e5b  mov     rax, [rax+18h]
0x180003e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e64  mov     edi, eax
0x180003e66  test    eax, eax
0x180003e68  js      loc_18000400C
0x180003e6e  mov     rcx, [rsp+110h+var_E0]
0x180003e73  mov     rax, [rcx]
0x180003e76  lea     r8, [rbp+4Fh+var_A0]
0x180003e7a  lea     rdx, [rbp+4Fh+var_C8]
0x180003e7e  mov     rax, [rax+18h]
0x180003e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e87  mov     edi, eax
0x180003e89  test    eax, eax
0x180003e8b  js      loc_18000400C
0x180003e91  mov     r10d, [rbp+4Fh+var_B8]
0x180003e95  test    r10d, r10d
0x180003e98  jz      loc_180004280
0x180003e9e  mov     edx, [rbp+4Fh+var_B4]; unsigned int
0x180003ea1  test    edx, edx
0x180003ea3  jz      loc_180004280
0x180003ea9  mov     r8d, [rbp+4Fh+var_C8]; unsigned int
0x180003ead  test    r8d, r8d
0x180003eb0  jz      loc_180004280
0x180003eb6  mov     r9d, [rbp+4Fh+var_A0]; unsigned int
0x180003eba  test    r9d, r9d
0x180003ebd  jz      loc_180004280
0x180003ec3  xorps   xmm4, xmm4
0x180003ec6  cvtsi2sd xmm4, r10
0x180003ecb  xorps   xmm0, xmm0
0x180003ece  cvtsi2sd xmm0, rdx
0x180003ed3  divsd   xmm4, xmm0
0x180003ed7  xorps   xmm6, xmm6
0x180003eda  cvtsi2sd xmm6, r8
0x180003edf  xorps   xmm0, xmm0
0x180003ee2  cvtsi2sd xmm0, r9
0x180003ee7  divsd   xmm6, xmm0
0x180003eeb  movsd   xmm1, cs:__real@3ff0000000000000
0x180003ef3  comisd  xmm4, xmm1
0x180003ef7  jb      loc_180004270
0x180003efd  comisd  xmm6, xmm1
0x180003f01  jb      loc_180004270
0x180003f07  mov     ecx, r10d; unsigned int
0x180003f0a  call    ?DoesThumbnailMatchImageAspectRatio@@YA_NIIII@Z; DoesThumbnailMatchImageAspectRatio(uint,uint,uint,uint)
0x180003f0f  test    al, al
0x180003f11  jnz     loc_18000415B
0x180003f17  mov     rsi, r10
0x180003f1a  xorps   xmm0, xmm0
0x180003f1d  comisd  xmm4, xmm6
0x180003f21  jbe     loc_1800042B3
0x180003f27  cvtsi2sd xmm0, rdx
0x180003f2c  mulsd   xmm0, xmm6
0x180003f30  addsd   xmm0, cs:__real@3fe0000000000000
0x180003f38  cvttsd2si rsi, xmm0
0x180003f3d  mov     r14d, edx
0x180003f40  cmp     esi, r10d
0x180003f43  jz      loc_1800042C9
0x180003f49  mov     rcx, [rsp+110h+var_D0]; struct IWICBitmapSource *
0x180003f4e  call    ?DoesThumbnailHaveBlackBars@@YA_NPEAUIWICBitmapSource@@@Z; DoesThumbnailHaveBlackBars(IWICBitmapSource *)
0x180003f53  mov     [rsp+110h+var_D8], 0
0x180003f5c  test    al, al
0x180003f5e  jnz     loc_180004335
0x180003f64  mov     rdi, [rbp+4Fh+var_C0]
0x180003f68  mov     rax, [rdi]
0x180003f6b  mov     rbx, [rax+58h]
0x180003f6f  lea     rcx, [rsp+110h+var_D8]
0x180003f74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003f79  lea     rdx, [rsp+110h+var_D8]
0x180003f7e  mov     rcx, rdi
  ... truncated ...
```

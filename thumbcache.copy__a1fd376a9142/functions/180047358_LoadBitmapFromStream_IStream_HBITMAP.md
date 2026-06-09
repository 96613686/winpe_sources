# LoadBitmapFromStream(IStream *,HBITMAP__ * *)

- ea: `0x180047358`
- end: `0x180047515`
- name: `?LoadBitmapFromStream@@YAJPEAUIStream@@PEAPEAUHBITMAP__@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(struct IStream *, HBITMAP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180047630`

## callees

- `0x180005138`
- `0x180005228`
- `0x180005d80`
- `0x180006af0`
- `0x18001f98c`
- `0x18002a1bc`
- `0x180035830`
- `0x180047358`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800473a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800473a3`

## pseudocode

```c
__int64 __fastcall LoadBitmapFromStream(struct IStream *a1, HBITMAP *a2)
{
  int Instance; // ebx
  struct IWICBitmapSource *v6; // [rsp+30h] [rbp-50h] BYREF
  struct IWICBitmapSource *v7; // [rsp+38h] [rbp-48h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+40h] [rbp-40h] BYREF
  struct IWICBitmapSource *v9; // [rsp+48h] [rbp-38h] BYREF
  struct IWICBitmapDecoder *v10[2]; // [rsp+50h] [rbp-30h] BYREF
  struct _GUID v11; // [rsp+60h] [rbp-20h] BYREF

  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v10[0] = 0;
    Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IStream *, GUID *, _QWORD, struct IWICBitmapDecoder **))ppv->lpVtbl->CreateDecoderFromStream)(
                 ppv,
                 a1,
                 &GUID_VendorMicrosoft,
                 0,
                 v10);
    if ( Instance < 0 )
    {
LABEL_16:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v10);
      goto LABEL_17;
    }
    v9 = 0;
    Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, struct IWICBitmapSource **))v10[0]->lpVtbl->GetFrame)(
                 v10[0],
                 0,
                 &v9);
    if ( Instance < 0 )
    {
LABEL_15:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
      goto LABEL_16;
    }
    v7 = 0;
    v11 = GUID_WICPixelFormat32bppBGRA;
    Instance = ConvertIWICBitmapSourcePixelFormat(v9, &v11, ppv, &v7);
    if ( Instance < 0 )
    {
LABEL_14:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
      goto LABEL_15;
    }
    v6 = 0;
    if ( WICIsOrientationSupported(v10[0]) )
    {
      *(_QWORD *)&v11.Data1 = 0;
      Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct _GUID *))v9->lpVtbl[1].QueryInterface)(
                   v9,
                   &v11);
      if ( Instance >= 0 )
        Instance = WICCreateOrientedBitmapSource(ppv, v7, *(struct IWICMetadataQueryReader **)&v11.Data1, &v6);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
      if ( Instance < 0 )
        goto LABEL_13;
    }
    else if ( v7 )
    {
      ATL::AtlComPtrAssign((struct IUnknown **)&v6, (struct IUnknown *)v7);
    }
    Instance = Convert32bppIWICBitmapSourceToHBITMAP(v6, a2);
LABEL_13:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
    goto LABEL_14;
  }
LABEL_17:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180047358  mov     [rsp-18h+arg_10], rbx
0x18004735d  push    rbp
0x18004735e  push    rsi
0x18004735f  push    rdi
0x180047360  mov     rbp, rsp
0x180047363  sub     rsp, 80h
0x18004736a  mov     rax, cs:__security_cookie
0x180047371  xor     rax, rsp
0x180047374  mov     [rbp+var_10], rax
0x180047378  mov     rdi, rdx
0x18004737b  mov     rsi, rcx
0x18004737e  mov     [rbp+var_40], 0
0x180047386  lea     rax, [rbp+var_40]
0x18004738a  mov     [rsp+80h+ppv], rax; ppv
0x18004738f  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180047396  xor     edx, edx; pUnkOuter
0x180047398  lea     r8d, [rdx+1]; dwClsContext
0x18004739c  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1800473a3  call    cs:__imp_CoCreateInstance
0x1800473a9  mov     ebx, eax
0x1800473ab  test    eax, eax
0x1800473ad  js      loc_1800474EB
0x1800473b3  mov     [rbp+var_30], 0
0x1800473bb  mov     rcx, [rbp+var_40]
0x1800473bf  mov     rax, [rcx]
0x1800473c2  lea     rdx, [rbp+var_30]
0x1800473c6  mov     [rsp+80h+ppv], rdx
0x1800473cb  xor     r9d, r9d
0x1800473ce  lea     r8, GUID_VendorMicrosoft
0x1800473d5  mov     rdx, rsi
0x1800473d8  mov     rax, [rax+20h]
0x1800473dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473e1  mov     ebx, eax
0x1800473e3  test    eax, eax
0x1800473e5  js      loc_1800474E1
0x1800473eb  mov     [rbp+var_38], 0
0x1800473f3  mov     rcx, [rbp+var_30]
0x1800473f7  mov     rax, [rcx]
0x1800473fa  lea     r8, [rbp+var_38]
0x1800473fe  xor     edx, edx
0x180047400  mov     rax, [rax+68h]
0x180047404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047409  mov     ebx, eax
0x18004740b  test    eax, eax
0x18004740d  js      loc_1800474D7
0x180047413  mov     [rbp+var_48], 0
0x18004741b  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x180047422  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x180047427  lea     r9, [rbp+var_48]; struct IWICBitmapSource **
0x18004742b  mov     r8, [rbp+var_40]; struct IWICImagingFactory *
0x18004742f  lea     rdx, [rbp+var_20]; struct _GUID
0x180047433  mov     rcx, [rbp+var_38]; struct IWICBitmapSource *
0x180047437  call    ?ConvertIWICBitmapSourcePixelFormat@@YAJPEAUIWICBitmapSource@@U_GUID@@PEAUIWICImagingFactory@@PEAPEAU1@@Z; ConvertIWICBitmapSourcePixelFormat(IWICBitmapSource *,_GUID,IWICImagingFactory *,IWICBitmapSource * *)
0x18004743c  mov     ebx, eax
0x18004743e  test    eax, eax
0x180047440  js      loc_1800474CD
0x180047446  mov     [rbp+var_50], 0
0x18004744e  mov     rcx, [rbp+var_30]; struct IWICBitmapDecoder *
0x180047452  call    ?WICIsOrientationSupported@@YA_NPEAUIWICBitmapDecoder@@@Z; WICIsOrientationSupported(IWICBitmapDecoder *)
0x180047457  test    al, al
0x180047459  jz      short loc_1800474A3
0x18004745b  mov     qword ptr [rbp+var_20.Data1], 0
0x180047463  mov     rcx, [rbp+var_38]
0x180047467  mov     rax, [rcx]
0x18004746a  lea     rdx, [rbp+var_20]
0x18004746e  mov     rax, [rax+40h]
0x180047472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047477  mov     ebx, eax
0x180047479  test    eax, eax
0x18004747b  js      short loc_180047494
0x18004747d  lea     r9, [rbp+var_50]; struct IWICBitmapSource **
0x180047481  mov     r8, qword ptr [rbp+var_20.Data1]; struct IWICMetadataQueryReader *
0x180047485  mov     rdx, [rbp+var_48]; struct IWICBitmapSource *
0x180047489  mov     rcx, [rbp+var_40]; struct IWICImagingFactory *
0x18004748d  call    ?WICCreateOrientedBitmapSource@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAUIWICMetadataQueryReader@@PEAPEAU2@@Z; WICCreateOrientedBitmapSource(IWICImagingFactory *,IWICBitmapSource *,IWICMetadataQueryReader *,IWICBitmapSource * *)
0x180047492  mov     ebx, eax
0x180047494  lea     rcx, [rbp+var_20]
0x180047498  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004749d  test    ebx, ebx
0x18004749f  jns     short loc_1800474B5
0x1800474a1  jmp     short loc_1800474C3
0x1800474a3  mov     rdx, [rbp+var_48]; struct IUnknown *
0x1800474a7  test    rdx, rdx
0x1800474aa  jz      short loc_1800474B5
0x1800474ac  lea     rcx, [rbp+var_50]; struct IUnknown **
0x1800474b0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800474b5  mov     rdx, rdi; HBITMAP *
0x1800474b8  mov     rcx, [rbp+var_50]; struct IWICBitmapSource *
0x1800474bc  call    ?Convert32bppIWICBitmapSourceToHBITMAP@@YAJPEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; Convert32bppIWICBitmapSourceToHBITMAP(IWICBitmapSource *,HBITMAP__ * *)
0x1800474c1  mov     ebx, eax
0x1800474c3  lea     rcx, [rbp+var_50]
0x1800474c7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800474cc  nop
0x1800474cd  lea     rcx, [rbp+var_48]
0x1800474d1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800474d6  nop
0x1800474d7  lea     rcx, [rbp+var_38]
0x1800474db  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800474e0  nop
0x1800474e1  lea     rcx, [rbp+var_30]
0x1800474e5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800474ea  nop
0x1800474eb  lea     rcx, [rbp+var_40]
0x1800474ef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800474f4  mov     eax, ebx
0x1800474f6  mov     rcx, [rbp+var_10]
0x1800474fa  xor     rcx, rsp; StackCookie
0x1800474fd  call    __security_check_cookie
0x180047502  mov     rbx, [rsp+80h+arg_10]
0x18004750a  add     rsp, 80h
0x180047511  pop     rdi
0x180047512  pop     rsi
0x180047513  pop     rbp
0x180047514  retn
```

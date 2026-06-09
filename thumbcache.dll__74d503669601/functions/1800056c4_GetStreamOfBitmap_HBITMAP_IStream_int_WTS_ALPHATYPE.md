# GetStreamOfBitmap(HBITMAP__ *,IStream * *,int,WTS_ALPHATYPE)

- ea: `0x1800056c4`
- end: `0x1800059a2`
- name: `?GetStreamOfBitmap@@YAJPEAUHBITMAP__@@PEAPEAUIStream@@HW4WTS_ALPHATYPE@@@Z`
- size: `734`
- prototype: `__int64 __fastcall(HBITMAP, struct IStream **, int, enum WTS_ALPHATYPE)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800056b0`

## callees

- `0x180003624`
- `0x1800056c4`
- `0x1800067ec`
- `0x18002bac4`
- `0x18002cdcc`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005754`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005754`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180005716`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180005716`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetStreamOfBitmap(HBITMAP a1, struct IStream **a2, __int64 a3, enum WTS_ALPHATYPE a4)
{
  HRESULT v7; // ebx
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, HBITMAP, _QWORD, __int64, struct IWICBitmap **); // rbx
  __int64 v10; // r9
  int v11; // eax
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, GUID *, GUID *, int *); // rbx
  struct IStream *v14; // rax
  __int64 v15; // rcx
  struct IWICBitmap *v16; // rcx
  LPVOID v17; // rcx
  LPSTREAM v18; // rcx
  GUID v20; // [rsp+30h] [rbp-29h] BYREF
  int v21[2]; // [rsp+40h] [rbp-19h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-9h] BYREF
  struct IWICBitmap *v24; // [rsp+58h] [rbp-1h] BYREF
  GUID v25; // [rsp+60h] [rbp+7h] BYREF
  GUID v26; // [rsp+70h] [rbp+17h]
  unsigned int JPEGQuality; // [rsp+80h] [rbp+27h]

  *a2 = 0;
  ppstm = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
  v7 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v7 >= 0 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v7 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
    if ( v7 >= 0 )
    {
      v24 = 0;
      v8 = ppv;
      v9 = *(__int64 (__fastcall **)(LPVOID, HBITMAP, _QWORD, __int64, struct IWICBitmap **))(*(_QWORD *)ppv + 168LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v10 = 2;
      if ( a4 != WTSAT_RGB )
        v10 = 0;
      v7 = v9(v8, a1, 0, v10, &v24);
      if ( v7 >= 0 )
      {
        v11 = a4 != WTSAT_RGB;
        v21[0] = v11;
        if ( a4 == WTSAT_UNKNOWN )
        {
          v7 = FindAndRepairInvalidAlpha(v24, v21);
          v11 = v21[0];
        }
        if ( v7 >= 0 )
        {
          JPEGQuality = 0;
          if ( v11 )
          {
            v25 = GUID_ContainerFormatPng;
            v26 = GUID_WICPixelFormat32bppBGRA;
          }
          else
          {
            v25 = GUID_ContainerFormatJpeg;
            v26 = GUID_WICPixelFormat24bppRGB;
            JPEGQuality = GetJPEGQuality();
          }
          *(_QWORD *)v21 = 0;
          v12 = ppv;
          v13 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, int *))(*(_QWORD *)ppv + 64LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v21);
          v7 = v13(v12, &v25, &GUID_VendorMicrosoft, v21);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(_QWORD, LPSTREAM, __int64))(**(_QWORD **)v21 + 24LL))(
                   *(_QWORD *)v21,
                   ppstm,
                   2);
            if ( v7 >= 0 )
            {
              v20 = v26;
              v7 = AddFrameToWICBitmap(ppv, *(_QWORD *)v21, v24, &v20, 2);
              if ( v7 >= 0 )
              {
                v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 88LL))(*(_QWORD *)v21);
                if ( v7 >= 0 )
                {
                  v7 = (*(__int64 (__fastcall **)(LPSTREAM, __int64, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(
                         ppstm,
                         `GetStreamOfWICBitmapSourceWithOptions'::`23'::lnBeginning,
                         0,
                         0);
                  if ( v7 >= 0 )
                  {
                    v14 = ppstm;
                    ppstm = 0;
                    *a2 = v14;
                  }
                }
              }
            }
          }
          v15 = *(_QWORD *)v21;
          if ( *(_QWORD *)v21 )
          {
            *(_QWORD *)v21 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
        }
      }
      v16 = v24;
      if ( v24 )
      {
        v24 = 0;
        ((void (__fastcall *)(struct IWICBitmap *))v16->lpVtbl->Release)(v16);
      }
    }
    v17 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  v18 = ppstm;
  if ( ppstm )
  {
    ppstm = 0;
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800056c4  mov     [rsp-8+arg_10], rbx
0x1800056c9  push    rbp
0x1800056ca  push    rsi
0x1800056cb  push    rdi
0x1800056cc  push    r14
0x1800056ce  push    r15
0x1800056d0  lea     rbp, [rsp-37h]
0x1800056d5  sub     rsp, 90h
0x1800056dc  mov     rax, cs:__security_cookie
0x1800056e3  xor     rax, rsp
0x1800056e6  mov     [rbp+57h+var_28], rax
0x1800056ea  mov     esi, r9d
0x1800056ed  mov     r14, rdx
0x1800056f0  mov     r15, rcx
0x1800056f3  mov     qword ptr [rdx], 0
0x1800056fa  mov     [rbp+57h+ppstm], 0
0x180005702  lea     rcx, [rbp+57h+ppstm]
0x180005706  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000570b  lea     r8, [rbp+57h+ppstm]; ppstm
0x18000570f  mov     edx, 1; fDeleteOnRelease
0x180005714  xor     ecx, ecx; hGlobal
0x180005716  call    cs:__imp_CreateStreamOnHGlobal
0x18000571c  mov     ebx, eax
0x18000571e  test    eax, eax
0x180005720  js      loc_180005922
0x180005726  mov     [rbp+57h+var_60], 0
0x18000572e  lea     rcx, [rbp+57h+var_60]
0x180005732  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005737  lea     rax, [rbp+57h+var_60]
0x18000573b  mov     [rsp+0B0h+ppv], rax; ppv
0x180005740  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180005747  xor     edx, edx; pUnkOuter
0x180005749  lea     r8d, [rdx+1]; dwClsContext
0x18000574d  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180005754  call    cs:__imp_CoCreateInstance
0x18000575a  mov     ebx, eax
0x18000575c  test    eax, eax
0x18000575e  js      loc_180005904
0x180005764  mov     [rbp+57h+var_58], 0
0x18000576c  mov     rdi, [rbp+57h+var_60]
0x180005770  mov     rax, [rdi]
0x180005773  mov     rbx, [rax+0A8h]
0x18000577a  lea     rcx, [rbp+57h+var_58]
0x18000577e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005783  mov     r9d, 2
0x180005789  xor     r8d, r8d
0x18000578c  cmp     esi, 1
0x18000578f  cmovnz  r9d, r8d
0x180005793  lea     rax, [rbp+57h+var_58]
0x180005797  mov     [rsp+0B0h+ppv], rax
0x18000579c  mov     rdx, r15
0x18000579f  mov     rcx, rdi
0x1800057a2  mov     rax, rbx
0x1800057a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057aa  mov     ebx, eax
0x1800057ac  test    eax, eax
0x1800057ae  js      loc_1800058E6
0x1800057b4  xor     eax, eax
0x1800057b6  cmp     esi, 1
0x1800057b9  setnz   al
0x1800057bc  mov     [rbp+57h+var_70], eax
0x1800057bf  test    esi, esi
0x1800057c1  jz      loc_18000598A
0x1800057c7  test    ebx, ebx
0x1800057c9  js      loc_1800058E6
0x1800057cf  mov     [rbp+57h+var_30], 0
0x1800057d6  test    eax, eax
0x1800057d8  jz      loc_180005965
0x1800057de  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatPng.Data1
0x1800057e5  movdqu  [rbp+57h+var_50], xmm0
0x1800057ea  movups  xmm1, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x1800057f1  movdqu  [rbp+57h+var_40], xmm1
0x1800057f6  mov     qword ptr [rbp+57h+var_70], 0
0x1800057fe  mov     rdi, [rbp+57h+var_60]
0x180005802  mov     rax, [rdi]
0x180005805  mov     rbx, [rax+40h]
0x180005809  lea     rcx, [rbp+57h+var_70]
0x18000580d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005812  lea     r9, [rbp+57h+var_70]
0x180005816  lea     r8, GUID_VendorMicrosoft
0x18000581d  lea     rdx, [rbp+57h+var_50]
0x180005821  mov     rcx, rdi
0x180005824  mov     rax, rbx
0x180005827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000582c  mov     ebx, eax
0x18000582e  test    eax, eax
0x180005830  js      loc_1800058C8
0x180005836  mov     rcx, qword ptr [rbp+57h+var_70]
0x18000583a  mov     rax, [rcx]
0x18000583d  mov     edi, 2
0x180005842  mov     r8d, edi
0x180005845  mov     rdx, [rbp+57h+ppstm]
0x180005849  mov     rax, [rax+18h]
0x18000584d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005852  mov     ebx, eax
0x180005854  test    eax, eax
0x180005856  js      short loc_1800058C8
0x180005858  movups  xmm0, [rbp+57h+var_40]
0x18000585c  movdqu  [rbp+57h+var_80], xmm0
0x180005861  mov     dword ptr [rsp+0B0h+ppv], edi
0x180005865  lea     r9, [rbp+57h+var_80]
0x180005869  mov     r8, [rbp+57h+var_58]
0x18000586d  mov     rdx, qword ptr [rbp+57h+var_70]
0x180005871  mov     rcx, [rbp+57h+var_60]
0x180005875  call    ?AddFrameToWICBitmap@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapEncoder@@PEAUIWICBitmapSource@@U_GUID@@W4EncodingOptions@@@Z; AddFrameToWICBitmap(IWICImagingFactory *,IWICBitmapEncoder *,IWICBitmapSource *,_GUID,EncodingOptions)
0x18000587a  mov     ebx, eax
0x18000587c  test    eax, eax
0x18000587e  js      short loc_1800058C8
0x180005880  mov     rcx, qword ptr [rbp+57h+var_70]
0x180005884  mov     rax, [rcx]
0x180005887  mov     rax, [rax+58h]
0x18000588b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005890  mov     ebx, eax
0x180005892  test    eax, eax
0x180005894  js      short loc_1800058C8
0x180005896  mov     rcx, [rbp+57h+ppstm]
0x18000589a  mov     rax, [rcx]
0x18000589d  xor     r9d, r9d
0x1800058a0  xor     r8d, r8d
0x1800058a3  mov     rdx, cs:?lnBeginning@?BH@??GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U4@W4EncodingOptions@@PEAPEAUIStream@@@Z@4T_LARGE_INTEGER@@B; _LARGE_INTEGER const `GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)'::`23'::lnBeginning
0x1800058aa  mov     rax, [rax+28h]
0x1800058ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058b3  mov     ebx, eax
0x1800058b5  test    eax, eax
0x1800058b7  js      short loc_1800058C8
0x1800058b9  mov     rax, [rbp+57h+ppstm]
0x1800058bd  mov     [rbp+57h+ppstm], 0
0x1800058c5  mov     [r14], rax
0x1800058c8  mov     rcx, qword ptr [rbp+57h+var_70]
0x1800058cc  test    rcx, rcx
0x1800058cf  jz      short loc_1800058E6
0x1800058d1  mov     qword ptr [rbp+57h+var_70], 0
0x1800058d9  mov     rax, [rcx]
0x1800058dc  mov     rax, [rax+10h]
0x1800058e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e5  nop
0x1800058e6  mov     rcx, [rbp+57h+var_58]
0x1800058ea  test    rcx, rcx
0x1800058ed  jz      short loc_180005904
0x1800058ef  mov     [rbp+57h+var_58], 0
0x1800058f7  mov     rax, [rcx]
0x1800058fa  mov     rax, [rax+10h]
0x1800058fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005903  nop
0x180005904  mov     rcx, [rbp+57h+var_60]
0x180005908  test    rcx, rcx
0x18000590b  jz      short loc_180005922
0x18000590d  mov     [rbp+57h+var_60], 0
0x180005915  mov     rax, [rcx]
0x180005918  mov     rax, [rax+10h]
0x18000591c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005921  nop
0x180005922  mov     rcx, [rbp+57h+ppstm]
0x180005926  test    rcx, rcx
0x180005929  jz      short loc_180005940
0x18000592b  mov     [rbp+57h+ppstm], 0
0x180005933  mov     rax, [rcx]
0x180005936  mov     rax, [rax+10h]
0x18000593a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000593f  nop
0x180005940  mov     eax, ebx
0x180005942  mov     rcx, [rbp+57h+var_28]
0x180005946  xor     rcx, rsp; StackCookie
0x180005949  call    __security_check_cookie
0x18000594e  mov     rbx, [rsp+0B0h+arg_10]
0x180005956  add     rsp, 90h
0x18000595d  pop     r15
0x18000595f  pop     r14
0x180005961  pop     rdi
0x180005962  pop     rsi
0x180005963  pop     rbp
0x180005964  retn
0x180005965  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatJpeg.Data1
0x18000596c  movdqu  [rbp+57h+var_50], xmm0
0x180005971  movups  xmm1, xmmword ptr cs:GUID_WICPixelFormat24bppRGB.Data1
0x180005978  movdqu  [rbp+57h+var_40], xmm1
0x18000597d  call    ?GetJPEGQuality@@YAKXZ; GetJPEGQuality(void)
0x180005982  mov     [rbp+57h+var_30], eax
0x180005985  jmp     loc_1800057F6
0x18000598a  lea     rdx, [rbp+57h+var_70]; int *
0x18000598e  mov     rcx, [rbp+57h+var_58]; struct IWICBitmap *
0x180005992  call    ?FindAndRepairInvalidAlpha@@YAJPEAUIWICBitmap@@PEAH@Z; FindAndRepairInvalidAlpha(IWICBitmap *,int *)
0x180005997  mov     ebx, eax
0x180005999  mov     eax, [rbp+57h+var_70]
0x18000599c  jmp     loc_1800057C7
```

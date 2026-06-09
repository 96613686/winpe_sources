# CShellProviderResults::CWMCUPnPItem::GetJPEGStream(IShellItemImageFactory *,IStream * *)

- ea: `0x1400785a4`
- end: `0x1400786a5`
- name: `?GetJPEGStream@CWMCUPnPItem@CShellProviderResults@@AEAAJPEAUIShellItemImageFactory@@PEAPEAUIStream@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(CShellProviderResults::CWMCUPnPItem *__hidden this, struct IShellItemImageFactory *, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140079314`

## callees

- `0x140024688`
- `0x140074c68`
- `0x1400785a4`
- `0x14009e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1400785e7`
- `ole32!CoCreateInstance` at `0x1400785e7`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x140078680`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x140078680`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CShellProviderResults::CWMCUPnPItem::GetJPEGStream(
        CShellProviderResults::CWMCUPnPItem *this,
        struct IShellItemImageFactory *a2,
        struct IStream **a3)
{
  HRESULT Instance; // ebx
  struct IWICBitmap *v8; // [rsp+30h] [rbp-10h] BYREF
  HGDIOBJ ho; // [rsp+38h] [rbp-8h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+78h] [rbp+38h] BYREF

  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               0x17u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    ho = 0;
    v8 = (struct IWICBitmap *)0x10000000100LL;
    Instance = ((__int64 (__fastcall *)(struct IShellItemImageFactory *, __int64, _QWORD, HGDIOBJ *))a2->lpVtbl->GetImage)(
                 a2,
                 0x10000000100LL,
                 0,
                 &ho);
    if ( Instance >= 0 )
    {
      v8 = 0;
      Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, HGDIOBJ, _QWORD, _QWORD, struct IWICBitmap **))ppv->lpVtbl->CreateBitmapFromHBITMAP)(
                   ppv,
                   ho,
                   0,
                   0,
                   &v8);
      if ( Instance >= 0 )
        Instance = CShellProviderResults::CWMCUPnPItem::ConvertFrameToJPEG(this, ppv, v8, a3);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v8);
    }
    DeleteObject(ho);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1400785a4  mov     [rsp-18h+arg_0], rbx
0x1400785a9  mov     [rsp-18h+arg_8], rsi
0x1400785ae  push    rbp
0x1400785af  push    rdi
0x1400785b0  push    r14
0x1400785b2  mov     rbp, rsp
0x1400785b5  sub     rsp, 40h
0x1400785b9  mov     rsi, r8
0x1400785bc  mov     rdi, rdx
0x1400785bf  mov     r14, rcx
0x1400785c2  mov     [rbp+arg_18], 0
0x1400785ca  lea     rax, [rbp+arg_18]
0x1400785ce  mov     [rsp+40h+ppv], rax; ppv
0x1400785d3  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1400785da  xor     edx, edx; pUnkOuter
0x1400785dc  lea     r8d, [rdx+17h]; dwClsContext
0x1400785e0  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1400785e7  call    cs:__imp_CoCreateInstance
0x1400785ed  mov     ebx, eax
0x1400785ef  test    eax, eax
0x1400785f1  js      loc_140078687
0x1400785f7  mov     [rbp+ho], 0
0x1400785ff  mov     eax, 100h
0x140078604  mov     dword ptr [rbp+var_10], eax
0x140078607  mov     dword ptr [rbp+var_10+4], eax
0x14007860a  mov     rax, [rdi]
0x14007860d  lea     r9, [rbp+ho]
0x140078611  xor     r8d, r8d
0x140078614  mov     rdx, [rbp+var_10]
0x140078618  mov     rcx, rdi
0x14007861b  mov     rax, [rax+18h]
0x14007861f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140078624  mov     ebx, eax
0x140078626  test    eax, eax
0x140078628  js      short loc_14007867C
0x14007862a  mov     [rbp+var_10], 0
0x140078632  mov     rcx, [rbp+arg_18]
0x140078636  mov     rax, [rcx]
0x140078639  lea     rdx, [rbp+var_10]
0x14007863d  mov     [rsp+40h+ppv], rdx
0x140078642  xor     r9d, r9d
0x140078645  xor     r8d, r8d
0x140078648  mov     rdx, [rbp+ho]
0x14007864c  mov     rax, [rax+0A8h]
0x140078653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140078658  mov     ebx, eax
0x14007865a  test    eax, eax
0x14007865c  js      short loc_140078673
0x14007865e  mov     r9, rsi; struct IStream **
0x140078661  mov     r8, [rbp+var_10]; struct IWICBitmap *
0x140078665  mov     rdx, [rbp+arg_18]; struct IWICImagingFactory *
0x140078669  mov     rcx, r14; this
0x14007866c  call    ?ConvertFrameToJPEG@CWMCUPnPItem@CShellProviderResults@@AEAAJPEAUIWICImagingFactory@@PEAUIWICBitmap@@PEAPEAUIStream@@@Z; CShellProviderResults::CWMCUPnPItem::ConvertFrameToJPEG(IWICImagingFactory *,IWICBitmap *,IStream * *)
0x140078671  mov     ebx, eax
0x140078673  lea     rcx, [rbp+var_10]
0x140078677  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007867c  mov     rcx, [rbp+ho]; ho
0x140078680  call    cs:__imp_DeleteObject
0x140078686  nop
0x140078687  lea     rcx, [rbp+arg_18]
0x14007868b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140078690  mov     eax, ebx
0x140078692  mov     rbx, [rsp+40h+arg_0]
0x140078697  mov     rsi, [rsp+40h+arg_8]
0x14007869c  add     rsp, 40h
0x1400786a0  pop     r14
0x1400786a2  pop     rdi
0x1400786a3  pop     rbp
0x1400786a4  retn
```

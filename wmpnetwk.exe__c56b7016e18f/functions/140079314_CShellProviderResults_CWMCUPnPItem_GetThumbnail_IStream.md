# CShellProviderResults::CWMCUPnPItem::GetThumbnail(IStream * *)

- ea: `0x140079314`
- end: `0x1400793c9`
- name: `?GetThumbnail@CWMCUPnPItem@CShellProviderResults@@AEAAJPEAPEAUIStream@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(CShellProviderResults::CWMCUPnPItem *__hidden this, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140077c30`

## callees

- `0x140024688`
- `0x1400785a4`
- `0x140079314`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x1400793b1`
- `ole32!PropVariantClear` at `0x1400793b1`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x140079384`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x140079384`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShellProviderResults::CWMCUPnPItem::GetThumbnail(
        CShellProviderResults::CWMCUPnPItem *this,
        struct IStream **a2)
{
  HRESULT JPEGStream; // ebx
  PCWSTR pszPath[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+30h] [rbp-18h]
  void *ppv; // [rsp+50h] [rbp+8h] BYREF

  *(_OWORD *)pszPath = 0;
  v7 = 0;
  JPEGStream = (*(__int64 (__fastcall **)(_QWORD, const PROPERTYKEY *, PCWSTR *))(**((_QWORD **)this + 14) + 40LL))(
                 *((_QWORD *)this + 14),
                 &PKEY_ItemUrl,
                 pszPath);
  if ( JPEGStream >= 0 )
  {
    if ( LOWORD(pszPath[0]) == 31 )
    {
      ppv = 0;
      JPEGStream = SHCreateItemFromParsingName(pszPath[1], 0, &GUID_bcc18b79_ba16_442f_80c4_8a59c30c463b, &ppv);
      if ( JPEGStream >= 0 )
        JPEGStream = CShellProviderResults::CWMCUPnPItem::GetJPEGStream(this, (struct IShellItemImageFactory *)ppv, a2);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    }
    else
    {
      JPEGStream = -2147023728;
    }
  }
  PropVariantClear((PROPVARIANT *)pszPath);
  return (unsigned int)JPEGStream;
}

```

## disassembly

```asm
0x140079314  mov     r11, rsp
0x140079317  mov     [r11+10h], rbx
0x14007931b  mov     [r11+18h], rsi
0x14007931f  push    rdi
0x140079320  sub     rsp, 40h
0x140079324  mov     rsi, rdx
0x140079327  mov     rdi, rcx
0x14007932a  xorps   xmm0, xmm0
0x14007932d  xor     eax, eax
0x14007932f  movups  xmmword ptr [rsp+48h+pszPath], xmm0
0x140079334  mov     [r11-18h], rax
0x140079338  mov     rcx, [rcx+70h]
0x14007933c  mov     rax, [rcx]
0x14007933f  lea     r8, [r11-28h]
0x140079343  lea     rdx, PKEY_ItemUrl
0x14007934a  mov     rax, [rax+28h]
0x14007934e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079353  mov     ebx, eax
0x140079355  test    eax, eax
0x140079357  js      short loc_1400793AC
0x140079359  cmp     word ptr [rsp+48h+pszPath], 1Fh
0x14007935f  jz      short loc_140079368
0x140079361  mov     ebx, 80070490h
0x140079366  jmp     short loc_1400793AC
0x140079368  mov     [rsp+48h+ppv], 0
0x140079371  lea     r9, [rsp+48h+ppv]; ppv
0x140079376  lea     r8, _GUID_bcc18b79_ba16_442f_80c4_8a59c30c463b; riid
0x14007937d  xor     edx, edx; pbc
0x14007937f  mov     rcx, [rsp+48h+pszPath+8]; pszPath
0x140079384  call    cs:__imp_SHCreateItemFromParsingName
0x14007938a  mov     ebx, eax
0x14007938c  test    eax, eax
0x14007938e  js      short loc_1400793A2
0x140079390  mov     r8, rsi; struct IStream **
0x140079393  mov     rdx, [rsp+48h+ppv]; struct IShellItemImageFactory *
0x140079398  mov     rcx, rdi; this
0x14007939b  call    ?GetJPEGStream@CWMCUPnPItem@CShellProviderResults@@AEAAJPEAUIShellItemImageFactory@@PEAPEAUIStream@@@Z; CShellProviderResults::CWMCUPnPItem::GetJPEGStream(IShellItemImageFactory *,IStream * *)
0x1400793a0  mov     ebx, eax
0x1400793a2  lea     rcx, [rsp+48h+ppv]
0x1400793a7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400793ac  lea     rcx, [rsp+48h+pszPath]; pvar
0x1400793b1  call    cs:__imp_PropVariantClear
0x1400793b7  mov     eax, ebx
0x1400793b9  mov     rbx, [rsp+48h+arg_8]
0x1400793be  mov     rsi, [rsp+48h+arg_10]
0x1400793c3  add     rsp, 40h
0x1400793c7  pop     rdi
0x1400793c8  retn
```

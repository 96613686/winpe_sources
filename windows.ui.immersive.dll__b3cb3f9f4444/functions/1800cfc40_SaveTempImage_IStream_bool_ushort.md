# _SaveTempImage(IStream *,bool,ushort * *)

- ea: `0x1800cfc40`
- end: `0x1800cfdd9`
- name: `?_SaveTempImage@@YAJPEAUIStream@@_NPEAPEAG@Z`
- size: `409`
- prototype: `int(struct IStream *, bool, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800cf6e8`

## callees

- `0x18001b760`
- `0x180029e80`
- `0x18002e93c`
- `0x1800343ec`
- `0x180054130`
- `0x1800ceab4`
- `0x1800cfc40`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800cfd70`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800cfd70`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800cfd8c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800cfd8c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800cfcd8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800cfcd8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800cfcb2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800cfcb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _SaveTempImage(struct IStream *a1, char a2, unsigned __int16 **a3)
{
  HRESULT TempFolder; // ebx
  const unsigned __int16 *v7; // r8
  struct IShellItem *v9; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR pszPathIn; // [rsp+28h] [rbp-D8h] BYREF
  GUID pguid; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+250h] [rbp+150h] BYREF

  *a3 = 0;
  v9 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  TempFolder = _GetTempFolder(&v9);
  if ( TempFolder >= 0 )
  {
    pguid = 0;
    TempFolder = CoCreateGuid(&pguid);
    if ( TempFolder >= 0 )
    {
      StringFromGUID2(&pguid, sz, 260);
      v7 = L".mp4";
      if ( !a2 )
        v7 = L".bmp";
      TempFolder = StringCchCatW(sz, 0x104u, v7);
      if ( TempFolder >= 0 )
      {
        TempFolder = SaveStreamToFolder(v9, a1, sz, 1);
        if ( TempFolder >= 0 )
        {
          pszPathIn = 0;
          TempFolder = ((__int64 (__fastcall *)(struct IShellItem *, __int64, PCWSTR *))v9->lpVtbl->GetDisplayName)(
                         v9,
                         2147844096LL,
                         &pszPathIn);
          if ( TempFolder >= 0 )
          {
            TempFolder = PathCchCombine(pszPathOut, 0x104u, pszPathIn, sz);
            if ( TempFolder >= 0 )
              TempFolder = SHStrDupW(pszPathOut, a3);
          }
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pszPathIn);
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  return (unsigned int)TempFolder;
}

```

## disassembly

```asm
0x1800cfc40  mov     [rsp-8+arg_8], rbx
0x1800cfc45  mov     [rsp-8+arg_18], rsi
0x1800cfc4a  push    rbp
0x1800cfc4b  push    rdi
0x1800cfc4c  push    r14
0x1800cfc4e  lea     rbp, [rsp-370h]
0x1800cfc56  sub     rsp, 470h
0x1800cfc5d  mov     rax, cs:__security_cookie
0x1800cfc64  xor     rax, rsp
0x1800cfc67  mov     [rbp+380h+var_20], rax
0x1800cfc6e  mov     rdi, r8
0x1800cfc71  mov     r14b, dl
0x1800cfc74  mov     rsi, rcx
0x1800cfc77  mov     qword ptr [r8], 0
0x1800cfc7e  mov     [rsp+480h+var_460], 0
0x1800cfc87  lea     rcx, [rsp+480h+var_460]
0x1800cfc8c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cfc91  lea     rcx, [rsp+480h+var_460]; struct IShellItem **
0x1800cfc96  call    ?_GetTempFolder@@YAJPEAPEAUIShellItem@@@Z; _GetTempFolder(IShellItem * *)
0x1800cfc9b  mov     ebx, eax
0x1800cfc9d  test    eax, eax
0x1800cfc9f  js      loc_1800CFDA5
0x1800cfca5  xorps   xmm0, xmm0
0x1800cfca8  movups  xmmword ptr [rsp+480h+pguid.Data1], xmm0
0x1800cfcad  lea     rcx, [rsp+480h+pguid]; pguid
0x1800cfcb2  call    cs:__imp_CoCreateGuid
0x1800cfcb9  nop     dword ptr [rax+rax+00h]
0x1800cfcbe  mov     ebx, eax
0x1800cfcc0  test    eax, eax
0x1800cfcc2  js      loc_1800CFDA5
0x1800cfcc8  mov     r8d, 104h; cchMax
0x1800cfcce  lea     rdx, [rsp+480h+sz]; lpsz
0x1800cfcd3  lea     rcx, [rsp+480h+pguid]; rguid
0x1800cfcd8  call    cs:__imp_StringFromGUID2
0x1800cfcdf  nop     dword ptr [rax+rax+00h]
0x1800cfce4  lea     rax, aBmp; ".bmp"
0x1800cfceb  lea     r8, aMp4; ".mp4"
0x1800cfcf2  test    r14b, r14b
0x1800cfcf5  cmovz   r8, rax; unsigned __int16 *
0x1800cfcf9  mov     edx, 104h; unsigned __int64
0x1800cfcfe  lea     rcx, [rsp+480h+sz]; unsigned __int16 *
0x1800cfd03  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800cfd08  mov     ebx, eax
0x1800cfd0a  test    eax, eax
0x1800cfd0c  js      loc_1800CFDA5
0x1800cfd12  mov     r9d, 1
0x1800cfd18  lea     r8, [rsp+480h+sz]
0x1800cfd1d  mov     rdx, rsi
0x1800cfd20  mov     rcx, [rsp+480h+var_460]
0x1800cfd25  call    ?SaveStreamToFolder@@YAJPEAUIShellItem@@PEAUIStream@@PEBGW4SAVE_STREAM_MODE@@@Z; SaveStreamToFolder(IShellItem *,IStream *,ushort const *,SAVE_STREAM_MODE)
0x1800cfd2a  mov     ebx, eax
0x1800cfd2c  test    eax, eax
0x1800cfd2e  js      short loc_1800CFDA5
0x1800cfd30  mov     [rsp+480h+pszPathIn], 0
0x1800cfd39  mov     rcx, [rsp+480h+var_460]
0x1800cfd3e  mov     rax, [rcx]
0x1800cfd41  lea     r8, [rsp+480h+pszPathIn]
0x1800cfd46  mov     edx, 80058000h
0x1800cfd4b  mov     rax, [rax+28h]
0x1800cfd4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfd54  mov     ebx, eax
0x1800cfd56  test    eax, eax
0x1800cfd58  js      short loc_1800CFD9A
0x1800cfd5a  lea     r9, [rsp+480h+sz]; pszMore
0x1800cfd5f  mov     r8, [rsp+480h+pszPathIn]; pszPathIn
0x1800cfd64  mov     edx, 104h; cchPathOut
0x1800cfd69  lea     rcx, [rbp+380h+pszPathOut]; pszPathOut
0x1800cfd70  call    cs:__imp_PathCchCombine
0x1800cfd77  nop     dword ptr [rax+rax+00h]
0x1800cfd7c  mov     ebx, eax
0x1800cfd7e  test    eax, eax
0x1800cfd80  js      short loc_1800CFD9A
0x1800cfd82  mov     rdx, rdi; ppwsz
0x1800cfd85  lea     rcx, [rbp+380h+pszPathOut]; psz
0x1800cfd8c  call    cs:__imp_SHStrDupW
0x1800cfd93  nop     dword ptr [rax+rax+00h]
0x1800cfd98  mov     ebx, eax
0x1800cfd9a  lea     rcx, [rsp+480h+pszPathIn]
0x1800cfd9f  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800cfda4  nop
0x1800cfda5  lea     rcx, [rsp+480h+var_460]
0x1800cfdaa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cfdaf  mov     eax, ebx
0x1800cfdb1  mov     rcx, [rbp+380h+var_20]
0x1800cfdb8  xor     rcx, rsp; StackCookie
0x1800cfdbb  call    __security_check_cookie
0x1800cfdc0  lea     r11, [rsp+480h+var_10]
0x1800cfdc8  mov     rbx, [r11+28h]
0x1800cfdcc  mov     rsi, [r11+38h]
0x1800cfdd0  mov     rsp, r11
0x1800cfdd3  pop     r14
0x1800cfdd5  pop     rdi
0x1800cfdd6  pop     rbp
0x1800cfdd7  retn
```

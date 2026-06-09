# CPicturePasswordDUIHost::_ReloadTeachingBackgroundAsync(void)

- ea: `0x1800121f0`
- end: `0x18001232f`
- name: `?_ReloadTeachingBackgroundAsync@CPicturePasswordDUIHost@@IEAAJXZ`
- size: `319`
- prototype: `__int64 __fastcall(CPicturePasswordDUIHost *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f450`

## callees

- `0x1800043a4`
- `0x18000bcb8`
- `0x18000c100`
- `0x180010d04`
- `0x1800121f0`
- `0x180018910`

## import_xrefs

- `SHCORE!__imp_SHCreateStreamOnModuleResourceW` at `0x1800122c8`
- `SHCORE!__imp_SHCreateStreamOnModuleResourceW` at `0x1800122c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012270`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012270`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001228b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001228b`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180012227`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180012227`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012219`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012219`
- `DUI70!StrToID` at `0x18001220d`
- `DUI70!StrToID` at `0x18001220d`

## string_xrefs

- `0x180012263`: `imageres.dll`

## pseudocode

```c
__int64 __fastcall CPicturePasswordDUIHost::_ReloadTeachingBackgroundAsync(CPicturePasswordDUIHost *this)
{
  int Instance; // ebx
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rax
  const struct tagSIZE *Extent; // rax
  const struct tagSIZE *v6; // rbp
  struct CLoadImageToFill **v7; // rdi
  CPrivateNotificationWindow *v8; // rcx
  HMODULE Library; // rax
  struct IStream *v11; // [rsp+58h] [rbp+10h] BYREF
  struct DirectUI::Value *v12; // [rsp+60h] [rbp+18h] BYREF

  Instance = 0;
  v12 = 0;
  v3 = StrToID(L"teachingContentViewer");
  Descendent = DirectUI::Element::FindDescendent(this, v3);
  Extent = DirectUI::Element::GetExtent(Descendent, &v12);
  v6 = Extent;
  if ( Extent->cx > 0 && Extent->cy > 0 )
  {
    v7 = (struct CLoadImageToFill **)((char *)this + 912);
    v8 = (CPrivateNotificationWindow *)*((_QWORD *)this + 114);
    if ( v8 )
    {
      CPrivateNotificationWindow::DisconnectAndRelease(v8);
      *v7 = 0;
    }
    if ( g_hinstImageRes )
      goto LABEL_11;
    Library = LoadLibraryExW(L"imageres.dll", 0, 0x802u);
    if ( Library
      && _InterlockedCompareExchange64((volatile signed __int64 *)&g_hinstImageRes, (signed __int64)Library, 0) )
    {
      FreeLibrary(Library);
    }
    if ( g_hinstImageRes )
    {
LABEL_11:
      v11 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
      Instance = SHCreateStreamOnModuleResourceW(&_ImageBase, 12345, L"Image", &v11);
      if ( Instance >= 0 )
      {
        Instance = CLoadImageToFill::CreateInstance(
                     v11,
                     v6,
                     (struct CPrivateNotificationWindowSink *)(((unsigned __int64)this + 440) & -(__int64)(this != 0)),
                     0x40Du,
                     v7);
        if ( Instance >= 0 )
          Instance = CLoadImageAsync::LoadImageAsync(*v7);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
    }
    else
    {
      Instance = -2147467259;
    }
  }
  CValuePtr::Release((CValuePtr *)&v12);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800121f0  mov     [rsp+arg_0], rbx
0x1800121f5  push    rbp
0x1800121f6  push    rsi
0x1800121f7  push    rdi
0x1800121f8  sub     rsp, 30h
0x1800121fc  mov     rsi, rcx
0x1800121ff  xor     ebx, ebx
0x180012201  lea     rcx, aTeachingconten_0; "teachingContentViewer"
0x180012208  mov     [rsp+48h+arg_10], rbx
0x18001220d  call    cs:__imp_StrToID
0x180012213  movzx   edx, ax
0x180012216  mov     rcx, rsi
0x180012219  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001221f  mov     rcx, rax
0x180012222  lea     rdx, [rsp+48h+arg_10]
0x180012227  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x18001222d  mov     rbp, rax
0x180012230  cmp     [rax], ebx
0x180012232  jle     loc_180012316
0x180012238  cmp     [rax+4], ebx
0x18001223b  jle     loc_180012316
0x180012241  lea     rdi, [rsi+390h]
0x180012248  mov     rcx, [rdi]; this
0x18001224b  test    rcx, rcx
0x18001224e  jz      short loc_180012258
0x180012250  call    ?DisconnectAndRelease@CPrivateNotificationWindow@@QEAAXXZ; CPrivateNotificationWindow::DisconnectAndRelease(void)
0x180012255  mov     [rdi], rbx
0x180012258  cmp     cs:?g_hinstImageRes@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hinstImageRes
0x18001225f  jnz     short loc_1800122A1
0x180012261  xor     edx, edx; hFile
0x180012263  lea     rcx, LibFileName; "imageres.dll"
0x18001226a  mov     r8d, 802h; dwFlags
0x180012270  call    cs:__imp_LoadLibraryExW
0x180012276  mov     rcx, rax; hLibModule
0x180012279  test    rax, rax
0x18001227c  jz      short loc_180012291
0x18001227e  xor     eax, eax
0x180012280  lock cmpxchg cs:?g_hinstImageRes@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hinstImageRes
0x180012289  jz      short loc_180012291
0x18001228b  call    cs:__imp_FreeLibrary
0x180012291  cmp     cs:?g_hinstImageRes@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hinstImageRes
0x180012298  jnz     short loc_1800122A1
0x18001229a  mov     ebx, 80004005h
0x18001229f  jmp     short loc_180012316
0x1800122a1  lea     rcx, [rsp+48h+arg_8]
0x1800122a6  mov     [rsp+48h+arg_8], rbx
0x1800122ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800122b0  lea     r9, [rsp+48h+arg_8]
0x1800122b5  mov     edx, 3039h
0x1800122ba  lea     r8, aImage; "Image"
0x1800122c1  lea     rcx, __ImageBase
0x1800122c8  call    cs:__imp_SHCreateStreamOnModuleResourceW
0x1800122ce  mov     ebx, eax
0x1800122d0  test    eax, eax
0x1800122d2  js      short loc_18001230C
0x1800122d4  mov     rcx, [rsp+48h+arg_8]; struct IStream *
0x1800122d9  lea     rax, [rsi+1B8h]
0x1800122e0  neg     rsi
0x1800122e3  mov     [rsp+48h+var_28], rdi; struct CLoadImageToFill **
0x1800122e8  mov     r9d, 40Dh; unsigned int
0x1800122ee  mov     rdx, rbp; struct tagSIZE *
0x1800122f1  sbb     r8, r8
0x1800122f4  and     r8, rax; struct CPrivateNotificationWindowSink *
0x1800122f7  call    ?CreateInstance@CLoadImageToFill@@SAJPEAUIStream@@AEBUtagSIZE@@PEAVCPrivateNotificationWindowSink@@IPEAPEAV1@@Z; CLoadImageToFill::CreateInstance(IStream *,tagSIZE const &,CPrivateNotificationWindowSink *,uint,CLoadImageToFill * *)
0x1800122fc  mov     ebx, eax
0x1800122fe  test    eax, eax
0x180012300  js      short loc_18001230C
0x180012302  mov     rcx, [rdi]; this
0x180012305  call    ?LoadImageAsync@CLoadImageAsync@@QEAAJXZ; CLoadImageAsync::LoadImageAsync(void)
0x18001230a  mov     ebx, eax
0x18001230c  lea     rcx, [rsp+48h+arg_8]
0x180012311  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012316  lea     rcx, [rsp+48h+arg_10]; this
0x18001231b  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180012320  mov     eax, ebx
0x180012322  mov     rbx, [rsp+48h+arg_0]
0x180012327  add     rsp, 30h
0x18001232b  pop     rdi
0x18001232c  pop     rsi
0x18001232d  pop     rbp
0x18001232e  retn
```

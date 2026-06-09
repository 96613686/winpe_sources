# CPreflistExtractImage::Extract(HBITMAP__ * *)

- ea: `0x180014230`
- end: `0x18001449e`
- name: `?Extract@CPreflistExtractImage@@UEAAJPEAPEAUHBITMAP__@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(CPreflistExtractImage *__hidden this, HBITMAP *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003458`
- `0x180014230`
- `0x18002d80e`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_OleLoadPicture` at `0x1800142a9`
- `OLEAUT32!__imp_OleLoadPicture` at `0x1800142a9`
- `GDI32!DeleteObject` at `0x180014431`
- `GDI32!DeleteObject` at `0x180014431`
- `GDI32!DeleteDC` at `0x180014424`
- `GDI32!DeleteDC` at `0x180014424`
- `GDI32!SelectObject` at `0x1800143b1`
- `GDI32!SelectObject` at `0x18001441b`
- `GDI32!SelectObject` at `0x1800143b1`
- `GDI32!SelectObject` at `0x18001441b`
- `GDI32!CreateDIBSection` at `0x1800143a2`
- `GDI32!CreateDIBSection` at `0x1800143a2`
- `GDI32!CreateCompatibleDC` at `0x1800142f1`
- `GDI32!CreateCompatibleDC` at `0x1800142f1`
- `USER32!ReleaseDC` at `0x1800142ff`
- `USER32!ReleaseDC` at `0x1800142ff`
- `USER32!GetDC` at `0x1800142e5`
- `USER32!GetDC` at `0x1800142e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPreflistExtractImage::Extract(CPreflistExtractImage *this, HBITMAP *a2)
{
  void (*v4)(void); // rax
  HDC DC; // rbx
  HDC CompatibleDC; // rsi
  HBITMAP v7; // r14
  HGDIOBJ v8; // rdi
  unsigned int v9; // ebx
  LPVOID lpvObj; // [rsp+60h] [rbp-D8h] BYREF
  int v12; // [rsp+68h] [rbp-D0h] BYREF
  int v13; // [rsp+6Ch] [rbp-CCh]
  LPSTREAM lpstream; // [rsp+70h] [rbp-C8h] BYREF
  void *ppvBits; // [rsp+78h] [rbp-C0h] BYREF
  BITMAPINFO pbmi; // [rsp+80h] [rbp-B8h] BYREF
  int v17; // [rsp+ACh] [rbp-8Ch]
  int v18; // [rsp+B0h] [rbp-88h]
  int v19; // [rsp+B4h] [rbp-84h]
  ProfileStoreException *v20; // [rsp+100h] [rbp-38h] BYREF

  lpstream = 0;
  lpvObj = 0;
  try
  {
    (*(void (**)(void))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 136LL))();
    OleLoadPicture(lpstream, 0, 0, &IID_IPicture, &lpvObj);
    v13 = 0;
    v12 = 0;
    v4 = *(void (**)(void))(*(_QWORD *)lpvObj + 48LL);
  }
  catch ( ProfileStoreException *v20 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpvObj);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpstream);
    return 2147500037LL;
  }
  v4();
  (*(void (__fastcall **)(LPVOID, int *))(*(_QWORD *)lpvObj + 56LL))(lpvObj, &v12);
  DC = GetDC(0);
  CompatibleDC = CreateCompatibleDC(DC);
  ReleaseDC(0, DC);
  ppvBits = 0;
  memset_0(&pbmi, 0, 0x7Cu);
  pbmi.bmiHeader.biSize = 124;
  pbmi.bmiHeader.biWidth = *((_DWORD *)this + 16);
  pbmi.bmiHeader.biHeight = -*((_DWORD *)this + 17);
  *(_DWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  pbmi.bmiHeader.biCompression = 3;
  pbmi.bmiColors[0] = (RGBQUAD)16711680;
  v17 = 65280;
  v18 = 255;
  v19 = -16777216;
  v7 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
  v8 = SelectObject(CompatibleDC, v7);
  v9 = (*(__int64 (__fastcall **)(LPVOID, HDC, _QWORD, _QWORD, int, int, _DWORD, _DWORD, int, int, _QWORD))(*(_QWORD *)lpvObj + 64LL))(
         lpvObj,
         CompatibleDC,
         0,
         (unsigned int)(*((_DWORD *)this + 17) - 1),
         *((_DWORD *)this + 16) - 1,
         -*((_DWORD *)this + 17),
         0,
         0,
         v13,
         v12,
         0);
  SelectObject(CompatibleDC, v8);
  DeleteDC(CompatibleDC);
  if ( v9 )
  {
    DeleteObject(v7);
    v7 = 0;
  }
  *a2 = v7;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpvObj);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpstream);
  return v9;
}

```

## disassembly

```asm
0x180014230  mov     [rsp+arg_10], rbx
0x180014235  mov     [rsp+arg_18], rsi
0x18001423a  push    rdi
0x18001423b  push    r12
0x18001423d  push    r13
0x18001423f  push    r14
0x180014241  push    r15
0x180014243  sub     rsp, 110h
0x18001424a  mov     rax, cs:__security_cookie
0x180014251  xor     rax, rsp
0x180014254  mov     [rsp+138h+var_30], rax
0x18001425c  mov     r12, rdx
0x18001425f  mov     r15, rcx
0x180014262  xor     edi, edi
0x180014264  mov     [rsp+138h+lpstream], rdi
0x180014269  mov     [rsp+138h+lpvObj], rdi
0x18001426e  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180014275  mov     rax, [rcx]
0x180014278  lea     rdx, [r15+50h]
0x18001427c  lea     r8, [rsp+138h+lpstream]
0x180014281  mov     rax, [rax+88h]
0x180014288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001428d  nop
0x18001428e  lea     rax, [rsp+138h+lpvObj]
0x180014293  mov     [rsp+138h+lplpvObj], rax; lplpvObj
0x180014298  lea     r9, IID_IPicture; riid
0x18001429f  xor     r8d, r8d; fRunmode
0x1800142a2  xor     edx, edx; lSize
0x1800142a4  mov     rcx, [rsp+138h+lpstream]; lpstream
0x1800142a9  call    cs:__imp_OleLoadPicture
0x1800142af  mov     [rsp+138h+var_CC], edi
0x1800142b3  mov     [rsp+138h+var_D0], edi
0x1800142b7  mov     rcx, [rsp+138h+lpvObj]
0x1800142bc  mov     rax, [rcx]
0x1800142bf  lea     rdx, [rsp+138h+var_CC]
0x1800142c4  mov     rax, [rax+30h]
0x1800142c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142cd  mov     rcx, [rsp+138h+lpvObj]
0x1800142d2  mov     rax, [rcx]
0x1800142d5  lea     rdx, [rsp+138h+var_D0]
0x1800142da  mov     rax, [rax+38h]
0x1800142de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e3  xor     ecx, ecx; hWnd
0x1800142e5  call    cs:__imp_GetDC
0x1800142eb  mov     rbx, rax
0x1800142ee  mov     rcx, rax; hdc
0x1800142f1  call    cs:__imp_CreateCompatibleDC
0x1800142f7  mov     rsi, rax
0x1800142fa  mov     rdx, rbx; hDC
0x1800142fd  xor     ecx, ecx; hWnd
0x1800142ff  call    cs:__imp_ReleaseDC
0x180014305  mov     [rsp+138h+ppvBits], rdi
0x18001430a  mov     ebx, 7Ch ; '|'
0x18001430f  mov     r8d, ebx; Size
0x180014312  xor     edx, edx; Val
0x180014314  lea     rcx, [rsp+138h+pbmi]; void *
0x18001431c  call    memset_0
0x180014321  mov     [rsp+138h+pbmi.bmiHeader.biSize], ebx
0x180014328  mov     ecx, [r15+40h]
0x18001432c  mov     [rsp+138h+pbmi.bmiHeader.biWidth], ecx
0x180014333  mov     eax, [r15+44h]
0x180014337  neg     eax
0x180014339  mov     [rsp+138h+pbmi.bmiHeader.biHeight], eax
0x180014340  lea     r13d, [rbx-7Bh]
0x180014344  mov     dword ptr [rsp+138h+pbmi.bmiHeader.biPlanes], 200001h
0x18001434f  mov     [rsp+138h+pbmi.bmiHeader.biCompression], 3
0x18001435a  mov     dword ptr [rsp+138h+pbmi.bmiColors.rgbBlue], 0FF0000h
0x180014365  mov     [rsp+138h+var_8C], 0FF00h
0x180014370  mov     [rsp+138h+var_88], 0FFh
0x18001437b  mov     [rsp+138h+var_84], 0FF000000h
0x180014386  mov     [rsp+138h+offset], edi; offset
0x18001438a  mov     [rsp+138h+lplpvObj], rdi; hSection
0x18001438f  lea     r9, [rsp+138h+ppvBits]; ppvBits
0x180014394  xor     r8d, r8d; usage
0x180014397  lea     rdx, [rsp+138h+pbmi]; pbmi
0x18001439f  mov     rcx, rsi; hdc
0x1800143a2  call    cs:__imp_CreateDIBSection
0x1800143a8  mov     r14, rax
0x1800143ab  mov     rdx, rax; h
0x1800143ae  mov     rcx, rsi; hdc
0x1800143b1  call    cs:__imp_SelectObject
0x1800143b7  mov     rdi, rax
0x1800143ba  mov     rcx, [rsp+138h+lpvObj]
0x1800143bf  mov     r10d, [rsp+138h+var_D0]
0x1800143c4  mov     r11d, [rsp+138h+var_CC]
0x1800143c9  mov     r9d, [r15+44h]
0x1800143cd  mov     rdx, [rcx]
0x1800143d0  mov     ebx, r9d
0x1800143d3  neg     ebx
0x1800143d5  mov     r8d, [r15+40h]
0x1800143d9  sub     r8d, r13d
0x1800143dc  dec     r9d
0x1800143df  mov     rax, [rdx+40h]
0x1800143e3  xor     r15d, r15d
0x1800143e6  mov     [rsp+138h+var_E8], r15
0x1800143eb  mov     [rsp+138h+var_F0], r10d
0x1800143f0  mov     [rsp+138h+var_F8], r11d
0x1800143f5  mov     [rsp+138h+var_100], r15d
0x1800143fa  mov     [rsp+138h+var_108], r15d
0x1800143ff  mov     [rsp+138h+offset], ebx
0x180014403  mov     dword ptr [rsp+138h+lplpvObj], r8d
0x180014408  xor     r8d, r8d
0x18001440b  mov     rdx, rsi
0x18001440e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014413  mov     ebx, eax
0x180014415  mov     rdx, rdi; h
0x180014418  mov     rcx, rsi; hdc
0x18001441b  call    cs:__imp_SelectObject
0x180014421  mov     rcx, rsi; hdc
0x180014424  call    cs:__imp_DeleteDC
0x18001442a  test    ebx, ebx
0x18001442c  jz      short loc_18001443A
0x18001442e  mov     rcx, r14; ho
0x180014431  call    cs:__imp_DeleteObject
0x180014437  mov     r14d, r15d
0x18001443a  mov     [r12], r14
0x18001443e  lea     rcx, [rsp+138h+lpvObj]
0x180014443  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014448  nop
0x180014449  lea     rcx, [rsp+138h+lpstream]
0x18001444e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014453  mov     eax, ebx
0x180014455  jmp     short loc_180014471
0x180014457  lea     rcx, [rsp+138h+lpvObj]
0x18001445c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014461  nop
0x180014462  lea     rcx, [rsp+138h+lpstream]
0x180014467  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001446c  mov     eax, 80004005h
0x180014471  mov     rcx, [rsp+138h+var_30]
0x180014479  xor     rcx, rsp; StackCookie
0x18001447c  call    __security_check_cookie
0x180014481  lea     r11, [rsp+138h+var_28]
0x180014489  mov     rbx, [r11+40h]
0x18001448d  mov     rsi, [r11+48h]
0x180014491  mov     rsp, r11
0x180014494  pop     r15
0x180014496  pop     r14
0x180014498  pop     r13
0x18001449a  pop     r12
0x18001449c  pop     rdi
0x18001449d  retn
```

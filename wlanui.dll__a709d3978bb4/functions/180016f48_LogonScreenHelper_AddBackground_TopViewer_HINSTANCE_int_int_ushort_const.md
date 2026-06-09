# LogonScreenHelper::AddBackground(TopViewer *,HINSTANCE__ *,int,int,ushort const *)

- ea: `0x180016f48`
- end: `0x180017163`
- name: `?AddBackground@LogonScreenHelper@@QEAAXPEAVTopViewer@@PEAUHINSTANCE__@@HHPEBG@Z`
- size: `539`
- prototype: `void(LogonScreenHelper *__hidden this, struct TopViewer *, HINSTANCE, int, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800176d0`

## callees

- `0x180016f48`
- `0x180017bc0`
- `0x18001bf40`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x18001701b`
- `KERNEL32!SizeofResource` at `0x18001701b`
- `KERNEL32!LoadResource` at `0x180017031`
- `KERNEL32!LoadResource` at `0x180017031`
- `KERNEL32!FindResourceW` at `0x180017003`
- `KERNEL32!FindResourceW` at `0x180017003`
- `KERNEL32!LockResource` at `0x180017043`
- `KERNEL32!LockResource` at `0x180017043`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180017057`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180017057`
- `USER32!GetWindowInfo` at `0x180016faf`
- `USER32!GetWindowInfo` at `0x180016faf`
- `gdiplus!GdipCreateBitmapFromStream` at `0x180017091`
- `gdiplus!GdipCreateBitmapFromStream` at `0x180017091`
- `gdiplus!GdipAlloc` at `0x18001706e`
- `gdiplus!GdipAlloc` at `0x18001706e`
- `gdiplus!GdiplusShutdown` at `0x180017136`
- `gdiplus!GdiplusShutdown` at `0x180017136`
- `gdiplus!GdiplusStartup` at `0x180016ff0`
- `gdiplus!GdiplusStartup` at `0x180016ff0`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180017123`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180017123`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001710a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001710a`
- `DUI70!StrToID` at `0x1800170fe`
- `DUI70!StrToID` at `0x1800170fe`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001712c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001712c`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180017110`

## string_xrefs

- `0x1800170f7`: `InsideFrame`

## pseudocode

```c
void __fastcall LogonScreenHelper::AddBackground(
        LogonScreenHelper *this,
        struct TopViewer *a2,
        HINSTANCE a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int16 *lpName)
{
  __int64 v6; // rcx
  LONG top; // r15d
  LONG left; // r12d
  LONG bottom; // r13d
  HRSRC ResourceW; // rax
  HRSRC v13; // rdi
  UINT v14; // esi
  HGLOBAL Resource; // rax
  const BYTE *v16; // rax
  IStream *v17; // rbx
  struct DirectUI::Value *v18; // rdi
  __int64 v19; // rsi
  int v20; // eax
  LogonScreenHelper *v21; // rcx
  unsigned __int16 v22; // ax
  DirectUI::Element *Descendent; // rax
  LONG right; // [rsp+40h] [rbp-79h]
  struct tagRECT v26; // [rsp+50h] [rbp-69h] BYREF
  __int64 v27; // [rsp+60h] [rbp-59h] BYREF
  int v28; // [rsp+68h] [rbp-51h] BYREF
  __int64 v29; // [rsp+70h] [rbp-49h]
  __int64 v30; // [rsp+78h] [rbp-41h]
  tagWINDOWINFO pwi; // [rsp+80h] [rbp-39h] BYREF

  v6 = *((_QWORD *)a2 + 35);
  memset(&pwi, 0, sizeof(pwi));
  pwi.cbSize = 60;
  GetWindowInfo(*(HWND *)(v6 + 8), &pwi);
  if ( lpName )
  {
    top = pwi.rcClient.top;
    left = pwi.rcClient.left;
    bottom = pwi.rcClient.bottom;
    right = pwi.rcClient.right;
    v27 = 0;
    v28 = 1;
    v29 = 0;
    v30 = 0;
    GdiplusStartup(&v27, &v28, 0);
    ResourceW = FindResourceW(a3, lpName, L"Image");
    v13 = ResourceW;
    if ( ResourceW )
    {
      v14 = SizeofResource(a3, ResourceW);
      if ( v14 )
      {
        Resource = LoadResource(a3, v13);
        if ( Resource )
        {
          v16 = (const BYTE *)LockResource(Resource);
          if ( v16 )
          {
            v17 = SHCreateMemStream(v16, v14);
            if ( v17 )
            {
              v18 = 0;
              v19 = GdipAlloc(24);
              if ( v19 )
              {
                *(_QWORD *)&v26.left = 0;
                *(_QWORD *)v19 = &Gdiplus::Image::`vftable';
                v20 = GdipCreateBitmapFromStream(v17, &v26);
                v21 = *(LogonScreenHelper **)&v26.left;
                *(_DWORD *)(v19 + 16) = v20;
                v26.right = right;
                *(_QWORD *)(v19 + 8) = v21;
                v26.left = left;
                v26.top = top;
                v26.bottom = bottom;
                v18 = LogonScreenHelper::CreateDuiBitmapFromGDIPlusBitmap(
                        v21,
                        (struct Gdiplus::Bitmap *)v19,
                        a4,
                        a5,
                        &v26);
                (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
              }
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)v17 + 16LL))(v17);
              if ( v18 )
              {
                v22 = StrToID(L"InsideFrame");
                Descendent = DirectUI::Element::FindDescendent(a2, v22);
                DirectUI::Element::SetValue(
                  Descendent,
                  (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
                  1,
                  v18);
                DirectUI::Value::Release(v18);
              }
            }
          }
        }
      }
    }
    GdiplusShutdown(v27);
  }
}

```

## disassembly

```asm
0x180016f48  mov     [rsp-8+arg_0], rbx
0x180016f4d  push    rbp
0x180016f4e  push    rsi
0x180016f4f  push    rdi
0x180016f50  push    r12
0x180016f52  push    r13
0x180016f54  push    r14
0x180016f56  push    r15
0x180016f58  lea     rbp, [rsp-17h]
0x180016f5d  sub     rsp, 0D0h
0x180016f64  mov     rax, cs:__security_cookie
0x180016f6b  xor     rax, rsp
0x180016f6e  mov     [rbp+47h+var_40], rax
0x180016f72  mov     rcx, [rdx+118h]
0x180016f79  xorps   xmm0, xmm0
0x180016f7c  mov     eax, [rbp+47h+arg_20]
0x180016f7f  mov     r14, rdx
0x180016f82  mov     rdi, [rbp+47h+lpName]
0x180016f86  lea     rdx, [rbp+47h+pwi]; pwi
0x180016f8a  movups  xmmword ptr [rbp+47h+pwi.cbSize], xmm0
0x180016f8e  mov     [rbp+47h+pwi.cbSize], 3Ch ; '<'
0x180016f95  mov     rbx, r8
0x180016f98  movups  xmmword ptr [rbp+47h+pwi.rcClient.bottom], xmm0
0x180016f9c  mov     [rbp+47h+var_B8], r9d
0x180016fa0  movups  xmmword ptr [rbp+47h+pwi.rcWindow.bottom], xmm0
0x180016fa4  mov     [rbp+47h+var_BC], eax
0x180016fa7  movups  xmmword ptr [rbp+47h+pwi.dwWindowStatus], xmm0
0x180016fab  mov     rcx, [rcx+8]; hwnd
0x180016faf  call    cs:__imp_GetWindowInfo
0x180016fb5  xor     esi, esi
0x180016fb7  test    rdi, rdi
0x180016fba  jz      loc_18001713C
0x180016fc0  mov     eax, [rbp+47h+pwi.rcClient.right]
0x180016fc3  lea     rdx, [rbp+47h+var_98]
0x180016fc7  mov     r15d, [rbp+47h+pwi.rcClient.top]
0x180016fcb  lea     rcx, [rbp+47h+var_A0]
0x180016fcf  mov     r12d, [rbp+47h+pwi.rcClient.left]
0x180016fd3  xor     r8d, r8d
0x180016fd6  mov     r13d, [rbp+47h+pwi.rcClient.bottom]
0x180016fda  mov     [rbp+47h+var_C0], eax
0x180016fdd  mov     [rbp+47h+var_A0], rsi
0x180016fe1  mov     [rbp+47h+var_98], 1
0x180016fe8  mov     [rbp+47h+var_90], rsi
0x180016fec  mov     [rbp+47h+var_88], rsi
0x180016ff0  call    cs:__imp_GdiplusStartup
0x180016ff6  lea     r8, Type; "Image"
0x180016ffd  mov     rdx, rdi; lpName
0x180017000  mov     rcx, rbx; hModule
0x180017003  call    cs:__imp_FindResourceW
0x180017009  mov     rdi, rax
0x18001700c  test    rax, rax
0x18001700f  jz      loc_180017132
0x180017015  mov     rdx, rax; hResInfo
0x180017018  mov     rcx, rbx; hModule
0x18001701b  call    cs:__imp_SizeofResource
0x180017021  mov     esi, eax
0x180017023  test    eax, eax
0x180017025  jz      loc_180017132
0x18001702b  mov     rdx, rdi; hResInfo
0x18001702e  mov     rcx, rbx; hModule
0x180017031  call    cs:__imp_LoadResource
0x180017037  test    rax, rax
0x18001703a  jz      loc_180017132
0x180017040  mov     rcx, rax; hResData
0x180017043  call    cs:__imp_LockResource
0x180017049  test    rax, rax
0x18001704c  jz      loc_180017132
0x180017052  mov     edx, esi; cbInit
0x180017054  mov     rcx, rax; pInit
0x180017057  call    cs:__imp_SHCreateMemStream
0x18001705d  mov     rbx, rax
0x180017060  test    rax, rax
0x180017063  jz      loc_180017132
0x180017069  xor     edi, edi
0x18001706b  lea     ecx, [rdi+18h]
0x18001706e  call    cs:__imp_GdipAlloc
0x180017074  mov     rsi, rax
0x180017077  test    rax, rax
0x18001707a  jz      short loc_1800170E3
0x18001707c  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x180017083  mov     qword ptr [rbp+47h+var_B0.left], rdi
0x180017087  lea     rdx, [rbp+47h+var_B0]
0x18001708b  mov     [rsi], rax
0x18001708e  mov     rcx, rbx
0x180017091  call    cs:__imp_GdipCreateBitmapFromStream
0x180017097  mov     rcx, qword ptr [rbp+47h+var_B0.left]; this
0x18001709b  mov     rdx, rsi; struct Gdiplus::Bitmap *
0x18001709e  mov     r9d, [rbp+47h+var_BC]; unsigned int
0x1800170a2  mov     r8d, [rbp+47h+var_B8]; unsigned int
0x1800170a6  mov     [rsi+10h], eax
0x1800170a9  mov     eax, [rbp+47h+var_C0]
0x1800170ac  mov     [rbp+47h+var_B0.right], eax
0x1800170af  lea     rax, [rbp+47h+var_B0]
0x1800170b3  mov     [rsp+100h+var_E0], rax; struct tagRECT *
0x1800170b8  mov     [rsi+8], rcx
0x1800170bc  mov     [rbp+47h+var_B0.left], r12d
0x1800170c0  mov     [rbp+47h+var_B0.top], r15d
0x1800170c4  mov     [rbp+47h+var_B0.bottom], r13d
0x1800170c8  call    ?CreateDuiBitmapFromGDIPlusBitmap@LogonScreenHelper@@QEAAPEAVValue@DirectUI@@PEAVBitmap@Gdiplus@@IIUtagRECT@@E_N@Z; LogonScreenHelper::CreateDuiBitmapFromGDIPlusBitmap(Gdiplus::Bitmap *,uint,uint,tagRECT,uchar,bool)
0x1800170cd  mov     rcx, [rsi]
0x1800170d0  mov     rdi, rax
0x1800170d3  mov     edx, 1
0x1800170d8  mov     rax, [rcx]
0x1800170db  mov     rcx, rsi
0x1800170de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170e3  mov     rdx, [rbx]
0x1800170e6  mov     rcx, rbx
0x1800170e9  mov     rax, [rdx+10h]
0x1800170ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170f2  test    rdi, rdi
0x1800170f5  jz      short loc_180017132
0x1800170f7  lea     rcx, aInsideframe; "InsideFrame"
0x1800170fe  call    cs:__imp_StrToID
0x180017104  movzx   edx, ax
0x180017107  mov     rcx, r14
0x18001710a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180017110  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180017117  mov     r9, rdi
0x18001711a  mov     rcx, rax
0x18001711d  mov     r8d, 1
0x180017123  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180017129  mov     rcx, rdi
0x18001712c  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180017132  mov     rcx, [rbp+47h+var_A0]
0x180017136  call    cs:__imp_GdiplusShutdown
0x18001713c  mov     rcx, [rbp+47h+var_40]
0x180017140  xor     rcx, rsp; StackCookie
0x180017143  call    __security_check_cookie
0x180017148  mov     rbx, [rsp+100h+arg_0]
0x180017150  add     rsp, 0D0h
0x180017157  pop     r15
0x180017159  pop     r14
0x18001715b  pop     r13
0x18001715d  pop     r12
0x18001715f  pop     rdi
0x180017160  pop     rsi
0x180017161  pop     rbp
0x180017162  retn
```

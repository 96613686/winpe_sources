# CDesktopThumbnailCVIVisual::SetVisual(CDesktopThumbnailCVI *,tagRECT const &)

- ea: `0x1800813ac`
- end: `0x18008149b`
- name: `?SetVisual@CDesktopThumbnailCVIVisual@@QEAAJPEAVCDesktopThumbnailCVI@@AEBUtagRECT@@@Z`
- size: `239`
- prototype: `int(CDesktopThumbnailCVIVisual *__hidden this, struct CDesktopThumbnailCVI *, const struct tagRECT *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026190`
- `0x180062420`
- `0x1800dbf20`

## callees

- `0x1800029e8`
- `0x180015460`
- `0x18001d6fc`
- `0x180052df0`
- `0x180080914`
- `0x1800813ac`
- `0x1800814a4`
- `0x1800814c8`
- `0x180081a68`
- `0x1800b13e8`

## import_xrefs

- `USER32!CopyRect` at `0x1800813d4`
- `USER32!CopyRect` at `0x1800813d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDesktopThumbnailCVIVisual::SetVisual(
        struct tagRECT *this,
        struct CDesktopThumbnailCVI *a2,
        const struct tagRECT *a3)
{
  int VisualBrush; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v9[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_OWORD *)v9 = 0;
  CopyRect(this + 15, a3);
  VisualBrush = CDesktopThumbnailCVI::GetVisualBrush(a2, (struct CVisualBrush *)v9);
  v6 = VisualBrush;
  if ( VisualBrush >= 0 )
  {
    CVisual::SetInterpolationMode(this, 1);
    v7 = CSpriteVisual::SetBrush<Windows::UI::Composition::ICompositionColorBrush *>(this, *(_QWORD *)v9);
    v6 = v7;
    if ( v7 >= 0 )
    {
      CVisualBrush::operator=(&this[14], v9);
      *(_QWORD *)&this[13].left = a2;
      if ( a2 )
        CBaseObject::AddRef(a2);
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E3,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\desktopthumbnail.cpp",
        (const char *)(unsigned int)v7,
        v9[0]);
    }
    CVisualBrush::~CVisualBrush((CVisualBrush *)v9);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\desktopthumbnail.cpp",
      (const char *)(unsigned int)VisualBrush,
      v9[0]);
    wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(&v9[2]);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(v9);
  }
  return v6;
}

```

## disassembly

```asm
0x1800813ac  mov     [rsp+arg_0], rbx
0x1800813b1  mov     [rsp+arg_8], rsi
0x1800813b6  push    rdi
0x1800813b7  sub     rsp, 30h
0x1800813bb  mov     rsi, rdx
0x1800813be  mov     rdi, rcx
0x1800813c1  xorps   xmm0, xmm0
0x1800813c4  movdqu  xmmword ptr [rsp+38h+var_18], xmm0; int
0x1800813ca  add     rcx, 0F0h; lprcDst
0x1800813d1  mov     rdx, r8; lprcSrc
0x1800813d4  call    cs:__imp_CopyRect
0x1800813da  lea     rdx, [rsp+38h+var_18]; struct CVisualBrush *
0x1800813df  mov     rcx, rsi; this
0x1800813e2  call    ?GetVisualBrush@CDesktopThumbnailCVI@@QEAAJPEAVCVisualBrush@@@Z; CDesktopThumbnailCVI::GetVisualBrush(CVisualBrush *)
0x1800813e7  mov     ebx, eax
0x1800813e9  test    eax, eax
0x1800813eb  jns     short loc_18008141D
0x1800813ed  mov     rcx, [rsp+38h]; this
0x1800813f2  mov     r9d, eax; char *
0x1800813f5  lea     r8, aClientcoreWind_70; "clientcore\\windows\\dwm\\udwm\\desktop"...
0x1800813fc  mov     edx, 1DFh; void *
0x180081401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081406  nop
0x180081407  lea     rcx, [rsp+38h+var_18+8]
0x18008140c  call    ??1?$com_ptr_t@UICompositionVisualSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(void)
0x180081411  lea     rcx, [rsp+38h+var_18]
0x180081416  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18008141b  jmp     short loc_180081489
0x18008141d  mov     edx, 1
0x180081422  mov     rcx, rdi
0x180081425  call    ?SetInterpolationMode@CVisual@@QEAAXW4Enum@MilBitmapInterpolationMode@@@Z; CVisual::SetInterpolationMode(MilBitmapInterpolationMode::Enum)
0x18008142a  mov     rdx, qword ptr [rsp+38h+var_18]
0x18008142f  mov     rcx, rdi
0x180081432  call    ??$SetBrush@PEAUICompositionColorBrush@Composition@UI@Windows@@@CSpriteVisual@@QEAAJPEAUICompositionColorBrush@Composition@UI@Windows@@@Z; CSpriteVisual::SetBrush<Windows::UI::Composition::ICompositionColorBrush *>(Windows::UI::Composition::ICompositionColorBrush *)
0x180081437  mov     ebx, eax
0x180081439  test    eax, eax
0x18008143b  jns     short loc_180081458
0x18008143d  mov     rcx, [rsp+38h]; this
0x180081442  mov     r9d, eax; char *
0x180081445  lea     r8, aClientcoreWind_70; "clientcore\\windows\\dwm\\udwm\\desktop"...
0x18008144c  mov     edx, 1E3h; void *
0x180081451  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081456  jmp     short loc_18008147F
0x180081458  lea     rcx, [rdi+0E0h]
0x18008145f  lea     rdx, [rsp+38h+var_18]
0x180081464  call    ??4CVisualBrush@@QEAAAEAV0@$$QEAV0@@Z; CVisualBrush::operator=(CVisualBrush &&)
0x180081469  mov     [rdi+0D0h], rsi
0x180081470  test    rsi, rsi
0x180081473  jz      short loc_18008147D
0x180081475  mov     rcx, rsi; this
0x180081478  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x18008147d  xor     ebx, ebx
0x18008147f  lea     rcx, [rsp+38h+var_18]; this
0x180081484  call    ??1CVisualBrush@@QEAA@XZ; CVisualBrush::~CVisualBrush(void)
0x180081489  mov     eax, ebx
0x18008148b  mov     rbx, [rsp+38h+arg_0]
0x180081490  mov     rsi, [rsp+38h+arg_8]
0x180081495  add     rsp, 30h
0x180081499  pop     rdi
0x18008149a  retn
```

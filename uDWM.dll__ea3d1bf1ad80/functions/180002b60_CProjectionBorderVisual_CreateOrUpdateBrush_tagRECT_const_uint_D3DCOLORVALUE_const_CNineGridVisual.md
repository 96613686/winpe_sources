# CProjectionBorderVisual::_CreateOrUpdateBrush(tagRECT const &,uint,_D3DCOLORVALUE const &,CNineGridVisual *)

- ea: `0x180002b60`
- end: `0x180002d30`
- name: `?_CreateOrUpdateBrush@CProjectionBorderVisual@@IEAAJAEBUtagRECT@@IAEBU_D3DCOLORVALUE@@PEAVCNineGridVisual@@@Z`
- size: `464`
- prototype: `int(CProjectionBorderVisual *__hidden this, const struct tagRECT *, unsigned int, const struct _D3DCOLORVALUE *, struct CNineGridVisual *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c1238`

## callees

- `0x180002b60`
- `0x180004a44`
- `0x18000e41c`
- `0x18000eeac`
- `0x18000fb00`
- `0x180052df0`
- `0x1800801c0`
- `0x180081a68`
- `0x1800c0df4`
- `0x1800ea010`

## import_xrefs

- `USER32!IsRectEmpty` at `0x180002b7d`
- `USER32!IsRectEmpty` at `0x180002b7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProjectionBorderVisual::_CreateOrUpdateBrush(
        CProjectionBorderVisual *this,
        const struct tagRECT *a2,
        int a3,
        const struct _D3DCOLORVALUE *a4,
        struct CNineGridVisual *a5)
{
  int IsCenterHollow; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v15; // eax
  __int64 v16; // r9
  int v17; // eax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  CProjectionBorderVisual *v21; // [rsp+40h] [rbp+8h] BYREF

  v21 = this;
  if ( IsRectEmpty(a2) )
  {
    v18 = CNineGridVisual::UpdateInnerBrush<std::nullptr_t>(a5);
    v8 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\projectionbordervisual.cpp",
        (const char *)(unsigned int)v18,
        v19);
      return v8;
    }
  }
  else
  {
    v21 = 0;
    IsCenterHollow = CNineGridVisual::GetInnerBrush<Windows::UI::Composition::ICompositionColorBrush>(a5, &v21);
    v8 = IsCenterHollow;
    if ( IsCenterHollow < 0 )
    {
      v9 = 108;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\projectionbordervisual.cpp",
        (const char *)(unsigned int)IsCenterHollow,
        v19);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v21);
      return v8;
    }
    if ( !v21 )
    {
      v10 = *(__int64 **)(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 6) + 40LL);
      v11 = *v10;
      v21 = 0;
      IsCenterHollow = (*(__int64 (__fastcall **)(__int64 *, CProjectionBorderVisual **))(v11 + 56))(v10, &v21);
      v8 = IsCenterHollow;
      if ( IsCenterHollow < 0 )
      {
        v9 = 113;
        goto LABEL_13;
      }
      IsCenterHollow = CNineGridVisual::UpdateInnerBrush<Windows::UI::Composition::ICompositionColorBrush *>(a5);
      v8 = IsCenterHollow;
      if ( IsCenterHollow < 0 )
      {
        v9 = 114;
        goto LABEL_13;
      }
      IsCenterHollow = CNineGridVisual::UpdateIsCenterHollow(a5, 1);
      v8 = IsCenterHollow;
      if ( IsCenterHollow < 0 )
      {
        v9 = 115;
        goto LABEL_13;
      }
    }
    IsCenterHollow = CNineGridVisual::UpdateInsets(
                       a5,
                       (float)(int)((double)a3 * *((double *)CDesktopManager::s_pDesktopManagerInstance + 52)),
                       (float)(int)((double)a3 * *((double *)CDesktopManager::s_pDesktopManagerInstance + 52)),
                       (float)(int)((double)a3 * *((double *)CDesktopManager::s_pDesktopManagerInstance + 52)),
                       (float)(int)((double)a3 * *((double *)CDesktopManager::s_pDesktopManagerInstance + 52)));
    v8 = IsCenterHollow;
    if ( IsCenterHollow < 0 )
    {
      v9 = 118;
      goto LABEL_13;
    }
    v15 = WUColorFromD2DColor(a4, v12, v13, v21);
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 56LL))(v16, v15);
    v8 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\projectionbordervisual.cpp",
        (const char *)(unsigned int)v17,
        v19);
      if ( v21 )
        (*(void (__fastcall **)(CProjectionBorderVisual *))(*(_QWORD *)v21 + 16LL))(v21);
      return v8;
    }
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v21);
  }
  return 0;
}

```

## disassembly

```asm
0x180002b60  mov     [rsp+arg_8], rbx
0x180002b65  mov     [rsp+arg_10], rbp
0x180002b6a  mov     [rsp+arg_0], rcx
0x180002b6f  push    rsi
0x180002b70  sub     rsp, 30h
0x180002b74  mov     rbp, r9
0x180002b77  mov     esi, r8d
0x180002b7a  mov     rcx, rdx; lprc
0x180002b7d  call    cs:__imp_IsRectEmpty
0x180002b83  test    eax, eax
0x180002b85  jnz     loc_180002D02
0x180002b8b  mov     [rsp+38h+arg_0], 0
0x180002b94  lea     rdx, [rsp+38h+arg_0]
0x180002b99  mov     rcx, [rsp+38h+arg_20]
0x180002b9e  call    ??$GetInnerBrush@UICompositionColorBrush@Composition@UI@Windows@@@CNineGridVisual@@QEAAJPEAPEAUICompositionColorBrush@Composition@UI@Windows@@@Z; CNineGridVisual::GetInnerBrush<Windows::UI::Composition::ICompositionColorBrush>(Windows::UI::Composition::ICompositionColorBrush * *)
0x180002ba3  mov     ebx, eax
0x180002ba5  test    eax, eax
0x180002ba7  jns     short loc_180002BB3
0x180002ba9  mov     edx, 6Ch ; 'l'
0x180002bae  jmp     loc_180002C69
0x180002bb3  cmp     [rsp+38h+arg_0], 0
0x180002bb9  jnz     short loc_180002C26
0x180002bbb  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180002bc2  mov     rcx, [rax+30h]
0x180002bc6  mov     rcx, [rcx+28h]
0x180002bca  mov     rax, [rcx]
0x180002bcd  mov     [rsp+38h+arg_0], 0
0x180002bd6  lea     rdx, [rsp+38h+arg_0]
0x180002bdb  mov     rax, [rax+38h]
0x180002bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be4  mov     ebx, eax
0x180002be6  test    eax, eax
0x180002be8  jns     short loc_180002BF1
0x180002bea  mov     edx, 71h ; 'q'
0x180002bef  jmp     short loc_180002C69
0x180002bf1  mov     rdx, [rsp+38h+arg_0]
0x180002bf6  mov     rcx, [rsp+38h+arg_20]
0x180002bfb  call    ??$UpdateInnerBrush@PEAUICompositionColorBrush@Composition@UI@Windows@@@CNineGridVisual@@QEAAJPEAUICompositionColorBrush@Composition@UI@Windows@@@Z; CNineGridVisual::UpdateInnerBrush<Windows::UI::Composition::ICompositionColorBrush *>(Windows::UI::Composition::ICompositionColorBrush *)
0x180002c00  mov     ebx, eax
0x180002c02  test    eax, eax
0x180002c04  jns     short loc_180002C0D
0x180002c06  mov     edx, 72h ; 'r'
0x180002c0b  jmp     short loc_180002C69
0x180002c0d  mov     dl, 1; bool
0x180002c0f  mov     rcx, [rsp+38h+arg_20]; this
0x180002c14  call    ?UpdateIsCenterHollow@CNineGridVisual@@QEAAJ_N@Z; CNineGridVisual::UpdateIsCenterHollow(bool)
0x180002c19  mov     ebx, eax
0x180002c1b  test    eax, eax
0x180002c1d  jns     short loc_180002C26
0x180002c1f  mov     edx, 73h ; 's'
0x180002c24  jmp     short loc_180002C69
0x180002c26  movd    xmm0, esi
0x180002c2a  cvtdq2pd xmm0, xmm0
0x180002c2e  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180002c35  mulsd   xmm0, qword ptr [rax+1A0h]
0x180002c3d  cvttsd2si eax, xmm0
0x180002c41  movd    xmm1, eax
0x180002c45  cvtdq2ps xmm1, xmm1; float
0x180002c48  movss   [rsp+38h+var_18], xmm1; int
0x180002c4e  movaps  xmm3, xmm1; float
0x180002c51  movaps  xmm2, xmm1; float
0x180002c54  mov     rcx, [rsp+38h+arg_20]; this
0x180002c59  call    ?UpdateInsets@CNineGridVisual@@QEAAJMMMM@Z; CNineGridVisual::UpdateInsets(float,float,float,float)
0x180002c5e  mov     ebx, eax
0x180002c60  test    eax, eax
0x180002c62  jns     short loc_180002C8C
0x180002c64  mov     edx, 76h ; 'v'; void *
0x180002c69  mov     r9d, eax; char *
0x180002c6c  lea     r8, aClientcoreWind_12; "clientcore\\windows\\dwm\\udwm\\project"...
0x180002c73  mov     rcx, [rsp+38h]; this
0x180002c78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002c7d  nop
0x180002c7e  lea     rcx, [rsp+38h+arg_0]
0x180002c83  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x180002c88  mov     eax, ebx
0x180002c8a  jmp     short loc_180002CF2
0x180002c8c  mov     r9, [rsp+38h+arg_0]
0x180002c91  mov     rcx, rbp
0x180002c94  call    ?WUColorFromD2DColor@@YA?AUColor@UI@Windows@@AEBU_D3DCOLORVALUE@@@Z; WUColorFromD2DColor(_D3DCOLORVALUE const &)
0x180002c99  mov     rdx, [r9]
0x180002c9c  mov     r8, [rdx+38h]
0x180002ca0  mov     edx, eax
0x180002ca2  mov     rcx, r9
0x180002ca5  mov     rax, r8
0x180002ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cad  mov     ebx, eax
0x180002caf  test    eax, eax
0x180002cb1  jns     short loc_180002CE6
0x180002cb3  mov     rcx, [rsp+38h]; this
0x180002cb8  mov     r9d, eax; char *
0x180002cbb  lea     r8, aClientcoreWind_12; "clientcore\\windows\\dwm\\udwm\\project"...
0x180002cc2  mov     edx, 77h ; 'w'; void *
0x180002cc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002ccc  nop
0x180002ccd  mov     rcx, [rsp+38h+arg_0]
0x180002cd2  test    rcx, rcx
0x180002cd5  jz      short loc_180002CE4
0x180002cd7  mov     rax, [rcx]
0x180002cda  mov     rax, [rax+10h]
0x180002cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce3  nop
0x180002ce4  jmp     short loc_180002C88
0x180002ce6  lea     rcx, [rsp+38h+arg_0]
0x180002ceb  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x180002cf0  xor     eax, eax
0x180002cf2  mov     rbx, [rsp+38h+arg_8]
0x180002cf7  mov     rbp, [rsp+38h+arg_10]
0x180002cfc  add     rsp, 30h
0x180002d00  pop     rsi
0x180002d01  retn
0x180002d02  mov     rcx, [rsp+38h+arg_20]
0x180002d07  call    ??$UpdateInnerBrush@$$T@CNineGridVisual@@QEAAJ$$T@Z; CNineGridVisual::UpdateInnerBrush<std::nullptr_t>(std::nullptr_t)
0x180002d0c  mov     ebx, eax
0x180002d0e  test    eax, eax
0x180002d10  jns     short loc_180002CF0
0x180002d12  mov     rcx, [rsp+38h]; this
0x180002d17  mov     r9d, eax; char *
0x180002d1a  lea     r8, aClientcoreWind_12; "clientcore\\windows\\dwm\\udwm\\project"...
0x180002d21  mov     edx, 7Bh ; '{'; void *
0x180002d26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002d2b  jmp     loc_180002C88
```

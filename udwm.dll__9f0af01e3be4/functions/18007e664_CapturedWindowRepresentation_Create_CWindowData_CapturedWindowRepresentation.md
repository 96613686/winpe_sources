# CapturedWindowRepresentation::Create(CWindowData *,CapturedWindowRepresentation * *)

- ea: `0x18007e664`
- end: `0x18007e915`
- name: `?Create@CapturedWindowRepresentation@@SAJPEAVCWindowData@@PEAPEAV1@@Z`
- size: `689`
- prototype: `__int64 __fastcall(struct CWindowData *, struct CapturedWindowRepresentation **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007e514`

## callees

- `0x180004b3c`
- `0x1800061e4`
- `0x18001d6c0`
- `0x180022310`
- `0x18006be08`
- `0x18007e664`
- `0x180081a68`
- `0x180083a34`
- `0x180090c6c`
- `0x18009348c`
- `0x1800a2880`
- `0x1800a3294`
- `0x1800ac178`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x18007e739`
- `USER32!GetWindowThreadProcessId` at `0x18007e739`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CapturedWindowRepresentation::Create(
        struct CWindowData *a1,
        struct CapturedWindowRepresentation **a2)
{
  CBaseObject *v4; // rax
  CBaseObject *v5; // rbx
  unsigned int v6; // edi
  CCompositor *v7; // r14
  struct CVisualProxy *v8; // r15
  int v9; // eax
  __int64 v10; // rdx
  int inserted; // eax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  struct CVisualProxy *v16; // [rsp+20h] [rbp-10h] BYREF
  CBaseObject *v17; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  struct CVisualProxy *v19; // [rsp+80h] [rbp+50h] BYREF
  CContainerVisualProxy *v20; // [rsp+88h] [rbp+58h] BYREF

  v4 = (CBaseObject *)operator new(0x60u);
  v5 = v4;
  v17 = v4;
  if ( v4 )
  {
    CBaseObject::CBaseObject(v4);
    *(_QWORD *)v5 = &CapturedWindowRepresentation::`vftable';
    *((_QWORD *)v5 + 2) = 0;
    *((_QWORD *)v5 + 3) = 0;
    *((_QWORD *)v5 + 4) = 0;
    *((_QWORD *)v5 + 5) = 0;
    *((_QWORD *)v5 + 6) = 0;
    *((_QWORD *)v5 + 7) = 0;
    *((_QWORD *)v5 + 8) = 0;
    *((_DWORD *)v5 + 18) = 0;
    *((_DWORD *)v5 + 20) = 0;
    *((_QWORD *)v5 + 11) = 0;
  }
  else
  {
    v5 = 0;
  }
  v17 = v5;
  if ( !(unsigned __int8)std::operator==<CWindowBorder::CCachedBorderBrush>(&v17) )
  {
    *((_QWORD *)v5 + 2) = *((_QWORD *)a1 + 5);
    if ( *((_QWORD *)a1 + 55) )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_SecondaryWindowsFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_SecondaryWindowsFix>::GetImpl'::`2'::impl) )
        goto LABEL_10;
      if ( GetWindowThreadProcessId(*((HWND *)a1 + 5), (LPDWORD)v5 + 20) )
      {
        *((_QWORD *)v5 + 11) = a1;
LABEL_10:
        v7 = (CCompositor *)*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 6);
        v8 = *(struct CVisualProxy **)(*((_QWORD *)a1 + 55) + 16LL);
        v19 = 0;
        Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(&v19);
        v9 = CCompositor::CreateRedirectVisualProxy(v7, &v19);
        v6 = v9;
        if ( v9 < 0 )
        {
          v10 = 32;
LABEL_12:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v10,
            (unsigned int)"clientcore\\windows\\dwm\\udwm\\capturedwindowrepresentation.cpp",
            (const char *)(unsigned int)v9,
            (int)v16);
LABEL_13:
          Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(&v19);
          goto LABEL_31;
        }
        v9 = CRedirectVisualProxy::SetRedirectedVisual(v19, v8);
        v6 = v9;
        if ( v9 < 0 )
        {
          v10 = 33;
          goto LABEL_12;
        }
        Microsoft::WRL::ComPtr<CRedirectVisualProxy>::operator=((char *)v5 + 32, &v19);
        v20 = 0;
        Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(&v20);
        inserted = CCompositor::CreateContainerVisualProxy(v7, &v20);
        v6 = inserted;
        if ( inserted >= 0 )
        {
          inserted = CContainerVisualProxy::InsertChild(v20, v19, 0, 0);
          v6 = inserted;
          if ( inserted >= 0 )
          {
            Microsoft::WRL::ComPtr<CRedirectVisualProxy>::operator=((char *)v5 + 24, &v20);
            v16 = 0;
            Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(&v16);
            v13 = CCompositor::CreateContainerVisualProxy(v7, &v16);
            v6 = v13;
            if ( v13 >= 0 )
            {
              v13 = CContainerVisualProxy::InsertChild(v20, v16, v19, 1);
              v6 = v13;
              if ( v13 >= 0 )
              {
                Microsoft::WRL::ComPtr<CRedirectVisualProxy>::operator=((char *)v5 + 40, &v16);
                v13 = CapturedWindowRepresentation::LookForSecondaryWindows(v5, a1);
                v6 = v13;
                if ( v13 >= 0 )
                {
                  v17 = 0;
                  *a2 = v5;
                  Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(&v16);
                  Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(&v20);
                  Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(&v19);
                  v6 = 0;
                  goto LABEL_31;
                }
                v14 = 47;
              }
              else
              {
                v14 = 43;
              }
            }
            else
            {
              v14 = 42;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v14,
              (unsigned int)"clientcore\\windows\\dwm\\udwm\\capturedwindowrepresentation.cpp",
              (const char *)(unsigned int)v13,
              (int)v16);
            Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(&v16);
            goto LABEL_19;
          }
          v12 = 38;
        }
        else
        {
          v12 = 37;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"clientcore\\windows\\dwm\\udwm\\capturedwindowrepresentation.cpp",
          (const char *)(unsigned int)inserted,
          (int)v16);
LABEL_19:
        Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(&v20);
        goto LABEL_13;
      }
    }
    v6 = -2147024809;
    goto LABEL_31;
  }
  v6 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB,
    (unsigned int)"clientcore\\windows\\dwm\\udwm\\capturedwindowrepresentation.cpp",
    (const char *)0x8007000ELL,
    (int)v16);
LABEL_31:
  Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(&v17);
  return v6;
}

```

## disassembly

```asm
0x18007e664  mov     [rsp-38h+arg_0], rbx
0x18007e669  push    rbp
0x18007e66a  push    rsi
0x18007e66b  push    rdi
0x18007e66c  push    r12
0x18007e66e  push    r13
0x18007e670  push    r14
0x18007e672  push    r15
0x18007e674  mov     rbp, rsp
0x18007e677  sub     rsp, 30h
0x18007e67b  mov     r12, rdx
0x18007e67e  mov     rsi, rcx
0x18007e681  mov     ecx, 60h ; '`'; unsigned __int64
0x18007e686  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007e68b  mov     rbx, rax
0x18007e68e  mov     [rbp+var_8], rax
0x18007e692  xor     r13d, r13d
0x18007e695  test    rax, rax
0x18007e698  jz      short loc_18007E6D6
0x18007e69a  mov     rcx, rax; this
0x18007e69d  call    ??0CBaseObject@@QEAA@XZ; CBaseObject::CBaseObject(void)
0x18007e6a2  lea     rcx, ??_7CapturedWindowRepresentation@@6B@; const CapturedWindowRepresentation::`vftable'
0x18007e6a9  mov     [rbx], rcx
0x18007e6ac  mov     [rbx+10h], r13
0x18007e6b0  mov     [rbx+18h], r13
0x18007e6b4  mov     [rbx+20h], r13
0x18007e6b8  mov     [rbx+28h], r13
0x18007e6bc  mov     [rbx+30h], r13
0x18007e6c0  mov     [rbx+38h], r13
0x18007e6c4  mov     [rbx+40h], r13
0x18007e6c8  mov     [rbx+48h], r13d
0x18007e6cc  mov     [rbx+50h], r13d
0x18007e6d0  mov     [rbx+58h], r13
0x18007e6d4  jmp     short loc_18007E6D9
0x18007e6d6  mov     rbx, r13
0x18007e6d9  mov     [rbp+var_8], rbx
0x18007e6dd  lea     rcx, [rbp+var_8]
0x18007e6e1  call    ??$?8VCCachedBorderBrush@CWindowBorder@@@std@@YA_NAEBV?$shared_ptr@VCCachedBorderBrush@CWindowBorder@@@0@$$T@Z; std::operator==<CWindowBorder::CCachedBorderBrush>(std::shared_ptr<CWindowBorder::CCachedBorderBrush> const &,std::nullptr_t)
0x18007e6e6  test    al, al
0x18007e6e8  jz      short loc_18007E70C
0x18007e6ea  mov     rcx, [rbp+38h]; this
0x18007e6ee  mov     edi, 8007000Eh
0x18007e6f3  mov     r9d, edi; char *
0x18007e6f6  lea     r8, aClientcoreWind_36; "clientcore\\windows\\dwm\\udwm\\capture"...
0x18007e6fd  mov     edx, 0Bh; void *
0x18007e702  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e707  jmp     loc_18007E8F5
0x18007e70c  mov     rax, [rsi+28h]
0x18007e710  mov     [rbx+10h], rax
0x18007e714  cmp     [rsi+1B8h], r13
0x18007e71b  jz      loc_18007E8F0
0x18007e721  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_SecondaryWindowsFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_SecondaryWindowsFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_SecondaryWindowsFix> `wil::Feature<__WilFeatureTraits_Feature_Capture_SecondaryWindowsFix>::GetImpl(void)'::`2'::impl
0x18007e728  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_SecondaryWindowsFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_SecondaryWindowsFix>::__private_IsEnabled(void)
0x18007e72d  test    al, al
0x18007e72f  jz      short loc_18007E74B
0x18007e731  lea     rdx, [rbx+50h]; lpdwProcessId
0x18007e735  mov     rcx, [rsi+28h]; hWnd
0x18007e739  call    cs:__imp_GetWindowThreadProcessId
0x18007e73f  test    eax, eax
0x18007e741  jz      loc_18007E8F0
0x18007e747  mov     [rbx+58h], rsi
0x18007e74b  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18007e752  mov     r14, [rax+30h]
0x18007e756  mov     rax, [rsi+1B8h]
0x18007e75d  mov     r15, [rax+10h]
0x18007e761  mov     [rbp+arg_10], r13
0x18007e765  lea     rcx, [rbp+arg_10]
0x18007e769  call    ?InternalRelease@?$ComPtr@VCSpriteVisual@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(void)
0x18007e76e  lea     rdx, [rbp+arg_10]; struct CRedirectVisualProxy **
0x18007e772  mov     rcx, r14; this
0x18007e775  call    ?CreateRedirectVisualProxy@CCompositor@@QEAAJPEAPEAVCRedirectVisualProxy@@@Z; CCompositor::CreateRedirectVisualProxy(CRedirectVisualProxy * *)
0x18007e77a  mov     edi, eax
0x18007e77c  test    eax, eax
0x18007e77e  jns     short loc_18007E7A7
0x18007e780  mov     edx, 20h ; ' '; void *
0x18007e785  lea     r8, aClientcoreWind_36; "clientcore\\windows\\dwm\\udwm\\capture"...
0x18007e78c  mov     r9d, eax; char *
0x18007e78f  mov     rcx, [rbp+38h]; this
0x18007e793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e798  nop
0x18007e799  lea     rcx, [rbp+arg_10]
0x18007e79d  call    ?InternalRelease@?$ComPtr@VCSpriteVisual@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(void)
0x18007e7a2  jmp     loc_18007E8F5
0x18007e7a7  mov     rdx, r15; struct CVisualProxy *
0x18007e7aa  mov     rcx, [rbp+arg_10]; this
0x18007e7ae  call    ?SetRedirectedVisual@CRedirectVisualProxy@@QEAAJPEAVCVisualProxy@@@Z; CRedirectVisualProxy::SetRedirectedVisual(CVisualProxy *)
0x18007e7b3  mov     edi, eax
0x18007e7b5  test    eax, eax
0x18007e7b7  jns     short loc_18007E7C0
0x18007e7b9  mov     edx, 21h ; '!'
0x18007e7be  jmp     short loc_18007E785
0x18007e7c0  lea     rcx, [rbx+20h]
0x18007e7c4  lea     rdx, [rbp+arg_10]
0x18007e7c8  call    ??4?$ComPtr@VCRedirectVisualProxy@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<CRedirectVisualProxy>::operator=(Microsoft::WRL::ComPtr<CRedirectVisualProxy> const &)
0x18007e7cd  mov     [rbp+arg_18], r13
0x18007e7d1  lea     rcx, [rbp+arg_18]
0x18007e7d5  call    ?InternalRelease@?$ComPtr@VCSpriteVisual@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(void)
0x18007e7da  lea     rdx, [rbp+arg_18]; struct CContainerVisualProxy **
0x18007e7de  mov     rcx, r14; this
0x18007e7e1  call    ?CreateContainerVisualProxy@CCompositor@@QEAAJPEAPEAVCContainerVisualProxy@@@Z; CCompositor::CreateContainerVisualProxy(CContainerVisualProxy * *)
0x18007e7e6  mov     edi, eax
0x18007e7e8  test    eax, eax
0x18007e7ea  jns     short loc_18007E810
0x18007e7ec  mov     edx, 25h ; '%'; void *
0x18007e7f1  lea     r8, aClientcoreWind_36; "clientcore\\windows\\dwm\\udwm\\capture"...
0x18007e7f8  mov     r9d, eax; char *
0x18007e7fb  mov     rcx, [rbp+38h]; this
0x18007e7ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e804  nop
0x18007e805  lea     rcx, [rbp+arg_18]
0x18007e809  call    ?InternalRelease@?$ComPtr@VCSpriteVisual@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(void)
0x18007e80e  jmp     short loc_18007E799
0x18007e810  xor     r9d, r9d; bool
0x18007e813  xor     r8d, r8d; struct CVisualProxy *
0x18007e816  mov     rdx, [rbp+arg_10]; struct CVisualProxy *
0x18007e81a  mov     rcx, [rbp+arg_18]; this
0x18007e81e  call    ?InsertChild@CContainerVisualProxy@@QEAAJPEAVCVisualProxy@@0_N@Z; CContainerVisualProxy::InsertChild(CVisualProxy *,CVisualProxy *,bool)
0x18007e823  mov     edi, eax
0x18007e825  test    eax, eax
0x18007e827  jns     short loc_18007E830
0x18007e829  mov     edx, 26h ; '&'
0x18007e82e  jmp     short loc_18007E7F1
0x18007e830  lea     rcx, [rbx+18h]
0x18007e834  lea     rdx, [rbp+arg_18]
0x18007e838  call    ??4?$ComPtr@VCRedirectVisualProxy@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<CRedirectVisualProxy>::operator=(Microsoft::WRL::ComPtr<CRedirectVisualProxy> const &)
0x18007e83d  mov     [rbp+var_10], r13
0x18007e841  lea     rcx, [rbp+var_10]
0x18007e845  call    ?InternalRelease@?$ComPtr@VCSpriteVisual@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(void)
0x18007e84a  lea     rdx, [rbp+var_10]; struct CContainerVisualProxy **
0x18007e84e  mov     rcx, r14; this
0x18007e851  call    ?CreateContainerVisualProxy@CCompositor@@QEAAJPEAPEAVCContainerVisualProxy@@@Z; CCompositor::CreateContainerVisualProxy(CContainerVisualProxy * *)
0x18007e856  mov     edi, eax
0x18007e858  test    eax, eax
0x18007e85a  jns     short loc_18007E880
0x18007e85c  mov     edx, 2Ah ; '*'; void *
0x18007e861  mov     rcx, [rbp+38h]; this
0x18007e865  mov     r9d, eax; char *
0x18007e868  lea     r8, aClientcoreWind_36; "clientcore\\windows\\dwm\\udwm\\capture"...
0x18007e86f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e874  nop
0x18007e875  lea     rcx, [rbp+var_10]
0x18007e879  call    ?InternalRelease@?$ComPtr@VCSpriteVisual@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(void)
0x18007e87e  jmp     short loc_18007E805
0x18007e880  mov     r9b, 1; bool
0x18007e883  mov     r8, [rbp+arg_10]; struct CVisualProxy *
0x18007e887  mov     rdx, [rbp+var_10]; struct CVisualProxy *
0x18007e88b  mov     rcx, [rbp+arg_18]; this
0x18007e88f  call    ?InsertChild@CContainerVisualProxy@@QEAAJPEAVCVisualProxy@@0_N@Z; CContainerVisualProxy::InsertChild(CVisualProxy *,CVisualProxy *,bool)
0x18007e894  mov     edi, eax
0x18007e896  test    eax, eax
0x18007e898  jns     short loc_18007E8A1
0x18007e89a  mov     edx, 2Bh ; '+'
0x18007e89f  jmp     short loc_18007E861
0x18007e8a1  lea     rcx, [rbx+28h]
0x18007e8a5  lea     rdx, [rbp+var_10]
0x18007e8a9  call    ??4?$ComPtr@VCRedirectVisualProxy@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<CRedirectVisualProxy>::operator=(Microsoft::WRL::ComPtr<CRedirectVisualProxy> const &)
0x18007e8ae  mov     rdx, rsi; struct CWindowData *
0x18007e8b1  mov     rcx, rbx; this
0x18007e8b4  call    ?LookForSecondaryWindows@CapturedWindowRepresentation@@IEAAJPEAVCWindowData@@@Z; CapturedWindowRepresentation::LookForSecondaryWindows(CWindowData *)
0x18007e8b9  mov     edi, eax
0x18007e8bb  test    eax, eax
0x18007e8bd  jns     short loc_18007E8C6
0x18007e8bf  mov     edx, 2Fh ; '/'
0x18007e8c4  jmp     short loc_18007E861
0x18007e8c6  mov     [rbp+var_8], r13
0x18007e8ca  mov     [r12], rbx
0x18007e8ce  lea     rcx, [rbp+var_10]
0x18007e8d2  call    ?InternalRelease@?$ComPtr@VCSpriteVisual@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(void)
0x18007e8d7  nop
0x18007e8d8  lea     rcx, [rbp+arg_18]
0x18007e8dc  call    ?InternalRelease@?$ComPtr@VCSpriteVisual@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(void)
0x18007e8e1  nop
0x18007e8e2  lea     rcx, [rbp+arg_10]
0x18007e8e6  call    ?InternalRelease@?$ComPtr@VCSpriteVisual@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(void)
0x18007e8eb  mov     edi, r13d
0x18007e8ee  jmp     short loc_18007E8F5
0x18007e8f0  mov     edi, 80070057h
0x18007e8f5  lea     rcx, [rbp+var_8]
0x18007e8f9  call    ?InternalRelease@?$ComPtr@VCSpriteVisual@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpriteVisual>::InternalRelease(void)
0x18007e8fe  mov     eax, edi
0x18007e900  mov     rbx, [rsp+30h+arg_0]
0x18007e905  add     rsp, 30h
0x18007e909  pop     r15
0x18007e90b  pop     r14
0x18007e90d  pop     r13
0x18007e90f  pop     r12
0x18007e911  pop     rdi
0x18007e912  pop     rsi
0x18007e913  pop     rbp
0x18007e914  retn
```

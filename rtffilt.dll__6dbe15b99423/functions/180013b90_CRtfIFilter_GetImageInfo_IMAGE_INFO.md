# CRtfIFilter::GetImageInfo(IMAGE_INFO *)

- ea: `0x180013b90`
- end: `0x180013d45`
- name: `?GetImageInfo@CRtfIFilter@@UEAAJPEAUIMAGE_INFO@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(CRtfIFilter *this, struct IMAGE_INFO *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a844`
- `0x180010780`
- `0x1800108a4`
- `0x180011384`
- `0x180013b90`
- `0x180015484`
- `0x180018f38`
- `0x18001b010`

## string_xrefs

- `0x180013c7a`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x180013bfd`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`

## pseudocode

```c
__int64 __fastcall CRtfIFilter::GetImageInfo(CRtfIFilter *this, struct IMAGE_INFO *a2)
{
  __int64 v2; // rdi
  __int64 v4; // r14
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64); // rbp
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // r14
  int (__fastcall *v11)(__int64, _QWORD, __int64); // rbp
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v15; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 3);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl'::`2'::impl) )
  {
    v4 = *(_QWORD *)(v2 + 8);
    v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v4 + 104LL);
    if ( *(_QWORD *)(v2 + 16) )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(v2 + 16);
    v6 = v5(v4, 0, v2 + 16);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v15 = 0;
      v6 = ImagingHandler::ConvertFrameToSupportedFormat((ImagingHandler *)v2, (enum IMAGE_PIXELFORMAT *)&v15);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v6 = ImagingHandler::CalculateTotalSizeOccupiedByImageFrame(
               (ImagingHandler *)v2,
               (const enum IMAGE_PIXELFORMAT *)&v15);
        v7 = v6;
        if ( v6 >= 0 )
        {
          v7 = 0;
          *(_DWORD *)a2 = *(_DWORD *)(v2 + 36);
          *((_DWORD *)a2 + 1) = *(_DWORD *)(v2 + 40);
          *((_DWORD *)a2 + 2) = v15;
          return v7;
        }
        v8 = 84;
      }
      else
      {
        v8 = 81;
      }
    }
    else
    {
      v8 = 78;
    }
    v9 = (unsigned int)v6;
  }
  else
  {
    if ( !a2 )
    {
      v7 = -2147467261;
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
        (const wchar_t *)0x62,
        (unsigned int)L"ImagingHandler::GetImageFrame : Invalid IMAGE_FRAME pointer, hr(0x%08x)",
        (const wchar_t *)0x80004003LL);
      return v7;
    }
    v10 = *(_QWORD *)(v2 + 8);
    v11 = *(int (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v10 + 104LL);
    if ( *(_QWORD *)(v2 + 16) )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(v2 + 16);
    if ( v11(v10, 0, v2 + 16) >= 0 )
    {
      v15 = 0;
      if ( (int)ImagingHandler::ConvertFrameToSupportedFormat((ImagingHandler *)v2, (enum IMAGE_PIXELFORMAT *)&v15) >= 0 )
      {
        v7 = ImagingHandler::CalculateTotalSizeOccupiedByImageFrame(
               (ImagingHandler *)v2,
               (const enum IMAGE_PIXELFORMAT *)&v15);
        if ( (v7 & 0x80000000) == 0 )
        {
          *(_DWORD *)a2 = *(_DWORD *)(v2 + 36);
          *((_DWORD *)a2 + 1) = *(_DWORD *)(v2 + 40);
          *((_DWORD *)a2 + 2) = v15;
          return v7;
        }
        v7 = -2147215602;
        v8 = 117;
        v9 = 2147751694LL;
      }
      else
      {
        v7 = -2147215602;
        v8 = 110;
        v9 = 2147751694LL;
      }
    }
    else
    {
      v7 = -2147215602;
      v8 = 106;
      v9 = 2147751694LL;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
    (const char *)v9,
    v13);
  return v7;
}

```

## disassembly

```asm
0x180013b90  mov     [rsp+arg_8], rbx
0x180013b95  mov     [rsp+arg_10], rbp
0x180013b9a  push    rsi
0x180013b9b  push    rdi
0x180013b9c  push    r14; int
0x180013b9e  sub     rsp, 20h
0x180013ba2  mov     rdi, [rcx+18h]
0x180013ba6  mov     rsi, rdx
0x180013ba9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x180013bb0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x180013bb5  test    al, al
0x180013bb7  jz      loc_180013C63
0x180013bbd  mov     r14, [rdi+8]
0x180013bc1  lea     rbx, [rdi+10h]
0x180013bc5  cmp     qword ptr [rbx], 0
0x180013bc9  mov     rax, [r14]
0x180013bcc  mov     rbp, [rax+68h]
0x180013bd0  jz      short loc_180013BDA
0x180013bd2  mov     rcx, rbx
0x180013bd5  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180013bda  mov     r8, rbx
0x180013bdd  xor     edx, edx
0x180013bdf  mov     rcx, r14
0x180013be2  mov     rax, rbp
0x180013be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bea  mov     ebx, eax
0x180013bec  test    eax, eax
0x180013bee  jns     short loc_180013C0E
0x180013bf0  mov     edx, 4Eh ; 'N'; void *
0x180013bf5  mov     r9d, eax; char *
0x180013bf8  mov     rcx, [rsp+38h]; this
0x180013bfd  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180013c04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c09  jmp     loc_180013D30
0x180013c0e  lea     rdx, [rsp+38h+arg_0]; enum IMAGE_PIXELFORMAT *
0x180013c13  mov     [rsp+38h+arg_0], 0
0x180013c1b  mov     rcx, rdi; this
0x180013c1e  call    ?ConvertFrameToSupportedFormat@ImagingHandler@@AEAAJPEAW4IMAGE_PIXELFORMAT@@@Z; ImagingHandler::ConvertFrameToSupportedFormat(IMAGE_PIXELFORMAT *)
0x180013c23  mov     ebx, eax
0x180013c25  test    eax, eax
0x180013c27  jns     short loc_180013C30
0x180013c29  mov     edx, 51h ; 'Q'
0x180013c2e  jmp     short loc_180013BF5
0x180013c30  lea     rdx, [rsp+38h+arg_0]; enum IMAGE_PIXELFORMAT *
0x180013c35  mov     rcx, rdi; this
0x180013c38  call    ?CalculateTotalSizeOccupiedByImageFrame@ImagingHandler@@AEAAJAEBW4IMAGE_PIXELFORMAT@@@Z; ImagingHandler::CalculateTotalSizeOccupiedByImageFrame(IMAGE_PIXELFORMAT const &)
0x180013c3d  mov     ebx, eax
0x180013c3f  test    eax, eax
0x180013c41  jns     short loc_180013C4A
0x180013c43  mov     edx, 54h ; 'T'
0x180013c48  jmp     short loc_180013BF5
0x180013c4a  mov     eax, [rdi+24h]
0x180013c4d  xor     ebx, ebx
0x180013c4f  mov     [rsi], eax
0x180013c51  mov     eax, [rdi+28h]
0x180013c54  mov     [rsi+4], eax
0x180013c57  mov     eax, [rsp+38h+arg_0]
0x180013c5b  mov     [rsi+8], eax
0x180013c5e  jmp     loc_180013D30
0x180013c63  test    rsi, rsi
0x180013c66  jnz     short loc_180013C8B
0x180013c68  mov     ebx, 80004003h
0x180013c6d  lea     r8, aImaginghandler_1; "ImagingHandler::GetImageFrame : Invalid"...
0x180013c74  mov     r9d, ebx; wchar_t *
0x180013c77  lea     edx, [rsi+62h]; wchar_t *
0x180013c7a  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180013c81  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180013c86  jmp     loc_180013D30
0x180013c8b  mov     r14, [rdi+8]
0x180013c8f  lea     rbx, [rdi+10h]
0x180013c93  cmp     qword ptr [rbx], 0
0x180013c97  mov     rax, [r14]
0x180013c9a  mov     rbp, [rax+68h]
0x180013c9e  jz      short loc_180013CA8
0x180013ca0  mov     rcx, rbx
0x180013ca3  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180013ca8  mov     r8, rbx
0x180013cab  xor     edx, edx
0x180013cad  mov     rcx, r14
0x180013cb0  mov     rax, rbp
0x180013cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cb8  test    eax, eax
0x180013cba  jns     short loc_180013CCE
0x180013cbc  mov     ebx, 8004170Eh
0x180013cc1  mov     edx, 6Ah ; 'j'
0x180013cc6  mov     r9d, ebx
0x180013cc9  jmp     loc_180013BF8
0x180013cce  lea     rdx, [rsp+38h+arg_0]; enum IMAGE_PIXELFORMAT *
0x180013cd3  mov     [rsp+38h+arg_0], 0
0x180013cdb  mov     rcx, rdi; this
0x180013cde  call    ?ConvertFrameToSupportedFormat@ImagingHandler@@AEAAJPEAW4IMAGE_PIXELFORMAT@@@Z; ImagingHandler::ConvertFrameToSupportedFormat(IMAGE_PIXELFORMAT *)
0x180013ce3  test    eax, eax
0x180013ce5  jns     short loc_180013CF9
0x180013ce7  mov     ebx, 8004170Eh
0x180013cec  mov     edx, 6Eh ; 'n'
0x180013cf1  mov     r9d, ebx
0x180013cf4  jmp     loc_180013BF8
0x180013cf9  lea     rdx, [rsp+38h+arg_0]; enum IMAGE_PIXELFORMAT *
0x180013cfe  mov     rcx, rdi; this
0x180013d01  call    ?CalculateTotalSizeOccupiedByImageFrame@ImagingHandler@@AEAAJAEBW4IMAGE_PIXELFORMAT@@@Z; ImagingHandler::CalculateTotalSizeOccupiedByImageFrame(IMAGE_PIXELFORMAT const &)
0x180013d06  mov     ebx, eax
0x180013d08  test    eax, eax
0x180013d0a  jns     short loc_180013D1E
0x180013d0c  mov     ebx, 8004170Eh
0x180013d11  mov     edx, 75h ; 'u'
0x180013d16  mov     r9d, ebx
0x180013d19  jmp     loc_180013BF8
0x180013d1e  mov     ecx, [rdi+24h]
0x180013d21  mov     [rsi], ecx
0x180013d23  mov     ecx, [rdi+28h]
0x180013d26  mov     [rsi+4], ecx
0x180013d29  mov     ecx, [rsp+38h+arg_0]
0x180013d2d  mov     [rsi+8], ecx
0x180013d30  mov     rbp, [rsp+38h+arg_10]
0x180013d35  mov     eax, ebx
0x180013d37  mov     rbx, [rsp+38h+arg_8]
0x180013d3c  add     rsp, 20h
0x180013d40  pop     r14
0x180013d42  pop     rdi
0x180013d43  pop     rsi
0x180013d44  retn
```

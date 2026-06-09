# CRtfIFilter::GetPixelsForImage(float,tagRECT const *,ulong,uchar *)

- ea: `0x180013f00`
- end: `0x180013f68`
- name: `?GetPixelsForImage@CRtfIFilter@@UEAAJMPEBUtagRECT@@KPEAE@Z`
- size: `104`
- prototype: `__int64 __fastcall(CRtfIFilter *__hidden this, float, const struct tagRECT *, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011384`
- `0x18001153c`
- `0x180013f00`

## string_xrefs

- `0x180013f52`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x180013f46`: `ImagingHandler::GetPixelsForImage : Error copying pixels to buffer, hr(0x%08x)`

## pseudocode

```c
__int64 __fastcall CRtfIFilter::GetPixelsForImage(
        CRtfIFilter *this,
        float a2,
        const struct tagRECT *a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  __int64 result; // rax

  result = ImagingHandler::ExtractBitmapFromImage(
             *(_DWORD *)(*((_QWORD *)this + 3) + 36LL),
             *(_DWORD *)(*((_QWORD *)this + 3) + 40LL),
             *(_DWORD *)(*((_QWORD *)this + 3) + 44LL),
             **((const wchar_t ***)this + 3),
             *(struct IWICBitmap **)(*((_QWORD *)this + 3) + 24LL),
             a2,
             a3,
             a4,
             a5);
  if ( (int)result < 0 )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
      (const wchar_t *)0x87,
      (unsigned int)L"ImagingHandler::GetPixelsForImage : Error copying pixels to buffer, hr(0x%08x)",
      (const wchar_t *)(unsigned int)result);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180013f00  mov     r11, rsp
0x180013f03  sub     rsp, 58h
0x180013f07  mov     rcx, [rcx+18h]
0x180013f0b  mov     rax, [rsp+58h+arg_20]
0x180013f13  mov     [r11-18h], rax
0x180013f17  mov     [r11-20h], r9d
0x180013f1b  mov     rax, [rcx+18h]
0x180013f1f  mov     r9, [rcx]; struct IWICImagingFactory *
0x180013f22  mov     edx, [rcx+28h]; int
0x180013f25  mov     [r11-28h], r8
0x180013f29  mov     r8d, [rcx+2Ch]; int
0x180013f2d  mov     ecx, [rcx+24h]; int
0x180013f30  movss   [rsp+58h+var_30], xmm1; float
0x180013f36  mov     [r11-38h], rax
0x180013f3a  call    ?ExtractBitmapFromImage@ImagingHandler@@SAJHHHPEAUIWICImagingFactory@@PEAUIWICBitmap@@MPEBUtagRECT@@KPEAE@Z; ImagingHandler::ExtractBitmapFromImage(int,int,int,IWICImagingFactory *,IWICBitmap *,float,tagRECT const *,ulong,uchar *)
0x180013f3f  test    eax, eax
0x180013f41  jns     short loc_180013F63
0x180013f43  mov     r9d, eax; wchar_t *
0x180013f46  lea     r8, aImaginghandler_7; "ImagingHandler::GetPixelsForImage : Err"...
0x180013f4d  mov     edx, 87h; wchar_t *
0x180013f52  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180013f59  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180013f5e  mov     eax, 80004005h
0x180013f63  add     rsp, 58h
0x180013f67  retn
```

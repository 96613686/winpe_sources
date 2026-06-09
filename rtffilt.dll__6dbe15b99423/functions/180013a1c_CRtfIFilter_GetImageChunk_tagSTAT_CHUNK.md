# CRtfIFilter::GetImageChunk(tagSTAT_CHUNK *)

- ea: `0x180013a1c`
- end: `0x180013b81`
- name: `?GetImageChunk@CRtfIFilter@@AEAAJPEAUtagSTAT_CHUNK@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(CRtfIFilter *__hidden this, struct tagSTAT_CHUNK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013100`

## callees

- `0x18000a844`
- `0x180011384`
- `0x180013a1c`
- `0x180018f38`
- `0x18001b010`

## string_xrefs

- `0x180013a72`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x180013ad3`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x180013ac7`: `ImagingHandler::InitImageDecoder : Failed to create decoder for image stream, hr(0x%08x)`

## pseudocode

```c
__int64 __fastcall CRtfIFilter::GetImageChunk(CRtfIFilter *this, struct tagSTAT_CHUNK *a2)
{
  int v5; // edi
  _QWORD *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rbp
  _QWORD *v9; // r8
  __int64 v10; // r14
  int v11; // edi
  __int64 (__fastcall *v12)(__int64, __int64, _QWORD, _QWORD); // r15
  int v13; // eax
  __int64 v14; // rbp
  _QWORD *v15; // rcx
  int v16; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( **((_QWORD **)this + 11) == *(_QWORD *)(*((_QWORD *)this + 11) + 8LL) )
    return 2147751680LL;
  v5 = 0;
  do
  {
    v6 = (_QWORD *)*((_QWORD *)this + 11);
    v7 = v6[1];
    if ( *v6 == v7 )
      break;
    v8 = *(_QWORD *)(v7 - 8);
    if ( v8 )
    {
      v9 = (_QWORD *)*((_QWORD *)this + 3);
      v10 = *v9;
      v11 = (_DWORD)v9 + 8;
      v12 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)*v9 + 32LL);
      if ( v9[1] )
        winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(v9 + 1);
      v16 = v11;
      v13 = v12(v10, v8, 0, 0);
      v5 = v13;
      if ( v13 < 0 )
        SearchIndexerTrace::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
          (const wchar_t *)0x42,
          (unsigned int)L"ImagingHandler::InitImageDecoder : Failed to create decoder for image stream, hr(0x%08x)",
          (const wchar_t *)(unsigned int)v13);
    }
    else
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
        (const wchar_t *)0x39,
        (unsigned int)L"ImagingHandler::InitImageDecoder : Invalid image stream, hr(0x%08x)",
        (const wchar_t *)0x80004003LL);
      v5 = -2147467261;
    }
    v14 = *((_QWORD *)this + 11);
    v15 = (_QWORD *)(*(_QWORD *)(v14 + 8) - 8LL);
    if ( *v15 )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(v15);
    *(_QWORD *)(v14 + 8) -= 8LL;
  }
  while ( v5 < 0 );
  if ( v5 >= 0 )
  {
    a2->idChunk = ++*((_DWORD *)this + 8);
    a2->breakType = CHUNK_EOC;
    *(_QWORD *)&a2->flags = 8;
    a2->attribute.guidPropSet.Data1 = -1222250192;
    *(_DWORD *)&a2->attribute.guidPropSet.Data2 = 270157807;
    *(_DWORD *)a2->attribute.guidPropSet.Data4 = 1610805669;
    *(_DWORD *)&a2->attribute.guidPropSet.Data4[4] = -1393844596;
    a2->attribute.psProperty.ulKind = 1;
    a2->attribute.psProperty.propid = 19;
    *(_QWORD *)&a2->idChunkSource = 0;
    a2->cwcLenSource = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\rtf\\rtffilt\\lib\\rtffilt.cxx",
      (const char *)(unsigned int)v5,
      v16);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013a1c  push    rbx
0x180013a1e  push    rbp
0x180013a1f  push    rsi
0x180013a20  push    rdi
0x180013a21  push    r14
0x180013a23  push    r15
0x180013a25  sub     rsp, 38h
0x180013a29  mov     r8, [rcx+58h]
0x180013a2d  mov     rbx, rdx
0x180013a30  mov     rsi, rcx
0x180013a33  mov     rax, [r8+8]
0x180013a37  cmp     [r8], rax
0x180013a3a  jnz     short loc_180013A46
0x180013a3c  mov     eax, 80041700h
0x180013a41  jmp     loc_180013B74
0x180013a46  xor     edi, edi
0x180013a48  mov     rax, [rsi+58h]
0x180013a4c  mov     rcx, [rax+8]
0x180013a50  cmp     [rax], rcx
0x180013a53  jz      loc_180013B03
0x180013a59  mov     rbp, [rcx-8]
0x180013a5d  test    rbp, rbp
0x180013a60  jnz     short loc_180013A85
0x180013a62  mov     r9d, 80004003h; wchar_t *
0x180013a68  lea     r8, aImaginghandler_5; "ImagingHandler::InitImageDecoder : Inva"...
0x180013a6f  lea     edx, [rbp+39h]; wchar_t *
0x180013a72  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180013a79  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180013a7e  mov     edi, 80004003h
0x180013a83  jmp     short loc_180013ADF
0x180013a85  mov     r8, [rsi+18h]
0x180013a89  mov     r14, [r8]
0x180013a8c  lea     rdi, [r8+8]
0x180013a90  cmp     qword ptr [rdi], 0
0x180013a94  mov     rax, [r14]
0x180013a97  mov     r15, [rax+20h]
0x180013a9b  jz      short loc_180013AA5
0x180013a9d  mov     rcx, rdi
0x180013aa0  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180013aa5  xor     r9d, r9d
0x180013aa8  mov     qword ptr [rsp+68h+var_48], rdi; int
0x180013aad  xor     r8d, r8d
0x180013ab0  mov     rdx, rbp
0x180013ab3  mov     rcx, r14
0x180013ab6  mov     rax, r15
0x180013ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013abe  mov     edi, eax
0x180013ac0  test    eax, eax
0x180013ac2  jns     short loc_180013ADF
0x180013ac4  mov     r9d, eax; wchar_t *
0x180013ac7  lea     r8, aImaginghandler_6; "ImagingHandler::InitImageDecoder : Fail"...
0x180013ace  mov     edx, 42h ; 'B'; wchar_t *
0x180013ad3  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180013ada  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180013adf  mov     rbp, [rsi+58h]
0x180013ae3  mov     rcx, [rbp+8]
0x180013ae7  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180013aeb  cmp     qword ptr [rcx], 0
0x180013aef  jz      short loc_180013AF6
0x180013af1  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180013af6  add     qword ptr [rbp+8], 0FFFFFFFFFFFFFFF8h
0x180013afb  test    edi, edi
0x180013afd  js      loc_180013A48
0x180013b03  test    edi, edi
0x180013b05  jns     short loc_180013B22
0x180013b07  mov     rcx, [rsp+68h]; this
0x180013b0c  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180013b13  mov     r9d, edi; char *
0x180013b16  mov     edx, 46Fh; void *
0x180013b1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b20  jmp     short loc_180013B72
0x180013b22  inc     dword ptr [rsi+20h]
0x180013b25  mov     eax, [rsi+20h]
0x180013b28  mov     [rbx], eax
0x180013b2a  mov     dword ptr [rbx+4], 4
0x180013b31  mov     qword ptr [rbx+8], 8
0x180013b39  mov     dword ptr [rbx+10h], 0B725F130h
0x180013b40  mov     dword ptr [rbx+14h], 101A47EFh
0x180013b47  mov     dword ptr [rbx+18h], 6002F1A5h
0x180013b4e  mov     dword ptr [rbx+1Ch], 0ACEB9E8Ch
0x180013b55  mov     dword ptr [rbx+20h], 1
0x180013b5c  mov     dword ptr [rbx+28h], 13h
0x180013b63  mov     qword ptr [rbx+30h], 0
0x180013b6b  mov     dword ptr [rbx+38h], 0
0x180013b72  mov     eax, edi
0x180013b74  add     rsp, 38h
0x180013b78  pop     r15
0x180013b7a  pop     r14
0x180013b7c  pop     rdi
0x180013b7d  pop     rsi
0x180013b7e  pop     rbp
0x180013b7f  pop     rbx
0x180013b80  retn
```

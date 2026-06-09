# CFsrmPipelineModuleImplWrapper::~CFsrmPipelineModuleImplWrapper(void)

- ea: `0x1800aae98`
- end: `0x1800ab124`
- name: `??1CFsrmPipelineModuleImplWrapper@@QEAA@XZ`
- size: `652`
- prototype: `void __fastcall(CFsrmPipelineModuleImplWrapper *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800a9060`
- `0x1800d1dee`
- `0x1800d1f92`

## callees

- `0x180001350`
- `0x180040608`
- `0x1800887b0`
- `0x1800aae98`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800ab050`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ab05e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ab06c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ab050`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ab05e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ab06c`
- `KERNEL32!DeleteCriticalSection` at `0x1800aaed9`
- `KERNEL32!DeleteCriticalSection` at `0x1800aaef3`
- `KERNEL32!DeleteCriticalSection` at `0x1800aaf0d`
- `KERNEL32!DeleteCriticalSection` at `0x1800ab115`
- `KERNEL32!DeleteCriticalSection` at `0x1800aaed9`
- `KERNEL32!DeleteCriticalSection` at `0x1800aaef3`
- `KERNEL32!DeleteCriticalSection` at `0x1800aaf0d`
- `KERNEL32!DeleteCriticalSection` at `0x1800ab115`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800aaebc`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800aaebc`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CFsrmPipelineModuleImplWrapper::~CFsrmPipelineModuleImplWrapper(CFsrmPipelineModuleImplWrapper *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  if ( *((_QWORD *)this + 81) )
  {
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 81));
    *((_QWORD *)this + 81) = 0;
  }
  if ( *((_BYTE *)this + 856) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 816));
    *((_BYTE *)this + 856) = 0;
  }
  if ( *((_BYTE *)this + 808) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 768));
    *((_BYTE *)this + 808) = 0;
  }
  if ( *((_BYTE *)this + 760) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 18);
    *((_BYTE *)this + 760) = 0;
  }
  if ( *((_QWORD *)this + 86) >= 8u )
    operator delete(*((void **)this + 83));
  *((_QWORD *)this + 86) = 7;
  *((_QWORD *)this + 85) = 0;
  *((_WORD *)this + 332) = 0;
  if ( *((_QWORD *)this + 79) >= 8u )
    operator delete(*((void **)this + 76));
  *((_QWORD *)this + 79) = 7;
  *((_QWORD *)this + 78) = 0;
  *((_WORD *)this + 304) = 0;
  if ( *((_QWORD *)this + 70) >= 8u )
    operator delete(*((void **)this + 67));
  *((_QWORD *)this + 70) = 7;
  *((_QWORD *)this + 69) = 0;
  *((_WORD *)this + 268) = 0;
  if ( *((_QWORD *)this + 65) >= 8u )
    operator delete(*((void **)this + 62));
  *((_QWORD *)this + 65) = 7;
  *((_QWORD *)this + 64) = 0;
  *((_WORD *)this + 248) = 0;
  if ( *((_QWORD *)this + 60) >= 8u )
    operator delete(*((void **)this + 57));
  *((_QWORD *)this + 60) = 7;
  *((_QWORD *)this + 59) = 0;
  *((_WORD *)this + 228) = 0;
  if ( *((_QWORD *)this + 55) >= 8u )
    operator delete(*((void **)this + 52));
  *((_QWORD *)this + 55) = 7;
  *((_QWORD *)this + 54) = 0;
  *((_WORD *)this + 208) = 0;
  if ( *((_QWORD *)this + 50) >= 8u )
    operator delete(*((void **)this + 47));
  *((_QWORD *)this + 50) = 7;
  *((_QWORD *)this + 49) = 0;
  *((_WORD *)this + 188) = 0;
  SysFreeString(*((BSTR *)this + 44));
  SysFreeString(*((BSTR *)this + 43));
  SysFreeString(*((BSTR *)this + 42));
  std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>>>,0>>::clear((char *)this + 304);
  operator delete(*((void **)this + 39));
  CScanInformation::~CScanInformation((CFsrmPipelineModuleImplWrapper *)((char *)this + 128));
  v2 = *((_QWORD *)this + 15);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 14);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 13);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *((_BYTE *)this + 88) )
  {
    *((_BYTE *)this + 88) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  }
}

```

## disassembly

```asm
0x1800aae98  mov     [rsp+arg_0], rcx
0x1800aae9d  push    rbx
0x1800aae9e  push    rsi
0x1800aae9f  push    rdi
0x1800aaea0  sub     rsp, 30h
0x1800aaea4  mov     rdi, rcx
0x1800aaea7  mov     rax, [rcx+288h]
0x1800aaeae  xor     esi, esi
0x1800aaeb0  test    rax, rax
0x1800aaeb3  jz      short loc_1800AAEC9
0x1800aaeb5  mov     rcx, [rcx+288h]; pti
0x1800aaebc  call    cs:__imp_CloseThreadpoolTimer
0x1800aaec2  mov     [rdi+288h], rsi
0x1800aaec9  lea     rbx, [rdi+330h]
0x1800aaed0  cmp     [rbx+28h], sil
0x1800aaed4  jz      short loc_1800AAEE3
0x1800aaed6  mov     rcx, rbx; lpCriticalSection
0x1800aaed9  call    cs:__imp_DeleteCriticalSection
0x1800aaedf  mov     [rbx+28h], sil
0x1800aaee3  lea     rbx, [rdi+300h]
0x1800aaeea  cmp     [rbx+28h], sil
0x1800aaeee  jz      short loc_1800AAEFD
0x1800aaef0  mov     rcx, rbx; lpCriticalSection
0x1800aaef3  call    cs:__imp_DeleteCriticalSection
0x1800aaef9  mov     [rbx+28h], sil
0x1800aaefd  lea     rbx, [rdi+2D0h]
0x1800aaf04  cmp     [rbx+28h], sil
0x1800aaf08  jz      short loc_1800AAF17
0x1800aaf0a  mov     rcx, rbx; lpCriticalSection
0x1800aaf0d  call    cs:__imp_DeleteCriticalSection
0x1800aaf13  mov     [rbx+28h], sil
0x1800aaf17  cmp     qword ptr [rdi+2B0h], 8
0x1800aaf1f  jb      short loc_1800AAF2D
0x1800aaf21  mov     rcx, [rdi+298h]; Block
0x1800aaf28  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aaf2d  mov     ebx, 7
0x1800aaf32  mov     [rdi+2B0h], rbx
0x1800aaf39  mov     [rdi+2A8h], rsi
0x1800aaf40  mov     [rdi+298h], si
0x1800aaf47  cmp     qword ptr [rdi+278h], 8
0x1800aaf4f  jb      short loc_1800AAF5D
0x1800aaf51  mov     rcx, [rdi+260h]; Block
0x1800aaf58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aaf5d  mov     [rdi+278h], rbx
0x1800aaf64  mov     [rdi+270h], rsi
0x1800aaf6b  mov     [rdi+260h], si
0x1800aaf72  cmp     qword ptr [rdi+230h], 8
0x1800aaf7a  jb      short loc_1800AAF88
0x1800aaf7c  mov     rcx, [rdi+218h]; Block
0x1800aaf83  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aaf88  mov     [rdi+230h], rbx
0x1800aaf8f  mov     [rdi+228h], rsi
0x1800aaf96  mov     [rdi+218h], si
0x1800aaf9d  cmp     qword ptr [rdi+208h], 8
0x1800aafa5  jb      short loc_1800AAFB3
0x1800aafa7  mov     rcx, [rdi+1F0h]; Block
0x1800aafae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aafb3  mov     [rdi+208h], rbx
0x1800aafba  mov     [rdi+200h], rsi
0x1800aafc1  mov     [rdi+1F0h], si
0x1800aafc8  cmp     qword ptr [rdi+1E0h], 8
0x1800aafd0  jb      short loc_1800AAFDE
0x1800aafd2  mov     rcx, [rdi+1C8h]; Block
0x1800aafd9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aafde  mov     [rdi+1E0h], rbx
0x1800aafe5  mov     [rdi+1D8h], rsi
0x1800aafec  mov     [rdi+1C8h], si
0x1800aaff3  cmp     qword ptr [rdi+1B8h], 8
0x1800aaffb  jb      short loc_1800AB009
0x1800aaffd  mov     rcx, [rdi+1A0h]; Block
0x1800ab004  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ab009  mov     [rdi+1B8h], rbx
0x1800ab010  mov     [rdi+1B0h], rsi
0x1800ab017  mov     [rdi+1A0h], si
0x1800ab01e  cmp     qword ptr [rdi+190h], 8
0x1800ab026  jb      short loc_1800AB034
0x1800ab028  mov     rcx, [rdi+178h]; Block
0x1800ab02f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ab034  mov     [rdi+190h], rbx
0x1800ab03b  mov     [rdi+188h], rsi
0x1800ab042  mov     [rdi+178h], si
0x1800ab049  mov     rcx, [rdi+160h]; bstrString
0x1800ab050  call    cs:__imp_SysFreeString
0x1800ab056  nop
0x1800ab057  mov     rcx, [rdi+158h]; bstrString
0x1800ab05e  call    cs:__imp_SysFreeString
0x1800ab064  nop
0x1800ab065  mov     rcx, [rdi+150h]; bstrString
0x1800ab06c  call    cs:__imp_SysFreeString
0x1800ab072  nop
0x1800ab073  lea     rbx, [rdi+130h]
0x1800ab07a  mov     [rsp+48h+var_28], rbx
0x1800ab07f  mov     rcx, rbx
0x1800ab082  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>>>,0>>::clear(void)
0x1800ab087  nop
0x1800ab088  mov     rcx, [rbx+8]; Block
0x1800ab08c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ab091  nop
0x1800ab092  lea     rcx, [rdi+80h]; this
0x1800ab099  call    ??1CScanInformation@@QEAA@XZ; CScanInformation::~CScanInformation(void)
0x1800ab09e  nop
0x1800ab09f  lea     rax, [rdi+78h]
0x1800ab0a3  mov     [rsp+48h+arg_8], rax
0x1800ab0a8  mov     rcx, [rax]
0x1800ab0ab  test    rcx, rcx
0x1800ab0ae  jz      short loc_1800AB0BD
0x1800ab0b0  mov     rax, [rcx]
0x1800ab0b3  mov     rax, [rax+10h]
0x1800ab0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0bc  nop
0x1800ab0bd  lea     rax, [rdi+70h]
0x1800ab0c1  mov     [rsp+48h+arg_8], rax
0x1800ab0c6  mov     rcx, [rax]
0x1800ab0c9  test    rcx, rcx
0x1800ab0cc  jz      short loc_1800AB0DB
0x1800ab0ce  mov     rax, [rcx]
0x1800ab0d1  mov     rax, [rax+10h]
0x1800ab0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0da  nop
0x1800ab0db  lea     rax, [rdi+68h]
0x1800ab0df  mov     [rsp+48h+arg_8], rax
0x1800ab0e4  mov     rcx, [rax]
0x1800ab0e7  test    rcx, rcx
0x1800ab0ea  jz      short loc_1800AB0F9
0x1800ab0ec  mov     rax, [rcx]
0x1800ab0ef  mov     rax, [rax+10h]
0x1800ab0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0f8  nop
0x1800ab0f9  lea     rax, [rdi+28h]
0x1800ab0fd  mov     [rsp+48h+arg_8], rax
0x1800ab102  lea     rcx, [rax+8]; lpCriticalSection
0x1800ab106  mov     [rsp+48h+arg_10], rcx
0x1800ab10b  cmp     [rcx+28h], sil
0x1800ab10f  jz      short loc_1800AB11C
0x1800ab111  mov     [rcx+28h], sil
0x1800ab115  call    cs:__imp_DeleteCriticalSection
0x1800ab11b  nop
0x1800ab11c  add     rsp, 30h
0x1800ab120  pop     rdi
0x1800ab121  pop     rsi
0x1800ab122  pop     rbx
0x1800ab123  retn
```

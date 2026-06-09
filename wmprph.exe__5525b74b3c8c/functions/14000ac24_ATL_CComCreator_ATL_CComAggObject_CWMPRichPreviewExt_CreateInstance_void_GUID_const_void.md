# ATL::CComCreator<ATL::CComAggObject<CWMPRichPreviewExt>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x14000ac24`
- end: `0x14000ad23`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCWMPRichPreviewExt@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14000ac10`

## callees

- `0x140001008`
- `0x140001014`
- `0x140001f24`
- `0x140002370`
- `0x1400045fc`
- `0x140004784`
- `0x14000ac24`
- `0x14000c818`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CWMPRichPreviewExt>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebx
  char *v8; // rax
  _QWORD *v9; // rdi
  CExeModule *v10; // rcx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0xB0u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CWMPRichPreviewExt>::`vftable';
    CWMPRichPreviewExt::CWMPRichPreviewExt((CWMPRichPreviewExt *)(v8 + 16));
    v9[6] = a1;
    v9[2] = &ATL::CComContainedObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandler'};
    v9[3] = &ATL::CComContainedObject<CWMPRichPreviewExt>::`vftable'{for `IInitializeWithFile'};
    v9[4] = &ATL::CComContainedObject<CWMPRichPreviewExt>::`vftable'{for `IObjectWithSite'};
    v9[5] = &ATL::CComContainedObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandlerVisuals'};
    _InterlockedIncrement(&dword_1400153D8);
    v7 = CWMPRichPreviewExt::FinalConstruct((CWMPRichPreviewExt *)(v9 + 2));
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
    {
      *v9 = &ATL::CComAggObject<CWMPRichPreviewExt>::`vftable';
      *((_DWORD *)v9 + 2) = 1;
      CWMPRichPreviewExt::FinalRelease((CWMPRichPreviewExt *)(v9 + 2));
      CExeModule::Unlock(v10);
      CWMPRichPreviewExt::~CWMPRichPreviewExt((CWMPRichPreviewExt *)(v9 + 2));
      operator delete(v9);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000ac24  push    rbx
0x14000ac26  push    rbp
0x14000ac27  push    rsi
0x14000ac28  push    rdi
0x14000ac29  push    r12
0x14000ac2b  push    r14
0x14000ac2d  sub     rsp, 28h
0x14000ac31  mov     rsi, r8
0x14000ac34  mov     r14, rdx
0x14000ac37  mov     rbp, rcx
0x14000ac3a  test    r8, r8
0x14000ac3d  jnz     short loc_14000AC49
0x14000ac3f  mov     eax, 80004003h
0x14000ac44  jmp     loc_14000AD16
0x14000ac49  mov     ecx, 0B0h; Size
0x14000ac4e  mov     qword ptr [r8], 0
0x14000ac55  mov     ebx, 8007000Eh
0x14000ac5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ac5f  mov     rdi, rax
0x14000ac62  test    rax, rax
0x14000ac65  jz      loc_14000AD14
0x14000ac6b  lea     r12, ??_7?$CComAggObject@VCWMPRichPreviewExt@@@ATL@@6B@; const ATL::CComAggObject<CWMPRichPreviewExt>::`vftable'
0x14000ac72  mov     dword ptr [rax+8], 0
0x14000ac79  lea     rcx, [rax+10h]; this
0x14000ac7d  mov     [rax], r12
0x14000ac80  call    ??0CWMPRichPreviewExt@@QEAA@XZ; CWMPRichPreviewExt::CWMPRichPreviewExt(void)
0x14000ac85  lea     rax, ??_7?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@6BIPreviewHandler@@@; const ATL::CComContainedObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandler'}
0x14000ac8c  mov     [rdi+30h], rbp
0x14000ac90  mov     [rdi+10h], rax
0x14000ac94  lea     rax, ??_7?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@6BIInitializeWithFile@@@; const ATL::CComContainedObject<CWMPRichPreviewExt>::`vftable'{for `IInitializeWithFile'}
0x14000ac9b  mov     [rdi+18h], rax
0x14000ac9f  lea     rax, ??_7?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@6BIObjectWithSite@@@; const ATL::CComContainedObject<CWMPRichPreviewExt>::`vftable'{for `IObjectWithSite'}
0x14000aca6  mov     [rdi+20h], rax
0x14000acaa  lea     rax, ??_7?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@6BIPreviewHandlerVisuals@@@; const ATL::CComContainedObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandlerVisuals'}
0x14000acb1  mov     [rdi+28h], rax
0x14000acb5  lock inc cs:dword_1400153D8
0x14000acbc  lea     rbp, [rdi+10h]
0x14000acc0  mov     rcx, rbp; this
0x14000acc3  call    ?FinalConstruct@CWMPRichPreviewExt@@QEAAJXZ; CWMPRichPreviewExt::FinalConstruct(void)
0x14000acc8  mov     ebx, eax
0x14000acca  test    eax, eax
0x14000accc  jnz     short loc_14000ACE8
0x14000acce  mov     rax, [rdi]
0x14000acd1  mov     r8, rsi
0x14000acd4  mov     rdx, r14
0x14000acd7  mov     rcx, rdi
0x14000acda  mov     rax, [rax]
0x14000acdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ace2  mov     ebx, eax
0x14000ace4  test    eax, eax
0x14000ace6  jz      short loc_14000AD14
0x14000ace8  mov     rcx, rbp; this
0x14000aceb  mov     [rdi], r12
0x14000acee  mov     dword ptr [rdi+8], 1
0x14000acf5  call    ?FinalRelease@CWMPRichPreviewExt@@QEAAJXZ; CWMPRichPreviewExt::FinalRelease(void)
0x14000acfa  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x14000acff  mov     rcx, rbp; this
0x14000ad02  call    ??1CWMPRichPreviewExt@@QEAA@XZ; CWMPRichPreviewExt::~CWMPRichPreviewExt(void)
0x14000ad07  mov     edx, 0B0h; unsigned __int64
0x14000ad0c  mov     rcx, rdi; void *
0x14000ad0f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ad14  mov     eax, ebx
0x14000ad16  add     rsp, 28h
0x14000ad1a  pop     r14
0x14000ad1c  pop     r12
0x14000ad1e  pop     rdi
0x14000ad1f  pop     rsi
0x14000ad20  pop     rbp
0x14000ad21  pop     rbx
0x14000ad22  retn
```

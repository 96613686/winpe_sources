# ATL::CComCreator<ATL::CComObject<CWMPRichPreviewExt>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x14000ad2c`
- end: `0x14000ae24`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWMPRichPreviewExt@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `248`
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
- `0x14000ad2c`
- `0x14000c818`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CWMPRichPreviewExt>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CWMPRichPreviewExt *v7; // rax
  CWMPRichPreviewExt *v8; // rbx
  CExeModule *v9; // rcx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CWMPRichPreviewExt *)operator new(0xA0u);
  v8 = v7;
  if ( v7 )
  {
    CWMPRichPreviewExt::CWMPRichPreviewExt(v7);
    *((_QWORD *)v8 + 3) = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandlerVisuals'};
    *(_QWORD *)v8 = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandler'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IInitializeWithFile'};
    *((_QWORD *)v8 + 2) = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IObjectWithSite'};
    _InterlockedIncrement(&dword_1400153D8);
    v6 = CWMPRichPreviewExt::FinalConstruct(v8);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CWMPRichPreviewExt *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
    {
      *(_QWORD *)v8 = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandler'};
      *((_QWORD *)v8 + 3) = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandlerVisuals'};
      *((_QWORD *)v8 + 1) = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IInitializeWithFile'};
      *((_QWORD *)v8 + 2) = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IObjectWithSite'};
      *((_DWORD *)v8 + 8) = 1;
      CWMPRichPreviewExt::FinalRelease(v8);
      CExeModule::Unlock(v9);
      CWMPRichPreviewExt::~CWMPRichPreviewExt(v8);
      operator delete(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14000ad2c  push    rbx
0x14000ad2e  push    rbp
0x14000ad2f  push    rsi
0x14000ad30  push    rdi
0x14000ad31  push    r12
0x14000ad33  push    r13
0x14000ad35  push    r15
0x14000ad37  sub     rsp, 20h
0x14000ad3b  mov     rsi, r8
0x14000ad3e  mov     rbp, rdx
0x14000ad41  test    r8, r8
0x14000ad44  jnz     short loc_14000AD50
0x14000ad46  mov     eax, 80004003h
0x14000ad4b  jmp     loc_14000AE15
0x14000ad50  mov     ecx, 0A0h; Size
0x14000ad55  mov     qword ptr [r8], 0
0x14000ad5c  mov     edi, 8007000Eh
0x14000ad61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ad66  mov     rbx, rax
0x14000ad69  test    rax, rax
0x14000ad6c  jz      loc_14000AE13
0x14000ad72  mov     rcx, rax; this
0x14000ad75  call    ??0CWMPRichPreviewExt@@QEAA@XZ; CWMPRichPreviewExt::CWMPRichPreviewExt(void)
0x14000ad7a  lea     rax, ??_7?$CComObject@VCWMPRichPreviewExt@@@ATL@@6BIPreviewHandlerVisuals@@@; const ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandlerVisuals'}
0x14000ad81  lea     r15, ??_7?$CComObject@VCWMPRichPreviewExt@@@ATL@@6BIPreviewHandler@@@; const ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandler'}
0x14000ad88  mov     [rbx+18h], rax
0x14000ad8c  lea     r12, ??_7?$CComObject@VCWMPRichPreviewExt@@@ATL@@6BIInitializeWithFile@@@; const ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IInitializeWithFile'}
0x14000ad93  mov     [rbx], r15
0x14000ad96  lea     r13, ??_7?$CComObject@VCWMPRichPreviewExt@@@ATL@@6BIObjectWithSite@@@; const ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IObjectWithSite'}
0x14000ad9d  mov     [rbx+8], r12
0x14000ada1  mov     [rbx+10h], r13
0x14000ada5  lock inc cs:dword_1400153D8
0x14000adac  mov     rcx, rbx; this
0x14000adaf  call    ?FinalConstruct@CWMPRichPreviewExt@@QEAAJXZ; CWMPRichPreviewExt::FinalConstruct(void)
0x14000adb4  mov     edi, eax
0x14000adb6  test    eax, eax
0x14000adb8  jnz     short loc_14000ADD4
0x14000adba  mov     rax, [rbx]
0x14000adbd  mov     r8, rsi
0x14000adc0  mov     rdx, rbp
0x14000adc3  mov     rcx, rbx
0x14000adc6  mov     rax, [rax]
0x14000adc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000adce  mov     edi, eax
0x14000add0  test    eax, eax
0x14000add2  jz      short loc_14000AE13
0x14000add4  lea     rax, ??_7?$CComObject@VCWMPRichPreviewExt@@@ATL@@6BIPreviewHandlerVisuals@@@; const ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandlerVisuals'}
0x14000addb  mov     [rbx], r15
0x14000adde  mov     rcx, rbx; this
0x14000ade1  mov     [rbx+18h], rax
0x14000ade5  mov     [rbx+8], r12
0x14000ade9  mov     [rbx+10h], r13
0x14000aded  mov     dword ptr [rbx+20h], 1
0x14000adf4  call    ?FinalRelease@CWMPRichPreviewExt@@QEAAJXZ; CWMPRichPreviewExt::FinalRelease(void)
0x14000adf9  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x14000adfe  mov     rcx, rbx; this
0x14000ae01  call    ??1CWMPRichPreviewExt@@QEAA@XZ; CWMPRichPreviewExt::~CWMPRichPreviewExt(void)
0x14000ae06  mov     edx, 0A0h; unsigned __int64
0x14000ae0b  mov     rcx, rbx; void *
0x14000ae0e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ae13  mov     eax, edi
0x14000ae15  add     rsp, 20h
0x14000ae19  pop     r15
0x14000ae1b  pop     r13
0x14000ae1d  pop     r12
0x14000ae1f  pop     rdi
0x14000ae20  pop     rsi
0x14000ae21  pop     rbp
0x14000ae22  pop     rbx
0x14000ae23  retn
```

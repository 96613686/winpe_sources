# ATL::CComObject<CWMPRichPreviewExt>::Release(void)

- ea: `0x14000c630`
- end: `0x14000c6c6`
- name: `?Release@?$CComObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ`
- size: `150`
- prototype: `__int64 __fastcall(CWMPRichPreviewExt *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14000c6d0`
- `0x14000c6e0`
- `0x14000c6f0`

## callees

- `0x140001008`
- `0x140002370`
- `0x140004784`
- `0x14000c630`
- `0x14000c818`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewExt>::Release(CWMPRichPreviewExt *this)
{
  int v1; // edi
  unsigned int v3; // edi
  CExeModule *v4; // rcx

  v1 = *((_DWORD *)this + 8);
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    *((_DWORD *)this + 8) = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_1400153D8);
      if ( this )
      {
        *((_DWORD *)this + 8) = 1;
        *(_QWORD *)this = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandler'};
        *((_QWORD *)this + 1) = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IInitializeWithFile'};
        *((_QWORD *)this + 2) = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IObjectWithSite'};
        *((_QWORD *)this + 3) = &ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandlerVisuals'};
        CWMPRichPreviewExt::FinalRelease(this);
        CExeModule::Unlock(v4);
        CWMPRichPreviewExt::~CWMPRichPreviewExt(this);
        operator delete(this);
      }
      CExeModule::Unlock(this);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14000c630  mov     [rsp+arg_0], rbx
0x14000c635  push    rdi
0x14000c636  sub     rsp, 20h
0x14000c63a  mov     edi, [rcx+20h]
0x14000c63d  mov     rbx, rcx
0x14000c640  cmp     edi, 7FFFFFFFh
0x14000c646  jnz     short loc_14000C64F
0x14000c648  mov     edi, 7FFFFFFEh
0x14000c64d  jmp     short loc_14000C6B9
0x14000c64f  sub     edi, 1
0x14000c652  mov     [rcx+20h], edi
0x14000c655  jnz     short loc_14000C6B9
0x14000c657  lock inc cs:dword_1400153D8
0x14000c65e  test    rbx, rbx
0x14000c661  jz      short loc_14000C6B4
0x14000c663  lea     rax, ??_7?$CComObject@VCWMPRichPreviewExt@@@ATL@@6BIPreviewHandler@@@; const ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandler'}
0x14000c66a  mov     dword ptr [rcx+20h], 1
0x14000c671  mov     [rcx], rax
0x14000c674  lea     rax, ??_7?$CComObject@VCWMPRichPreviewExt@@@ATL@@6BIInitializeWithFile@@@; const ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IInitializeWithFile'}
0x14000c67b  mov     [rcx+8], rax
0x14000c67f  lea     rax, ??_7?$CComObject@VCWMPRichPreviewExt@@@ATL@@6BIObjectWithSite@@@; const ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IObjectWithSite'}
0x14000c686  mov     [rcx+10h], rax
0x14000c68a  lea     rax, ??_7?$CComObject@VCWMPRichPreviewExt@@@ATL@@6BIPreviewHandlerVisuals@@@; const ATL::CComObject<CWMPRichPreviewExt>::`vftable'{for `IPreviewHandlerVisuals'}
0x14000c691  mov     [rcx+18h], rax
0x14000c695  call    ?FinalRelease@CWMPRichPreviewExt@@QEAAJXZ; CWMPRichPreviewExt::FinalRelease(void)
0x14000c69a  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x14000c69f  mov     rcx, rbx; this
0x14000c6a2  call    ??1CWMPRichPreviewExt@@QEAA@XZ; CWMPRichPreviewExt::~CWMPRichPreviewExt(void)
0x14000c6a7  mov     edx, 0A0h; unsigned __int64
0x14000c6ac  mov     rcx, rbx; void *
0x14000c6af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c6b4  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x14000c6b9  mov     rbx, [rsp+28h+arg_0]
0x14000c6be  mov     eax, edi
0x14000c6c0  add     rsp, 20h
0x14000c6c4  pop     rdi
0x14000c6c5  retn
```

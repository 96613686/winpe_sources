# ATL::CComObject<CRecoExt>::~CComObject<CRecoExt>(void)

- ea: `0x1800057f8`
- end: `0x18000588c`
- name: `??1?$CComObject@VCRecoExt@@@ATL@@UEAA@XZ`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005940`

## callees

- `0x1800057f8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005880`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005880`

## pseudocode

```c
void __fastcall ATL::CComObject<CRecoExt>::~CComObject<CRecoExt>(__int64 a1)
{
  *(_DWORD *)(a1 + 64) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CRecoExt>::`vftable'{for `IMsasrRecoExt'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CRecoExt>::`vftable'{for `ISpDisplayAlternates'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<CRecoExt>::`vftable'{for `ISpDisplayAlternatesPrivate'};
  *(_QWORD *)(a1 + 24) = &ATL::CComObject<CRecoExt>::`vftable'{for `ISpEnginePronunciation'};
  *(_QWORD *)(a1 + 32) = &ATL::CComObject<CRecoExt>::`vftable'{for `ISpServExtCFGPrep'};
  *(_QWORD *)(a1 + 40) = &ATL::CComObject<CRecoExt>::`vftable'{for `ISpServExtBargeIn'};
  *(_QWORD *)(a1 + 48) = &ATL::CComObject<CRecoExt>::`vftable'{for `IMSSRCFGPreparationV10'};
  *(_QWORD *)(a1 + 56) = &ATL::CComObject<CRecoExt>::`vftable'{for `IEnginePronunciationPrivate'};
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( *(_BYTE *)(a1 + 112) )
  {
    *(_BYTE *)(a1 + 112) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  }
}

```

## disassembly

```asm
0x1800057f8  push    rbx
0x1800057fa  sub     rsp, 20h
0x1800057fe  mov     dword ptr [rcx+40h], 0C0000001h
0x180005805  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BIMsasrRecoExt@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `IMsasrRecoExt'}
0x18000580c  mov     [rcx], rax
0x18000580f  mov     rbx, rcx
0x180005812  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BISpDisplayAlternates@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `ISpDisplayAlternates'}
0x180005819  mov     [rcx+8], rax
0x18000581d  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BISpDisplayAlternatesPrivate@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `ISpDisplayAlternatesPrivate'}
0x180005824  mov     [rcx+10h], rax
0x180005828  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BISpEnginePronunciation@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `ISpEnginePronunciation'}
0x18000582f  mov     [rcx+18h], rax
0x180005833  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BISpServExtCFGPrep@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `ISpServExtCFGPrep'}
0x18000583a  mov     [rcx+20h], rax
0x18000583e  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BISpServExtBargeIn@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `ISpServExtBargeIn'}
0x180005845  mov     [rcx+28h], rax
0x180005849  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BIMSSRCFGPreparationV10@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `IMSSRCFGPreparationV10'}
0x180005850  mov     [rcx+30h], rax
0x180005854  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BIEnginePronunciationPrivate@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `IEnginePronunciationPrivate'}
0x18000585b  mov     [rcx+38h], rax
0x18000585f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005866  mov     rax, [rcx]
0x180005869  mov     rax, [rax+10h]
0x18000586d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005872  lea     rcx, [rbx+48h]; lpCriticalSection
0x180005876  cmp     byte ptr [rcx+28h], 0
0x18000587a  jz      short loc_180005886
0x18000587c  mov     byte ptr [rcx+28h], 0
0x180005880  call    cs:__imp_DeleteCriticalSection
0x180005886  add     rsp, 20h
0x18000588a  pop     rbx
0x18000588b  retn
```

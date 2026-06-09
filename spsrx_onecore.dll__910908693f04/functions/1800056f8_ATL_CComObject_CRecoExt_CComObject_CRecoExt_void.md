# ATL::CComObject<CRecoExt>::CComObject<CRecoExt>(void *)

- ea: `0x1800056f8`
- end: `0x18000578f`
- name: `??0?$CComObject@VCRecoExt@@@ATL@@QEAA@PEAX@Z`
- size: `151`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006b88`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRecoExt>::CComObject<CRecoExt>(__int64 a1)
{
  *(_DWORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_OWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_BYTE *)(a1 + 112) = 0;
  *(_QWORD *)a1 = &ATL::CComObject<CRecoExt>::`vftable'{for `IMsasrRecoExt'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CRecoExt>::`vftable'{for `ISpDisplayAlternates'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<CRecoExt>::`vftable'{for `ISpDisplayAlternatesPrivate'};
  *(_QWORD *)(a1 + 24) = &ATL::CComObject<CRecoExt>::`vftable'{for `ISpEnginePronunciation'};
  *(_QWORD *)(a1 + 32) = &ATL::CComObject<CRecoExt>::`vftable'{for `ISpServExtCFGPrep'};
  *(_QWORD *)(a1 + 40) = &ATL::CComObject<CRecoExt>::`vftable'{for `ISpServExtBargeIn'};
  *(_QWORD *)(a1 + 48) = &ATL::CComObject<CRecoExt>::`vftable'{for `IMSSRCFGPreparationV10'};
  *(_QWORD *)(a1 + 56) = &ATL::CComObject<CRecoExt>::`vftable'{for `IEnginePronunciationPrivate'};
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return a1;
}

```

## disassembly

```asm
0x1800056f8  push    rbx
0x1800056fa  sub     rsp, 20h
0x1800056fe  mov     dword ptr [rcx+40h], 0
0x180005705  xor     eax, eax
0x180005707  xorps   xmm0, xmm0
0x18000570a  mov     rbx, rcx
0x18000570d  movups  xmmword ptr [rcx+48h], xmm0
0x180005711  movups  xmmword ptr [rcx+58h], xmm0
0x180005715  mov     [rcx+68h], rax
0x180005719  mov     [rcx+70h], al
0x18000571c  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BIMsasrRecoExt@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `IMsasrRecoExt'}
0x180005723  mov     [rcx], rax
0x180005726  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BISpDisplayAlternates@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `ISpDisplayAlternates'}
0x18000572d  mov     [rcx+8], rax
0x180005731  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BISpDisplayAlternatesPrivate@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `ISpDisplayAlternatesPrivate'}
0x180005738  mov     [rcx+10h], rax
0x18000573c  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BISpEnginePronunciation@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `ISpEnginePronunciation'}
0x180005743  mov     [rcx+18h], rax
0x180005747  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BISpServExtCFGPrep@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `ISpServExtCFGPrep'}
0x18000574e  mov     [rcx+20h], rax
0x180005752  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BISpServExtBargeIn@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `ISpServExtBargeIn'}
0x180005759  mov     [rcx+28h], rax
0x18000575d  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BIMSSRCFGPreparationV10@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `IMSSRCFGPreparationV10'}
0x180005764  mov     [rcx+30h], rax
0x180005768  lea     rax, ??_7?$CComObject@VCRecoExt@@@ATL@@6BIEnginePronunciationPrivate@@@; const ATL::CComObject<CRecoExt>::`vftable'{for `IEnginePronunciationPrivate'}
0x18000576f  mov     [rcx+38h], rax
0x180005773  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000577a  mov     rax, [rcx]
0x18000577d  mov     rax, [rax+8]
0x180005781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005786  mov     rax, rbx
0x180005789  add     rsp, 20h
0x18000578d  pop     rbx
0x18000578e  retn
```

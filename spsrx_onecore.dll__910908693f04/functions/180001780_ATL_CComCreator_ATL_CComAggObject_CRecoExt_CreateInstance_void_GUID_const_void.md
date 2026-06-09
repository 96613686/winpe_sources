# ATL::CComCreator<ATL::CComAggObject<CRecoExt>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001780`
- end: `0x180001986`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCRecoExt@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `518`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001760`

## callees

- `0x180001780`
- `0x180001b30`
- `0x180001b50`
- `0x180001b80`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800017e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800017e6`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CRecoExt>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v7; // edi
  _DWORD *v8; // rax
  __int64 (__fastcall ***v9)(_QWORD, __int64, _QWORD *); // rbx
  void (*v10)(void); // rax
  int v11; // eax
  __int64 (__fastcall *v12)(_QWORD, __int64, _QWORD *); // rax
  unsigned int Interface; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  if ( g_heap && (v8 = HeapAlloc(g_heap, 0, 0xA0u), (v9 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))v8) != 0) )
  {
    v8[2] = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CRecoExt>::`vftable';
    *((_OWORD *)v8 + 6) = 0;
    *((_OWORD *)v8 + 7) = 0;
    *((_QWORD *)v8 + 16) = 0;
    *((_BYTE *)v8 + 136) = 0;
    *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CRecoExt>::`vftable'{for `IMsasrRecoExt'};
    *((_QWORD *)v8 + 4) = &ATL::CComContainedObject<CRecoExt>::`vftable'{for `ISpDisplayAlternates'};
    *((_QWORD *)v8 + 5) = &ATL::CComContainedObject<CRecoExt>::`vftable'{for `ISpDisplayAlternatesPrivate'};
    *((_QWORD *)v8 + 6) = &ATL::CComContainedObject<CRecoExt>::`vftable'{for `ISpEnginePronunciation'};
    *((_QWORD *)v8 + 7) = &ATL::CComContainedObject<CRecoExt>::`vftable'{for `ISpServExtCFGPrep'};
    *((_QWORD *)v8 + 8) = &ATL::CComContainedObject<CRecoExt>::`vftable'{for `ISpServExtBargeIn'};
    *((_QWORD *)v8 + 9) = &ATL::CComContainedObject<CRecoExt>::`vftable'{for `IMSSRCFGPreparationV10'};
    *((_QWORD *)v8 + 10) = &ATL::CComContainedObject<CRecoExt>::`vftable'{for `IEnginePronunciationPrivate'};
    *((_QWORD *)v8 + 11) = a1;
    v10 = *(void (**)(void))(*(_QWORD *)ATL::_pAtlModule + 8LL);
    if ( (char *)v10 == (char *)ATL::CAtlModule::Lock )
      ATL::CAtlModule::Lock(ATL::_pAtlModule);
    else
      v10();
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v11 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v9 + 12));
    if ( v11 >= 0 )
    {
      *((_BYTE *)v9 + 136) = 1;
      if ( (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))v9[3][46])(v9 + 3) == v9 + 3 )
      {
        v11 = -2147467259;
      }
      else
      {
        v11 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v9[11])(
                v9[11],
                &IID__ISpPrivateEngineCall,
                (__int64)(v9 + 18));
        if ( v11 >= 0 )
          v9[19] = 0;
      }
    }
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7
      || ((v12 = **v9, (char *)v12 != (char *)ATL::CComAggObject<CRecoExt>::QueryInterface)
        ? (Interface = v12(v9, a2, a3))
        : (Interface = ATL::CComAggObject<CRecoExt>::QueryInterface(v9, a2, a3)),
          (v7 = Interface) != 0) )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *), __int64))(*v9)[3])(v9, 1);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180001780  mov     [rsp+arg_0], rbx
0x180001785  mov     [rsp+arg_10], r8
0x18000178a  mov     [rsp+arg_8], rdx
0x18000178f  push    rsi
0x180001790  push    rdi
0x180001791  push    r12
0x180001793  push    r14
0x180001795  push    r15
0x180001797  sub     rsp, 30h
0x18000179b  mov     r14, r8
0x18000179e  mov     r15, rdx
0x1800017a1  mov     r12, rcx
0x1800017a4  test    r8, r8
0x1800017a7  jnz     short loc_1800017C0
0x1800017a9  mov     eax, 80004003h
0x1800017ae  mov     rbx, [rsp+58h+arg_0]
0x1800017b3  add     rsp, 30h
0x1800017b7  pop     r15
0x1800017b9  pop     r14
0x1800017bb  pop     r12
0x1800017bd  pop     rdi
0x1800017be  pop     rsi
0x1800017bf  retn
0x1800017c0  xor     esi, esi
0x1800017c2  mov     [r8], rsi
0x1800017c5  mov     edi, 8007000Eh
0x1800017ca  mov     [rsp+58h+arg_18], edi
0x1800017ce  mov     rcx, cs:?g_heap@@3VCHeap@@A; hHeap
0x1800017d5  test    rcx, rcx
0x1800017d8  jz      loc_1800018A3
0x1800017de  xor     edx, edx; dwFlags
0x1800017e0  mov     r8d, 0A0h; dwBytes
0x1800017e6  call    cs:__imp_HeapAlloc
0x1800017ec  mov     rbx, rax
0x1800017ef  test    rax, rax
0x1800017f2  jz      loc_1800018A3
0x1800017f8  mov     [rax+8], esi
0x1800017fb  lea     rax, ??_7?$CComAggObject@VCRecoExt@@@ATL@@6B@; const ATL::CComAggObject<CRecoExt>::`vftable'
0x180001802  mov     [rbx], rax
0x180001805  xorps   xmm0, xmm0
0x180001808  xor     eax, eax
0x18000180a  movups  xmmword ptr [rbx+60h], xmm0
0x18000180e  movups  xmmword ptr [rbx+70h], xmm0
0x180001812  mov     [rbx+80h], rax
0x180001819  mov     [rbx+88h], al
0x18000181f  lea     rax, ??_7?$CComContainedObject@VCRecoExt@@@ATL@@6BIMsasrRecoExt@@@; const ATL::CComContainedObject<CRecoExt>::`vftable'{for `IMsasrRecoExt'}
0x180001826  mov     [rbx+18h], rax
0x18000182a  lea     rax, ??_7?$CComContainedObject@VCRecoExt@@@ATL@@6BISpDisplayAlternates@@@; const ATL::CComContainedObject<CRecoExt>::`vftable'{for `ISpDisplayAlternates'}
0x180001831  mov     [rbx+20h], rax
0x180001835  lea     rax, ??_7?$CComContainedObject@VCRecoExt@@@ATL@@6BISpDisplayAlternatesPrivate@@@; const ATL::CComContainedObject<CRecoExt>::`vftable'{for `ISpDisplayAlternatesPrivate'}
0x18000183c  mov     [rbx+28h], rax
0x180001840  lea     rax, ??_7?$CComContainedObject@VCRecoExt@@@ATL@@6BISpEnginePronunciation@@@; const ATL::CComContainedObject<CRecoExt>::`vftable'{for `ISpEnginePronunciation'}
0x180001847  mov     [rbx+30h], rax
0x18000184b  lea     rax, ??_7?$CComContainedObject@VCRecoExt@@@ATL@@6BISpServExtCFGPrep@@@; const ATL::CComContainedObject<CRecoExt>::`vftable'{for `ISpServExtCFGPrep'}
0x180001852  mov     [rbx+38h], rax
0x180001856  lea     rax, ??_7?$CComContainedObject@VCRecoExt@@@ATL@@6BISpServExtBargeIn@@@; const ATL::CComContainedObject<CRecoExt>::`vftable'{for `ISpServExtBargeIn'}
0x18000185d  mov     [rbx+40h], rax
0x180001861  lea     rax, ??_7?$CComContainedObject@VCRecoExt@@@ATL@@6BIMSSRCFGPreparationV10@@@; const ATL::CComContainedObject<CRecoExt>::`vftable'{for `IMSSRCFGPreparationV10'}
0x180001868  mov     [rbx+48h], rax
0x18000186c  lea     rax, ??_7?$CComContainedObject@VCRecoExt@@@ATL@@6BIEnginePronunciationPrivate@@@; const ATL::CComContainedObject<CRecoExt>::`vftable'{for `IEnginePronunciationPrivate'}
0x180001873  mov     [rbx+50h], rax
0x180001877  mov     [rbx+58h], r12
0x18000187b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; this
0x180001882  mov     rax, [rcx]
0x180001885  mov     rax, [rax+8]
0x180001889  lea     rdx, ?Lock@CAtlModule@ATL@@UEAAJXZ; ATL::CAtlModule::Lock(void)
0x180001890  cmp     rax, rdx
0x180001893  jnz     short loc_18000189C
0x180001895  call    ?Lock@CAtlModule@ATL@@UEAAJXZ; ATL::CAtlModule::Lock(void)
0x18000189a  jmp     short loc_1800018A6
0x18000189c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018a1  jmp     short loc_1800018A6
0x1800018a3  mov     rbx, rsi
0x1800018a6  mov     [rsp+58h+var_38], rbx
0x1800018ab  jmp     short loc_1800018C2
0x1800018ad  xor     esi, esi
0x1800018af  mov     r14, [rsp+58h+arg_10]
0x1800018b4  mov     r15, [rsp+58h+arg_8]
0x1800018b9  mov     edi, [rsp+58h+arg_18]
0x1800018bd  mov     rbx, [rsp+58h+var_38]
0x1800018c2  test    rbx, rbx
0x1800018c5  jz      loc_180001972
0x1800018cb  lea     rcx, [rbx+60h]; this
0x1800018cf  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800018d4  test    eax, eax
0x1800018d6  js      short loc_180001926
0x1800018d8  mov     byte ptr [rbx+88h], 1
0x1800018df  lea     rdi, [rbx+18h]
0x1800018e3  mov     rax, [rdi]
0x1800018e6  mov     rcx, rdi
0x1800018e9  mov     rax, [rax+170h]
0x1800018f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018f5  cmp     rax, rdi
0x1800018f8  jnz     short loc_180001901
0x1800018fa  mov     eax, 80004005h
0x1800018ff  jmp     short loc_180001926
0x180001901  mov     rcx, [rdi+40h]
0x180001905  mov     rax, [rcx]
0x180001908  lea     r8, [rdi+78h]
0x18000190c  lea     rdx, IID__ISpPrivateEngineCall
0x180001913  mov     rax, [rax]
0x180001916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000191b  test    eax, eax
0x18000191d  js      short loc_180001926
0x18000191f  mov     [rdi+80h], rsi
0x180001926  mov     edi, esi
0x180001928  test    eax, eax
0x18000192a  cmovs   edi, eax
0x18000192d  test    edi, edi
0x18000192f  jnz     short loc_18000195E
0x180001931  mov     rax, [rbx]
0x180001934  mov     rax, [rax]
0x180001937  lea     rcx, ?QueryInterface@?$CComAggObject@VCRecoExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComAggObject<CRecoExt>::QueryInterface(_GUID const &,void * *)
0x18000193e  mov     r8, r14
0x180001941  mov     rdx, r15
0x180001944  cmp     rax, rcx
0x180001947  mov     rcx, rbx
0x18000194a  jnz     short loc_180001953
0x18000194c  call    ?QueryInterface@?$CComAggObject@VCRecoExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComAggObject<CRecoExt>::QueryInterface(_GUID const &,void * *)
0x180001951  jmp     short loc_180001958
0x180001953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001958  mov     edi, eax
0x18000195a  test    eax, eax
0x18000195c  jz      short loc_180001972
0x18000195e  mov     rax, [rbx]
0x180001961  mov     edx, 1
0x180001966  mov     rcx, rbx
0x180001969  mov     rax, [rax+18h]
0x18000196d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001972  mov     eax, edi
0x180001974  mov     rbx, [rsp+58h+arg_0]
0x180001979  add     rsp, 30h
0x18000197d  pop     r15
0x18000197f  pop     r14
0x180001981  pop     r12
0x180001983  pop     rdi
0x180001984  pop     rsi
0x180001985  retn
```

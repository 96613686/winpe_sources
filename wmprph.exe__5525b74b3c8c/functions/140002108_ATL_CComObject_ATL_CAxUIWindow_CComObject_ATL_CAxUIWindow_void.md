# ATL::CComObject<ATL::CAxUIWindow>::~CComObject<ATL::CAxUIWindow>(void)

- ea: `0x140002108`
- end: `0x140002187`
- name: `??1?$CComObject@VCAxUIWindow@ATL@@@ATL@@QEAA@XZ`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140007ab0`

## callees

- `0x140002108`
- `0x14000c818`
- `0x14000d83c`
- `0x14000f010`

## import_xrefs

- `USER32!DestroyWindow` at `0x140002153`
- `USER32!DestroyWindow` at `0x140002153`

## pseudocode

```c
void __fastcall ATL::CComObject<ATL::CAxUIWindow>::~CComObject<ATL::CAxUIWindow>(__int64 a1)
{
  __int64 v2; // rcx
  CExeModule *v3; // rcx
  __int64 v4; // rcx
  AtlThunkData_t *v5; // rcx

  *(_DWORD *)(a1 + 72) = 1;
  *(_QWORD *)a1 = &ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `ATL::CWindowImpl<ATL::CAxUIWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'};
  *(_QWORD *)(a1 + 64) = &ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `IOleInPlaceUIWindow'};
  v2 = *(_QWORD *)(a1 + 80);
  if ( v2 )
  {
    *(_QWORD *)(a1 + 80) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = *(CExeModule **)(a1 + 8);
  if ( v3 )
    DestroyWindow((HWND)v3);
  CExeModule::Unlock(v3);
  v4 = *(_QWORD *)(a1 + 80);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *(AtlThunkData_t **)(a1 + 40);
  if ( v5 )
    AtlThunk_FreeData(v5);
}

```

## disassembly

```asm
0x140002108  push    rbx
0x14000210a  sub     rsp, 20h
0x14000210e  lea     rax, ??_7?$CComObject@VCAxUIWindow@ATL@@@ATL@@6B?$CWindowImpl@VCAxUIWindow@ATL@@VCWindow@2@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@1@@; const ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `ATL::CWindowImpl<ATL::CAxUIWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'}
0x140002115  mov     dword ptr [rcx+48h], 1
0x14000211c  mov     [rcx], rax
0x14000211f  mov     rbx, rcx
0x140002122  lea     rax, ??_7?$CComObject@VCAxUIWindow@ATL@@@ATL@@6BIOleInPlaceUIWindow@@@; const ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `IOleInPlaceUIWindow'}
0x140002129  mov     [rcx+40h], rax
0x14000212d  mov     rcx, [rcx+50h]
0x140002131  test    rcx, rcx
0x140002134  jz      short loc_14000214A
0x140002136  mov     qword ptr [rbx+50h], 0
0x14000213e  mov     rax, [rcx]
0x140002141  mov     rax, [rax+10h]
0x140002145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000214a  mov     rcx, [rbx+8]; hWnd
0x14000214e  test    rcx, rcx
0x140002151  jz      short loc_140002159
0x140002153  call    cs:__imp_DestroyWindow
0x140002159  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x14000215e  mov     rcx, [rbx+50h]
0x140002162  test    rcx, rcx
0x140002165  jz      short loc_140002173
0x140002167  mov     rax, [rcx]
0x14000216a  mov     rax, [rax+10h]
0x14000216e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002173  mov     rcx, [rbx+28h]; Thunk
0x140002177  test    rcx, rcx
0x14000217a  jz      short loc_140002181
0x14000217c  call    AtlThunk_FreeData
0x140002181  add     rsp, 20h
0x140002185  pop     rbx
0x140002186  retn
```

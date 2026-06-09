# ATL::CComObject<ATL::CAxFrameWindow>::~CComObject<ATL::CAxFrameWindow>(void)

- ea: `0x140002080`
- end: `0x1400020ff`
- name: `??1?$CComObject@VCAxFrameWindow@ATL@@@ATL@@QEAA@XZ`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140007a40`

## callees

- `0x140002080`
- `0x14000c818`
- `0x14000d83c`
- `0x14000f010`

## import_xrefs

- `USER32!DestroyWindow` at `0x1400020cb`
- `USER32!DestroyWindow` at `0x1400020cb`

## pseudocode

```c
void __fastcall ATL::CComObject<ATL::CAxFrameWindow>::~CComObject<ATL::CAxFrameWindow>(__int64 a1)
{
  __int64 v2; // rcx
  CExeModule *v3; // rcx
  __int64 v4; // rcx
  AtlThunkData_t *v5; // rcx

  *(_DWORD *)(a1 + 72) = 1;
  *(_QWORD *)a1 = &ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `ATL::CWindowImpl<ATL::CAxUIWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'};
  *(_QWORD *)(a1 + 64) = &ATL::CComObject<ATL::CAxFrameWindow>::`vftable'{for `IOleInPlaceFrame'};
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
0x140002080  push    rbx
0x140002082  sub     rsp, 20h
0x140002086  lea     rax, ??_7?$CComObject@VCAxUIWindow@ATL@@@ATL@@6B?$CWindowImpl@VCAxUIWindow@ATL@@VCWindow@2@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@1@@; const ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `ATL::CWindowImpl<ATL::CAxUIWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'}
0x14000208d  mov     dword ptr [rcx+48h], 1
0x140002094  mov     [rcx], rax
0x140002097  mov     rbx, rcx
0x14000209a  lea     rax, ??_7?$CComObject@VCAxFrameWindow@ATL@@@ATL@@6BIOleInPlaceFrame@@@; const ATL::CComObject<ATL::CAxFrameWindow>::`vftable'{for `IOleInPlaceFrame'}
0x1400020a1  mov     [rcx+40h], rax
0x1400020a5  mov     rcx, [rcx+50h]
0x1400020a9  test    rcx, rcx
0x1400020ac  jz      short loc_1400020C2
0x1400020ae  mov     qword ptr [rbx+50h], 0
0x1400020b6  mov     rax, [rcx]
0x1400020b9  mov     rax, [rax+10h]
0x1400020bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020c2  mov     rcx, [rbx+8]; hWnd
0x1400020c6  test    rcx, rcx
0x1400020c9  jz      short loc_1400020D1
0x1400020cb  call    cs:__imp_DestroyWindow
0x1400020d1  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x1400020d6  mov     rcx, [rbx+50h]
0x1400020da  test    rcx, rcx
0x1400020dd  jz      short loc_1400020EB
0x1400020df  mov     rax, [rcx]
0x1400020e2  mov     rax, [rax+10h]
0x1400020e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020eb  mov     rcx, [rbx+28h]; Thunk
0x1400020ef  test    rcx, rcx
0x1400020f2  jz      short loc_1400020F9
0x1400020f4  call    AtlThunk_FreeData
0x1400020f9  add     rsp, 20h
0x1400020fd  pop     rbx
0x1400020fe  retn
```

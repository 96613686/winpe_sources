# CViewSettings::_SaveToPropertyBag(IPropertyBag *)

- ea: `0x1801725c0`
- end: `0x18017285d`
- name: `?_SaveToPropertyBag@CViewSettings@@AEAAJPEAUIPropertyBag@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(CViewSettings *__hidden this, struct IPropertyBag *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180172520`
- `0x180533310`
- `0x18053400c`

## callees

- `0x18010fce8`
- `0x1801725c0`
- `0x180172864`
- `0x18017290c`
- `0x180172944`
- `0x180172b74`
- `0x180172df8`
- `0x180187e6c`
- `0x18065a010`

## import_xrefs

- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x18017273c`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x18017273c`
- `PROPSYS!PSPropertyBag_Delete` at `0x180172704`
- `PROPSYS!PSPropertyBag_Delete` at `0x1801727f7`
- `PROPSYS!PSPropertyBag_Delete` at `0x180172852`
- `PROPSYS!PSPropertyBag_Delete` at `0x180172704`
- `PROPSYS!PSPropertyBag_Delete` at `0x1801727f7`
- `PROPSYS!PSPropertyBag_Delete` at `0x180172852`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801726b0`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801727b2`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801727e2`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801726b0`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801727b2`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801727e2`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801725e7`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801725fe`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180172615`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180172650`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180172771`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801725e7`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801725fe`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180172615`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180172650`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180172771`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x18017274f`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x18017274f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18017269d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18017279f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1801727cf`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18017269d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18017279f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1801727cf`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18017265a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180172679`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801726d9`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18017265a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180172679`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801726d9`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_GetDPIAdjustedLogicalSize` at `0x18017263d`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_GetDPIAdjustedLogicalSize` at `0x18017263d`

## pseudocode

```c
__int64 __fastcall CViewSettings::_SaveToPropertyBag(CViewSettings *this, struct IPropertyBag *a2)
{
  enum FOLDERVIEWMODE v4; // eax
  __int64 v5; // rdx
  BOOL v6; // ebp
  DWORD DPIAdjustedLogicalSize; // r8d
  struct IStream *v8; // rax
  IStream *v9; // rsi
  struct IStream *v10; // rax
  IStream *v11; // rsi
  struct IStream *v12; // rax
  IStream *v13; // rsi
  _QWORD *v14; // rsi
  __int64 v16; // rax

  v4 = ViewModeFromLogicalViewMode(*((enum FOLDERLOGICALVIEWMODE *)this + 50));
  PSPropertyBag_WriteDWORD(a2, L"Mode", v4);
  PSPropertyBag_WriteDWORD(a2, L"LogicalViewMode", *((_DWORD *)this + 50));
  PSPropertyBag_WriteDWORD(a2, L"FFlags", *((_DWORD *)this + 51));
  v6 = 1;
  if ( (*((_BYTE *)this + 204) & 0x20) != 0 )
  {
    LOBYTE(v5) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware>::GetImpl'::`2'::impl,
      v5);
    DPIAdjustedLogicalSize = *((_DWORD *)this + 44);
  }
  else
  {
    DPIAdjustedLogicalSize = SHELL32_GetDPIAdjustedLogicalSize(*((_QWORD *)this + 35), *((unsigned int *)this + 44), 1);
  }
  PSPropertyBag_WriteDWORD(a2, L"IconSize", DPIAdjustedLogicalSize);
  v8 = SHCreateMemStream(0, 0);
  v9 = v8;
  if ( v8 )
  {
    if ( CViewSettings::_SaveSortColumns(this, v8) )
    {
      PSPropertyBag_Delete(a2, L"Sort");
    }
    else
    {
      IStream_Reset(v9);
      PSPropertyBag_WriteStream(a2, L"Sort", v9);
    }
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( (*((_BYTE *)this + 204) & 0x20) == 0 )
  {
    v10 = SHCreateMemStream(0, 0);
    v11 = v10;
    if ( v10 )
    {
      if ( (unsigned int)CViewSettings::_SaveColumns(this, v10) )
      {
        PSPropertyBag_Delete(a2, L"ColInfo");
      }
      else
      {
        IStream_Reset(v11);
        PSPropertyBag_WriteStream(a2, L"ColInfo", v11);
      }
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  if ( !(unsigned int)CViewSettings::_ShouldSuppressGrouping(this) )
  {
    v12 = SHCreateMemStream(0, 0);
    v13 = v12;
    if ( v12 )
    {
      if ( CViewSettings::_SaveGroupState(this, v12) )
      {
        PSPropertyBag_Delete(a2, L"GroupCollapseState");
      }
      else
      {
        IStream_Reset(v13);
        PSPropertyBag_WriteStream(a2, L"GroupCollapseState", v13);
      }
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = (_QWORD *)((char *)this + 148);
    if ( *((_DWORD *)this + 41) == PKEY_Null.pid )
    {
      v16 = *v14 - *(_QWORD *)&PKEY_Null.fmtid.Data1;
      if ( *v14 == *(_QWORD *)&PKEY_Null.fmtid.Data1 )
        v16 = *(_QWORD *)((char *)this + 156) - *(_QWORD *)PKEY_Null.fmtid.Data4;
      if ( !v16 )
        v6 = 0;
    }
    PSPropertyBag_WriteBOOL(a2, L"GroupView", v6);
    PSPropertyBag_WritePropertyKey(a2, L"GroupByKey", (const PROPERTYKEY *const)((char *)this + 148));
    PSPropertyBag_WriteDWORD(a2, L"GroupByDirection", *((_DWORD *)this + 42) != 0 ? 1 : -1);
  }
  CViewSettings::_FireSaveEvent(this, a2);
  return 0;
}

```

## disassembly

```asm
0x1801725c0  push    rbx
0x1801725c2  push    rbp
0x1801725c3  push    rsi
0x1801725c4  push    rdi
0x1801725c5  sub     rsp, 28h
0x1801725c9  mov     rbx, rcx
0x1801725cc  mov     rdi, rdx
0x1801725cf  mov     ecx, [rcx+0C8h]; enum FOLDERLOGICALVIEWMODE
0x1801725d5  call    ?ViewModeFromLogicalViewMode@@YA?AW4FOLDERVIEWMODE@@W4FOLDERLOGICALVIEWMODE@@@Z; ViewModeFromLogicalViewMode(FOLDERLOGICALVIEWMODE)
0x1801725da  mov     r8d, eax; value
0x1801725dd  lea     rdx, aMode_0; "Mode"
0x1801725e4  mov     rcx, rdi; propBag
0x1801725e7  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1801725ed  mov     r8d, [rbx+0C8h]; value
0x1801725f4  lea     rdx, aLogicalviewmod; "LogicalViewMode"
0x1801725fb  mov     rcx, rdi; propBag
0x1801725fe  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180172604  mov     r8d, [rbx+0CCh]; value
0x18017260b  lea     rdx, aFflags; "FFlags"
0x180172612  mov     rcx, rdi; propBag
0x180172615  call    cs:__imp_PSPropertyBag_WriteDWORD
0x18017261b  test    byte ptr [rbx+0CCh], 20h
0x180172622  jnz     loc_1801727FF
0x180172628  mov     edx, [rbx+0B0h]
0x18017262e  mov     ebp, 1
0x180172633  mov     rcx, [rbx+118h]
0x18017263a  mov     r8d, ebp
0x18017263d  call    cs:__imp_SHELL32_GetDPIAdjustedLogicalSize
0x180172643  mov     r8d, eax; value
0x180172646  lea     rdx, aIconsize; "IconSize"
0x18017264d  mov     rcx, rdi; propBag
0x180172650  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180172656  xor     edx, edx; cbInit
0x180172658  xor     ecx, ecx; pInit
0x18017265a  call    cs:__imp_SHCreateMemStream
0x180172660  mov     rsi, rax
0x180172663  test    rax, rax
0x180172666  jnz     loc_18017278D
0x18017266c  test    byte ptr [rbx+0CCh], 20h
0x180172673  jnz     short loc_1801726C5
0x180172675  xor     edx, edx; cbInit
0x180172677  xor     ecx, ecx; pInit
0x180172679  call    cs:__imp_SHCreateMemStream
0x18017267f  mov     rsi, rax
0x180172682  test    rax, rax
0x180172685  jz      short loc_1801726C5
0x180172687  mov     rdx, rax; struct IStream *
0x18017268a  mov     rcx, rbx; this
0x18017268d  call    ?_SaveColumns@CViewSettings@@AEAAJPEAUIStream@@@Z; CViewSettings::_SaveColumns(IStream *)
0x180172692  test    eax, eax
0x180172694  jnz     loc_180172848
0x18017269a  mov     rcx, rsi; pstm
0x18017269d  call    cs:__imp_IStream_Reset
0x1801726a3  mov     r8, rsi; value
0x1801726a6  lea     rdx, aColinfo; "ColInfo"
0x1801726ad  mov     rcx, rdi; propBag
0x1801726b0  call    cs:__imp_PSPropertyBag_WriteStream
0x1801726b6  mov     rax, [rsi]
0x1801726b9  mov     rcx, rsi
0x1801726bc  mov     rax, [rax+10h]
0x1801726c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801726c5  mov     rcx, rbx; this
0x1801726c8  call    ?_ShouldSuppressGrouping@CViewSettings@@AEAAHXZ; CViewSettings::_ShouldSuppressGrouping(void)
0x1801726cd  test    eax, eax
0x1801726cf  jnz     loc_180172777
0x1801726d5  xor     edx, edx; cbInit
0x1801726d7  xor     ecx, ecx; pInit
0x1801726d9  call    cs:__imp_SHCreateMemStream
0x1801726df  mov     rsi, rax
0x1801726e2  test    rax, rax
0x1801726e5  jz      short loc_180172719
0x1801726e7  mov     rdx, rax; struct IStream *
0x1801726ea  mov     rcx, rbx; this
0x1801726ed  call    ?_SaveGroupState@CViewSettings@@AEAAJPEAUIStream@@@Z; CViewSettings::_SaveGroupState(IStream *)
0x1801726f2  test    eax, eax
0x1801726f4  jz      loc_1801727CC
0x1801726fa  lea     rdx, aGroupcollapses; "GroupCollapseState"
0x180172701  mov     rcx, rdi; propBag
0x180172704  call    cs:__imp_PSPropertyBag_Delete
0x18017270a  mov     rax, [rsi]
0x18017270d  mov     rcx, rsi
0x180172710  mov     rax, [rax+10h]
0x180172714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172719  mov     eax, cs:PKEY_Null.pid
0x18017271f  lea     rsi, [rbx+94h]
0x180172726  cmp     [rsi+10h], eax
0x180172729  jz      loc_180172821
0x18017272f  mov     r8d, ebp; value
0x180172732  lea     rdx, aGroupview; "GroupView"
0x180172739  mov     rcx, rdi; propBag
0x18017273c  call    cs:__imp_PSPropertyBag_WriteBOOL
0x180172742  mov     r8, rsi; value
0x180172745  lea     rdx, aGroupbykey; "GroupByKey"
0x18017274c  mov     rcx, rdi; propBag
0x18017274f  call    cs:__imp_PSPropertyBag_WritePropertyKey
0x180172755  mov     eax, [rbx+0A8h]
0x18017275b  lea     rdx, aGroupbydirecti; "GroupByDirection"
0x180172762  neg     eax
0x180172764  mov     rcx, rdi; propBag
0x180172767  sbb     r8d, r8d
0x18017276a  and     r8d, 2
0x18017276e  dec     r8d; value
0x180172771  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180172777  mov     rdx, rdi; struct IPropertyBag *
0x18017277a  mov     rcx, rbx; this
0x18017277d  call    ?_FireSaveEvent@CViewSettings@@AEAAXPEAUIPropertyBag@@@Z; CViewSettings::_FireSaveEvent(IPropertyBag *)
0x180172782  xor     eax, eax
0x180172784  add     rsp, 28h
0x180172788  pop     rdi
0x180172789  pop     rsi
0x18017278a  pop     rbp
0x18017278b  pop     rbx
0x18017278c  retn
0x18017278d  mov     rdx, rsi; struct IStream *
0x180172790  mov     rcx, rbx; this
0x180172793  call    ?_SaveSortColumns@CViewSettings@@AEAAJPEAUIStream@@@Z; CViewSettings::_SaveSortColumns(IStream *)
0x180172798  test    eax, eax
0x18017279a  jnz     short loc_1801727ED
0x18017279c  mov     rcx, rsi; pstm
0x18017279f  call    cs:__imp_IStream_Reset
0x1801727a5  mov     r8, rsi; value
0x1801727a8  lea     rdx, aSort; "Sort"
0x1801727af  mov     rcx, rdi; propBag
0x1801727b2  call    cs:__imp_PSPropertyBag_WriteStream
0x1801727b8  mov     rax, [rsi]
0x1801727bb  mov     rcx, rsi
0x1801727be  mov     rax, [rax+10h]
0x1801727c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801727c7  jmp     loc_18017266C
0x1801727cc  mov     rcx, rsi; pstm
0x1801727cf  call    cs:__imp_IStream_Reset
0x1801727d5  mov     r8, rsi; value
0x1801727d8  lea     rdx, aGroupcollapses; "GroupCollapseState"
0x1801727df  mov     rcx, rdi; propBag
0x1801727e2  call    cs:__imp_PSPropertyBag_WriteStream
0x1801727e8  jmp     loc_18017270A
0x1801727ed  lea     rdx, aSort; "Sort"
0x1801727f4  mov     rcx, rdi; propBag
0x1801727f7  call    cs:__imp_PSPropertyBag_Delete
0x1801727fd  jmp     short loc_1801727B8
0x1801727ff  xor     r8d, r8d
0x180172802  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware> `wil::Feature<__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware>::GetImpl(void)'::`2'::impl
0x180172809  lea     ebp, [r8+1]
0x18017280d  mov     dl, bpl
0x180172810  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180172815  mov     r8d, [rbx+0B0h]
0x18017281c  jmp     loc_180172646
0x180172821  mov     rax, [rsi]
0x180172824  sub     rax, qword ptr cs:PKEY_Null.fmtid.Data1
0x18017282b  jnz     short loc_180172838
0x18017282d  mov     rax, [rsi+8]
0x180172831  sub     rax, qword ptr cs:PKEY_Null.fmtid.Data4
0x180172838  test    rax, rax
0x18017283b  jnz     loc_18017272F
0x180172841  xor     ebp, ebp
0x180172843  jmp     loc_18017272F
0x180172848  lea     rdx, aColinfo; "ColInfo"
0x18017284f  mov     rcx, rdi; propBag
0x180172852  call    cs:__imp_PSPropertyBag_Delete
0x180172858  jmp     loc_1801726B6
```

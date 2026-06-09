# CViewSettings::_SaveToPropertyBag(IPropertyBag *)

- ea: `0x1801b1098`
- end: `0x1801b13ae`
- name: `?_SaveToPropertyBag@CViewSettings@@AEAAJPEAUIPropertyBag@@@Z`
- size: `790`
- prototype: `__int64 __fastcall(CViewSettings *__hidden this, struct IPropertyBag *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1801b0ff0`
- `0x180549fa0`
- `0x18054ad40`

## callees

- `0x18012efb4`
- `0x1801b1098`
- `0x1801b13b4`
- `0x1801b1460`
- `0x1801b149c`
- `0x1801b1dfc`
- `0x1801b1e8c`
- `0x1801b2118`
- `0x18067d010`

## import_xrefs

- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1801b1256`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1801b1256`
- `PROPSYS!PSPropertyBag_Delete` at `0x1801b1218`
- `PROPSYS!PSPropertyBag_Delete` at `0x1801b133c`
- `PROPSYS!PSPropertyBag_Delete` at `0x1801b139d`
- `PROPSYS!PSPropertyBag_Delete` at `0x1801b1218`
- `PROPSYS!PSPropertyBag_Delete` at `0x1801b133c`
- `PROPSYS!PSPropertyBag_Delete` at `0x1801b139d`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801b11b8`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801b12e5`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801b1321`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801b11b8`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801b12e5`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1801b1321`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801b10bf`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801b10dc`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801b10f9`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801b1140`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801b1297`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801b10bf`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801b10dc`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801b10f9`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801b1140`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801b1297`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x1801b126f`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x1801b126f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1801b119f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1801b12cc`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1801b1308`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1801b119f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1801b12cc`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1801b1308`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801b1150`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801b1175`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801b11e7`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801b1150`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801b1175`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1801b11e7`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_GetDPIAdjustedLogicalSize` at `0x1801b1127`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_GetDPIAdjustedLogicalSize` at `0x1801b1127`

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
0x1801b1098  push    rbx
0x1801b109a  push    rbp
0x1801b109b  push    rsi
0x1801b109c  push    rdi
0x1801b109d  sub     rsp, 28h
0x1801b10a1  mov     rbx, rcx
0x1801b10a4  mov     rdi, rdx
0x1801b10a7  mov     ecx, [rcx+0C8h]; enum FOLDERLOGICALVIEWMODE
0x1801b10ad  call    ?ViewModeFromLogicalViewMode@@YA?AW4FOLDERVIEWMODE@@W4FOLDERLOGICALVIEWMODE@@@Z; ViewModeFromLogicalViewMode(FOLDERLOGICALVIEWMODE)
0x1801b10b2  mov     r8d, eax; value
0x1801b10b5  lea     rdx, aMode_0; "Mode"
0x1801b10bc  mov     rcx, rdi; propBag
0x1801b10bf  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1801b10c6  nop     dword ptr [rax+rax+00h]
0x1801b10cb  mov     r8d, [rbx+0C8h]; value
0x1801b10d2  lea     rdx, aLogicalviewmod; "LogicalViewMode"
0x1801b10d9  mov     rcx, rdi; propBag
0x1801b10dc  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1801b10e3  nop     dword ptr [rax+rax+00h]
0x1801b10e8  mov     r8d, [rbx+0CCh]; value
0x1801b10ef  lea     rdx, aFflags; "FFlags"
0x1801b10f6  mov     rcx, rdi; propBag
0x1801b10f9  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1801b1100  nop     dword ptr [rax+rax+00h]
0x1801b1105  test    byte ptr [rbx+0CCh], 20h
0x1801b110c  jnz     loc_1801B134A
0x1801b1112  mov     edx, [rbx+0B0h]
0x1801b1118  mov     ebp, 1
0x1801b111d  mov     rcx, [rbx+118h]
0x1801b1124  mov     r8d, ebp
0x1801b1127  call    cs:__imp_SHELL32_GetDPIAdjustedLogicalSize
0x1801b112e  nop     dword ptr [rax+rax+00h]
0x1801b1133  mov     r8d, eax; value
0x1801b1136  lea     rdx, aIconsize; "IconSize"
0x1801b113d  mov     rcx, rdi; propBag
0x1801b1140  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1801b1147  nop     dword ptr [rax+rax+00h]
0x1801b114c  xor     edx, edx; cbInit
0x1801b114e  xor     ecx, ecx; pInit
0x1801b1150  call    cs:__imp_SHCreateMemStream
0x1801b1157  nop     dword ptr [rax+rax+00h]
0x1801b115c  mov     rsi, rax
0x1801b115f  test    rax, rax
0x1801b1162  jnz     loc_1801B12BA
0x1801b1168  test    byte ptr [rbx+0CCh], 20h
0x1801b116f  jnz     short loc_1801B11D3
0x1801b1171  xor     edx, edx; cbInit
0x1801b1173  xor     ecx, ecx; pInit
0x1801b1175  call    cs:__imp_SHCreateMemStream
0x1801b117c  nop     dword ptr [rax+rax+00h]
0x1801b1181  mov     rsi, rax
0x1801b1184  test    rax, rax
0x1801b1187  jz      short loc_1801B11D3
0x1801b1189  mov     rdx, rax; struct IStream *
0x1801b118c  mov     rcx, rbx; this
0x1801b118f  call    ?_SaveColumns@CViewSettings@@AEAAJPEAUIStream@@@Z; CViewSettings::_SaveColumns(IStream *)
0x1801b1194  test    eax, eax
0x1801b1196  jnz     loc_1801B1393
0x1801b119c  mov     rcx, rsi; pstm
0x1801b119f  call    cs:__imp_IStream_Reset
0x1801b11a6  nop     dword ptr [rax+rax+00h]
0x1801b11ab  mov     r8, rsi; value
0x1801b11ae  lea     rdx, aColinfo; "ColInfo"
0x1801b11b5  mov     rcx, rdi; propBag
0x1801b11b8  call    cs:__imp_PSPropertyBag_WriteStream
0x1801b11bf  nop     dword ptr [rax+rax+00h]
0x1801b11c4  mov     rax, [rsi]
0x1801b11c7  mov     rcx, rsi
0x1801b11ca  mov     rax, [rax+10h]
0x1801b11ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b11d3  mov     rcx, rbx; this
0x1801b11d6  call    ?_ShouldSuppressGrouping@CViewSettings@@AEAAHXZ; CViewSettings::_ShouldSuppressGrouping(void)
0x1801b11db  test    eax, eax
0x1801b11dd  jnz     loc_1801B12A3
0x1801b11e3  xor     edx, edx; cbInit
0x1801b11e5  xor     ecx, ecx; pInit
0x1801b11e7  call    cs:__imp_SHCreateMemStream
0x1801b11ee  nop     dword ptr [rax+rax+00h]
0x1801b11f3  mov     rsi, rax
0x1801b11f6  test    rax, rax
0x1801b11f9  jz      short loc_1801B1233
0x1801b11fb  mov     rdx, rax; struct IStream *
0x1801b11fe  mov     rcx, rbx; this
0x1801b1201  call    ?_SaveGroupState@CViewSettings@@AEAAJPEAUIStream@@@Z; CViewSettings::_SaveGroupState(IStream *)
0x1801b1206  test    eax, eax
0x1801b1208  jz      loc_1801B1305
0x1801b120e  lea     rdx, aGroupcollapses; "GroupCollapseState"
0x1801b1215  mov     rcx, rdi; propBag
0x1801b1218  call    cs:__imp_PSPropertyBag_Delete
0x1801b121f  nop     dword ptr [rax+rax+00h]
0x1801b1224  mov     rax, [rsi]
0x1801b1227  mov     rcx, rsi
0x1801b122a  mov     rax, [rax+10h]
0x1801b122e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1233  mov     eax, cs:PKEY_Null.pid
0x1801b1239  lea     rsi, [rbx+94h]
0x1801b1240  cmp     [rsi+10h], eax
0x1801b1243  jz      loc_1801B136C
0x1801b1249  mov     r8d, ebp; value
0x1801b124c  lea     rdx, aGroupview; "GroupView"
0x1801b1253  mov     rcx, rdi; propBag
0x1801b1256  call    cs:__imp_PSPropertyBag_WriteBOOL
0x1801b125d  nop     dword ptr [rax+rax+00h]
0x1801b1262  mov     r8, rsi; value
0x1801b1265  lea     rdx, aGroupbykey; "GroupByKey"
0x1801b126c  mov     rcx, rdi; propBag
0x1801b126f  call    cs:__imp_PSPropertyBag_WritePropertyKey
0x1801b1276  nop     dword ptr [rax+rax+00h]
0x1801b127b  mov     eax, [rbx+0A8h]
0x1801b1281  lea     rdx, aGroupbydirecti; "GroupByDirection"
0x1801b1288  neg     eax
0x1801b128a  mov     rcx, rdi; propBag
0x1801b128d  sbb     r8d, r8d
0x1801b1290  and     r8d, 2
0x1801b1294  dec     r8d; value
0x1801b1297  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1801b129e  nop     dword ptr [rax+rax+00h]
0x1801b12a3  mov     rdx, rdi; struct IPropertyBag *
0x1801b12a6  mov     rcx, rbx; this
0x1801b12a9  call    ?_FireSaveEvent@CViewSettings@@AEAAXPEAUIPropertyBag@@@Z; CViewSettings::_FireSaveEvent(IPropertyBag *)
0x1801b12ae  xor     eax, eax
0x1801b12b0  add     rsp, 28h
0x1801b12b4  pop     rdi
0x1801b12b5  pop     rsi
0x1801b12b6  pop     rbp
0x1801b12b7  pop     rbx
0x1801b12b8  retn
0x1801b12ba  mov     rdx, rsi; struct IStream *
0x1801b12bd  mov     rcx, rbx; this
0x1801b12c0  call    ?_SaveSortColumns@CViewSettings@@AEAAJPEAUIStream@@@Z; CViewSettings::_SaveSortColumns(IStream *)
0x1801b12c5  test    eax, eax
0x1801b12c7  jnz     short loc_1801B1332
0x1801b12c9  mov     rcx, rsi; pstm
0x1801b12cc  call    cs:__imp_IStream_Reset
0x1801b12d3  nop     dword ptr [rax+rax+00h]
0x1801b12d8  mov     r8, rsi; value
0x1801b12db  lea     rdx, aSort; "Sort"
0x1801b12e2  mov     rcx, rdi; propBag
0x1801b12e5  call    cs:__imp_PSPropertyBag_WriteStream
0x1801b12ec  nop     dword ptr [rax+rax+00h]
0x1801b12f1  mov     rax, [rsi]
0x1801b12f4  mov     rcx, rsi
0x1801b12f7  mov     rax, [rax+10h]
0x1801b12fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1300  jmp     loc_1801B1168
0x1801b1305  mov     rcx, rsi; pstm
0x1801b1308  call    cs:__imp_IStream_Reset
0x1801b130f  nop     dword ptr [rax+rax+00h]
0x1801b1314  mov     r8, rsi; value
0x1801b1317  lea     rdx, aGroupcollapses; "GroupCollapseState"
0x1801b131e  mov     rcx, rdi; propBag
0x1801b1321  call    cs:__imp_PSPropertyBag_WriteStream
0x1801b1328  nop     dword ptr [rax+rax+00h]
0x1801b132d  jmp     loc_1801B1224
0x1801b1332  lea     rdx, aSort; "Sort"
0x1801b1339  mov     rcx, rdi; propBag
0x1801b133c  call    cs:__imp_PSPropertyBag_Delete
0x1801b1343  nop     dword ptr [rax+rax+00h]
0x1801b1348  jmp     short loc_1801B12F1
0x1801b134a  xor     r8d, r8d
0x1801b134d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware> `wil::Feature<__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware>::GetImpl(void)'::`2'::impl
0x1801b1354  lea     ebp, [r8+1]
0x1801b1358  mov     dl, bpl
0x1801b135b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopWorkAreaDPIAware>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801b1360  mov     r8d, [rbx+0B0h]
0x1801b1367  jmp     loc_1801B1136
0x1801b136c  mov     rax, [rsi]
0x1801b136f  sub     rax, qword ptr cs:PKEY_Null.fmtid.Data1
0x1801b1376  jnz     short loc_1801B1383
0x1801b1378  mov     rax, [rsi+8]
0x1801b137c  sub     rax, qword ptr cs:PKEY_Null.fmtid.Data4
0x1801b1383  test    rax, rax
0x1801b1386  jnz     loc_1801B1249
0x1801b138c  xor     ebp, ebp
0x1801b138e  jmp     loc_1801B1249
0x1801b1393  lea     rdx, aColinfo; "ColInfo"
0x1801b139a  mov     rcx, rdi; propBag
0x1801b139d  call    cs:__imp_PSPropertyBag_Delete
0x1801b13a4  nop     dword ptr [rax+rax+00h]
0x1801b13a9  jmp     loc_1801B11C4
```

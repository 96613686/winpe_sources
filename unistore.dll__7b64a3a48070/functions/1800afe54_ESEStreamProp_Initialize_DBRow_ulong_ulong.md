# ESEStreamProp::Initialize(DBRow *,ulong,ulong)

- ea: `0x1800afe54`
- end: `0x1800b026e`
- name: `?Initialize@ESEStreamProp@@AEAAJPEAVDBRow@@KK@Z`
- size: `1050`
- prototype: `int(ESEStreamProp *__hidden this, struct DBRow *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800afd60`

## callees

- `0x1800029e0`
- `0x180003b3c`
- `0x1800068f0`
- `0x180008638`
- `0x18000866c`
- `0x1800086bc`
- `0x180009a50`
- `0x180009a90`
- `0x18000f530`
- `0x18001cba0`
- `0x1800325d0`
- `0x180035d40`
- `0x18003bf70`
- `0x180078a40`
- `0x180078a8c`
- `0x1800afe54`
- `0x1800b0274`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b0105`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b0105`

## string_xrefs

- `0x1800afeb6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x1800afeed`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x1800aff43`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x1800aff96`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x1800b011c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x1800b0160`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x1800b01d9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`

## pseudocode

```c
__int64 __fastcall ESEStreamProp::Initialize(ESEStreamProp *this, struct IUnknown *a2, unsigned int a3, int a4)
{
  _QWORD *v4; // rsi
  unsigned int v9; // edi
  struct IDBVolume *v10; // rdx
  int v11; // eax
  unsigned int v12; // eax
  int v13; // eax
  int HresultFromJetError; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  ColumnIdMappings *v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  int v21; // ebx
  unsigned __int64 v22; // rcx
  void *v23; // rax
  void *v24; // rbx
  int Column; // eax
  int v26; // edi
  _QWORD *v27; // r15
  HRESULT Instance; // eax
  HRESULT v29; // r14d
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // r9
  struct JET_RETINFO *v34; // [rsp+38h] [rbp-51h]
  struct JET_RETINFO *v35; // [rsp+38h] [rbp-51h]
  unsigned int v36[2]; // [rsp+40h] [rbp-49h] BYREF
  int v37; // [rsp+48h] [rbp-41h]
  struct TableHandleInfo *v38; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v39[8]; // [rsp+58h] [rbp-31h] BYREF
  _QWORD v40[2]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v41[112]; // [rsp+70h] [rbp-19h] BYREF
  unsigned int v42; // [rsp+100h] [rbp+77h] BYREF
  int v43; // [rsp+108h] [rbp+7Fh] BYREF

  v4 = (_QWORD *)((char *)this + 48);
  if ( *((struct IUnknown **)this + 6) != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 6, a2);
  *((_DWORD *)this + 14) = a3;
  *((_DWORD *)this + 8) = a4;
  v9 = ((__int64 (__fastcall *)(struct IUnknown *, char *))a2->lpVtbl[1].QueryInterface)(a2, (char *)this + 64);
  if ( (v9 & 0x80000000) == 0 )
  {
    v10 = (struct IDBVolume *)*((_QWORD *)this + 8);
    v40[0] = 0;
    v40[1] = 0;
    v11 = auto_DBSession::Open((auto_DBSession *)v40, v10);
    v9 = v11;
    if ( v11 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v11,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
        322);
LABEL_51:
      auto_DBSession::~auto_DBSession((auto_DBSession *)v40);
      return v9;
    }
    v38 = 0;
    ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v39, v40[0]);
    v12 = ((__int64 (__fastcall *)(struct IUnknown *))a2->lpVtbl[1].AddRef)(a2);
    v13 = auto_TableHandle::Open(&v38, v12, 0);
    v9 = v13;
    if ( v13 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v13,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
        325);
LABEL_9:
      auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v38);
      goto LABEL_51;
    }
    UnifiedStoreCursorLocation::UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)v41);
    HresultFromJetError = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v4 + 128LL))(*v4, v41);
    v9 = HresultFromJetError;
    if ( HresultFromJetError < 0 )
    {
      v15 = 328;
LABEL_12:
      v16 = 1;
LABEL_13:
      v17 = (unsigned int)HresultFromJetError;
LABEL_14:
      Log_UnistoreHREvent_0(
        v17,
        v16,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
        v15);
LABEL_15:
      UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)v41);
      goto LABEL_9;
    }
    HresultFromJetError = UnistoreJetGotoBookmark(v38, (const struct UnifiedStoreCursorLocation *)v41);
    v9 = HresultFromJetError;
    if ( HresultFromJetError < 0 )
    {
      v15 = 329;
      goto LABEL_12;
    }
    v42 = 0;
    *(_QWORD *)v36 = 0;
    v37 = 0;
    HresultFromJetError = ColumnIdMappings::PropIdToColumnId(v18, v38, a3, (struct ColumnDetails *)v36);
    v9 = HresultFromJetError;
    if ( HresultFromJetError == -2147023728 )
      goto LABEL_39;
    if ( HresultFromJetError < 0 )
    {
      v15 = 344;
      v16 = 1;
      goto LABEL_13;
    }
    v19 = CommsESE_JetRetrieveColumn(*((_QWORD *)v38 + 1), *((_QWORD *)v38 + 2), v36[0], 0, 0, &v42, 0, v34);
    v21 = v19;
    if ( v19 == -1507 || v19 == -1517 || v19 == 1531 || (v22 = v42) == 0 )
    {
LABEL_39:
      v26 = 1;
      v24 = 0;
      if ( a4 == 0x80000000 )
      {
        UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)v41);
        auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v38);
        v9 = -2147023728;
        goto LABEL_51;
      }
    }
    else
    {
      if ( v42 >= 0x100000 )
      {
        Log_AssertionEvent_17(v42, v20, 365);
        v22 = v42;
      }
      if ( v21 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v21);
        v9 = HresultFromJetError;
        v15 = 366;
        v16 = 0;
        goto LABEL_13;
      }
      v23 = operator new[](v22);
      v24 = v23;
      if ( !v23 )
      {
        v9 = -2147024882;
        v15 = 369;
        v17 = 2147942414LL;
        v16 = 0;
        goto LABEL_14;
      }
      Column = CommsESE_JetRetrieveColumn(*((_QWORD *)v38 + 1), *((_QWORD *)v38 + 2), v36[0], v23, v42, 0, 0, v35);
      if ( Column < 0 )
      {
        v9 = MakeHresultFromJetError(Column);
        Log_UnistoreHREvent_0(
          v9,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
          379);
LABEL_38:
        operator delete(v24);
        goto LABEL_15;
      }
      v26 = 0;
    }
    v27 = (_QWORD *)((char *)this + 24);
    Instance = CoCreateInstance(
                 &CLSID_VirtualStream,
                 0,
                 1u,
                 &GUID_0000000c_0000_0000_c000_000000000046,
                 (LPVOID *)this + 3);
    v29 = Instance;
    if ( Instance < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)Instance,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
        393);
      if ( v24 )
        operator delete(v24);
      UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)v41);
      auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v38);
      v9 = v29;
      goto LABEL_51;
    }
    if ( !v26 )
    {
      v30 = *v27;
      v43 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, int *))(*(_QWORD *)v30 + 32LL))(v30, v24, v42, &v43);
      v9 = v31;
      if ( v31 < 0 )
      {
        v32 = 398;
        goto LABEL_44;
      }
      v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v27 + 40LL))(*v27, 0, 0, 0);
      v9 = v31;
      if ( v31 < 0 )
      {
        v32 = 401;
LABEL_44:
        Log_UnistoreHREvent_0(
          (unsigned int)v31,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
          v32);
        if ( !v24 )
          goto LABEL_15;
        goto LABEL_38;
      }
    }
    if ( v24 )
      operator delete(v24);
    UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)v41);
    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v38);
    v9 = 0;
    goto LABEL_51;
  }
  Log_UnistoreHREvent_0(
    v9,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
    319);
  return v9;
}

```

## disassembly

```asm
0x1800afe54  mov     [rsp-8+arg_8], rbx
0x1800afe59  push    rbp
0x1800afe5a  push    rsi
0x1800afe5b  push    rdi
0x1800afe5c  push    r12
0x1800afe5e  push    r13
0x1800afe60  push    r14
0x1800afe62  push    r15
0x1800afe64  lea     rbp, [rsp-27h]
0x1800afe69  sub     rsp, 0B0h
0x1800afe70  lea     rsi, [rcx+30h]
0x1800afe74  mov     r13d, r9d
0x1800afe77  mov     r12d, r8d
0x1800afe7a  mov     rbx, rdx
0x1800afe7d  mov     r14, rcx
0x1800afe80  cmp     [rsi], rdx
0x1800afe83  jz      short loc_1800AFE8D
0x1800afe85  mov     rcx, rsi; struct IUnknown **
0x1800afe88  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800afe8d  mov     [r14+38h], r12d
0x1800afe91  lea     rdx, [r14+40h]
0x1800afe95  mov     [r14+20h], r13d
0x1800afe99  mov     rcx, rbx
0x1800afe9c  mov     rax, [rbx]
0x1800afe9f  mov     rax, [rax+18h]
0x1800afea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afea8  mov     edi, eax
0x1800afeaa  xor     eax, eax
0x1800afeac  test    edi, edi
0x1800afeae  jns     short loc_1800AFECC
0x1800afeb0  mov     r9d, 13Fh
0x1800afeb6  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800afebd  lea     edx, [rax+1]
0x1800afec0  mov     ecx, edi
0x1800afec2  call    Log_UnistoreHREvent_0
0x1800afec7  jmp     loc_1800B0251
0x1800afecc  mov     rdx, [r14+40h]; struct IDBVolume *
0x1800afed0  lea     rcx, [rbp+57h+var_80]; this
0x1800afed4  mov     [rbp+57h+var_80], rax
0x1800afed8  mov     [rbp+57h+var_78], rax
0x1800afedc  call    ?Open@auto_DBSession@@QEAAJPEAVIDBVolume@@@Z; auto_DBSession::Open(IDBVolume *)
0x1800afee1  mov     edi, eax
0x1800afee3  test    eax, eax
0x1800afee5  jns     short loc_1800AFF05
0x1800afee7  mov     r9d, 142h
0x1800afeed  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800afef4  mov     edx, 1
0x1800afef9  mov     ecx, eax
0x1800afefb  call    Log_UnistoreHREvent_0
0x1800aff00  jmp     loc_1800B0248
0x1800aff05  mov     rdx, [rbp+57h+var_80]
0x1800aff09  lea     rcx, [rbp+57h+var_88]
0x1800aff0d  mov     [rbp+57h+var_90], 0
0x1800aff15  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x1800aff1a  mov     rax, [rbx]
0x1800aff1d  mov     rcx, rbx
0x1800aff20  mov     rax, [rax+20h]
0x1800aff24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff29  xor     r8d, r8d
0x1800aff2c  lea     rcx, [rbp+57h+var_90]
0x1800aff30  mov     edx, eax
0x1800aff32  call    ?Open@auto_TableHandle@@QEAAJW4US_TABLEID@@K@Z; auto_TableHandle::Open(US_TABLEID,ulong)
0x1800aff37  mov     edi, eax
0x1800aff39  test    eax, eax
0x1800aff3b  jns     short loc_1800AFF64
0x1800aff3d  mov     r9d, 145h
0x1800aff43  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800aff4a  mov     edx, 1
0x1800aff4f  mov     ecx, eax
0x1800aff51  call    Log_UnistoreHREvent_0
0x1800aff56  lea     rcx, [rbp+57h+var_90]; this
0x1800aff5a  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x1800aff5f  jmp     loc_1800B0248
0x1800aff64  lea     rcx, [rbp+57h+var_70]; this
0x1800aff68  call    ??0UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::UnifiedStoreCursorLocation(void)
0x1800aff6d  mov     rcx, [rsi]
0x1800aff70  lea     rdx, [rbp+57h+var_70]
0x1800aff74  mov     rax, [rcx]
0x1800aff77  mov     rax, [rax+80h]
0x1800aff7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff83  mov     edi, eax
0x1800aff85  test    eax, eax
0x1800aff87  jns     short loc_1800AFFAD
0x1800aff89  mov     r9d, 148h
0x1800aff8f  mov     edx, 1
0x1800aff94  mov     ecx, eax
0x1800aff96  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800aff9d  call    Log_UnistoreHREvent_0
0x1800affa2  lea     rcx, [rbp+57h+var_70]; this
0x1800affa6  call    ??1UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation(void)
0x1800affab  jmp     short loc_1800AFF56
0x1800affad  mov     rcx, [rbp+57h+var_90]; struct TableHandleInfo *
0x1800affb1  lea     rdx, [rbp+57h+var_70]; struct UnifiedStoreCursorLocation *
0x1800affb5  call    ?UnistoreJetGotoBookmark@@YAJPEAUTableHandleInfo@@AEBVUnifiedStoreCursorLocation@@@Z; UnistoreJetGotoBookmark(TableHandleInfo *,UnifiedStoreCursorLocation const &)
0x1800affba  mov     edi, eax
0x1800affbc  test    eax, eax
0x1800affbe  jns     short loc_1800AFFC8
0x1800affc0  mov     r9d, 149h
0x1800affc6  jmp     short loc_1800AFF8F
0x1800affc8  mov     rdx, [rbp+57h+var_90]; struct TableHandleInfo *
0x1800affcc  lea     r9, [rbp+57h+var_A0]; struct ColumnDetails *
0x1800affd0  xor     eax, eax
0x1800affd2  mov     [rbp+57h+arg_10], 0
0x1800affd9  mov     r8d, r12d; unsigned int
0x1800affdc  mov     qword ptr [rbp+57h+var_A0], rax
0x1800affe0  mov     [rbp+57h+var_98], eax
0x1800affe3  call    ?PropIdToColumnId@ColumnIdMappings@@QEAAJQEAUTableHandleInfo@@KPEAUColumnDetails@@@Z; ColumnIdMappings::PropIdToColumnId(TableHandleInfo * const,ulong,ColumnDetails *)
0x1800affe8  mov     r15d, 80070490h
0x1800affee  xor     r12d, r12d
0x1800afff1  mov     edi, eax
0x1800afff3  mov     esi, 1
0x1800afff8  cmp     eax, r15d
0x1800afffb  jz      loc_1800B017F
0x1800b0001  test    eax, eax
0x1800b0003  jns     short loc_1800B000F
0x1800b0005  mov     r9d, 158h
0x1800b000b  mov     edx, esi
0x1800b000d  jmp     short loc_1800AFF94
0x1800b000f  mov     rcx, [rbp+57h+var_90]
0x1800b0013  lea     rax, [rbp+57h+arg_10]
0x1800b0017  mov     r8d, [rbp+57h+var_A0]; unsigned int
0x1800b001b  xor     r9d, r9d; void *
0x1800b001e  mov     [rsp+0E0h+var_B0], r12d; JET_GRBIT
0x1800b0023  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x1800b0028  mov     rdx, [rcx+10h]; unsigned __int64
0x1800b002c  mov     rcx, [rcx+8]; unsigned __int64
0x1800b0030  mov     dword ptr [rsp+0E0h+ppv], r12d; unsigned int
0x1800b0035  call    ?CommsESE_JetRetrieveColumn@@YAJ_K0KPEAXKPEAKKPEAUJET_RETINFO@@@Z; CommsESE_JetRetrieveColumn(unsigned __int64,unsigned __int64,ulong,void *,ulong,ulong *,ulong,JET_RETINFO *)
0x1800b003a  mov     ebx, eax
0x1800b003c  cmp     eax, 0FFFFFA1Dh
0x1800b0041  jz      loc_1800B017F
0x1800b0047  cmp     eax, 0FFFFFA13h
0x1800b004c  jz      loc_1800B017F
0x1800b0052  cmp     eax, 5FBh
0x1800b0057  jz      loc_1800B017F
0x1800b005d  mov     ecx, [rbp+57h+arg_10]
0x1800b0060  test    ecx, ecx
0x1800b0062  jz      loc_1800B017F
0x1800b0068  cmp     ecx, 100000h
0x1800b006e  jb      short loc_1800B007E
0x1800b0070  mov     r8d, 16Dh
0x1800b0076  call    Log_AssertionEvent_17
0x1800b007b  mov     ecx, [rbp+57h+arg_10]; unsigned __int64
0x1800b007e  test    ebx, ebx
0x1800b0080  jns     short loc_1800B0098
0x1800b0082  mov     ecx, ebx; int
0x1800b0084  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800b0089  mov     edi, eax
0x1800b008b  mov     r9d, 16Eh
0x1800b0091  xor     edx, edx
0x1800b0093  jmp     loc_1800AFF94
0x1800b0098  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b009d  mov     rbx, rax
0x1800b00a0  test    rax, rax
0x1800b00a3  jnz     short loc_1800B00B9
0x1800b00a5  mov     edi, 8007000Eh
0x1800b00aa  mov     r9d, 171h
0x1800b00b0  mov     ecx, edi
0x1800b00b2  xor     edx, edx
0x1800b00b4  jmp     loc_1800AFF96
0x1800b00b9  mov     rcx, [rbp+57h+var_90]
0x1800b00bd  mov     r9, rbx; void *
0x1800b00c0  mov     eax, [rbp+57h+arg_10]
0x1800b00c3  mov     r8d, [rbp+57h+var_A0]; unsigned int
0x1800b00c7  mov     [rsp+0E0h+var_B0], r12d; JET_GRBIT
0x1800b00cc  mov     rdx, [rcx+10h]; unsigned __int64
0x1800b00d0  mov     rcx, [rcx+8]; unsigned __int64
0x1800b00d4  mov     [rsp+0E0h+var_B8], r12; unsigned int *
0x1800b00d9  mov     dword ptr [rsp+0E0h+ppv], eax; unsigned int
0x1800b00dd  call    ?CommsESE_JetRetrieveColumn@@YAJ_K0KPEAXKPEAKKPEAUJET_RETINFO@@@Z; CommsESE_JetRetrieveColumn(unsigned __int64,unsigned __int64,ulong,void *,ulong,ulong *,ulong,JET_RETINFO *)
0x1800b00e2  test    eax, eax
0x1800b00e4  js      short loc_1800B0153
0x1800b00e6  mov     edi, r12d
0x1800b00e9  lea     r15, [r14+18h]
0x1800b00ed  mov     r8d, esi; dwClsContext
0x1800b00f0  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x1800b00f7  mov     [rsp+0E0h+ppv], r15; ppv
0x1800b00fc  xor     edx, edx; pUnkOuter
0x1800b00fe  lea     rcx, CLSID_VirtualStream; rclsid
0x1800b0105  call    cs:__imp_CoCreateInstance
0x1800b010b  mov     r14d, eax
0x1800b010e  test    eax, eax
0x1800b0110  jns     loc_1800B01AB
0x1800b0116  mov     r9d, 189h
0x1800b011c  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b0123  mov     edx, esi
0x1800b0125  mov     ecx, eax
0x1800b0127  call    Log_UnistoreHREvent_0
0x1800b012c  test    rbx, rbx
0x1800b012f  jz      short loc_1800B0139
0x1800b0131  mov     rcx, rbx; Block
0x1800b0134  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b0139  lea     rcx, [rbp+57h+var_70]; this
0x1800b013d  call    ??1UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation(void)
0x1800b0142  lea     rcx, [rbp+57h+var_90]; this
0x1800b0146  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x1800b014b  mov     edi, r14d
0x1800b014e  jmp     loc_1800B0248
0x1800b0153  mov     ecx, eax; int
0x1800b0155  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800b015a  mov     r9d, 17Bh
0x1800b0160  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b0167  xor     edx, edx
0x1800b0169  mov     ecx, eax
0x1800b016b  mov     edi, eax
0x1800b016d  call    Log_UnistoreHREvent_0
0x1800b0172  mov     rcx, rbx; Block
0x1800b0175  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b017a  jmp     loc_1800AFFA2
0x1800b017f  mov     edi, esi
0x1800b0181  mov     rbx, r12
0x1800b0184  cmp     r13d, 80000000h
0x1800b018b  jnz     loc_1800B00E9
0x1800b0191  lea     rcx, [rbp+57h+var_70]; this
0x1800b0195  call    ??1UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation(void)
0x1800b019a  lea     rcx, [rbp+57h+var_90]; this
0x1800b019e  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x1800b01a3  mov     edi, r15d
0x1800b01a6  jmp     loc_1800B0248
0x1800b01ab  test    edi, edi
0x1800b01ad  jnz     short loc_1800B0226
0x1800b01af  mov     rcx, [r15]
0x1800b01b2  lea     r9, [rbp+57h+arg_18]
0x1800b01b6  mov     r8d, [rbp+57h+arg_10]
0x1800b01ba  mov     rdx, rbx
0x1800b01bd  mov     [rbp+57h+arg_18], r12d
0x1800b01c1  mov     rax, [rcx]
0x1800b01c4  mov     rax, [rax+20h]
0x1800b01c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b01cd  mov     edi, eax
0x1800b01cf  test    eax, eax
0x1800b01d1  jns     short loc_1800B01F7
0x1800b01d3  mov     r9d, 18Eh
0x1800b01d9  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b01e0  mov     edx, esi
0x1800b01e2  mov     ecx, eax
0x1800b01e4  call    Log_UnistoreHREvent_0
0x1800b01e9  test    rbx, rbx
0x1800b01ec  jz      loc_1800AFFA2
0x1800b01f2  jmp     loc_1800B0172
0x1800b01f7  mov     rcx, [r15]
0x1800b01fa  xor     r9d, r9d
0x1800b01fd  mov     [rbp+57h+arg_0], 0
0x1800b0205  xor     r8d, r8d
0x1800b0208  mov     rdx, [rbp+57h+arg_0]
0x1800b020c  mov     rax, [rcx]
0x1800b020f  mov     rax, [rax+28h]
0x1800b0213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0218  mov     edi, eax
0x1800b021a  test    eax, eax
0x1800b021c  jns     short loc_1800B0226
0x1800b021e  mov     r9d, 191h
0x1800b0224  jmp     short loc_1800B01D9
0x1800b0226  test    rbx, rbx
0x1800b0229  jz      short loc_1800B0233
0x1800b022b  mov     rcx, rbx; Block
0x1800b022e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b0233  lea     rcx, [rbp+57h+var_70]; this
0x1800b0237  call    ??1UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation(void)
0x1800b023c  lea     rcx, [rbp+57h+var_90]; this
0x1800b0240  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x1800b0245  mov     edi, r12d
0x1800b0248  lea     rcx, [rbp+57h+var_80]; this
0x1800b024c  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x1800b0251  mov     rbx, [rsp+0E0h+arg_8]
0x1800b0259  mov     eax, edi
0x1800b025b  add     rsp, 0B0h
0x1800b0262  pop     r15
0x1800b0264  pop     r14
0x1800b0266  pop     r13
0x1800b0268  pop     r12
0x1800b026a  pop     rdi
0x1800b026b  pop     rsi
0x1800b026c  pop     rbp
0x1800b026d  retn
```

# CDataLinkDialog_Connect::OnGetCatalogs(ushort,ushort,HWND__ *,int &)

- ea: `0x3839da820`
- end: `0x3839dadb6`
- name: `?OnGetCatalogs@CDataLinkDialog_Connect@@AEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `1430`
- prototype: `__int64 __fastcall(CDataLinkDialog_Connect *__hidden this, struct IRowset *, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x3839ddf90`

## callees

- `0x3838434c0`
- `0x3838435e0`
- `0x383844d50`
- `0x38391aed0`
- `0x38391afe0`
- `0x3839d91a0`
- `0x3839da820`
- `0x3839dadc0`
- `0x3839db090`
- `0x3839dc240`
- `0x383ade150`

## import_xrefs

- `USER32!LoadCursorW` at `0x3839da8cd`
- `USER32!LoadCursorW` at `0x3839da8cd`
- `USER32!SetCursor` at `0x3839da8d6`
- `USER32!SetCursor` at `0x3839dad6a`
- `USER32!SetCursor` at `0x3839da8d6`
- `USER32!SetCursor` at `0x3839dad6a`
- `USER32!SetWindowTextW` at `0x3839da9ca`
- `USER32!SetWindowTextW` at `0x3839dacf9`
- `USER32!SetWindowTextW` at `0x3839da9ca`
- `USER32!SetWindowTextW` at `0x3839dacf9`
- `USER32!GetWindowTextW` at `0x3839da937`
- `USER32!GetWindowTextW` at `0x3839da937`
- `USER32!GetWindowTextLengthW` at `0x3839da8e3`
- `USER32!GetWindowTextLengthW` at `0x3839da8e3`
- `ole32!CoUninitialize` at `0x3839dad56`
- `ole32!CoUninitialize` at `0x3839dad56`
- `ole32!CoTaskMemFree` at `0x3839dad08`
- `ole32!CoTaskMemFree` at `0x3839dad17`
- `ole32!CoTaskMemFree` at `0x3839dad08`
- `ole32!CoTaskMemFree` at `0x3839dad17`
- `ole32!CoInitializeEx` at `0x3839da89f`
- `ole32!CoInitializeEx` at `0x3839da89f`
- `OLEAUT32!__imp_SysAllocString` at `0x3839dac44`
- `OLEAUT32!__imp_SysAllocString` at `0x3839dac44`
- `OLEAUT32!__imp_VariantClear` at `0x3839da9d7`
- `OLEAUT32!__imp_VariantClear` at `0x3839da9d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDataLinkDialog_Connect::OnGetCatalogs(
        CDataLinkDialog_Connect *this,
        struct IRowset *a2,
        __int64 a3,
        HWND a4,
        int *a5)
{
  struct IRowset *v5; // rsi
  CDataLinkDialog_Connect *v6; // rbx
  __int64 v7; // rdi
  unsigned int v8; // r15d
  HCURSOR CursorW; // rax
  int WindowTextLengthW; // r14d
  size_t v11; // r8
  __int64 v12; // rax
  void *v13; // rsp
  WCHAR *v14; // rdi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int i; // ecx
  bool v20; // zf
  unsigned __int64 v21; // r8
  bool v22; // cf
  unsigned __int64 v23; // r8
  int v24; // eax
  int v25; // eax
  HWND v26; // r8
  int CatalogData; // eax
  BSTR v28; // r11
  struct IDBInitialize **v30; // [rsp+28h] [rbp-28h]
  struct IDBInitialize **v31; // [rsp+28h] [rbp-28h]
  struct IUnknown **v32; // [rsp+30h] [rbp-20h]
  struct IUnknown **v33; // [rsp+30h] [rbp-20h]
  int v34; // [rsp+38h] [rbp-18h]
  int v35; // [rsp+38h] [rbp-18h]
  WCHAR String[2]; // [rsp+50h] [rbp+0h] BYREF
  unsigned int v37; // [rsp+54h] [rbp+4h]
  int v38; // [rsp+58h] [rbp+8h]
  struct IUnknown *v39; // [rsp+60h] [rbp+10h] BYREF
  int v40; // [rsp+68h] [rbp+18h] BYREF
  unsigned int v41; // [rsp+6Ch] [rbp+1Ch] BYREF
  __int64 v42; // [rsp+70h] [rbp+20h] BYREF
  struct IDBInitialize *v43; // [rsp+78h] [rbp+28h] BYREF
  CDataLinkDialog_Connect *v44; // [rsp+80h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+38h] BYREF
  WCHAR *v46; // [rsp+90h] [rbp+40h]
  LPVOID v47; // [rsp+98h] [rbp+48h] BYREF
  __int64 v48; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v49; // [rsp+A8h] [rbp+58h] BYREF
  __int64 v50; // [rsp+B0h] [rbp+60h] BYREF
  __int64 v51; // [rsp+B8h] [rbp+68h]
  __int64 v52; // [rsp+C0h] [rbp+70h] BYREF
  HCURSOR hCursor; // [rsp+C8h] [rbp+78h]
  char v54; // [rsp+D0h] [rbp+80h]
  _QWORD pExceptionObject[2]; // [rsp+D8h] [rbp+88h] BYREF

  pExceptionObject[1] = -2;
  v5 = a2;
  v6 = this;
  v7 = *((_QWORD *)this + 107);
  if ( v7 )
    (*(void (__fastcall **)(__int64, struct IRowset *, __int64, HWND))(*(_QWORD *)(v7 + 32) + 8LL))(v7 + 32, a2, a3, a4);
  v51 = v7;
  v40 = 0;
  *(_DWORD *)String = 0;
  v43 = 0;
  v39 = 0;
  v8 = CoInitializeEx(0, 0);
  v37 = v8;
  v41 = 0;
  pv = 0;
  v47 = 0;
  v44 = 0;
  v42 = 0;
  v54 = 1;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  hCursor = SetCursor(CursorW);
  WindowTextLengthW = GetWindowTextLengthW((HWND)v5);
  v11 = (unsigned int)(2 * WindowTextLengthW + 2);
  v12 = v11 + 15;
  if ( v11 + 15 <= v11 )
    v12 = 0xFFFFFFFFFFFFFF0LL;
  v13 = alloca(v12 & 0xFFFFFFFFFFFFFFF0uLL);
  v14 = String;
  v46 = String;
  memset(String, 0, v11);
  if ( WindowTextLengthW )
    GetWindowTextW((HWND)v5, String, WindowTextLengthW + 1);
  (*(void (__fastcall **)(CDataLinkDialog_Connect *))(*(_QWORD *)v6 + 40LL))(v6);
  LODWORD(v30) = 0;
  v15 = CDataLinkDialog_Connect::ConnectToDS(
          v6,
          &v40,
          (unsigned int *)String,
          (unsigned __int16 *)&v43,
          &v39,
          v30,
          v32,
          v34);
  if ( v15 >= 0 )
  {
    v38 = 1;
    goto LABEL_70;
  }
  if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    bidTraceW(off_383B432A8[0], 2298921, off_383B49128[0], (unsigned int)v15);
  CDataLinkDialog_Connect::DisconnectFromDS(v6, &v43, &v39);
  SetWindowTextW((HWND)v5, &WideCharStr);
  VariantClear((VARIANTARG *)((char *)v6 + 440));
  *((_QWORD *)v6 + 56) = 0;
  LODWORD(v31) = 1;
  v16 = CDataLinkDialog_Connect::ConnectToDS(
          v6,
          &v40,
          (unsigned int *)String,
          (unsigned __int16 *)&v43,
          &v39,
          v31,
          v33,
          v35);
  if ( v16 >= 0 )
  {
    v38 = 0;
LABEL_70:
    try
    {
      v17 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v39->lpVtbl->QueryInterface)(
              v39,
              &IID_IDBSchemaRowset,
              &v42);
      if ( v17 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B432A8[0], 2347017, (unsigned int)v17);
        pExceptionObject[0] = 0;
        throw (__int64 *)pExceptionObject;
      }
      v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *, LPVOID *))(*(_QWORD *)v42 + 32LL))(
              v42,
              &v41,
              &pv,
              &v47);
      if ( v18 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B432A8[0], 2356233, (unsigned int)v18);
        v50 = 0;
        throw (__int64 *)&v50;
      }
      for ( i = 0; ; ++i )
      {
        v20 = i == v41;
        if ( i >= v41 )
          break;
        v21 = *((_QWORD *)pv + 2 * i);
        v22 = v21 < *(_QWORD *)&DBSCHEMA_CATALOGS.Data1;
        if ( v21 == *(_QWORD *)&DBSCHEMA_CATALOGS.Data1
          && (v23 = *((_QWORD *)pv + 2 * i + 1),
              v22 = v23 < *(_QWORD *)DBSCHEMA_CATALOGS.Data4,
              v23 == *(_QWORD *)DBSCHEMA_CATALOGS.Data4) )
        {
          v24 = 0;
        }
        else
        {
          v24 = -v22 - (v22 - 1);
        }
        if ( !v24 )
        {
          v20 = i == v41;
          break;
        }
      }
      if ( v20 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          bidTraceW(off_383B432A8[0], 2365481, off_383B49128[0], 2147500037LL);
        v48 = 0;
        throw (__int64 *)&v48;
      }
      v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, _QWORD, _QWORD, GUID *, _DWORD, _QWORD, CDataLinkDialog_Connect **))(*(_QWORD *)v42 + 24LL))(
              v42,
              0,
              &DBSCHEMA_CATALOGS,
              0,
              0,
              &IID_IRowset,
              0,
              0,
              &v44);
      if ( v25 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B432A8[0], 2380809, (unsigned int)v25);
        v52 = 0;
        throw (__int64 *)&v52;
      }
      CatalogData = CDataLinkDialog_Connect::GetCatalogData(v44, v5, v26);
      if ( CatalogData < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B432A8[0], 2389001, (unsigned int)CatalogData);
        v49 = 0;
        throw (__int64 *)&v49;
      }
    }
    catch ( __int64 )
    {
      CDataLinkDialog::DataLinkMessageBoxInfo(this, 0x9C9Fu);
      v14 = v46;
      v8 = v37;
      v5 = a2;
      v6 = this;
    }
    catch ( ... )
    {
      CDataLinkDialog::DataLinkMessageBoxInfo(this, 0x9C8Cu);
      v14 = v46;
      v8 = v37;
      v5 = a2;
      v6 = this;
    }
    if ( v38 )
      goto LABEL_53;
    goto LABEL_55;
  }
  if ( (bidGblFlags & 2) != 0 )
    bidTraceHR(off_383B432A8[0], 2319369, (unsigned int)v16);
  CDataLinkDialog::DataLinkMessageBoxInfo(v6, *(unsigned int *)String);
  v28 = SysAllocString(String);
  if ( v28 )
  {
    *((_QWORD *)v6 + 49) = 233;
    *(DBID *)((char *)v6 + 408) = DB_NULLID;
    *((_WORD *)v6 + 220) = 8;
    *((_QWORD *)v6 + 56) = v28;
LABEL_53:
    if ( *v14 )
      SetWindowTextW((HWND)v5, v14);
    goto LABEL_55;
  }
  if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    bidTraceW(off_383B432A8[0], 2328617, off_383B49128[0], 2147942414LL);
LABEL_55:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v47 )
    CoTaskMemFree(v47);
  if ( v44 )
    (*(void (__fastcall **)(CDataLinkDialog_Connect *))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  CDataLinkDialog_Connect::DisconnectFromDS(v6, &v43, &v39);
  if ( v8 <= 1 )
    CoUninitialize();
  if ( v54 )
    SetCursor(hCursor);
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v51 + 32) + 24LL))(v51 + 32);
  return 1;
}

```

## disassembly

```asm
0x3839da820  mov     [rsp-8+arg_8], rdx
0x3839da825  mov     [rsp-8+arg_0], rcx
0x3839da82a  push    rbp
0x3839da82b  push    rdi
0x3839da82c  push    r12
0x3839da82e  push    r14
0x3839da830  push    r15
0x3839da832  sub     rsp, 0F0h
0x3839da839  lea     rbp, [rsp+50h]
0x3839da83e  mov     [rbp+0C0h+var_30], 0FFFFFFFFFFFFFFFEh
0x3839da849  mov     [rbp+0C0h+arg_10], rbx
0x3839da850  mov     [rbp+0C0h+arg_18], rsi
0x3839da857  mov     rax, cs:__security_cookie
0x3839da85e  xor     rax, rbp
0x3839da861  mov     [rbp+0C0h+var_28], rax
0x3839da868  mov     rsi, rdx
0x3839da86b  mov     rbx, rcx
0x3839da86e  mov     rdi, [rcx+358h]
0x3839da875  test    rdi, rdi
0x3839da878  jz      short loc_3839DA884
0x3839da87a  lea     rcx, [rdi+20h]
0x3839da87e  mov     rax, [rcx]
0x3839da881  call    qword ptr [rax+8]
0x3839da884  mov     [rbp+0C0h+var_58], rdi
0x3839da888  xor     r12d, r12d
0x3839da88b  mov     [rbp+0C0h+var_A8], r12d
0x3839da88f  mov     dword ptr [rbp+0C0h+String], r12d
0x3839da893  mov     [rbp+0C0h+var_98], r12
0x3839da897  mov     [rbp+0C0h+var_B0], r12
0x3839da89b  xor     edx, edx; dwCoInit
0x3839da89d  xor     ecx, ecx; pvReserved
0x3839da89f  call    cs:__imp_CoInitializeEx
0x3839da8a5  mov     r15d, eax
0x3839da8a8  mov     [rbp+0C0h+var_BC], eax
0x3839da8ab  mov     [rbp+0C0h+var_A4], r12d
0x3839da8af  mov     [rbp+0C0h+pv], r12
0x3839da8b3  mov     [rbp+0C0h+var_78], r12
0x3839da8b7  mov     [rbp+0C0h+var_90], r12
0x3839da8bb  mov     [rbp+0C0h+var_A0], r12
0x3839da8bf  mov     [rbp+0C0h+var_40], 1
0x3839da8c6  mov     edx, 7F02h; lpCursorName
0x3839da8cb  xor     ecx, ecx; hInstance
0x3839da8cd  call    cs:__imp_LoadCursorW
0x3839da8d3  mov     rcx, rax; hCursor
0x3839da8d6  call    cs:__imp_SetCursor
0x3839da8dc  mov     [rbp+0C0h+hCursor], rax
0x3839da8e0  mov     rcx, rsi; hWnd
0x3839da8e3  call    cs:__imp_GetWindowTextLengthW
0x3839da8e9  mov     r14d, eax
0x3839da8ec  lea     ecx, ds:2[rax*2]
0x3839da8f3  mov     r8d, ecx
0x3839da8f6  lea     rax, [rcx+0Fh]
0x3839da8fa  cmp     rax, r8
0x3839da8fd  ja      short loc_3839DA909
0x3839da8ff  mov     rax, 0FFFFFFFFFFFFFF0h
0x3839da909  and     rax, 0FFFFFFFFFFFFFFF0h
0x3839da90d  call    _alloca_probe
0x3839da912  sub     rsp, rax
0x3839da915  lea     rdi, [rsp+110h+String]
0x3839da91a  mov     [rbp+0C0h+var_80], rdi
0x3839da91e  xor     edx, edx; Val
0x3839da920  mov     rcx, rdi; void *
0x3839da923  call    memset
0x3839da928  test    r14d, r14d
0x3839da92b  jz      short loc_3839DA93D
0x3839da92d  lea     r8d, [r14+1]; nMaxCount
0x3839da931  mov     rdx, rdi; lpString
0x3839da934  mov     rcx, rsi; hWnd
0x3839da937  call    cs:__imp_GetWindowTextW
0x3839da93d  mov     rax, [rbx]
0x3839da940  mov     rcx, rbx
0x3839da943  call    qword ptr [rax+28h]
0x3839da946  mov     dword ptr [rsp+110h+var_E8], r12d; struct IDBInitialize **
0x3839da94b  lea     rax, [rbp+0C0h+var_B0]
0x3839da94f  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int
0x3839da954  lea     r9, [rbp+0C0h+var_98]; unsigned __int16 *
0x3839da958  lea     r8, [rbp+0C0h+String]; unsigned int *
0x3839da95c  lea     rdx, [rbp+0C0h+var_A8]; int *
0x3839da960  mov     rcx, rbx; this
0x3839da963  call    ?ConnectToDS@CDataLinkDialog_Connect@@AEAAJPEAHPEAKPEAGKPEAPEAUIDBInitialize@@PEAPEAUIUnknown@@H@Z; CDataLinkDialog_Connect::ConnectToDS(int *,ulong *,ushort *,ulong,IDBInitialize * *,IUnknown * *,int)
0x3839da968  mov     r9d, eax
0x3839da96b  test    eax, eax
0x3839da96d  js      short loc_3839DA97B
0x3839da96f  mov     [rbp+0C0h+var_B8], 1
0x3839da976  jmp     loc_3839DAA15
0x3839da97b  test    byte ptr cs:_bidGblFlags, 2
0x3839da982  jz      short loc_3839DA9B0
0x3839da984  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839da98b  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839da992  test    rax, rax
0x3839da995  jz      short loc_3839DA9B0
0x3839da997  mov     [rsp+110h+var_F0], 8C5h
0x3839da99f  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839da9a6  mov     edx, 231429h
0x3839da9ab  call    _bidTraceW
0x3839da9b0  lea     r8, [rbp+0C0h+var_B0]; struct IUnknown **
0x3839da9b4  lea     rdx, [rbp+0C0h+var_98]; struct IDBInitialize **
0x3839da9b8  mov     rcx, rbx; this
0x3839da9bb  call    ?DisconnectFromDS@CDataLinkDialog_Connect@@AEAAXPEAPEAUIDBInitialize@@PEAPEAUIUnknown@@@Z; CDataLinkDialog_Connect::DisconnectFromDS(IDBInitialize * *,IUnknown * *)
0x3839da9c0  lea     rdx, WideCharStr; lpString
0x3839da9c7  mov     rcx, rsi; hWnd
0x3839da9ca  call    cs:__imp_SetWindowTextW
0x3839da9d0  lea     rcx, [rbx+1B8h]; pvarg
0x3839da9d7  call    cs:__imp_VariantClear
0x3839da9dd  mov     [rbx+1C0h], r12
0x3839da9e4  mov     dword ptr [rsp+110h+var_E8], 1; struct IDBInitialize **
0x3839da9ec  lea     rax, [rbp+0C0h+var_B0]
0x3839da9f0  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int
0x3839da9f5  lea     r9, [rbp+0C0h+var_98]; unsigned __int16 *
0x3839da9f9  lea     r8, [rbp+0C0h+String]; unsigned int *
0x3839da9fd  lea     rdx, [rbp+0C0h+var_A8]; int *
0x3839daa01  mov     rcx, rbx; this
0x3839daa04  call    ?ConnectToDS@CDataLinkDialog_Connect@@AEAAJPEAHPEAKPEAGKPEAPEAUIDBInitialize@@PEAPEAUIUnknown@@H@Z; CDataLinkDialog_Connect::ConnectToDS(int *,ulong *,ushort *,ulong,IDBInitialize * *,IUnknown * *,int)
0x3839daa09  test    eax, eax
0x3839daa0b  js      loc_3839DAC19
0x3839daa11  mov     [rbp+0C0h+var_B8], r12d
0x3839daa15  mov     rcx, [rbp+0C0h+var_B0]
0x3839daa19  mov     rax, [rcx]
0x3839daa1c  lea     r8, [rbp+0C0h+var_A0]
0x3839daa20  lea     rdx, IID_IDBSchemaRowset
0x3839daa27  call    qword ptr [rax]
0x3839daa29  test    eax, eax
0x3839daa2b  jns     short loc_3839DAA64
0x3839daa2d  test    byte ptr cs:_bidGblFlags, 2
0x3839daa34  jz      short loc_3839DAA4A
0x3839daa36  mov     r8d, eax
0x3839daa39  mov     edx, 23D009h
0x3839daa3e  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839daa45  call    _bidTraceHR
0x3839daa4a  mov     [rbp+0C0h+pExceptionObject], r12
0x3839daa51  lea     rdx, _TI1_J; pThrowInfo
0x3839daa58  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x3839daa5f  call    _CxxThrowException
0x3839daa64  mov     rcx, [rbp+0C0h+var_A0]
0x3839daa68  mov     rax, [rcx]
0x3839daa6b  lea     r9, [rbp+0C0h+var_78]
0x3839daa6f  lea     r8, [rbp+0C0h+pv]
0x3839daa73  lea     rdx, [rbp+0C0h+var_A4]
0x3839daa77  call    qword ptr [rax+20h]
0x3839daa7a  test    eax, eax
0x3839daa7c  jns     short loc_3839DAAAF
0x3839daa7e  test    byte ptr cs:_bidGblFlags, 2
0x3839daa85  jz      short loc_3839DAA9B
0x3839daa87  mov     r8d, eax
0x3839daa8a  mov     edx, 23F409h
0x3839daa8f  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839daa96  call    _bidTraceHR
0x3839daa9b  mov     [rbp+0C0h+var_60], r12
0x3839daa9f  lea     rdx, _TI1_J; pThrowInfo
0x3839daaa6  lea     rcx, [rbp+0C0h+var_60]; pExceptionObject
0x3839daaaa  call    _CxxThrowException
0x3839daaaf  mov     ecx, r12d
0x3839daab2  lea     r11, DBSCHEMA_CATALOGS
0x3839daab9  mov     r9d, [rbp+0C0h+var_A4]
0x3839daabd  mov     r10, [rbp+0C0h+pv]
0x3839daac1  cmp     ecx, r9d
0x3839daac4  jnb     short loc_3839DAAF4
0x3839daac6  mov     eax, ecx
0x3839daac8  add     rax, rax
0x3839daacb  mov     r8, [r10+rax*8]
0x3839daacf  cmp     r8, [r11]
0x3839daad2  jnz     short loc_3839DAAE4
0x3839daad4  mov     r8, [r10+rax*8+8]
0x3839daad9  cmp     r8, [r11+8]
0x3839daadd  jnz     short loc_3839DAAE4
0x3839daadf  mov     eax, r12d
0x3839daae2  jmp     short loc_3839DAAE9
0x3839daae4  sbb     eax, eax
0x3839daae6  sbb     eax, 0FFFFFFFFh
0x3839daae9  test    eax, eax
0x3839daaeb  jz      short loc_3839DAAF1
0x3839daaed  inc     ecx
0x3839daaef  jmp     short loc_3839DAAC1
0x3839daaf1  cmp     ecx, r9d
0x3839daaf4  jnz     short loc_3839DAB45
0x3839daaf6  test    byte ptr cs:_bidGblFlags, 2
0x3839daafd  jz      short loc_3839DAB31
0x3839daaff  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839dab06  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839dab0d  test    rax, rax
0x3839dab10  jz      short loc_3839DAB31
0x3839dab12  mov     [rsp+110h+var_F0], 906h
0x3839dab1a  mov     r9d, 80004005h
0x3839dab20  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839dab27  mov     edx, 241829h
0x3839dab2c  call    _bidTraceW
0x3839dab31  mov     [rbp+0C0h+var_70], r12
0x3839dab35  lea     rdx, _TI1_J; pThrowInfo
0x3839dab3c  lea     rcx, [rbp+0C0h+var_70]; pExceptionObject
0x3839dab40  call    _CxxThrowException
0x3839dab45  mov     rcx, [rbp+0C0h+var_A0]
0x3839dab49  mov     rax, [rcx]
0x3839dab4c  lea     rdx, [rbp+0C0h+var_90]
0x3839dab50  mov     [rsp+110h+var_D0], rdx
0x3839dab55  mov     [rsp+110h+var_D8], r12
0x3839dab5a  mov     dword ptr [rsp+110h+var_E0], r12d
0x3839dab5f  lea     rdx, IID_IRowset
0x3839dab66  mov     [rsp+110h+var_E8], rdx
0x3839dab6b  mov     qword ptr [rsp+110h+var_F0], r12
0x3839dab70  xor     r9d, r9d
0x3839dab73  mov     r8, r11
0x3839dab76  xor     edx, edx
0x3839dab78  call    qword ptr [rax+18h]
0x3839dab7b  test    eax, eax
0x3839dab7d  jns     short loc_3839DABB0
0x3839dab7f  test    byte ptr cs:_bidGblFlags, 2
0x3839dab86  jz      short loc_3839DAB9C
0x3839dab88  mov     r8d, eax
0x3839dab8b  mov     edx, 245409h
0x3839dab90  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839dab97  call    _bidTraceHR
0x3839dab9c  mov     [rbp+0C0h+var_50], r12
0x3839daba0  lea     rdx, _TI1_J; pThrowInfo
0x3839daba7  lea     rcx, [rbp+0C0h+var_50]; pExceptionObject
0x3839dabab  call    _CxxThrowException
0x3839dabb0  mov     rdx, rsi; struct IRowset *
0x3839dabb3  mov     rcx, [rbp+0C0h+var_90]; this
0x3839dabb7  call    ?GetCatalogData@CDataLinkDialog_Connect@@AEAAJPEAUIRowset@@PEAUHWND__@@@Z; CDataLinkDialog_Connect::GetCatalogData(IRowset *,HWND__ *)
0x3839dabbc  test    eax, eax
0x3839dabbe  jns     short loc_3839DABF2
0x3839dabc0  test    byte ptr cs:_bidGblFlags, 2
0x3839dabc7  jz      short loc_3839DABDD
0x3839dabc9  mov     r8d, eax
0x3839dabcc  mov     edx, 247409h
0x3839dabd1  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839dabd8  call    _bidTraceHR
0x3839dabdd  mov     [rbp+0C0h+var_68], r12
0x3839dabe1  lea     rdx, _TI1_J; pThrowInfo
0x3839dabe8  lea     rcx, [rbp+0C0h+var_68]; pExceptionObject
0x3839dabec  call    _CxxThrowException
0x3839dabf2  jmp     short loc_3839DAC0A
0x3839dabf4  mov     rdi, [rbp+0C0h+var_80]
0x3839dabf8  mov     r15d, [rbp+0C0h+var_BC]
0x3839dabfc  mov     rsi, [rbp+0C0h+arg_8]
0x3839dac03  mov     rbx, [rbp+0C0h+arg_0]
0x3839dac0a  cmp     [rbp+0C0h+var_B8], 0
0x3839dac0e  jz      loc_3839DACFF
0x3839dac14  jmp     loc_3839DACED
0x3839dac19  test    byte ptr cs:_bidGblFlags, 2
0x3839dac20  jz      short loc_3839DAC36
0x3839dac22  mov     r8d, eax
0x3839dac25  mov     edx, 236409h
0x3839dac2a  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839dac31  call    _bidTraceHR
0x3839dac36  mov     edx, dword ptr [rbp+0C0h+String]; unsigned int
0x3839dac39  mov     rcx, rbx; this
0x3839dac3c  call    ?DataLinkMessageBoxInfo@CDataLinkDialog@@IEAAXK@Z; CDataLinkDialog::DataLinkMessageBoxInfo(ulong)
0x3839dac41  mov     rcx, rdi; psz
0x3839dac44  call    cs:__imp_SysAllocString
0x3839dac4a  mov     r11, rax
0x3839dac4d  test    rax, rax
0x3839dac50  jnz     short loc_3839DAC97
0x3839dac52  test    byte ptr cs:_bidGblFlags, 2
0x3839dac59  jz      loc_3839DACFF
0x3839dac5f  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839dac66  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839dac6d  test    rax, rax
0x3839dac70  jz      loc_3839DACFF
0x3839dac76  mov     [rsp+110h+var_F0], 8E2h
0x3839dac7e  mov     r9d, 8007000Eh
0x3839dac84  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839dac8b  mov     edx, 238829h
0x3839dac90  call    _bidTraceW
0x3839dac95  jmp     short loc_3839DACFF
0x3839dac97  mov     qword ptr [rbx+188h], 0E9h
0x3839daca2  mov     rax, qword ptr cs:DB_NULLID.uGuid
0x3839daca9  mov     [rbx+198h], rax
0x3839dacb0  mov     rax, qword ptr cs:DB_NULLID.uGuid+8
0x3839dacb7  mov     [rbx+1A0h], rax
0x3839dacbe  mov     rax, qword ptr cs:DB_NULLID.eKind
0x3839dacc5  mov     [rbx+1A8h], rax
0x3839daccc  mov     rax, qword ptr cs:DB_NULLID.uName
0x3839dacd3  mov     [rbx+1B0h], rax
0x3839dacda  mov     eax, 8
0x3839dacdf  mov     [rbx+1B8h], ax
0x3839dace6  mov     [rbx+1C0h], r11
0x3839daced  cmp     word ptr [rdi], 0
0x3839dacf1  jz      short loc_3839DACFF
0x3839dacf3  mov     rdx, rdi; lpString
0x3839dacf6  mov     rcx, rsi; hWnd
0x3839dacf9  call    cs:__imp_SetWindowTextW
0x3839dacff  mov     rcx, [rbp+0C0h+pv]; pv
0x3839dad03  test    rcx, rcx
0x3839dad06  jz      short loc_3839DAD0E
0x3839dad08  call    cs:__imp_CoTaskMemFree
0x3839dad0e  mov     rcx, [rbp+0C0h+var_78]; pv
0x3839dad12  test    rcx, rcx
0x3839dad15  jz      short loc_3839DAD1D
0x3839dad17  call    cs:__imp_CoTaskMemFree
0x3839dad1d  mov     rcx, [rbp+0C0h+var_90]
0x3839dad21  test    rcx, rcx
0x3839dad24  jz      short loc_3839DAD2C
0x3839dad26  mov     rax, [rcx]
0x3839dad29  call    qword ptr [rax+10h]
0x3839dad2c  mov     rcx, [rbp+0C0h+var_A0]
0x3839dad30  test    rcx, rcx
0x3839dad33  jz      short loc_3839DAD3B
0x3839dad35  mov     rax, [rcx]
0x3839dad38  call    qword ptr [rax+10h]
0x3839dad3b  lea     r8, [rbp+0C0h+var_B0]; struct IUnknown **
  ... truncated ...
```

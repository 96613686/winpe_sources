# CVsSoftwareProvider::SetSnapshotProperty(_GUID,_VSS_SNAPSHOT_PROPERTY_ID,tagVARIANT)

- ea: `0x180016550`
- end: `0x180016fe7`
- name: `?SetSnapshotProperty@CVsSoftwareProvider@@UEAAJU_GUID@@W4_VSS_SNAPSHOT_PROPERTY_ID@@UtagVARIANT@@@Z`
- size: `2711`
- prototype: `__int64 __fastcall(CVsSoftwareProvider *__hidden this, struct _GUID *Buf1, enum _VSS_SNAPSHOT_PROPERTY_ID, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001acc`
- `0x18000212c`
- `0x1800034cc`
- `0x1800036c4`
- `0x180003888`
- `0x1800039d8`
- `0x180003de8`
- `0x18000610c`
- `0x180009588`
- `0x18000ddb0`
- `0x180010974`
- `0x180016550`
- `0x180017284`
- `0x18001bf14`
- `0x18001c4b0`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x1800367b8`
- `0x180037080`
- `0x18003d78c`
- `0x1800419fc`
- `0x18004b010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180016f28`
- `OLEAUT32!__imp_VariantClear` at `0x180016f28`
- `OLEAUT32!__imp_VariantCopy` at `0x1800166b2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800166b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016dd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016dd7`

## string_xrefs

- `0x180016a8c`: `NULL exposed name/path`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CVsSoftwareProvider::SetSnapshotProperty(
        CVsSoftwareProvider *this,
        struct _GUID *Buf1,
        enum _VSS_SNAPSHOT_PROPERTY_ID a3,
        struct tagVARIANT *a4)
{
  HRESULT v8; // eax
  _QWORD *v9; // rax
  __int64 v10; // rbx
  int ContextInternal; // eax
  __int64 v12; // rdi
  int v13; // esi
  LONG lVal; // ebx
  LPVOID *v15; // rbx
  unsigned int v16; // ebx
  __int64 v18; // [rsp+20h] [rbp-2C8h]
  __int64 v19; // [rsp+28h] [rbp-2C0h]
  __int64 v20; // [rsp+38h] [rbp-2B0h]
  _QWORD *v21; // [rsp+80h] [rbp-268h] BYREF
  const unsigned __int16 *v22; // [rsp+88h] [rbp-260h] BYREF
  const unsigned __int16 *v23; // [rsp+90h] [rbp-258h]
  const unsigned __int16 *v24; // [rsp+98h] [rbp-250h]
  int v25; // [rsp+A0h] [rbp-248h]
  int v26; // [rsp+A4h] [rbp-244h]
  int v27; // [rsp+A8h] [rbp-240h]
  _BYTE v28[120]; // [rsp+B0h] [rbp-238h] BYREF
  int v29; // [rsp+128h] [rbp-1C0h]
  VARIANTARG pvargDest; // [rsp+130h] [rbp-1B8h] BYREF
  struct _GUID v31; // [rsp+150h] [rbp-198h] BYREF
  LPVOID v32; // [rsp+160h] [rbp-188h] BYREF
  unsigned int v33; // [rsp+168h] [rbp-180h]
  unsigned int v34; // [rsp+184h] [rbp-164h]
  unsigned int v35; // [rsp+1D0h] [rbp-118h] BYREF
  const unsigned __int16 *v36; // [rsp+1E0h] [rbp-108h] BYREF
  __int128 v37; // [rsp+1E8h] [rbp-100h]
  __int128 v38; // [rsp+1F8h] [rbp-F0h]
  _WORD v39[2]; // [rsp+208h] [rbp-E0h] BYREF
  __int64 v40; // [rsp+20Ch] [rbp-DCh]
  __int64 v41; // [rsp+218h] [rbp-D0h]
  __int64 v42; // [rsp+220h] [rbp-C8h]
  int v43; // [rsp+228h] [rbp-C0h]
  __int64 v44; // [rsp+230h] [rbp-B8h]
  __int16 v45; // [rsp+238h] [rbp-B0h]
  void **v46; // [rsp+240h] [rbp-A8h]
  __int64 v47; // [rsp+248h] [rbp-A0h]
  int v48; // [rsp+280h] [rbp-68h]
  _com_error *v49; // [rsp+290h] [rbp-58h] BYREF
  const std::exception *v50; // [rsp+298h] [rbp-50h] BYREF
  LPCRITICAL_SECTION v51[9]; // [rsp+2A0h] [rbp-48h] BYREF

  v36 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  *(_QWORD *)&v37 = L"CVsSoftwareProvider::SetSnapshotProperty";
  *((_QWORD *)&v37 + 1) = L"SPRPROVC";
  *(_QWORD *)&v38 = 0x200000623LL;
  DWORD2(v38) = 255;
  v48 = 0x1000000;
  memset_0(v39, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v32, (__int64)&v36, 0);
  try
  {
    if ( !IsInGroup() )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v23 = L"CVsSoftwareProvider::SetSnapshotProperty";
      v24 = L"SPRPROVC";
      v25 = 1577;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(
        &v32,
        &v22,
        2147942405LL,
        L"The client process is not running under an administrator account");
    }
    if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v23 = L"CVsSoftwareProvider::SetSnapshotProperty";
      v24 = L"SPRPROVC";
      v25 = 1582;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(&v32, &v22, 2147942487LL, L"SnapshotId == GUID_NULL");
    }
    pvargDest.vt = 0;
    v8 = VariantCopy(&pvargDest, a4);
    if ( v8 < 0 )
    {
      pvargDest.vt = 10;
      pvargDest.lVal = v8;
      ATL::AtlThrowImpl(v8);
    }
    if ( a3 == VSS_SPROPID_SERVICE_MACHINE || a3 == VSS_SPROPID_EXPOSED_NAME || a3 == VSS_SPROPID_EXPOSED_PATH )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      v23 = L"CVsSoftwareProvider::SetSnapshotProperty";
      v24 = L"SPRPROVC";
      if ( pvargDest.vt != 8 )
      {
        v25 = 1607;
        memset_0(v28, 0, sizeof(v28));
        CVssFunctionTracer::Throw(&v32, &v22, 2147942487LL, L"Invalid variant %ul for property %d", pvargDest.vt, a3);
      }
      v25 = 1612;
      memset_0(v28, 0, sizeof(v28));
      LODWORD(v20) = Buf1->Data4[1];
      CVssFunctionTracer::Trace(
        &v32,
        &v22,
        L"Parameters: SnapshotId: {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, eSnapshotPropertyId = %d, vProperty = %s",
        Buf1->Data1,
        Buf1->Data2,
        Buf1->Data3,
        Buf1->Data4[0]);
      if ( !pvargDest.llVal )
      {
        v22 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
        v23 = L"CVsSoftwareProvider::SetSnapshotProperty";
        v24 = L"SPRPROVC";
        v25 = 1618;
        v26 = 2;
        v27 = 255;
        v29 = 0x1000000;
        memset_0(v28, 0, sizeof(v28));
        CVssFunctionTracer::Throw(&v32, &v22, 2147942487LL, L"NULL exposed name/path");
      }
    }
    else
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      v23 = L"CVsSoftwareProvider::SetSnapshotProperty";
      v24 = L"SPRPROVC";
      if ( a3 != VSS_SPROPID_SNAPSHOT_ATTRIBUTES )
      {
        v25 = 1622;
        memset_0(v28, 0, sizeof(v28));
        CVssFunctionTracer::Throw(&v32, &v22, 2147942487LL, L"Invalid property %d", a3);
      }
      if ( pvargDest.vt != 3 )
      {
        v25 = 1592;
        memset_0(v28, 0, sizeof(v28));
        CVssFunctionTracer::Throw(&v32, &v22, 2147942487LL, L"Invalid variant %ul for property %d", pvargDest.vt, 11);
      }
      v25 = 1597;
      memset_0(v28, 0, sizeof(v28));
      LODWORD(v20) = Buf1->Data4[1];
      CVssFunctionTracer::Trace(
        &v32,
        &v22,
        L"Parameters: SnapshotId: {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, eSnapshotPropertyId = %d, vProperty = 0x%08lx",
        Buf1->Data1,
        Buf1->Data2,
        Buf1->Data3,
        Buf1->Data4[0]);
    }
    CVssAutomaticLock2::CVssAutomaticLock2(
      (CVssAutomaticLock2 *)v51,
      (struct CVssCriticalSection *)CVsSoftwareProvider::m_cs);
    v9 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = (__int64)v9;
    v21 = v9;
    if ( v9 )
    {
      v9[1] = 0;
      v9[2] = 0;
      *((_DWORD *)v9 + 6) = 0;
      *v9 = &VSS_OBJECT_PROP_Array::`vftable';
    }
    else
    {
      v10 = 0;
    }
    if ( !v10 )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v23 = L"CVsSoftwareProvider::SetSnapshotProperty";
      v24 = L"SPRPROVC";
      v25 = 1631;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(&v32, &v22, 2147942414LL, L"Memory allocation error.");
    }
    v21 = (_QWORD *)v10;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    ContextInternal = CVsSoftwareProvider::GetContextInternal(this);
    v31 = *Buf1;
    CVssQueuedSnapshot::EnumerateSnapshots(1, &v31, ContextInternal, (struct VSS_OBJECT_PROP_Array *)v10);
    if ( !*(_DWORD *)(v10 + 16) )
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v23 = L"CVsSoftwareProvider::SetSnapshotProperty";
      v24 = L"SPRPROVC";
      v25 = 1644;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(&v32, &v22, 2147754760LL, L"Snapshot not found.");
    }
    v12 = *(_QWORD *)ATL::CSimpleArray<VSS_OBJECT_PROP_Ptr,ATL::CSimpleArrayEqualHelper<VSS_OBJECT_PROP_Ptr>>::operator[](
                       v10 + 8,
                       0);
    if ( a3 == VSS_SPROPID_SERVICE_MACHINE )
    {
      CoTaskMemFree(*(LPVOID *)(v12 + 72));
      *(_QWORD *)(v12 + 72) = 0;
      VssSafeDuplicateStr((struct CVssFunctionTracer *)&v32, (unsigned __int16 **)(v12 + 72), pvargDest.bstrVal);
    }
    else
    {
      if ( a3 == VSS_SPROPID_EXPOSED_NAME )
      {
        v15 = (LPVOID *)(v12 + 80);
      }
      else
      {
        if ( a3 != VSS_SPROPID_EXPOSED_PATH )
        {
          v13 = *(_DWORD *)(v12 + 112);
          lVal = pvargDest.lVal;
          if ( ((pvargDest.lVal ^ v13) & 0xFDCDFFFD) != 0 )
          {
            v22 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
            v23 = L"CVsSoftwareProvider::SetSnapshotProperty";
            v24 = L"SPRPROVC";
            v25 = 1661;
            v26 = 2;
            v27 = 255;
            v29 = 0x1000000;
            memset_0(v28, 0, sizeof(v28));
            LODWORD(v19) = v13;
            LODWORD(v18) = lVal;
            CVssFunctionTracer::Throw(
              &v32,
              &v22,
              2147942487LL,
              L"Invalid attributes 0x%08lx, previous attributes are 0x%08lx",
              v18,
              v19);
          }
          *(_DWORD *)(v12 + 112) = pvargDest.lVal;
          goto LABEL_36;
        }
        v15 = (LPVOID *)(v12 + 88);
      }
      CoTaskMemFree(*v15);
      *v15 = 0;
      VssSafeDuplicateStr((struct CVssFunctionTracer *)&v32, (unsigned __int16 **)v15, pvargDest.bstrVal);
    }
LABEL_36:
    v36 = 0;
    v39[0] = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v47 = 0;
    v46 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v37 = 0;
    v38 = 0;
    CVssIOCTLChannel::Open(
      (CVssIOCTLChannel *)&v36,
      (__int64)&v32,
      *(unsigned __int16 **)(v12 + 48),
      0,
      1,
      2,
      0xC0000000,
      v20,
      0x80u);
    CVssQueuedSnapshot::SaveStructure(
      (struct CVssIOCTLChannel *)&v36,
      (struct _VSS_SNAPSHOT_PROP *)(v12 + 8),
      *(_DWORD *)(v12 + 112) & 0xFDCDFFFD,
      0);
    CVssIOCTLChannel::Call(&v36, (__int64)&v32, 0x53C198u, 1, 2, 0);
    CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v36);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
    CVssAutomaticLock2::~CVssAutomaticLock2(v51);
    VariantClear(&pvargDest);
  }
  catch ( long v35 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v32,
      v35,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::SetSnapshotProperty",
      0x6A9u,
      v34);
  }
  catch ( _com_error *v49 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v32,
      v49,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::SetSnapshotProperty",
      0x6A9u,
      v34);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v32,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::SetSnapshotProperty",
      0x6A9u,
      v34);
  }
  catch ( const std::exception *v50 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v32,
      v50,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::SetSnapshotProperty",
      0x6A9u,
      v34);
  }
  v16 = v33;
  CVssFunctionTracer::~CVssFunctionTracer(&v32);
  return v16;
}

```

## disassembly

```asm
0x180016550  mov     r11, rsp
0x180016553  push    rbx
0x180016554  push    rsi
0x180016555  push    rdi
0x180016556  push    r12
0x180016558  push    r13
0x18001655a  push    r14
0x18001655c  push    r15
0x18001655e  sub     rsp, 2B0h
0x180016565  mov     rbx, r9
0x180016568  mov     r12d, r8d
0x18001656b  mov     r15, rdx
0x18001656e  mov     r13, rcx
0x180016571  lea     r14, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x180016578  mov     [r11-108h], r14
0x18001657f  lea     rax, aCvssoftwarepro_28; "CVsSoftwareProvider::SetSnapshotPropert"...
0x180016586  mov     [r11-100h], rax
0x18001658d  lea     rax, aSprprovc; "SPRPROVC"
0x180016594  mov     [r11-0F8h], rax
0x18001659b  mov     dword ptr [rsp+2E8h+var_F0], 623h
0x1800165a6  mov     esi, 2
0x1800165ab  mov     dword ptr [rsp+2E8h+var_F0+4], esi
0x1800165b2  mov     dword ptr [rsp+2E8h+var_F0+8], 0FFh
0x1800165bd  xor     edi, edi
0x1800165bf  mov     dword ptr [r11-68h], 1000000h
0x1800165c7  xor     edx, edx; Val
0x1800165c9  lea     r8d, [rsi+76h]; Size
0x1800165cd  lea     rcx, [r11-0E0h]; void *
0x1800165d4  call    memset_0
0x1800165d9  xor     r8d, r8d
0x1800165dc  lea     rdx, [rsp+2E8h+var_108]
0x1800165e4  lea     rcx, [rsp+2E8h+var_188]
0x1800165ec  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800165f1  nop
0x1800165f2  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x1800165f7  test    al, al
0x1800165f9  jnz     loc_180016682
0x1800165ff  mov     [rsp+2E8h+var_260], r14
0x180016607  lea     rax, aCvssoftwarepro_28; "CVsSoftwareProvider::SetSnapshotPropert"...
0x18001660e  mov     [rsp+2E8h+var_258], rax
0x180016616  lea     rax, aSprprovc; "SPRPROVC"
0x18001661d  mov     [rsp+2E8h+var_250], rax
0x180016625  mov     [rsp+2E8h+var_248], 629h
0x180016630  mov     [rsp+2E8h+var_244], esi
0x180016637  mov     [rsp+2E8h+var_240], 0FFh
0x180016642  mov     [rsp+2E8h+var_1C0], 1000000h
0x18001664d  xor     edx, edx; Val
0x18001664f  lea     r8d, [rsi+76h]; Size
0x180016653  lea     rcx, [rsp+2E8h+var_238]; void *
0x18001665b  call    memset_0
0x180016660  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x180016667  mov     r8d, 80070005h
0x18001666d  lea     rdx, [rsp+2E8h+var_260]
0x180016675  lea     rcx, [rsp+2E8h+var_188]
0x18001667d  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180016682  mov     r8d, 10h; Size
0x180016688  lea     rdx, GUID_NULL; Buf2
0x18001668f  mov     rcx, r15; Buf1
0x180016692  call    memcmp_0
0x180016697  test    eax, eax
0x180016699  jz      loc_180016F34
0x18001669f  mov     word ptr [rsp+2E8h+pvargDest], di
0x1800166a7  mov     rdx, rbx; pvargSrc
0x1800166aa  lea     rcx, [rsp+2E8h+pvargDest]; pvargDest
0x1800166b2  call    cs:__imp_VariantCopy
0x1800166b8  test    eax, eax
0x1800166ba  jns     short loc_1800166D8
0x1800166bc  mov     ecx, 0Ah
0x1800166c1  mov     word ptr [rsp+2E8h+pvargDest], cx
0x1800166c9  mov     dword ptr [rsp+2E8h+pvargDest+8], eax
0x1800166d0  mov     ecx, eax; int
0x1800166d2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800166d8  mov     ecx, r12d
0x1800166db  sub     ecx, 7
0x1800166de  jz      loc_1800168D0
0x1800166e4  sub     ecx, 1
0x1800166e7  jz      loc_1800168D0
0x1800166ed  sub     ecx, 1
0x1800166f0  jz      loc_1800168D0
0x1800166f6  mov     [rsp+2E8h+var_260], r14
0x1800166fe  lea     rax, aCvssoftwarepro_28; "CVsSoftwareProvider::SetSnapshotPropert"...
0x180016705  mov     [rsp+2E8h+var_244], esi
0x18001670c  mov     [rsp+2E8h+var_240], 0FFh
0x180016717  mov     [rsp+2E8h+var_1C0], 1000000h
0x180016722  xor     edx, edx; Val
0x180016724  lea     r8d, [rdx+78h]; Size
0x180016728  mov     [rsp+2E8h+var_258], rax
0x180016730  lea     rax, aSprprovc; "SPRPROVC"
0x180016737  mov     [rsp+2E8h+var_250], rax
0x18001673f  cmp     ecx, esi
0x180016741  lea     rcx, [rsp+2E8h+var_238]; void *
0x180016749  jz      short loc_180016782
0x18001674b  mov     [rsp+2E8h+var_248], 656h
0x180016756  call    memset_0
0x18001675b  mov     dword ptr [rsp+2E8h+var_2C8], r12d
0x180016760  lea     r9, aInvalidPropert; "Invalid property %d"
0x180016767  mov     r8d, 80070057h
0x18001676d  lea     rdx, [rsp+2E8h+var_260]
0x180016775  lea     rcx, [rsp+2E8h+var_188]
0x18001677d  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180016782  cmp     word ptr [rsp+2E8h+pvargDest], 3
0x18001678b  jz      short loc_1800167D3
0x18001678d  mov     [rsp+2E8h+var_248], 638h
0x180016798  call    memset_0
0x18001679d  movzx   eax, word ptr [rsp+2E8h+pvargDest]
0x1800167a5  mov     dword ptr [rsp+2E8h+var_2C0], 0Bh
0x1800167ad  mov     dword ptr [rsp+2E8h+var_2C8], eax
0x1800167b1  lea     r9, aInvalidVariant; "Invalid variant %ul for property %d"
0x1800167b8  mov     r8d, 80070057h
0x1800167be  lea     rdx, [rsp+2E8h+var_260]
0x1800167c6  lea     rcx, [rsp+2E8h+var_188]
0x1800167ce  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800167d3  mov     [rsp+2E8h+var_248], 63Dh
0x1800167de  call    memset_0
0x1800167e3  movzx   ecx, byte ptr [r15+0Fh]
0x1800167e8  movzx   edx, byte ptr [r15+0Eh]
0x1800167ed  movzx   r8d, byte ptr [r15+0Dh]
0x1800167f2  movzx   r9d, byte ptr [r15+0Ch]
0x1800167f7  movzx   r10d, byte ptr [r15+0Bh]
0x1800167fc  movzx   r11d, byte ptr [r15+0Ah]
0x180016801  movzx   ebx, byte ptr [r15+9]
0x180016806  movzx   edi, byte ptr [r15+8]
0x18001680b  movzx   esi, word ptr [r15+6]
0x180016810  movzx   r14d, word ptr [r15+4]
0x180016815  mov     eax, dword ptr [rsp+2E8h+pvargDest+8]
0x18001681c  mov     dword ptr [rsp+2E8h+var_270], eax
0x180016820  mov     [rsp+2E8h+var_278], 0Bh
0x180016828  mov     [rsp+2E8h+var_280], ecx
0x18001682c  mov     [rsp+2E8h+var_288], edx
0x180016830  mov     [rsp+2E8h+var_290], r8d
0x180016835  mov     [rsp+2E8h+var_298], r9d
0x18001683a  mov     [rsp+2E8h+var_2A0], r10d
0x18001683f  mov     [rsp+2E8h+var_2A8], r11d
0x180016844  mov     dword ptr [rsp+2E8h+var_2B0], ebx
0x180016848  mov     dword ptr [rsp+2E8h+var_2B8], edi
0x18001684c  mov     dword ptr [rsp+2E8h+var_2C0], esi
0x180016850  mov     dword ptr [rsp+2E8h+var_2C8], r14d
0x180016855  mov     r9d, [r15]
0x180016858  lea     r8, aParametersSnap; "Parameters: SnapshotId: {%.8x-%.4x-%.4x"...
0x18001685f  lea     rdx, [rsp+2E8h+var_260]
0x180016867  lea     rcx, [rsp+2E8h+var_188]
0x18001686f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180016874  xor     r14d, r14d
0x180016877  lea     rdx, ?m_cs@CVsSoftwareProvider@@0VCVssCriticalSection@@A; struct CVssCriticalSection *
0x18001687e  lea     rcx, [rsp+2E8h+var_48]; this
0x180016886  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x18001688b  nop
0x18001688c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016893  mov     ecx, 20h ; ' '; unsigned __int64
0x180016898  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001689d  mov     rbx, rax
0x1800168a0  mov     [rsp+2E8h+var_268], rax
0x1800168a8  test    rax, rax
0x1800168ab  jz      loc_180016AAF
0x1800168b1  mov     [rax+8], r14
0x1800168b5  mov     qword ptr [rax+10h], 0
0x1800168bd  mov     [rax+18h], r14d
0x1800168c1  lea     rax, ??_7VSS_OBJECT_PROP_Array@@6B@; const VSS_OBJECT_PROP_Array::`vftable'
0x1800168c8  mov     [rbx], rax
0x1800168cb  jmp     loc_180016AB2
0x1800168d0  mov     [rsp+2E8h+var_260], r14
0x1800168d8  lea     rax, aCvssoftwarepro_28; "CVsSoftwareProvider::SetSnapshotPropert"...
0x1800168df  mov     [rsp+2E8h+var_244], esi
0x1800168e6  mov     [rsp+2E8h+var_240], 0FFh
0x1800168f1  mov     [rsp+2E8h+var_1C0], 1000000h
0x1800168fc  xor     edx, edx; Val
0x1800168fe  lea     r8d, [rdx+78h]; Size
0x180016902  lea     rcx, [rsp+2E8h+var_238]; void *
0x18001690a  mov     [rsp+2E8h+var_258], rax
0x180016912  lea     rax, aSprprovc; "SPRPROVC"
0x180016919  mov     [rsp+2E8h+var_250], rax
0x180016921  cmp     word ptr [rsp+2E8h+pvargDest], 8
0x18001692a  jz      short loc_18001696F
0x18001692c  mov     [rsp+2E8h+var_248], 647h
0x180016937  call    memset_0
0x18001693c  movzx   eax, word ptr [rsp+2E8h+pvargDest]
0x180016944  mov     dword ptr [rsp+2E8h+var_2C0], r12d
0x180016949  mov     dword ptr [rsp+2E8h+var_2C8], eax
0x18001694d  lea     r9, aInvalidVariant; "Invalid variant %ul for property %d"
0x180016954  mov     r8d, 80070057h
0x18001695a  lea     rdx, [rsp+2E8h+var_260]
0x180016962  lea     rcx, [rsp+2E8h+var_188]
0x18001696a  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18001696f  mov     [rsp+2E8h+var_248], 64Ch
0x18001697a  call    memset_0
0x18001697f  movzx   ecx, byte ptr [r15+0Fh]
0x180016984  movzx   edx, byte ptr [r15+0Eh]
0x180016989  movzx   r8d, byte ptr [r15+0Dh]
0x18001698e  movzx   r9d, byte ptr [r15+0Ch]
0x180016993  movzx   r10d, byte ptr [r15+0Bh]
0x180016998  movzx   r11d, byte ptr [r15+0Ah]
0x18001699d  movzx   ebx, byte ptr [r15+9]
0x1800169a2  movzx   edi, byte ptr [r15+8]
0x1800169a7  movzx   esi, word ptr [r15+6]
0x1800169ac  movzx   r14d, word ptr [r15+4]
0x1800169b1  mov     rax, qword ptr [rsp+2E8h+pvargDest+8]
0x1800169b9  mov     [rsp+2E8h+var_270], rax
0x1800169be  mov     [rsp+2E8h+var_278], r12d
0x1800169c3  mov     [rsp+2E8h+var_280], ecx
0x1800169c7  mov     [rsp+2E8h+var_288], edx
0x1800169cb  mov     [rsp+2E8h+var_290], r8d
0x1800169d0  mov     [rsp+2E8h+var_298], r9d
0x1800169d5  mov     [rsp+2E8h+var_2A0], r10d
0x1800169da  mov     [rsp+2E8h+var_2A8], r11d
0x1800169df  mov     dword ptr [rsp+2E8h+var_2B0], ebx
0x1800169e3  mov     dword ptr [rsp+2E8h+var_2B8], edi
0x1800169e7  mov     dword ptr [rsp+2E8h+var_2C0], esi
0x1800169eb  mov     dword ptr [rsp+2E8h+var_2C8], r14d
0x1800169f0  mov     r9d, [r15]
0x1800169f3  lea     r8, aParametersSnap_3; "Parameters: SnapshotId: {%.8x-%.4x-%.4x"...
0x1800169fa  lea     rdx, [rsp+2E8h+var_260]
0x180016a02  lea     rcx, [rsp+2E8h+var_188]
0x180016a0a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180016a0f  xor     r14d, r14d
0x180016a12  cmp     qword ptr [rsp+2E8h+pvargDest+8], r14
0x180016a1a  jnz     loc_180016877
0x180016a20  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x180016a27  mov     [rsp+2E8h+var_260], rax
0x180016a2f  lea     rax, aCvssoftwarepro_28; "CVsSoftwareProvider::SetSnapshotPropert"...
0x180016a36  mov     [rsp+2E8h+var_258], rax
0x180016a3e  lea     rax, aSprprovc; "SPRPROVC"
0x180016a45  mov     [rsp+2E8h+var_250], rax
0x180016a4d  mov     [rsp+2E8h+var_248], 652h
0x180016a58  mov     [rsp+2E8h+var_244], 2
0x180016a63  mov     [rsp+2E8h+var_240], 0FFh
0x180016a6e  mov     [rsp+2E8h+var_1C0], 1000000h
0x180016a79  xor     edx, edx; Val
0x180016a7b  lea     r8d, [r14+78h]; Size
0x180016a7f  lea     rcx, [rsp+2E8h+var_238]; void *
0x180016a87  call    memset_0
0x180016a8c  lea     r9, aNullExposedNam; "NULL exposed name/path"
0x180016a93  mov     r8d, 80070057h
0x180016a99  lea     rdx, [rsp+2E8h+var_260]
0x180016aa1  lea     rcx, [rsp+2E8h+var_188]
0x180016aa9  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180016aaf  mov     rbx, r14
0x180016ab2  test    rbx, rbx
0x180016ab5  jnz     loc_180016B4A
0x180016abb  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x180016ac2  mov     [rsp+2E8h+var_260], rax
0x180016aca  lea     rax, aCvssoftwarepro_28; "CVsSoftwareProvider::SetSnapshotPropert"...
0x180016ad1  mov     [rsp+2E8h+var_258], rax
0x180016ad9  lea     rax, aSprprovc; "SPRPROVC"
0x180016ae0  mov     [rsp+2E8h+var_250], rax
0x180016ae8  mov     [rsp+2E8h+var_248], 65Fh
0x180016af3  mov     [rsp+2E8h+var_244], 2
0x180016afe  mov     [rsp+2E8h+var_240], 0FFh
0x180016b09  mov     [rsp+2E8h+var_1C0], 1000000h
0x180016b14  xor     edx, edx; Val
0x180016b16  lea     r8d, [rbx+78h]; Size
0x180016b1a  lea     rcx, [rsp+2E8h+var_238]; void *
0x180016b22  call    memset_0
0x180016b27  lea     r9, aMemoryAllocati_0; "Memory allocation error."
0x180016b2e  mov     r8d, 8007000Eh
0x180016b34  lea     rdx, [rsp+2E8h+var_260]
0x180016b3c  lea     rcx, [rsp+2E8h+var_188]
0x180016b44  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180016b4a  mov     [rsp+2E8h+var_268], rbx
0x180016b52  mov     rax, [rbx]
0x180016b55  mov     rcx, rbx
0x180016b58  mov     rax, [rax+8]
0x180016b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b61  nop
0x180016b62  mov     rcx, r13; this
0x180016b65  call    ?GetContextInternal@CVsSoftwareProvider@@AEBAJXZ; CVsSoftwareProvider::GetContextInternal(void)
0x180016b6a  movups  xmm0, xmmword ptr [r15]
0x180016b6e  movdqu  xmmword ptr [rsp+2E8h+var_198.Data1], xmm0
0x180016b77  mov     r9, rbx; struct VSS_OBJECT_PROP_Array *
0x180016b7a  mov     r8d, eax; int
0x180016b7d  lea     rdx, [rsp+2E8h+var_198]; struct _GUID
0x180016b85  mov     cl, 1; bool
0x180016b87  call    ?EnumerateSnapshots@CVssQueuedSnapshot@@SAX_NU_GUID@@JPEAVVSS_OBJECT_PROP_Array@@@Z; CVssQueuedSnapshot::EnumerateSnapshots(bool,_GUID,long,VSS_OBJECT_PROP_Array *)
0x180016b8c  cmp     [rbx+10h], r14d
0x180016b90  jnz     loc_180016C24
0x180016b96  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x180016b9d  mov     [rsp+2E8h+var_260], rax
0x180016ba5  lea     rax, aCvssoftwarepro_28; "CVsSoftwareProvider::SetSnapshotPropert"...
0x180016bac  mov     [rsp+2E8h+var_258], rax
0x180016bb4  lea     rax, aSprprovc; "SPRPROVC"
0x180016bbb  mov     [rsp+2E8h+var_250], rax
0x180016bc3  mov     [rsp+2E8h+var_248], 66Ch
0x180016bce  mov     [rsp+2E8h+var_244], 2
0x180016bd9  mov     [rsp+2E8h+var_240], 0FFh
0x180016be4  mov     [rsp+2E8h+var_1C0], 1000000h
0x180016bef  xor     edx, edx; Val
0x180016bf1  lea     r8d, [rdx+78h]; Size
0x180016bf5  lea     rcx, [rsp+2E8h+var_238]; void *
0x180016bfd  call    memset_0
0x180016c02  lea     r9, aSnapshotNotFou; "Snapshot not found."
0x180016c09  mov     r8d, 80042308h
0x180016c0f  lea     rdx, [rsp+2E8h+var_260]
0x180016c17  lea     rcx, [rsp+2E8h+var_188]
0x180016c1f  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180016c24  lea     rcx, [rbx+8]
0x180016c28  xor     edx, edx
0x180016c2a  call    ??A?$CSimpleArray@VVSS_OBJECT_PROP_Ptr@@V?$CSimpleArrayEqualHelper@VVSS_OBJECT_PROP_Ptr@@@ATL@@@ATL@@QEAAAEAVVSS_OBJECT_PROP_Ptr@@H@Z; ATL::CSimpleArray<VSS_OBJECT_PROP_Ptr,ATL::CSimpleArrayEqualHelper<VSS_OBJECT_PROP_Ptr>>::operator[](int)
0x180016c2f  mov     rdi, [rax]
0x180016c32  mov     ecx, r12d
0x180016c35  sub     ecx, 7
0x180016c38  jz      loc_180016DD0
  ... truncated ...
```

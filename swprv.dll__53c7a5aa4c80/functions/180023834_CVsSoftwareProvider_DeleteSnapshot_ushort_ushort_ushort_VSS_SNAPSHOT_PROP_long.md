# CVsSoftwareProvider::DeleteSnapshot(ushort *,ushort *,ushort *,_VSS_SNAPSHOT_PROP &,long)

- ea: `0x180023834`
- end: `0x180023d61`
- name: `?DeleteSnapshot@CVsSoftwareProvider@@CA_NPEAG00AEAU_VSS_SNAPSHOT_PROP@@J@Z`
- size: `1325`
- prototype: `bool __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct _VSS_SNAPSHOT_PROP *, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180024a6c`
- `0x180025228`

## callees

- `0x18000212c`
- `0x1800039d8`
- `0x180003de8`
- `0x180004a38`
- `0x18000610c`
- `0x1800066fc`
- `0x18001bf14`
- `0x18001febc`
- `0x180023834`
- `0x180024710`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`

## string_xrefs

- `0x180023855`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180023c01`: `Warning: snapshot %s cannot be opened`
- `0x180023863`: `CVsSoftwareProvider::DeleteSnapshot`
- `0x1800239d3`: `CVsSoftwareProvider::DeleteSnapshot`
- `0x180023bb3`: `CVsSoftwareProvider::DeleteSnapshot`
- `0x180023adf`: `Cannot dismount snapshot volume %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CVsSoftwareProvider::DeleteSnapshot(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _VSS_SNAPSHOT_PROP *a4,
        int a5)
{
  __int64 v9; // r9
  bool v10; // bl
  char v12; // [rsp+20h] [rbp-2C8h]
  int v13; // [rsp+20h] [rbp-2C8h]
  const unsigned __int16 *v14; // [rsp+58h] [rbp-290h] BYREF
  const unsigned __int16 *v15; // [rsp+60h] [rbp-288h]
  const unsigned __int16 *v16; // [rsp+68h] [rbp-280h]
  int v17; // [rsp+70h] [rbp-278h]
  int v18; // [rsp+74h] [rbp-274h]
  int v19; // [rsp+78h] [rbp-270h]
  _BYTE v20[120]; // [rsp+80h] [rbp-268h] BYREF
  int v21; // [rsp+F8h] [rbp-1F0h]
  LPVOID v22; // [rsp+100h] [rbp-1E8h] BYREF
  int v23; // [rsp+108h] [rbp-1E0h]
  unsigned int v24; // [rsp+124h] [rbp-1C4h]
  int v25; // [rsp+170h] [rbp-178h] BYREF
  __int64 v26; // [rsp+180h] [rbp-168h] BYREF
  __int128 v27; // [rsp+188h] [rbp-160h]
  __int128 v28; // [rsp+198h] [rbp-150h]
  __int16 v29; // [rsp+1A8h] [rbp-140h]
  __int64 v30; // [rsp+1ACh] [rbp-13Ch]
  __int64 v31; // [rsp+1B8h] [rbp-130h]
  __int64 v32; // [rsp+1C0h] [rbp-128h]
  int v33; // [rsp+1C8h] [rbp-120h]
  __int64 v34; // [rsp+1D0h] [rbp-118h]
  __int16 v35; // [rsp+1D8h] [rbp-110h]
  void **v36; // [rsp+1E0h] [rbp-108h]
  __int64 v37; // [rsp+1E8h] [rbp-100h]
  const unsigned __int16 *v38; // [rsp+1F0h] [rbp-F8h] BYREF
  __int128 v39; // [rsp+1F8h] [rbp-F0h]
  __int128 v40; // [rsp+208h] [rbp-E0h]
  _WORD v41[2]; // [rsp+218h] [rbp-D0h] BYREF
  __int64 v42; // [rsp+21Ch] [rbp-CCh]
  __int64 v43; // [rsp+228h] [rbp-C0h]
  __int64 v44; // [rsp+230h] [rbp-B8h]
  int v45; // [rsp+238h] [rbp-B0h]
  __int64 v46; // [rsp+240h] [rbp-A8h]
  __int16 v47; // [rsp+248h] [rbp-A0h]
  void **v48; // [rsp+250h] [rbp-98h]
  __int64 v49; // [rsp+258h] [rbp-90h]
  int v50; // [rsp+290h] [rbp-58h]
  _com_error *v51; // [rsp+2A0h] [rbp-48h] BYREF
  const std::exception *v52; // [rsp+2A8h] [rbp-40h] BYREF

  v38 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
  *(_QWORD *)&v39 = L"CVsSoftwareProvider::DeleteSnapshot";
  *((_QWORD *)&v39 + 1) = L"SPRDELEC";
  *(_QWORD *)&v40 = 0x20000025CLL;
  DWORD2(v40) = 255;
  v50 = 0x1000000;
  memset_0(v41, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v22, (__int64)&v38, 0);
  try
  {
    v26 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v37 = 0;
    v36 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v27 = 0;
    v28 = 0;
    v12 = 0;
    v23 = CVssIOCTLChannel::Open(&v26, &v22, a3, 0, v12, 0, -1073741824);
    if ( v23 < 0 )
    {
      v14 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
      v15 = L"CVsSoftwareProvider::DeleteSnapshot";
      v16 = L"SPRDELEC";
      v17 = 619;
      v18 = 2;
      v19 = 255;
      v21 = 0x1000000;
      memset_0(v20, 0, sizeof(v20));
      CVssFunctionTracer::Trace(&v22, &v14, L"Warning: snapshot %s cannot be opened", a3);
    }
    else
    {
      CVssQueuedSnapshot::SaveStructure((struct CVssIOCTLChannel *)&v26, a4, a4->m_lSnapshotAttributes & 0xFDCDFFFD, 1);
      v23 = CVssIOCTLChannel::Call(&v26, (__int64)&v22, 0x53C198u, 0, 0, 0);
      if ( v23 < 0 )
      {
        v14 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
        v15 = L"CVsSoftwareProvider::DeleteSnapshot";
        v16 = L"SPRDELEC";
        v17 = 630;
        v18 = 2;
        v19 = 255;
        v21 = 0x1000000;
        memset_0(v20, 0, sizeof(v20));
        CVssFunctionTracer::Trace(&v22, &v14, L"cannot set app info for snapshot %s", a3);
      }
      CVsSoftwareProvider::HideSnapshotForDelete((struct CVssIOCTLChannel *)&v26);
      LODWORD(v30) = 0;
      LODWORD(v32) = 0;
      CVssIOCTLChannel::Call(&v26, (__int64)&v22, 0x90020u, 0, 0, 0);
      if ( v23 < 0 )
      {
        v14 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
        v15 = L"CVsSoftwareProvider::DeleteSnapshot";
        v16 = L"SPRDELEC";
        v17 = 637;
        v18 = 2;
        v19 = 255;
        v21 = 0x1000000;
        memset_0(v20, 0, sizeof(v20));
        CVssFunctionTracer::Trace(&v22, &v14, L"Cannot dismount snapshot volume %s", a3);
      }
      LODWORD(v30) = 0;
      LODWORD(v32) = 0;
      CVssIOCTLChannel::Call(&v26, (__int64)&v22, 0x56C00Cu, 0, 0, 0);
      if ( v23 < 0 )
      {
        v14 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
        v15 = L"CVsSoftwareProvider::DeleteSnapshot";
        v16 = L"SPRDELEC";
        v17 = 642;
        v18 = 2;
        v19 = 255;
        v21 = 0x1000000;
        memset_0(v20, 0, sizeof(v20));
        CVssFunctionTracer::Trace(&v22, &v14, L"Cannot offline snapshot volume %s", a3);
      }
      CVssIOCTLChannel::Close((CVssIOCTLChannel *)&v26);
    }
    v38 = 0;
    v41[0] = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v49 = 0;
    v48 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v39 = 0;
    v40 = 0;
    LOBYTE(v13) = 1;
    LOBYTE(v9) = 1;
    CVssIOCTLChannel::Open(&v38, &v22, a1, v9, v13, 2, -1073741824);
    CVssIOCTLChannel::PackSmallString((CVssIOCTLChannel *)&v38, (struct CVssFunctionTracer *)&v22, a2);
    CVssIOCTLChannel::Call(&v38, (__int64)&v22, 0x53C038u, 1, 4, 0);
    CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v38);
    CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v26);
  }
  catch ( long v25 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v22,
      v25,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::DeleteSnapshot",
      0x295u,
      v24);
  }
  catch ( _com_error *v51 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v22,
      v51,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::DeleteSnapshot",
      0x295u,
      v24);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v22,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::DeleteSnapshot",
      0x295u,
      v24);
  }
  catch ( const std::exception *v52 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v22,
      v52,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::DeleteSnapshot",
      0x295u,
      v24);
  }
  v26 = 0;
  v29 = 0;
  v30 = 0;
}

```

## disassembly

```asm
0x180023834  mov     r11, rsp
0x180023837  push    rbx
0x180023838  push    rsi
0x180023839  push    rdi
0x18002383a  push    r12
0x18002383c  push    r13
0x18002383e  push    r14
0x180023840  push    r15
0x180023842  sub     rsp, 2B0h
0x180023849  mov     rdi, r9
0x18002384c  mov     rsi, r8
0x18002384f  mov     r14, rdx
0x180023852  mov     r15, rcx
0x180023855  lea     r13, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002385c  mov     [r11-0F8h], r13
0x180023863  lea     rax, aCvssoftwarepro_15; "CVsSoftwareProvider::DeleteSnapshot"
0x18002386a  mov     [r11-0F0h], rax
0x180023871  lea     rax, aSprdelec; "SPRDELEC"
0x180023878  mov     [r11-0E8h], rax
0x18002387f  mov     dword ptr [rsp+2E8h+var_E0], 25Ch
0x18002388a  mov     r12d, 2
0x180023890  mov     [r11-0DCh], r12d
0x180023897  mov     dword ptr [rsp+2E8h+var_E0+8], 0FFh
0x1800238a2  xor     ebx, ebx
0x1800238a4  mov     dword ptr [r11-58h], 1000000h
0x1800238ac  xor     edx, edx; Val
0x1800238ae  lea     r8d, [r12+76h]; Size
0x1800238b3  lea     rcx, [r11-0D0h]; void *
0x1800238ba  call    memset_0
0x1800238bf  xor     r8d, r8d
0x1800238c2  lea     rdx, [rsp+2E8h+var_F8]
0x1800238ca  lea     rcx, [rsp+2E8h+var_1E8]
0x1800238d2  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800238d7  nop
0x1800238d8  mov     [rsp+2E8h+var_168], rbx
0x1800238e0  mov     [rsp+2E8h+var_140], bx
0x1800238e8  mov     [rsp+2E8h+var_13C], rbx
0x1800238f0  mov     [rsp+2E8h+var_130], rbx
0x1800238f8  mov     [rsp+2E8h+var_128], rbx
0x180023900  mov     [rsp+2E8h+var_120], ebx
0x180023907  mov     [rsp+2E8h+var_118], rbx
0x18002390f  mov     [rsp+2E8h+var_110], bx
0x180023917  mov     [rsp+2E8h+var_100], rbx
0x18002391f  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180023926  mov     [rsp+2E8h+var_108], rax
0x18002392e  xorps   xmm0, xmm0
0x180023931  movups  [rsp+2E8h+var_160], xmm0
0x180023939  movups  [rsp+2E8h+var_150], xmm0
0x180023941  mov     [rsp+2E8h+var_2A8], 80h
0x180023949  mov     dword ptr [rsp+2E8h+var_2B8], 0C0000000h
0x180023951  mov     [rsp+2E8h+var_2C0], ebx
0x180023955  mov     byte ptr [rsp+2E8h+var_2C8], bl
0x180023959  xor     r9d, r9d
0x18002395c  mov     r8, rsi
0x18002395f  lea     rdx, [rsp+2E8h+var_1E8]
0x180023967  lea     rcx, [rsp+2E8h+var_168]
0x18002396f  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x180023974  mov     [rsp+2E8h+var_1E0], eax
0x18002397b  test    eax, eax
0x18002397d  js      loc_180023BAE
0x180023983  mov     r8d, [rdi+68h]
0x180023987  and     r8d, 0FDCDFFFDh; int
0x18002398e  mov     r9b, 1; bool
0x180023991  mov     rdx, rdi; struct _VSS_SNAPSHOT_PROP *
0x180023994  lea     rcx, [rsp+2E8h+var_168]; this
0x18002399c  call    ?SaveStructure@CVssQueuedSnapshot@@SAXAEAVCVssIOCTLChannel@@PEAU_VSS_SNAPSHOT_PROP@@J_N@Z; CVssQueuedSnapshot::SaveStructure(CVssIOCTLChannel &,_VSS_SNAPSHOT_PROP *,long,bool)
0x1800239a1  mov     [rsp+2E8h+var_2B8], rbx
0x1800239a6  mov     byte ptr [rsp+2E8h+var_2C0], bl
0x1800239aa  mov     [rsp+2E8h+var_2C8], ebx
0x1800239ae  xor     r9d, r9d
0x1800239b1  mov     r8d, 53C198h
0x1800239b7  lea     rdx, [rsp+2E8h+var_1E8]
0x1800239bf  lea     rcx, [rsp+2E8h+var_168]
0x1800239c7  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x1800239cc  mov     [rsp+2E8h+var_1E0], eax
0x1800239d3  lea     rdi, aCvssoftwarepro_15; "CVsSoftwareProvider::DeleteSnapshot"
0x1800239da  test    eax, eax
0x1800239dc  jns     short loc_180023A44
0x1800239de  mov     [rsp+2E8h+var_290], r13
0x1800239e3  mov     [rsp+2E8h+var_288], rdi
0x1800239e8  lea     rax, aSprdelec; "SPRDELEC"
0x1800239ef  mov     [rsp+2E8h+var_280], rax
0x1800239f4  mov     [rsp+2E8h+var_278], 276h
0x1800239fc  mov     [rsp+2E8h+var_274], r12d
0x180023a01  mov     [rsp+2E8h+var_270], 0FFh
0x180023a09  mov     [rsp+2E8h+var_1F0], 1000000h
0x180023a14  xor     edx, edx; Val
0x180023a16  lea     r8d, [r12+76h]; Size
0x180023a1b  lea     rcx, [rsp+2E8h+var_268]; void *
0x180023a23  call    memset_0
0x180023a28  mov     r9, rsi
0x180023a2b  lea     r8, aCannotSetAppIn; "cannot set app info for snapshot %s"
0x180023a32  lea     rdx, [rsp+2E8h+var_290]
0x180023a37  lea     rcx, [rsp+2E8h+var_1E8]
0x180023a3f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180023a44  lea     rcx, [rsp+2E8h+var_168]; this
0x180023a4c  call    ?HideSnapshotForDelete@CVsSoftwareProvider@@CAXAEAVCVssIOCTLChannel@@@Z; CVsSoftwareProvider::HideSnapshotForDelete(CVssIOCTLChannel &)
0x180023a51  mov     dword ptr [rsp+2E8h+var_13C], ebx
0x180023a58  mov     dword ptr [rsp+2E8h+var_128], ebx
0x180023a5f  mov     [rsp+2E8h+var_2B8], rbx
0x180023a64  mov     byte ptr [rsp+2E8h+var_2C0], bl
0x180023a68  mov     [rsp+2E8h+var_2C8], ebx
0x180023a6c  xor     r9d, r9d
0x180023a6f  mov     r8d, 90020h
0x180023a75  lea     rdx, [rsp+2E8h+var_1E8]
0x180023a7d  lea     rcx, [rsp+2E8h+var_168]
0x180023a85  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x180023a8a  cmp     [rsp+2E8h+var_1E0], ebx
0x180023a91  jge     short loc_180023AF8
0x180023a93  mov     [rsp+2E8h+var_290], r13
0x180023a98  mov     [rsp+2E8h+var_288], rdi
0x180023a9d  lea     rax, aSprdelec; "SPRDELEC"
0x180023aa4  mov     [rsp+2E8h+var_280], rax
0x180023aa9  mov     [rsp+2E8h+var_278], 27Dh
0x180023ab1  mov     [rsp+2E8h+var_274], r12d
0x180023ab6  mov     [rsp+2E8h+var_270], 0FFh
0x180023abe  mov     [rsp+2E8h+var_1F0], 1000000h
0x180023ac9  xor     edx, edx; Val
0x180023acb  lea     r8d, [rdx+78h]; Size
0x180023acf  lea     rcx, [rsp+2E8h+var_268]; void *
0x180023ad7  call    memset_0
0x180023adc  mov     r9, rsi
0x180023adf  lea     r8, aCannotDismount; "Cannot dismount snapshot volume %s"
0x180023ae6  lea     rdx, [rsp+2E8h+var_290]
0x180023aeb  lea     rcx, [rsp+2E8h+var_1E8]
0x180023af3  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180023af8  mov     dword ptr [rsp+2E8h+var_13C], ebx
0x180023aff  mov     dword ptr [rsp+2E8h+var_128], ebx
0x180023b06  mov     [rsp+2E8h+var_2B8], rbx
0x180023b0b  mov     byte ptr [rsp+2E8h+var_2C0], bl
0x180023b0f  mov     [rsp+2E8h+var_2C8], ebx
0x180023b13  xor     r9d, r9d
0x180023b16  mov     r8d, 56C00Ch
0x180023b1c  lea     rdx, [rsp+2E8h+var_1E8]
0x180023b24  lea     rcx, [rsp+2E8h+var_168]
0x180023b2c  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x180023b31  cmp     [rsp+2E8h+var_1E0], ebx
0x180023b38  jge     short loc_180023B9F
0x180023b3a  mov     [rsp+2E8h+var_290], r13
0x180023b3f  mov     [rsp+2E8h+var_288], rdi
0x180023b44  lea     rax, aSprdelec; "SPRDELEC"
0x180023b4b  mov     [rsp+2E8h+var_280], rax
0x180023b50  mov     [rsp+2E8h+var_278], 282h
0x180023b58  mov     [rsp+2E8h+var_274], r12d
0x180023b5d  mov     [rsp+2E8h+var_270], 0FFh
0x180023b65  mov     [rsp+2E8h+var_1F0], 1000000h
0x180023b70  xor     edx, edx; Val
0x180023b72  lea     r8d, [rdx+78h]; Size
0x180023b76  lea     rcx, [rsp+2E8h+var_268]; void *
0x180023b7e  call    memset_0
0x180023b83  mov     r9, rsi
0x180023b86  lea     r8, aCannotOfflineS; "Cannot offline snapshot volume %s"
0x180023b8d  lea     rdx, [rsp+2E8h+var_290]
0x180023b92  lea     rcx, [rsp+2E8h+var_1E8]
0x180023b9a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180023b9f  lea     rcx, [rsp+2E8h+var_168]; this
0x180023ba7  call    ?Close@CVssIOCTLChannel@@QEAAXXZ; CVssIOCTLChannel::Close(void)
0x180023bac  jmp     short loc_180023C1A
0x180023bae  mov     [rsp+2E8h+var_290], r13
0x180023bb3  lea     rdi, aCvssoftwarepro_15; "CVsSoftwareProvider::DeleteSnapshot"
0x180023bba  mov     [rsp+2E8h+var_288], rdi
0x180023bbf  lea     rax, aSprdelec; "SPRDELEC"
0x180023bc6  mov     [rsp+2E8h+var_280], rax
0x180023bcb  mov     [rsp+2E8h+var_278], 26Bh
0x180023bd3  mov     [rsp+2E8h+var_274], r12d
0x180023bd8  mov     [rsp+2E8h+var_270], 0FFh
0x180023be0  mov     [rsp+2E8h+var_1F0], 1000000h
0x180023beb  xor     edx, edx; Val
0x180023bed  lea     r8d, [rdx+78h]; Size
0x180023bf1  lea     rcx, [rsp+2E8h+var_268]; void *
0x180023bf9  call    memset_0
0x180023bfe  mov     r9, rsi
0x180023c01  lea     r8, aWarningSnapsho_0; "Warning: snapshot %s cannot be opened"
0x180023c08  lea     rdx, [rsp+2E8h+var_290]
0x180023c0d  lea     rcx, [rsp+2E8h+var_1E8]
0x180023c15  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180023c1a  mov     [rsp+2E8h+var_F8], rbx
0x180023c22  mov     [rsp+2E8h+var_D0], bx
0x180023c2a  mov     [rsp+2E8h+var_CC], rbx
0x180023c32  mov     [rsp+2E8h+var_C0], rbx
0x180023c3a  mov     [rsp+2E8h+var_B8], rbx
0x180023c42  mov     [rsp+2E8h+var_B0], ebx
0x180023c49  mov     [rsp+2E8h+var_A8], rbx
0x180023c51  mov     [rsp+2E8h+var_A0], bx
0x180023c59  mov     [rsp+2E8h+var_90], rbx
0x180023c61  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180023c68  mov     [rsp+2E8h+var_98], rax
0x180023c70  xorps   xmm0, xmm0
0x180023c73  movups  [rsp+2E8h+var_F0], xmm0
0x180023c7b  movups  [rsp+2E8h+var_E0], xmm0
0x180023c83  mov     [rsp+2E8h+var_2A8], 80h
0x180023c8b  mov     dword ptr [rsp+2E8h+var_2B8], 0C0000000h
0x180023c93  mov     [rsp+2E8h+var_2C0], r12d
0x180023c98  mov     byte ptr [rsp+2E8h+var_2C8], 1
0x180023c9d  mov     r9b, 1
0x180023ca0  mov     r8, r15
0x180023ca3  lea     rdx, [rsp+2E8h+var_1E8]
0x180023cab  lea     rcx, [rsp+2E8h+var_F8]
0x180023cb3  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x180023cb8  mov     r8, r14; unsigned __int16 *
0x180023cbb  lea     rdx, [rsp+2E8h+var_1E8]; struct CVssFunctionTracer *
0x180023cc3  lea     rcx, [rsp+2E8h+var_F8]; this
0x180023ccb  call    ?PackSmallString@CVssIOCTLChannel@@QEAAPEAXAEAVCVssFunctionTracer@@PEBG@Z; CVssIOCTLChannel::PackSmallString(CVssFunctionTracer &,ushort const *)
0x180023cd0  mov     [rsp+2E8h+var_2B8], rbx
0x180023cd5  mov     byte ptr [rsp+2E8h+var_2C0], bl
0x180023cd9  mov     [rsp+2E8h+var_2C8], 4
0x180023ce1  mov     r9b, 1
0x180023ce4  mov     r8d, 53C038h
0x180023cea  lea     rdx, [rsp+2E8h+var_1E8]
0x180023cf2  lea     rcx, [rsp+2E8h+var_F8]
0x180023cfa  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x180023cff  nop
0x180023d00  lea     rcx, [rsp+2E8h+var_F8]; this
0x180023d08  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x180023d0d  nop
0x180023d0e  lea     rcx, [rsp+2E8h+var_168]; this
0x180023d16  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x180023d1b  nop
0x180023d1c  jmp     short loc_180023D26
0x180023d1e  jmp     short loc_180023D24
0x180023d20  jmp     short loc_180023D24
0x180023d22  jmp     short $+2
0x180023d24  xor     ebx, ebx
0x180023d26  cmp     [rsp+2E8h+var_1E0], ebx
0x180023d2d  setnl   dl; bool
0x180023d30  lea     rcx, [rsp+2E8h+var_1E8]; this
0x180023d38  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x180023d3d  mov     bl, al
0x180023d3f  lea     rcx, [rsp+2E8h+var_1E8]; this
0x180023d47  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180023d4c  mov     al, bl
0x180023d4e  add     rsp, 2B0h
0x180023d55  pop     r15
0x180023d57  pop     r14
0x180023d59  pop     r13
0x180023d5b  pop     r12
0x180023d5d  pop     rdi
0x180023d5e  pop     rsi
0x180023d5f  pop     rbx
0x180023d60  retn
```

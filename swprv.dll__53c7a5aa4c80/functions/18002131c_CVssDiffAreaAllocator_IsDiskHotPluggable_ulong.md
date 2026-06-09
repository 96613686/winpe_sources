# CVssDiffAreaAllocator::IsDiskHotPluggable(ulong)

- ea: `0x18002131c`
- end: `0x180021b57`
- name: `?IsDiskHotPluggable@CVssDiffAreaAllocator@@AEAA_NK@Z`
- size: `2107`
- prototype: `char __fastcall(CVssDiffAreaAllocator *this, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020638`

## callees

- `0x180001580`
- `0x18000212c`
- `0x1800039d8`
- `0x180003de8`
- `0x180004a38`
- `0x18000610c`
- `0x18001eea0`
- `0x18001febc`
- `0x18002131c`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x1800377c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219f5`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1800217c1`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1800217c1`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180021b0f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180021b0f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180021417`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180021417`
- `DEVOBJ!DevObjGetClassDevs` at `0x180021492`
- `DEVOBJ!DevObjGetClassDevs` at `0x180021492`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18002150f`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18002150f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18002156c`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800215b1`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18002156c`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800215b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021547`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021547`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021576`

## string_xrefs

- `0x18002145d`: `DevObjCreateDeviceInfoList(NULL, NULL, NULL, NULL, NULL)`
- `0x180021834`: `Unable to Open an IOCTL channel to %s`
- `0x1800218c2`: `Error in DevObjGetDeviceRegistryProperty querying DODRP_REMOVAL_POLICY on %s: 0x%x, HRESULT 0x%08lx`

## pseudocode

```c
char __fastcall CVssDiffAreaAllocator::IsDiskHotPluggable(CVssDiffAreaAllocator *this, unsigned int a2)
{
  __int64 DeviceInfoList; // rax
  __int64 v4; // r15
  char *v5; // rbx
  char v6; // r13
  unsigned int i; // r14d
  char *v8; // rax
  signed int v9; // eax
  signed int v10; // esi
  unsigned int v11; // edi
  signed int LastError; // eax
  signed int v13; // esi
  unsigned int v14; // edi
  signed int v15; // eax
  unsigned int v16; // edi
  unsigned int v17; // esi
  char v18; // bl
  __int64 v20; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+20h] [rbp-E0h]
  int *v22; // [rsp+20h] [rbp-E0h]
  __int64 v23; // [rsp+28h] [rbp-D8h]
  __int64 v24; // [rsp+28h] [rbp-D8h]
  __int64 v25; // [rsp+30h] [rbp-D0h]
  __int64 v26; // [rsp+30h] [rbp-D0h]
  SIZE_T cb[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v29; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v30; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v31; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+8Ch] [rbp-74h]
  int v35; // [rsp+90h] [rbp-70h]
  _BYTE v36[120]; // [rsp+98h] [rbp-68h] BYREF
  int v37; // [rsp+110h] [rbp+10h]
  int v38; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v39; // [rsp+120h] [rbp+20h] BYREF
  __int128 v40; // [rsp+128h] [rbp+28h]
  __int128 v41; // [rsp+138h] [rbp+38h]
  _WORD v42[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v43; // [rsp+14Ch] [rbp+4Ch]
  __int64 v44; // [rsp+158h] [rbp+58h]
  __int64 v45; // [rsp+160h] [rbp+60h]
  int v46; // [rsp+168h] [rbp+68h]
  __int64 v47; // [rsp+170h] [rbp+70h]
  __int16 v48; // [rsp+178h] [rbp+78h]
  void **v49; // [rsp+180h] [rbp+80h]
  __int64 v50; // [rsp+188h] [rbp+88h]
  int v51; // [rsp+1C0h] [rbp+C0h]
  LPVOID v52; // [rsp+1D0h] [rbp+D0h] BYREF
  int v53; // [rsp+1D8h] [rbp+D8h]
  _QWORD v54[3]; // [rsp+240h] [rbp+140h] BYREF
  int v55; // [rsp+258h] [rbp+158h]
  int v56; // [rsp+25Ch] [rbp+15Ch]
  int v57; // [rsp+260h] [rbp+160h]
  _BYTE v58[120]; // [rsp+268h] [rbp+168h] BYREF
  int v59; // [rsp+2E0h] [rbp+1E0h]
  __int64 v60; // [rsp+2E8h] [rbp+1E8h] BYREF
  int v61; // [rsp+2F0h] [rbp+1F0h]
  _OWORD v62[2]; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int128 v63; // [rsp+318h] [rbp+218h] BYREF
  __int128 v64; // [rsp+328h] [rbp+228h]
  __int128 v65; // [rsp+338h] [rbp+238h]

  v29 = a2;
  v39 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
  *(_QWORD *)&v40 = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
  *((_QWORD *)&v40 + 1) = L"SPRALLOC";
  *(_QWORD *)&v41 = 0x20000073ALL;
  DWORD2(v41) = 255;
  v51 = 0x1000000;
  memset_0(v42, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v52, (__int64)&v39, 0);
  LODWORD(cb[0]) = 0;
  v28 = 1;
  v60 = 0;
  v61 = 0;
  v38 = 0;
  memset(v62, 0, sizeof(v62));
  v63 = 0;
  v64 = 0;
  v65 = 0;
  LODWORD(v62[0]) = 32;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v4 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    v39 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
    *(_QWORD *)&v40 = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
    *((_QWORD *)&v40 + 1) = L"SPRALLOC";
    *(_QWORD *)&v41 = 0x200000753LL;
    DWORD2(v41) = 255;
    v51 = 0x1000000;
    memset_0(v42, 0, 0x78u);
    CVssFunctionTracer::TranslateWin32Error(&v52, &v39, L"DevObjCreateDeviceInfoList(NULL, NULL, NULL, NULL, NULL)");
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0) )
  {
    v39 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
    *(_QWORD *)&v40 = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
    *((_QWORD *)&v40 + 1) = L"SPRALLOC";
    *(_QWORD *)&v41 = 0x20000075DLL;
    DWORD2(v41) = 255;
    v51 = 0x1000000;
    memset_0(v42, 0, 0x78u);
    CVssFunctionTracer::TranslateWin32Error(
      &v52,
      &v39,
      L"DevObjGetClassDevs(&, NULL, NULL, DOGCF_DEVICEINTERFACE | DOGCF_PRESENT, NULL, NULL)");
  }
  v5 = 0;
  v6 = 0;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v4, 0, &GUID_DEVINTERFACE_DISK, i, v62); ++i )
  {
    v63 = 0;
    v64 = 0;
    v65 = 0;
    LODWORD(v63) = 48;
    if ( v5 )
      CoTaskMemFree(v5);
    DevObjGetDeviceInterfaceDetail(v4, v62, 0, 0, cb, 0, v25);
    v8 = (char *)CoTaskMemAlloc(LODWORD(cb[0]));
    v5 = v8;
    if ( !v8 )
    {
      v30 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
      v31 = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
      v32 = L"SPRALLOC";
      v33 = 1921;
      v34 = 2;
      v35 = 255;
      v37 = 0x1000000;
      memset_0(v36, 0, sizeof(v36));
      CVssFunctionTracer::Trace(&v52, &v30, L"Can't determine whether disk %d is hot pluggable. E_OUTOFMEMORY", a2);
      goto LABEL_36;
    }
    *(_DWORD *)v8 = 8;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v4, v62, v8, LODWORD(cb[0]), 0, &v63, v26) )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      else
        v14 = LastError;
      v53 = v14;
      v30 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
      v31 = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
      v32 = L"SPRALLOC";
      v33 = 1940;
      v34 = 2;
      v35 = 255;
      v37 = 0x1000000;
      memset_0(v36, 0, sizeof(v36));
      LODWORD(v23) = v14;
      LODWORD(v21) = v13;
      CVssFunctionTracer::Trace(
        &v52,
        &v30,
        L"Error-DevObjGetDeviceInterfaceDetail for disk no %d: 0x%x, HRESULT 0x%08lx",
        i,
        v21,
        v23);
LABEL_35:
      CoTaskMemFree(v5);
      goto LABEL_36;
    }
    v39 = 0;
    v42[0] = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v50 = 0;
    v49 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v40 = 0;
    v41 = 0;
    LOBYTE(v21) = 0;
    v53 = CVssIOCTLChannel::Open(&v39, &v52, v5 + 4, 0, v21, 0, 0x80000000);
    if ( v53 < 0 )
    {
      v30 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
      v31 = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
      v32 = L"SPRALLOC";
      v33 = 1983;
      v34 = 2;
      v35 = 255;
      v37 = 0x1000000;
      memset_0(v36, 0, sizeof(v36));
      CVssFunctionTracer::Trace(&v52, &v30, L"Unable to Open an IOCTL channel to %s", v5 + 4);
    }
    else
    {
      v25 = 0;
      v53 = CVssIOCTLChannel::Call(&v39, (__int64)&v52, 0x2D1080u, 0, 0, 0);
      if ( v53 >= 0 )
      {
        v60 = 0;
        v61 = 0;
        CVssIOCTLChannel::Unpack<_STORAGE_DEVICE_NUMBER>(
          (__int64)&v39,
          (struct CVssFunctionTracer *)&v52,
          (__int64)&v60);
        CVssIOCTLChannel::Close((CVssIOCTLChannel *)&v39);
        if ( HIDWORD(v60) == a2 )
        {
          CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v39);
          v30 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
          v31 = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
          v32 = L"SPRALLOC";
          v33 = 1997;
          v34 = 2;
          v35 = 255;
          v37 = 0x1000000;
          memset_0(v36, 0, sizeof(v36));
          CVssFunctionTracer::Trace(&v52, &v30, L"Found device matching disk number %d", a2);
          v22 = &v28;
          if ( (unsigned int)DevObjGetDeviceRegistryProperty(v4, &v63, 31) )
          {
            if ( v28 != 1 )
              v6 = 1;
          }
          else
          {
            v9 = GetLastError();
            v10 = v9;
            if ( v9 > 0 )
              v11 = (unsigned __int16)v9 | 0x80070000;
            else
              v11 = v9;
            v53 = v11;
            v30 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
            v31 = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
            v32 = L"SPRALLOC";
            v33 = 2010;
            v34 = 2;
            v35 = 255;
            v37 = 0x1000000;
            memset_0(v36, 0, sizeof(v36));
            LODWORD(v24) = v11;
            LODWORD(v22) = v10;
            CVssFunctionTracer::Trace(
              &v52,
              &v30,
              L"Error in DevObjGetDeviceRegistryProperty querying DODRP_REMOVAL_POLICY on %s: 0x%x, HRESULT 0x%08lx",
              v5 + 4,
              v22,
              v24);
          }
          goto LABEL_35;
        }
      }
      else
      {
        v54[0] = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
        v54[1] = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
        v54[2] = L"SPRALLOC";
        v55 = 1965;
        v56 = 2;
        v57 = 255;
        v59 = 0x1000000;
        memset_0(v58, 0, sizeof(v58));
        CVssFunctionTracer::Trace(&v52, v54, L"Unable to get the disk number of %s", v5 + 4);
      }
    }
    CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v39);
  }
  v15 = GetLastError();
  v16 = v15;
  if ( v15 != 259 )
  {
    if ( v15 > 0 )
      v17 = (unsigned __int16)v15 | 0x80070000;
    else
      v17 = v15;
    v53 = v17;
    v30 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
    v31 = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
    v32 = L"SPRALLOC";
    v33 = 1898;
    v34 = 2;
    v35 = 255;
    v37 = 0x1000000;
    memset_0(v36, 0, sizeof(v36));
    LODWORD(v20) = v17;
    CVssFunctionTracer::Trace(&v52, &v30, L"Error-DevObjEnumDeviceInterfaces: 0x%x, HRESULT 0x%08lx", v16, v20);
  }
  v30 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
  v31 = L"CVssDiffAreaAllocator::IsDiskHotPluggable";
  v32 = L"SPRALLOC";
  v33 = 1994;
  v34 = 2;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(v36, 0, sizeof(v36));
  CVssFunctionTracer::Trace(&v52, &v30, L"Couldn't find device %d for the volume. E_UNEXPECTED", v29);
  v6 = 0;
  if ( v5 )
    goto LABEL_35;
LABEL_36:
  DevObjDestroyDeviceInfoList(v4);
  v18 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v52, v6);
  CVssFunctionTracer::~CVssFunctionTracer(&v52);
  return v18;
}

```

## disassembly

```asm
0x18002131c  push    rbp
0x18002131e  push    rbx
0x18002131f  push    rsi
0x180021320  push    rdi
0x180021321  push    r12
0x180021323  push    r13
0x180021325  push    r14
0x180021327  push    r15
0x180021329  lea     rbp, [rsp-258h]
0x180021331  sub     rsp, 358h
0x180021338  mov     rax, cs:__security_cookie
0x18002133f  xor     rax, rsp
0x180021342  mov     [rbp+290h+var_48], rax
0x180021349  mov     edi, edx
0x18002134b  mov     [rsp+390h+var_328], edx
0x18002134f  lea     r12, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x180021356  mov     [rbp+290h+var_270], r12
0x18002135a  lea     rbx, aCvssdiffareaal_0; "CVssDiffAreaAllocator::IsDiskHotPluggab"...
0x180021361  mov     qword ptr [rbp+290h+var_268], rbx
0x180021365  lea     r14, aSpralloc; "SPRALLOC"
0x18002136c  mov     qword ptr [rbp+290h+var_268+8], r14
0x180021370  mov     dword ptr [rbp+290h+var_258], 73Ah
0x180021377  mov     r13d, 2
0x18002137d  mov     dword ptr [rbp+290h+var_258+4], r13d
0x180021381  mov     dword ptr [rbp+290h+var_258+8], 0FFh
0x180021388  xor     esi, esi
0x18002138a  mov     [rbp+290h+var_1D0], 1000000h
0x180021394  xor     edx, edx; Val
0x180021396  lea     r8d, [r13+76h]; Size
0x18002139a  lea     rcx, [rbp+290h+var_248]; void *
0x18002139e  call    memset_0
0x1800213a3  xor     r8d, r8d
0x1800213a6  lea     rdx, [rbp+290h+var_270]
0x1800213aa  lea     rcx, [rbp+290h+var_1C0]
0x1800213b1  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800213b6  nop
0x1800213b7  mov     dword ptr [rsp+390h+cb], esi
0x1800213bb  mov     [rsp+390h+var_330], 1
0x1800213c3  xor     eax, eax
0x1800213c5  mov     [rbp+290h+var_A8], rax
0x1800213cc  mov     [rbp+290h+var_A0], eax
0x1800213d2  mov     [rbp+290h+var_278], esi
0x1800213d5  xorps   xmm0, xmm0
0x1800213d8  movups  [rbp+290h+var_98], xmm0
0x1800213df  movups  [rbp+290h+var_88], xmm0
0x1800213e6  xorps   xmm1, xmm1
0x1800213e9  movups  [rbp+290h+var_78], xmm1
0x1800213f0  movups  [rbp+290h+var_68], xmm1
0x1800213f7  movups  [rbp+290h+var_58], xmm1
0x1800213fe  mov     dword ptr [rbp+290h+var_98], 20h ; ' '
0x180021408  mov     [rsp+390h+var_370], rsi
0x18002140d  xor     r9d, r9d
0x180021410  xor     r8d, r8d
0x180021413  xor     edx, edx
0x180021415  xor     ecx, ecx
0x180021417  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002141d  mov     r15, rax
0x180021420  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021424  jnz     short loc_180021475
0x180021426  mov     [rbp+290h+var_270], r12
0x18002142a  mov     qword ptr [rbp+290h+var_268], rbx
0x18002142e  mov     qword ptr [rbp+290h+var_268+8], r14
0x180021432  mov     dword ptr [rbp+290h+var_258], 753h
0x180021439  mov     dword ptr [rbp+290h+var_258+4], r13d
0x18002143d  mov     dword ptr [rbp+290h+var_258+8], 0FFh
0x180021444  mov     [rbp+290h+var_1D0], 1000000h
0x18002144e  xor     edx, edx; Val
0x180021450  lea     r8d, [r13+76h]; Size
0x180021454  lea     rcx, [rbp+290h+var_248]; void *
0x180021458  call    memset_0
0x18002145d  lea     r8, aDevobjcreatede; "DevObjCreateDeviceInfoList(NULL, NULL, "...
0x180021464  lea     rdx, [rbp+290h+var_270]
0x180021468  lea     rcx, [rbp+290h+var_1C0]
0x18002146f  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x180021475  mov     [rsp+390h+var_368], rsi
0x18002147a  mov     [rsp+390h+var_370], rsi
0x18002147f  mov     r9d, 12h
0x180021485  xor     r8d, r8d
0x180021488  lea     rdx, GUID_DEVINTERFACE_DISK
0x18002148f  mov     rcx, r15
0x180021492  call    cs:__imp_DevObjGetClassDevs
0x180021498  test    eax, eax
0x18002149a  jnz     short loc_1800214EB
0x18002149c  mov     [rbp+290h+var_270], r12
0x1800214a0  mov     qword ptr [rbp+290h+var_268], rbx
0x1800214a4  mov     qword ptr [rbp+290h+var_268+8], r14
0x1800214a8  mov     dword ptr [rbp+290h+var_258], 75Dh
0x1800214af  mov     dword ptr [rbp+290h+var_258+4], r13d
0x1800214b3  mov     dword ptr [rbp+290h+var_258+8], 0FFh
0x1800214ba  mov     [rbp+290h+var_1D0], 1000000h
0x1800214c4  xor     edx, edx; Val
0x1800214c6  lea     r8d, [rax+78h]; Size
0x1800214ca  lea     rcx, [rbp+290h+var_248]; void *
0x1800214ce  call    memset_0
0x1800214d3  lea     r8, aDevobjgetclass; "DevObjGetClassDevs(&, NULL, NULL, DOGCF"...
0x1800214da  lea     rdx, [rbp+290h+var_270]
0x1800214de  lea     rcx, [rbp+290h+var_1C0]
0x1800214e5  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1800214eb  mov     rbx, rsi
0x1800214ee  mov     r13b, sil
0x1800214f1  mov     r14d, esi
0x1800214f4  lea     rax, [rbp+290h+var_98]
0x1800214fb  mov     [rsp+390h+var_370], rax
0x180021500  mov     r9d, r14d
0x180021503  lea     r8, GUID_DEVINTERFACE_DISK
0x18002150a  xor     edx, edx
0x18002150c  mov     rcx, r15
0x18002150f  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180021515  test    eax, eax
0x180021517  jz      loc_1800219F5
0x18002151d  xorps   xmm0, xmm0
0x180021520  movups  [rbp+290h+var_78], xmm0
0x180021527  movups  [rbp+290h+var_68], xmm0
0x18002152e  movups  [rbp+290h+var_58], xmm0
0x180021535  mov     dword ptr [rbp+290h+var_78], 30h ; '0'
0x18002153f  test    rbx, rbx
0x180021542  jz      short loc_18002154D
0x180021544  mov     rcx, rbx; pv
0x180021547  call    cs:__imp_CoTaskMemFree
0x18002154d  mov     [rsp+390h+var_368], rsi
0x180021552  lea     rax, [rsp+390h+cb]
0x180021557  mov     [rsp+390h+var_370], rax
0x18002155c  xor     r9d, r9d
0x18002155f  xor     r8d, r8d
0x180021562  lea     rdx, [rbp+290h+var_98]
0x180021569  mov     rcx, r15
0x18002156c  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180021572  mov     ecx, dword ptr [rsp+390h+cb]; cb
0x180021576  call    cs:__imp_CoTaskMemAlloc
0x18002157c  mov     rbx, rax
0x18002157f  test    rax, rax
0x180021582  jz      loc_180021987
0x180021588  mov     dword ptr [rax], 8
0x18002158e  lea     rax, [rbp+290h+var_78]
0x180021595  mov     [rsp+390h+var_368], rax
0x18002159a  mov     [rsp+390h+var_370], rsi
0x18002159f  mov     r9d, dword ptr [rsp+390h+cb]
0x1800215a4  mov     r8, rbx
0x1800215a7  lea     rdx, [rbp+290h+var_98]
0x1800215ae  mov     rcx, r15
0x1800215b1  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800215b7  test    eax, eax
0x1800215b9  jz      loc_1800218F2
0x1800215bf  mov     [rbp+290h+var_270], rsi
0x1800215c3  mov     [rbp+290h+var_248], si
0x1800215c7  mov     [rbp+290h+var_244], rsi
0x1800215cb  mov     [rbp+290h+var_238], rsi
0x1800215cf  mov     [rbp+290h+var_230], rsi
0x1800215d3  mov     [rbp+290h+var_228], esi
0x1800215d6  mov     [rbp+290h+var_220], rsi
0x1800215da  mov     [rbp+290h+var_218], si
0x1800215de  mov     [rbp+290h+var_208], rsi
0x1800215e5  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x1800215ec  mov     [rbp+290h+var_210], rax
0x1800215f3  xorps   xmm0, xmm0
0x1800215f6  movups  [rbp+290h+var_268], xmm0
0x1800215fa  movups  [rbp+290h+var_258], xmm0
0x1800215fe  lea     r12, [rbx+4]
0x180021602  mov     [rsp+390h+var_350], 80h
0x18002160a  mov     dword ptr [rsp+390h+var_360], 80000000h
0x180021612  mov     dword ptr [rsp+390h+var_368], esi
0x180021616  mov     byte ptr [rsp+390h+var_370], sil
0x18002161b  xor     r9d, r9d
0x18002161e  mov     r8, r12
0x180021621  lea     rdx, [rbp+290h+var_1C0]
0x180021628  lea     rcx, [rbp+290h+var_270]
0x18002162c  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x180021631  mov     [rbp+290h+var_1B8], eax
0x180021637  test    eax, eax
0x180021639  js      loc_1800217E6
0x18002163f  mov     [rsp+390h+var_360], rsi
0x180021644  mov     byte ptr [rsp+390h+var_368], sil
0x180021649  mov     dword ptr [rsp+390h+var_370], esi
0x18002164d  xor     r9d, r9d
0x180021650  mov     r8d, 2D1080h
0x180021656  lea     rdx, [rbp+290h+var_1C0]
0x18002165d  lea     rcx, [rbp+290h+var_270]
0x180021661  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x180021666  mov     [rbp+290h+var_1B8], eax
0x18002166c  test    eax, eax
0x18002166e  jns     short loc_1800216E7
0x180021670  lea     rax, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x180021677  mov     [rbp+290h+var_150], rax
0x18002167e  lea     rax, aCvssdiffareaal_0; "CVssDiffAreaAllocator::IsDiskHotPluggab"...
0x180021685  mov     [rbp+290h+var_148], rax
0x18002168c  lea     rax, aSpralloc; "SPRALLOC"
0x180021693  mov     [rbp+290h+var_140], rax
0x18002169a  mov     [rbp+290h+var_138], 7ADh
0x1800216a4  mov     [rbp+290h+var_134], 2
0x1800216ae  mov     [rbp+290h+var_130], 0FFh
0x1800216b8  mov     [rbp+290h+var_B0], 1000000h
0x1800216c2  xor     edx, edx; Val
0x1800216c4  lea     r8d, [rdx+78h]; Size
0x1800216c8  lea     rcx, [rbp+290h+var_128]; void *
0x1800216cf  call    memset_0
0x1800216d4  lea     r8, aUnableToGetThe_0; "Unable to get the disk number of %s"
0x1800216db  lea     rdx, [rbp+290h+var_150]
0x1800216e2  jmp     loc_180021840
0x1800216e7  xor     eax, eax
0x1800216e9  mov     [rbp+290h+var_A8], rax
0x1800216f0  mov     [rbp+290h+var_A0], eax
0x1800216f6  lea     r8, [rbp+290h+var_A8]
0x1800216fd  lea     rdx, [rbp+290h+var_1C0]
0x180021704  lea     rcx, [rbp+290h+var_270]
0x180021708  call    ??$Unpack@U_STORAGE_DEVICE_NUMBER@@@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAU_STORAGE_DEVICE_NUMBER@@K_N@Z; CVssIOCTLChannel::Unpack<_STORAGE_DEVICE_NUMBER>(CVssFunctionTracer &,_STORAGE_DEVICE_NUMBER *,ulong,bool)
0x18002170d  lea     rcx, [rbp+290h+var_270]; this
0x180021711  call    ?Close@CVssIOCTLChannel@@QEAAXXZ; CVssIOCTLChannel::Close(void)
0x180021716  nop
0x180021717  cmp     dword ptr [rbp+290h+var_A8+4], edi
0x18002171d  jnz     loc_180021850
0x180021723  lea     rcx, [rbp+290h+var_270]; this
0x180021727  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x18002172c  lea     r14, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x180021733  mov     [rsp+390h+var_320], r14
0x180021738  lea     rax, aCvssdiffareaal_0; "CVssDiffAreaAllocator::IsDiskHotPluggab"...
0x18002173f  mov     [rsp+390h+var_318], rax
0x180021744  lea     rax, aSpralloc; "SPRALLOC"
0x18002174b  mov     [rbp+290h+var_310], rax
0x18002174f  mov     [rbp+290h+var_308], 7CDh
0x180021756  mov     [rbp+290h+var_304], 2
0x18002175d  mov     [rbp+290h+var_300], 0FFh
0x180021764  mov     [rbp+290h+var_280], 1000000h
0x18002176b  xor     edx, edx; Val
0x18002176d  lea     r8d, [rdx+78h]; Size
0x180021771  lea     rcx, [rbp+290h+var_2F8]; void *
0x180021775  call    memset_0
0x18002177a  mov     r9d, edi
0x18002177d  lea     r8, aFoundDeviceMat; "Found device matching disk number %d"
0x180021784  lea     rdx, [rsp+390h+var_320]
0x180021789  lea     rcx, [rbp+290h+var_1C0]
0x180021790  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180021795  lea     rax, [rbp+290h+var_278]
0x180021799  mov     [rsp+390h+var_360], rax
0x18002179e  mov     dword ptr [rsp+390h+var_368], 4
0x1800217a6  lea     rax, [rsp+390h+var_330]
0x1800217ab  mov     [rsp+390h+var_370], rax
0x1800217b0  xor     r9d, r9d
0x1800217b3  lea     r8d, [r9+1Fh]
0x1800217b7  lea     rdx, [rbp+290h+var_78]
0x1800217be  mov     rcx, r15
0x1800217c1  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x1800217c7  test    eax, eax
0x1800217c9  jnz     loc_1800218DF
0x1800217cf  call    cs:__imp_GetLastError
0x1800217d5  mov     esi, eax
0x1800217d7  test    eax, eax
0x1800217d9  jg      loc_180021861
0x1800217df  mov     edi, eax
0x1800217e1  jmp     loc_18002186A
0x1800217e6  lea     rax, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x1800217ed  mov     [rsp+390h+var_320], rax
0x1800217f2  lea     rax, aCvssdiffareaal_0; "CVssDiffAreaAllocator::IsDiskHotPluggab"...
0x1800217f9  mov     [rsp+390h+var_318], rax
0x1800217fe  lea     rax, aSpralloc; "SPRALLOC"
0x180021805  mov     [rbp+290h+var_310], rax
0x180021809  mov     [rbp+290h+var_308], 7BFh
0x180021810  mov     [rbp+290h+var_304], 2
0x180021817  mov     [rbp+290h+var_300], 0FFh
0x18002181e  mov     [rbp+290h+var_280], 1000000h
0x180021825  xor     edx, edx; Val
0x180021827  lea     r8d, [rdx+78h]; Size
0x18002182b  lea     rcx, [rbp+290h+var_2F8]; void *
0x18002182f  call    memset_0
0x180021834  lea     r8, aUnableToOpenAn; "Unable to Open an IOCTL channel to %s"
0x18002183b  lea     rdx, [rsp+390h+var_320]
0x180021840  mov     r9, r12
0x180021843  lea     rcx, [rbp+290h+var_1C0]
0x18002184a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002184f  nop
0x180021850  lea     rcx, [rbp+290h+var_270]; this
0x180021854  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x180021859  inc     r14d
0x18002185c  jmp     loc_1800214F4
0x180021861  movzx   edi, si
0x180021864  or      edi, 80070000h
0x18002186a  mov     [rbp+290h+var_1B8], edi
0x180021870  mov     [rsp+390h+var_320], r14
0x180021875  lea     rax, aCvssdiffareaal_0; "CVssDiffAreaAllocator::IsDiskHotPluggab"...
0x18002187c  mov     [rsp+390h+var_318], rax
0x180021881  lea     rax, aSpralloc; "SPRALLOC"
0x180021888  mov     [rbp+290h+var_310], rax
0x18002188c  mov     [rbp+290h+var_308], 7DAh
0x180021893  mov     [rbp+290h+var_304], 2
0x18002189a  mov     [rbp+290h+var_300], 0FFh
0x1800218a1  mov     [rbp+290h+var_280], 1000000h
0x1800218a8  xor     edx, edx; Val
0x1800218aa  lea     r8d, [rdx+78h]; Size
0x1800218ae  lea     rcx, [rbp+290h+var_2F8]; void *
0x1800218b2  call    memset_0
0x1800218b7  mov     dword ptr [rsp+390h+var_368], edi
0x1800218bb  mov     dword ptr [rsp+390h+var_370], esi
0x1800218bf  mov     r9, r12
0x1800218c2  lea     r8, aErrorInDevobjg; "Error in DevObjGetDeviceRegistryPropert"...
0x1800218c9  lea     rdx, [rsp+390h+var_320]
0x1800218ce  lea     rcx, [rbp+290h+var_1C0]
0x1800218d5  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800218da  jmp     loc_180021B03
0x1800218df  cmp     [rsp+390h+var_330], 1
0x1800218e4  jz      loc_180021B03
0x1800218ea  mov     r13b, 1
  ... truncated ...
```

# CVssDiffAreaAllocator::GetHotPluggableAndSectorSize(ushort *,bool *,ulong *)

- ea: `0x180020638`
- end: `0x180020ba8`
- name: `?GetHotPluggableAndSectorSize@CVssDiffAreaAllocator@@AEAAXPEAGPEA_NPEAK@Z`
- size: `1392`
- prototype: `void __fastcall(CVssDiffAreaAllocator *this, unsigned __int16 *, bool *, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x1800200c0`
- `0x180021bc4`

## callees

- `0x180001580`
- `0x18000212c`
- `0x1800039d8`
- `0x180003de8`
- `0x18000610c`
- `0x180007604`
- `0x18000dc40`
- `0x180020638`
- `0x18002131c`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x1800367b8`
- `0x180037080`

## string_xrefs

- `0x1800207b3`: `Failure of StringCchCopy to copy the volume GUID, HRESULT 0x%08lx`
- `0x180020855`: `Fail to open IOCTL channel on volume %s. Assume not hot pluggable, default to 0 sector size.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssDiffAreaAllocator::GetHotPluggableAndSectorSize(
        CVssDiffAreaAllocator *this,
        unsigned __int16 *a2,
        bool *a3,
        unsigned int *a4)
{
  __int64 v7; // rax
  int v8; // ebx
  __int64 v9; // r9
  bool IsDiskHotPluggable; // si
  _DWORD *v11; // rbx
  unsigned int v12; // r14d
  CVssDiffAreaAllocator *v13; // rcx
  unsigned int i; // edi
  unsigned int v15; // ebx
  _DWORD *v16; // rax
  const wchar_t *v17; // r9
  int v18; // [rsp+20h] [rbp-E0h]
  char v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+20h] [rbp-E0h]
  _DWORD *v21; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v22; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v23; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+70h] [rbp-90h]
  int v26; // [rsp+74h] [rbp-8Ch]
  int v27; // [rsp+78h] [rbp-88h]
  _BYTE v28[120]; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+F8h] [rbp-8h]
  __int64 v30; // [rsp+110h] [rbp+10h] BYREF
  __int128 v31; // [rsp+118h] [rbp+18h]
  __int128 v32; // [rsp+128h] [rbp+28h]
  __int16 v33; // [rsp+138h] [rbp+38h]
  __int64 v34; // [rsp+13Ch] [rbp+3Ch]
  __int64 v35; // [rsp+148h] [rbp+48h]
  __int64 v36; // [rsp+150h] [rbp+50h]
  int v37; // [rsp+158h] [rbp+58h]
  _DWORD *v38; // [rsp+160h] [rbp+60h]
  __int16 v39; // [rsp+168h] [rbp+68h]
  void **v40; // [rsp+170h] [rbp+70h]
  __int64 v41; // [rsp+178h] [rbp+78h]
  LPVOID v42; // [rsp+180h] [rbp+80h] BYREF
  int v43; // [rsp+188h] [rbp+88h]
  unsigned __int16 v44[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  v22 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
  v23 = L"CVssDiffAreaAllocator::GetHotPluggableAndSectorSize";
  v24 = L"SPRALLOC";
  v25 = 1767;
  v26 = 2;
  v27 = 255;
  v29 = 0x1000000;
  memset_0(v28, 0, sizeof(v28));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v42, (__int64)&v22, 0);
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v41 = 0;
  v40 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v31 = 0;
  v32 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( !a2 )
    goto LABEL_22;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( !v7 )
  {
LABEL_22:
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
    v23 = L"CVssDiffAreaAllocator::GetHotPluggableAndSectorSize";
    v24 = L"SPRALLOC";
    v25 = 1782;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    CVssFunctionTracer::Throw(&v42, &v22, 2147942487LL, L"NULL or empty parameter to GetHotPluggableAndSectorSize.");
  }
  memset_0(v44, 0, 0x20Au);
  v8 = StringCchCopyW(v44, 0x105u, a2);
  v43 = v8;
  if ( v8 < 0 )
  {
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
    v23 = L"CVssDiffAreaAllocator::GetHotPluggableAndSectorSize";
    v24 = L"SPRALLOC";
    v25 = 1793;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    v18 = v8;
    CVssFunctionTracer::TranslateGenericError(
      &v42,
      &v22,
      (unsigned int)v8,
      L"Failure of StringCchCopy to copy the volume GUID, HRESULT 0x%08lx",
      v18);
  }
  v19 = 0;
  LOBYTE(v9) = 1;
  v43 = CVssIOCTLChannel::Open(&v30, &v42, v44, v9, v19, 0, -1073741824);
  if ( v43 >= 0 )
  {
    IsDiskHotPluggable = 0;
    v43 = CVssIOCTLChannel::Call(&v30, (__int64)&v42, 0x560000u, 0, 0, 0);
    if ( v43 >= 0 )
    {
      v11 = v38;
      v38 = 0;
      v36 = 0;
      v37 = 0;
      v21 = v11;
      v12 = *v11;
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
      v23 = L"CVssDiffAreaAllocator::GetHotPluggableAndSectorSize";
      v24 = L"SPRALLOC";
      v25 = 1817;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Trace(&v42, &v22, L"Found %d extents.", v12);
      for ( i = 0; i < v12; IsDiskHotPluggable = CVssDiffAreaAllocator::IsDiskHotPluggable(v13, v11[6 * i++ + 2]) )
      {
        if ( IsDiskHotPluggable )
          break;
      }
      CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>::~CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>(&v21);
    }
    else
    {
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
      v23 = L"CVssDiffAreaAllocator::GetHotPluggableAndSectorSize";
      v24 = L"SPRALLOC";
      v25 = 1809;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Trace(
        &v42,
        &v22,
        L"IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS fails on volume %s. Assume not hot pluggable.",
        v44);
    }
    LODWORD(v34) = 0;
    LODWORD(v36) = 0;
    v43 = CVssIOCTLChannel::Call(&v30, (__int64)&v42, 0x70000u, 0, 0, 0);
    if ( v43 >= 0 )
    {
      v16 = v38;
      v38 = 0;
      v36 = 0;
      v37 = 0;
      v21 = v16;
      v15 = v16[5];
      CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>::~CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>(&v21);
    }
    else
    {
      v15 = 0;
      v22 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
      v23 = L"CVssDiffAreaAllocator::GetHotPluggableAndSectorSize";
      v24 = L"SPRALLOC";
      v25 = 1830;
      v26 = 2;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Trace(
        &v42,
        &v22,
        L"IOCTL_DISK_GET_DRIVE_GEOMETRY fails on volume %s. Default to 0 sector size.",
        v44);
    }
    *a3 = IsDiskHotPluggable;
    *a4 = v15;
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
    v23 = L"CVssDiffAreaAllocator::GetHotPluggableAndSectorSize";
    v24 = L"SPRALLOC";
    v25 = 1840;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    v17 = L"TRUE";
    if ( !*a3 )
      v17 = L"FALSE";
    LODWORD(v20) = v15;
    CVssFunctionTracer::Trace(&v42, &v22, L"Returning hotpluggable %s sectorsize %d", v17, v20);
  }
  else
  {
    v22 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
    v23 = L"CVssDiffAreaAllocator::GetHotPluggableAndSectorSize";
    v24 = L"SPRALLOC";
    v25 = 1801;
    v26 = 2;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    CVssFunctionTracer::Trace(
      &v42,
      &v22,
      L"Fail to open IOCTL channel on volume %s. Assume not hot pluggable, default to 0 sector size.",
      v44);
  }
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v30);
  CVssFunctionTracer::~CVssFunctionTracer(&v42);
}

```

## disassembly

```asm
0x180020638  mov     [rsp-8+arg_0], rbx
0x18002063d  push    rbp
0x18002063e  push    rsi
0x18002063f  push    rdi
0x180020640  push    r12
0x180020642  push    r13
0x180020644  push    r14
0x180020646  push    r15
0x180020648  lea     rbp, [rsp-310h]
0x180020650  sub     rsp, 410h
0x180020657  mov     rax, cs:__security_cookie
0x18002065e  xor     rax, rsp
0x180020661  mov     [rbp+340h+var_40], rax
0x180020668  mov     r12, r9
0x18002066b  mov     r15, r8
0x18002066e  mov     rbx, rdx
0x180020671  lea     rdi, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x180020678  mov     [rsp+440h+var_3E8], rdi
0x18002067d  lea     r14, aCvssdiffareaal_4; "CVssDiffAreaAllocator::GetHotPluggableA"...
0x180020684  mov     [rsp+440h+var_3E0], r14
0x180020689  lea     rsi, aSpralloc; "SPRALLOC"
0x180020690  mov     [rsp+440h+var_3D8], rsi
0x180020695  mov     [rsp+440h+var_3D0], 6E7h
0x18002069d  mov     [rsp+440h+var_3CC], 2
0x1800206a5  mov     [rsp+440h+var_3C8], 0FFh
0x1800206ad  xor     r13d, r13d
0x1800206b0  mov     [rbp+340h+var_348], 1000000h
0x1800206b7  xor     edx, edx; Val
0x1800206b9  lea     r8d, [r13+78h]; Size
0x1800206bd  lea     rcx, [rbp+340h+var_3C0]; void *
0x1800206c1  call    memset_0
0x1800206c6  xor     r8d, r8d
0x1800206c9  lea     rdx, [rsp+440h+var_3E8]
0x1800206ce  lea     rcx, [rbp+340h+var_2C0]
0x1800206d5  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800206da  nop
0x1800206db  mov     [rbp+340h+var_330], r13
0x1800206df  mov     [rbp+340h+var_308], r13w
0x1800206e4  mov     [rbp+340h+var_304], r13
0x1800206e8  mov     [rbp+340h+var_2F8], r13
0x1800206ec  mov     [rbp+340h+var_2F0], r13
0x1800206f0  mov     [rbp+340h+var_2E8], r13d
0x1800206f4  mov     [rbp+340h+var_2E0], r13
0x1800206f8  mov     [rbp+340h+var_2D8], r13w
0x1800206fd  mov     [rbp+340h+var_2C8], r13
0x180020701  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180020708  mov     [rbp+340h+var_2D0], rax
0x18002070c  xorps   xmm0, xmm0
0x18002070f  movups  [rbp+340h+var_328], xmm0
0x180020713  movups  [rbp+340h+var_318], xmm0
0x180020717  mov     [r15], r13b
0x18002071a  mov     [r12], r13d
0x18002071e  test    rbx, rbx
0x180020721  jz      loc_180020B4C
0x180020727  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002072b  inc     rax
0x18002072e  cmp     [rbx+rax*2], r13w
0x180020733  jnz     short loc_18002072B
0x180020735  test    rax, rax
0x180020738  jz      loc_180020B4C
0x18002073e  xor     edx, edx; Val
0x180020740  mov     r8d, 20Ah; Size
0x180020746  lea     rcx, [rbp+340h+var_250]; void *
0x18002074d  call    memset_0
0x180020752  mov     r8, rbx; unsigned __int16 *
0x180020755  mov     edx, 105h; unsigned __int64
0x18002075a  lea     rcx, [rbp+340h+var_250]; unsigned __int16 *
0x180020761  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180020766  mov     ebx, eax
0x180020768  mov     [rbp+340h+var_2B8], eax
0x18002076e  test    eax, eax
0x180020770  jns     short loc_1800207CF
0x180020772  mov     [rsp+440h+var_3E8], rdi
0x180020777  mov     [rsp+440h+var_3E0], r14
0x18002077c  mov     [rsp+440h+var_3D8], rsi
0x180020781  mov     [rsp+440h+var_3D0], 701h
0x180020789  mov     [rsp+440h+var_3CC], 2
0x180020791  mov     [rsp+440h+var_3C8], 0FFh
0x180020799  mov     [rbp+340h+var_348], 1000000h
0x1800207a0  xor     edx, edx; Val
0x1800207a2  lea     r8d, [rdx+78h]; Size
0x1800207a6  lea     rcx, [rbp+340h+var_3C0]; void *
0x1800207aa  call    memset_0
0x1800207af  mov     dword ptr [rsp+440h+var_420], ebx
0x1800207b3  lea     r9, aFailureOfStrin; "Failure of StringCchCopy to copy the vo"...
0x1800207ba  mov     r8d, ebx
0x1800207bd  lea     rdx, [rsp+440h+var_3E8]
0x1800207c2  lea     rcx, [rbp+340h+var_2C0]
0x1800207c9  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1800207cf  mov     [rsp+440h+var_400], 80h
0x1800207d7  mov     dword ptr [rsp+440h+var_410], 0C0000000h
0x1800207df  mov     [rsp+440h+var_418], r13d
0x1800207e4  mov     byte ptr [rsp+440h+var_420], r13b
0x1800207e9  mov     r9b, 1
0x1800207ec  lea     r8, [rbp+340h+var_250]
0x1800207f3  lea     rdx, [rbp+340h+var_2C0]
0x1800207fa  lea     rcx, [rbp+340h+var_330]
0x1800207fe  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x180020803  mov     [rbp+340h+var_2B8], eax
0x180020809  test    eax, eax
0x18002080b  jns     loc_1800208AE
0x180020811  mov     [rsp+440h+var_3E8], rdi
0x180020816  mov     [rsp+440h+var_3E0], r14
0x18002081b  mov     [rsp+440h+var_3D8], rsi
0x180020820  mov     [rsp+440h+var_3D0], 709h
0x180020828  mov     [rsp+440h+var_3CC], 2
0x180020830  mov     [rsp+440h+var_3C8], 0FFh
0x180020838  mov     [rbp+340h+var_348], 1000000h
0x18002083f  xor     edx, edx; Val
0x180020841  lea     r8d, [rdx+78h]; Size
0x180020845  lea     rcx, [rbp+340h+var_3C0]; void *
0x180020849  call    memset_0
0x18002084e  lea     r9, [rbp+340h+var_250]
0x180020855  lea     r8, aFailToOpenIoct; "Fail to open IOCTL channel on volume %s"...
0x18002085c  lea     rdx, [rsp+440h+var_3E8]
0x180020861  lea     rcx, [rbp+340h+var_2C0]
0x180020868  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002086d  nop
0x18002086e  lea     rcx, [rbp+340h+var_330]; this
0x180020872  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x180020877  nop
0x180020878  lea     rcx, [rbp+340h+var_2C0]; this
0x18002087f  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180020884  mov     rcx, [rbp+340h+var_40]
0x18002088b  xor     rcx, rsp; StackCookie
0x18002088e  call    __security_check_cookie
0x180020893  mov     rbx, [rsp+440h+arg_0]
0x18002089b  add     rsp, 410h
0x1800208a2  pop     r15
0x1800208a4  pop     r14
0x1800208a6  pop     r13
0x1800208a8  pop     r12
0x1800208aa  pop     rdi
0x1800208ab  pop     rsi
0x1800208ac  pop     rbp
0x1800208ad  retn
0x1800208ae  mov     sil, r13b
0x1800208b1  mov     [rsp+440h+var_410], r13
0x1800208b6  mov     byte ptr [rsp+440h+var_418], r13b
0x1800208bb  mov     dword ptr [rsp+440h+var_420], r13d
0x1800208c0  xor     r9d, r9d
0x1800208c3  mov     r8d, 560000h
0x1800208c9  lea     rdx, [rbp+340h+var_2C0]
0x1800208d0  lea     rcx, [rbp+340h+var_330]
0x1800208d4  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x1800208d9  mov     [rbp+340h+var_2B8], eax
0x1800208df  test    eax, eax
0x1800208e1  jns     short loc_18002094B
0x1800208e3  mov     [rsp+440h+var_3E8], rdi
0x1800208e8  mov     [rsp+440h+var_3E0], r14
0x1800208ed  lea     rax, aSpralloc; "SPRALLOC"
0x1800208f4  mov     [rsp+440h+var_3D8], rax
0x1800208f9  mov     [rsp+440h+var_3D0], 711h
0x180020901  mov     [rsp+440h+var_3CC], 2
0x180020909  mov     [rsp+440h+var_3C8], 0FFh
0x180020911  mov     [rbp+340h+var_348], 1000000h
0x180020918  xor     edx, edx; Val
0x18002091a  lea     r8d, [rdx+78h]; Size
0x18002091e  lea     rcx, [rbp+340h+var_3C0]; void *
0x180020922  call    memset_0
0x180020927  lea     r9, [rbp+340h+var_250]
0x18002092e  lea     r8, aIoctlVolumeGet; "IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS fa"...
0x180020935  lea     rdx, [rsp+440h+var_3E8]
0x18002093a  lea     rcx, [rbp+340h+var_2C0]
0x180020941  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180020946  jmp     loc_180020A07
0x18002094b  mov     rbx, [rbp+340h+var_2E0]
0x18002094f  mov     [rbp+340h+var_2E0], r13
0x180020953  mov     [rbp+340h+var_2F0], r13
0x180020957  mov     [rbp+340h+var_2E8], r13d
0x18002095b  mov     [rsp+440h+var_3F0], rbx
0x180020960  mov     r14d, [rbx]
0x180020963  mov     [rsp+440h+var_3E8], rdi
0x180020968  lea     rax, aCvssdiffareaal_4; "CVssDiffAreaAllocator::GetHotPluggableA"...
0x18002096f  mov     [rsp+440h+var_3E0], rax
0x180020974  lea     rax, aSpralloc; "SPRALLOC"
0x18002097b  mov     [rsp+440h+var_3D8], rax
0x180020980  mov     [rsp+440h+var_3D0], 719h
0x180020988  mov     [rsp+440h+var_3CC], 2
0x180020990  mov     [rsp+440h+var_3C8], 0FFh
0x180020998  mov     [rbp+340h+var_348], 1000000h
0x18002099f  xor     edx, edx; Val
0x1800209a1  lea     r8d, [rdx+78h]; Size
0x1800209a5  lea     rcx, [rbp+340h+var_3C0]; void *
0x1800209a9  call    memset_0
0x1800209ae  mov     r9d, r14d
0x1800209b1  lea     r8, aFoundDExtents; "Found %d extents."
0x1800209b8  lea     rdx, [rsp+440h+var_3E8]
0x1800209bd  lea     rcx, [rbp+340h+var_2C0]
0x1800209c4  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800209c9  mov     edi, r13d
0x1800209cc  test    r14d, r14d
0x1800209cf  jz      short loc_1800209EF
0x1800209d1  test    sil, sil
0x1800209d4  jnz     short loc_1800209EF
0x1800209d6  mov     eax, edi
0x1800209d8  lea     rdx, [rax+rax*2]
0x1800209dc  mov     edx, [rbx+rdx*8+8]; unsigned int
0x1800209e0  call    ?IsDiskHotPluggable@CVssDiffAreaAllocator@@AEAA_NK@Z; CVssDiffAreaAllocator::IsDiskHotPluggable(ulong)
0x1800209e5  mov     sil, al
0x1800209e8  inc     edi
0x1800209ea  cmp     edi, r14d
0x1800209ed  jb      short loc_1800209D1
0x1800209ef  lea     rcx, [rsp+440h+var_3F0]
0x1800209f4  call    ??1?$CVssMallocAutoPtr@U_FILE_FS_ATTRIBUTE_INFORMATION@@@@QEAA@XZ; CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>::~CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>(void)
0x1800209f9  lea     rdi, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x180020a00  lea     r14, aCvssdiffareaal_4; "CVssDiffAreaAllocator::GetHotPluggableA"...
0x180020a07  mov     dword ptr [rbp+340h+var_304], r13d
0x180020a0b  mov     dword ptr [rbp+340h+var_2F0], r13d
0x180020a0f  mov     [rsp+440h+var_410], r13
0x180020a14  mov     byte ptr [rsp+440h+var_418], r13b
0x180020a19  mov     dword ptr [rsp+440h+var_420], r13d
0x180020a1e  xor     r9d, r9d
0x180020a21  mov     r8d, 70000h
0x180020a27  lea     rdx, [rbp+340h+var_2C0]
0x180020a2e  lea     rcx, [rbp+340h+var_330]
0x180020a32  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x180020a37  mov     [rbp+340h+var_2B8], eax
0x180020a3d  test    eax, eax
0x180020a3f  jns     short loc_180020AA9
0x180020a41  mov     ebx, r13d
0x180020a44  mov     [rsp+440h+var_3E8], rdi
0x180020a49  mov     [rsp+440h+var_3E0], r14
0x180020a4e  lea     rax, aSpralloc; "SPRALLOC"
0x180020a55  mov     [rsp+440h+var_3D8], rax
0x180020a5a  mov     [rsp+440h+var_3D0], 726h
0x180020a62  mov     [rsp+440h+var_3CC], 2
0x180020a6a  mov     [rsp+440h+var_3C8], 0FFh
0x180020a72  mov     [rbp+340h+var_348], 1000000h
0x180020a79  xor     edx, edx; Val
0x180020a7b  lea     r8d, [rdx+78h]; Size
0x180020a7f  lea     rcx, [rbp+340h+var_3C0]; void *
0x180020a83  call    memset_0
0x180020a88  lea     r9, [rbp+340h+var_250]
0x180020a8f  lea     r8, aIoctlDiskGetDr; "IOCTL_DISK_GET_DRIVE_GEOMETRY fails on "...
0x180020a96  lea     rdx, [rsp+440h+var_3E8]
0x180020a9b  lea     rcx, [rbp+340h+var_2C0]
0x180020aa2  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180020aa7  jmp     short loc_180020ACB
0x180020aa9  mov     rax, [rbp+340h+var_2E0]
0x180020aad  mov     [rbp+340h+var_2E0], r13
0x180020ab1  mov     [rbp+340h+var_2F0], r13
0x180020ab5  mov     [rbp+340h+var_2E8], r13d
0x180020ab9  mov     [rsp+440h+var_3F0], rax
0x180020abe  mov     ebx, [rax+14h]
0x180020ac1  lea     rcx, [rsp+440h+var_3F0]
0x180020ac6  call    ??1?$CVssMallocAutoPtr@U_FILE_FS_ATTRIBUTE_INFORMATION@@@@QEAA@XZ; CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>::~CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>(void)
0x180020acb  mov     [r15], sil
0x180020ace  mov     [r12], ebx
0x180020ad2  mov     [rsp+440h+var_3E8], rdi
0x180020ad7  mov     [rsp+440h+var_3E0], r14
0x180020adc  lea     rax, aSpralloc; "SPRALLOC"
0x180020ae3  mov     [rsp+440h+var_3D8], rax
0x180020ae8  mov     [rsp+440h+var_3D0], 730h
0x180020af0  mov     [rsp+440h+var_3CC], 2
0x180020af8  mov     [rsp+440h+var_3C8], 0FFh
0x180020b00  mov     [rbp+340h+var_348], 1000000h
0x180020b07  xor     edx, edx; Val
0x180020b09  lea     r8d, [rdx+78h]; Size
0x180020b0d  lea     rcx, [rbp+340h+var_3C0]; void *
0x180020b11  call    memset_0
0x180020b16  lea     rax, aFalse; "FALSE"
0x180020b1d  lea     r9, aTrue; "TRUE"
0x180020b24  cmp     [r15], r13b
0x180020b27  cmovz   r9, rax
0x180020b2b  mov     dword ptr [rsp+440h+var_420], ebx
0x180020b2f  lea     r8, aReturningHotpl; "Returning hotpluggable %s sectorsize %d"
0x180020b36  lea     rdx, [rsp+440h+var_3E8]
0x180020b3b  lea     rcx, [rbp+340h+var_2C0]
0x180020b42  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180020b47  jmp     loc_18002086E
0x180020b4c  mov     [rsp+440h+var_3E8], rdi
0x180020b51  mov     [rsp+440h+var_3E0], r14
0x180020b56  mov     [rsp+440h+var_3D8], rsi
0x180020b5b  mov     [rsp+440h+var_3D0], 6F6h
0x180020b63  mov     [rsp+440h+var_3CC], 2
0x180020b6b  mov     [rsp+440h+var_3C8], 0FFh
0x180020b73  mov     [rbp+340h+var_348], 1000000h
0x180020b7a  xor     edx, edx; Val
0x180020b7c  lea     r8d, [rdx+78h]; Size
0x180020b80  lea     rcx, [rbp+340h+var_3C0]; void *
0x180020b84  call    memset_0
0x180020b89  lea     r9, aNullOrEmptyPar; "NULL or empty parameter to GetHotPlugga"...
0x180020b90  mov     r8d, 80070057h
0x180020b96  lea     rdx, [rsp+440h+var_3E8]
0x180020b9b  lea     rcx, [rbp+340h+var_2C0]
0x180020ba2  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```

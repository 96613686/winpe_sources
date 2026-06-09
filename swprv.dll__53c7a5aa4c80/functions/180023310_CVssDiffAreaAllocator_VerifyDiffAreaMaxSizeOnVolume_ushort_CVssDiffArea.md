# CVssDiffAreaAllocator::VerifyDiffAreaMaxSizeOnVolume(ushort *,CVssDiffArea *)

- ea: `0x180023310`
- end: `0x1800235d7`
- name: `?VerifyDiffAreaMaxSizeOnVolume@CVssDiffAreaAllocator@@AEAAXPEAGPEAVCVssDiffArea@@@Z`
- size: `711`
- prototype: `void __fastcall(CVssDiffAreaAllocator *__hidden this, LPCWSTR lpDirectoryName, struct CVssDiffArea *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180020c6c`

## callees

- `0x18000212c`
- `0x180003718`
- `0x180004a78`
- `0x18001dc3c`
- `0x18001e148`
- `0x18001f7f8`
- `0x180023310`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x1800377c4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1800233e0`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1800233e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800235a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800235a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssDiffAreaAllocator::VerifyDiffAreaMaxSizeOnVolume(
        CVssDiffAreaAllocator *this,
        LPCWSTR lpDirectoryName,
        struct CVssDiffArea *a3)
{
  void *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rdi
  union _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v11; // [rsp+38h] [rbp-C8h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  void **v14; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v16; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v17; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v18; // [rsp+70h] [rbp-90h]
  int v19; // [rsp+78h] [rbp-88h]
  int v20; // [rsp+7Ch] [rbp-84h]
  int v21; // [rsp+80h] [rbp-80h]
  _BYTE v22[120]; // [rsp+88h] [rbp-78h] BYREF
  int v23; // [rsp+100h] [rbp+0h]
  _QWORD v24[4]; // [rsp+108h] [rbp+8h] BYREF
  int v25; // [rsp+128h] [rbp+28h]
  char v26; // [rsp+12Ch] [rbp+2Ch]
  int v27; // [rsp+130h] [rbp+30h]
  __int16 v28; // [rsp+134h] [rbp+34h]
  __int64 v29; // [rsp+138h] [rbp+38h] BYREF
  LPVOID v30[22]; // [rsp+140h] [rbp+40h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+218h] [rbp+118h] BYREF

  v16 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
  v17 = L"CVssDiffAreaAllocator::VerifyDiffAreaMaxSizeOnVolume";
  v18 = L"SPRALLOC";
  v19 = 457;
  v20 = 2;
  v21 = 255;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v30, (__int64)&v16, 0);
  pv = 0;
  v14 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  FreeBytesAvailableToCaller.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  v11 = 0;
  v29 = 0;
  v13 = 0;
  if ( !GetDiskFreeSpaceExW(lpDirectoryName, &FreeBytesAvailableToCaller, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
  {
    v16 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
    v17 = L"CVssDiffAreaAllocator::VerifyDiffAreaMaxSizeOnVolume";
    v18 = L"SPRALLOC";
    v19 = 481;
    v20 = 2;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    CVssFunctionTracer::TranslateWin32Error(v30, &v16, L"GetDiskFreeSpaceEx(%s)", lpDirectoryName);
  }
  CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom((__int64)&v14, lpDirectoryName);
  v6 = pv;
  pv = 0;
  v24[0] = v6;
  v24[1] = TotalNumberOfBytes.QuadPart;
  v24[2] = FreeBytesAvailableToCaller.QuadPart;
  v24[3] = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  CVssDiffArea::GetDiffAreaSizes(a3, &v11, &v29, &v13);
  v7 = CVssDiffAreaAllocator::CalculateDiffAreaMaxSize(this, (struct CVssDiffAreaCandidate *)v24);
  v8 = v7;
  if ( v7 != -1 )
  {
    v9 = v13;
    if ( v13 < v7 )
    {
      v16 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
      v17 = L"CVssDiffAreaAllocator::VerifyDiffAreaMaxSizeOnVolume";
      v18 = L"SPRALLOC";
      v19 = 509;
      v20 = 2;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::Trace(
        v30,
        &v16,
        L"Not enough space in the diff area on %s, increasing to the size calculated by the default formula.",
        lpDirectoryName);
      v16 = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
      v17 = L"CVssDiffAreaAllocator::VerifyDiffAreaMaxSizeOnVolume";
      v18 = L"SPRALLOC";
      v19 = 510;
      v20 = 2;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::Trace(v30, &v16, L"DiffArea Expected: %I64u  DiffArea Max: %I64u", v8, v9);
      CVssDiffArea::ChangeDiffAreaMaximumSize(a3, v8, 0);
    }
  }
  CoTaskMemFree(v6);
  CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v14);
  CVssFunctionTracer::~CVssFunctionTracer(v30);
}

```

## disassembly

```asm
0x180023310  push    rbp
0x180023312  push    rbx
0x180023313  push    rsi
0x180023314  push    rdi
0x180023315  push    r12
0x180023317  push    r13
0x180023319  push    r14
0x18002331b  push    r15
0x18002331d  lea     rbp, [rsp-0B8h]
0x180023325  sub     rsp, 1B8h
0x18002332c  mov     r15, r8
0x18002332f  mov     r14, rdx
0x180023332  mov     rbx, rcx
0x180023335  lea     r13, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002333c  mov     [rsp+1F0h+var_190], r13
0x180023341  lea     rdi, aCvssdiffareaal_9; "CVssDiffAreaAllocator::VerifyDiffAreaMa"...
0x180023348  mov     [rsp+1F0h+var_188], rdi
0x18002334d  lea     rsi, aSpralloc; "SPRALLOC"
0x180023354  mov     [rsp+1F0h+var_180], rsi
0x180023359  mov     [rsp+1F0h+var_178], 1C9h
0x180023361  mov     [rsp+1F0h+var_174], 2
0x180023369  mov     [rbp+0F0h+var_170], 0FFh
0x180023370  xor     r12d, r12d
0x180023373  mov     [rbp+0F0h+var_F0], 1000000h
0x18002337a  xor     edx, edx; Val
0x18002337c  lea     r8d, [r12+78h]; Size
0x180023381  lea     rcx, [rbp+0F0h+var_168]; void *
0x180023385  call    memset_0
0x18002338a  xor     r8d, r8d
0x18002338d  lea     rdx, [rsp+1F0h+var_190]
0x180023392  lea     rcx, [rbp+0F0h+var_B0]
0x180023396  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18002339b  nop
0x18002339c  mov     [rsp+1F0h+pv], r12
0x1800233a1  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x1800233a8  mov     [rsp+1F0h+var_1A0], rax
0x1800233ad  mov     qword ptr [rsp+1F0h+FreeBytesAvailableToCaller], r12
0x1800233b2  mov     qword ptr [rbp+0F0h+TotalNumberOfBytes], r12
0x1800233b9  mov     qword ptr [rsp+1F0h+TotalNumberOfFreeBytes], r12
0x1800233be  mov     [rsp+1F0h+var_1B8], r12
0x1800233c3  mov     [rbp+0F0h+var_B8], r12
0x1800233c7  mov     [rsp+1F0h+var_1A8], r12
0x1800233cc  lea     r9, [rsp+1F0h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1800233d1  lea     r8, [rbp+0F0h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x1800233d8  lea     rdx, [rsp+1F0h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x1800233dd  mov     rcx, r14; lpDirectoryName
0x1800233e0  call    cs:__imp_GetDiskFreeSpaceExW
0x1800233e6  test    eax, eax
0x1800233e8  jnz     short loc_180023440
0x1800233ea  mov     [rsp+1F0h+var_190], r13
0x1800233ef  mov     [rsp+1F0h+var_188], rdi
0x1800233f4  mov     [rsp+1F0h+var_180], rsi
0x1800233f9  mov     [rsp+1F0h+var_178], 1E1h
0x180023401  mov     [rsp+1F0h+var_174], 2
0x180023409  mov     [rbp+0F0h+var_170], 0FFh
0x180023410  mov     [rbp+0F0h+var_F0], 1000000h
0x180023417  xor     edx, edx; Val
0x180023419  lea     r8d, [r12+78h]; Size
0x18002341e  lea     rcx, [rbp+0F0h+var_168]; void *
0x180023422  call    memset_0
0x180023427  mov     r9, r14
0x18002342a  lea     r8, aGetdiskfreespa; "GetDiskFreeSpaceEx(%s)"
0x180023431  lea     rdx, [rsp+1F0h+var_190]
0x180023436  lea     rcx, [rbp+0F0h+var_B0]
0x18002343a  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x180023440  mov     rdx, r14
0x180023443  lea     rcx, [rsp+1F0h+var_1A0]
0x180023448  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)
0x18002344d  mov     rsi, [rsp+1F0h+pv]
0x180023452  mov     [rsp+1F0h+pv], r12
0x180023457  mov     [rbp+0F0h+var_E8], rsi
0x18002345b  mov     eax, dword ptr [rbp+0F0h+TotalNumberOfBytes]
0x180023461  mov     dword ptr [rbp+0F0h+var_E0], eax
0x180023464  mov     eax, dword ptr [rbp+0F0h+TotalNumberOfBytes+4]
0x18002346a  mov     dword ptr [rbp+0F0h+var_E0+4], eax
0x18002346d  mov     eax, dword ptr [rsp+1F0h+FreeBytesAvailableToCaller]
0x180023471  mov     dword ptr [rbp+0F0h+var_D8], eax
0x180023474  mov     eax, dword ptr [rsp+1F0h+FreeBytesAvailableToCaller+4]
0x180023478  mov     dword ptr [rbp+0F0h+var_D8+4], eax
0x18002347b  mov     [rbp+0F0h+var_D0], r12
0x18002347f  mov     [rbp+0F0h+var_C8], r12d
0x180023483  mov     [rbp+0F0h+var_C4], r12b
0x180023487  mov     [rbp+0F0h+var_C0], r12d
0x18002348b  mov     [rbp+0F0h+var_BC], r12w
0x180023490  lea     r9, [rsp+1F0h+var_1A8]; __int64 *
0x180023495  lea     r8, [rbp+0F0h+var_B8]; __int64 *
0x180023499  lea     rdx, [rsp+1F0h+var_1B8]; __int64 *
0x18002349e  mov     rcx, r15; this
0x1800234a1  call    ?GetDiffAreaSizes@CVssDiffArea@@QEAAXAEA_J00@Z; CVssDiffArea::GetDiffAreaSizes(__int64 &,__int64 &,__int64 &)
0x1800234a6  lea     rdx, [rbp+0F0h+var_E8]; struct CVssDiffAreaCandidate *
0x1800234aa  mov     rcx, rbx; this
0x1800234ad  call    ?CalculateDiffAreaMaxSize@CVssDiffAreaAllocator@@AEAA_JPEAVCVssDiffAreaCandidate@@@Z; CVssDiffAreaAllocator::CalculateDiffAreaMaxSize(CVssDiffAreaCandidate *)
0x1800234b2  mov     rbx, rax
0x1800234b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800234b9  jz      loc_1800235A5
0x1800234bf  mov     rdi, [rsp+1F0h+var_1A8]
0x1800234c4  cmp     rdi, rax
0x1800234c7  jge     loc_1800235A5
0x1800234cd  mov     [rsp+1F0h+var_190], r13
0x1800234d2  lea     rax, aCvssdiffareaal_9; "CVssDiffAreaAllocator::VerifyDiffAreaMa"...
0x1800234d9  mov     [rsp+1F0h+var_188], rax
0x1800234de  lea     rax, aSpralloc; "SPRALLOC"
0x1800234e5  mov     [rsp+1F0h+var_180], rax
0x1800234ea  mov     [rsp+1F0h+var_178], 1FDh
0x1800234f2  mov     [rsp+1F0h+var_174], 2
0x1800234fa  mov     [rbp+0F0h+var_170], 0FFh
0x180023501  mov     [rbp+0F0h+var_F0], 1000000h
0x180023508  xor     edx, edx; Val
0x18002350a  lea     r8d, [rdx+78h]; Size
0x18002350e  lea     rcx, [rbp+0F0h+var_168]; void *
0x180023512  call    memset_0
0x180023517  mov     r9, r14
0x18002351a  lea     r8, aNotEnoughSpace; "Not enough space in the diff area on %s"...
0x180023521  lea     rdx, [rsp+1F0h+var_190]
0x180023526  lea     rcx, [rbp+0F0h+var_B0]
0x18002352a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002352f  mov     [rsp+1F0h+var_190], r13
0x180023534  lea     rax, aCvssdiffareaal_9; "CVssDiffAreaAllocator::VerifyDiffAreaMa"...
0x18002353b  mov     [rsp+1F0h+var_188], rax
0x180023540  lea     rax, aSpralloc; "SPRALLOC"
0x180023547  mov     [rsp+1F0h+var_180], rax
0x18002354c  mov     [rsp+1F0h+var_178], 1FEh
0x180023554  mov     [rsp+1F0h+var_174], 2
0x18002355c  mov     [rbp+0F0h+var_170], 0FFh
0x180023563  mov     [rbp+0F0h+var_F0], 1000000h
0x18002356a  xor     edx, edx; Val
0x18002356c  lea     r8d, [rdx+78h]; Size
0x180023570  lea     rcx, [rbp+0F0h+var_168]; void *
0x180023574  call    memset_0
0x180023579  mov     [rsp+1F0h+var_1D0], rdi
0x18002357e  mov     r9, rbx
0x180023581  lea     r8, aDiffareaExpect; "DiffArea Expected: %I64u  DiffArea Max:"...
0x180023588  lea     rdx, [rsp+1F0h+var_190]
0x18002358d  lea     rcx, [rbp+0F0h+var_B0]
0x180023591  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180023596  xor     r8d, r8d; bool
0x180023599  mov     rdx, rbx; __int64
0x18002359c  mov     rcx, r15; this
0x18002359f  call    ?ChangeDiffAreaMaximumSize@CVssDiffArea@@QEAAX_J_N@Z; CVssDiffArea::ChangeDiffAreaMaximumSize(__int64,bool)
0x1800235a4  nop
0x1800235a5  mov     rcx, rsi; pv
0x1800235a8  call    cs:__imp_CoTaskMemFree
0x1800235ae  nop
0x1800235af  lea     rcx, [rsp+1F0h+var_1A0]
0x1800235b4  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x1800235b9  nop
0x1800235ba  lea     rcx, [rbp+0F0h+var_B0]; this
0x1800235be  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800235c3  add     rsp, 1B8h
0x1800235ca  pop     r15
0x1800235cc  pop     r14
0x1800235ce  pop     r13
0x1800235d0  pop     r12
0x1800235d2  pop     rdi
0x1800235d3  pop     rsi
0x1800235d4  pop     rbx
0x1800235d5  pop     rbp
0x1800235d6  retn
```

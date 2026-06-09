# CVssQueuedSnapshot::LoadOriginalVolumeNameIoctl(CVssIOCTLChannel &,ushort * *)

- ea: `0x18001b380`
- end: `0x18001b656`
- name: `?LoadOriginalVolumeNameIoctl@CVssQueuedSnapshot@@SAJAEAVCVssIOCTLChannel@@PEAPEAG@Z`
- size: `726`
- prototype: `__int64 __fastcall(struct CVssIOCTLChannel *, LPVOID *)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18001c5dc`
- `0x18002b490`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180003de8`
- `0x180017284`
- `0x18001b034`
- `0x18001b380`
- `0x18001c208`
- `0x18001c294`
- `0x180033a8c`
- `0x180033c78`
- `0x180037080`
- `0x18003750c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b610`

## string_xrefs

- `0x18001b566`: `GetVolumeNameForVolumeMountPointW( %s, ...)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVssQueuedSnapshot::LoadOriginalVolumeNameIoctl(struct CVssIOCTLChannel *a1, LPVOID *a2)
{
  bool v4; // r9
  int v5; // edi
  signed int LastError; // eax
  unsigned int v7; // ebx
  LPVOID v8; // rbx
  unsigned int v9; // ebx
  LPVOID pv; // [rsp+40h] [rbp-588h] BYREF
  unsigned int v12; // [rsp+48h] [rbp-580h] BYREF
  const unsigned __int16 *v13; // [rsp+58h] [rbp-570h] BYREF
  const unsigned __int16 *v14; // [rsp+60h] [rbp-568h]
  const unsigned __int16 *v15; // [rsp+68h] [rbp-560h]
  int v16; // [rsp+70h] [rbp-558h]
  int v17; // [rsp+74h] [rbp-554h]
  int v18; // [rsp+78h] [rbp-550h]
  _BYTE v19[120]; // [rsp+80h] [rbp-548h] BYREF
  int v20; // [rsp+F8h] [rbp-4D0h]
  LPVOID v21; // [rsp+100h] [rbp-4C8h] BYREF
  int VolumeNameAnyFormat; // [rsp+108h] [rbp-4C0h]
  unsigned int v23; // [rsp+124h] [rbp-4A4h]
  _com_error *v24; // [rsp+170h] [rbp-458h] BYREF
  const std::exception *v25; // [rsp+178h] [rbp-450h] BYREF
  unsigned __int16 v26[264]; // [rsp+180h] [rbp-448h] BYREF
  unsigned __int16 v27[264]; // [rsp+390h] [rbp-238h] BYREF

  v13 = L"base\\stor\\vss\\modules\\softprv\\src\\persist.cxx";
  v14 = L"CVssQueuedSnapshot::LoadOriginalVolumeNameIoctl";
  v15 = L"SPRPERSC";
  v16 = 408;
  v17 = 2;
  v18 = 255;
  v20 = 0x1000000;
  memset_0(v19, 0, sizeof(v19));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v21, (__int64)&v13, 0);
  try
  {
    pv = 0;
    CVssIOCTLChannel::Call(a1, (__int64)&v21, 0x530190u, 1, 2, 0);
    CVssIOCTLChannel::UnpackSmallString(a1, (struct CVssFunctionTracer *)&v21, (unsigned __int16 **)&pv, v4);
    v5 = StringCchPrintfW(v26, 0x104u, L"%s%s\\", L"\\\\?\\GLOBALROOT", pv);
    VolumeNameAnyFormat = v5;
    if ( v5 < 0 )
    {
      v8 = pv;
      v13 = L"base\\stor\\vss\\modules\\softprv\\src\\persist.cxx";
      v14 = L"CVssQueuedSnapshot::LoadOriginalVolumeNameIoctl";
      v15 = L"SPRPERSC";
      v16 = 427;
      v17 = 2;
      v18 = 255;
      v20 = 0x1000000;
      memset_0(v19, 0, sizeof(v19));
      CVssFunctionTracer::TranslateGenericError(
        &v21,
        &v13,
        (unsigned int)v5,
        L"StringCchPrintfW(,%s,%s)",
        L"\\\\?\\GLOBALROOT",
        v8,
        0);
    }
    VolumeNameAnyFormat = GetVolumeNameAnyFormat(v26, v27);
    if ( VolumeNameAnyFormat < 0 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v13 = L"base\\stor\\vss\\modules\\softprv\\src\\persist.cxx";
      v14 = L"CVssQueuedSnapshot::LoadOriginalVolumeNameIoctl";
      v15 = L"SPRPERSC";
      v16 = 435;
      v17 = 2;
      v18 = 255;
      v20 = 0x1000000;
      memset_0(v19, 0, sizeof(v19));
      CVssFunctionTracer::TranslateInternalProviderError(
        &v21,
        &v13,
        v7,
        2147754758LL,
        L"GetVolumeNameForVolumeMountPointW( %s, ...)",
        v26,
        0);
    }
    CoTaskMemFree(*a2);
    *a2 = 0;
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v21, (unsigned __int16 **)a2, v27);
  }
  catch ( long v12 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v21,
      v12,
      L"base\\stor\\vss\\modules\\softprv\\src\\persist.cxx",
      L"SPRPERSC",
      L"CVssQueuedSnapshot::LoadOriginalVolumeNameIoctl",
      0x1BBu,
      v23);
  }
  catch ( _com_error *v24 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v21,
      v24,
      L"base\\stor\\vss\\modules\\softprv\\src\\persist.cxx",
      L"SPRPERSC",
      L"CVssQueuedSnapshot::LoadOriginalVolumeNameIoctl",
      0x1BBu,
      v23);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v21,
      L"base\\stor\\vss\\modules\\softprv\\src\\persist.cxx",
      L"SPRPERSC",
      L"CVssQueuedSnapshot::LoadOriginalVolumeNameIoctl",
      0x1BBu,
      v23);
  }
  catch ( const std::exception *v25 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v21,
      v25,
      L"base\\stor\\vss\\modules\\softprv\\src\\persist.cxx",
      L"SPRPERSC",
      L"CVssQueuedSnapshot::LoadOriginalVolumeNameIoctl",
      0x1BBu,
      v23);
  }
  pv = 0;
  CVssIOCTLChannel::Call(a1, (__int64)&v21, 0x530190u, 1, 2, 0);
  CVssIOCTLChannel::UnpackSmallString(a1, (struct CVssFunctionTracer *)&v21, (unsigned __int16 **)&pv, v4);
  v5 = StringCchPrintfW(v26, 0x104u, L"%s%s\\", L"\\\\?\\GLOBALROOT", pv);
}

```

## disassembly

```asm
0x18001b380  mov     [rsp+arg_10], rbx
0x18001b385  mov     [rsp+arg_18], rdi
0x18001b38a  push    r12
0x18001b38c  push    r13
0x18001b38e  push    r14
0x18001b390  sub     rsp, 5B0h
0x18001b397  mov     rax, cs:__security_cookie
0x18001b39e  xor     rax, rsp
0x18001b3a1  mov     [rsp+5C8h+var_28], rax
0x18001b3a9  mov     rbx, rdx
0x18001b3ac  mov     rdi, rcx
0x18001b3af  lea     r12, aBaseStorVssMod_12; "base\\stor\\vss\\modules\\softprv\\src"...
0x18001b3b6  mov     [rsp+5C8h+var_570], r12
0x18001b3bb  lea     r13, aCvssqueuedsnap_27; "CVssQueuedSnapshot::LoadOriginalVolumeN"...
0x18001b3c2  mov     [rsp+5C8h+var_568], r13
0x18001b3c7  lea     rax, aSprpersc; "SPRPERSC"
0x18001b3ce  mov     [rsp+5C8h+var_560], rax
0x18001b3d3  mov     [rsp+5C8h+var_558], 198h
0x18001b3db  mov     [rsp+5C8h+var_554], 2
0x18001b3e3  mov     [rsp+5C8h+var_550], 0FFh
0x18001b3eb  mov     [rsp+5C8h+var_4D0], 1000000h
0x18001b3f6  xor     edx, edx; Val
0x18001b3f8  lea     r8d, [rdx+78h]; Size
0x18001b3fc  lea     rcx, [rsp+5C8h+var_548]; void *
0x18001b404  call    memset_0
0x18001b409  xor     r8d, r8d
0x18001b40c  lea     rdx, [rsp+5C8h+var_570]
0x18001b411  lea     rcx, [rsp+5C8h+var_4C8]
0x18001b419  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18001b41e  nop
0x18001b41f  mov     [rsp+5C8h+pv], 0
0x18001b428  mov     [rsp+5C8h+var_598], 0
0x18001b431  mov     byte ptr [rsp+5C8h+var_5A0], 0
0x18001b436  mov     dword ptr [rsp+5C8h+var_5A8], 2
0x18001b43e  mov     r9b, 1
0x18001b441  mov     r8d, 530190h
0x18001b447  lea     rdx, [rsp+5C8h+var_4C8]
0x18001b44f  mov     rcx, rdi
0x18001b452  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x18001b457  lea     r8, [rsp+5C8h+pv]; unsigned __int16 **
0x18001b45c  lea     rdx, [rsp+5C8h+var_4C8]; struct CVssFunctionTracer *
0x18001b464  mov     rcx, rdi; this
0x18001b467  call    ?UnpackSmallString@CVssIOCTLChannel@@QEAAPEBGAEAVCVssFunctionTracer@@AEAPEAG_N@Z; CVssIOCTLChannel::UnpackSmallString(CVssFunctionTracer &,ushort * &,bool)
0x18001b46c  mov     rax, [rsp+5C8h+pv]
0x18001b471  mov     [rsp+5C8h+var_5A8], rax
0x18001b476  lea     r14, aGlobalroot_0; "\\\\?\\GLOBALROOT"
0x18001b47d  mov     r9, r14
0x18001b480  lea     r8, aSS; "%s%s\\"
0x18001b487  mov     edx, 104h; unsigned __int64
0x18001b48c  lea     rcx, [rsp+5C8h+var_448]; unsigned __int16 *
0x18001b494  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b499  mov     edi, eax
0x18001b49b  mov     [rsp+5C8h+var_4C0], eax
0x18001b4a2  test    eax, eax
0x18001b4a4  js      loc_18001B58D
0x18001b4aa  lea     rdx, [rsp+5C8h+var_238]; unsigned __int16 *
0x18001b4b2  lea     rcx, [rsp+5C8h+var_448]; unsigned __int16 *
0x18001b4ba  call    ?GetVolumeNameAnyFormat@@YAJPEBGPEAGK@Z; GetVolumeNameAnyFormat(ushort const *,ushort *,ulong)
0x18001b4bf  mov     [rsp+5C8h+var_4C0], eax
0x18001b4c6  test    eax, eax
0x18001b4c8  js      short loc_18001B4F8
0x18001b4ca  mov     rcx, [rbx]; pv
0x18001b4cd  call    cs:__imp_CoTaskMemFree
0x18001b4d3  mov     qword ptr [rbx], 0
0x18001b4da  lea     r8, [rsp+5C8h+var_238]; unsigned __int16 *
0x18001b4e2  mov     rdx, rbx; unsigned __int16 **
0x18001b4e5  lea     rcx, [rsp+5C8h+var_4C8]; struct CVssFunctionTracer *
0x18001b4ed  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18001b4f2  nop
0x18001b4f3  jmp     loc_18001B60B
0x18001b4f8  call    cs:__imp_GetLastError
0x18001b4fe  mov     ebx, eax
0x18001b500  test    eax, eax
0x18001b502  jle     short loc_18001B50D
0x18001b504  movzx   ebx, ax
0x18001b507  or      ebx, 80070000h
0x18001b50d  mov     [rsp+5C8h+var_570], r12
0x18001b512  mov     [rsp+5C8h+var_568], r13
0x18001b517  lea     rax, aSprpersc; "SPRPERSC"
0x18001b51e  mov     [rsp+5C8h+var_560], rax
0x18001b523  mov     [rsp+5C8h+var_558], 1B3h
0x18001b52b  mov     [rsp+5C8h+var_554], 2
0x18001b533  mov     [rsp+5C8h+var_550], 0FFh
0x18001b53b  mov     [rsp+5C8h+var_4D0], 1000000h
0x18001b546  xor     edx, edx; Val
0x18001b548  lea     r8d, [rdx+78h]; Size
0x18001b54c  lea     rcx, [rsp+5C8h+var_548]; void *
0x18001b554  call    memset_0
0x18001b559  lea     rax, [rsp+5C8h+var_448]
0x18001b561  mov     [rsp+5C8h+var_5A0], rax
0x18001b566  lea     rax, aGetvolumenamef_0; "GetVolumeNameForVolumeMountPointW( %s, "...
0x18001b56d  mov     [rsp+5C8h+var_5A8], rax
0x18001b572  mov     r9d, 80042306h
0x18001b578  mov     r8d, ebx
0x18001b57b  lea     rdx, [rsp+5C8h+var_570]
0x18001b580  lea     rcx, [rsp+5C8h+var_4C8]
0x18001b588  call    ?TranslateInternalProviderError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JJPEBGZZ; CVssFunctionTracer::TranslateInternalProviderError(CVssDebugInfo,long,long,ushort const *,...)
0x18001b58d  mov     rbx, [rsp+5C8h+pv]
0x18001b592  mov     [rsp+5C8h+var_570], r12
0x18001b597  mov     [rsp+5C8h+var_568], r13
0x18001b59c  lea     rax, aSprpersc; "SPRPERSC"
0x18001b5a3  mov     [rsp+5C8h+var_560], rax
0x18001b5a8  mov     [rsp+5C8h+var_558], 1ABh
0x18001b5b0  mov     [rsp+5C8h+var_554], 2
0x18001b5b8  mov     [rsp+5C8h+var_550], 0FFh
0x18001b5c0  mov     [rsp+5C8h+var_4D0], 1000000h
0x18001b5cb  xor     edx, edx; Val
0x18001b5cd  lea     r8d, [rdx+78h]; Size
0x18001b5d1  lea     rcx, [rsp+5C8h+var_548]; void *
0x18001b5d9  call    memset_0
0x18001b5de  mov     [rsp+5C8h+var_5A0], rbx
0x18001b5e3  mov     [rsp+5C8h+var_5A8], r14
0x18001b5e8  lea     r9, aStringcchprint_0; "StringCchPrintfW(,%s,%s)"
0x18001b5ef  mov     r8d, edi
0x18001b5f2  lea     rdx, [rsp+5C8h+var_570]
0x18001b5f7  lea     rcx, [rsp+5C8h+var_4C8]
0x18001b5ff  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18001b605  jmp     short loc_18001B60B
0x18001b607  jmp     short loc_18001B60B
0x18001b609  jmp     short $+2
0x18001b60b  mov     rcx, [rsp+5C8h+pv]; pv
0x18001b610  call    cs:__imp_CoTaskMemFree
0x18001b616  mov     ebx, [rsp+5C8h+var_4C0]
0x18001b61d  lea     rcx, [rsp+5C8h+var_4C8]; this
0x18001b625  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18001b62a  mov     eax, ebx
0x18001b62c  mov     rcx, [rsp+5C8h+var_28]
0x18001b634  xor     rcx, rsp; StackCookie
0x18001b637  call    __security_check_cookie
0x18001b63c  lea     r11, [rsp+5C8h+var_18]
0x18001b644  mov     rbx, [r11+30h]
0x18001b648  mov     rdi, [r11+38h]
0x18001b64c  mov     rsp, r11
0x18001b64f  pop     r14
0x18001b651  pop     r13
0x18001b653  pop     r12
0x18001b655  retn
```

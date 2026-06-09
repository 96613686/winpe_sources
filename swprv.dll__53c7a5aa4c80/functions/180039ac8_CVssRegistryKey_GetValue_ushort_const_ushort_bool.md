# CVssRegistryKey::GetValue(ushort const *,ushort * &,bool)

- ea: `0x180039ac8`
- end: `0x180039f53`
- name: `?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAPEAG_N@Z`
- size: `1163`
- prototype: `char __fastcall(HKEY *this, const unsigned __int16 *, BYTE **, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180039f5c`

## callees

- `0x18000212c`
- `0x180002138`
- `0x180003718`
- `0x1800049e0`
- `0x18001febc`
- `0x180033a8c`
- `0x180033c78`
- `0x180035f44`
- `0x18003649c`
- `0x180037080`
- `0x180039ac8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039b95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039e5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039b95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039e5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039dff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039dff`

## string_xrefs

- `0x180039af3`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180039cc3`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180039e8e`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180039aff`: `CVssRegistryKey::GetValue`
- `0x180039bb7`: `CVssRegistryKey::GetValue`
- `0x180039ccf`: `CVssRegistryKey::GetValue`
- `0x180039e9a`: `CVssRegistryKey::GetValue`
- `0x180039c72`: `Registry key not found`

## pseudocode

```c
char __fastcall CVssRegistryKey::GetValue(HKEY *this, const unsigned __int16 *a2, BYTE **a3, char a4)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  int v8; // ebx
  DWORD v9; // edi
  int v10; // edi
  DWORD v11; // r14d
  HKEY v12; // r15
  HKEY v13; // rsi
  DWORD v14; // ebx
  __int64 v15; // r14
  BYTE *v16; // rdi
  LSTATUS v17; // eax
  unsigned int v18; // ebx
  DWORD v19; // edi
  DWORD v20; // r14d
  HKEY v21; // r15
  HKEY v22; // rsi
  char v23; // bl
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  int pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v27; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v28; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+70h] [rbp-90h]
  int v31; // [rsp+74h] [rbp-8Ch]
  int v32; // [rsp+78h] [rbp-88h]
  _BYTE v33[120]; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+F8h] [rbp-8h]
  void **v35; // [rsp+100h] [rbp+0h] BYREF
  BYTE *v36; // [rsp+108h] [rbp+8h]
  LPVOID v37[22]; // [rsp+110h] [rbp+10h] BYREF
  DWORD lpcbData; // [rsp+1D0h] [rbp+D0h] BYREF
  const unsigned __int16 *cbData; // [rsp+1D8h] [rbp+D8h] BYREF
  DWORD v40; // [rsp+1E0h] [rbp+E0h] BYREF
  DWORD Type; // [rsp+1E8h] [rbp+E8h] BYREF

  LOBYTE(Type) = a4;
  cbData = a2;
  v27 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v28 = L"CVssRegistryKey::GetValue";
  v29 = L"REGREGSC";
  v30 = 394;
  v31 = 11;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v37, (__int64)&v27, 0);
  *a3 = 0;
  Type = 0;
  LODWORD(cbData) = 0;
  v6 = RegQueryValueExW(this[1], L"MaxDiffSpace", 0, &Type, 0, (LPDWORD)&cbData);
  v7 = v6;
  if ( v6 == 2 )
  {
    v8 = (int)cbData;
    v9 = Type;
    v27 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v28 = L"CVssRegistryKey::GetValue";
    v29 = L"REGREGSC";
    v30 = 417;
    v31 = 11;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::LogGenericWarning(
      v37,
      &v27,
      L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu]) => ERROR_FILE_NOT_FOUND",
      this[1],
      this[3],
      L"MaxDiffSpace",
      v9,
      v8);
    v27 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v28 = L"CVssRegistryKey::GetValue";
    v29 = L"REGREGSC";
    v30 = 420;
    v31 = 11;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::Throw(v37, &v27, 2147754760LL, L"Registry key not found");
  }
  if ( v6 && v6 != 234 )
  {
    v10 = (int)cbData;
    v11 = Type;
    v12 = this[3];
    v13 = this[1];
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v27 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v28 = L"CVssRegistryKey::GetValue";
    v29 = L"REGREGSC";
    v30 = 426;
    v31 = 11;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::TranslateGenericError(
      v37,
      &v27,
      v7,
      L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
      v13,
      v12,
      L"MaxDiffSpace",
      v11,
      v10);
  }
  v14 = Type;
  if ( Type != 1 && Type != 2 )
  {
    v27 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v28 = L"CVssRegistryKey::GetValue";
    v29 = L"REGREGSC";
    v30 = 432;
    v31 = 11;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    LODWORD(lpData) = v14;
    CVssFunctionTracer::TranslateGenericError(
      v37,
      &v27,
      2147549183LL,
      L"Unexpected type %lu for a string value 0x%08lx(%s),%s",
      lpData,
      this[1],
      this[3],
      L"MaxDiffSpace");
  }
  v36 = 0;
  v35 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v15 = (unsigned int)cbData >> 1;
  CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close((__int64)&v35);
  v16 = (BYTE *)CoTaskMemAlloc(2 * v15 + 2);
  v36 = v16;
  if ( !v16 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v40 = 0;
  lpcbData = 2 * v15;
  v17 = RegQueryValueExW(this[1], L"MaxDiffSpace", 0, &v40, v16, &lpcbData);
  v18 = v17;
  if ( v17 )
  {
    v19 = lpcbData;
    v20 = v40;
    v21 = this[3];
    v22 = this[1];
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    v27 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v28 = L"CVssRegistryKey::GetValue";
    v29 = L"REGREGSC";
    v30 = 453;
    v31 = 11;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::TranslateGenericError(
      v37,
      &v27,
      v18,
      L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
      v22,
      v21,
      L"MaxDiffSpace",
      v20,
      v19);
  }
  *(_WORD *)&v16[2 * v15] = 0;
  v36 = 0;
  *a3 = v16;
  v23 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v37, 1);
  CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v35);
  CVssFunctionTracer::~CVssFunctionTracer(v37);
  return v23;
}

```

## disassembly

```asm
0x180039ac8  mov     byte ptr [rsp-8+Type], r9b
0x180039acd  mov     [rsp-8+cbData], rdx
0x180039ad2  push    rbp
0x180039ad3  push    rbx
0x180039ad4  push    rsi
0x180039ad5  push    rdi
0x180039ad6  push    r12
0x180039ad8  push    r13
0x180039ada  push    r14
0x180039adc  push    r15
0x180039ade  lea     rbp, [rsp-88h]
0x180039ae6  sub     rsp, 188h
0x180039aed  mov     r15, r8
0x180039af0  mov     rsi, rcx
0x180039af3  lea     r14, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x180039afa  mov     [rsp+1C0h+var_168], r14
0x180039aff  lea     rdi, aCvssregistryke_3; "CVssRegistryKey::GetValue"
0x180039b06  mov     [rsp+1C0h+var_160], rdi
0x180039b0b  lea     rax, aRegregsc; "REGREGSC"
0x180039b12  mov     [rsp+1C0h+var_158], rax
0x180039b17  mov     [rsp+1C0h+var_150], 18Ah
0x180039b1f  mov     [rsp+1C0h+var_14C], 0Bh
0x180039b27  mov     [rsp+1C0h+var_148], 0FFh
0x180039b2f  xor     r12d, r12d
0x180039b32  mov     [rbp+0C0h+var_C8], 1000000h
0x180039b39  xor     edx, edx; Val
0x180039b3b  lea     r8d, [r12+78h]; Size
0x180039b40  lea     rcx, [rbp+0C0h+var_140]; void *
0x180039b44  call    memset_0
0x180039b49  xor     r8d, r8d
0x180039b4c  lea     rdx, [rsp+1C0h+var_168]
0x180039b51  lea     rcx, [rbp+0C0h+var_B0]
0x180039b55  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180039b5a  nop
0x180039b5b  mov     [r15], r12
0x180039b5e  mov     [rbp+0C0h+Type], r12d
0x180039b65  mov     dword ptr [rbp+0C0h+cbData], r12d
0x180039b6c  lea     rax, [rbp+0C0h+cbData]
0x180039b73  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x180039b78  mov     [rsp+1C0h+lpData], r12; lpData
0x180039b7d  lea     r9, [rbp+0C0h+Type]; lpType
0x180039b84  xor     r8d, r8d; lpReserved
0x180039b87  lea     r13, ValueName; "MaxDiffSpace"
0x180039b8e  mov     rdx, r13; lpValueName
0x180039b91  mov     rcx, [rsi+8]; hKey
0x180039b95  call    cs:__imp_RegQueryValueExW
0x180039b9b  mov     ebx, eax
0x180039b9d  cmp     eax, 2
0x180039ba0  jnz     loc_180039C8E
0x180039ba6  mov     ebx, dword ptr [rbp+0C0h+cbData]
0x180039bac  mov     edi, [rbp+0C0h+Type]
0x180039bb2  mov     [rsp+1C0h+var_168], r14
0x180039bb7  lea     r15, aCvssregistryke_3; "CVssRegistryKey::GetValue"
0x180039bbe  mov     [rsp+1C0h+var_160], r15
0x180039bc3  lea     rax, aRegregsc; "REGREGSC"
0x180039bca  mov     [rsp+1C0h+var_158], rax
0x180039bcf  mov     [rsp+1C0h+var_150], 1A1h
0x180039bd7  mov     [rsp+1C0h+var_14C], 0Bh
0x180039bdf  mov     [rsp+1C0h+var_148], 0FFh
0x180039be7  mov     [rbp+0C0h+var_C8], 1000000h
0x180039bee  xor     edx, edx; Val
0x180039bf0  lea     r8d, [r12+78h]; Size
0x180039bf5  lea     rcx, [rbp+0C0h+var_140]; void *
0x180039bf9  call    memset_0
0x180039bfe  mov     dword ptr [rsp+1C0h+var_188], ebx
0x180039c02  mov     dword ptr [rsp+1C0h+var_190], edi
0x180039c06  mov     [rsp+1C0h+lpcbData], r13
0x180039c0b  mov     rax, [rsi+18h]
0x180039c0f  mov     [rsp+1C0h+lpData], rax
0x180039c14  mov     r9, [rsi+8]
0x180039c18  lea     r8, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x180039c1f  lea     rdx, [rsp+1C0h+var_168]
0x180039c24  lea     rcx, [rbp+0C0h+var_B0]
0x180039c28  call    ?LogGenericWarning@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::LogGenericWarning(CVssDebugInfo,ushort const *,...)
0x180039c2d  mov     [rsp+1C0h+var_168], r14
0x180039c32  mov     [rsp+1C0h+var_160], r15
0x180039c37  lea     rax, aRegregsc; "REGREGSC"
0x180039c3e  mov     [rsp+1C0h+var_158], rax
0x180039c43  mov     [rsp+1C0h+var_150], 1A4h
0x180039c4b  mov     [rsp+1C0h+var_14C], 0Bh
0x180039c53  mov     [rsp+1C0h+var_148], 0FFh
0x180039c5b  mov     [rbp+0C0h+var_C8], 1000000h
0x180039c62  xor     edx, edx; Val
0x180039c64  lea     r8d, [r12+78h]; Size
0x180039c69  lea     rcx, [rbp+0C0h+var_140]; void *
0x180039c6d  call    memset_0
0x180039c72  lea     r9, aRegistryKeyNot; "Registry key not found"
0x180039c79  mov     r8d, 80042308h
0x180039c7f  lea     rdx, [rsp+1C0h+var_168]
0x180039c84  lea     rcx, [rbp+0C0h+var_B0]
0x180039c88  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180039c8e  test    eax, eax
0x180039c90  jz      loc_180039D46
0x180039c96  cmp     eax, 0EAh
0x180039c9b  jz      loc_180039D46
0x180039ca1  mov     edi, dword ptr [rbp+0C0h+cbData]
0x180039ca7  mov     r14d, [rbp+0C0h+Type]
0x180039cae  mov     r15, [rsi+18h]
0x180039cb2  mov     rsi, [rsi+8]
0x180039cb6  test    eax, eax
0x180039cb8  jle     short loc_180039CC3
0x180039cba  movzx   ebx, ax
0x180039cbd  or      ebx, 80070000h
0x180039cc3  lea     rax, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x180039cca  mov     [rsp+1C0h+var_168], rax
0x180039ccf  lea     rax, aCvssregistryke_3; "CVssRegistryKey::GetValue"
0x180039cd6  mov     [rsp+1C0h+var_160], rax
0x180039cdb  lea     rax, aRegregsc; "REGREGSC"
0x180039ce2  mov     [rsp+1C0h+var_158], rax
0x180039ce7  mov     [rsp+1C0h+var_150], 1AAh
0x180039cef  mov     [rsp+1C0h+var_14C], 0Bh
0x180039cf7  mov     [rsp+1C0h+var_148], 0FFh
0x180039cff  mov     [rbp+0C0h+var_C8], 1000000h
0x180039d06  xor     edx, edx; Val
0x180039d08  lea     r8d, [rdx+78h]; Size
0x180039d0c  lea     rcx, [rbp+0C0h+var_140]; void *
0x180039d10  call    memset_0
0x180039d15  mov     [rsp+1C0h+var_180], edi
0x180039d19  mov     dword ptr [rsp+1C0h+var_188], r14d
0x180039d1e  mov     [rsp+1C0h+var_190], r13
0x180039d23  mov     [rsp+1C0h+lpcbData], r15
0x180039d28  mov     [rsp+1C0h+lpData], rsi
0x180039d2d  lea     r9, aRegqueryvaluee_0; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x180039d34  mov     r8d, ebx
0x180039d37  lea     rdx, [rsp+1C0h+var_168]
0x180039d3c  lea     rcx, [rbp+0C0h+var_B0]
0x180039d40  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180039d46  mov     ebx, [rbp+0C0h+Type]
0x180039d4c  cmp     ebx, 1
0x180039d4f  jz      loc_180039DD5
0x180039d55  cmp     ebx, 2
0x180039d58  jz      short loc_180039DD5
0x180039d5a  mov     [rsp+1C0h+var_168], r14
0x180039d5f  mov     [rsp+1C0h+var_160], rdi
0x180039d64  lea     rax, aRegregsc; "REGREGSC"
0x180039d6b  mov     [rsp+1C0h+var_158], rax
0x180039d70  mov     [rsp+1C0h+var_150], 1B0h
0x180039d78  mov     [rsp+1C0h+var_14C], 0Bh
0x180039d80  mov     [rsp+1C0h+var_148], 0FFh
0x180039d88  mov     [rbp+0C0h+var_C8], 1000000h
0x180039d8f  xor     edx, edx; Val
0x180039d91  lea     r8d, [rdx+78h]; Size
0x180039d95  lea     rcx, [rbp+0C0h+var_140]; void *
0x180039d99  call    memset_0
0x180039d9e  mov     [rsp+1C0h+var_188], r13
0x180039da3  mov     rax, [rsi+18h]
0x180039da7  mov     [rsp+1C0h+var_190], rax
0x180039dac  mov     rax, [rsi+8]
0x180039db0  mov     [rsp+1C0h+lpcbData], rax
0x180039db5  mov     dword ptr [rsp+1C0h+lpData], ebx
0x180039db9  lea     r9, aUnexpectedType; "Unexpected type %lu for a string value "...
0x180039dc0  mov     r8d, 8000FFFFh
0x180039dc6  lea     rdx, [rsp+1C0h+var_168]
0x180039dcb  lea     rcx, [rbp+0C0h+var_B0]
0x180039dcf  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180039dd5  mov     [rbp+0C0h+var_B8], r12
0x180039dd9  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180039de0  mov     [rbp+0C0h+var_C0], rax
0x180039de4  mov     r14d, dword ptr [rbp+0C0h+cbData]
0x180039deb  shr     r14d, 1
0x180039dee  lea     rcx, [rbp+0C0h+var_C0]
0x180039df2  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void (*)(void *),&CoTaskMemFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x180039df7  lea     rcx, ds:2[r14*2]; cb
0x180039dff  call    cs:__imp_CoTaskMemAlloc
0x180039e05  mov     rdi, rax
0x180039e08  mov     [rbp+0C0h+var_B8], rax
0x180039e0c  test    rax, rax
0x180039e0f  jnz     short loc_180039E2B
0x180039e11  mov     [rsp+1C0h+pExceptionObject], 8007000Eh
0x180039e19  lea     rdx, _TI1J; pThrowInfo
0x180039e20  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x180039e25  call    _CxxThrowException_0
0x180039e2b  mov     [rbp+0C0h+arg_10], r12d
0x180039e32  lea     eax, [r14+r14]
0x180039e36  mov     [rbp+0C0h+arg_0], eax
0x180039e3c  lea     rax, [rbp+0C0h+arg_0]
0x180039e43  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x180039e48  mov     [rsp+1C0h+lpData], rdi; lpData
0x180039e4d  lea     r9, [rbp+0C0h+arg_10]; lpType
0x180039e54  xor     r8d, r8d; lpReserved
0x180039e57  mov     rdx, r13; lpValueName
0x180039e5a  mov     rcx, [rsi+8]; hKey
0x180039e5e  call    cs:__imp_RegQueryValueExW
0x180039e64  mov     ebx, eax
0x180039e66  test    eax, eax
0x180039e68  jz      loc_180039F11
0x180039e6e  mov     edi, [rbp+0C0h+arg_0]
0x180039e74  mov     r14d, [rbp+0C0h+arg_10]
0x180039e7b  mov     r15, [rsi+18h]
0x180039e7f  mov     rsi, [rsi+8]
0x180039e83  jle     short loc_180039E8E
0x180039e85  movzx   ebx, ax
0x180039e88  or      ebx, 80070000h
0x180039e8e  lea     rax, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x180039e95  mov     [rsp+1C0h+var_168], rax
0x180039e9a  lea     rax, aCvssregistryke_3; "CVssRegistryKey::GetValue"
0x180039ea1  mov     [rsp+1C0h+var_160], rax
0x180039ea6  lea     rax, aRegregsc; "REGREGSC"
0x180039ead  mov     [rsp+1C0h+var_158], rax
0x180039eb2  mov     [rsp+1C0h+var_150], 1C5h
0x180039eba  mov     [rsp+1C0h+var_14C], 0Bh
0x180039ec2  mov     [rsp+1C0h+var_148], 0FFh
0x180039eca  mov     [rbp+0C0h+var_C8], 1000000h
0x180039ed1  xor     edx, edx; Val
0x180039ed3  lea     r8d, [rdx+78h]; Size
0x180039ed7  lea     rcx, [rbp+0C0h+var_140]; void *
0x180039edb  call    memset_0
0x180039ee0  mov     [rsp+1C0h+var_180], edi
0x180039ee4  mov     dword ptr [rsp+1C0h+var_188], r14d
0x180039ee9  mov     [rsp+1C0h+var_190], r13
0x180039eee  mov     [rsp+1C0h+lpcbData], r15
0x180039ef3  mov     [rsp+1C0h+lpData], rsi
0x180039ef8  lea     r9, aRegqueryvaluee_0; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x180039eff  mov     r8d, ebx
0x180039f02  lea     rdx, [rsp+1C0h+var_168]
0x180039f07  lea     rcx, [rbp+0C0h+var_B0]
0x180039f0b  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180039f11  mov     [rdi+r14*2], r12w
0x180039f16  mov     [rbp+0C0h+var_B8], r12
0x180039f1a  mov     [r15], rdi
0x180039f1d  mov     dl, 1; bool
0x180039f1f  lea     rcx, [rbp+0C0h+var_B0]; this
0x180039f23  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x180039f28  mov     bl, al
0x180039f2a  lea     rcx, [rbp+0C0h+var_C0]
0x180039f2e  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x180039f33  nop
0x180039f34  lea     rcx, [rbp+0C0h+var_B0]; this
0x180039f38  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180039f3d  mov     al, bl
0x180039f3f  add     rsp, 188h
0x180039f46  pop     r15
0x180039f48  pop     r14
0x180039f4a  pop     r13
0x180039f4c  pop     r12
0x180039f4e  pop     rdi
0x180039f4f  pop     rsi
0x180039f50  pop     rbx
0x180039f51  pop     rbp
0x180039f52  retn
```

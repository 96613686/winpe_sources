# SrmGetVolumeDisplayName(ushort const *,ushort * *)

- ea: `0x18007f2bc`
- end: `0x18007f647`
- name: `?SrmGetVolumeDisplayName@@YAXPEBGPEAPEAG@Z`
- size: `907`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x180080078`

## callees

- `0x180006a1c`
- `0x18000ad14`
- `0x18000af40`
- `0x180016ee0`
- `0x180017f54`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x180074a04`
- `0x18007f2bc`
- `0x18007f760`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007f49a`
- `ole32!CoTaskMemFree` at `0x18007f4ad`
- `ole32!CoTaskMemFree` at `0x18007f49a`
- `ole32!CoTaskMemFree` at `0x18007f4ad`
- `KERNEL32!GetLastError` at `0x18007f3ad`
- `KERNEL32!GetLastError` at `0x18007f3ad`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18007f3e8`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18007f3e8`

## string_xrefs

- `0x18007f630`: `StringCchCopyW`
- `0x18007f5d8`: `GetVolumePathNamesForVolumeName(%s, %d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall SrmGetVolumeDisplayName(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  DWORD v4; // r14d
  WCHAR *v5; // rbx
  signed int LastError; // eax
  unsigned int v7; // edi
  unsigned __int16 *v8; // rdi
  WCHAR *v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  const unsigned __int16 *v13; // r14
  int v14; // r8d
  const unsigned __int16 *v15; // rax
  __int64 v16; // rax
  unsigned int Hr; // ebx
  __int64 v18; // rax
  __int64 v19; // [rsp+28h] [rbp-D8h]
  DWORD cchReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp-B8h] BYREF
  LPWCH lpszVolumePathNames; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 **v23; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v24; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v25; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+7Ch] [rbp-84h]
  int v29; // [rsp+80h] [rbp-80h]
  _BYTE v30[96]; // [rsp+88h] [rbp-78h] BYREF
  int v31; // [rsp+E8h] [rbp-18h]
  void **v32; // [rsp+F0h] [rbp-10h] BYREF
  int v33; // [rsp+F8h] [rbp-8h]
  WCHAR szVolumeName[56]; // [rsp+1A0h] [rbp+A0h] BYREF

  v23 = &v24;
  v24 = L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp";
  v25 = L"SrmGetVolumeDisplayName";
  v26 = L"SRMVOLMC";
  v27 = 170;
  v28 = 17;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(v30, 0, sizeof(v30));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v32, (const struct CSrmDebugInfo *)&v24, 0);
  lpszVolumePathNames = 0;
  v21 = 0;
  SrmGetVolumeNameForPathName(a1, szVolumeName, 0x32u, 0, 0);
  v4 = 512;
  CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumePathNames, 0x200u);
  v5 = lpszVolumePathNames;
  *lpszVolumePathNames = 0;
  cchReturnLength = 0;
  while ( !GetVolumePathNamesForVolumeNameW(a1, v5, v4, &cchReturnLength) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError != 234 )
    {
      if ( LastError != 1168 && (unsigned int)(LastError - 2) > 1 )
      {
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        v23 = &v24;
        v16 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)&v24,
                (__int64)L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp",
                (__int64)L"SRMVOLMC",
                (__int64)L"SrmGetVolumeDisplayName",
                229,
                17);
        LODWORD(v19) = v4;
        CSrmFunctionTracer::TranslateGenericError(&v32, v16, v7, L"GetVolumePathNamesForVolumeName(%s, %d)", a1, v19);
      }
      v23 = &v24;
      v24 = L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp";
      v25 = L"SrmGetVolumeDisplayName";
      v26 = L"SRMVOLMC";
      v27 = 224;
      v28 = 17;
      v29 = 255;
      v31 = 0x1000000;
      memset_0(v30, 0, sizeof(v30));
      CSrmFunctionTracer::Trace(&v32, &v24, L"volume %s is not found", a1);
      break;
    }
    v4 = cchReturnLength + 1;
    CSrmAutoPWSZ::Reallocate((CSrmAutoPWSZ *)&lpszVolumePathNames, cchReturnLength + 1);
    v5 = lpszVolumePathNames;
    *lpszVolumePathNames = 0;
  }
  if ( *v5 )
  {
    v9 = v5;
    v10 = -1;
    do
      ++v10;
    while ( v5[v10] );
    v11 = -1;
    do
      ++v11;
    while ( v5[v11] );
    LODWORD(v12) = v10;
    v13 = v5;
    if ( (_DWORD)v10 )
    {
      do
      {
        v14 = v12;
        if ( (int)v12 >= (int)v10 )
          v14 = v10;
        v15 = v9;
        if ( (int)v12 >= (int)v10 )
          v15 = v13;
        v13 = v15;
        v9 += (int)v12 + 1;
        v12 = -1;
        do
          ++v12;
        while ( v9[v12] );
        LODWORD(v10) = v14;
      }
      while ( (_DWORD)v12 );
    }
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&v21, (int)v10 - 1);
    v8 = v21;
    v33 = StringCchCopyNW(v21, (int)v10, v13, (int)v10 - 1);
    if ( v33 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      v23 = &v24;
      v18 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)&v24,
              (__int64)L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp",
              (__int64)L"SRMVOLMC",
              (__int64)L"SrmGetVolumeDisplayName",
              274,
              17);
      CSrmFunctionTracer::TranslateGenericError(&v32, v18, Hr, L"StringCchCopyW");
    }
  }
  else
  {
    CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v21, a1);
    v8 = v21;
  }
  v21 = 0;
  *a2 = v8;
  CoTaskMemFree(0);
  v21 = 0;
  CoTaskMemFree(v5);
  lpszVolumePathNames = 0;
  v32 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v32);
}

```

## disassembly

```asm
0x18007f2bc  mov     [rsp-8+arg_10], rbx
0x18007f2c1  push    rbp
0x18007f2c2  push    rsi
0x18007f2c3  push    rdi
0x18007f2c4  push    r12
0x18007f2c6  push    r13
0x18007f2c8  push    r14
0x18007f2ca  push    r15
0x18007f2cc  lea     rbp, [rsp-120h]
0x18007f2d4  sub     rsp, 220h
0x18007f2db  mov     rax, cs:__security_cookie
0x18007f2e2  xor     rax, rsp
0x18007f2e5  mov     [rbp+150h+var_40], rax
0x18007f2ec  mov     r15, rdx
0x18007f2ef  mov     rsi, rcx
0x18007f2f2  lea     rax, [rsp+250h+var_1F0]
0x18007f2f7  mov     [rsp+250h+var_1F8], rax
0x18007f2fc  lea     r13, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\volume\\srmv"...
0x18007f303  mov     [rsp+250h+var_1F0], r13
0x18007f308  lea     rax, aSrmgetvolumedi_0; "SrmGetVolumeDisplayName"
0x18007f30f  mov     [rsp+250h+var_1E8], rax
0x18007f314  lea     rax, aSrmvolmc; "SRMVOLMC"
0x18007f31b  mov     [rsp+250h+var_1E0], rax
0x18007f320  mov     [rsp+250h+var_1D8], 0AAh
0x18007f328  mov     [rsp+250h+var_1D4], 11h
0x18007f330  mov     [rbp+150h+var_1D0], 0FFh
0x18007f337  xor     r12d, r12d
0x18007f33a  mov     [rbp+150h+var_168], 1000000h
0x18007f341  xor     edx, edx; Val
0x18007f343  lea     r8d, [r12+60h]; Size
0x18007f348  lea     rcx, [rbp+150h+var_1C8]; void *
0x18007f34c  call    memset_0
0x18007f351  nop
0x18007f352  xor     r8d, r8d
0x18007f355  lea     rdx, [rsp+250h+var_1F0]
0x18007f35a  lea     rcx, [rbp+150h+var_160]
0x18007f35e  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007f363  nop
0x18007f364  mov     [rsp+250h+lpszVolumePathNames], r12
0x18007f369  mov     [rsp+250h+var_208], r12
0x18007f36e  mov     [rsp+250h+var_230], r12; unsigned __int16 **
0x18007f373  xor     r9d, r9d; bool
0x18007f376  lea     r8d, [r12+32h]; unsigned int
0x18007f37b  lea     rdx, [rbp+150h+szVolumeName]; lpszVolumeName
0x18007f382  mov     rcx, rsi; lpszFileName
0x18007f385  call    ?SrmGetVolumeNameForPathName@@YAXPEBGPEAGK_NPEAPEAG@Z; SrmGetVolumeNameForPathName(ushort const *,ushort *,ulong,bool,ushort * *)
0x18007f38a  mov     r14d, 200h
0x18007f390  mov     edx, r14d; unsigned __int64
0x18007f393  lea     rcx, [rsp+250h+lpszVolumePathNames]; this
0x18007f398  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007f39d  mov     rbx, [rsp+250h+lpszVolumePathNames]
0x18007f3a2  mov     [rbx], r12w
0x18007f3a6  mov     [rsp+250h+cchReturnLength], r12d
0x18007f3ab  jmp     short loc_18007F3DA
0x18007f3ad  call    cs:__imp_GetLastError
0x18007f3b3  mov     edi, eax
0x18007f3b5  cmp     eax, 0EAh
0x18007f3ba  jnz     short loc_18007F3F7
0x18007f3bc  mov     r14d, [rsp+250h+cchReturnLength]
0x18007f3c1  inc     r14d
0x18007f3c4  mov     edx, r14d; unsigned __int64
0x18007f3c7  lea     rcx, [rsp+250h+lpszVolumePathNames]; this
0x18007f3cc  call    ?Reallocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Reallocate(unsigned __int64)
0x18007f3d1  mov     rbx, [rsp+250h+lpszVolumePathNames]
0x18007f3d6  mov     [rbx], r12w
0x18007f3da  lea     r9, [rsp+250h+cchReturnLength]; lpcchReturnLength
0x18007f3df  mov     r8d, r14d; cchBufferLength
0x18007f3e2  mov     rdx, rbx; lpszVolumePathNames
0x18007f3e5  mov     rcx, rsi; lpszVolumeName
0x18007f3e8  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18007f3ee  test    eax, eax
0x18007f3f0  jz      short loc_18007F3AD
0x18007f3f2  jmp     loc_18007F478
0x18007f3f7  cmp     edi, 490h
0x18007f3fd  jz      short loc_18007F40B
0x18007f3ff  add     eax, 0FFFFFFFEh
0x18007f402  cmp     eax, 1
0x18007f405  ja      loc_18007F58B
0x18007f40b  lea     rax, [rsp+250h+var_1F0]
0x18007f410  mov     [rsp+250h+var_1F8], rax
0x18007f415  mov     [rsp+250h+var_1F0], r13
0x18007f41a  lea     rax, aSrmgetvolumedi_0; "SrmGetVolumeDisplayName"
0x18007f421  mov     [rsp+250h+var_1E8], rax
0x18007f426  lea     rax, aSrmvolmc; "SRMVOLMC"
0x18007f42d  mov     [rsp+250h+var_1E0], rax
0x18007f432  mov     [rsp+250h+var_1D8], 0E0h
0x18007f43a  mov     [rsp+250h+var_1D4], 11h
0x18007f442  mov     [rbp+150h+var_1D0], 0FFh
0x18007f449  mov     [rbp+150h+var_168], 1000000h
0x18007f450  xor     edx, edx; Val
0x18007f452  lea     r8d, [rdx+60h]; Size
0x18007f456  lea     rcx, [rbp+150h+var_1C8]; void *
0x18007f45a  call    memset_0
0x18007f45f  nop
0x18007f460  mov     r9, rsi
0x18007f463  lea     r8, aVolumeSIsNotFo; "volume %s is not found"
0x18007f46a  lea     rdx, [rsp+250h+var_1F0]
0x18007f46f  lea     rcx, [rbp+150h+var_160]
0x18007f473  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007f478  cmp     [rbx], r12w
0x18007f47c  jnz     short loc_18007F4FB
0x18007f47e  mov     rdx, rsi; unsigned __int16 *
0x18007f481  lea     rcx, [rsp+250h+var_208]; this
0x18007f486  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007f48b  mov     rdi, [rsp+250h+var_208]
0x18007f490  mov     [rsp+250h+var_208], r12
0x18007f495  mov     [r15], rdi
0x18007f498  xor     ecx, ecx; pv
0x18007f49a  call    cs:__imp_CoTaskMemFree
0x18007f4a0  mov     [rsp+250h+var_208], r12
0x18007f4a5  mov     [rsp+250h+var_208], r12
0x18007f4aa  mov     rcx, rbx; pv
0x18007f4ad  call    cs:__imp_CoTaskMemFree
0x18007f4b3  mov     [rsp+250h+lpszVolumePathNames], r12
0x18007f4b8  mov     [rsp+250h+lpszVolumePathNames], r12
0x18007f4bd  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007f4c4  mov     [rbp+150h+var_160], rax
0x18007f4c8  lea     rcx, [rbp+150h+var_160]; this
0x18007f4cc  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007f4d1  mov     rcx, [rbp+150h+var_40]
0x18007f4d8  xor     rcx, rsp; StackCookie
0x18007f4db  call    __security_check_cookie
0x18007f4e0  mov     rbx, [rsp+250h+arg_10]
0x18007f4e8  add     rsp, 220h
0x18007f4ef  pop     r15
0x18007f4f1  pop     r14
0x18007f4f3  pop     r13
0x18007f4f5  pop     r12
0x18007f4f7  pop     rdi
0x18007f4f8  pop     rsi
0x18007f4f9  pop     rbp
0x18007f4fa  retn
0x18007f4fb  mov     rdx, rbx
0x18007f4fe  or      r9, 0FFFFFFFFFFFFFFFFh
0x18007f502  mov     rsi, r9
0x18007f505  inc     rsi
0x18007f508  cmp     [rbx+rsi*2], r12w
0x18007f50d  jnz     short loc_18007F505
0x18007f50f  mov     rax, r9
0x18007f512  inc     rax
0x18007f515  cmp     [rbx+rax*2], r12w
0x18007f51a  jnz     short loc_18007F512
0x18007f51c  mov     ecx, esi
0x18007f51e  mov     r14, rbx
0x18007f521  test    esi, esi
0x18007f523  jz      short loc_18007F556
0x18007f525  mov     r8d, ecx
0x18007f528  cmp     ecx, esi
0x18007f52a  cmovge  r8d, esi
0x18007f52e  mov     rax, rdx
0x18007f531  cmovge  rax, r14
0x18007f535  mov     r14, rax
0x18007f538  lea     eax, [rcx+1]
0x18007f53b  movsxd  rcx, eax
0x18007f53e  lea     rdx, [rdx+rcx*2]
0x18007f542  mov     rcx, r9
0x18007f545  inc     rcx
0x18007f548  cmp     [rdx+rcx*2], r12w
0x18007f54d  jnz     short loc_18007F545
0x18007f54f  mov     esi, r8d
0x18007f552  test    ecx, ecx
0x18007f554  jnz     short loc_18007F525
0x18007f556  lea     eax, [rsi-1]
0x18007f559  movsxd  rdi, eax
0x18007f55c  mov     rdx, rdi; unsigned __int64
0x18007f55f  lea     rcx, [rsp+250h+var_208]; this
0x18007f564  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007f569  movsxd  rdx, esi; unsigned __int64
0x18007f56c  mov     r9, rdi; unsigned __int64
0x18007f56f  mov     r8, r14; unsigned __int16 *
0x18007f572  mov     rdi, [rsp+250h+var_208]
0x18007f577  mov     rcx, rdi; unsigned __int16 *
0x18007f57a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18007f57f  mov     [rbp+150h+var_158], eax
0x18007f582  test    eax, eax
0x18007f584  js      short loc_18007F5EF
0x18007f586  jmp     loc_18007F490
0x18007f58b  test    edi, edi
0x18007f58d  jle     short loc_18007F598
0x18007f58f  movzx   edi, di
0x18007f592  or      edi, 80070000h
0x18007f598  lea     rax, [rsp+250h+var_1F0]
0x18007f59d  mov     [rsp+250h+var_1F8], rax
0x18007f5a2  mov     dword ptr [rsp+250h+var_228], 11h
0x18007f5aa  mov     dword ptr [rsp+250h+var_230], 0E5h
0x18007f5b2  lea     r9, aSrmgetvolumedi_0; "SrmGetVolumeDisplayName"
0x18007f5b9  lea     r8, aSrmvolmc; "SRMVOLMC"
0x18007f5c0  mov     rdx, r13
0x18007f5c3  lea     rcx, [rsp+250h+var_1F0]
0x18007f5c8  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007f5cd  nop
0x18007f5ce  mov     dword ptr [rsp+250h+var_228], r14d
0x18007f5d3  mov     [rsp+250h+var_230], rsi
0x18007f5d8  lea     r9, aGetvolumepathn_0; "GetVolumePathNamesForVolumeName(%s, %d)"
0x18007f5df  mov     r8d, edi
0x18007f5e2  mov     rdx, rax
0x18007f5e5  lea     rcx, [rbp+150h+var_160]
0x18007f5e9  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18007f5ef  lea     rcx, [rbp+150h+var_160]; this
0x18007f5f3  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007f5f8  mov     ebx, eax
0x18007f5fa  lea     rax, [rsp+250h+var_1F0]
0x18007f5ff  mov     [rsp+250h+var_1F8], rax
0x18007f604  mov     dword ptr [rsp+250h+var_228], 11h
0x18007f60c  mov     dword ptr [rsp+250h+var_230], 112h
0x18007f614  lea     r9, aSrmgetvolumedi_0; "SrmGetVolumeDisplayName"
0x18007f61b  lea     r8, aSrmvolmc; "SRMVOLMC"
0x18007f622  mov     rdx, r13
0x18007f625  lea     rcx, [rsp+250h+var_1F0]
0x18007f62a  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007f62f  nop
0x18007f630  lea     r9, aStringcchcopyw; "StringCchCopyW"
0x18007f637  mov     r8d, ebx
0x18007f63a  mov     rdx, rax
0x18007f63d  lea     rcx, [rbp+150h+var_160]
0x18007f641  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```

# IsVolumeRootPath(ushort const *)

- ea: `0x18007ecc8`
- end: `0x18007ef34`
- name: `?IsVolumeRootPath@@YAHPEBG@Z`
- size: `620`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18007b5f4`
- `0x180096d3c`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000ad14`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x180074d00`
- `0x18007ecc8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007ed88`
- `ole32!CoTaskMemFree` at `0x18007ee79`
- `ole32!CoTaskMemFree` at `0x18007ed88`
- `ole32!CoTaskMemFree` at `0x18007ee79`
- `KERNEL32!GetLastError` at `0x18007eec2`
- `KERNEL32!GetLastError` at `0x18007eec2`
- `KERNEL32!GetVolumePathNameW` at `0x18007edd0`
- `KERNEL32!GetVolumePathNameW` at `0x18007edd0`

## string_xrefs

- `0x18007ef1d`: `GetVolumePathName`
- `0x18007ed0e`: `IsVolumeRootPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_BOOL8 __fastcall IsVolumeRootPath(LPCWSTR lpszFileName)
{
  __int64 v2; // rdi
  __int64 v3; // rbx
  LPWSTR v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rax
  BOOL v8; // ebx
  signed int LastError; // eax
  unsigned int Hr; // ebx
  __int64 v11; // rax
  LPWSTR lpszVolumePathName; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 **v13; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v14; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v15; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v16; // [rsp+60h] [rbp-A0h]
  int v17; // [rsp+68h] [rbp-98h]
  int v18; // [rsp+6Ch] [rbp-94h]
  int v19; // [rsp+70h] [rbp-90h]
  _BYTE v20[96]; // [rsp+78h] [rbp-88h] BYREF
  int v21; // [rsp+D8h] [rbp-28h]
  _QWORD v22[22]; // [rsp+E0h] [rbp-20h] BYREF

  v13 = &v14;
  v14 = L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp";
  v15 = L"IsVolumeRootPath";
  v16 = L"SRMVOLMC";
  v17 = 930;
  v18 = 17;
  v19 = 255;
  v21 = 0x1000000;
  memset_0(v20, 0, sizeof(v20));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v22, (const struct CSrmDebugInfo *)&v14, 0);
  lpszVolumePathName = 0;
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( lpszFileName[v3] );
  if ( v3 )
  {
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumePathName, v3 + 1);
    v5 = lpszVolumePathName;
    if ( !GetVolumePathNameW(lpszFileName, lpszVolumePathName, v3 + 2) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)v22, LastError);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)v22);
      v13 = &v14;
      v11 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)&v14,
              (__int64)L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp",
              (__int64)L"SRMVOLMC",
              (__int64)L"IsVolumeRootPath",
              947,
              17);
      CSrmFunctionTracer::TranslatePathError(v22, v11, Hr, L"GetVolumePathName");
    }
    v13 = &v14;
    v14 = L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp";
    v15 = L"IsVolumeRootPath";
    v16 = L"SRMVOLMC";
    v17 = 952;
    v18 = 17;
    v19 = 255;
    v21 = 0x1000000;
    memset_0(v20, 0, sizeof(v20));
    CSrmFunctionTracer::Trace(v22, &v14, L"Volume root is %s", v5);
    do
      ++v2;
    while ( v5[v2] );
    v6 = v2 - 1;
    if ( v5[v2 - 1] != 92 )
      v6 = v2;
    v7 = v3 - 1;
    if ( lpszFileName[v3 - 1] != 92 )
      v7 = v3;
    v8 = v7 == v6;
    CoTaskMemFree(v5);
    lpszVolumePathName = 0;
    v22[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v22);
    return v8;
  }
  else
  {
    CoTaskMemFree(0);
    lpszVolumePathName = 0;
    v22[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v22);
    return 0;
  }
}

```

## disassembly

```asm
0x18007ecc8  push    rbp
0x18007ecca  push    rbx
0x18007eccb  push    rsi
0x18007eccc  push    rdi
0x18007eccd  push    r12
0x18007eccf  push    r13
0x18007ecd1  push    r14
0x18007ecd3  push    r15
0x18007ecd5  lea     rbp, [rsp-0A8h]
0x18007ecdd  sub     rsp, 1A8h
0x18007ece4  mov     rax, cs:__security_cookie
0x18007eceb  xor     rax, rsp
0x18007ecee  mov     [rbp+0E0h+var_50], rax
0x18007ecf5  mov     r14, rcx
0x18007ecf8  lea     rax, [rsp+1E0h+var_190]
0x18007ecfd  mov     [rsp+1E0h+var_198], rax
0x18007ed02  lea     r12, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\volume\\srmv"...
0x18007ed09  mov     [rsp+1E0h+var_190], r12
0x18007ed0e  lea     r13, aIsvolumerootpa; "IsVolumeRootPath"
0x18007ed15  mov     [rsp+1E0h+var_188], r13
0x18007ed1a  lea     rax, aSrmvolmc; "SRMVOLMC"
0x18007ed21  mov     [rsp+1E0h+var_180], rax
0x18007ed26  mov     [rsp+1E0h+var_178], 3A2h
0x18007ed2e  mov     [rsp+1E0h+var_174], 11h
0x18007ed36  mov     [rsp+1E0h+var_170], 0FFh
0x18007ed3e  xor     r15d, r15d
0x18007ed41  mov     [rbp+0E0h+var_108], 1000000h
0x18007ed48  xor     edx, edx; Val
0x18007ed4a  lea     r8d, [r15+60h]; Size
0x18007ed4e  lea     rcx, [rsp+1E0h+var_168]; void *
0x18007ed53  call    memset_0
0x18007ed58  nop
0x18007ed59  xor     r8d, r8d
0x18007ed5c  lea     rdx, [rsp+1E0h+var_190]
0x18007ed61  lea     rcx, [rbp+0E0h+var_100]
0x18007ed65  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007ed6a  nop
0x18007ed6b  mov     [rsp+1E0h+lpszVolumePathName], r15
0x18007ed70  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007ed74  mov     rbx, rdi
0x18007ed77  inc     rbx
0x18007ed7a  cmp     [r14+rbx*2], r15w
0x18007ed7f  jnz     short loc_18007ED77
0x18007ed81  test    rbx, rbx
0x18007ed84  jnz     short loc_18007EDB3
0x18007ed86  xor     ecx, ecx; pv
0x18007ed88  call    cs:__imp_CoTaskMemFree
0x18007ed8e  mov     [rsp+1E0h+lpszVolumePathName], r15
0x18007ed93  mov     [rsp+1E0h+lpszVolumePathName], r15
0x18007ed98  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007ed9f  mov     [rbp+0E0h+var_100], rax
0x18007eda3  lea     rcx, [rbp+0E0h+var_100]; this
0x18007eda7  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007edac  xor     eax, eax
0x18007edae  jmp     loc_18007EE9F
0x18007edb3  lea     rdx, [rbx+1]; unsigned __int64
0x18007edb7  lea     rcx, [rsp+1E0h+lpszVolumePathName]; this
0x18007edbc  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007edc1  lea     r8d, [rbx+2]; cchBufferLength
0x18007edc5  mov     rsi, [rsp+1E0h+lpszVolumePathName]
0x18007edca  mov     rdx, rsi; lpszVolumePathName
0x18007edcd  mov     rcx, r14; lpszFileName
0x18007edd0  call    cs:__imp_GetVolumePathNameW
0x18007edd6  test    eax, eax
0x18007edd8  jz      loc_18007EEC2
0x18007edde  lea     rax, [rsp+1E0h+var_190]
0x18007ede3  mov     [rsp+1E0h+var_198], rax
0x18007ede8  mov     [rsp+1E0h+var_190], r12
0x18007eded  mov     [rsp+1E0h+var_188], r13
0x18007edf2  lea     rax, aSrmvolmc; "SRMVOLMC"
0x18007edf9  mov     [rsp+1E0h+var_180], rax
0x18007edfe  mov     [rsp+1E0h+var_178], 3B8h
0x18007ee06  mov     [rsp+1E0h+var_174], 11h
0x18007ee0e  mov     [rsp+1E0h+var_170], 0FFh
0x18007ee16  mov     [rbp+0E0h+var_108], 1000000h
0x18007ee1d  xor     edx, edx; Val
0x18007ee1f  lea     r8d, [rdx+60h]; Size
0x18007ee23  lea     rcx, [rsp+1E0h+var_168]; void *
0x18007ee28  call    memset_0
0x18007ee2d  nop
0x18007ee2e  mov     r9, rsi
0x18007ee31  lea     r8, aVolumeRootIsS; "Volume root is %s"
0x18007ee38  lea     rdx, [rsp+1E0h+var_190]
0x18007ee3d  lea     rcx, [rbp+0E0h+var_100]
0x18007ee41  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007ee46  inc     rdi
0x18007ee49  cmp     [rsi+rdi*2], r15w
0x18007ee4e  jnz     short loc_18007EE46
0x18007ee50  lea     rdx, [rdi-1]
0x18007ee54  cmp     word ptr [rsi+rdi*2-2], 5Ch ; '\'
0x18007ee5a  cmovnz  rdx, rdi
0x18007ee5e  lea     rax, [rbx-1]
0x18007ee62  cmp     word ptr [r14+rbx*2-2], 5Ch ; '\'
0x18007ee69  cmovnz  rax, rbx
0x18007ee6d  mov     ebx, r15d
0x18007ee70  cmp     rax, rdx
0x18007ee73  setz    bl
0x18007ee76  mov     rcx, rsi; pv
0x18007ee79  call    cs:__imp_CoTaskMemFree
0x18007ee7f  mov     [rsp+1E0h+lpszVolumePathName], r15
0x18007ee84  mov     [rsp+1E0h+lpszVolumePathName], r15
0x18007ee89  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007ee90  mov     [rbp+0E0h+var_100], rax
0x18007ee94  lea     rcx, [rbp+0E0h+var_100]; this
0x18007ee98  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007ee9d  mov     eax, ebx
0x18007ee9f  mov     rcx, [rbp+0E0h+var_50]
0x18007eea6  xor     rcx, rsp; StackCookie
0x18007eea9  call    __security_check_cookie
0x18007eeae  add     rsp, 1A8h
0x18007eeb5  pop     r15
0x18007eeb7  pop     r14
0x18007eeb9  pop     r13
0x18007eebb  pop     r12
0x18007eebd  pop     rdi
0x18007eebe  pop     rsi
0x18007eebf  pop     rbx
0x18007eec0  pop     rbp
0x18007eec1  retn
0x18007eec2  call    cs:__imp_GetLastError
0x18007eec8  nop
0x18007eec9  test    eax, eax
0x18007eecb  jle     short loc_18007EED5
0x18007eecd  movzx   eax, ax
0x18007eed0  or      eax, 80070000h
0x18007eed5  mov     edx, eax; int
0x18007eed7  lea     rcx, [rbp+0E0h+var_100]; this
0x18007eedb  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18007eee0  lea     rcx, [rbp+0E0h+var_100]; this
0x18007eee4  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007eee9  mov     ebx, eax
0x18007eeeb  lea     rax, [rsp+1E0h+var_190]
0x18007eef0  mov     [rsp+1E0h+var_198], rax
0x18007eef5  mov     [rsp+1E0h+var_1B8], 11h
0x18007eefd  mov     [rsp+1E0h+var_1C0], 3B3h
0x18007ef05  mov     r9, r13
0x18007ef08  lea     r8, aSrmvolmc; "SRMVOLMC"
0x18007ef0f  mov     rdx, r12
0x18007ef12  lea     rcx, [rsp+1E0h+var_190]
0x18007ef17  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007ef1c  nop
0x18007ef1d  lea     r9, aGetvolumepathn_1; "GetVolumePathName"
0x18007ef24  mov     r8d, ebx
0x18007ef27  mov     rdx, rax
0x18007ef2a  lea     rcx, [rbp+0E0h+var_100]
0x18007ef2e  call    ?TranslatePathError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslatePathError(CSrmDebugInfo,long,ushort const *,...)
```

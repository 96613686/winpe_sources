# CSrmAutoPWSZ::ExpandEnvironmentStringsW(ushort const *)

- ea: `0x1800a3c00`
- end: `0x1800a3e2c`
- name: `?ExpandEnvironmentStringsW@CSrmAutoPWSZ@@QEAAXPEBG@Z`
- size: `556`
- prototype: `void __fastcall(CSrmAutoPWSZ *__hidden this, LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800a46cc`

## callees

- `0x18000ad14`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x1800744a8`
- `0x180075034`
- `0x1800a3c00`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800a3ce8`
- `ole32!CoTaskMemFree` at `0x1800a3d64`
- `ole32!CoTaskMemFree` at `0x1800a3ce8`
- `ole32!CoTaskMemFree` at `0x1800a3d64`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800a3cb8`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800a3d53`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800a3cb8`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800a3d53`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CSrmAutoPWSZ::ExpandEnvironmentStringsW(LPVOID *this, LPCWSTR lpSrc)
{
  DWORD v4; // eax
  DWORD v5; // edi
  WCHAR *v6; // rsi
  DWORD v7; // eax
  __int64 v8; // rax
  LPVOID v9; // rbx
  __int64 v10; // rax
  __int64 v11; // [rsp+28h] [rbp-D8h]
  _QWORD v12[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[3]; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+68h] [rbp-98h]
  int v15; // [rsp+6Ch] [rbp-94h]
  int v16; // [rsp+70h] [rbp-90h]
  _BYTE v17[96]; // [rsp+78h] [rbp-88h] BYREF
  int v18; // [rsp+D8h] [rbp-28h]
  _BYTE v19[144]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v20[22]; // [rsp+170h] [rbp+70h] BYREF

  v12[0] = v13;
  v13[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h";
  v13[1] = L"CSrmAutoPWSZ::ExpandEnvironmentStringsW";
  v13[2] = L"INCLSTRH";
  v14 = 452;
  v15 = 17;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v20, (const struct CSrmDebugInfo *)v13, 0);
  if ( !lpSrc )
    lpSrc = (LPCWSTR)*this;
  v4 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
  v5 = v4;
  if ( !v4 )
  {
    v12[0] = v19;
    v8 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v19,
           (__int64)L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h",
           (__int64)L"INCLSTRH",
           (__int64)L"CSrmAutoPWSZ::ExpandEnvironmentStringsW",
           461,
           17);
    CSrmFunctionTracer::TranslateWin32Error(v20, v8, L"ExpandEnvironmentString(%s, NULL, 0)", lpSrc);
  }
  v12[0] = 0;
  v6 = (WCHAR *)*this;
  *this = 0;
  v12[0] = v6;
  if ( v4 != 1 )
  {
    CSrmAutoPWSZ::Allocate(this, v4);
    v7 = ExpandEnvironmentStringsW(lpSrc, (LPWSTR)*this, v5);
    if ( !v7 || v7 > v5 )
    {
      CSrmAutoPWSZ::TransferFrom((CSrmAutoPWSZ *)this, (struct CSrmAutoPWSZ *)v12);
      v9 = *this;
      v12[1] = v19;
      v10 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v19,
              (__int64)L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h",
              (__int64)L"INCLSTRH",
              (__int64)L"CSrmAutoPWSZ::ExpandEnvironmentStringsW",
              474,
              17);
      LODWORD(v11) = v5;
      CSrmFunctionTracer::TranslateWin32Error(v20, v10, L"ExpandEnvironmentString(%s, %p, %d)", lpSrc, v9, v11);
    }
  }
  CoTaskMemFree(v6);
  v12[0] = 0;
  v20[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v20);
}

```

## disassembly

```asm
0x1800a3c00  mov     [rsp-8+arg_10], rbx
0x1800a3c05  mov     [rsp-8+arg_18], rsi
0x1800a3c0a  push    rbp
0x1800a3c0b  push    rdi
0x1800a3c0c  push    r12
0x1800a3c0e  push    r13
0x1800a3c10  push    r14
0x1800a3c12  lea     rbp, [rsp-130h]
0x1800a3c1a  sub     rsp, 230h
0x1800a3c21  mov     rax, cs:__security_cookie
0x1800a3c28  xor     rax, rsp
0x1800a3c2b  mov     [rbp+150h+var_30], rax
0x1800a3c32  mov     r14, rdx
0x1800a3c35  mov     rbx, rcx
0x1800a3c38  lea     rax, [rsp+250h+var_200]
0x1800a3c3d  mov     [rsp+250h+var_210], rax
0x1800a3c42  lea     r12, aBaseFsFsrmUtil_8; "base\\fs\\fsrm\\utilities\\inc\\srmstr."...
0x1800a3c49  mov     [rsp+250h+var_200], r12
0x1800a3c4e  lea     r13, aCsrmautopwszEx; "CSrmAutoPWSZ::ExpandEnvironmentStringsW"
0x1800a3c55  mov     [rsp+250h+var_1F8], r13
0x1800a3c5a  lea     rsi, aInclstrh; "INCLSTRH"
0x1800a3c61  mov     [rsp+250h+var_1F0], rsi
0x1800a3c66  mov     [rsp+250h+var_1E8], 1C4h
0x1800a3c6e  mov     [rsp+250h+var_1E4], 11h
0x1800a3c76  mov     [rsp+250h+var_1E0], 0FFh
0x1800a3c7e  mov     [rbp+150h+var_178], 1000000h
0x1800a3c85  xor     edx, edx; Val
0x1800a3c87  lea     r8d, [rdx+60h]; Size
0x1800a3c8b  lea     rcx, [rsp+250h+var_1D8]; void *
0x1800a3c90  call    memset_0
0x1800a3c95  nop
0x1800a3c96  xor     r8d, r8d
0x1800a3c99  lea     rdx, [rsp+250h+var_200]
0x1800a3c9e  lea     rcx, [rbp+150h+var_E0]
0x1800a3ca2  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800a3ca7  nop
0x1800a3ca8  test    r14, r14
0x1800a3cab  jnz     short loc_1800A3CB0
0x1800a3cad  mov     r14, [rbx]
0x1800a3cb0  xor     r8d, r8d; nSize
0x1800a3cb3  xor     edx, edx; lpDst
0x1800a3cb5  mov     rcx, r14; lpSrc
0x1800a3cb8  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a3cbe  mov     edi, eax
0x1800a3cc0  test    eax, eax
0x1800a3cc2  jz      loc_1800A3D89
0x1800a3cc8  mov     [rsp+250h+var_210], 0
0x1800a3cd1  mov     rsi, [rbx]
0x1800a3cd4  mov     qword ptr [rbx], 0
0x1800a3cdb  mov     [rsp+250h+var_210], rsi
0x1800a3ce0  cmp     edi, 1
0x1800a3ce3  jnz     short loc_1800A3D3F
0x1800a3ce5  mov     rcx, rsi; pv
0x1800a3ce8  call    cs:__imp_CoTaskMemFree
0x1800a3cee  mov     [rsp+250h+var_210], 0
0x1800a3cf7  mov     [rsp+250h+var_210], 0
0x1800a3d00  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a3d07  mov     [rbp+150h+var_E0], rax
0x1800a3d0b  lea     rcx, [rbp+150h+var_E0]; this
0x1800a3d0f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800a3d14  mov     rcx, [rbp+150h+var_30]
0x1800a3d1b  xor     rcx, rsp; StackCookie
0x1800a3d1e  call    __security_check_cookie
0x1800a3d23  lea     r11, [rsp+250h+var_20]
0x1800a3d2b  mov     rbx, [r11+40h]
0x1800a3d2f  mov     rsi, [r11+48h]
0x1800a3d33  mov     rsp, r11
0x1800a3d36  pop     r14
0x1800a3d38  pop     r13
0x1800a3d3a  pop     r12
0x1800a3d3c  pop     rdi
0x1800a3d3d  pop     rbp
0x1800a3d3e  retn
0x1800a3d3f  mov     rdx, rdi; unsigned __int64
0x1800a3d42  mov     rcx, rbx; this
0x1800a3d45  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x1800a3d4a  mov     r8d, edi; nSize
0x1800a3d4d  mov     rdx, [rbx]; lpDst
0x1800a3d50  mov     rcx, r14; lpSrc
0x1800a3d53  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a3d59  test    eax, eax
0x1800a3d5b  jz      short loc_1800A3DCC
0x1800a3d5d  cmp     eax, edi
0x1800a3d5f  ja      short loc_1800A3DCC
0x1800a3d61  mov     rcx, rsi; pv
0x1800a3d64  call    cs:__imp_CoTaskMemFree
0x1800a3d6a  mov     [rsp+250h+var_210], 0
0x1800a3d73  mov     [rsp+250h+var_210], 0
0x1800a3d7c  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a3d83  mov     [rbp+150h+var_E0], rax
0x1800a3d87  jmp     short loc_1800A3D0B
0x1800a3d89  lea     rax, [rbp+150h+var_170]
0x1800a3d8d  mov     [rsp+250h+var_210], rax
0x1800a3d92  mov     dword ptr [rsp+250h+var_228], 11h
0x1800a3d9a  mov     dword ptr [rsp+250h+var_230], 1CDh
0x1800a3da2  mov     r9, r13
0x1800a3da5  mov     r8, rsi
0x1800a3da8  mov     rdx, r12
0x1800a3dab  lea     rcx, [rbp+150h+var_170]
0x1800a3daf  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a3db4  nop
0x1800a3db5  mov     r9, r14
0x1800a3db8  lea     r8, aExpandenvironm; "ExpandEnvironmentString(%s, NULL, 0)"
0x1800a3dbf  mov     rdx, rax
0x1800a3dc2  lea     rcx, [rbp+150h+var_E0]
0x1800a3dc6  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
0x1800a3dcc  lea     rdx, [rsp+250h+var_210]; struct CSrmAutoPWSZ *
0x1800a3dd1  mov     rcx, rbx; this
0x1800a3dd4  call    ?TransferFrom@CSrmAutoPWSZ@@QEAAXAEAV1@@Z; CSrmAutoPWSZ::TransferFrom(CSrmAutoPWSZ &)
0x1800a3dd9  mov     rbx, [rbx]
0x1800a3ddc  lea     rax, [rbp+150h+var_170]
0x1800a3de0  mov     [rsp+250h+var_208], rax
0x1800a3de5  mov     dword ptr [rsp+250h+var_228], 11h
0x1800a3ded  mov     dword ptr [rsp+250h+var_230], 1DAh
0x1800a3df5  mov     r9, r13
0x1800a3df8  lea     r8, aInclstrh; "INCLSTRH"
0x1800a3dff  mov     rdx, r12
0x1800a3e02  lea     rcx, [rbp+150h+var_170]
0x1800a3e06  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a3e0b  nop
0x1800a3e0c  mov     dword ptr [rsp+250h+var_228], edi
0x1800a3e10  mov     [rsp+250h+var_230], rbx
0x1800a3e15  mov     r9, r14
0x1800a3e18  lea     r8, aExpandenvironm_0; "ExpandEnvironmentString(%s, %p, %d)"
0x1800a3e1f  mov     rdx, rax
0x1800a3e22  lea     rcx, [rbp+150h+var_E0]
0x1800a3e26  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
```

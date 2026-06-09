# SrmIsPathParent(ushort const *,ushort const *,bool,bool)

- ea: `0x18007d914`
- end: `0x18007dbb9`
- name: `?SrmIsPathParent@@YA_NPEBG0_N1@Z`
- size: `677`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *, bool, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180095680`

## callees

- `0x18000af40`
- `0x18006febc`
- `0x1800700b8`
- `0x18007d914`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18007da72`
- `msvcrt!_wcsnicmp` at `0x18007da72`
- `ole32!CoTaskMemFree` at `0x18007da95`
- `ole32!CoTaskMemFree` at `0x18007daaa`
- `ole32!CoTaskMemFree` at `0x18007dae3`
- `ole32!CoTaskMemFree` at `0x18007daf8`
- `ole32!CoTaskMemFree` at `0x18007db2d`
- `ole32!CoTaskMemFree` at `0x18007db42`
- `ole32!CoTaskMemFree` at `0x18007da95`
- `ole32!CoTaskMemFree` at `0x18007daaa`
- `ole32!CoTaskMemFree` at `0x18007dae3`
- `ole32!CoTaskMemFree` at `0x18007daf8`
- `ole32!CoTaskMemFree` at `0x18007db2d`
- `ole32!CoTaskMemFree` at `0x18007db42`

## string_xrefs

- `0x18007d948`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007d962`: `SRMPATHC`
- `0x18007d954`: `SrmIsPathParent`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
char __fastcall SrmIsPathParent(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  char v4; // si
  wchar_t *v5; // rcx
  unsigned __int64 v6; // rdi
  size_t v7; // rbx
  wchar_t *v8; // rdx
  wchar_t *String2; // [rsp+40h] [rbp-1A8h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-1A0h] BYREF
  size_t v12; // [rsp+58h] [rbp-190h]
  unsigned __int64 v13; // [rsp+60h] [rbp-188h]
  _QWORD v14[4]; // [rsp+78h] [rbp-170h] BYREF
  int v15; // [rsp+98h] [rbp-150h]
  _DWORD v16[28]; // [rsp+A0h] [rbp-148h] BYREF
  _QWORD v17[22]; // [rsp+110h] [rbp-D8h] BYREF

  v14[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v14[1] = L"SrmIsPathParent";
  v14[2] = L"SRMPATHC";
  v14[3] = 908;
  v15 = 255;
  v16[24] = 0x1000000;
  v4 = 1;
  memset_0(v16, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v17, (const struct CSrmDebugInfo *)v14, 0);
  String1 = 0;
  String2 = 0;
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&String1, a1);
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&String2, a2);
  v5 = String1;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( String1[v7] );
  v12 = v7;
  v8 = String2;
  do
    ++v6;
  while ( String2[v6] );
  v13 = v6;
  if ( v7 && String1[v7 - 1] == 92 )
  {
    String1[--v7] = 0;
    v12 = v7;
    v5 = String1;
    v8 = String2;
  }
  if ( v6 && v8[v6 - 1] == 92 )
  {
    v8[--v6] = 0;
    v13 = v6;
    v5 = String1;
    v8 = String2;
  }
  if ( !v7 || v7 > v6 || _wcsnicmp(v5, v8, v7) )
  {
    CoTaskMemFree(String2);
    String2 = 0;
    CoTaskMemFree(String1);
    String1 = 0;
    v17[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v17);
    return 0;
  }
  else
  {
    if ( v7 != v6 && String2[v7] != 92 )
      v4 = 0;
    CoTaskMemFree(String2);
    String2 = 0;
    CoTaskMemFree(String1);
    String1 = 0;
    v17[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v17);
    return v4;
  }
}

```

## disassembly

```asm
0x18007d914  mov     r11, rsp
0x18007d917  mov     [r11+18h], rbx
0x18007d91b  push    rsi
0x18007d91c  push    rdi
0x18007d91d  push    r14
0x18007d91f  sub     rsp, 1D0h
0x18007d926  mov     rax, cs:__security_cookie
0x18007d92d  xor     rax, rsp
0x18007d930  mov     [rsp+1E8h+var_28], rax
0x18007d938  mov     rdi, rdx
0x18007d93b  mov     rbx, rcx
0x18007d93e  lea     rax, [rsp+1E8h+var_170]
0x18007d943  mov     [rsp+1E8h+String1], rax
0x18007d948  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007d94f  mov     [rsp+1E8h+var_170], rax
0x18007d954  lea     rax, aSrmispathparen; "SrmIsPathParent"
0x18007d95b  mov     [r11-168h], rax
0x18007d962  lea     rax, aSrmpathc; "SRMPATHC"
0x18007d969  mov     [r11-160h], rax
0x18007d970  mov     qword ptr [r11-158h], 38Ch
0x18007d97b  xor     r14d, r14d
0x18007d97e  mov     [rsp+1E8h+var_150], 0FFh
0x18007d989  mov     [rsp+1E8h+var_E8], 1000000h
0x18007d994  mov     sil, 1
0x18007d997  xor     edx, edx; Val
0x18007d999  lea     r8d, [r14+60h]; Size
0x18007d99d  lea     rcx, [r11-148h]; void *
0x18007d9a4  call    memset_0
0x18007d9a9  nop
0x18007d9aa  xor     r8d, r8d
0x18007d9ad  lea     rdx, [rsp+1E8h+var_170]
0x18007d9b2  lea     rcx, [rsp+1E8h+var_D8]
0x18007d9ba  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007d9bf  nop
0x18007d9c0  mov     [rsp+1E8h+String1], r14
0x18007d9c5  mov     [rsp+1E8h+String2], r14
0x18007d9ca  mov     rdx, rbx; unsigned __int16 *
0x18007d9cd  lea     rcx, [rsp+1E8h+String1]; this
0x18007d9d2  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007d9d7  mov     rdx, rdi; unsigned __int16 *
0x18007d9da  lea     rcx, [rsp+1E8h+String2]; this
0x18007d9df  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007d9e4  mov     rcx, [rsp+1E8h+String1]
0x18007d9e9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007d9ed  mov     rbx, rdi
0x18007d9f0  inc     rbx
0x18007d9f3  cmp     [rcx+rbx*2], r14w
0x18007d9f8  jnz     short loc_18007D9F0
0x18007d9fa  mov     [rsp+1E8h+var_190], rbx
0x18007d9ff  mov     rdx, [rsp+1E8h+String2]
0x18007da04  inc     rdi
0x18007da07  cmp     [rdx+rdi*2], r14w
0x18007da0c  jnz     short loc_18007DA04
0x18007da0e  mov     [rsp+1E8h+var_188], rdi
0x18007da13  test    rbx, rbx
0x18007da16  jz      short loc_18007DA38
0x18007da18  cmp     word ptr [rcx+rbx*2-2], 5Ch ; '\'
0x18007da1e  jnz     short loc_18007DA38
0x18007da20  mov     [rcx+rbx*2-2], r14w
0x18007da26  dec     rbx
0x18007da29  mov     [rsp+1E8h+var_190], rbx
0x18007da2e  mov     rcx, [rsp+1E8h+String1]
0x18007da33  mov     rdx, [rsp+1E8h+String2]
0x18007da38  test    rdi, rdi
0x18007da3b  jz      short loc_18007DA5D
0x18007da3d  cmp     word ptr [rdx+rdi*2-2], 5Ch ; '\'
0x18007da43  jnz     short loc_18007DA5D
0x18007da45  mov     [rdx+rdi*2-2], r14w
0x18007da4b  dec     rdi
0x18007da4e  mov     [rsp+1E8h+var_188], rdi
0x18007da53  mov     rcx, [rsp+1E8h+String1]; String1
0x18007da58  mov     rdx, [rsp+1E8h+String2]; String2
0x18007da5d  test    rbx, rbx
0x18007da60  jz      loc_18007DB28
0x18007da66  cmp     rbx, rdi
0x18007da69  ja      loc_18007DB28
0x18007da6f  mov     r8, rbx; MaxCount
0x18007da72  call    cs:__imp__wcsnicmp
0x18007da78  test    eax, eax
0x18007da7a  jnz     short loc_18007DADE
0x18007da7c  cmp     rbx, rdi
0x18007da7f  jz      short loc_18007DA90
0x18007da81  mov     rax, [rsp+1E8h+String2]
0x18007da86  cmp     word ptr [rax+rbx*2], 5Ch ; '\'
0x18007da8b  jz      short loc_18007DA90
0x18007da8d  mov     sil, r14b
0x18007da90  mov     rcx, [rsp+1E8h+String2]; pv
0x18007da95  call    cs:__imp_CoTaskMemFree
0x18007da9b  mov     [rsp+1E8h+String2], r14
0x18007daa0  mov     [rsp+1E8h+String2], r14
0x18007daa5  mov     rcx, [rsp+1E8h+String1]; pv
0x18007daaa  call    cs:__imp_CoTaskMemFree
0x18007dab0  mov     [rsp+1E8h+String1], r14
0x18007dab5  mov     [rsp+1E8h+String1], r14
0x18007daba  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007dac1  mov     [rsp+1E8h+var_D8], rax
0x18007dac9  lea     rcx, [rsp+1E8h+var_D8]; this
0x18007dad1  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007dad6  mov     al, sil
0x18007dad9  jmp     loc_18007DB90
0x18007dade  mov     rcx, [rsp+1E8h+String2]; pv
0x18007dae3  call    cs:__imp_CoTaskMemFree
0x18007dae9  mov     [rsp+1E8h+String2], r14
0x18007daee  mov     [rsp+1E8h+String2], r14
0x18007daf3  mov     rcx, [rsp+1E8h+String1]; pv
0x18007daf8  call    cs:__imp_CoTaskMemFree
0x18007dafe  mov     [rsp+1E8h+String1], r14
0x18007db03  mov     [rsp+1E8h+String1], r14
0x18007db08  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007db0f  mov     [rsp+1E8h+var_D8], rax
0x18007db17  lea     rcx, [rsp+1E8h+var_D8]; this
0x18007db1f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007db24  xor     al, al
0x18007db26  jmp     short loc_18007DB90
0x18007db28  mov     rcx, [rsp+1E8h+String2]; pv
0x18007db2d  call    cs:__imp_CoTaskMemFree
0x18007db33  mov     [rsp+1E8h+String2], r14
0x18007db38  mov     [rsp+1E8h+String2], r14
0x18007db3d  mov     rcx, [rsp+1E8h+String1]; pv
0x18007db42  call    cs:__imp_CoTaskMemFree
0x18007db48  mov     [rsp+1E8h+String1], r14
0x18007db4d  mov     [rsp+1E8h+String1], r14
0x18007db52  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007db59  mov     [rsp+1E8h+var_D8], rax
0x18007db61  lea     rcx, [rsp+1E8h+var_D8]; this
0x18007db69  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007db6e  xor     al, al
0x18007db70  jmp     short loc_18007DB90
0x18007db72  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007db79  mov     [rsp+1E8h+var_D8], rax
0x18007db81  lea     rcx, [rsp+1E8h+var_D8]; this
0x18007db89  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007db8e  xor     al, al
0x18007db90  mov     rcx, [rsp+1E8h+var_28]
0x18007db98  xor     rcx, rsp; StackCookie
0x18007db9b  call    __security_check_cookie
0x18007dba0  mov     rbx, [rsp+1E8h+arg_10]
0x18007dba8  add     rsp, 1D0h
0x18007dbaf  pop     r14
0x18007dbb1  pop     rdi
0x18007dbb2  pop     rsi
0x18007dbb3  retn
0x18007dbb4  jmp     short loc_18007DB72
0x18007dbb6  jmp     short loc_18007DB72
```

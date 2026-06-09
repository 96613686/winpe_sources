# CScanInformation::GetNamespaceVolumePathsLight(ushort const *,CSrmAutoPWSZ &,CSrmAutoPWSZ &,CSrmAutoPWSZ &,CSrmAutoPWSZ &)

- ea: `0x180051278`
- end: `0x1800513f1`
- name: `?GetNamespaceVolumePathsLight@CScanInformation@@SAXPEBGAEAVCSrmAutoPWSZ@@111@Z`
- size: `377`
- prototype: `void __fastcall(const unsigned __int16 *, struct CSrmAutoPWSZ *this, struct CSrmAutoPWSZ *, struct CSrmAutoPWSZ *, struct CSrmAutoPWSZ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x180096d3c`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000af40`
- `0x180051278`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!wcschr` at `0x180051348`
- `msvcrt!wcschr` at `0x18005135b`
- `msvcrt!wcschr` at `0x180051348`
- `msvcrt!wcschr` at `0x18005135b`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18005132f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18005132f`

## string_xrefs

- `0x1800512bb`: `base\fs\fsrm\service\pipeline\namespace.cpp`
- `0x1800512c7`: `CScanInformation::GetNamespaceVolumePathsLight`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CScanInformation::GetNamespaceVolumePathsLight(
        const unsigned __int16 *a1,
        LPVOID *this,
        LPVOID *a3,
        LPVOID *a4,
        LPVOID *a5)
{
  wchar_t *v9; // rax
  wchar_t *v10; // rax
  char Hr; // al
  _QWORD v12[3]; // [rsp+28h] [rbp-D8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+44h] [rbp-BCh]
  int v15; // [rsp+48h] [rbp-B8h]
  _BYTE v16[96]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+B0h] [rbp-50h]
  void **v18; // [rsp+C0h] [rbp-40h] BYREF
  int v19; // [rsp+C8h] [rbp-38h]

  v12[0] = L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp";
  v12[1] = L"CScanInformation::GetNamespaceVolumePathsLight";
  v12[2] = L"NAMESPCC";
  v13 = 712;
  v14 = 22;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v18, (const struct CSrmDebugInfo *)v12, 0);
  CSrmAutoPWSZ::CopyFrom(this, a1);
  PathRemoveFileSpecW((LPWSTR)*this);
  CSrmAutoPWSZ::CopyFrom(a3, (const unsigned __int16 *)*this);
  v9 = wcschr((const wchar_t *)*a3, 0x7Du);
  if ( !v9 || (v10 = wcschr(v9, 0x5Cu)) == 0 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v18, -2147024809);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v18);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v18, 0x2DDu, Hr, 0, v12);
  }
  v10[1] = 0;
  CSrmAutoPWSZ::CopyFrom(a4, (const unsigned __int16 *)*a3);
  CSrmAutoPWSZ::CopyFrom(a5, (const unsigned __int16 *)*a3);
  v19 = 0;
  v18 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v18);
}

```

## disassembly

```asm
0x180051278  push    rbp
0x18005127a  push    rbx
0x18005127b  push    rsi
0x18005127c  push    rdi
0x18005127d  push    r14
0x18005127f  push    r15
0x180051281  lea     rbp, [rsp-88h]
0x180051289  sub     rsp, 188h
0x180051290  mov     rax, cs:__security_cookie
0x180051297  xor     rax, rsp
0x18005129a  mov     [rbp+0B0h+var_40], rax
0x18005129e  mov     r14, r9
0x1800512a1  mov     rsi, r8
0x1800512a4  mov     rdi, rdx
0x1800512a7  mov     rbx, rcx
0x1800512aa  mov     r15, [rbp+0B0h+arg_20]
0x1800512b1  lea     rax, [rsp+1B0h+var_188]
0x1800512b6  mov     [rsp+1B0h+var_190], rax
0x1800512bb  lea     rax, aBaseFsFsrmServ_34; "base\\fs\\fsrm\\service\\pipeline\\name"...
0x1800512c2  mov     [rsp+1B0h+var_188], rax
0x1800512c7  lea     rax, aCscaninformati_7; "CScanInformation::GetNamespaceVolumePat"...
0x1800512ce  mov     [rsp+1B0h+var_180], rax
0x1800512d3  lea     rax, aNamespcc; "NAMESPCC"
0x1800512da  mov     [rsp+1B0h+var_178], rax
0x1800512df  mov     [rsp+1B0h+var_170], 2C8h
0x1800512e7  mov     [rsp+1B0h+var_16C], 16h
0x1800512ef  mov     [rsp+1B0h+var_168], 0FFh
0x1800512f7  mov     [rbp+0B0h+var_100], 1000000h
0x1800512fe  xor     edx, edx; Val
0x180051300  lea     r8d, [rdx+60h]; Size
0x180051304  lea     rcx, [rsp+1B0h+var_160]; void *
0x180051309  call    memset_0
0x18005130e  nop
0x18005130f  xor     r8d, r8d
0x180051312  lea     rdx, [rsp+1B0h+var_188]
0x180051317  lea     rcx, [rbp+0B0h+var_F0]
0x18005131b  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180051320  nop
0x180051321  mov     rdx, rbx; unsigned __int16 *
0x180051324  mov     rcx, rdi; this
0x180051327  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18005132c  mov     rcx, [rdi]; pszPath
0x18005132f  call    cs:__imp_PathRemoveFileSpecW
0x180051335  mov     rdx, [rdi]; unsigned __int16 *
0x180051338  mov     rcx, rsi; this
0x18005133b  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180051340  mov     edx, 7Dh ; '}'; Ch
0x180051345  mov     rcx, [rsi]; Str
0x180051348  call    cs:__imp_wcschr
0x18005134e  test    rax, rax
0x180051351  jz      short loc_1800513BF
0x180051353  mov     edx, 5Ch ; '\'; Ch
0x180051358  mov     rcx, rax; Str
0x18005135b  call    cs:__imp_wcschr
0x180051361  test    rax, rax
0x180051364  jz      short loc_1800513BF
0x180051366  xor     edx, edx
0x180051368  mov     [rax+2], dx
0x18005136c  mov     rdx, [rsi]; unsigned __int16 *
0x18005136f  mov     rcx, r14; this
0x180051372  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180051377  mov     rdx, [rsi]; unsigned __int16 *
0x18005137a  mov     rcx, r15; this
0x18005137d  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180051382  mov     eax, [rbp+0B0h+var_E8]
0x180051385  mov     [rbp+0B0h+var_E8], eax
0x180051388  mov     [rbp+0B0h+var_E8], 0
0x18005138f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180051396  mov     [rbp+0B0h+var_F0], rax
0x18005139a  lea     rcx, [rbp+0B0h+var_F0]; this
0x18005139e  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800513a3  mov     rcx, [rbp+0B0h+var_40]
0x1800513a7  xor     rcx, rsp; StackCookie
0x1800513aa  call    __security_check_cookie
0x1800513af  add     rsp, 188h
0x1800513b6  pop     r15
0x1800513b8  pop     r14
0x1800513ba  pop     rdi
0x1800513bb  pop     rsi
0x1800513bc  pop     rbx
0x1800513bd  pop     rbp
0x1800513be  retn
0x1800513bf  mov     eax, [rbp+0B0h+var_E8]
0x1800513c2  mov     [rbp+0B0h+var_E8], eax
0x1800513c5  mov     edx, 80070057h; int
0x1800513ca  lea     rcx, [rbp+0B0h+var_F0]; this
0x1800513ce  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800513d3  lea     rcx, [rbp+0B0h+var_F0]; this
0x1800513d7  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800513dc  mov     r8d, eax; char
0x1800513df  xor     r9d, r9d; unsigned __int16 *
0x1800513e2  mov     edx, 2DDh; unsigned int
0x1800513e7  lea     rcx, [rbp+0B0h+var_F0]; this
0x1800513eb  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```

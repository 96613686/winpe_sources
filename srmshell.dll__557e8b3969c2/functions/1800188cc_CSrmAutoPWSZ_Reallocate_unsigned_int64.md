# CSrmAutoPWSZ::Reallocate(unsigned __int64)

- ea: `0x1800188cc`
- end: `0x180018ae9`
- name: `?Reallocate@CSrmAutoPWSZ@@QEAAX_K@Z`
- size: `541`
- prototype: `void __fastcall(LPVOID *this, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016f34`
- `0x180018af0`

## callees

- `0x1800083e0`
- `0x1800161e8`
- `0x18001623c`
- `0x180016564`
- `0x1800188cc`
- `0x1800191ec`
- `0x180019b84`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800189aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800189aa`

## pseudocode

```c
void __fastcall CSrmAutoPWSZ::Reallocate(LPVOID *this, unsigned __int64 a2)
{
  LPVOID v4; // rax
  __int64 v5; // rax
  unsigned int Hr; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  _QWORD v9[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v10; // [rsp+60h] [rbp-A0h]
  int v11; // [rsp+64h] [rbp-9Ch]
  int v12; // [rsp+68h] [rbp-98h]
  _BYTE v13[96]; // [rsp+70h] [rbp-90h] BYREF
  int v14; // [rsp+D0h] [rbp-30h]
  _BYTE v15[152]; // [rsp+D8h] [rbp-28h] BYREF
  void **v16; // [rsp+170h] [rbp+70h] BYREF
  int v17; // [rsp+178h] [rbp+78h]

  v9[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h";
  v9[1] = L"CSrmAutoPWSZ::Reallocate";
  v9[2] = L"INCLSTRH";
  v10 = 351;
  v11 = 17;
  v12 = 255;
  v14 = 0x1000000;
  memset_0(v13, 0, sizeof(v13));
  CSrmFunctionTracer::CSrmFunctionTracer(
    (__int64)&v16,
    (const struct CSrmDebugInfo *)v9,
    (__int64)L"CSrmAutoPWSZ::ReAllocate");
  if ( a2 > 0x3200000 )
  {
    v8 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v15,
           (__int64)L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h",
           (__int64)L"INCLSTRH",
           (__int64)L"SrmReallocString",
           173,
           17);
    CSrmFunctionTracer::TranslateGenericError(&v16, v8, 2147942414LL, L"String too big");
  }
  if ( a2 + 1 < a2 )
  {
    v17 = -2147024362;
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v16);
    v7 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v15,
           (__int64)L"base\\fs\\fsrm\\utilities\\inc\\srmtypes.h",
           (__int64)L"INCTYPEH",
           (__int64)L"SafeAddSizeT",
           108,
           17);
    CSrmFunctionTracer::TranslateGenericError(
      &v16,
      v7,
      Hr,
      L"arithmetic overflow detected on addition of size_t variables");
  }
  v17 = 0;
  v4 = CoTaskMemRealloc(*this, 2 * (a2 + 1));
  if ( !v4 )
  {
    v5 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v15,
           (__int64)L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h",
           (__int64)L"INCLSTRH",
           (__int64)L"SrmReallocString",
           180,
           17);
    CSrmFunctionTracer::Throw(&v16, v5, 2147942414LL, L"Memory allocation error");
  }
  *this = v4;
  v16 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v16);
}

```

## disassembly

```asm
0x1800188cc  mov     [rsp-8+arg_10], rbx
0x1800188d1  mov     [rsp-8+arg_18], rdi
0x1800188d6  push    rbp
0x1800188d7  push    r12
0x1800188d9  push    r15
0x1800188db  lea     rbp, [rsp-130h]
0x1800188e3  sub     rsp, 230h
0x1800188ea  mov     rax, cs:__security_cookie
0x1800188f1  xor     rax, rsp
0x1800188f4  mov     [rbp+140h+var_20], rax
0x1800188fb  mov     rbx, rdx
0x1800188fe  mov     rdi, rcx
0x180018901  lea     rax, [rsp+240h+var_1F8]
0x180018906  mov     [rsp+240h+var_200], rax
0x18001890b  lea     r15, aBaseFsFsrmUtil_0; "base\\fs\\fsrm\\utilities\\inc\\srmstr."...
0x180018912  mov     [rsp+240h+var_1F8], r15
0x180018917  lea     rax, aCsrmautopwszRe; "CSrmAutoPWSZ::Reallocate"
0x18001891e  mov     [rsp+240h+var_1F0], rax
0x180018923  lea     r12, aInclstrh; "INCLSTRH"
0x18001892a  mov     [rsp+240h+var_1E8], r12
0x18001892f  mov     [rsp+240h+var_1E0], 15Fh
0x180018937  mov     [rsp+240h+var_1DC], 11h
0x18001893f  mov     [rsp+240h+var_1D8], 0FFh
0x180018947  mov     [rbp+140h+var_170], 1000000h
0x18001894e  xor     edx, edx; Val
0x180018950  lea     r8d, [rdx+60h]; Size
0x180018954  lea     rcx, [rsp+240h+var_1D0]; void *
0x180018959  call    memset_0
0x18001895e  nop
0x18001895f  lea     r8, aCsrmautopwszRe_0; "CSrmAutoPWSZ::ReAllocate"
0x180018966  lea     rdx, [rsp+240h+var_1F8]
0x18001896b  lea     rcx, [rbp+140h+var_D0]
0x18001896f  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180018974  nop
0x180018975  cmp     rbx, 3200000h
0x18001897c  ja      loc_180018A9F
0x180018982  lea     rdx, [rbx+1]
0x180018986  cmp     rdx, rbx
0x180018989  jb      loc_180018A3E
0x18001898f  mov     [rbp+140h+var_C8], 0
0x180018996  mov     [rbp+140h+var_C8], 0
0x18001899d  mov     [rbp+140h+var_C8], 0
0x1800189a4  add     rdx, rdx; cb
0x1800189a7  mov     rcx, [rdi]; pv
0x1800189aa  call    cs:__imp_CoTaskMemRealloc
0x1800189b0  test    rax, rax
0x1800189b3  jz      short loc_1800189F4
0x1800189b5  mov     [rdi], rax
0x1800189b8  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800189bf  mov     [rbp+140h+var_D0], rax
0x1800189c3  lea     rcx, [rbp+140h+var_D0]; this
0x1800189c7  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800189cc  mov     rcx, [rbp+140h+var_20]
0x1800189d3  xor     rcx, rsp; StackCookie
0x1800189d6  call    __security_check_cookie
0x1800189db  lea     r11, [rsp+240h+var_10]
0x1800189e3  mov     rbx, [r11+30h]
0x1800189e7  mov     rdi, [r11+38h]
0x1800189eb  mov     rsp, r11
0x1800189ee  pop     r15
0x1800189f0  pop     r12
0x1800189f2  pop     rbp
0x1800189f3  retn
0x1800189f4  lea     rax, [rbp+140h+var_168]
0x1800189f8  mov     [rsp+240h+var_200], rax
0x1800189fd  mov     [rsp+240h+var_218], 11h
0x180018a05  mov     [rsp+240h+var_220], 0B4h
0x180018a0d  lea     r9, aSrmreallocstri; "SrmReallocString"
0x180018a14  mov     r8, r12
0x180018a17  mov     rdx, r15
0x180018a1a  lea     rcx, [rbp+140h+var_168]
0x180018a1e  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180018a23  nop
0x180018a24  lea     r9, aMemoryAllocati; "Memory allocation error"
0x180018a2b  mov     r8d, 8007000Eh
0x180018a31  mov     rdx, rax
0x180018a34  lea     rcx, [rbp+140h+var_D0]
0x180018a38  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180018a3e  mov     [rbp+140h+var_C8], 80070216h
0x180018a45  lea     rcx, [rbp+140h+var_D0]; this
0x180018a49  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180018a4e  mov     ebx, eax
0x180018a50  lea     rax, [rbp+140h+var_168]
0x180018a54  mov     [rsp+240h+var_200], rax
0x180018a59  mov     [rsp+240h+var_218], 11h
0x180018a61  mov     [rsp+240h+var_220], 6Ch ; 'l'
0x180018a69  lea     r9, aSafeaddsizet; "SafeAddSizeT"
0x180018a70  lea     r8, aInctypeh; "INCTYPEH"
0x180018a77  lea     rdx, aBaseFsFsrmUtil; "base\\fs\\fsrm\\utilities\\inc\\srmtype"...
0x180018a7e  lea     rcx, [rbp+140h+var_168]
0x180018a82  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180018a87  nop
0x180018a88  lea     r9, aArithmeticOver; "arithmetic overflow detected on additio"...
0x180018a8f  mov     r8d, ebx
0x180018a92  mov     rdx, rax
0x180018a95  lea     rcx, [rbp+140h+var_D0]
0x180018a99  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180018a9f  lea     rax, [rbp+140h+var_168]
0x180018aa3  mov     [rsp+240h+var_200], rax
0x180018aa8  mov     [rsp+240h+var_218], 11h
0x180018ab0  mov     [rsp+240h+var_220], 0ADh
0x180018ab8  lea     r9, aSrmreallocstri; "SrmReallocString"
0x180018abf  mov     r8, r12
0x180018ac2  mov     rdx, r15
0x180018ac5  lea     rcx, [rbp+140h+var_168]
0x180018ac9  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180018ace  nop
0x180018acf  lea     r9, aStringTooBig; "String too big"
0x180018ad6  mov     r8d, 8007000Eh
0x180018adc  mov     rdx, rax
0x180018adf  lea     rcx, [rbp+140h+var_D0]
0x180018ae3  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```

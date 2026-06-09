# TrimEdgeQuotes(ushort const *,ushort * *)

- ea: `0x18007e620`
- end: `0x18007e8e4`
- name: `?TrimEdgeQuotes@@YAJPEBGPEAPEAG@Z`
- size: `708`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18007c45c`
- `0x18007c7b0`

## callees

- `0x180006a1c`
- `0x18000ad14`
- `0x180017f54`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074a04`
- `0x18007e620`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007e76a`
- `ole32!CoTaskMemFree` at `0x18007e819`
- `ole32!CoTaskMemFree` at `0x18007e76a`
- `ole32!CoTaskMemFree` at `0x18007e819`

## string_xrefs

- `0x18007e8c8`: `StringCchCopyN`
- `0x18007e65f`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007e67b`: `SRMPATHC`
- `0x18007e8b0`: `SRMPATHC`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall TrimEdgeQuotes(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v4; // rax
  const unsigned __int16 *v5; // rcx
  int v6; // eax
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rdi
  unsigned __int16 *v11; // rax
  unsigned int v12; // ebx
  unsigned int Hr; // ebx
  __int64 v14; // rax
  LPVOID pv; // [rsp+40h] [rbp-1C8h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-1C0h]
  const unsigned __int16 *v17; // [rsp+58h] [rbp-1B0h]
  __int64 v18; // [rsp+60h] [rbp-1A8h]
  unsigned __int64 v19; // [rsp+68h] [rbp-1A0h]
  _QWORD *v20; // [rsp+70h] [rbp-198h]
  _QWORD v21[3]; // [rsp+88h] [rbp-180h] BYREF
  int v22; // [rsp+A0h] [rbp-168h]
  int v23; // [rsp+A4h] [rbp-164h]
  int v24; // [rsp+A8h] [rbp-160h]
  _DWORD v25[28]; // [rsp+B0h] [rbp-158h] BYREF
  void **v26; // [rsp+120h] [rbp-E8h] BYREF
  int v27; // [rsp+128h] [rbp-E0h]

  v20 = v21;
  v21[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v21[1] = L"TrimEdgeQuotes";
  v21[2] = L"SRMPATHC";
  v22 = 728;
  v23 = 17;
  v24 = 255;
  v25[24] = 0x1000000;
  memset_0(v25, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v26, (const struct CSrmDebugInfo *)v21, (__int64)L"TrimEdgeQuotes");
  *a2 = 0;
  pv = 0;
  v16 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
LABEL_11:
    v16 = 0;
    goto LABEL_12;
  }
  v4 = 0x8000;
  v18 = 0x8000;
  v5 = a1;
  v17 = a1;
  while ( v4 )
  {
    if ( !*v5 )
    {
      v16 = 0x8000 - v4;
      v6 = 0;
      goto LABEL_8;
    }
    v17 = ++v5;
    v18 = --v4;
  }
  v16 = 0;
  v6 = -2147024809;
LABEL_8:
  if ( v6 < 0 )
    goto LABEL_11;
LABEL_12:
  v27 = v6;
  if ( v6 >= 0 )
  {
    v8 = 0;
    v19 = 0;
    while ( v8 < v16 >> 1 && a1[v8] == 34 && a1[v16 - v8 - 1] == 34 )
      v19 = ++v8;
    v9 = 2 * v8;
    v10 = v16 - v9;
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&pv, v16 - v9);
    v27 = StringCchCopyNW((unsigned __int16 *)pv, v10 + 1, &a1[v9 / 2], v10);
    if ( v27 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v26);
      v20 = v21;
      v14 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v21,
              (__int64)L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
              (__int64)L"SRMPATHC",
              (__int64)L"TrimEdgeQuotes",
              765,
              17);
      CSrmFunctionTracer::TranslateGenericError(&v26, v14, Hr, L"StringCchCopyN");
    }
    v11 = (unsigned __int16 *)pv;
    pv = 0;
    *a2 = v11;
    CoTaskMemFree(pv);
    pv = 0;
    v12 = v27;
    v26 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v26);
    return v12;
  }
  else
  {
    v27 = -2147200243;
    CoTaskMemFree(pv);
    pv = 0;
    v26 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v26);
    return 2147767053LL;
  }
}

```

## disassembly

```asm
0x18007e620  mov     r11, rsp
0x18007e623  mov     [r11+18h], rbx
0x18007e627  mov     [r11+20h], rsi
0x18007e62b  push    rdi
0x18007e62c  push    r12
0x18007e62e  push    r13
0x18007e630  push    r14
0x18007e632  push    r15
0x18007e634  sub     rsp, 1E0h
0x18007e63b  mov     rax, cs:__security_cookie
0x18007e642  xor     rax, rsp
0x18007e645  mov     [rsp+208h+var_38], rax
0x18007e64d  mov     r14, rdx
0x18007e650  mov     rsi, rcx
0x18007e653  lea     rax, [r11-180h]
0x18007e65a  mov     [rsp+208h+var_198], rax
0x18007e65f  lea     r13, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007e666  mov     [r11-180h], r13
0x18007e66d  lea     r12, aTrimedgequotes_0; "TrimEdgeQuotes"
0x18007e674  mov     [r11-178h], r12
0x18007e67b  lea     rax, aSrmpathc; "SRMPATHC"
0x18007e682  mov     [r11-170h], rax
0x18007e689  mov     [rsp+208h+var_168], 2D8h
0x18007e694  mov     [rsp+208h+var_164], 11h
0x18007e69f  mov     [rsp+208h+var_160], 0FFh
0x18007e6aa  xor     r15d, r15d
0x18007e6ad  mov     [rsp+208h+var_F8], 1000000h
0x18007e6b8  xor     edx, edx; Val
0x18007e6ba  lea     r8d, [r15+60h]; Size
0x18007e6be  lea     rcx, [r11-158h]; void *
0x18007e6c5  call    memset_0
0x18007e6ca  nop
0x18007e6cb  mov     r8, r12
0x18007e6ce  lea     rdx, [rsp+208h+var_180]
0x18007e6d6  lea     rcx, [rsp+208h+var_E8]
0x18007e6de  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007e6e3  nop
0x18007e6e4  mov     [r14], r15
0x18007e6e7  mov     [rsp+208h+pv], r15
0x18007e6ec  mov     [rsp+208h+var_1C0], r15
0x18007e6f1  lea     r8, [rsp+208h+var_1C0]
0x18007e6f6  test    rsi, rsi
0x18007e6f9  jz      short loc_18007E746
0x18007e6fb  mov     edx, 8000h
0x18007e700  mov     eax, edx
0x18007e702  mov     [rsp+208h+var_1A8], rdx
0x18007e707  mov     rcx, rsi
0x18007e70a  mov     [rsp+208h+var_1B0], rcx
0x18007e70f  test    rax, rax
0x18007e712  jz      short loc_18007E738
0x18007e714  cmp     [rcx], r15w
0x18007e718  jz      short loc_18007E72D
0x18007e71a  add     rcx, 2
0x18007e71e  mov     [rsp+208h+var_1B0], rcx
0x18007e723  dec     rax
0x18007e726  mov     [rsp+208h+var_1A8], rax
0x18007e72b  jmp     short loc_18007E70F
0x18007e72d  sub     rdx, rax
0x18007e730  mov     [r8], rdx
0x18007e733  mov     eax, r15d
0x18007e736  jmp     short loc_18007E740
0x18007e738  mov     [r8], r15
0x18007e73b  mov     eax, 80070057h
0x18007e740  test    eax, eax
0x18007e742  jns     short loc_18007E74E
0x18007e744  jmp     short loc_18007E74B
0x18007e746  mov     eax, 80070057h
0x18007e74b  mov     [r8], r15
0x18007e74e  mov     [rsp+208h+var_E0], eax
0x18007e755  test    eax, eax
0x18007e757  jns     short loc_18007E79D
0x18007e759  mov     ebx, 8004530Dh
0x18007e75e  mov     [rsp+208h+var_E0], ebx
0x18007e765  mov     rcx, [rsp+208h+pv]; pv
0x18007e76a  call    cs:__imp_CoTaskMemFree
0x18007e770  mov     [rsp+208h+pv], r15
0x18007e775  mov     [rsp+208h+pv], r15
0x18007e77a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007e781  mov     [rsp+208h+var_E8], rax
0x18007e789  lea     rcx, [rsp+208h+var_E8]; this
0x18007e791  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007e796  mov     eax, ebx
0x18007e798  jmp     loc_18007E84E
0x18007e79d  mov     rbx, r15
0x18007e7a0  mov     [rsp+208h+var_1A0], rbx
0x18007e7a5  mov     rdi, [rsp+208h+var_1C0]
0x18007e7aa  mov     rax, rdi
0x18007e7ad  shr     rax, 1
0x18007e7b0  cmp     rbx, rax
0x18007e7b3  jnb     short loc_18007E7D4
0x18007e7b5  cmp     word ptr [rsi+rbx*2], 22h ; '"'
0x18007e7ba  jnz     short loc_18007E7D4
0x18007e7bc  mov     rax, rdi
0x18007e7bf  sub     rax, rbx
0x18007e7c2  cmp     word ptr [rsi+rax*2-2], 22h ; '"'
0x18007e7c8  jnz     short loc_18007E7D4
0x18007e7ca  inc     rbx
0x18007e7cd  mov     [rsp+208h+var_1A0], rbx
0x18007e7d2  jmp     short loc_18007E7AA
0x18007e7d4  add     rbx, rbx
0x18007e7d7  sub     rdi, rbx
0x18007e7da  mov     rdx, rdi; unsigned __int64
0x18007e7dd  lea     rcx, [rsp+208h+pv]; this
0x18007e7e2  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007e7e7  lea     r8, [rbx+rsi]; unsigned __int16 *
0x18007e7eb  lea     rdx, [rdi+1]; unsigned __int64
0x18007e7ef  mov     r9, rdi; unsigned __int64
0x18007e7f2  mov     rcx, [rsp+208h+pv]; unsigned __int16 *
0x18007e7f7  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18007e7fc  mov     [rsp+208h+var_E0], eax
0x18007e803  test    eax, eax
0x18007e805  js      short loc_18007E881
0x18007e807  mov     rax, [rsp+208h+pv]
0x18007e80c  mov     [rsp+208h+pv], r15
0x18007e811  mov     [r14], rax
0x18007e814  mov     rcx, [rsp+208h+pv]; pv
0x18007e819  call    cs:__imp_CoTaskMemFree
0x18007e81f  mov     [rsp+208h+pv], r15
0x18007e824  mov     [rsp+208h+pv], r15
0x18007e829  mov     ebx, [rsp+208h+var_E0]
0x18007e830  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007e837  mov     [rsp+208h+var_E8], rax
0x18007e83f  lea     rcx, [rsp+208h+var_E8]; this
0x18007e847  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007e84c  mov     eax, ebx
0x18007e84e  mov     rcx, [rsp+208h+var_38]
0x18007e856  xor     rcx, rsp; StackCookie
0x18007e859  call    __security_check_cookie
0x18007e85e  lea     r11, [rsp+208h+var_28]
0x18007e866  mov     rbx, [r11+40h]
0x18007e86a  mov     rsi, [r11+48h]
0x18007e86e  mov     rsp, r11
0x18007e871  pop     r15
0x18007e873  pop     r14
0x18007e875  pop     r13
0x18007e877  pop     r12
0x18007e879  pop     rdi
0x18007e87a  retn
0x18007e87b  jmp     short loc_18007E829
0x18007e87d  jmp     short loc_18007E829
0x18007e87f  jmp     short loc_18007E829
0x18007e881  lea     rcx, [rsp+208h+var_E8]; this
0x18007e889  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007e88e  mov     ebx, eax
0x18007e890  lea     rax, [rsp+208h+var_180]
0x18007e898  mov     [rsp+208h+var_198], rax
0x18007e89d  mov     [rsp+208h+var_1E0], 11h
0x18007e8a5  mov     [rsp+208h+var_1E8], 2FDh
0x18007e8ad  mov     r9, r12
0x18007e8b0  lea     r8, aSrmpathc; "SRMPATHC"
0x18007e8b7  mov     rdx, r13
0x18007e8ba  lea     rcx, [rsp+208h+var_180]
0x18007e8c2  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007e8c7  nop
0x18007e8c8  lea     r9, aStringcchcopyn; "StringCchCopyN"
0x18007e8cf  mov     r8d, ebx
0x18007e8d2  mov     rdx, rax
0x18007e8d5  lea     rcx, [rsp+208h+var_E8]
0x18007e8dd  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```

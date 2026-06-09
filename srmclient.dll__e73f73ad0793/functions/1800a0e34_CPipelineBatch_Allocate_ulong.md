# CPipelineBatch::Allocate(ulong)

- ea: `0x1800a0e34`
- end: `0x1800a10d6`
- name: `?Allocate@CPipelineBatch@@AEAAXK@Z`
- size: `674`
- prototype: `void __fastcall(CPipelineBatch *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800a14c0`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800a0e34`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800a0ed4`
- `ole32!CoTaskMemAlloc` at `0x1800a0f04`
- `ole32!CoTaskMemAlloc` at `0x1800a0f34`
- `ole32!CoTaskMemAlloc` at `0x1800a0f64`
- `ole32!CoTaskMemAlloc` at `0x1800a0f94`
- `ole32!CoTaskMemAlloc` at `0x1800a0ed4`
- `ole32!CoTaskMemAlloc` at `0x1800a0f04`
- `ole32!CoTaskMemAlloc` at `0x1800a0f34`
- `ole32!CoTaskMemAlloc` at `0x1800a0f64`
- `ole32!CoTaskMemAlloc` at `0x1800a0f94`

## string_xrefs

- `0x1800a0e65`: `base\fs\fsrm\service\pipeline\plbatch.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CPipelineBatch::Allocate(CPipelineBatch *this, unsigned int a2)
{
  void *v4; // rax
  void *v5; // rax
  void *v6; // rax
  void *v7; // rax
  void *v8; // rax
  char v9; // al
  char Hr; // al
  char v11; // al
  char v12; // al
  char v13; // al
  _QWORD v14[3]; // [rsp+28h] [rbp-D8h] BYREF
  int v15; // [rsp+40h] [rbp-C0h]
  int v16; // [rsp+44h] [rbp-BCh]
  int v17; // [rsp+48h] [rbp-B8h]
  _BYTE v18[96]; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+B0h] [rbp-50h]
  void **v20; // [rsp+C0h] [rbp-40h] BYREF
  int v21; // [rsp+C8h] [rbp-38h]

  v14[0] = L"base\\fs\\fsrm\\service\\pipeline\\plbatch.cpp";
  v14[1] = L"CPipelineBatch::Allocate";
  v14[2] = L"PLBATCHC";
  v15 = 594;
  v16 = 22;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v20, (const struct CSrmDebugInfo *)v14, 0);
  v4 = CoTaskMemAlloc(8LL * a2);
  *((_QWORD *)this + 10) = v4;
  if ( !v4 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v20, -2147024882);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v20, 0x256u, Hr, 0, v14);
  }
  v21 = 0;
  memset_0(v4, 0, 8LL * a2);
  v5 = CoTaskMemAlloc(8LL * a2);
  *((_QWORD *)this + 11) = v5;
  if ( !v5 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v20, -2147024882);
    v11 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v20, 0x25Bu, v11, 0, v14);
  }
  v21 = 0;
  memset_0(v5, 0, 8LL * a2);
  v6 = CoTaskMemAlloc(8LL * a2);
  *((_QWORD *)this + 12) = v6;
  if ( !v6 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v20, -2147024882);
    v12 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v20, 0x260u, v12, 0, v14);
  }
  v21 = 0;
  memset_0(v6, 0, 8LL * a2);
  v7 = CoTaskMemAlloc(8LL * a2);
  *((_QWORD *)this + 13) = v7;
  if ( !v7 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v20, -2147024882);
    v13 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v20, 0x265u, v13, 0, v14);
  }
  v21 = 0;
  memset_0(v7, 0, 8LL * a2);
  v8 = CoTaskMemAlloc(8LL * a2);
  *((_QWORD *)this + 14) = v8;
  if ( !v8 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v20, -2147024882);
    v9 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v20, 0x26Au, v9, 0, v14);
  }
  v21 = 0;
  memset_0(v8, 0, 8LL * a2);
  *((_DWORD *)this + 17) = 0;
  *((_DWORD *)this + 18) = a2;
  v20 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v20);
}

```

## disassembly

```asm
0x1800a0e34  mov     [rsp-8+arg_10], rbx
0x1800a0e39  push    rbp
0x1800a0e3a  push    rsi
0x1800a0e3b  push    rdi
0x1800a0e3c  lea     rbp, [rsp-80h]
0x1800a0e41  sub     rsp, 180h
0x1800a0e48  mov     rax, cs:__security_cookie
0x1800a0e4f  xor     rax, rsp
0x1800a0e52  mov     [rbp+90h+var_20], rax
0x1800a0e56  mov     esi, edx
0x1800a0e58  mov     rdi, rcx
0x1800a0e5b  lea     rax, [rsp+190h+var_168]
0x1800a0e60  mov     [rsp+190h+var_170], rax
0x1800a0e65  lea     rax, aBaseFsFsrmServ_1; "base\\fs\\fsrm\\service\\pipeline\\plba"...
0x1800a0e6c  mov     [rsp+190h+var_168], rax
0x1800a0e71  lea     rax, aCpipelinebatch_0; "CPipelineBatch::Allocate"
0x1800a0e78  mov     [rsp+190h+var_160], rax
0x1800a0e7d  lea     rax, aPlbatchc; "PLBATCHC"
0x1800a0e84  mov     [rsp+190h+var_158], rax
0x1800a0e89  mov     [rsp+190h+var_150], 252h
0x1800a0e91  mov     [rsp+190h+var_14C], 16h
0x1800a0e99  mov     [rsp+190h+var_148], 0FFh
0x1800a0ea1  mov     [rbp+90h+var_E0], 1000000h
0x1800a0ea8  xor     edx, edx; Val
0x1800a0eaa  lea     r8d, [rdx+60h]; Size
0x1800a0eae  lea     rcx, [rsp+190h+var_140]; void *
0x1800a0eb3  call    memset_0
0x1800a0eb8  nop
0x1800a0eb9  xor     r8d, r8d
0x1800a0ebc  lea     rdx, [rsp+190h+var_168]
0x1800a0ec1  lea     rcx, [rbp+90h+var_D0]
0x1800a0ec5  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800a0eca  nop
0x1800a0ecb  mov     ebx, esi
0x1800a0ecd  shl     rbx, 3
0x1800a0ed1  mov     rcx, rbx; cb
0x1800a0ed4  call    cs:__imp_CoTaskMemAlloc
0x1800a0eda  mov     [rdi+50h], rax
0x1800a0ede  mov     ecx, [rbp+90h+var_C8]
0x1800a0ee1  mov     [rbp+90h+var_C8], ecx
0x1800a0ee4  test    rax, rax
0x1800a0ee7  jz      loc_1800A1026
0x1800a0eed  mov     [rbp+90h+var_C8], 0
0x1800a0ef4  mov     r8, rbx; Size
0x1800a0ef7  xor     edx, edx; Val
0x1800a0ef9  mov     rcx, rax; void *
0x1800a0efc  call    memset_0
0x1800a0f01  mov     rcx, rbx; cb
0x1800a0f04  call    cs:__imp_CoTaskMemAlloc
0x1800a0f0a  mov     [rdi+58h], rax
0x1800a0f0e  mov     ecx, [rbp+90h+var_C8]
0x1800a0f11  mov     [rbp+90h+var_C8], ecx
0x1800a0f14  test    rax, rax
0x1800a0f17  jz      loc_1800A1052
0x1800a0f1d  mov     [rbp+90h+var_C8], 0
0x1800a0f24  mov     r8, rbx; Size
0x1800a0f27  xor     edx, edx; Val
0x1800a0f29  mov     rcx, rax; void *
0x1800a0f2c  call    memset_0
0x1800a0f31  mov     rcx, rbx; cb
0x1800a0f34  call    cs:__imp_CoTaskMemAlloc
0x1800a0f3a  mov     [rdi+60h], rax
0x1800a0f3e  mov     ecx, [rbp+90h+var_C8]
0x1800a0f41  mov     [rbp+90h+var_C8], ecx
0x1800a0f44  test    rax, rax
0x1800a0f47  jz      loc_1800A107E
0x1800a0f4d  mov     [rbp+90h+var_C8], 0
0x1800a0f54  mov     r8, rbx; Size
0x1800a0f57  xor     edx, edx; Val
0x1800a0f59  mov     rcx, rax; void *
0x1800a0f5c  call    memset_0
0x1800a0f61  mov     rcx, rbx; cb
0x1800a0f64  call    cs:__imp_CoTaskMemAlloc
0x1800a0f6a  mov     [rdi+68h], rax
0x1800a0f6e  mov     ecx, [rbp+90h+var_C8]
0x1800a0f71  mov     [rbp+90h+var_C8], ecx
0x1800a0f74  test    rax, rax
0x1800a0f77  jz      loc_1800A10AA
0x1800a0f7d  mov     [rbp+90h+var_C8], 0
0x1800a0f84  mov     r8, rbx; Size
0x1800a0f87  xor     edx, edx; Val
0x1800a0f89  mov     rcx, rax; void *
0x1800a0f8c  call    memset_0
0x1800a0f91  mov     rcx, rbx; cb
0x1800a0f94  call    cs:__imp_CoTaskMemAlloc
0x1800a0f9a  mov     [rdi+70h], rax
0x1800a0f9e  mov     ecx, [rbp+90h+var_C8]
0x1800a0fa1  mov     [rbp+90h+var_C8], ecx
0x1800a0fa4  test    rax, rax
0x1800a0fa7  jz      short loc_1800A0FFA
0x1800a0fa9  mov     [rbp+90h+var_C8], 0
0x1800a0fb0  mov     r8, rbx; Size
0x1800a0fb3  xor     edx, edx; Val
0x1800a0fb5  mov     rcx, rax; void *
0x1800a0fb8  call    memset_0
0x1800a0fbd  mov     dword ptr [rdi+44h], 0
0x1800a0fc4  mov     [rdi+48h], esi
0x1800a0fc7  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a0fce  mov     [rbp+90h+var_D0], rax
0x1800a0fd2  lea     rcx, [rbp+90h+var_D0]; this
0x1800a0fd6  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800a0fdb  mov     rcx, [rbp+90h+var_20]
0x1800a0fdf  xor     rcx, rsp; StackCookie
0x1800a0fe2  call    __security_check_cookie
0x1800a0fe7  mov     rbx, [rsp+190h+arg_10]
0x1800a0fef  add     rsp, 180h
0x1800a0ff6  pop     rdi
0x1800a0ff7  pop     rsi
0x1800a0ff8  pop     rbp
0x1800a0ff9  retn
0x1800a0ffa  mov     edx, 8007000Eh; int
0x1800a0fff  lea     rcx, [rbp+90h+var_D0]; this
0x1800a1003  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800a1008  lea     rcx, [rbp+90h+var_D0]; this
0x1800a100c  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a1011  mov     r8d, eax; char
0x1800a1014  xor     r9d, r9d; unsigned __int16 *
0x1800a1017  mov     edx, 26Ah; unsigned int
0x1800a101c  lea     rcx, [rbp+90h+var_D0]; this
0x1800a1020  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800a1026  mov     edx, 8007000Eh; int
0x1800a102b  lea     rcx, [rbp+90h+var_D0]; this
0x1800a102f  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800a1034  lea     rcx, [rbp+90h+var_D0]; this
0x1800a1038  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a103d  mov     r8d, eax; char
0x1800a1040  xor     r9d, r9d; unsigned __int16 *
0x1800a1043  mov     edx, 256h; unsigned int
0x1800a1048  lea     rcx, [rbp+90h+var_D0]; this
0x1800a104c  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800a1052  mov     edx, 8007000Eh; int
0x1800a1057  lea     rcx, [rbp+90h+var_D0]; this
0x1800a105b  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800a1060  lea     rcx, [rbp+90h+var_D0]; this
0x1800a1064  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a1069  mov     r8d, eax; char
0x1800a106c  xor     r9d, r9d; unsigned __int16 *
0x1800a106f  mov     edx, 25Bh; unsigned int
0x1800a1074  lea     rcx, [rbp+90h+var_D0]; this
0x1800a1078  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800a107e  mov     edx, 8007000Eh; int
0x1800a1083  lea     rcx, [rbp+90h+var_D0]; this
0x1800a1087  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800a108c  lea     rcx, [rbp+90h+var_D0]; this
0x1800a1090  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a1095  mov     r8d, eax; char
0x1800a1098  xor     r9d, r9d; unsigned __int16 *
0x1800a109b  mov     edx, 260h; unsigned int
0x1800a10a0  lea     rcx, [rbp+90h+var_D0]; this
0x1800a10a4  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800a10aa  mov     edx, 8007000Eh; int
0x1800a10af  lea     rcx, [rbp+90h+var_D0]; this
0x1800a10b3  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800a10b8  lea     rcx, [rbp+90h+var_D0]; this
0x1800a10bc  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a10c1  mov     r8d, eax; char
0x1800a10c4  xor     r9d, r9d; unsigned __int16 *
0x1800a10c7  mov     edx, 265h; unsigned int
0x1800a10cc  lea     rcx, [rbp+90h+var_D0]; this
0x1800a10d0  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```

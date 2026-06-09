# CPropertyBagFieldsBase::GetFields(_FSRM_PROPERTYBAG_FIELDS *)

- ea: `0x180084eb0`
- end: `0x1800851e6`
- name: `?GetFields@CPropertyBagFieldsBase@@QEBAXPEAU_FSRM_PROPERTYBAG_FIELDS@@@Z`
- size: `822`
- prototype: `void(CPropertyBagFieldsBase *__hidden this, struct _FSRM_PROPERTYBAG_FIELDS *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800457c0`
- `0x18008ea80`

## callees

- `0x18000af40`
- `0x18006febc`
- `0x1800700b8`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180085146`
- `ole32!CoTaskMemFree` at `0x180085158`
- `ole32!CoTaskMemFree` at `0x18008516a`
- `ole32!CoTaskMemFree` at `0x18008517c`
- `ole32!CoTaskMemFree` at `0x18008518e`
- `ole32!CoTaskMemFree` at `0x1800851a0`
- `ole32!CoTaskMemFree` at `0x180085146`
- `ole32!CoTaskMemFree` at `0x180085158`
- `ole32!CoTaskMemFree` at `0x18008516a`
- `ole32!CoTaskMemFree` at `0x18008517c`
- `ole32!CoTaskMemFree` at `0x18008518e`
- `ole32!CoTaskMemFree` at `0x1800851a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CPropertyBagFieldsBase::GetFields(const unsigned __int16 ***this, struct _FSRM_PROPERTYBAG_FIELDS *a2)
{
  const unsigned __int16 *v4; // rax
  const unsigned __int16 *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  const unsigned __int16 **v12; // rax
  __int64 v13; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+74h] [rbp-8Ch]
  int v22; // [rsp+78h] [rbp-88h]
  _BYTE v23[96]; // [rsp+80h] [rbp-80h] BYREF
  int v24; // [rsp+E0h] [rbp-20h]
  _QWORD v25[22]; // [rsp+F0h] [rbp-10h] BYREF

  v18[1] = v19;
  v19[0] = L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp";
  v19[1] = L"CPropertyBagFieldsBase::GetFields";
  v19[2] = L"SRMPROPC";
  v20 = 257;
  v21 = 17;
  v22 = 255;
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v25, (const struct CSrmDebugInfo *)v19, 0);
  memset_0(a2, 0, 0xD0u);
  v18[0] = 0;
  v17 = 0;
  v16 = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)v18, *this[1]);
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v17, this[1][1]);
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v16, this[1][2]);
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v15, this[1][3]);
  v4 = (const unsigned __int16 *)((__int64 (__fastcall *)(const unsigned __int16 ***))(*this)[3])(this);
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v14, v4);
  v5 = (const unsigned __int16 *)((__int64 (__fastcall *)(const unsigned __int16 ***))(*this)[5])(this);
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v13, v5);
  v6 = v18[0];
  v18[0] = 0;
  *(_QWORD *)a2 = v6;
  v7 = v17;
  v17 = 0;
  *((_QWORD *)a2 + 1) = v7;
  v8 = v16;
  v16 = 0;
  *((_QWORD *)a2 + 2) = v8;
  v9 = v15;
  v15 = 0;
  *((_QWORD *)a2 + 3) = v9;
  v10 = v14;
  v14 = 0;
  *((_QWORD *)a2 + 4) = v10;
  v11 = v13;
  v13 = 0;
  *((_QWORD *)a2 + 5) = v11;
  *((_DWORD *)a2 + 12) = *((_DWORD *)this[1] + 12);
  *((_DWORD *)a2 + 13) = *((_DWORD *)this[1] + 13);
  *((_DWORD *)a2 + 14) = *((_DWORD *)this[1] + 14);
  *((_DWORD *)a2 + 15) = *((_DWORD *)this[1] + 15);
  *((_QWORD *)a2 + 8) = this[1][8];
  *((_QWORD *)a2 + 9) = this[1][9];
  *((_QWORD *)a2 + 10) = this[1][10];
  *((_QWORD *)a2 + 11) = this[1][11];
  *((_QWORD *)a2 + 12) = this[1][12];
  *((_QWORD *)a2 + 13) = this[1][13];
  *((_QWORD *)a2 + 14) = this[1][14];
  *((_QWORD *)a2 + 15) = this[1][15];
  *((_DWORD *)a2 + 32) = *((_DWORD *)this[1] + 32);
  *((_DWORD *)a2 + 33) = ((__int64 (__fastcall *)(const unsigned __int16 ***))(*this)[6])(this);
  v12 = this[1];
  *(_OWORD *)((char *)a2 + 136) = *(_OWORD *)(v12 + 17);
  *(_OWORD *)((char *)a2 + 152) = *(_OWORD *)(v12 + 19);
  *(_OWORD *)((char *)a2 + 168) = *(_OWORD *)(v12 + 21);
  *(_OWORD *)((char *)a2 + 184) = *(_OWORD *)(v12 + 23);
  *((_DWORD *)a2 + 50) = *((_DWORD *)v12 + 50);
  CoTaskMemFree(0);
  v13 = 0;
  CoTaskMemFree(0);
  v14 = 0;
  CoTaskMemFree(0);
  v15 = 0;
  CoTaskMemFree(0);
  v16 = 0;
  CoTaskMemFree(0);
  v17 = 0;
  CoTaskMemFree(0);
  v18[0] = 0;
  v25[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v25);
}

```

## disassembly

```asm
0x180084eb0  mov     [rsp-8+arg_10], rbx
0x180084eb5  push    rbp
0x180084eb6  push    rsi
0x180084eb7  push    rdi
0x180084eb8  lea     rbp, [rsp-0B0h]
0x180084ec0  sub     rsp, 1B0h
0x180084ec7  mov     rax, cs:__security_cookie
0x180084ece  xor     rax, rsp
0x180084ed1  mov     [rbp+0C0h+var_20], rax
0x180084ed8  mov     rdi, rdx
0x180084edb  mov     rbx, rcx
0x180084ede  lea     rax, [rsp+1C0h+var_168]
0x180084ee3  mov     [rsp+1C0h+var_170], rax
0x180084ee8  lea     rax, aBaseFsFsrmUtil_17; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x180084eef  mov     [rsp+1C0h+var_168], rax
0x180084ef4  lea     rax, aCpropertybagfi_3; "CPropertyBagFieldsBase::GetFields"
0x180084efb  mov     [rsp+1C0h+var_160], rax
0x180084f00  lea     rax, aSrmpropc; "SRMPROPC"
0x180084f07  mov     [rsp+1C0h+var_158], rax
0x180084f0c  mov     [rsp+1C0h+var_150], 101h
0x180084f14  mov     [rsp+1C0h+var_14C], 11h
0x180084f1c  mov     [rsp+1C0h+var_148], 0FFh
0x180084f24  xor     esi, esi
0x180084f26  mov     [rbp+0C0h+var_E0], 1000000h
0x180084f2d  xor     edx, edx; Val
0x180084f2f  lea     r8d, [rsi+60h]; Size
0x180084f33  lea     rcx, [rbp+0C0h+var_140]; void *
0x180084f37  call    memset_0
0x180084f3c  nop
0x180084f3d  xor     r8d, r8d
0x180084f40  lea     rdx, [rsp+1C0h+var_168]
0x180084f45  lea     rcx, [rbp+0C0h+var_D0]
0x180084f49  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180084f4e  nop
0x180084f4f  xor     edx, edx; Val
0x180084f51  mov     r8d, 0D0h; Size
0x180084f57  mov     rcx, rdi; void *
0x180084f5a  call    memset_0
0x180084f5f  mov     [rsp+1C0h+var_178], rsi
0x180084f64  mov     [rsp+1C0h+var_180], rsi
0x180084f69  mov     [rsp+1C0h+var_188], rsi
0x180084f6e  mov     [rsp+1C0h+var_190], rsi
0x180084f73  mov     [rsp+1C0h+var_198], rsi
0x180084f78  mov     [rsp+1C0h+var_1A0], rsi
0x180084f7d  mov     rdx, [rbx+8]
0x180084f81  mov     rdx, [rdx]; unsigned __int16 *
0x180084f84  lea     rcx, [rsp+1C0h+var_178]; this
0x180084f89  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180084f8e  mov     rdx, [rbx+8]
0x180084f92  mov     rdx, [rdx+8]; unsigned __int16 *
0x180084f96  lea     rcx, [rsp+1C0h+var_180]; this
0x180084f9b  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180084fa0  mov     rdx, [rbx+8]
0x180084fa4  mov     rdx, [rdx+10h]; unsigned __int16 *
0x180084fa8  lea     rcx, [rsp+1C0h+var_188]; this
0x180084fad  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180084fb2  mov     rdx, [rbx+8]
0x180084fb6  mov     rdx, [rdx+18h]; unsigned __int16 *
0x180084fba  lea     rcx, [rsp+1C0h+var_190]; this
0x180084fbf  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180084fc4  mov     rax, [rbx]
0x180084fc7  mov     rcx, rbx
0x180084fca  mov     rax, [rax+18h]
0x180084fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084fd3  mov     rdx, rax; unsigned __int16 *
0x180084fd6  lea     rcx, [rsp+1C0h+var_198]; this
0x180084fdb  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180084fe0  mov     rax, [rbx]
0x180084fe3  mov     rcx, rbx
0x180084fe6  mov     rax, [rax+28h]
0x180084fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084fef  mov     rdx, rax; unsigned __int16 *
0x180084ff2  lea     rcx, [rsp+1C0h+var_1A0]; this
0x180084ff7  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180084ffc  mov     rax, [rsp+1C0h+var_178]
0x180085001  mov     [rsp+1C0h+var_178], rsi
0x180085006  mov     [rdi], rax
0x180085009  mov     rax, [rsp+1C0h+var_180]
0x18008500e  mov     [rsp+1C0h+var_180], rsi
0x180085013  mov     [rdi+8], rax
0x180085017  mov     rax, [rsp+1C0h+var_188]
0x18008501c  mov     [rsp+1C0h+var_188], rsi
0x180085021  mov     [rdi+10h], rax
0x180085025  mov     rax, [rsp+1C0h+var_190]
0x18008502a  mov     [rsp+1C0h+var_190], rsi
0x18008502f  mov     [rdi+18h], rax
0x180085033  mov     rax, [rsp+1C0h+var_198]
0x180085038  mov     [rsp+1C0h+var_198], rsi
0x18008503d  mov     [rdi+20h], rax
0x180085041  mov     rax, [rsp+1C0h+var_1A0]
0x180085046  mov     [rsp+1C0h+var_1A0], rsi
0x18008504b  mov     [rdi+28h], rax
0x18008504f  mov     rax, [rbx+8]
0x180085053  mov     ecx, [rax+30h]
0x180085056  mov     [rdi+30h], ecx
0x180085059  mov     rax, [rbx+8]
0x18008505d  mov     ecx, [rax+34h]
0x180085060  mov     [rdi+34h], ecx
0x180085063  mov     rax, [rbx+8]
0x180085067  mov     ecx, [rax+38h]
0x18008506a  mov     [rdi+38h], ecx
0x18008506d  mov     rax, [rbx+8]
0x180085071  mov     ecx, [rax+3Ch]
0x180085074  mov     [rdi+3Ch], ecx
0x180085077  mov     rax, [rbx+8]
0x18008507b  mov     rcx, [rax+40h]
0x18008507f  mov     [rdi+40h], rcx
0x180085083  mov     rax, [rbx+8]
0x180085087  mov     rcx, [rax+48h]
0x18008508b  mov     [rdi+48h], rcx
0x18008508f  mov     rax, [rbx+8]
0x180085093  mov     rcx, [rax+50h]
0x180085097  mov     [rdi+50h], rcx
0x18008509b  mov     rax, [rbx+8]
0x18008509f  mov     rcx, [rax+58h]
0x1800850a3  mov     [rdi+58h], rcx
0x1800850a7  mov     rax, [rbx+8]
0x1800850ab  mov     rcx, [rax+60h]
0x1800850af  mov     [rdi+60h], rcx
0x1800850b3  mov     rax, [rbx+8]
0x1800850b7  mov     rcx, [rax+68h]
0x1800850bb  mov     [rdi+68h], rcx
0x1800850bf  mov     rax, [rbx+8]
0x1800850c3  mov     rcx, [rax+70h]
0x1800850c7  mov     [rdi+70h], rcx
0x1800850cb  mov     rax, [rbx+8]
0x1800850cf  mov     rcx, [rax+78h]
0x1800850d3  mov     [rdi+78h], rcx
0x1800850d7  mov     rax, [rbx+8]
0x1800850db  mov     ecx, [rax+80h]
0x1800850e1  mov     [rdi+80h], ecx
0x1800850e7  mov     rax, [rbx]
0x1800850ea  mov     rcx, rbx
0x1800850ed  mov     rax, [rax+30h]
0x1800850f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800850f6  mov     [rdi+84h], eax
0x1800850fc  mov     rax, [rbx+8]
0x180085100  movups  xmm0, xmmword ptr [rax+88h]
0x180085107  movups  xmmword ptr [rdi+88h], xmm0
0x18008510e  movups  xmm1, xmmword ptr [rax+98h]
0x180085115  movups  xmmword ptr [rdi+98h], xmm1
0x18008511c  movups  xmm0, xmmword ptr [rax+0A8h]
0x180085123  movups  xmmword ptr [rdi+0A8h], xmm0
0x18008512a  movups  xmm1, xmmword ptr [rax+0B8h]
0x180085131  movups  xmmword ptr [rdi+0B8h], xmm1
0x180085138  mov     eax, [rax+0C8h]
0x18008513e  mov     [rdi+0C8h], eax
0x180085144  xor     ecx, ecx; pv
0x180085146  call    cs:__imp_CoTaskMemFree
0x18008514c  mov     [rsp+1C0h+var_1A0], rsi
0x180085151  mov     [rsp+1C0h+var_1A0], rsi
0x180085156  xor     ecx, ecx; pv
0x180085158  call    cs:__imp_CoTaskMemFree
0x18008515e  mov     [rsp+1C0h+var_198], rsi
0x180085163  mov     [rsp+1C0h+var_198], rsi
0x180085168  xor     ecx, ecx; pv
0x18008516a  call    cs:__imp_CoTaskMemFree
0x180085170  mov     [rsp+1C0h+var_190], rsi
0x180085175  mov     [rsp+1C0h+var_190], rsi
0x18008517a  xor     ecx, ecx; pv
0x18008517c  call    cs:__imp_CoTaskMemFree
0x180085182  mov     [rsp+1C0h+var_188], rsi
0x180085187  mov     [rsp+1C0h+var_188], rsi
0x18008518c  xor     ecx, ecx; pv
0x18008518e  call    cs:__imp_CoTaskMemFree
0x180085194  mov     [rsp+1C0h+var_180], rsi
0x180085199  mov     [rsp+1C0h+var_180], rsi
0x18008519e  xor     ecx, ecx; pv
0x1800851a0  call    cs:__imp_CoTaskMemFree
0x1800851a6  mov     [rsp+1C0h+var_178], rsi
0x1800851ab  mov     [rsp+1C0h+var_178], rsi
0x1800851b0  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800851b7  mov     [rbp+0C0h+var_D0], rax
0x1800851bb  lea     rcx, [rbp+0C0h+var_D0]; this
0x1800851bf  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800851c4  mov     rcx, [rbp+0C0h+var_20]
0x1800851cb  xor     rcx, rsp; StackCookie
0x1800851ce  call    __security_check_cookie
0x1800851d3  mov     rbx, [rsp+1C0h+arg_10]
0x1800851db  add     rsp, 1B0h
0x1800851e2  pop     rdi
0x1800851e3  pop     rsi
0x1800851e4  pop     rbp
0x1800851e5  retn
```

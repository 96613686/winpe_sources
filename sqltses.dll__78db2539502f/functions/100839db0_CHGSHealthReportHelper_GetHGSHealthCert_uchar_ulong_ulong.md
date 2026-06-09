# CHGSHealthReportHelper::GetHGSHealthCert(uchar *,ulong,ulong *)

- ea: `0x100839db0`
- end: `0x10083a05c`
- name: `?GetHGSHealthCert@CHGSHealthReportHelper@@SAJPEAEKPEAK@Z`
- size: `684`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1008337c0`

## callees

- `0x100401cc0`
- `0x100839680`
- `0x100839ae0`
- `0x100839db0`
- `0x10083a0a0`

## import_xrefs

- `ole32!CoUninitialize` at `0x10083a03a`
- `ole32!CoUninitialize` at `0x10083a03a`
- `OLEAUT32!__imp_VariantInit` at `0x100839e38`
- `OLEAUT32!__imp_VariantInit` at `0x100839f0a`
- `OLEAUT32!__imp_VariantInit` at `0x100839e38`
- `OLEAUT32!__imp_VariantInit` at `0x100839f0a`
- `OLEAUT32!__imp_VariantClear` at `0x100839fd3`
- `OLEAUT32!__imp_VariantClear` at `0x100839fdf`
- `OLEAUT32!__imp_VariantClear` at `0x100839ff6`
- `OLEAUT32!__imp_VariantClear` at `0x10083a013`
- `OLEAUT32!__imp_VariantClear` at `0x10083a033`
- `OLEAUT32!__imp_VariantClear` at `0x100839fd3`
- `OLEAUT32!__imp_VariantClear` at `0x100839fdf`
- `OLEAUT32!__imp_VariantClear` at `0x100839ff6`
- `OLEAUT32!__imp_VariantClear` at `0x10083a013`
- `OLEAUT32!__imp_VariantClear` at `0x10083a033`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x100839fa1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x100839fa1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x100839fc8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x100839fc8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839e1e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839e85`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839ede`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839f6c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839e1e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839e85`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839ede`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839f6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CHGSHealthReportHelper::GetHGSHealthCert(unsigned __int8 *a1, int a2, unsigned int *a3)
{
  SAFEARRAY *parray; // rbx
  __int64 v8; // [rsp+28h] [rbp-80h]
  __int64 v9; // [rsp+28h] [rbp-80h]
  struct IWbemClassObject *v10; // [rsp+30h] [rbp-78h] BYREF
  VARIANTARG v11; // [rsp+38h] [rbp-70h] BYREF
  struct IWbemServices *v12; // [rsp+50h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-50h] BYREF
  void *ppvData[3]; // [rsp+70h] [rbp-38h] BYREF
  VARIANTARG psa; // [rsp+88h] [rbp-20h]
  int v16; // [rsp+C8h] [rbp+20h]
  int HealthCertInternal; // [rsp+C8h] [rbp+20h]
  int v18; // [rsp+C8h] [rbp+20h]
  int v19; // [rsp+C8h] [rbp+20h]

  ppvData[1] = (void *)-2LL;
  v12 = 0;
  v16 = CHGSHealthReportHelper::InitializeWMI(&v12);
  if ( v16 < 0 )
  {
    _mm_lfence();
    ex_raise(373, 14, 16, 14, L"WMI Initialization", v16);
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  HealthCertInternal = CHGSHealthReportHelper::GetHealthCertInternal(v12, (struct ATL::CComVariant *)&pvarg);
  if ( HealthCertInternal < 0 )
  {
    _mm_lfence();
    LODWORD(v8) = HealthCertInternal;
    ex_raise(373, 14, 16, 15, L"GetHealthCertInternal", v8);
  }
  v10 = 0;
  v18 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IWbemClassObject **))pvarg.llVal)(
          pvarg.llVal,
          &IID_IWbemClassObject,
          &v10);
  if ( v18 < 0 )
  {
    _mm_lfence();
    LODWORD(v8) = v18;
    ex_raise(373, 14, 16, 16, L"Get cmdletOutput", v8);
  }
  if ( (int)CHGSHealthReportHelper::ValidateStatus(v10) < 0 )
    goto LABEL_16;
  memset(&v11, 0, sizeof(v11));
  VariantInit(&v11);
  v19 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v10->lpVtbl->Get)(
          v10,
          L"Data",
          0,
          &v11,
          0,
          0);
  if ( v19 < 0 )
  {
    _mm_lfence();
    LODWORD(v9) = v19;
    ex_raise(373, 14, 16, 17, L"Get Data", v9);
  }
  psa = v11;
  if ( a1 && a2 )
  {
    SafeArrayAccessData(v11.parray, ppvData);
    parray = psa.parray;
    memmove(a1, ppvData[0], *(unsigned int *)(psa.llVal + 24));
    *a3 = parray->rgsabound[0].cElements;
    SafeArrayUnaccessData(parray);
    VariantClear(&pvarg);
    VariantClear(&v11);
LABEL_16:
    if ( v10 )
      ((void (__fastcall *)(struct IWbemClassObject *))v10->lpVtbl->Release)(v10);
    VariantClear(&pvarg);
    CoUninitialize();
    return 0;
  }
  *a3 = *(_DWORD *)(v11.llVal + 24);
  VariantClear(&v11);
  if ( v10 )
    ((void (__fastcall *)(struct IWbemClassObject *))v10->lpVtbl->Release)(v10);
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x100839db0  mov     rax, rsp
0x100839db3  push    r14
0x100839db5  sub     rsp, 0A0h
0x100839dbc  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x100839dc4  mov     [rax+8], rbx
0x100839dc8  mov     [rax+10h], rsi
0x100839dcc  mov     [rax+18h], rdi
0x100839dd0  mov     rdi, r8
0x100839dd3  mov     ebx, edx
0x100839dd5  mov     rsi, rcx
0x100839dd8  xor     r14d, r14d
0x100839ddb  mov     [rax-58h], r14
0x100839ddf  lea     rcx, [rax-58h]; struct IWbemServices **
0x100839de3  call    ?InitializeWMI@CHGSHealthReportHelper@@CAJPEAPEAUIWbemServices@@@Z; CHGSHealthReportHelper::InitializeWMI(IWbemServices * *)
0x100839de8  mov     [rsp+0A8h+arg_18], eax
0x100839def  test    eax, eax
0x100839df1  jns     short loc_100839E24
0x100839df3  lfence
0x100839df6  mov     eax, [rsp+0A8h+arg_18]
0x100839dfd  mov     dword ptr [rsp+0A8h+var_80], eax
0x100839e01  lea     rax, aWmiInitializat; "WMI Initialization"
0x100839e08  mov     [rsp+0A8h+var_88], rax
0x100839e0d  mov     edx, 0Eh
0x100839e12  mov     r9d, edx
0x100839e15  lea     r8d, [r14+10h]
0x100839e19  mov     ecx, 175h
0x100839e1e  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100839e24  xorps   xmm0, xmm0
0x100839e27  xor     eax, eax
0x100839e29  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x100839e2e  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x100839e33  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x100839e38  call    cs:__imp_VariantInit
0x100839e3e  nop
0x100839e3f  lea     rdx, [rsp+0A8h+pvarg]; struct ATL::CComVariant *
0x100839e44  mov     rcx, [rsp+0A8h+var_58]; struct IWbemServices *
0x100839e49  call    ?GetHealthCertInternal@CHGSHealthReportHelper@@CAJPEAUIWbemServices@@PEAVCComVariant@ATL@@@Z; CHGSHealthReportHelper::GetHealthCertInternal(IWbemServices *,ATL::CComVariant *)
0x100839e4e  mov     [rsp+0A8h+arg_18], eax
0x100839e55  test    eax, eax
0x100839e57  jns     short loc_100839E8B
0x100839e59  lfence
0x100839e5c  mov     eax, [rsp+0A8h+arg_18]
0x100839e63  mov     dword ptr [rsp+0A8h+var_80], eax
0x100839e67  lea     rax, aGethealthcerti; "GetHealthCertInternal"
0x100839e6e  mov     [rsp+0A8h+var_88], rax
0x100839e73  mov     edx, 0Eh
0x100839e78  lea     r9d, [rdx+1]
0x100839e7c  lea     r8d, [rdx+2]
0x100839e80  mov     ecx, 175h
0x100839e85  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100839e8b  mov     [rsp+0A8h+var_78], r14
0x100839e90  mov     rcx, qword ptr [rsp+0A8h+pvarg+8]
0x100839e95  mov     rax, [rcx]
0x100839e98  lea     r8, [rsp+0A8h+var_78]
0x100839e9d  lea     rdx, IID_IWbemClassObject
0x100839ea4  call    qword ptr [rax]
0x100839ea6  mov     [rsp+0A8h+arg_18], eax
0x100839ead  test    eax, eax
0x100839eaf  jns     short loc_100839EE4
0x100839eb1  lfence
0x100839eb4  mov     eax, [rsp+0A8h+arg_18]
0x100839ebb  mov     dword ptr [rsp+0A8h+var_80], eax
0x100839ebf  lea     rax, aGetCmdletoutpu; "Get cmdletOutput"
0x100839ec6  mov     [rsp+0A8h+var_88], rax
0x100839ecb  mov     edx, 0Eh
0x100839ed0  mov     r9d, 10h
0x100839ed6  mov     r8d, r9d
0x100839ed9  mov     ecx, 175h
0x100839ede  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100839ee4  mov     rcx, [rsp+0A8h+var_78]; struct IWbemClassObject *
0x100839ee9  call    ?ValidateStatus@CHGSHealthReportHelper@@CAJPEAUIWbemClassObject@@@Z; CHGSHealthReportHelper::ValidateStatus(IWbemClassObject *)
0x100839eee  test    eax, eax
0x100839ef0  js      loc_10083A01D
0x100839ef6  xorps   xmm0, xmm0
0x100839ef9  xor     eax, eax
0x100839efb  movups  xmmword ptr [rsp+0A8h+var_70], xmm0
0x100839f00  mov     qword ptr [rsp+0A8h+var_70+10h], rax
0x100839f05  lea     rcx, [rsp+0A8h+var_70]; pvarg
0x100839f0a  call    cs:__imp_VariantInit
0x100839f10  nop
0x100839f11  mov     rcx, [rsp+0A8h+var_78]
0x100839f16  mov     rax, [rcx]
0x100839f19  mov     [rsp+0A8h+var_80], r14
0x100839f1e  mov     [rsp+0A8h+var_88], r14
0x100839f23  lea     r9, [rsp+0A8h+var_70]
0x100839f28  xor     r8d, r8d
0x100839f2b  lea     rdx, aData_2; "Data"
0x100839f32  call    qword ptr [rax+20h]
0x100839f35  mov     [rsp+0A8h+arg_18], eax
0x100839f3c  test    eax, eax
0x100839f3e  jns     short loc_100839F72
0x100839f40  lfence
0x100839f43  mov     eax, [rsp+0A8h+arg_18]
0x100839f4a  mov     dword ptr [rsp+0A8h+var_80], eax
0x100839f4e  lea     rax, aGetData; "Get Data"
0x100839f55  mov     [rsp+0A8h+var_88], rax
0x100839f5a  mov     edx, 0Eh
0x100839f5f  lea     r9d, [rdx+3]
0x100839f63  lea     r8d, [rdx+2]
0x100839f67  mov     ecx, 175h
0x100839f6c  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100839f72  movups  xmm0, xmmword ptr [rsp+0A8h+var_70]
0x100839f77  movups  xmmword ptr [rsp+0A8h+psa], xmm0
0x100839f7f  movsd   xmm1, qword ptr [rsp+0A8h+var_70+10h]
0x100839f85  movsd   [rsp+0A8h+var_10], xmm1
0x100839f8e  test    rsi, rsi
0x100839f91  jz      short loc_100839FE7
0x100839f93  test    ebx, ebx
0x100839f95  jz      short loc_100839FE7
0x100839f97  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x100839f9c  mov     rcx, qword ptr [rsp+0A8h+var_70+8]; psa
0x100839fa1  call    cs:__imp_SafeArrayAccessData
0x100839fa7  mov     rbx, [rsp+0A8h+psa+8]
0x100839faf  mov     r8d, [rbx+18h]; Size
0x100839fb3  mov     rdx, [rsp+0A8h+ppvData]; Src
0x100839fb8  mov     rcx, rsi; void *
0x100839fbb  call    memmove
0x100839fc0  mov     eax, [rbx+18h]
0x100839fc3  mov     [rdi], eax
0x100839fc5  mov     rcx, rbx; psa
0x100839fc8  call    cs:__imp_SafeArrayUnaccessData
0x100839fce  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x100839fd3  call    cs:__imp_VariantClear
0x100839fd9  nop
0x100839fda  lea     rcx, [rsp+0A8h+var_70]; pvarg
0x100839fdf  call    cs:__imp_VariantClear
0x100839fe5  jmp     short loc_10083A01D
0x100839fe7  mov     rax, qword ptr [rsp+0A8h+var_70+8]
0x100839fec  mov     ecx, [rax+18h]
0x100839fef  mov     [rdi], ecx
0x100839ff1  lea     rcx, [rsp+0A8h+var_70]; pvarg
0x100839ff6  call    cs:__imp_VariantClear
0x100839ffc  nop
0x100839ffd  mov     rcx, [rsp+0A8h+var_78]
0x10083a002  test    rcx, rcx
0x10083a005  jz      short loc_10083A00E
0x10083a007  mov     rax, [rcx]
0x10083a00a  call    qword ptr [rax+10h]
0x10083a00d  nop
0x10083a00e  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x10083a013  call    cs:__imp_VariantClear
0x10083a019  xor     eax, eax
0x10083a01b  jmp     short loc_10083A042
0x10083a01d  mov     rcx, [rsp+0A8h+var_78]
0x10083a022  test    rcx, rcx
0x10083a025  jz      short loc_10083A02E
0x10083a027  mov     rax, [rcx]
0x10083a02a  call    qword ptr [rax+10h]
0x10083a02d  nop
0x10083a02e  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x10083a033  call    cs:__imp_VariantClear
0x10083a039  nop
0x10083a03a  call    cs:__imp_CoUninitialize
0x10083a040  xor     eax, eax
0x10083a042  lea     r11, [rsp+0A8h+var_8]
0x10083a04a  mov     rbx, [r11+10h]
0x10083a04e  mov     rsi, [r11+18h]
0x10083a052  mov     rdi, [r11+20h]
0x10083a056  mov     rsp, r11
0x10083a059  pop     r14
0x10083a05b  retn
```

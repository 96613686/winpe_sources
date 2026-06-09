# DeviceIdentityImplementation::GetDevicePostData(ushort * *)

- ea: `0x180035690`
- end: `0x180035829`
- name: `?GetDevicePostData@DeviceIdentityImplementation@@UEAAJPEAPEAG@Z`
- size: `409`
- prototype: `__int64 __fastcall(DeviceIdentityImplementation *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800034c0`
- `0x180003990`
- `0x180003cb0`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x180010b80`
- `0x180013434`
- `0x180016ea0`
- `0x1800199e4`
- `0x180030b40`
- `0x180032b88`
- `0x180035690`
- `0x18004670c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003577e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003577e`

## string_xrefs

- `0x18003572f`: `hr = WLIDCGetDeviceDAToken(&pDeviceDAToken)`
- `0x1800357b9`: `hr = StringCchCopyW(pCopyOfPostData, bufferSizeChar, urlEscapedPostData.GetBuffer(bufferSizeChar))`

## pseudocode

```c
__int64 __fastcall DeviceIdentityImplementation::GetDevicePostData(
        DeviceIdentityImplementation *this,
        unsigned __int16 **a2)
{
  unsigned int v3; // edx
  int v4; // eax
  unsigned int v5; // esi
  unsigned __int16 *v6; // rdi
  const unsigned __int16 *v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  char *v11; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v12; // [rsp+30h] [rbp-40h] BYREF
  __int64 v13; // [rsp+38h] [rbp-38h]
  __int64 v14; // [rsp+40h] [rbp-30h]
  _QWORD v15[5]; // [rsp+48h] [rbp-28h] BYREF
  int v16; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 *v18; // [rsp+B8h] [rbp+48h] BYREF

  v16 = 0;
  v18 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v17);
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v15[0] = "DeviceIdentityImplementation::GetDevicePostData";
  v15[1] = &v16;
  v15[2] = 0;
  v15[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\deviceidentityimplementation.cpp",
    "DeviceIdentityImplementation::GetDevicePostData",
    (const char *)0x2A,
    0,
    (const unsigned __int16 *)v11);
  if ( !a2 )
    goto LABEL_9;
  *a2 = 0;
  v4 = WLIDCGetDeviceDAToken(&v18, v3);
  v16 = v4;
  if ( v4 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\deviceidentityimplementation.cpp",
      "DeviceIdentityImplementation::GetDevicePostData",
      0x2Fu,
      v4,
      "hr = WLIDCGetDeviceDAToken(&pDeviceDAToken)");
    goto LABEL_10;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v17, v18);
  UrlEscapeString(&v17);
  v5 = *(_DWORD *)(v17 - 16) + 1;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v5);
  Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::Clear(&v12);
  v12 = v6;
  if ( v6 )
  {
    v7 = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(&v17, v5);
    v8 = StringCchCopyW(v6, v5, v7);
    v16 = v8;
    if ( v8 >= 0 )
    {
      v12 = 0;
      v13 = 0;
      *a2 = v6;
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\deviceidentityimplementation.cpp",
        "DeviceIdentityImplementation::GetDevicePostData",
        0x39u,
        v8,
        "hr = StringCchCopyW(pCopyOfPostData, bufferSizeChar, urlEscapedPostData.GetBuffer(bufferSizeChar))");
    }
  }
  else
  {
LABEL_9:
    v16 = -2147024882;
  }
LABEL_10:
  v9 = v16;
  CTraceFuncW<long>::~CTraceFuncW<long>(v15);
  Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(&v12);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v17);
  CMIDLPtr<unsigned short *>::Clear(&v18);
  return v9;
}

```

## disassembly

```asm
0x180035690  mov     [rsp-28h+arg_0], rbx
0x180035695  push    rbp
0x180035696  push    rsi
0x180035697  push    rdi
0x180035698  push    r12
0x18003569a  push    r14
0x18003569c  mov     rbp, rsp
0x18003569f  sub     rsp, 70h
0x1800356a3  lea     rcx, [rbp+arg_10]; void *
0x1800356a7  mov     [rbp+arg_8], 0
0x1800356ae  mov     rbx, rdx
0x1800356b1  mov     [rbp+arg_18], 0
0x1800356b9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800356be  xor     r9d, r9d; unsigned int
0x1800356c1  mov     [rbp+var_40], 0
0x1800356c9  lea     r12, aDeviceidentity; "DeviceIdentityImplementation::GetDevice"...
0x1800356d0  mov     [rbp+var_30], 0
0x1800356d8  lea     rax, [rbp+arg_8]
0x1800356dc  mov     [rbp+var_38], 0
0x1800356e4  mov     rdx, r12; char *
0x1800356e7  mov     [rbp+var_28], r12
0x1800356eb  lea     r8d, [r9+2Ah]; char *
0x1800356ef  mov     [rbp+var_20], rax
0x1800356f3  lea     rcx, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800356fa  mov     [rbp+var_18], 0
0x180035702  mov     [rbp+var_10], 0
0x18003570a  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003570f  test    rbx, rbx
0x180035712  jz      loc_1800357E5
0x180035718  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x18003571c  mov     qword ptr [rbx], 0
0x180035723  call    ?WLIDCGetDeviceDAToken@@YAJPEAPEAG@Z; WLIDCGetDeviceDAToken(ushort * *)
0x180035728  mov     [rbp+arg_8], eax
0x18003572b  test    eax, eax
0x18003572d  jns     short loc_180035758
0x18003572f  lea     r8, aHrWlidcgetdevi; "hr = WLIDCGetDeviceDAToken(&pDeviceDATo"...
0x180035736  mov     [rsp+70h+var_50], r8; char *
0x18003573b  mov     r8d, 2Fh ; '/'; unsigned int
0x180035741  mov     r9d, eax; int
0x180035744  lea     rcx, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18003574b  mov     rdx, r12; char *
0x18003574e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180035753  jmp     loc_1800357EC
0x180035758  mov     rdx, [rbp+arg_18]
0x18003575c  lea     rcx, [rbp+arg_10]
0x180035760  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180035765  lea     rcx, [rbp+arg_10]
0x180035769  call    ?UrlEscapeString@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; UrlEscapeString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003576e  mov     rax, [rbp+arg_10]
0x180035772  mov     esi, [rax-10h]
0x180035775  inc     esi
0x180035777  mov     r14d, esi
0x18003577a  lea     rcx, [rsi+rsi]; cb
0x18003577e  call    cs:__imp_CoTaskMemAlloc
0x180035784  lea     rcx, [rbp+var_40]
0x180035788  mov     rdi, rax
0x18003578b  call    ?Clear@?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@QEAAXXZ; Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext>::Clear(void)
0x180035790  mov     [rbp+var_40], rdi
0x180035794  test    rdi, rdi
0x180035797  jz      short loc_1800357E5
0x180035799  mov     edx, esi
0x18003579b  lea     rcx, [rbp+arg_10]
0x18003579f  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800357a4  mov     r8, rax; unsigned __int16 *
0x1800357a7  mov     edx, r14d; unsigned __int64
0x1800357aa  mov     rcx, rdi; unsigned __int16 *
0x1800357ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800357b2  mov     [rbp+arg_8], eax
0x1800357b5  test    eax, eax
0x1800357b7  jns     short loc_1800357D0
0x1800357b9  lea     rcx, aHrStringcchcop; "hr = StringCchCopyW(pCopyOfPostData, bu"...
0x1800357c0  mov     r8d, 39h ; '9'
0x1800357c6  mov     [rsp+70h+var_50], rcx
0x1800357cb  jmp     loc_180035741
0x1800357d0  mov     [rbp+var_40], 0
0x1800357d8  mov     [rbp+var_38], 0
0x1800357e0  mov     [rbx], rdi
0x1800357e3  jmp     short loc_1800357EC
0x1800357e5  mov     [rbp+arg_8], 8007000Eh
0x1800357ec  mov     ebx, [rbp+arg_8]
0x1800357ef  lea     rcx, [rbp+var_28]
0x1800357f3  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800357f8  lea     rcx, [rbp+var_40]
0x1800357fc  call    ??1?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext>::~Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext>(void)
0x180035801  lea     rcx, [rbp+arg_10]; void *
0x180035805  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003580a  lea     rcx, [rbp+arg_18]
0x18003580e  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x180035813  mov     eax, ebx
0x180035815  mov     rbx, [rsp+70h+arg_0]
0x18003581d  add     rsp, 70h
0x180035821  pop     r14
0x180035823  pop     r12
0x180035825  pop     rdi
0x180035826  pop     rsi
0x180035827  pop     rbp
0x180035828  retn
```

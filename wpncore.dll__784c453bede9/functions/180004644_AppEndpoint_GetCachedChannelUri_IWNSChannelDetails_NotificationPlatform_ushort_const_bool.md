# AppEndpoint::GetCachedChannelUri(IWNSChannelDetails *,NotificationPlatform *,ushort const *,bool *)

- ea: `0x180004644`
- end: `0x1800048c4`
- name: `?GetCachedChannelUri@AppEndpoint@@QEAAJPEAUIWNSChannelDetails@@PEAVNotificationPlatform@@PEBGPEA_N@Z`
- size: `640`
- prototype: `int(AppEndpoint *__hidden this, struct IWNSChannelDetails *, struct NotificationPlatform *, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004d8c4`
- `0x18009f8a8`

## callees

- `0x180004644`
- `0x18000568c`
- `0x18000e5f4`
- `0x18004c9e4`
- `0x18004ca20`
- `0x180088be4`
- `0x1800cc7dc`
- `0x1800ccf5c`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004823`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004823`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004833`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004848`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000485d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004833`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004848`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000485d`

## pseudocode

```c
__int64 __fastcall AppEndpoint::GetCachedChannelUri(
        AppEndpoint *this,
        struct IWNSChannelDetails *a2,
        struct NotificationPlatform *a3,
        const unsigned __int16 *a4,
        bool *a5)
{
  int v8; // eax
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int64 v11; // rsi
  __int64 v12; // rcx
  const char *v13; // r9
  int v14; // eax
  int v15; // eax
  int v16; // eax
  const char *v17; // r9
  bool v18; // cl
  __int64 v19; // rcx
  WpncoreTelemetry *v20; // rax
  __int64 result; // rax
  int v22; // [rsp+20h] [rbp-68h]
  _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-58h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int64 v25; // [rsp+40h] [rbp-48h] BYREF
  FILETIME FileTime2; // [rsp+48h] [rbp-40h] BYREF
  FILETIME v27; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned __int64 v29; // [rsp+90h] [rbp+8h] BYREF

  v29 = 0;
  try
  {
    WpnGetDeviceVersionFromRegistry(&v29);
    v25 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AG780>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AG780>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Throw_HrIfNullMsg<IWNSChannelDetails *,0>(
        (_DWORD)retaddr,
        3702,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
        -2147024809,
        (__int64)a2);
    v8 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, unsigned __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v25);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE79,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
        (const char *)(unsigned int)v8,
        v22);
    v11 = v29;
    if ( v29 == v25 )
    {
      v12 = *((_QWORD *)a3 + 29);
      v13 = v12 == 0 ? (const char *)0x803E0105LL : 0LL;
      if ( !v12 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE80,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          v13,
          v22);
      LODWORD(v29) = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, __int64, const char *))(*(_QWORD *)v12 + 24LL))(
              v12,
              &v29,
              v10,
              v13);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE82,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)(unsigned int)v14,
          v22);
      FileTime1 = 0;
      v15 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, FILETIME *))(*(_QWORD *)a2 + 48LL))(a2, &FileTime1);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE85,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)(unsigned int)v15,
          v22);
      v27 = (FILETIME)(10000000LL * (unsigned int)v29 + *(_QWORD *)&FileTime1);
      FileTime2 = 0;
      v16 = (*(__int64 (__fastcall **)(struct IWNSChannelDetails *, FILETIME *))(*(_QWORD *)a2 + 56LL))(a2, &FileTime2);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE94,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)(unsigned int)v16,
          v22);
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v18 = CompareFileTime(&SystemTimeAsFileTime, &FileTime2) == -1
         && CompareFileTime(&SystemTimeAsFileTime, &v27) == -1
         && CompareFileTime(&FileTime1, &SystemTimeAsFileTime) == -1;
      *a5 = v18;
    }
    else
    {
      *a5 = 0;
      if ( WpncoreTelemetry::IsEnabled((unsigned __int8)retaddr, v9) )
      {
        v20 = (WpncoreTelemetry *)wil::details::static_lazy<WpncoreTelemetry>::get(
                                    v19,
                                    _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_);
        WpncoreTelemetry::ChannelVersionChanged_(v20, a4, v11, v25);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v29) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xEAB,
                     (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
                     v17);
    return (unsigned int)v29;
  }
  return result;
}

```

## disassembly

```asm
0x180004644  mov     rax, rsp
0x180004647  mov     [rax+8], rcx
0x18000464b  push    rsi
0x18000464c  push    rdi
0x18000464d  push    r14
0x18000464f  push    r15
0x180004651  sub     rsp, 68h
0x180004655  mov     r15, r9
0x180004658  mov     r14, r8
0x18000465b  mov     rdi, rdx
0x18000465e  mov     qword ptr [rax+8], 0
0x180004666  lea     rcx, [rax+8]; unsigned __int64 *
0x18000466a  call    ?WpnGetDeviceVersionFromRegistry@@YAXPEA_K@Z; WpnGetDeviceVersionFromRegistry(unsigned __int64 *)
0x18000466f  mov     [rsp+88h+var_48], 0
0x180004678  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AG780@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AG780@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AG780> `wil::Feature<__WilFeatureTraits_Feature_AG780>::GetImpl(void)'::`2'::impl
0x18000467f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AG780@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AG780>::__private_IsEnabled(void)
0x180004684  test    al, al
0x180004686  jz      short loc_1800046B8
0x180004688  mov     rcx, [rsp+88h]
0x180004690  lea     rax, aChanneldetails; "channelDetails is NULL"
0x180004697  mov     [rsp+88h+var_60], rax
0x18000469c  mov     qword ptr [rsp+88h+var_68], rdi; int
0x1800046a1  mov     r9d, 80070057h
0x1800046a7  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800046ae  mov     edx, 0E76h
0x1800046b3  call    ??$Throw_HrIfNullMsg@PEAUIWNSChannelDetails@@$0A@@in1diag3@details@wil@@YAPEAUIWNSChannelDetails@@PEAXIPEBDJPEAU3@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<IWNSChannelDetails *,0>(void *,uint,char const *,long,IWNSChannelDetails *,char const *,...)
0x1800046b8  mov     rax, [rdi]
0x1800046bb  lea     rdx, [rsp+88h+var_48]
0x1800046c0  mov     rcx, rdi
0x1800046c3  mov     rax, [rax+40h]
0x1800046c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046cc  mov     rcx, [rsp+88h]; unsigned __int8
0x1800046d4  test    eax, eax
0x1800046d6  jns     short loc_1800046EC
0x1800046d8  mov     r9d, eax; char *
0x1800046db  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800046e2  mov     edx, 0E79h; void *
0x1800046e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800046ec  mov     rsi, [rsp+88h+arg_0]
0x1800046f4  cmp     rsi, [rsp+88h+var_48]
0x1800046f9  jnz     loc_18000487A
0x1800046ff  mov     rcx, [r14+0E8h]
0x180004706  mov     rax, rcx
0x180004709  neg     rax
0x18000470c  sbb     r9d, r9d
0x18000470f  not     r9d
0x180004712  and     r9d, 803E0105h; char *
0x180004719  mov     rax, [rsp+88h]
0x180004721  test    rcx, rcx
0x180004724  jnz     short loc_18000473A
0x180004726  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000472d  mov     edx, 0E80h; void *
0x180004732  mov     rcx, rax; this
0x180004735  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000473a  mov     dword ptr [rsp+88h+arg_0], 0
0x180004745  mov     rax, [rcx]
0x180004748  lea     rdx, [rsp+88h+arg_0]
0x180004750  mov     rax, [rax+18h]
0x180004754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004759  mov     rcx, [rsp+88h]; this
0x180004761  test    eax, eax
0x180004763  jns     short loc_180004779
0x180004765  mov     r9d, eax; char *
0x180004768  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000476f  mov     edx, 0E82h; void *
0x180004774  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004779  mov     qword ptr [rsp+88h+FileTime1.dwLowDateTime], 0
0x180004782  mov     rax, [rdi]
0x180004785  lea     rdx, [rsp+88h+FileTime1]
0x18000478a  mov     rcx, rdi
0x18000478d  mov     rax, [rax+30h]
0x180004791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004796  mov     rcx, [rsp+88h]; this
0x18000479e  test    eax, eax
0x1800047a0  jns     short loc_1800047B6
0x1800047a2  mov     r9d, eax; char *
0x1800047a5  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800047ac  mov     edx, 0E85h; void *
0x1800047b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800047b6  mov     rax, qword ptr [rsp+88h+FileTime1.dwLowDateTime]
0x1800047bb  mov     ecx, dword ptr [rsp+88h+arg_0]
0x1800047c2  imul    rdx, rcx, 989680h
0x1800047c9  add     rax, rdx
0x1800047cc  mov     [rsp+88h+var_38.dwLowDateTime], eax
0x1800047d0  shr     rax, 20h
0x1800047d4  mov     [rsp+88h+var_38.dwHighDateTime], eax
0x1800047d8  mov     qword ptr [rsp+88h+FileTime2.dwLowDateTime], 0
0x1800047e1  mov     rax, [rdi]
0x1800047e4  lea     rdx, [rsp+88h+FileTime2]
0x1800047e9  mov     rcx, rdi
0x1800047ec  mov     rax, [rax+38h]
0x1800047f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047f5  mov     rcx, [rsp+88h]; this
0x1800047fd  test    eax, eax
0x1800047ff  jns     short loc_180004815
0x180004801  mov     r9d, eax; char *
0x180004804  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000480b  mov     edx, 0E94h; void *
0x180004810  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004815  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000481e  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004823  call    cs:__imp_GetSystemTimeAsFileTime
0x180004829  lea     rdx, [rsp+88h+FileTime2]; lpFileTime2
0x18000482e  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpFileTime1
0x180004833  call    cs:__imp_CompareFileTime
0x180004839  cmp     eax, 0FFFFFFFFh
0x18000483c  jnz     short loc_18000486C
0x18000483e  lea     rdx, [rsp+88h+var_38]; lpFileTime2
0x180004843  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpFileTime1
0x180004848  call    cs:__imp_CompareFileTime
0x18000484e  cmp     eax, 0FFFFFFFFh
0x180004851  jnz     short loc_18000486C
0x180004853  lea     rdx, [rsp+88h+SystemTimeAsFileTime]; lpFileTime2
0x180004858  lea     rcx, [rsp+88h+FileTime1]; lpFileTime1
0x18000485d  call    cs:__imp_CompareFileTime
0x180004863  cmp     eax, 0FFFFFFFFh
0x180004866  jnz     short loc_18000486C
0x180004868  mov     cl, 1
0x18000486a  jmp     short loc_18000486E
0x18000486c  xor     cl, cl
0x18000486e  mov     rax, [rsp+88h+arg_20]
0x180004876  mov     [rax], cl
0x180004878  jmp     short loc_1800048AD
0x18000487a  mov     rax, [rsp+88h+arg_20]
0x180004882  mov     byte ptr [rax], 0
0x180004885  call    ?IsEnabled@WpncoreTelemetry@@SA_NE_K@Z; WpncoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000488a  test    al, al
0x18000488c  jz      short loc_1800048AD
0x18000488e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c91d295e9756ec26c89460bbd269b90b_@@CA@XZ; _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_(void)
0x180004895  call    ?get@?$static_lazy@VWpncoreTelemetry@@@details@wil@@QEAAPEAVWpncoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WpncoreTelemetry>::get(void (*)(void))
0x18000489a  mov     r9, [rsp+88h+var_48]; unsigned __int64
0x18000489f  mov     r8, rsi; unsigned __int64
0x1800048a2  mov     rdx, r15; unsigned __int16 *
0x1800048a5  mov     rcx, rax; this
0x1800048a8  call    ?ChannelVersionChanged_@WpncoreTelemetry@@QEAAXPEBG_K1@Z; WpncoreTelemetry::ChannelVersionChanged_(ushort const *,unsigned __int64,unsigned __int64)
0x1800048ad  xor     eax, eax
0x1800048af  jmp     short loc_1800048B8
0x1800048b1  mov     eax, dword ptr [rsp+88h+arg_0]
0x1800048b8  add     rsp, 68h
0x1800048bc  pop     r15
0x1800048be  pop     r14
0x1800048c0  pop     rdi
0x1800048c1  pop     rsi
0x1800048c2  retn
```

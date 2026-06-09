# Windows::Internal::Notifications::CWpnClient::ParseToast(HSTRING__ *,uint,uint,uchar *,Windows::Internal::Notifications::INotificationValueSet * *)

- ea: `0x1800061f0`
- end: `0x1800064ba`
- name: `?ParseToast@CWpnClient@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@IIPEAEPEAPEAUINotificationValueSet@234@@Z`
- size: `714`
- prototype: `int(Windows::Internal::Notifications::CWpnClient *__hidden this, HSTRING, unsigned int, unsigned int, unsigned __int8 *, struct Windows::Internal::Notifications::INotificationValueSet **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800061f0`
- `0x1800064c0`
- `0x180006800`
- `0x1800068f0`
- `0x1800070e8`
- `0x1800074d0`
- `0x18001ff00`
- `0x180020350`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000624d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000624d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000637c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000637c`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x1800062a9`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x1800062a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::Notifications::CWpnClient::ParseToast(
        Windows::Internal::Notifications::CWpnClient *this,
        HSTRING a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int8 *a5,
        struct Windows::Internal::Notifications::INotificationValueSet **a6)
{
  const WCHAR *StringRawBuffer; // rbx
  LONG PackagesByPackageFamily; // eax
  bool v9; // zf
  int v10; // eax
  unsigned int v11; // ebx
  void *v12; // rbx
  Windows::Internal::Notifications::CNotificationValueSet *v13; // rax
  WCHAR *v14; // rsi
  int v15; // r14d
  __int64 v17; // rdx
  int bufferLength; // [rsp+20h] [rbp-E0h]
  int bufferLengtha; // [rsp+20h] [rbp-E0h]
  UINT32 count; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR packageFullNames; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v24[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR buffer[128]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  *a6 = 0;
  v24[1] = -1;
  v24[2] = -1;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v24[0] = 0;
  memset(pv, 0, sizeof(pv));
  packageFullNames = 0;
  v22[0] = 128;
  count = 1;
  PackagesByPackageFamily = FindPackagesByPackageFamily(
                              StringRawBuffer,
                              0x10u,
                              &count,
                              &packageFullNames,
                              v22,
                              buffer,
                              0);
  v9 = PackagesByPackageFamily == 0;
  if ( PackagesByPackageFamily > 0 )
    v9 = 0;
  if ( v9 && count )
  {
    if ( count != 1 )
    {
      v11 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
        (const char *)0x8000FFFFLL,
        bufferLength);
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
        (const char *)v11,
        bufferLengtha);
      return v11;
    }
    if ( packageFullNames )
    {
      if ( *packageFullNames )
      {
        v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                (__int64)pv,
                (unsigned __int64)packageFullNames,
                0xFFFFFFFFFFFFFFFFuLL);
        v11 = v10;
        if ( v10 < 0 )
        {
          v17 = 172;
LABEL_25:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
            (const char *)(unsigned int)v10,
            bufferLength);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)pv);
          goto LABEL_14;
        }
      }
    }
  }
  else
  {
    v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            (__int64)pv,
            (unsigned __int64)StringRawBuffer,
            0xFFFFFFFFFFFFFFFFuLL);
    v11 = v10;
    if ( v10 < 0 )
    {
      v17 = 178;
      goto LABEL_25;
    }
  }
  v12 = pv[0];
  v24[0] = pv[0];
  *a6 = 0;
  v13 = (Windows::Internal::Notifications::CNotificationValueSet *)operator new(
                                                                     0xC8u,
                                                                     (const struct std::nothrow_t *)std::nothrow);
  if ( !v13 )
  {
    v15 = -2147024882;
    goto LABEL_20;
  }
  v14 = (WCHAR *)Windows::Internal::Notifications::CNotificationValueSet::CNotificationValueSet(v13);
  packageFullNames = v14;
  *(_QWORD *)v22 = 0;
  bufferLength = (int)a5;
  v15 = Windows::Internal::Notifications::CNotificationValueSet::RuntimeClassInitialize(v14, v12, a3, 1);
  if ( v15 < 0 )
  {
    if ( v14 )
      (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v14 + 16LL))(v14);
    goto LABEL_20;
  }
  v15 = (**(__int64 (__fastcall ***)(WCHAR *, GUID *, struct Windows::Internal::Notifications::INotificationValueSet **))v14)(
          v14,
          &GUID_07978036_2587_417d_85d1_6fa18e9c67e1,
          a6);
  (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v15 < 0 )
  {
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
      (const char *)(unsigned int)v15,
      bufferLength);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v24);
    return (unsigned int)v15;
  }
  if ( v12 )
    CoTaskMemFree(v12);
  return 0;
}

```

## disassembly

```asm
0x1800061f0  push    rbp
0x1800061f2  push    rbx
0x1800061f3  push    rsi
0x1800061f4  push    rdi
0x1800061f5  push    r12
0x1800061f7  push    r13
0x1800061f9  push    r14
0x1800061fb  push    r15
0x1800061fd  lea     rbp, [rsp-0A8h]
0x180006205  sub     rsp, 1A8h
0x18000620c  mov     rax, cs:__security_cookie
0x180006213  xor     rax, rsp
0x180006216  mov     [rbp+0E0h+var_50], rax
0x18000621d  mov     r14d, r9d
0x180006220  mov     r15d, r8d
0x180006223  mov     rcx, rdx; string
0x180006226  mov     r12, [rbp+0E0h+arg_20]
0x18000622d  mov     rdi, [rbp+0E0h+arg_28]
0x180006234  xor     r13d, r13d
0x180006237  mov     [rdi], r13
0x18000623a  mov     [rsp+1E0h+var_168], 0FFFFFFFFFFFFFFFFh
0x180006243  mov     [rbp+0E0h+var_160], 0FFFFFFFFFFFFFFFFh
0x18000624b  xor     edx, edx; length
0x18000624d  call    cs:__imp_WindowsGetStringRawBuffer
0x180006253  mov     rbx, rax
0x180006256  mov     [rsp+1E0h+var_170], r13
0x18000625b  mov     [rsp+1E0h+pv], r13
0x180006260  mov     [rsp+1E0h+var_180], r13
0x180006265  mov     [rsp+1E0h+var_178], r13
0x18000626a  mov     [rsp+1E0h+packageFullNames], r13
0x18000626f  mov     [rsp+1E0h+var_190], 80h
0x180006277  mov     [rsp+1E0h+count], 1
0x18000627f  mov     [rsp+1E0h+packageProperties], r13; packageProperties
0x180006284  lea     rax, [rbp+0E0h+var_150]
0x180006288  mov     [rsp+1E0h+buffer], rax; buffer
0x18000628d  lea     rax, [rsp+1E0h+var_190]
0x180006292  mov     [rsp+1E0h+bufferLength], rax; int
0x180006297  lea     r9, [rsp+1E0h+packageFullNames]; packageFullNames
0x18000629c  lea     r8, [rsp+1E0h+count]; count
0x1800062a1  mov     edx, 10h; packageFilters
0x1800062a6  mov     rcx, rbx; packageFamilyName
0x1800062a9  call    cs:__imp_FindPackagesByPackageFamily
0x1800062af  test    eax, eax
0x1800062b1  jg      loc_180006432
0x1800062b7  jz      loc_180006386
0x1800062bd  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800062c4  mov     rdx, rbx
0x1800062c7  lea     rcx, [rsp+1E0h+pv]
0x1800062cc  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800062d1  mov     ebx, eax
0x1800062d3  test    eax, eax
0x1800062d5  js      loc_18000648C
0x1800062db  mov     rbx, [rsp+1E0h+pv]
0x1800062e0  mov     [rsp+1E0h+var_170], rbx
0x1800062e5  mov     [rdi], r13
0x1800062e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800062ef  mov     ecx, 0C8h; unsigned __int64
0x1800062f4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800062f9  test    rax, rax
0x1800062fc  jz      loc_180006441
0x180006302  mov     rcx, rax; this
0x180006305  call    ??0CNotificationValueSet@Notifications@Internal@Windows@@QEAA@XZ; Windows::Internal::Notifications::CNotificationValueSet::CNotificationValueSet(void)
0x18000630a  mov     rsi, rax
0x18000630d  mov     [rsp+1E0h+packageFullNames], rax
0x180006312  mov     qword ptr [rsp+1E0h+var_190], r13
0x180006317  mov     dword ptr [rsp+1E0h+buffer], r14d
0x18000631c  mov     [rsp+1E0h+bufferLength], r12
0x180006321  mov     r9d, 1
0x180006327  mov     r8d, r15d
0x18000632a  mov     rdx, rbx
0x18000632d  mov     rcx, rax
0x180006330  call    ?RuntimeClassInitialize@CNotificationValueSet@Notifications@Internal@Windows@@QEAAJPEBGW4WPN_APP_TYPE@@W4WPN_NOTIFICATION_TYPE@234@PEAEK@Z; Windows::Internal::Notifications::CNotificationValueSet::RuntimeClassInitialize(ushort const *,WPN_APP_TYPE,Windows::Internal::Notifications::WPN_NOTIFICATION_TYPE,uchar *,ulong)
0x180006335  mov     r14d, eax
0x180006338  test    eax, eax
0x18000633a  js      loc_180006475
0x180006340  mov     rax, [rsi]
0x180006343  mov     r8, rdi
0x180006346  lea     rdx, _GUID_07978036_2587_417d_85d1_6fa18e9c67e1
0x18000634d  mov     rcx, rsi
0x180006350  mov     rax, [rax]
0x180006353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006358  mov     r14d, eax
0x18000635b  mov     rax, [rsi]
0x18000635e  mov     rcx, rsi
0x180006361  mov     rax, [rax+10h]
0x180006365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636a  nop
0x18000636b  test    r14d, r14d
0x18000636e  js      loc_180006447
0x180006374  test    rbx, rbx
0x180006377  jz      short loc_180006382
0x180006379  mov     rcx, rbx; pv
0x18000637c  call    cs:__imp_CoTaskMemFree
0x180006382  xor     eax, eax
0x180006384  jmp     short loc_1800063D5
0x180006386  mov     eax, [rsp+1E0h+count]
0x18000638a  test    eax, eax
0x18000638c  jz      loc_1800062BD
0x180006392  cmp     eax, 1
0x180006395  jz      short loc_1800063F8
0x180006397  mov     rcx, [rbp+0E8h]; this
0x18000639e  mov     ebx, 8000FFFFh
0x1800063a3  mov     r9d, ebx; char *
0x1800063a6  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800063ad  mov     edx, 0A8h; void *
0x1800063b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063b7  mov     rcx, [rbp+0E8h]; this
0x1800063be  mov     r9d, ebx; char *
0x1800063c1  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800063c8  mov     edx, 45h ; 'E'; void *
0x1800063cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063d2  nop
0x1800063d3  mov     eax, ebx
0x1800063d5  mov     rcx, [rbp+0E0h+var_50]
0x1800063dc  xor     rcx, rsp; StackCookie
0x1800063df  call    __security_check_cookie
0x1800063e4  add     rsp, 1A8h
0x1800063eb  pop     r15
0x1800063ed  pop     r14
0x1800063ef  pop     r13
0x1800063f1  pop     r12
0x1800063f3  pop     rdi
0x1800063f4  pop     rsi
0x1800063f5  pop     rbx
0x1800063f6  pop     rbp
0x1800063f7  retn
0x1800063f8  mov     rdx, [rsp+1E0h+packageFullNames]
0x1800063fd  test    rdx, rdx
0x180006400  jz      loc_1800062DB
0x180006406  cmp     word ptr [rdx], 0
0x18000640a  jz      loc_1800062DB
0x180006410  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180006417  lea     rcx, [rsp+1E0h+pv]
0x18000641c  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180006421  mov     ebx, eax
0x180006423  test    eax, eax
0x180006425  jns     loc_1800062DB
0x18000642b  mov     edx, 0ACh
0x180006430  jmp     short loc_180006491
0x180006432  movzx   eax, ax
0x180006435  or      eax, 80070000h
0x18000643a  test    eax, eax
0x18000643c  jmp     loc_1800062B7
0x180006441  mov     r14d, 8007000Eh
0x180006447  mov     rcx, [rbp+0E8h]; this
0x18000644e  mov     r9d, r14d; char *
0x180006451  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006458  mov     edx, 4Dh ; 'M'; void *
0x18000645d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006462  nop
0x180006463  lea     rcx, [rsp+1E0h+var_170]
0x180006468  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000646d  mov     eax, r14d
0x180006470  jmp     loc_1800063D5
0x180006475  test    rsi, rsi
0x180006478  jz      short loc_18000648A
0x18000647a  mov     rax, [rsi]
0x18000647d  mov     rcx, rsi
0x180006480  mov     rax, [rax+10h]
0x180006484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006489  nop
0x18000648a  jmp     short loc_180006447
0x18000648c  mov     edx, 0B2h; void *
0x180006491  lea     rdi, [rsp+1E0h+pv]
0x180006496  mov     r9d, eax; char *
0x180006499  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800064a0  mov     rcx, [rbp+0E8h]; this
0x1800064a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064ac  mov     rcx, rdi
0x1800064af  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800064b4  jmp     loc_1800063B7
```

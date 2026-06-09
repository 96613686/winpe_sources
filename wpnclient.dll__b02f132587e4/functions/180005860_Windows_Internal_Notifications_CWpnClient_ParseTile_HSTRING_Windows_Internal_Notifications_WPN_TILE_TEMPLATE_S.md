# Windows::Internal::Notifications::CWpnClient::ParseTile(HSTRING__ *,Windows::Internal::Notifications::WPN_TILE_TEMPLATE_SIZE,uint,uchar *,Windows::Internal::Notifications::INotificationValueSet * *)

- ea: `0x180005860`
- end: `0x1800059ed`
- name: `?ParseTile@CWpnClient@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@W4WPN_TILE_TEMPLATE_SIZE@234@IPEAEPEAPEAUINotificationValueSet@234@@Z`
- size: `397`
- prototype: `int __high(HSTRING, enum Windows::Internal::Notifications::WPN_TILE_TEMPLATE_SIZE, unsigned int, unsigned __int8 *, struct Windows::Internal::Notifications::INotificationValueSet **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005860`
- `0x180005a00`
- `0x1800068f0`
- `0x1800070e8`
- `0x1800074d0`
- `0x180007504`
- `0x18001bf84`
- `0x180020350`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800058a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800058a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059be`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::Notifications::CWpnClient::ParseTile(
        __int64 a1,
        HSTRING a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        _QWORD *a6)
{
  const unsigned __int16 *StringRawBuffer; // rax
  Windows::Internal::Notifications::CWpnClient *v9; // rcx
  int PackageFullName; // eax
  unsigned int v11; // ebx
  Windows::Internal::Notifications::CNotificationValueSet *v12; // rax
  int v13; // edi
  void *v15; // rbx
  __int64 v16; // r8
  void *v17; // rsi
  int v18; // [rsp+20h] [rbp-68h]
  __int64 v19; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pv[10]; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *a6 = 0;
  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  PackageFullName = Windows::Internal::Notifications::CWpnClient::QueryPackageFullName(
                      v9,
                      StringRawBuffer,
                      (unsigned __int16 **)pv);
  v11 = PackageFullName;
  if ( PackageFullName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
      (const char *)(unsigned int)PackageFullName,
      v18);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    return v11;
  }
  else
  {
    *a6 = 0;
    v12 = (Windows::Internal::Notifications::CNotificationValueSet *)operator new(
                                                                       0xC8u,
                                                                       (const struct std::nothrow_t *)std::nothrow);
    if ( !v12 )
    {
      v13 = -2147024882;
      goto LABEL_4;
    }
    v15 = (void *)Windows::Internal::Notifications::CNotificationValueSet::CNotificationValueSet(v12);
    pv[3] = v15;
    v19 = 0;
    v18 = a4;
    v16 = a3;
    v17 = pv[0];
    v13 = Windows::Internal::Notifications::CNotificationValueSet::RuntimeClassInitialize(v15, pv[0], v16, a5);
    if ( v13 < 0 )
    {
      if ( v15 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
      Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>::~MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>(&v19);
      goto LABEL_4;
    }
    v13 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))v15)(
            v15,
            &GUID_07978036_2587_417d_85d1_6fa18e9c67e1,
            a6);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v13 < 0 )
    {
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
        (const char *)(unsigned int)v13,
        v18);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
      return (unsigned int)v13;
    }
    if ( v17 )
      CoTaskMemFree(v17);
    return 0;
  }
}

```

## disassembly

```asm
0x180005860  push    rbx
0x180005862  push    rbp
0x180005863  push    rsi
0x180005864  push    rdi
0x180005865  push    r14
0x180005867  sub     rsp, 60h
0x18000586b  mov     edi, r9d
0x18000586e  mov     esi, r8d
0x180005871  mov     rax, rdx
0x180005874  mov     rbp, [rsp+88h+arg_20]
0x18000587c  mov     r14, [rsp+88h+arg_28]
0x180005884  mov     qword ptr [r14], 0
0x18000588b  mov     [rsp+88h+pv], 0
0x180005894  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180005898  mov     [rsp+88h+var_48], rcx
0x18000589d  mov     [rsp+88h+var_40], rcx
0x1800058a2  xor     edx, edx; length
0x1800058a4  mov     rcx, rax; string
0x1800058a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800058ad  lea     r8, [rsp+88h+pv]; unsigned __int16 **
0x1800058b2  mov     rdx, rax; unsigned __int16 *
0x1800058b5  call    ?QueryPackageFullName@CWpnClient@Notifications@Internal@Windows@@AEAAJPEBGPEAPEAG@Z; Windows::Internal::Notifications::CWpnClient::QueryPackageFullName(ushort const *,ushort * *)
0x1800058ba  mov     ebx, eax
0x1800058bc  test    eax, eax
0x1800058be  js      loc_180005997
0x1800058c4  mov     qword ptr [r14], 0
0x1800058cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800058d2  mov     ecx, 0C8h; unsigned __int64
0x1800058d7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800058dc  test    rax, rax
0x1800058df  jnz     short loc_180005911
0x1800058e1  mov     edi, 8007000Eh
0x1800058e6  mov     rcx, [rsp+88h]; this
0x1800058ee  mov     r9d, edi; char *
0x1800058f1  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800058f8  mov     edx, 29h ; ')'; void *
0x1800058fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005902  nop
0x180005903  lea     rcx, [rsp+88h+pv]
0x180005908  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000590d  mov     eax, edi
0x18000590f  jmp     short loc_18000598C
0x180005911  mov     rcx, rax; this
0x180005914  call    ??0CNotificationValueSet@Notifications@Internal@Windows@@QEAA@XZ; Windows::Internal::Notifications::CNotificationValueSet::CNotificationValueSet(void)
0x180005919  mov     rbx, rax
0x18000591c  mov     [rsp+88h+var_38], rax
0x180005921  mov     [rsp+88h+var_58], 0
0x18000592a  mov     [rsp+88h+var_68], edi
0x18000592e  mov     r9, rbp
0x180005931  mov     r8d, esi
0x180005934  mov     rsi, [rsp+88h+pv]
0x180005939  mov     rdx, rsi
0x18000593c  mov     rcx, rax
0x18000593f  call    ?RuntimeClassInitialize@CNotificationValueSet@Notifications@Internal@Windows@@QEAAJPEBGW4WPN_TILE_TEMPLATE_SIZE@234@PEAEK@Z; Windows::Internal::Notifications::CNotificationValueSet::RuntimeClassInitialize(ushort const *,Windows::Internal::Notifications::WPN_TILE_TEMPLATE_SIZE,uchar *,ulong)
0x180005944  mov     edi, eax
0x180005946  test    eax, eax
0x180005948  js      short loc_1800059C8
0x18000594a  mov     rax, [rbx]
0x18000594d  mov     r8, r14
0x180005950  lea     rdx, _GUID_07978036_2587_417d_85d1_6fa18e9c67e1
0x180005957  mov     rcx, rbx
0x18000595a  mov     rax, [rax]
0x18000595d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005962  mov     edi, eax
0x180005964  mov     rax, [rbx]
0x180005967  mov     rcx, rbx
0x18000596a  mov     rax, [rax+10h]
0x18000596e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005973  nop
0x180005974  test    edi, edi
0x180005976  js      loc_1800058E6
0x18000597c  test    rsi, rsi
0x18000597f  jz      short loc_18000598A
0x180005981  mov     rcx, rsi; pv
0x180005984  call    cs:__imp_CoTaskMemFree
0x18000598a  xor     eax, eax
0x18000598c  add     rsp, 60h
0x180005990  pop     r14
0x180005992  pop     rdi
0x180005993  pop     rsi
0x180005994  pop     rbp
0x180005995  pop     rbx
0x180005996  retn
0x180005997  mov     rcx, [rsp+88h]; this
0x18000599f  mov     r9d, ebx; char *
0x1800059a2  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800059a9  mov     edx, 22h ; '"'; void *
0x1800059ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800059b3  nop
0x1800059b4  mov     rcx, [rsp+88h+pv]; pv
0x1800059b9  test    rcx, rcx
0x1800059bc  jz      short loc_1800059C4
0x1800059be  call    cs:__imp_CoTaskMemFree
0x1800059c4  mov     eax, ebx
0x1800059c6  jmp     short loc_18000598C
0x1800059c8  test    rbx, rbx
0x1800059cb  jz      short loc_1800059DD
0x1800059cd  mov     rax, [rbx]
0x1800059d0  mov     rcx, rbx
0x1800059d3  mov     rax, [rax+10h]
0x1800059d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059dc  nop
0x1800059dd  lea     rcx, [rsp+88h+var_58]
0x1800059e2  call    ??1?$MakeAllocator@VCToastActivator_AppLaunch@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>::~MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>(void)
0x1800059e7  jmp     loc_1800058E6
```

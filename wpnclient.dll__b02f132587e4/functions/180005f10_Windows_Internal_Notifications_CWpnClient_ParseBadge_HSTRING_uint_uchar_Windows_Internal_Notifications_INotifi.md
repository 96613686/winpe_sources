# Windows::Internal::Notifications::CWpnClient::ParseBadge(HSTRING__ *,uint,uchar *,Windows::Internal::Notifications::INotificationValueSet * *)

- ea: `0x180005f10`
- end: `0x1800061e7`
- name: `?ParseBadge@CWpnClient@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@IPEAEPEAPEAUINotificationValueSet@234@@Z`
- size: `727`
- prototype: `int(Windows::Internal::Notifications::CWpnClient *__hidden this, HSTRING, unsigned int, unsigned __int8 *, struct Windows::Internal::Notifications::INotificationValueSet **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005f10`
- `0x1800064c0`
- `0x180006800`
- `0x1800068f0`
- `0x1800070e8`
- `0x1800074d0`
- `0x18001ff00`
- `0x180020350`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006143`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006143`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180005fc7`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180005fc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::Notifications::CWpnClient::ParseBadge(
        Windows::Internal::Notifications::CWpnClient *this,
        HSTRING a2,
        __int64 a3,
        unsigned __int8 *a4,
        struct Windows::Internal::Notifications::INotificationValueSet **a5)
{
  int v5; // r15d
  const WCHAR *StringRawBuffer; // rbx
  LONG PackagesByPackageFamily; // eax
  bool v8; // zf
  int v9; // eax
  unsigned int v10; // ebx
  void *v11; // rdi
  Windows::Internal::Notifications::CNotificationValueSet *v12; // rax
  WCHAR *v13; // rbx
  int v14; // esi
  __int64 v16; // rdx
  int bufferLength; // [rsp+20h] [rbp-E0h]
  int bufferLengtha; // [rsp+20h] [rbp-E0h]
  UINT32 count; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR packageFullNames; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv[3]; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+80h] [rbp-80h]
  WCHAR buffer[128]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v5 = (int)a4;
  *a5 = 0;
  v24 = -1;
  v25 = -1;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v23 = 0;
  memset(pv, 0, sizeof(pv));
  packageFullNames = 0;
  v21[0] = 128;
  count = 1;
  PackagesByPackageFamily = FindPackagesByPackageFamily(
                              StringRawBuffer,
                              0x10u,
                              &count,
                              &packageFullNames,
                              v21,
                              buffer,
                              0);
  v8 = PackagesByPackageFamily == 0;
  if ( PackagesByPackageFamily > 0 )
    v8 = 0;
  if ( v8 && count )
  {
    if ( count != 1 )
    {
      v10 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
        (const char *)0x8000FFFFLL,
        bufferLength);
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
        (const char *)v10,
        bufferLengtha);
      return v10;
    }
    if ( packageFullNames )
    {
      if ( *packageFullNames )
      {
        v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
               (__int64)pv,
               (unsigned __int64)packageFullNames,
               0xFFFFFFFFFFFFFFFFuLL);
        v10 = v9;
        if ( v9 < 0 )
        {
          v16 = 172;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
            (const char *)(unsigned int)v9,
            bufferLength);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
          goto LABEL_22;
        }
      }
    }
  }
  else
  {
    v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           (__int64)pv,
           (unsigned __int64)StringRawBuffer,
           0xFFFFFFFFFFFFFFFFuLL);
    v10 = v9;
    if ( v9 < 0 )
    {
      v16 = 178;
      goto LABEL_27;
    }
  }
  v11 = pv[0];
  v23 = pv[0];
  *a5 = 0;
  v12 = (Windows::Internal::Notifications::CNotificationValueSet *)operator new(
                                                                     0xC8u,
                                                                     (const struct std::nothrow_t *)std::nothrow);
  if ( v12 )
  {
    v13 = (WCHAR *)Windows::Internal::Notifications::CNotificationValueSet::CNotificationValueSet(v12);
    packageFullNames = v13;
    *(_QWORD *)v21 = 0;
    bufferLength = v5;
    v14 = Windows::Internal::Notifications::CNotificationValueSet::RuntimeClassInitialize(v13, v11, 0x10000000, 2);
    if ( v14 < 0 )
    {
      if ( v13 )
        (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    else
    {
      v14 = (**(__int64 (__fastcall ***)(WCHAR *, GUID *, struct Windows::Internal::Notifications::INotificationValueSet **))v13)(
              v13,
              &GUID_07978036_2587_417d_85d1_6fa18e9c67e1,
              a5);
      (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v13 + 16LL))(v13);
      if ( v14 >= 0 )
      {
        if ( v11 )
          CoTaskMemFree(v11);
        return 0;
      }
    }
  }
  else
  {
    v14 = -2147024882;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8D,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
    (const char *)(unsigned int)v14,
    bufferLength);
  if ( v11 )
    CoTaskMemFree(v11);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180005f10  mov     [rsp-8+arg_0], rbx
0x180005f15  mov     [rsp-8+arg_8], rsi
0x180005f1a  push    rbp
0x180005f1b  push    rdi
0x180005f1c  push    r12
0x180005f1e  push    r14
0x180005f20  push    r15
0x180005f22  lea     rbp, [rsp-0A0h]
0x180005f2a  sub     rsp, 1A0h
0x180005f31  mov     rax, cs:__security_cookie
0x180005f38  xor     rax, rsp
0x180005f3b  mov     [rbp+0C0h+var_30], rax
0x180005f42  mov     r15, r9
0x180005f45  mov     esi, r8d
0x180005f48  mov     rcx, rdx; string
0x180005f4b  mov     r14, [rbp+0C0h+arg_20]
0x180005f52  xor     r12d, r12d
0x180005f55  mov     [r14], r12
0x180005f58  mov     [rsp+1C0h+var_148], 0FFFFFFFFFFFFFFFFh
0x180005f61  mov     [rbp+0C0h+var_140], 0FFFFFFFFFFFFFFFFh
0x180005f69  xor     edx, edx; length
0x180005f6b  call    cs:__imp_WindowsGetStringRawBuffer
0x180005f71  mov     rbx, rax
0x180005f74  mov     [rsp+1C0h+var_150], r12
0x180005f79  mov     [rsp+1C0h+pv], r12
0x180005f7e  mov     [rsp+1C0h+var_160], r12
0x180005f83  mov     [rsp+1C0h+var_158], r12
0x180005f88  mov     [rsp+1C0h+packageFullNames], r12
0x180005f8d  mov     [rsp+1C0h+var_170], 80h
0x180005f95  mov     [rsp+1C0h+count], 1
0x180005f9d  mov     [rsp+1C0h+packageProperties], r12; packageProperties
0x180005fa2  lea     rax, [rbp+0C0h+var_130]
0x180005fa6  mov     [rsp+1C0h+buffer], rax; buffer
0x180005fab  lea     rax, [rsp+1C0h+var_170]
0x180005fb0  mov     [rsp+1C0h+bufferLength], rax; int
0x180005fb5  lea     r9, [rsp+1C0h+packageFullNames]; packageFullNames
0x180005fba  lea     r8, [rsp+1C0h+count]; count
0x180005fbf  mov     edx, 10h; packageFilters
0x180005fc4  mov     rcx, rbx; packageFamilyName
0x180005fc7  call    cs:__imp_FindPackagesByPackageFamily
0x180005fcd  test    eax, eax
0x180005fcf  jg      loc_180006193
0x180005fd5  jz      loc_1800060CC
0x180005fdb  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180005fe2  mov     rdx, rbx
0x180005fe5  lea     rcx, [rsp+1C0h+pv]
0x180005fea  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180005fef  mov     ebx, eax
0x180005ff1  test    eax, eax
0x180005ff3  js      loc_1800061BC
0x180005ff9  mov     rdi, [rsp+1C0h+pv]
0x180005ffe  mov     [rsp+1C0h+var_150], rdi
0x180006003  mov     [r14], r12
0x180006006  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000600d  mov     ecx, 0C8h; unsigned __int64
0x180006012  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006017  test    rax, rax
0x18000601a  jz      loc_18000611A
0x180006020  mov     rcx, rax; this
0x180006023  call    ??0CNotificationValueSet@Notifications@Internal@Windows@@QEAA@XZ; Windows::Internal::Notifications::CNotificationValueSet::CNotificationValueSet(void)
0x180006028  mov     rbx, rax
0x18000602b  mov     [rsp+1C0h+packageFullNames], rax
0x180006030  mov     qword ptr [rsp+1C0h+var_170], r12
0x180006035  mov     dword ptr [rsp+1C0h+buffer], esi
0x180006039  mov     [rsp+1C0h+bufferLength], r15
0x18000603e  mov     r9d, 2
0x180006044  mov     r8d, 10000000h
0x18000604a  mov     rdx, rdi
0x18000604d  mov     rcx, rax
0x180006050  call    ?RuntimeClassInitialize@CNotificationValueSet@Notifications@Internal@Windows@@QEAAJPEBGW4WPN_APP_TYPE@@W4WPN_NOTIFICATION_TYPE@234@PEAEK@Z; Windows::Internal::Notifications::CNotificationValueSet::RuntimeClassInitialize(ushort const *,WPN_APP_TYPE,Windows::Internal::Notifications::WPN_NOTIFICATION_TYPE,uchar *,ulong)
0x180006055  mov     esi, eax
0x180006057  test    eax, eax
0x180006059  js      loc_1800061A2
0x18000605f  mov     rax, [rbx]
0x180006062  mov     r8, r14
0x180006065  lea     rdx, _GUID_07978036_2587_417d_85d1_6fa18e9c67e1
0x18000606c  mov     rcx, rbx
0x18000606f  mov     rax, [rax]
0x180006072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006077  mov     esi, eax
0x180006079  mov     rax, [rbx]
0x18000607c  mov     rcx, rbx
0x18000607f  mov     rax, [rax+10h]
0x180006083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006088  nop
0x180006089  test    esi, esi
0x18000608b  js      loc_18000611F
0x180006091  test    rdi, rdi
0x180006094  jz      short loc_18000609F
0x180006096  mov     rcx, rdi; pv
0x180006099  call    cs:__imp_CoTaskMemFree
0x18000609f  xor     eax, eax
0x1800060a1  mov     rcx, [rbp+0C0h+var_30]
0x1800060a8  xor     rcx, rsp; StackCookie
0x1800060ab  call    __security_check_cookie
0x1800060b0  lea     r11, [rsp+1C0h+var_20]
0x1800060b8  mov     rbx, [r11+30h]
0x1800060bc  mov     rsi, [r11+38h]
0x1800060c0  mov     rsp, r11
0x1800060c3  pop     r15
0x1800060c5  pop     r14
0x1800060c7  pop     r12
0x1800060c9  pop     rdi
0x1800060ca  pop     rbp
0x1800060cb  retn
0x1800060cc  mov     eax, [rsp+1C0h+count]
0x1800060d0  test    eax, eax
0x1800060d2  jz      loc_180005FDB
0x1800060d8  cmp     eax, 1
0x1800060db  jnz     short loc_180006150
0x1800060dd  mov     rdx, [rsp+1C0h+packageFullNames]
0x1800060e2  test    rdx, rdx
0x1800060e5  jz      loc_180005FF9
0x1800060eb  cmp     word ptr [rdx], 0
0x1800060ef  jz      loc_180005FF9
0x1800060f5  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800060fc  lea     rcx, [rsp+1C0h+pv]
0x180006101  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180006106  mov     ebx, eax
0x180006108  test    eax, eax
0x18000610a  jns     loc_180005FF9
0x180006110  mov     edx, 0ACh
0x180006115  jmp     loc_1800061C1
0x18000611a  mov     esi, 8007000Eh
0x18000611f  mov     rcx, [rbp+0C8h]; this
0x180006126  mov     r9d, esi; char *
0x180006129  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006130  mov     edx, 8Dh; void *
0x180006135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000613a  nop
0x18000613b  test    rdi, rdi
0x18000613e  jz      short loc_180006149
0x180006140  mov     rcx, rdi; pv
0x180006143  call    cs:__imp_CoTaskMemFree
0x180006149  mov     eax, esi
0x18000614b  jmp     loc_1800060A1
0x180006150  mov     rcx, [rbp+0C8h]; this
0x180006157  mov     ebx, 8000FFFFh
0x18000615c  mov     r9d, ebx; char *
0x18000615f  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006166  mov     edx, 0A8h; void *
0x18000616b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006170  mov     rcx, [rbp+0C8h]; this
0x180006177  mov     r9d, ebx; char *
0x18000617a  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006181  mov     edx, 82h; void *
0x180006186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000618b  nop
0x18000618c  mov     eax, ebx
0x18000618e  jmp     loc_1800060A1
0x180006193  movzx   eax, ax
0x180006196  or      eax, 80070000h
0x18000619b  test    eax, eax
0x18000619d  jmp     loc_180005FD5
0x1800061a2  test    rbx, rbx
0x1800061a5  jz      short loc_1800061B7
0x1800061a7  mov     rax, [rbx]
0x1800061aa  mov     rcx, rbx
0x1800061ad  mov     rax, [rax+10h]
0x1800061b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061b6  nop
0x1800061b7  jmp     loc_18000611F
0x1800061bc  mov     edx, 0B2h; void *
0x1800061c1  lea     rdi, [rsp+1C0h+pv]
0x1800061c6  mov     r9d, eax; char *
0x1800061c9  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800061d0  mov     rcx, [rbp+0C8h]; this
0x1800061d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061dc  mov     rcx, rdi
0x1800061df  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800061e4  jmp     short loc_180006170
```

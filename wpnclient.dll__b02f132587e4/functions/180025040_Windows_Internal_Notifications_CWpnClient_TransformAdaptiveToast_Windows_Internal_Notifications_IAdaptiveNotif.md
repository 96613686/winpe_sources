# Windows::Internal::Notifications::CWpnClient::TransformAdaptiveToast(Windows::Internal::Notifications::IAdaptiveNotification *,Windows::Internal::Notifications::INotificationValueSet * *)

- ea: `0x180025040`
- end: `0x18002516d`
- name: `?TransformAdaptiveToast@CWpnClient@Notifications@Internal@Windows@@UEAAJPEAUIAdaptiveNotification@234@PEAPEAUINotificationValueSet@234@@Z`
- size: `301`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CWpnClient *__hidden this, struct Windows::Internal::Notifications::IAdaptiveNotification *, struct Windows::Internal::Notifications::INotificationValueSet **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005a00`
- `0x1800070e8`
- `0x1800074d0`
- `0x18001c080`
- `0x180025040`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800250e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800250e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025158`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Notifications::CWpnClient::TransformAdaptiveToast(
        Windows::Internal::Notifications::CWpnClient *this,
        struct Windows::Internal::Notifications::IAdaptiveNotification *a2,
        struct Windows::Internal::Notifications::INotificationValueSet **a3)
{
  __int64 (__fastcall *v5)(struct Windows::Internal::Notifications::IAdaptiveNotification *, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  const unsigned __int16 *StringRawBuffer; // rax
  Windows::Internal::Notifications::CWpnClient *v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  unsigned __int16 *v13; // [rsp+20h] [rbp-20h] BYREF
  __int64 v14; // [rsp+28h] [rbp-18h]
  __int64 v15; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  struct Windows::Internal::Notifications::IAdaptiveNotification *v17; // [rsp+68h] [rbp+28h] BYREF
  int v18; // [rsp+70h] [rbp+30h] BYREF
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF

  v17 = a2;
  *a3 = 0;
  string = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Internal::Notifications::IAdaptiveNotification *, HSTRING *))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(a2, &string);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v13 = 0;
    v14 = 0;
    v15 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v13);
    v14 = -1;
    v15 = -1;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v10 = Windows::Internal::Notifications::CWpnClient::QueryPackageFullName(v9, StringRawBuffer, &v13);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v18 = 3;
      v10 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Notifications::CNotificationValueSet,Windows::Internal::Notifications::INotificationValueSet,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &,enum Windows::Internal::Notifications::WPN_NOTIFICATION_TYPE,Windows::Internal::Notifications::IAdaptiveNotification * &>(
              a3,
              &v13,
              &v18,
              &v17);
      v7 = v10;
      if ( v10 >= 0 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v13);
        v7 = 0;
        goto LABEL_9;
      }
      v11 = 114;
    }
    else
    {
      v11 = 108;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
      (const char *)(unsigned int)v10,
      (int)v13);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v13);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
      (const char *)(unsigned int)v6,
      (int)v13);
  }
LABEL_9:
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x180025040  mov     [rsp-18h+arg_0], rbx
0x180025045  mov     [rsp-18h+arg_8], rdx
0x18002504a  push    rbp
0x18002504b  push    rsi
0x18002504c  push    rdi
0x18002504d  mov     rbp, rsp
0x180025050  sub     rsp, 40h
0x180025054  mov     rsi, r8
0x180025057  mov     rdi, rdx
0x18002505a  mov     qword ptr [r8], 0
0x180025061  mov     [rbp+string], 0
0x180025069  mov     rax, [rdx]
0x18002506c  mov     rbx, [rax+38h]
0x180025070  xor     ecx, ecx; string
0x180025072  call    cs:__imp_WindowsDeleteString
0x180025078  mov     [rbp+string], 0
0x180025080  lea     rdx, [rbp+string]
0x180025084  mov     rcx, rdi
0x180025087  mov     rax, rbx
0x18002508a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002508f  mov     ebx, eax
0x180025091  test    eax, eax
0x180025093  jns     short loc_1800250B2
0x180025095  mov     rcx, [rbp+18h]; this
0x180025099  mov     r9d, eax; char *
0x18002509c  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800250a3  mov     edx, 68h ; 'h'; void *
0x1800250a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800250ad  jmp     loc_180025154
0x1800250b2  mov     [rbp+var_20], 0
0x1800250ba  mov     [rbp+var_18], 0
0x1800250c2  mov     [rbp+var_10], 0
0x1800250ca  lea     rcx, [rbp+var_20]
0x1800250ce  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800250d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800250d7  mov     [rbp+var_18], rax
0x1800250db  mov     [rbp+var_10], rax
0x1800250df  xor     edx, edx; length
0x1800250e1  mov     rcx, [rbp+string]; string
0x1800250e5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800250eb  lea     r8, [rbp+var_20]; unsigned __int16 **
0x1800250ef  mov     rdx, rax; unsigned __int16 *
0x1800250f2  call    ?QueryPackageFullName@CWpnClient@Notifications@Internal@Windows@@AEAAJPEBGPEAPEAG@Z; Windows::Internal::Notifications::CWpnClient::QueryPackageFullName(ushort const *,ushort * *)
0x1800250f7  mov     ebx, eax
0x1800250f9  test    eax, eax
0x1800250fb  jns     short loc_180025121
0x1800250fd  mov     edx, 6Ch ; 'l'; void *
0x180025102  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180025109  mov     r9d, eax; char *
0x18002510c  mov     rcx, [rbp+18h]; this
0x180025110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025115  nop
0x180025116  lea     rcx, [rbp+var_20]
0x18002511a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002511f  jmp     short loc_180025154
0x180025121  mov     [rbp+arg_10], 3
0x180025128  lea     r9, [rbp+arg_8]
0x18002512c  lea     r8, [rbp+arg_10]
0x180025130  lea     rdx, [rbp+var_20]
0x180025134  mov     rcx, rsi
0x180025137  call    ??$MakeAndInitialize@VCNotificationValueSet@Notifications@Internal@Windows@@UINotificationValueSet@234@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@34@W4WPN_NOTIFICATION_TYPE@234@AEAPEAUIAdaptiveNotification@234@@Details@WRL@Microsoft@@YAJPEAPEAUINotificationValueSet@Notifications@Internal@Windows@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@56@$$QEAW4WPN_NOTIFICATION_TYPE@456@AEAPEAUIAdaptiveNotification@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Notifications::CNotificationValueSet,Windows::Internal::Notifications::INotificationValueSet,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::Notifications::WPN_NOTIFICATION_TYPE,Windows::Internal::Notifications::IAdaptiveNotification * &>(Windows::Internal::Notifications::INotificationValueSet * *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::Notifications::WPN_NOTIFICATION_TYPE &&,Windows::Internal::Notifications::IAdaptiveNotification * &)
0x18002513c  mov     ebx, eax
0x18002513e  test    eax, eax
0x180025140  jns     short loc_180025149
0x180025142  mov     edx, 72h ; 'r'
0x180025147  jmp     short loc_180025102
0x180025149  lea     rcx, [rbp+var_20]
0x18002514d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025152  xor     ebx, ebx
0x180025154  mov     rcx, [rbp+string]; string
0x180025158  call    cs:__imp_WindowsDeleteString
0x18002515e  mov     eax, ebx
0x180025160  mov     rbx, [rsp+40h+arg_0]
0x180025165  add     rsp, 40h
0x180025169  pop     rdi
0x18002516a  pop     rsi
0x18002516b  pop     rbp
0x18002516c  retn
```

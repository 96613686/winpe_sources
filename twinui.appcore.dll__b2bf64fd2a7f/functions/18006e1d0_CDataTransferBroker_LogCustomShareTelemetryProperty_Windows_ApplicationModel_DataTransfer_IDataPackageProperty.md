# CDataTransferBroker::_LogCustomShareTelemetryProperty(Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet *)

- ea: `0x18006e1d0`
- end: `0x18006e427`
- name: `?_LogCustomShareTelemetryProperty@CDataTransferBroker@@AEAAJPEAUIDataPackagePropertySet@DataTransfer@ApplicationModel@Windows@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(CDataTransferBroker *__hidden this, struct Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006d978`

## callees

- `0x180003d24`
- `0x180018dd4`
- `0x18001cc38`
- `0x18002b1b0`
- `0x180060b5c`
- `0x180060d08`
- `0x18006723c`
- `0x18006e1d0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e2a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e35a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e3e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e2a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e35a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e3e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDataTransferBroker::_LogCustomShareTelemetryProperty(
        CDataTransferBroker *this,
        __int64 (__fastcall ***a2)(struct Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet *, GUID *, __int64 **))
{
  __int64 (__fastcall *v4)(struct Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet *, GUID *, __int64 **); // rbx
  int v5; // eax
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rax
  int v9; // r14d
  __int64 *v10; // rsi
  bool v11; // r8
  bool v12; // r9
  __int64 v13; // rbx
  int v14; // edi
  __int64 v15; // rcx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-39h] BYREF
  HSTRING string; // [rsp+28h] [rbp-31h] BYREF
  __int64 *v20; // [rsp+30h] [rbp-29h] BYREF
  __int64 v21; // [rsp+38h] [rbp-21h] BYREF
  int v22; // [rsp+40h] [rbp-19h]
  __int64 v23; // [rsp+48h] [rbp-11h] BYREF
  char *v24; // [rsp+50h] [rbp-9h]
  __int64 *v25; // [rsp+58h] [rbp-1h]
  struct IInspectable *v26; // [rsp+60h] [rbp+7h] BYREF
  __int128 v27; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v20 = 0;
  v4 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v5 = v4(
         (struct Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet *)a2,
         &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
         &v20);
  v6 = v5;
  if ( v5 >= 0 )
  {
    string = 0;
    Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((Microsoft::WRL::Wrappers::HString *)&string);
    LOBYTE(v18) = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, int *))(*v20 + 64))(v20, string, &v18);
    v6 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C2,
        (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
        (const char *)(unsigned int)v7,
        v18);
LABEL_5:
      WindowsDeleteString(string);
LABEL_17:
      string = 0;
      goto LABEL_18;
    }
    if ( (_BYTE)v18 )
    {
      v23 = 0;
      LODWORD(v24) = 0;
      v8 = *v20;
      v25 = &v23;
      v26 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct IInspectable **))(v8 + 48))(v20, string, &v26);
      v10 = v25;
      RoVariant::RoVariant((RoVariant *)&v21, v26, v11, v12);
      v13 = v21;
      v21 = 0;
      v14 = v22;
      v22 = 0;
      RoVariant::~RoVariant((RoVariant *)&v21);
      v15 = *v10;
      *v10 = v13;
      v21 = v15;
      v16 = *((_DWORD *)v10 + 2);
      *((_DWORD *)v10 + 2) = v14;
      v22 = v16;
      RoVariant::~RoVariant((RoVariant *)&v21);
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C6,
          (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
          (const char *)(unsigned int)v9,
          v18);
        RoVariant::~RoVariant((RoVariant *)&v23);
        WindowsDeleteString(string);
        v6 = v9;
        goto LABEL_17;
      }
      v27 = 0;
      if ( (_DWORD)v24 != 7 )
      {
        v6 = -2147316576;
        if ( (int)v24 < 0 )
          v6 = (int)v24;
        goto LABEL_14;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v23 + 160LL))(v23, &v27);
      if ( v6 < 0 )
      {
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C9,
          (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
          (const char *)(unsigned int)v6,
          v18);
        RoVariant::~RoVariant((RoVariant *)&v23);
        goto LABEL_5;
      }
      ModernShareTelemetry::ModernShareFlow::ModernShareDataPackage<_GUID &>((char *)this + 536, &v27);
      RoVariant::~RoVariant((RoVariant *)&v23);
    }
    WindowsDeleteString(string);
    v6 = 0;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2BD,
    (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
    (const char *)(unsigned int)v5,
    v18);
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006e1d0  mov     [rsp-8+arg_10], rbx
0x18006e1d5  mov     [rsp-8+arg_18], rsi
0x18006e1da  push    rbp
0x18006e1db  push    rdi
0x18006e1dc  push    r12
0x18006e1de  push    r14
0x18006e1e0  push    r15
0x18006e1e2  lea     rbp, [rsp-37h]
0x18006e1e7  sub     rsp, 90h
0x18006e1ee  mov     rax, cs:__security_cookie
0x18006e1f5  xor     rax, rsp
0x18006e1f8  mov     [rbp+57h+var_30], rax
0x18006e1fc  mov     rdi, rdx
0x18006e1ff  mov     r15, rcx
0x18006e202  xor     r12d, r12d
0x18006e205  mov     [rbp+57h+var_80], r12
0x18006e209  mov     rax, [rdx]
0x18006e20c  mov     rbx, [rax]
0x18006e20f  lea     rcx, [rbp+57h+var_80]
0x18006e213  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e218  lea     r8, [rbp+57h+var_80]
0x18006e21c  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18006e223  mov     rcx, rdi
0x18006e226  mov     rax, rbx
0x18006e229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e22e  mov     ebx, eax
0x18006e230  test    eax, eax
0x18006e232  jns     short loc_18006E251
0x18006e234  mov     rcx, [rbp+5Fh]; this
0x18006e238  mov     r9d, eax; char *
0x18006e23b  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x18006e242  mov     edx, 2BDh; void *
0x18006e247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e24c  jmp     loc_18006E3F4
0x18006e251  mov     [rbp+57h+string], r12
0x18006e255  lea     rdx, off_18008FBE0; "shareTelemetrySessionId"
0x18006e25c  lea     rcx, [rbp+57h+string]; this
0x18006e260  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18006e265  mov     byte ptr [rbp+57h+var_90], r12b
0x18006e269  mov     rcx, [rbp+57h+var_80]
0x18006e26d  mov     rax, [rcx]
0x18006e270  lea     r8, [rbp+57h+var_90]
0x18006e274  mov     rdx, [rbp+57h+string]
0x18006e278  mov     rax, [rax+40h]
0x18006e27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e281  mov     ebx, eax
0x18006e283  test    eax, eax
0x18006e285  jns     short loc_18006E2AF
0x18006e287  mov     rcx, [rbp+5Fh]; this
0x18006e28b  mov     r9d, eax; char *
0x18006e28e  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x18006e295  mov     edx, 2C2h; void *
0x18006e29a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e29f  nop
0x18006e2a0  mov     rcx, [rbp+57h+string]; string
0x18006e2a4  call    cs:__imp_WindowsDeleteString
0x18006e2aa  jmp     loc_18006E3F0
0x18006e2af  cmp     byte ptr [rbp+57h+var_90], r12b
0x18006e2b3  jz      loc_18006E3E3
0x18006e2b9  mov     [rbp+57h+var_68], r12
0x18006e2bd  mov     dword ptr [rbp+57h+var_60], r12d
0x18006e2c1  mov     rcx, [rbp+57h+var_80]
0x18006e2c5  mov     rax, [rcx]
0x18006e2c8  lea     rdx, [rbp+57h+var_68]
0x18006e2cc  mov     [rbp+57h+var_58], rdx
0x18006e2d0  mov     [rbp+57h+var_50], r12
0x18006e2d4  lea     r8, [rbp+57h+var_50]
0x18006e2d8  mov     rdx, [rbp+57h+string]
0x18006e2dc  mov     rax, [rax+30h]
0x18006e2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2e5  mov     r14d, eax
0x18006e2e8  mov     rsi, [rbp+57h+var_58]
0x18006e2ec  mov     rdx, [rbp+57h+var_50]; struct IInspectable *
0x18006e2f0  lea     rcx, [rbp+57h+var_78]; this
0x18006e2f4  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x18006e2f9  mov     rbx, [rbp+57h+var_78]
0x18006e2fd  mov     [rbp+57h+var_78], r12
0x18006e301  mov     edi, [rbp+57h+var_70]
0x18006e304  mov     [rbp+57h+var_70], r12d
0x18006e308  lea     rcx, [rbp+57h+var_78]; this
0x18006e30c  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18006e311  mov     rcx, [rsi]
0x18006e314  mov     [rsi], rbx
0x18006e317  mov     [rbp+57h+var_78], rcx
0x18006e31b  mov     eax, [rsi+8]
0x18006e31e  mov     [rsi+8], edi
0x18006e321  mov     [rbp+57h+var_70], eax
0x18006e324  lea     rcx, [rbp+57h+var_78]; this
0x18006e328  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18006e32d  nop
0x18006e32e  test    r14d, r14d
0x18006e331  jns     short loc_18006E368
0x18006e333  mov     rcx, [rbp+5Fh]; this
0x18006e337  mov     r9d, r14d; char *
0x18006e33a  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x18006e341  mov     edx, 2C6h; void *
0x18006e346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e34b  nop
0x18006e34c  lea     rcx, [rbp+57h+var_68]; this
0x18006e350  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18006e355  nop
0x18006e356  mov     rcx, [rbp+57h+string]; string
0x18006e35a  call    cs:__imp_WindowsDeleteString
0x18006e360  mov     ebx, r14d
0x18006e363  jmp     loc_18006E3F0
0x18006e368  mov     eax, dword ptr [rbp+57h+var_60]
0x18006e36b  xorps   xmm0, xmm0
0x18006e36e  movdqa  [rbp+57h+var_40], xmm0
0x18006e373  cmp     eax, 7
0x18006e376  jz      short loc_18006E384
0x18006e378  mov     ebx, 80028CA0h
0x18006e37d  test    eax, eax
0x18006e37f  cmovs   ebx, eax
0x18006e382  jmp     short loc_18006E3A1
0x18006e384  mov     rcx, [rbp+57h+var_68]
0x18006e388  mov     rax, [rcx]
0x18006e38b  lea     rdx, [rbp+57h+var_40]
0x18006e38f  mov     rax, [rax+0A0h]
0x18006e396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e39b  mov     ebx, eax
0x18006e39d  test    eax, eax
0x18006e39f  jns     short loc_18006E3C8
0x18006e3a1  mov     rcx, [rbp+5Fh]; this
0x18006e3a5  mov     r9d, ebx; char *
0x18006e3a8  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x18006e3af  mov     edx, 2C9h; void *
0x18006e3b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e3b9  nop
0x18006e3ba  lea     rcx, [rbp+57h+var_68]; this
0x18006e3be  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18006e3c3  jmp     loc_18006E2A0
0x18006e3c8  lea     rcx, [r15+218h]
0x18006e3cf  lea     rdx, [rbp+57h+var_40]
0x18006e3d3  call    ??$ModernShareDataPackage@AEAU_GUID@@@ModernShareFlow@ModernShareTelemetry@@QEAAXAEAU_GUID@@@Z; ModernShareTelemetry::ModernShareFlow::ModernShareDataPackage<_GUID &>(_GUID &)
0x18006e3d8  nop
0x18006e3d9  lea     rcx, [rbp+57h+var_68]; this
0x18006e3dd  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18006e3e2  nop
0x18006e3e3  mov     rcx, [rbp+57h+string]; string
0x18006e3e7  call    cs:__imp_WindowsDeleteString
0x18006e3ed  mov     ebx, r12d
0x18006e3f0  mov     [rbp+57h+string], r12
0x18006e3f4  lea     rcx, [rbp+57h+var_80]
0x18006e3f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e3fd  mov     eax, ebx
0x18006e3ff  mov     rcx, [rbp+57h+var_30]
0x18006e403  xor     rcx, rsp; StackCookie
0x18006e406  call    __security_check_cookie
0x18006e40b  lea     r11, [rsp+0B0h+var_20]
0x18006e413  mov     rbx, [r11+40h]
0x18006e417  mov     rsi, [r11+48h]
0x18006e41b  mov     rsp, r11
0x18006e41e  pop     r15
0x18006e420  pop     r14
0x18006e422  pop     r12
0x18006e424  pop     rdi
0x18006e425  pop     rbp
0x18006e426  retn
```

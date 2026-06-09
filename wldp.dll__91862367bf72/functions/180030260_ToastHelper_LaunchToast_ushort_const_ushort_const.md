# ToastHelper::LaunchToast(ushort const *,ushort const *)

- ea: `0x180030260`
- end: `0x1800303ca`
- name: `?LaunchToast@ToastHelper@@SAJPEBG0@Z`
- size: `362`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030b0c`
- `0x180030cb0`
- `0x180030e24`

## callees

- `0x18001f038`
- `0x18002fb7c`
- `0x180030260`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800302bb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800302bb`

## string_xrefs

- `0x180030313`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x18003037d`: `Windows.Defender.SecurityCenter`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ToastHelper::LaunchToast(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HRESULT Instance; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 (__fastcall *v5)(LPVOID, __int64 *); // rdi
  int ppv; // [rsp+20h] [rbp-69h]
  __int64 v8; // [rsp+98h] [rbp+Fh] BYREF
  LPVOID v9[3]; // [rsp+A0h] [rbp+17h] BYREF
  int v10; // [rsp+B8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v9[0] = 0;
  v8 = 0;
  Instance = CoCreateInstance(
               &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
               0,
               4u,
               &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
               v9);
  v3 = Instance;
  if ( Instance >= 0 )
  {
    v5 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v9[0] + 24LL);
    v8 = 0;
    Instance = v5(v9[0], &v8);
    v3 = Instance;
    if ( Instance >= 0 )
    {
      v9[2] = 0;
      v10 = 0;
      ppv = 1;
      Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v8 + 64LL))(
                   v8,
                   L"NonImmersivePackage",
                   L"Windows.Defender.SecurityCenter",
                   0);
      v3 = Instance;
      if ( Instance >= 0 )
      {
        v3 = 0;
        goto LABEL_9;
      }
      v4 = 298;
    }
    else
    {
      v4 = 279;
    }
  }
  else
  {
    v4 = 277;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_9:
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v8);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(v9);
  return v3;
}

```

## disassembly

```asm
0x180030260  push    rbp
0x180030262  push    rbx
0x180030263  push    rsi
0x180030264  push    rdi
0x180030265  push    r14
0x180030267  lea     rbp, [rsp-37h]
0x18003026c  sub     rsp, 0C0h
0x180030273  mov     rsi, rdx
0x180030276  xor     r14d, r14d
0x180030279  mov     [rbp+57h+var_40], r14
0x18003027d  mov     [rbp+57h+var_48], r14
0x180030281  mov     [rbp+57h+var_50], r14d
0x180030285  mov     rcx, [rbp+57h+var_40]
0x180030289  mov     [rbp+57h+var_40], r14
0x18003028d  test    rcx, rcx
0x180030290  jz      short loc_18003029E
0x180030292  mov     rax, [rcx]
0x180030295  mov     rax, [rax+10h]
0x180030299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003029e  lea     rax, [rbp+57h+var_40]
0x1800302a2  mov     [rsp+0E0h+ppv], rax; int
0x1800302a7  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x1800302ae  xor     edx, edx; pUnkOuter
0x1800302b0  lea     r8d, [rdx+4]; dwClsContext
0x1800302b4  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x1800302bb  call    cs:__imp_CoCreateInstance
0x1800302c1  mov     ebx, eax
0x1800302c3  test    eax, eax
0x1800302c5  jns     short loc_1800302CE
0x1800302c7  mov     edx, 115h
0x1800302cc  jmp     short loc_18003030C
0x1800302ce  mov     rbx, [rbp+57h+var_40]
0x1800302d2  mov     rax, [rbx]
0x1800302d5  mov     rdi, [rax+18h]
0x1800302d9  mov     rcx, [rbp+57h+var_48]
0x1800302dd  mov     [rbp+57h+var_48], r14
0x1800302e1  test    rcx, rcx
0x1800302e4  jz      short loc_1800302F2
0x1800302e6  mov     rdx, [rcx]
0x1800302e9  mov     rax, [rdx+10h]
0x1800302ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302f2  lea     rdx, [rbp+57h+var_48]
0x1800302f6  mov     rcx, rbx
0x1800302f9  mov     rax, rdi
0x1800302fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030301  mov     ebx, eax
0x180030303  test    eax, eax
0x180030305  jns     short loc_180030324
0x180030307  mov     edx, 117h; void *
0x18003030c  mov     rcx, [rbp+5Fh]; this
0x180030310  mov     r9d, eax; char *
0x180030313  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x18003031a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003031f  jmp     loc_1800303A7
0x180030324  mov     rcx, [rbp+57h+var_48]
0x180030328  mov     [rbp+57h+var_30], r14
0x18003032c  mov     [rbp+57h+var_28], r14d
0x180030330  mov     rax, [rcx]
0x180030333  lea     rdx, [rbp+57h+var_50]
0x180030337  mov     [rsp+0E0h+var_68], rdx
0x18003033c  mov     [rsp+0E0h+var_70], r14d
0x180030341  mov     [rsp+0E0h+var_78], r14
0x180030346  mov     [rsp+0E0h+var_80], r14
0x18003034b  mov     [rsp+0E0h+var_88], r14
0x180030350  mov     [rsp+0E0h+var_90], r14d
0x180030355  mov     [rsp+0E0h+var_98], r14d
0x18003035a  lea     rdx, [rbp+57h+var_30]
0x18003035e  mov     [rsp+0E0h+var_A0], rdx
0x180030363  mov     [rsp+0E0h+var_A8], r14
0x180030368  mov     [rsp+0E0h+var_B0], r14
0x18003036d  mov     [rsp+0E0h+var_B8], rsi
0x180030372  mov     dword ptr [rsp+0E0h+ppv], 1
0x18003037a  xor     r9d, r9d
0x18003037d  lea     r8, aWindowsDefende; "Windows.Defender.SecurityCenter"
0x180030384  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x18003038b  mov     rax, [rax+40h]
0x18003038f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030394  mov     ebx, eax
0x180030396  test    eax, eax
0x180030398  jns     short loc_1800303A4
0x18003039a  mov     edx, 12Ah
0x18003039f  jmp     loc_18003030C
0x1800303a4  mov     ebx, r14d
0x1800303a7  lea     rcx, [rbp+57h+var_48]
0x1800303ab  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x1800303b0  nop
0x1800303b1  lea     rcx, [rbp+57h+var_40]
0x1800303b5  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x1800303ba  mov     eax, ebx
0x1800303bc  add     rsp, 0C0h
0x1800303c3  pop     r14
0x1800303c5  pop     rdi
0x1800303c6  pop     rsi
0x1800303c7  pop     rbx
0x1800303c8  pop     rbp
0x1800303c9  retn
```

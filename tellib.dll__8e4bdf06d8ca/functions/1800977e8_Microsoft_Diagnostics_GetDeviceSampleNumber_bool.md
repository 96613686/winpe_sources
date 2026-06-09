# Microsoft::Diagnostics::GetDeviceSampleNumber(bool)

- ea: `0x1800977e8`
- end: `0x1800979e7`
- name: `?GetDeviceSampleNumber@Diagnostics@Microsoft@@YAN_N@Z`
- size: `511`
- prototype: `double __fastcall(Microsoft::Diagnostics *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009c9c0`

## callees

- `0x18005af1c`
- `0x1800977e8`
- `0x180098d5c`
- `0x1800b83bc`
- `0x1800bc2e0`

## import_xrefs

- `msvcp_win!?_Random_device@std@@YAIXZ` at `0x18009787a`
- `msvcp_win!?_Random_device@std@@YAIXZ` at `0x180097896`
- `msvcp_win!?_Random_device@std@@YAIXZ` at `0x18009787a`
- `msvcp_win!?_Random_device@std@@YAIXZ` at `0x180097896`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800978d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800978d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009792c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009792c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180097839`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180097839`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180097986`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180097986`

## string_xrefs

- `0x18009794f`: `onecore\base\telemetry\utc\service\include\samplingnumber.hpp`
- `0x1800979a9`: `onecore\base\telemetry\utc\service\include\samplingnumber.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
double __fastcall Microsoft::Diagnostics::GetDeviceSampleNumber(Microsoft::Diagnostics *this)
{
  LSTATUS ValueW; // eax
  signed int v2; // ecx
  int v3; // eax
  char v4; // dl
  __int64 v5; // rax
  HKEY v6; // rbx
  int v7; // eax
  int v8; // eax
  int pdwType; // [rsp+20h] [rbp-38h]
  int pdwTypea; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+10h]
  unsigned int Data; // [rsp+70h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+28h] BYREF
  char v16; // [rsp+88h] [rbp+30h] BYREF

  Data = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Reliability Analysis\\RAC",
             L"RacSampleNumber",
             0x18u,
             0,
             &Data,
             &pcbData);
  v2 = ValueW;
  if ( ValueW > 0 )
    v2 = (unsigned __int16)ValueW | 0x80070000;
  v3 = Data;
  if ( !Data || (v4 = 0, Data > 0x5F5E100) )
    v4 = 1;
  if ( v2 < 0 || v4 )
  {
    hKey = 0;
    v5 = 100000000LL * std::_Random_device();
    if ( (unsigned int)v5 <= 0x5A915FF )
    {
      do
        v5 = 100000000LL * std::_Random_device();
      while ( (unsigned int)v5 < 0x5A91600 );
    }
    Data = HIDWORD(v5) + 1;
    v6 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
      RegCloseKey(v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
    }
    hKey = 0;
    v7 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Reliability Analysis\\RAC",
           0,
           0,
           0,
           0x20006u,
           0,
           &hKey,
           0);
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\samplingnumber.hpp",
        (const char *)(unsigned int)v7,
        pdwType);
    v8 = RegSetValueExW(hKey, L"RacSampleNumber", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\samplingnumber.hpp",
        (const char *)(unsigned int)v8,
        pdwTypea);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v3 = Data;
  }
  return (double)v3 / 100000000.0 * 100.0;
}

```

## disassembly

```asm
0x1800977e8  mov     byte ptr [rsp-10h+Data], cl
0x1800977ec  push    rbp
0x1800977ed  push    rbx
0x1800977ee  mov     rbp, rsp
0x1800977f1  sub     rsp, 58h
0x1800977f5  mov     [rbp+Data], 0
0x1800977fc  mov     [rbp+arg_8], 4
0x180097803  lea     rax, [rbp+arg_8]
0x180097807  mov     [rsp+58h+pcbData], rax; pcbData
0x18009780c  lea     rax, [rbp+Data]
0x180097810  mov     [rsp+58h+pvData], rax; pvData
0x180097815  mov     [rsp+58h+pdwType], 0; pdwType
0x18009781e  mov     r9d, 18h; dwFlags
0x180097824  lea     r8, ValueName; "RacSampleNumber"
0x18009782b  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Reliability Analys"...
0x180097832  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180097839  call    cs:__imp_RegGetValueW
0x180097840  nop     dword ptr [rax+rax+00h]
0x180097845  mov     ecx, eax
0x180097847  test    eax, eax
0x180097849  jle     short loc_180097854
0x18009784b  movzx   ecx, ax
0x18009784e  or      ecx, 80070000h
0x180097854  mov     eax, [rbp+Data]
0x180097857  test    eax, eax
0x180097859  jz      short loc_180097864
0x18009785b  xor     dl, dl
0x18009785d  cmp     eax, 5F5E100h
0x180097862  jbe     short loc_180097866
0x180097864  mov     dl, 1
0x180097866  test    ecx, ecx
0x180097868  js      short loc_180097872
0x18009786a  test    dl, dl
0x18009786c  jz      loc_1800979C7
0x180097872  mov     [rbp+hKey], 0
0x18009787a  call    cs:__imp_?_Random_device@std@@YAIXZ; std::_Random_device(void)
0x180097881  nop     dword ptr [rax+rax+00h]
0x180097886  mov     ecx, eax
0x180097888  imul    rax, rcx, 5F5E100h
0x18009788f  cmp     eax, 5A915FFh
0x180097894  ja      short loc_1800978B2
0x180097896  call    cs:__imp_?_Random_device@std@@YAIXZ; std::_Random_device(void)
0x18009789d  nop     dword ptr [rax+rax+00h]
0x1800978a2  mov     ecx, eax
0x1800978a4  imul    rax, rcx, 5F5E100h
0x1800978ab  cmp     eax, 5A91600h
0x1800978b0  jb      short loc_180097896
0x1800978b2  shr     rax, 20h
0x1800978b6  inc     eax
0x1800978b8  mov     [rbp+Data], eax
0x1800978bb  mov     rbx, [rbp+hKey]
0x1800978bf  test    rbx, rbx
0x1800978c2  jz      short loc_1800978E5
0x1800978c4  lea     rcx, [rbp+arg_18]; this
0x1800978c8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800978cd  mov     rcx, rbx; hKey
0x1800978d0  call    cs:__imp_RegCloseKey
0x1800978d7  nop     dword ptr [rax+rax+00h]
0x1800978dc  lea     rcx, [rbp+arg_18]; this
0x1800978e0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800978e5  mov     [rbp+hKey], 0
0x1800978ed  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800978f6  lea     rax, [rbp+hKey]
0x1800978fa  mov     [rsp+58h+phkResult], rax; phkResult
0x1800978ff  mov     [rsp+58h+pcbData], 0; lpSecurityAttributes
0x180097908  mov     dword ptr [rsp+58h+pvData], 20006h; samDesired
0x180097910  mov     dword ptr [rsp+58h+pdwType], 0; int
0x180097918  xor     r9d, r9d; lpClass
0x18009791b  xor     r8d, r8d; Reserved
0x18009791e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Reliability Analys"...
0x180097925  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009792c  call    cs:__imp_RegCreateKeyExW
0x180097933  nop     dword ptr [rax+rax+00h]
0x180097938  test    eax, eax
0x18009793a  jle     short loc_180097944
0x18009793c  movzx   eax, ax
0x18009793f  or      eax, 80070000h
0x180097944  mov     rcx, [rbp+10h]; this
0x180097948  test    eax, eax
0x18009794a  jns     short loc_180097961
0x18009794c  mov     r9d, eax; char *
0x18009794f  lea     r8, aOnecoreBaseTel_244; "onecore\\base\\telemetry\\utc\\service"...
0x180097956  mov     edx, 44h ; 'D'; void *
0x18009795b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180097961  mov     dword ptr [rsp+58h+pvData], 4; cbData
0x180097969  lea     rax, [rbp+Data]
0x18009796d  mov     [rsp+58h+pdwType], rax; int
0x180097972  mov     r9d, 4; dwType
0x180097978  xor     r8d, r8d; Reserved
0x18009797b  lea     rdx, ValueName; "RacSampleNumber"
0x180097982  mov     rcx, [rbp+hKey]; hKey
0x180097986  call    cs:__imp_RegSetValueExW
0x18009798d  nop     dword ptr [rax+rax+00h]
0x180097992  test    eax, eax
0x180097994  jle     short loc_18009799E
0x180097996  movzx   eax, ax
0x180097999  or      eax, 80070000h
0x18009799e  mov     rcx, [rbp+10h]; this
0x1800979a2  test    eax, eax
0x1800979a4  jns     short loc_1800979BB
0x1800979a6  mov     r9d, eax; char *
0x1800979a9  lea     r8, aOnecoreBaseTel_244; "onecore\\base\\telemetry\\utc\\service"...
0x1800979b0  mov     edx, 4Ch ; 'L'; void *
0x1800979b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800979bb  lea     rcx, [rbp+hKey]
0x1800979bf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800979c4  mov     eax, [rbp+Data]
0x1800979c7  xorps   xmm0, xmm0
0x1800979ca  cvtsi2sd xmm0, rax
0x1800979cf  divsd   xmm0, cs:__real@4197d78400000000
0x1800979d7  mulsd   xmm0, cs:__real@4059000000000000
0x1800979df  add     rsp, 58h
0x1800979e3  pop     rbx
0x1800979e4  pop     rbp
0x1800979e5  retn
```

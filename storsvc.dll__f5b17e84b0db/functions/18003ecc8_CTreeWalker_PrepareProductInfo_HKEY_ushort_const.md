# CTreeWalker::PrepareProductInfo(HKEY__ *,ushort const *)

- ea: `0x18003ecc8`
- end: `0x18003f001`
- name: `?PrepareProductInfo@CTreeWalker@@AEAAJPEAUHKEY__@@PEBG@Z`
- size: `825`
- prototype: `int(CTreeWalker *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003e804`

## callees

- `0x18000d030`
- `0x18000d450`
- `0x18001c208`
- `0x18001f634`
- `0x18002ce80`
- `0x18002ebb4`
- `0x18003d61c`
- `0x18003dd84`
- `0x18003dfc8`
- `0x18003e02c`
- `0x18003ecc8`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003efc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003efc2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ed83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003edd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ee33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ee6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003eece`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ed83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003edd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ee33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ee6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003eece`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ed29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ed29`

## string_xrefs

- `0x18003edc5`: `WindowsInstaller`
- `0x18003ed77`: `UninstallString`
- `0x18003eec2`: `InstallLocation`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTreeWalker::PrepareProductInfo(CTreeWalker *this, HKEY a2, const unsigned __int16 *a3)
{
  HKEY v5; // r10
  LSTATUS v6; // eax
  LSTATUS v7; // edi
  bool v8; // cc
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rbx
  unsigned int (__fastcall *v12)(BYTE *); // rax
  unsigned __int64 v13; // rbx
  __int64 v14; // rbx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE v17[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v19[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[24]; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[32]; // [rsp+90h] [rbp-70h] BYREF
  BYTE v25[32]; // [rsp+B0h] [rbp-50h] BYREF
  BYTE v26[2]; // [rsp+D0h] [rbp-30h] BYREF
  BYTE Data[1024]; // [rsp+2E0h] [rbp+1E0h] BYREF

  ProductInfo::ProductInfo((ProductInfo *)&v21);
  hKey = 0;
  v6 = RegOpenKeyExW(v5, a3, 0, 0x20019u, &hKey);
  v7 = v6;
  cbData = 0;
  v8 = v6 <= 0;
  if ( v6 )
    goto LABEL_2;
  v21 = 0;
  cbData = 1024;
  v6 = RegQueryValueExW(hKey, L"UninstallString", 0, 0, Data, &cbData);
  v7 = v6;
  if ( v6 == 2 )
  {
    *(_WORD *)Data = 0;
  }
  else
  {
    v8 = v6 <= 0;
    if ( v6 )
      goto LABEL_2;
  }
  *(_DWORD *)v17 = 0;
  cbData = 4;
  v6 = RegQueryValueExW(hKey, L"WindowsInstaller", 0, 0, v17, &cbData);
  v7 = v6;
  if ( v6 == 2 )
  {
    *(_DWORD *)v17 = 0;
LABEL_12:
    v9 = 0;
    goto LABEL_13;
  }
  v8 = v6 <= 0;
  if ( v6 )
    goto LABEL_2;
  v9 = 1;
  if ( *(_DWORD *)v17 != 1 )
    goto LABEL_12;
LABEL_13:
  v21 = v9;
  *(_QWORD *)v19 = 0;
  cbData = 8;
  v7 = RegQueryValueExW(hKey, L"sEstimatedSize2", 0, 0, v19, &cbData);
  if ( v7 == 2 )
  {
    cbData = 8;
    v7 = RegQueryValueExW(hKey, L"EstimatedSize", 0, 0, v19, &cbData);
    if ( v7 == 2 )
    {
      v10 = 0;
      *(_QWORD *)v19 = 0;
LABEL_20:
      v22 = v10 << 10;
      cbData = 520;
      v6 = RegQueryValueExW(hKey, L"InstallLocation", 0, 0, v26, &cbData);
      v7 = v6;
      if ( v6 == 2 )
      {
        *(_WORD *)v26 = 0;
        goto LABEL_23;
      }
      v8 = v6 <= 0;
      if ( !v6 )
      {
LABEL_23:
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v26[2 * v11] );
        if ( (unsigned __int64)(v11 - 1) <= 0x101 )
        {
          v12 = (unsigned int (__fastcall *)(BYTE *))*((_QWORD *)this + 43);
          if ( v12 )
          {
            if ( !v12(v26) )
            {
              if ( *(_WORD *)&v25[2 * v11 + 30] != 92 )
              {
                *(_WORD *)&v26[2 * v11] = 92;
                v13 = 2 * v11 + 2;
                if ( v13 >= 0x208 )
                  _report_rangecheckfailure();
                *(_WORD *)&v26[v13] = 0;
              }
              std::wstring::assign(v23, v26);
            }
          }
        }
        v7 = 0;
        std::wstring::wstring(v25, a3);
        v14 = *(_QWORD *)std::map<std::wstring,ProductInfo,StringComparatorIgnoreCase,std::allocator<std::pair<std::wstring const,ProductInfo>>>::_Try_emplace<std::wstring,>(
                           (char *)this + 296,
                           v20,
                           v25);
        *(_DWORD *)(v14 + 64) = v21;
        *(_QWORD *)(v14 + 72) = v22;
        std::wstring::operator=(v14 + 80, v23);
        std::vector<std::wstring>::operator=(v14 + 112, v24);
        std::wstring::_Tidy_deallocate(v25);
        goto LABEL_33;
      }
LABEL_2:
      if ( v8 )
        goto LABEL_33;
      v7 = (unsigned __int16)v6;
      goto LABEL_4;
    }
  }
  if ( !v7 )
  {
    v10 = *(_QWORD *)v19;
    goto LABEL_20;
  }
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7;
LABEL_4:
    v7 |= 0x80070000;
  }
LABEL_33:
  if ( hKey )
    RegCloseKey(hKey);
  ProductInfo::~ProductInfo((ProductInfo *)&v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003ecc8  mov     [rsp-8+arg_18], rbx
0x18003eccd  push    rbp
0x18003ecce  push    rsi
0x18003eccf  push    rdi
0x18003ecd0  push    r14
0x18003ecd2  push    r15
0x18003ecd4  lea     rbp, [rsp-5F0h]
0x18003ecdc  sub     rsp, 6F0h
0x18003ece3  mov     rax, cs:__security_cookie
0x18003ecea  xor     rax, rsp
0x18003eced  mov     [rbp+610h+var_30], rax
0x18003ecf4  mov     r14, r8
0x18003ecf7  mov     r10, rdx
0x18003ecfa  mov     rsi, rcx
0x18003ecfd  lea     rcx, [rsp+710h+var_6B0]; this
0x18003ed02  call    ??0ProductInfo@@QEAA@XZ; ProductInfo::ProductInfo(void)
0x18003ed07  nop
0x18003ed08  xor     r15d, r15d
0x18003ed0b  mov     [rsp+710h+hKey], r15
0x18003ed10  lea     rax, [rsp+710h+hKey]
0x18003ed15  mov     [rsp+710h+phkResult], rax; phkResult
0x18003ed1a  mov     r9d, 20019h; samDesired
0x18003ed20  xor     r8d, r8d; ulOptions
0x18003ed23  mov     rdx, r14; lpSubKey
0x18003ed26  mov     rcx, r10; hKey
0x18003ed29  call    cs:__imp_RegOpenKeyExW
0x18003ed2f  mov     edi, eax
0x18003ed31  mov     [rsp+710h+cbData], r15d
0x18003ed36  test    eax, eax
0x18003ed38  jz      short loc_18003ED4E
0x18003ed3a  jle     loc_18003EFB8
0x18003ed40  movzx   edi, ax
0x18003ed43  or      edi, 80070000h
0x18003ed49  jmp     loc_18003EFB8
0x18003ed4e  mov     [rsp+710h+var_6B0], r15d
0x18003ed53  mov     [rsp+710h+cbData], 400h
0x18003ed5b  lea     rax, [rsp+710h+cbData]
0x18003ed60  mov     [rsp+710h+lpcbData], rax; lpcbData
0x18003ed65  lea     rax, [rbp+610h+Data]
0x18003ed6c  mov     [rsp+710h+phkResult], rax; lpData
0x18003ed71  xor     r9d, r9d; lpType
0x18003ed74  xor     r8d, r8d; lpReserved
0x18003ed77  lea     rdx, aUninstallstrin; "UninstallString"
0x18003ed7e  mov     rcx, [rsp+710h+hKey]; hKey
0x18003ed83  call    cs:__imp_RegQueryValueExW
0x18003ed89  mov     edi, eax
0x18003ed8b  cmp     eax, 2
0x18003ed8e  jnz     short loc_18003ED9A
0x18003ed90  mov     word ptr [rbp+610h+Data], r15w
0x18003ed98  jmp     short loc_18003ED9E
0x18003ed9a  test    eax, eax
0x18003ed9c  jnz     short loc_18003ED3A
0x18003ed9e  mov     dword ptr [rsp+710h+var_6DC], r15d
0x18003eda3  mov     [rsp+710h+cbData], 4
0x18003edab  lea     rax, [rsp+710h+cbData]
0x18003edb0  mov     [rsp+710h+lpcbData], rax; lpcbData
0x18003edb5  lea     rax, [rsp+710h+var_6DC]
0x18003edba  mov     [rsp+710h+phkResult], rax; lpData
0x18003edbf  xor     r9d, r9d; lpType
0x18003edc2  xor     r8d, r8d; lpReserved
0x18003edc5  lea     rdx, aWindowsinstall; "WindowsInstaller"
0x18003edcc  mov     rcx, [rsp+710h+hKey]; hKey
0x18003edd1  call    cs:__imp_RegQueryValueExW
0x18003edd7  mov     edi, eax
0x18003edd9  cmp     eax, 2
0x18003eddc  jnz     short loc_18003EDE5
0x18003edde  mov     dword ptr [rsp+710h+var_6DC], r15d
0x18003ede3  jmp     short loc_18003EDF8
0x18003ede5  test    eax, eax
0x18003ede7  jnz     loc_18003ED3A
0x18003eded  mov     eax, 1
0x18003edf2  cmp     dword ptr [rsp+710h+var_6DC], eax
0x18003edf6  jz      short loc_18003EDFB
0x18003edf8  mov     eax, r15d
0x18003edfb  mov     [rsp+710h+var_6B0], eax
0x18003edff  mov     qword ptr [rsp+710h+var_6D0], r15
0x18003ee04  mov     ebx, 8
0x18003ee09  mov     [rsp+710h+cbData], ebx
0x18003ee0d  lea     rax, [rsp+710h+cbData]
0x18003ee12  mov     [rsp+710h+lpcbData], rax; lpcbData
0x18003ee17  lea     rax, [rsp+710h+var_6D0]
0x18003ee1c  mov     [rsp+710h+phkResult], rax; lpData
0x18003ee21  xor     r9d, r9d; lpType
0x18003ee24  xor     r8d, r8d; lpReserved
0x18003ee27  lea     rdx, aSestimatedsize; "sEstimatedSize2"
0x18003ee2e  mov     rcx, [rsp+710h+hKey]; hKey
0x18003ee33  call    cs:__imp_RegQueryValueExW
0x18003ee39  mov     edi, eax
0x18003ee3b  cmp     eax, 2
0x18003ee3e  jnz     short loc_18003EE81
0x18003ee40  mov     [rsp+710h+cbData], ebx
0x18003ee44  lea     rax, [rsp+710h+cbData]
0x18003ee49  mov     [rsp+710h+lpcbData], rax; lpcbData
0x18003ee4e  lea     rax, [rsp+710h+var_6D0]
0x18003ee53  mov     [rsp+710h+phkResult], rax; lpData
0x18003ee58  xor     r9d, r9d; lpType
0x18003ee5b  xor     r8d, r8d; lpReserved
0x18003ee5e  lea     rdx, aEstimatedsize; "EstimatedSize"
0x18003ee65  mov     rcx, [rsp+710h+hKey]; hKey
0x18003ee6a  call    cs:__imp_RegQueryValueExW
0x18003ee70  mov     edi, eax
0x18003ee72  cmp     eax, 2
0x18003ee75  jnz     short loc_18003EE81
0x18003ee77  mov     rax, r15
0x18003ee7a  mov     qword ptr [rsp+710h+var_6D0], rax
0x18003ee7f  jmp     short loc_18003EE98
0x18003ee81  test    edi, edi
0x18003ee83  jz      short loc_18003EE93
0x18003ee85  jle     loc_18003EFB8
0x18003ee8b  movzx   edi, di
0x18003ee8e  jmp     loc_18003ED43
0x18003ee93  mov     rax, qword ptr [rsp+710h+var_6D0]
0x18003ee98  shl     rax, 0Ah
0x18003ee9c  mov     [rsp+710h+var_6A8], rax
0x18003eea1  mov     [rsp+710h+cbData], 208h
0x18003eea9  lea     rax, [rsp+710h+cbData]
0x18003eeae  mov     [rsp+710h+lpcbData], rax; lpcbData
0x18003eeb3  lea     rax, [rbp+610h+var_640]
0x18003eeb7  mov     [rsp+710h+phkResult], rax; lpData
0x18003eebc  xor     r9d, r9d; lpType
0x18003eebf  xor     r8d, r8d; lpReserved
0x18003eec2  lea     rdx, aInstalllocatio; "InstallLocation"
0x18003eec9  mov     rcx, [rsp+710h+hKey]; hKey
0x18003eece  call    cs:__imp_RegQueryValueExW
0x18003eed4  mov     edi, eax
0x18003eed6  cmp     eax, 2
0x18003eed9  jnz     short loc_18003EEE2
0x18003eedb  mov     word ptr [rbp+610h+var_640], r15w
0x18003eee0  jmp     short loc_18003EEEA
0x18003eee2  test    eax, eax
0x18003eee4  jnz     loc_18003ED3A
0x18003eeea  lea     rax, [rbp+610h+var_640]
0x18003eeee  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003eef2  inc     rbx
0x18003eef5  cmp     [rax+rbx*2], r15w
0x18003eefa  jnz     short loc_18003EEF2
0x18003eefc  lea     rax, [rbx-1]
0x18003ef00  cmp     rax, 101h
0x18003ef06  ja      short loc_18003EF5B
0x18003ef08  mov     rax, [rsi+158h]
0x18003ef0f  test    rax, rax
0x18003ef12  jz      short loc_18003EF5B
0x18003ef14  lea     rcx, [rbp+610h+var_640]
0x18003ef18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef1d  test    eax, eax
0x18003ef1f  jnz     short loc_18003EF5B
0x18003ef21  mov     eax, 5Ch ; '\'
0x18003ef26  cmp     [rbp+rbx*2+610h+var_642], ax
0x18003ef2b  jz      short loc_18003EF4D
0x18003ef2d  mov     word ptr [rbp+rbx*2+610h+var_640], ax
0x18003ef32  lea     rbx, ds:2[rbx*2]
0x18003ef3a  cmp     rbx, 208h
0x18003ef41  jnb     loc_18003EFFB
0x18003ef47  mov     word ptr [rbp+rbx+610h+var_640], r15w
0x18003ef4d  lea     rdx, [rbp+610h+var_640]
0x18003ef51  lea     rcx, [rsp+710h+var_6A0]
0x18003ef56  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18003ef5b  mov     edi, r15d
0x18003ef5e  mov     rdx, r14
0x18003ef61  lea     rcx, [rbp+610h+var_660]
0x18003ef65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003ef6a  nop
0x18003ef6b  lea     rcx, [rsi+128h]
0x18003ef72  lea     r8, [rbp+610h+var_660]
0x18003ef76  lea     rdx, [rsp+710h+var_6C8]
0x18003ef7b  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProductInfo@@UStringComparatorIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProductInfo@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProductInfo@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ProductInfo,StringComparatorIgnoreCase,std::allocator<std::pair<std::wstring const,ProductInfo>>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18003ef80  mov     rbx, [rax]
0x18003ef83  mov     eax, [rsp+710h+var_6B0]
0x18003ef87  mov     [rbx+40h], eax
0x18003ef8a  mov     rax, [rsp+710h+var_6A8]
0x18003ef8f  mov     [rbx+48h], rax
0x18003ef93  lea     rcx, [rbx+50h]
0x18003ef97  lea     rdx, [rsp+710h+var_6A0]
0x18003ef9c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003efa1  lea     rcx, [rbx+70h]
0x18003efa5  lea     rdx, [rbp+610h+var_680]
0x18003efa9  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x18003efae  nop
0x18003efaf  lea     rcx, [rbp+610h+var_660]
0x18003efb3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003efb8  mov     rcx, [rsp+710h+hKey]; hKey
0x18003efbd  test    rcx, rcx
0x18003efc0  jz      short loc_18003EFC9
0x18003efc2  call    cs:__imp_RegCloseKey
0x18003efc8  nop
0x18003efc9  lea     rcx, [rsp+710h+var_6B0]; this
0x18003efce  call    ??1ProductInfo@@QEAA@XZ; ProductInfo::~ProductInfo(void)
0x18003efd3  mov     eax, edi
0x18003efd5  mov     rcx, [rbp+610h+var_30]
0x18003efdc  xor     rcx, rsp; StackCookie
0x18003efdf  call    __security_check_cookie
0x18003efe4  mov     rbx, [rsp+710h+arg_18]
0x18003efec  add     rsp, 6F0h
0x18003eff3  pop     r15
0x18003eff5  pop     r14
0x18003eff7  pop     rdi
0x18003eff8  pop     rsi
0x18003eff9  pop     rbp
0x18003effa  retn
0x18003effb  call    __report_rangecheckfailure
```

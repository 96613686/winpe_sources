# FireSubscriptionEvent

- ea: `0x18001c8fc`
- end: `0x18001cb4b`
- name: `FireSubscriptionEvent`
- size: `591`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b514`
- `0x18001913c`
- `0x18001b528`
- `0x18001b8a0`

## callees

- `0x18001c8fc`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!__imp_SHUnicodeToUnicode` at `0x18001ca17`
- `SHLWAPI!__imp_SHUnicodeToUnicode` at `0x18001ca17`
- `ADVAPI32!RegCloseKey` at `0x18001cb24`
- `ADVAPI32!RegCloseKey` at `0x18001cb24`
- `ADVAPI32!RegEnumValueW` at `0x18001caf8`
- `ADVAPI32!RegEnumValueW` at `0x18001caf8`
- `ADVAPI32!RegOpenKeyExW` at `0x18001c95e`
- `ADVAPI32!RegOpenKeyExW` at `0x18001c95e`
- `ole32!StringFromCLSID` at `0x18001c97e`
- `ole32!StringFromCLSID` at `0x18001c97e`
- `ole32!CLSIDFromString` at `0x18001ca25`
- `ole32!CLSIDFromString` at `0x18001ca25`
- `ole32!CoTaskMemFree` at `0x18001cb19`
- `ole32!CoTaskMemFree` at `0x18001cb19`
- `ole32!CoCreateInstance` at `0x18001ca53`
- `ole32!CoCreateInstance` at `0x18001ca53`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c9aa`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c9aa`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb0e`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb0e`

## pseudocode

```c
void __fastcall FireSubscriptionEvent(unsigned int a1, IID *a2)
{
  IID v2; // xmm0
  DWORD v4; // ebx
  DWORD v5; // edx
  LSTATUS v6; // eax
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchValueName; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  LPOLESTR lpsz; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  GUID pclsid; // [rsp+80h] [rbp-80h] BYREF
  IID rclsid; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pwzSrc[40]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pwzDst[40]; // [rsp+F0h] [rbp-10h] BYREF

  if ( a2 )
  {
    v2 = *a2;
    hKey = 0;
    rclsid = v2;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Webcheck\\Notification Handlers",
            0,
            0x20019u,
            &hKey) )
    {
      lpsz = 0;
      if ( StringFromCLSID(&rclsid, &lpsz) >= 0 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(lpsz);
        if ( pvarg.llVal )
        {
          v4 = 0;
          v5 = 0;
          Type = 0;
          *(_DWORD *)Data = 0;
          while ( 1 )
          {
            cchValueName = 39;
            cbData = 4;
            v6 = RegEnumValueW(hKey, v5, pwzSrc, &cchValueName, 0, &Type, Data, &cbData);
            if ( v6 == 259 )
              break;
            if ( !v6 && (a1 & *(_DWORD *)Data) != 0 )
            {
              pclsid = 0;
              SHUnicodeToUnicode(pwzSrc, pwzDst, 39);
              if ( CLSIDFromString(pwzDst, &pclsid) >= 0 )
              {
                ppv = 0;
                if ( CoCreateInstance(&pclsid, 0, 0x17u, &IID_IOleCommandTarget, &ppv) >= 0 )
                {
                  (*(void (__fastcall **)(LPVOID, GUID *, _QWORD, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)ppv + 32LL))(
                    ppv,
                    &CLSID_SubscriptionMgr,
                    a1,
                    0,
                    &pvarg,
                    0);
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                }
              }
            }
            Type = 0;
            ++v4;
            *(_DWORD *)Data = 0;
            v5 = v4;
          }
          VariantClear(&pvarg);
        }
        CoTaskMemFree(lpsz);
      }
      RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x18001c8fc  test    rdx, rdx
0x18001c8ff  jz      locret_18001CB4A
0x18001c905  mov     [rsp-8+arg_10], rbx
0x18001c90a  mov     [rsp-8+arg_18], rdi
0x18001c90f  push    rbp
0x18001c910  lea     rbp, [rsp-50h]
0x18001c915  sub     rsp, 150h
0x18001c91c  mov     rax, cs:__security_cookie
0x18001c923  xor     rax, rsp
0x18001c926  mov     [rbp+50h+var_10], rax
0x18001c92a  movups  xmm0, xmmword ptr [rdx]
0x18001c92d  mov     edi, ecx
0x18001c92f  mov     [rsp+150h+hKey], 0
0x18001c938  lea     rax, [rsp+150h+hKey]
0x18001c93d  mov     r9d, 20019h; samDesired
0x18001c943  xor     r8d, r8d; ulOptions
0x18001c946  mov     [rsp+150h+phkResult], rax; phkResult
0x18001c94b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001c952  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c959  movdqu  xmmword ptr [rbp+50h+rclsid.Data1], xmm0
0x18001c95e  call    cs:__imp_RegOpenKeyExW
0x18001c964  test    eax, eax
0x18001c966  jnz     loc_18001CB2A
0x18001c96c  lea     rdx, [rsp+150h+lpsz]; lplpsz
0x18001c971  mov     [rsp+150h+lpsz], 0
0x18001c97a  lea     rcx, [rbp+50h+rclsid]; rclsid
0x18001c97e  call    cs:__imp_StringFromCLSID
0x18001c984  test    eax, eax
0x18001c986  js      loc_18001CB1F
0x18001c98c  mov     rcx, [rsp+150h+lpsz]; psz
0x18001c991  xor     eax, eax
0x18001c993  mov     qword ptr [rsp+150h+pvarg+10h], rax
0x18001c998  xorps   xmm0, xmm0
0x18001c99b  mov     eax, 8
0x18001c9a0  movups  xmmword ptr [rsp+150h+pvarg], xmm0
0x18001c9a5  mov     word ptr [rsp+150h+pvarg], ax
0x18001c9aa  call    cs:__imp_SysAllocString
0x18001c9b0  mov     qword ptr [rsp+150h+pvarg+8], rax
0x18001c9b5  test    rax, rax
0x18001c9b8  jz      loc_18001CB14
0x18001c9be  xor     ebx, ebx
0x18001c9c0  lea     rax, [rsp+150h+cbData]
0x18001c9c5  mov     [rsp+150h+lpcbData], rax
0x18001c9ca  xor     edx, edx
0x18001c9cc  lea     rax, [rsp+150h+Data]
0x18001c9d1  mov     [rsp+150h+Type], ebx
0x18001c9d5  mov     [rsp+150h+lpData], rax
0x18001c9da  lea     rax, [rsp+150h+Type]
0x18001c9df  mov     [rsp+150h+lpType], rax
0x18001c9e4  mov     [rsp+150h+phkResult], rbx
0x18001c9e9  mov     dword ptr [rsp+150h+Data], ebx
0x18001c9ed  jmp     loc_18001CADA
0x18001c9f2  test    eax, eax
0x18001c9f4  jnz     loc_18001CA9F
0x18001c9fa  test    dword ptr [rsp+150h+Data], edi
0x18001c9fe  jz      loc_18001CA9F
0x18001ca04  xorps   xmm0, xmm0
0x18001ca07  lea     r8d, [rax+27h]; cwchBuf
0x18001ca0b  lea     rdx, [rbp+50h+pwzDst]; pwzDst
0x18001ca0f  lea     rcx, [rbp+50h+pwzSrc]; pwzSrc
0x18001ca13  movups  xmmword ptr [rbp+50h+pclsid.Data1], xmm0
0x18001ca17  call    cs:__imp_SHUnicodeToUnicode
0x18001ca1d  lea     rdx, [rbp+50h+pclsid]; pclsid
0x18001ca21  lea     rcx, [rbp+50h+pwzDst]; lpsz
0x18001ca25  call    cs:__imp_CLSIDFromString
0x18001ca2b  test    eax, eax
0x18001ca2d  js      short loc_18001CA9F
0x18001ca2f  xor     edx, edx; pUnkOuter
0x18001ca31  mov     [rsp+150h+ppv], 0
0x18001ca3a  lea     rax, [rsp+150h+ppv]
0x18001ca3f  lea     r9, IID_IOleCommandTarget; riid
0x18001ca46  mov     [rsp+150h+phkResult], rax; ppv
0x18001ca4b  lea     rcx, [rbp+50h+pclsid]; rclsid
0x18001ca4f  lea     r8d, [rdx+17h]; dwClsContext
0x18001ca53  call    cs:__imp_CoCreateInstance
0x18001ca59  test    eax, eax
0x18001ca5b  js      short loc_18001CA9F
0x18001ca5d  mov     rcx, [rsp+150h+ppv]
0x18001ca62  lea     rdx, [rsp+150h+pvarg]
0x18001ca67  mov     [rsp+150h+lpType], 0
0x18001ca70  xor     r9d, r9d
0x18001ca73  mov     [rsp+150h+phkResult], rdx
0x18001ca78  mov     r8d, edi
0x18001ca7b  lea     rdx, CLSID_SubscriptionMgr
0x18001ca82  mov     rax, [rcx]
0x18001ca85  mov     rax, [rax+20h]
0x18001ca89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca8e  mov     rcx, [rsp+150h+ppv]
0x18001ca93  mov     rax, [rcx]
0x18001ca96  mov     rax, [rax+10h]
0x18001ca9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca9f  lea     rax, [rsp+150h+cbData]
0x18001caa4  mov     [rsp+150h+Type], 0
0x18001caac  mov     [rsp+150h+lpcbData], rax; lpcbData
0x18001cab1  inc     ebx
0x18001cab3  lea     rax, [rsp+150h+Data]
0x18001cab8  mov     dword ptr [rsp+150h+Data], 0
0x18001cac0  mov     [rsp+150h+lpData], rax; lpData
0x18001cac5  mov     edx, ebx; dwIndex
0x18001cac7  lea     rax, [rsp+150h+Type]
0x18001cacc  mov     [rsp+150h+lpType], rax; lpType
0x18001cad1  mov     [rsp+150h+phkResult], 0; lpReserved
0x18001cada  mov     rcx, [rsp+150h+hKey]; hKey
0x18001cadf  lea     r9, [rsp+150h+cchValueName]; lpcchValueName
0x18001cae4  lea     r8, [rbp+50h+pwzSrc]; lpValueName
0x18001cae8  mov     [rsp+150h+cchValueName], 27h ; '''
0x18001caf0  mov     [rsp+150h+cbData], 4
0x18001caf8  call    cs:__imp_RegEnumValueW
0x18001cafe  cmp     eax, 103h
0x18001cb03  jnz     loc_18001C9F2
0x18001cb09  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18001cb0e  call    cs:__imp_VariantClear
0x18001cb14  mov     rcx, [rsp+150h+lpsz]; pv
0x18001cb19  call    cs:__imp_CoTaskMemFree
0x18001cb1f  mov     rcx, [rsp+150h+hKey]; hKey
0x18001cb24  call    cs:__imp_RegCloseKey
0x18001cb2a  mov     rcx, [rbp+50h+var_10]
0x18001cb2e  xor     rcx, rsp; StackCookie
0x18001cb31  call    __security_check_cookie
0x18001cb36  lea     r11, [rsp+150h+var_s0]
0x18001cb3e  mov     rbx, [r11+20h]
0x18001cb42  mov     rdi, [r11+28h]
0x18001cb46  mov     rsp, r11
0x18001cb49  pop     rbp
0x18001cb4a  retn
```

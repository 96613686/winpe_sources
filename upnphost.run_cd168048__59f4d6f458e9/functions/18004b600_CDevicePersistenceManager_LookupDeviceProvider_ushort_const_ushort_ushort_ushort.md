# CDevicePersistenceManager::LookupDeviceProvider(ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x18004b600`
- end: `0x18004b7fc`
- name: `?LookupDeviceProvider@CDevicePersistenceManager@@UEAAJPEBGPEAPEAG11@Z`
- size: `508`
- prototype: `__int64 __fastcall(CDevicePersistenceManager *this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **pv)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x180011cfc`
- `0x180012d70`
- `0x180026420`
- `0x180031534`
- `0x18003b1cc`
- `0x18004b600`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004b7b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004b7c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004b7d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004b7b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004b7c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004b7d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b6f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b704`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b6f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b704`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b763`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b763`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b772`

## pseudocode

```c
__int64 __fastcall CDevicePersistenceManager::LookupDeviceProvider(
        CDevicePersistenceManager *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned __int16 **pv)
{
  unsigned __int16 **v8; // r14
  void *v9; // rbx
  void *v10; // rdi
  int IsAllowedCOMCallLocality; // esi
  int String; // eax
  bool v13; // zf
  HKEY v15; // [rsp+20h] [rbp-28h] BYREF
  void *v16; // [rsp+28h] [rbp-20h] BYREF
  void *v17; // [rsp+30h] [rbp-18h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+50h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( !a3 )
    return 2147500035LL;
  if ( !a4 )
    return 2147500035LL;
  v8 = pv;
  if ( !pv )
    return 2147500035LL;
  v9 = 0;
  v10 = 0;
  v16 = 0;
  Block[0] = 0;
  v17 = 0;
  v15 = 0;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = HrCreateOrOpenProvidersKey(&v15);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      hKey = 0;
      IsAllowedCOMCallLocality = HrRegOpenKeyEx(v15, a2, 0x20019u, &hKey);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        IsAllowedCOMCallLocality = HrRegQueryString(hKey, L"Provider ProgId", (struct CUString *)&v16);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          IsAllowedCOMCallLocality = HrRegQueryString(hKey, L"Init String", (struct CUString *)Block);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            String = HrRegQueryString(hKey, L"Container Id", (struct CUString *)&v17);
            v10 = v17;
            IsAllowedCOMCallLocality = String;
          }
        }
        RegCloseKey(hKey);
        v9 = v16;
      }
      RegCloseKey(v15);
    }
  }
  *a3 = 0;
  *a4 = 0;
  *v8 = 0;
  v13 = IsAllowedCOMCallLocality == 0;
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)&v16, a3);
    if ( IsAllowedCOMCallLocality < 0
      || (IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)Block, a4), IsAllowedCOMCallLocality < 0)
      || (IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)&v17, v8), IsAllowedCOMCallLocality < 0) )
    {
      CoTaskMemFree(a4);
      CoTaskMemFree(v8);
    }
    v13 = IsAllowedCOMCallLocality == 0;
  }
  if ( !v13 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  free(v10);
  free(Block[0]);
  free(v9);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x18004b600  push    rbp
0x18004b602  push    rbx
0x18004b603  push    rsi
0x18004b604  push    rdi
0x18004b605  push    r12
0x18004b607  push    r13
0x18004b609  push    r14
0x18004b60b  push    r15
0x18004b60d  mov     rbp, rsp
0x18004b610  sub     rsp, 48h
0x18004b614  mov     r15, r9
0x18004b617  mov     r12, r8
0x18004b61a  mov     r13, rdx
0x18004b61d  test    rdx, rdx
0x18004b620  jz      loc_18004B7E5
0x18004b626  test    r8, r8
0x18004b629  jz      loc_18004B7E5
0x18004b62f  test    r9, r9
0x18004b632  jz      loc_18004B7E5
0x18004b638  mov     r14, [rbp+pv]
0x18004b63c  test    r14, r14
0x18004b63f  jz      loc_18004B7E5
0x18004b645  xor     ebx, ebx
0x18004b647  xor     edi, edi
0x18004b649  mov     [rbp+var_20], rbx
0x18004b64d  mov     [rbp+Block], rbx
0x18004b651  mov     [rbp+var_18], rdi
0x18004b655  lea     ecx, [rbx+1]
0x18004b658  mov     [rbp+var_28], rbx
0x18004b65c  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18004b661  mov     esi, eax
0x18004b663  test    eax, eax
0x18004b665  js      loc_18004B710
0x18004b66b  lea     rcx, [rbp+var_28]; HKEY *
0x18004b66f  call    ?HrCreateOrOpenProvidersKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenProvidersKey(HKEY__ * *)
0x18004b674  mov     esi, eax
0x18004b676  test    eax, eax
0x18004b678  js      loc_18004B710
0x18004b67e  mov     rcx, [rbp+var_28]; HKEY
0x18004b682  lea     r9, [rbp+hKey]; HKEY *
0x18004b686  mov     r8d, 20019h; unsigned int
0x18004b68c  mov     [rbp+hKey], rbx
0x18004b690  mov     rdx, r13; unsigned __int16 *
0x18004b693  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18004b698  mov     esi, eax
0x18004b69a  test    eax, eax
0x18004b69c  js      short loc_18004B700
0x18004b69e  mov     rcx, [rbp+hKey]; hKey
0x18004b6a2  lea     r8, [rbp+var_20]; this
0x18004b6a6  lea     rdx, aProviderProgid; "Provider ProgId"
0x18004b6ad  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004b6b2  mov     esi, eax
0x18004b6b4  test    eax, eax
0x18004b6b6  js      short loc_18004B6EC
0x18004b6b8  mov     rcx, [rbp+hKey]; hKey
0x18004b6bc  lea     r8, [rbp+Block]; this
0x18004b6c0  lea     rdx, aInitString; "Init String"
0x18004b6c7  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004b6cc  mov     esi, eax
0x18004b6ce  test    eax, eax
0x18004b6d0  js      short loc_18004B6EC
0x18004b6d2  mov     rcx, [rbp+hKey]; hKey
0x18004b6d6  lea     r8, [rbp+var_18]; this
0x18004b6da  lea     rdx, aContainerId; "Container Id"
0x18004b6e1  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004b6e6  mov     rdi, [rbp+var_18]
0x18004b6ea  mov     esi, eax
0x18004b6ec  mov     rcx, [rbp+hKey]; hKey
0x18004b6f0  call    cs:__imp_RegCloseKey
0x18004b6f7  nop     dword ptr [rax+rax+00h]
0x18004b6fc  mov     rbx, [rbp+var_20]
0x18004b700  mov     rcx, [rbp+var_28]; hKey
0x18004b704  call    cs:__imp_RegCloseKey
0x18004b70b  nop     dword ptr [rax+rax+00h]
0x18004b710  mov     qword ptr [r12], 0
0x18004b718  mov     qword ptr [r15], 0
0x18004b71f  mov     qword ptr [r14], 0
0x18004b726  test    esi, esi
0x18004b728  js      short loc_18004B780
0x18004b72a  mov     rdx, r12; unsigned __int16 **
0x18004b72d  lea     rcx, [rbp+var_20]; this
0x18004b731  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18004b736  mov     esi, eax
0x18004b738  test    eax, eax
0x18004b73a  js      short loc_18004B760
0x18004b73c  mov     rdx, r15; unsigned __int16 **
0x18004b73f  lea     rcx, [rbp+Block]; this
0x18004b743  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18004b748  mov     esi, eax
0x18004b74a  test    eax, eax
0x18004b74c  js      short loc_18004B760
0x18004b74e  mov     rdx, r14; unsigned __int16 **
0x18004b751  lea     rcx, [rbp+var_18]; this
0x18004b755  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18004b75a  mov     esi, eax
0x18004b75c  test    eax, eax
0x18004b75e  jns     short loc_18004B77E
0x18004b760  mov     rcx, r15; pv
0x18004b763  call    cs:__imp_CoTaskMemFree
0x18004b76a  nop     dword ptr [rax+rax+00h]
0x18004b76f  mov     rcx, r14; pv
0x18004b772  call    cs:__imp_CoTaskMemFree
0x18004b779  nop     dword ptr [rax+rax+00h]
0x18004b77e  test    esi, esi
0x18004b780  jz      short loc_18004B7B3
0x18004b782  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b789  lea     rax, WPP_GLOBAL_Control
0x18004b790  cmp     rcx, rax
0x18004b793  jz      short loc_18004B7B3
0x18004b795  test    byte ptr [rcx+1Ch], 1
0x18004b799  jz      short loc_18004B7B3
0x18004b79b  mov     rcx, [rcx+10h]
0x18004b79f  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x18004b7a6  mov     edx, 12h
0x18004b7ab  mov     r9d, esi
0x18004b7ae  call    WPP_SF_d
0x18004b7b3  mov     rcx, rdi; Block
0x18004b7b6  call    cs:__imp_free
0x18004b7bd  nop     dword ptr [rax+rax+00h]
0x18004b7c2  mov     rcx, [rbp+Block]; Block
0x18004b7c6  call    cs:__imp_free
0x18004b7cd  nop     dword ptr [rax+rax+00h]
0x18004b7d2  mov     rcx, rbx; Block
0x18004b7d5  call    cs:__imp_free
0x18004b7dc  nop     dword ptr [rax+rax+00h]
0x18004b7e1  mov     eax, esi
0x18004b7e3  jmp     short loc_18004B7EA
0x18004b7e5  mov     eax, 80004003h
0x18004b7ea  add     rsp, 48h
0x18004b7ee  pop     r15
0x18004b7f0  pop     r14
0x18004b7f2  pop     r13
0x18004b7f4  pop     r12
0x18004b7f6  pop     rdi
0x18004b7f7  pop     rsi
0x18004b7f8  pop     rbx
0x18004b7f9  pop     rbp
0x18004b7fa  retn
```

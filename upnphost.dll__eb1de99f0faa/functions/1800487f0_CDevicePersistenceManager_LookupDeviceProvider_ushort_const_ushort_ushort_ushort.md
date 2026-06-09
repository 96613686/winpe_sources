# CDevicePersistenceManager::LookupDeviceProvider(ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x1800487f0`
- end: `0x1800489c1`
- name: `?LookupDeviceProvider@CDevicePersistenceManager@@UEAAJPEBGPEAPEAG11@Z`
- size: `465`
- prototype: `int(CDevicePersistenceManager *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180013180`
- `0x18001d254`
- `0x18001dcac`
- `0x180025470`
- `0x18002fb24`
- `0x180038ce4`
- `0x1800487f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004898e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048998`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800489a1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004898e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048998`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800489a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800488e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800488ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800488e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800488ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048947`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048950`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048947`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048950`

## pseudocode

```c
__int64 __fastcall CDevicePersistenceManager::LookupDeviceProvider(
        CDevicePersistenceManager *this,
        const unsigned __int16 *a2,
        LPVOID *a3,
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
      || (IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)Block, (LPVOID *)a4), IsAllowedCOMCallLocality < 0)
      || (IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)&v17, (LPVOID *)v8), IsAllowedCOMCallLocality < 0) )
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
0x1800487f0  push    rbp
0x1800487f2  push    rbx
0x1800487f3  push    rsi
0x1800487f4  push    rdi
0x1800487f5  push    r12
0x1800487f7  push    r13
0x1800487f9  push    r14
0x1800487fb  push    r15
0x1800487fd  mov     rbp, rsp
0x180048800  sub     rsp, 48h
0x180048804  mov     r15, r9
0x180048807  mov     r12, r8
0x18004880a  mov     r13, rdx
0x18004880d  test    rdx, rdx
0x180048810  jz      loc_1800489AB
0x180048816  test    r8, r8
0x180048819  jz      loc_1800489AB
0x18004881f  test    r9, r9
0x180048822  jz      loc_1800489AB
0x180048828  mov     r14, [rbp+pv]
0x18004882c  test    r14, r14
0x18004882f  jz      loc_1800489AB
0x180048835  xor     ebx, ebx
0x180048837  xor     edi, edi
0x180048839  mov     [rbp+var_20], rbx
0x18004883d  mov     [rbp+Block], rbx
0x180048841  mov     [rbp+var_18], rdi
0x180048845  lea     ecx, [rbx+1]
0x180048848  mov     [rbp+var_28], rbx
0x18004884c  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180048851  mov     esi, eax
0x180048853  test    eax, eax
0x180048855  js      loc_1800488F4
0x18004885b  lea     rcx, [rbp+var_28]; HKEY *
0x18004885f  call    ?HrCreateOrOpenProvidersKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenProvidersKey(HKEY__ * *)
0x180048864  mov     esi, eax
0x180048866  test    eax, eax
0x180048868  js      loc_1800488F4
0x18004886e  mov     rcx, [rbp+var_28]; HKEY
0x180048872  lea     r9, [rbp+hKey]; HKEY *
0x180048876  mov     r8d, 20019h; unsigned int
0x18004887c  mov     [rbp+hKey], rbx
0x180048880  mov     rdx, r13; unsigned __int16 *
0x180048883  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180048888  mov     esi, eax
0x18004888a  test    eax, eax
0x18004888c  js      short loc_1800488EA
0x18004888e  mov     rcx, [rbp+hKey]; hKey
0x180048892  lea     r8, [rbp+var_20]; this
0x180048896  lea     rdx, aProviderProgid; "Provider ProgId"
0x18004889d  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x1800488a2  mov     esi, eax
0x1800488a4  test    eax, eax
0x1800488a6  js      short loc_1800488DC
0x1800488a8  mov     rcx, [rbp+hKey]; hKey
0x1800488ac  lea     r8, [rbp+Block]; this
0x1800488b0  lea     rdx, aInitString; "Init String"
0x1800488b7  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x1800488bc  mov     esi, eax
0x1800488be  test    eax, eax
0x1800488c0  js      short loc_1800488DC
0x1800488c2  mov     rcx, [rbp+hKey]; hKey
0x1800488c6  lea     r8, [rbp+var_18]; this
0x1800488ca  lea     rdx, aContainerId; "Container Id"
0x1800488d1  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x1800488d6  mov     rdi, [rbp+var_18]
0x1800488da  mov     esi, eax
0x1800488dc  mov     rcx, [rbp+hKey]; hKey
0x1800488e0  call    cs:__imp_RegCloseKey
0x1800488e6  mov     rbx, [rbp+var_20]
0x1800488ea  mov     rcx, [rbp+var_28]; hKey
0x1800488ee  call    cs:__imp_RegCloseKey
0x1800488f4  mov     qword ptr [r12], 0
0x1800488fc  mov     qword ptr [r15], 0
0x180048903  mov     qword ptr [r14], 0
0x18004890a  test    esi, esi
0x18004890c  js      short loc_180048958
0x18004890e  mov     rdx, r12; unsigned __int16 **
0x180048911  lea     rcx, [rbp+var_20]; this
0x180048915  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18004891a  mov     esi, eax
0x18004891c  test    eax, eax
0x18004891e  js      short loc_180048944
0x180048920  mov     rdx, r15; unsigned __int16 **
0x180048923  lea     rcx, [rbp+Block]; this
0x180048927  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18004892c  mov     esi, eax
0x18004892e  test    eax, eax
0x180048930  js      short loc_180048944
0x180048932  mov     rdx, r14; unsigned __int16 **
0x180048935  lea     rcx, [rbp+var_18]; this
0x180048939  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18004893e  mov     esi, eax
0x180048940  test    eax, eax
0x180048942  jns     short loc_180048956
0x180048944  mov     rcx, r15; pv
0x180048947  call    cs:__imp_CoTaskMemFree
0x18004894d  mov     rcx, r14; pv
0x180048950  call    cs:__imp_CoTaskMemFree
0x180048956  test    esi, esi
0x180048958  jz      short loc_18004898B
0x18004895a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048961  lea     rax, WPP_GLOBAL_Control
0x180048968  cmp     rcx, rax
0x18004896b  jz      short loc_18004898B
0x18004896d  test    byte ptr [rcx+1Ch], 1
0x180048971  jz      short loc_18004898B
0x180048973  mov     rcx, [rcx+10h]
0x180048977  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x18004897e  mov     edx, 12h
0x180048983  mov     r9d, esi
0x180048986  call    WPP_SF_d
0x18004898b  mov     rcx, rdi; Block
0x18004898e  call    cs:__imp_free
0x180048994  mov     rcx, [rbp+Block]; Block
0x180048998  call    cs:__imp_free
0x18004899e  mov     rcx, rbx; Block
0x1800489a1  call    cs:__imp_free
0x1800489a7  mov     eax, esi
0x1800489a9  jmp     short loc_1800489B0
0x1800489ab  mov     eax, 80004003h
0x1800489b0  add     rsp, 48h
0x1800489b4  pop     r15
0x1800489b6  pop     r14
0x1800489b8  pop     r13
0x1800489ba  pop     r12
0x1800489bc  pop     rdi
0x1800489bd  pop     rsi
0x1800489be  pop     rbx
0x1800489bf  pop     rbp
0x1800489c0  retn
```

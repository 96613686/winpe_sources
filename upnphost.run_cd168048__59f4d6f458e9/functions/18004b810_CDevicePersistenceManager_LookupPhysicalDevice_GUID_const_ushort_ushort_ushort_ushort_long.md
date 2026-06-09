# CDevicePersistenceManager::LookupPhysicalDevice(_GUID const &,ushort * *,ushort * *,ushort * *,ushort * *,long *)

- ea: `0x18004b810`
- end: `0x18004bb06`
- name: `?LookupPhysicalDevice@CDevicePersistenceManager@@UEAAJAEBU_GUID@@PEAPEAG111PEAJ@Z`
- size: `758`
- prototype: `int(CDevicePersistenceManager *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18000fb0c`
- `0x180011cfc`
- `0x180012fa0`
- `0x180026420`
- `0x180031534`
- `0x18003b1cc`
- `0x18004b810`
- `0x180055ab8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004ba9a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004baaa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004baba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bac9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bad8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004ba9a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004baaa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004baba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bac9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bad8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b96f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b983`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b96f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b983`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ba17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ba33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ba4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ba17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ba33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ba4e`

## string_xrefs

- `0x18004b943`: `Resource Path`

## pseudocode

```c
__int64 __fastcall CDevicePersistenceManager::LookupPhysicalDevice(
        CDevicePersistenceManager *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        LPVOID *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        int *a7)
{
  LPVOID *v9; // r14
  LPVOID *v10; // r15
  unsigned __int16 *v11; // rbx
  void *v12; // rdi
  int IsAllowedCOMCallLocality; // esi
  bool v14; // zf
  HKEY hKey; // [rsp+20h] [rbp-40h] BYREF
  HKEY v17; // [rsp+28h] [rbp-38h] BYREF
  unsigned __int16 *v18; // [rsp+30h] [rbp-30h] BYREF
  void *v19; // [rsp+38h] [rbp-28h] BYREF
  void *Block; // [rsp+40h] [rbp-20h] BYREF
  void *v21; // [rsp+48h] [rbp-18h] BYREF
  void *v22[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+B0h] [rbp+50h] BYREF

  if ( !a3 )
    return 2147500035LL;
  if ( !a4 )
    return 2147500035LL;
  v9 = (LPVOID *)a5;
  if ( !a5 )
    return 2147500035LL;
  v10 = (LPVOID *)a6;
  if ( !a6 || !a7 )
    return 2147500035LL;
  v18 = 0;
  v11 = 0;
  v19 = 0;
  v12 = 0;
  v22[0] = 0;
  v21 = 0;
  Block = 0;
  v24 = 0;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = CUString::HrInitFromGUID((CUString *)&v18, a2);
    if ( IsAllowedCOMCallLocality < 0
      || (v17 = 0, IsAllowedCOMCallLocality = HrCreateOrOpenDevicesKey(&v17), IsAllowedCOMCallLocality < 0) )
    {
      v11 = v18;
    }
    else
    {
      hKey = 0;
      v11 = v18;
      IsAllowedCOMCallLocality = HrRegOpenKeyEx(v17, v18, 0x20019u, &hKey);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        IsAllowedCOMCallLocality = HrRegQueryString(hKey, L"ProgId", (struct CUString *)&v19);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          IsAllowedCOMCallLocality = HrRegQueryString(hKey, L"Init String", (struct CUString *)v22);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            IsAllowedCOMCallLocality = HrRegQueryString(hKey, L"Container Id", (struct CUString *)&v21);
            if ( IsAllowedCOMCallLocality >= 0 )
            {
              IsAllowedCOMCallLocality = HrRegQueryString(hKey, L"Resource Path", (struct CUString *)&Block);
              if ( IsAllowedCOMCallLocality >= 0 )
                IsAllowedCOMCallLocality = HrRegQueryDword(hKey, L"Life Time", &v24);
            }
          }
        }
        RegCloseKey(hKey);
        v12 = v19;
      }
      RegCloseKey(v17);
    }
  }
  *a3 = 0;
  *a4 = 0;
  *v9 = 0;
  *v10 = 0;
  v14 = IsAllowedCOMCallLocality == 0;
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)&v19, a3);
    if ( IsAllowedCOMCallLocality < 0
      || (IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)v22, (unsigned __int16 **)a4),
          IsAllowedCOMCallLocality < 0)
      || (IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)&v21, (unsigned __int16 **)v9),
          IsAllowedCOMCallLocality < 0)
      || (IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)&Block, (unsigned __int16 **)v10),
          IsAllowedCOMCallLocality < 0) )
    {
      if ( *a4 )
      {
        CoTaskMemFree(*a4);
        *a4 = 0;
      }
      if ( *v9 )
      {
        CoTaskMemFree(*v9);
        *v9 = 0;
      }
      if ( *v10 )
      {
        CoTaskMemFree(*v10);
        *v10 = 0;
      }
    }
    else
    {
      *a7 = v24;
    }
    v14 = IsAllowedCOMCallLocality == 0;
  }
  if ( !v14 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  free(Block);
  free(v21);
  free(v22[0]);
  free(v12);
  free(v11);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x18004b810  mov     [rsp-38h+arg_0], rbx
0x18004b815  mov     [rsp-38h+arg_8], rdx
0x18004b81a  push    rbp
0x18004b81b  push    rsi
0x18004b81c  push    rdi
0x18004b81d  push    r12
0x18004b81f  push    r13
0x18004b821  push    r14
0x18004b823  push    r15
0x18004b825  mov     rbp, rsp
0x18004b828  sub     rsp, 60h
0x18004b82c  xor     eax, eax
0x18004b82e  mov     r12, r9
0x18004b831  mov     r13, r8
0x18004b834  test    r8, r8
0x18004b837  jz      loc_18004BAE8
0x18004b83d  test    r9, r9
0x18004b840  jz      loc_18004BAE8
0x18004b846  mov     r14, [rbp+arg_20]
0x18004b84a  test    r14, r14
0x18004b84d  jz      loc_18004BAE8
0x18004b853  mov     r15, [rbp+arg_28]
0x18004b857  test    r15, r15
0x18004b85a  jz      loc_18004BAE8
0x18004b860  cmp     [rbp+arg_30], rax
0x18004b864  jz      loc_18004BAE8
0x18004b86a  lea     ecx, [rax+1]
0x18004b86d  mov     [rbp+var_30], rax
0x18004b871  mov     ebx, eax
0x18004b873  mov     [rbp+var_28], rax
0x18004b877  mov     edi, eax
0x18004b879  mov     [rbp+var_10], rax
0x18004b87d  mov     [rbp+var_18], rax
0x18004b881  mov     [rbp+Block], rax
0x18004b885  mov     [rbp+arg_10], eax
0x18004b888  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18004b88d  mov     esi, eax
0x18004b88f  test    eax, eax
0x18004b891  js      loc_18004B995
0x18004b897  mov     rdx, [rbp+arg_8]; struct _GUID *
0x18004b89b  lea     rcx, [rbp+var_30]; this
0x18004b89f  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x18004b8a4  mov     esi, eax
0x18004b8a6  test    eax, eax
0x18004b8a8  js      loc_18004B991
0x18004b8ae  lea     rcx, [rbp+var_38]; HKEY *
0x18004b8b2  mov     [rbp+var_38], rbx
0x18004b8b6  call    ?HrCreateOrOpenDevicesKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDevicesKey(HKEY__ * *)
0x18004b8bb  mov     esi, eax
0x18004b8bd  test    eax, eax
0x18004b8bf  js      loc_18004B991
0x18004b8c5  mov     rcx, [rbp+var_38]; HKEY
0x18004b8c9  lea     r9, [rbp+hKey]; HKEY *
0x18004b8cd  mov     [rbp+hKey], rbx
0x18004b8d1  mov     r8d, 20019h; unsigned int
0x18004b8d7  mov     rbx, [rbp+var_30]
0x18004b8db  mov     rdx, rbx; unsigned __int16 *
0x18004b8de  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18004b8e3  mov     esi, eax
0x18004b8e5  test    eax, eax
0x18004b8e7  js      loc_18004B97F
0x18004b8ed  mov     rcx, [rbp+hKey]; hKey
0x18004b8f1  lea     r8, [rbp+var_28]; this
0x18004b8f5  lea     rdx, aProgid; "ProgId"
0x18004b8fc  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004b901  mov     esi, eax
0x18004b903  test    eax, eax
0x18004b905  js      short loc_18004B96B
0x18004b907  mov     rcx, [rbp+hKey]; hKey
0x18004b90b  lea     r8, [rbp+var_10]; this
0x18004b90f  lea     rdx, aInitString; "Init String"
0x18004b916  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004b91b  mov     esi, eax
0x18004b91d  test    eax, eax
0x18004b91f  js      short loc_18004B96B
0x18004b921  mov     rcx, [rbp+hKey]; hKey
0x18004b925  lea     r8, [rbp+var_18]; this
0x18004b929  lea     rdx, aContainerId; "Container Id"
0x18004b930  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004b935  mov     esi, eax
0x18004b937  test    eax, eax
0x18004b939  js      short loc_18004B96B
0x18004b93b  mov     rcx, [rbp+hKey]; hKey
0x18004b93f  lea     r8, [rbp+Block]; this
0x18004b943  lea     rdx, aResourcePath; "Resource Path"
0x18004b94a  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004b94f  mov     esi, eax
0x18004b951  test    eax, eax
0x18004b953  js      short loc_18004B96B
0x18004b955  mov     rcx, [rbp+hKey]; HKEY
0x18004b959  lea     r8, [rbp+arg_10]; unsigned int *
0x18004b95d  lea     rdx, aLifeTime; "Life Time"
0x18004b964  call    ?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; HrRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x18004b969  mov     esi, eax
0x18004b96b  mov     rcx, [rbp+hKey]; hKey
0x18004b96f  call    cs:__imp_RegCloseKey
0x18004b976  nop     dword ptr [rax+rax+00h]
0x18004b97b  mov     rdi, [rbp+var_28]
0x18004b97f  mov     rcx, [rbp+var_38]; hKey
0x18004b983  call    cs:__imp_RegCloseKey
0x18004b98a  nop     dword ptr [rax+rax+00h]
0x18004b98f  jmp     short loc_18004B995
0x18004b991  mov     rbx, [rbp+var_30]
0x18004b995  mov     qword ptr [r13+0], 0
0x18004b99d  mov     qword ptr [r12], 0
0x18004b9a5  mov     qword ptr [r14], 0
0x18004b9ac  mov     qword ptr [r15], 0
0x18004b9b3  test    esi, esi
0x18004b9b5  js      loc_18004BA63
0x18004b9bb  mov     rdx, r13; unsigned __int16 **
0x18004b9be  lea     rcx, [rbp+var_28]; this
0x18004b9c2  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18004b9c7  mov     esi, eax
0x18004b9c9  test    eax, eax
0x18004b9cb  js      short loc_18004BA0E
0x18004b9cd  mov     rdx, r12; unsigned __int16 **
0x18004b9d0  lea     rcx, [rbp+var_10]; this
0x18004b9d4  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18004b9d9  mov     esi, eax
0x18004b9db  test    eax, eax
0x18004b9dd  js      short loc_18004BA0E
0x18004b9df  mov     rdx, r14; unsigned __int16 **
0x18004b9e2  lea     rcx, [rbp+var_18]; this
0x18004b9e6  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18004b9eb  mov     esi, eax
0x18004b9ed  test    eax, eax
0x18004b9ef  js      short loc_18004BA0E
0x18004b9f1  mov     rdx, r15; unsigned __int16 **
0x18004b9f4  lea     rcx, [rbp+Block]; this
0x18004b9f8  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x18004b9fd  mov     esi, eax
0x18004b9ff  test    eax, eax
0x18004ba01  js      short loc_18004BA0E
0x18004ba03  mov     rcx, [rbp+arg_30]
0x18004ba07  mov     eax, [rbp+arg_10]
0x18004ba0a  mov     [rcx], eax
0x18004ba0c  jmp     short loc_18004BA61
0x18004ba0e  mov     rcx, [r12]; pv
0x18004ba12  test    rcx, rcx
0x18004ba15  jz      short loc_18004BA2B
0x18004ba17  call    cs:__imp_CoTaskMemFree
0x18004ba1e  nop     dword ptr [rax+rax+00h]
0x18004ba23  mov     qword ptr [r12], 0
0x18004ba2b  mov     rcx, [r14]; pv
0x18004ba2e  test    rcx, rcx
0x18004ba31  jz      short loc_18004BA46
0x18004ba33  call    cs:__imp_CoTaskMemFree
0x18004ba3a  nop     dword ptr [rax+rax+00h]
0x18004ba3f  mov     qword ptr [r14], 0
0x18004ba46  mov     rcx, [r15]; pv
0x18004ba49  test    rcx, rcx
0x18004ba4c  jz      short loc_18004BA61
0x18004ba4e  call    cs:__imp_CoTaskMemFree
0x18004ba55  nop     dword ptr [rax+rax+00h]
0x18004ba5a  mov     qword ptr [r15], 0
0x18004ba61  test    esi, esi
0x18004ba63  jz      short loc_18004BA96
0x18004ba65  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba6c  lea     rax, WPP_GLOBAL_Control
0x18004ba73  cmp     rcx, rax
0x18004ba76  jz      short loc_18004BA96
0x18004ba78  test    byte ptr [rcx+1Ch], 1
0x18004ba7c  jz      short loc_18004BA96
0x18004ba7e  mov     rcx, [rcx+10h]
0x18004ba82  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x18004ba89  mov     edx, 0Dh
0x18004ba8e  mov     r9d, esi
0x18004ba91  call    WPP_SF_d
0x18004ba96  mov     rcx, [rbp+Block]; Block
0x18004ba9a  call    cs:__imp_free
0x18004baa1  nop     dword ptr [rax+rax+00h]
0x18004baa6  mov     rcx, [rbp+var_18]; Block
0x18004baaa  call    cs:__imp_free
0x18004bab1  nop     dword ptr [rax+rax+00h]
0x18004bab6  mov     rcx, [rbp+var_10]; Block
0x18004baba  call    cs:__imp_free
0x18004bac1  nop     dword ptr [rax+rax+00h]
0x18004bac6  mov     rcx, rdi; Block
0x18004bac9  call    cs:__imp_free
0x18004bad0  nop     dword ptr [rax+rax+00h]
0x18004bad5  mov     rcx, rbx; Block
0x18004bad8  call    cs:__imp_free
0x18004badf  nop     dword ptr [rax+rax+00h]
0x18004bae4  mov     eax, esi
0x18004bae6  jmp     short loc_18004BAED
0x18004bae8  mov     eax, 80004003h
0x18004baed  mov     rbx, [rsp+60h+arg_0]
0x18004baf5  add     rsp, 60h
0x18004baf9  pop     r15
0x18004bafb  pop     r14
0x18004bafd  pop     r13
0x18004baff  pop     r12
0x18004bb01  pop     rdi
0x18004bb02  pop     rsi
0x18004bb03  pop     rbp
0x18004bb04  retn
```

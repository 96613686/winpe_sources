# CDevicePersistenceManager::LookupPhysicalDevice(_GUID const &,ushort * *,ushort * *,ushort * *,ushort * *,long *)

- ea: `0x1800489d0`
- end: `0x180048c89`
- name: `?LookupPhysicalDevice@CDevicePersistenceManager@@UEAAJAEBU_GUID@@PEAPEAG111PEAJ@Z`
- size: `697`
- prototype: `int(CDevicePersistenceManager *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180013180`
- `0x18001add0`
- `0x18001d254`
- `0x18001df9c`
- `0x180025470`
- `0x18002fb24`
- `0x180038ce4`
- `0x1800489d0`
- `0x180052258`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048c3c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048c46`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048c50`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048c59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048c62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048c3c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048c46`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048c50`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048c59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048c62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048b2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048b3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048b2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048b3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048bcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048bf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048bcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048bf6`

## string_xrefs

- `0x180048b03`: `Resource Path`

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
0x1800489d0  mov     [rsp-38h+arg_0], rbx
0x1800489d5  mov     [rsp-38h+arg_8], rdx
0x1800489da  push    rbp
0x1800489db  push    rsi
0x1800489dc  push    rdi
0x1800489dd  push    r12
0x1800489df  push    r13
0x1800489e1  push    r14
0x1800489e3  push    r15
0x1800489e5  mov     rbp, rsp
0x1800489e8  sub     rsp, 60h
0x1800489ec  xor     eax, eax
0x1800489ee  mov     r12, r9
0x1800489f1  mov     r13, r8
0x1800489f4  test    r8, r8
0x1800489f7  jz      loc_180048C6C
0x1800489fd  test    r9, r9
0x180048a00  jz      loc_180048C6C
0x180048a06  mov     r14, [rbp+arg_20]
0x180048a0a  test    r14, r14
0x180048a0d  jz      loc_180048C6C
0x180048a13  mov     r15, [rbp+arg_28]
0x180048a17  test    r15, r15
0x180048a1a  jz      loc_180048C6C
0x180048a20  cmp     [rbp+arg_30], rax
0x180048a24  jz      loc_180048C6C
0x180048a2a  lea     ecx, [rax+1]
0x180048a2d  mov     [rbp+var_30], rax
0x180048a31  mov     ebx, eax
0x180048a33  mov     [rbp+var_28], rax
0x180048a37  mov     edi, eax
0x180048a39  mov     [rbp+var_10], rax
0x180048a3d  mov     [rbp+var_18], rax
0x180048a41  mov     [rbp+Block], rax
0x180048a45  mov     [rbp+arg_10], eax
0x180048a48  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180048a4d  mov     esi, eax
0x180048a4f  test    eax, eax
0x180048a51  js      loc_180048B49
0x180048a57  mov     rdx, [rbp+arg_8]; struct _GUID *
0x180048a5b  lea     rcx, [rbp+var_30]; this
0x180048a5f  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x180048a64  mov     esi, eax
0x180048a66  test    eax, eax
0x180048a68  js      loc_180048B45
0x180048a6e  lea     rcx, [rbp+var_38]; HKEY *
0x180048a72  mov     [rbp+var_38], rbx
0x180048a76  call    ?HrCreateOrOpenDevicesKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDevicesKey(HKEY__ * *)
0x180048a7b  mov     esi, eax
0x180048a7d  test    eax, eax
0x180048a7f  js      loc_180048B45
0x180048a85  mov     rcx, [rbp+var_38]; HKEY
0x180048a89  lea     r9, [rbp+hKey]; HKEY *
0x180048a8d  mov     [rbp+hKey], rbx
0x180048a91  mov     r8d, 20019h; unsigned int
0x180048a97  mov     rbx, [rbp+var_30]
0x180048a9b  mov     rdx, rbx; unsigned __int16 *
0x180048a9e  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180048aa3  mov     esi, eax
0x180048aa5  test    eax, eax
0x180048aa7  js      loc_180048B39
0x180048aad  mov     rcx, [rbp+hKey]; hKey
0x180048ab1  lea     r8, [rbp+var_28]; this
0x180048ab5  lea     rdx, aProgid; "ProgId"
0x180048abc  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x180048ac1  mov     esi, eax
0x180048ac3  test    eax, eax
0x180048ac5  js      short loc_180048B2B
0x180048ac7  mov     rcx, [rbp+hKey]; hKey
0x180048acb  lea     r8, [rbp+var_10]; this
0x180048acf  lea     rdx, aInitString; "Init String"
0x180048ad6  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x180048adb  mov     esi, eax
0x180048add  test    eax, eax
0x180048adf  js      short loc_180048B2B
0x180048ae1  mov     rcx, [rbp+hKey]; hKey
0x180048ae5  lea     r8, [rbp+var_18]; this
0x180048ae9  lea     rdx, aContainerId; "Container Id"
0x180048af0  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x180048af5  mov     esi, eax
0x180048af7  test    eax, eax
0x180048af9  js      short loc_180048B2B
0x180048afb  mov     rcx, [rbp+hKey]; hKey
0x180048aff  lea     r8, [rbp+Block]; this
0x180048b03  lea     rdx, aResourcePath; "Resource Path"
0x180048b0a  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x180048b0f  mov     esi, eax
0x180048b11  test    eax, eax
0x180048b13  js      short loc_180048B2B
0x180048b15  mov     rcx, [rbp+hKey]; HKEY
0x180048b19  lea     r8, [rbp+arg_10]; unsigned int *
0x180048b1d  lea     rdx, aLifeTime; "Life Time"
0x180048b24  call    ?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; HrRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x180048b29  mov     esi, eax
0x180048b2b  mov     rcx, [rbp+hKey]; hKey
0x180048b2f  call    cs:__imp_RegCloseKey
0x180048b35  mov     rdi, [rbp+var_28]
0x180048b39  mov     rcx, [rbp+var_38]; hKey
0x180048b3d  call    cs:__imp_RegCloseKey
0x180048b43  jmp     short loc_180048B49
0x180048b45  mov     rbx, [rbp+var_30]
0x180048b49  mov     qword ptr [r13+0], 0
0x180048b51  mov     qword ptr [r12], 0
0x180048b59  mov     qword ptr [r14], 0
0x180048b60  mov     qword ptr [r15], 0
0x180048b67  test    esi, esi
0x180048b69  js      loc_180048C05
0x180048b6f  mov     rdx, r13; unsigned __int16 **
0x180048b72  lea     rcx, [rbp+var_28]; this
0x180048b76  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x180048b7b  mov     esi, eax
0x180048b7d  test    eax, eax
0x180048b7f  js      short loc_180048BC2
0x180048b81  mov     rdx, r12; unsigned __int16 **
0x180048b84  lea     rcx, [rbp+var_10]; this
0x180048b88  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x180048b8d  mov     esi, eax
0x180048b8f  test    eax, eax
0x180048b91  js      short loc_180048BC2
0x180048b93  mov     rdx, r14; unsigned __int16 **
0x180048b96  lea     rcx, [rbp+var_18]; this
0x180048b9a  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x180048b9f  mov     esi, eax
0x180048ba1  test    eax, eax
0x180048ba3  js      short loc_180048BC2
0x180048ba5  mov     rdx, r15; unsigned __int16 **
0x180048ba8  lea     rcx, [rbp+Block]; this
0x180048bac  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x180048bb1  mov     esi, eax
0x180048bb3  test    eax, eax
0x180048bb5  js      short loc_180048BC2
0x180048bb7  mov     rcx, [rbp+arg_30]
0x180048bbb  mov     eax, [rbp+arg_10]
0x180048bbe  mov     [rcx], eax
0x180048bc0  jmp     short loc_180048C03
0x180048bc2  mov     rcx, [r12]; pv
0x180048bc6  test    rcx, rcx
0x180048bc9  jz      short loc_180048BD9
0x180048bcb  call    cs:__imp_CoTaskMemFree
0x180048bd1  mov     qword ptr [r12], 0
0x180048bd9  mov     rcx, [r14]; pv
0x180048bdc  test    rcx, rcx
0x180048bdf  jz      short loc_180048BEE
0x180048be1  call    cs:__imp_CoTaskMemFree
0x180048be7  mov     qword ptr [r14], 0
0x180048bee  mov     rcx, [r15]; pv
0x180048bf1  test    rcx, rcx
0x180048bf4  jz      short loc_180048C03
0x180048bf6  call    cs:__imp_CoTaskMemFree
0x180048bfc  mov     qword ptr [r15], 0
0x180048c03  test    esi, esi
0x180048c05  jz      short loc_180048C38
0x180048c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c0e  lea     rax, WPP_GLOBAL_Control
0x180048c15  cmp     rcx, rax
0x180048c18  jz      short loc_180048C38
0x180048c1a  test    byte ptr [rcx+1Ch], 1
0x180048c1e  jz      short loc_180048C38
0x180048c20  mov     rcx, [rcx+10h]
0x180048c24  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x180048c2b  mov     edx, 0Dh
0x180048c30  mov     r9d, esi
0x180048c33  call    WPP_SF_d
0x180048c38  mov     rcx, [rbp+Block]; Block
0x180048c3c  call    cs:__imp_free
0x180048c42  mov     rcx, [rbp+var_18]; Block
0x180048c46  call    cs:__imp_free
0x180048c4c  mov     rcx, [rbp+var_10]; Block
0x180048c50  call    cs:__imp_free
0x180048c56  mov     rcx, rdi; Block
0x180048c59  call    cs:__imp_free
0x180048c5f  mov     rcx, rbx; Block
0x180048c62  call    cs:__imp_free
0x180048c68  mov     eax, esi
0x180048c6a  jmp     short loc_180048C71
0x180048c6c  mov     eax, 80004003h
0x180048c71  mov     rbx, [rsp+60h+arg_0]
0x180048c79  add     rsp, 60h
0x180048c7d  pop     r15
0x180048c7f  pop     r14
0x180048c81  pop     r13
0x180048c83  pop     r12
0x180048c85  pop     rdi
0x180048c86  pop     rsi
0x180048c87  pop     rbp
0x180048c88  retn
```

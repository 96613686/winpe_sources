# WFDMgrQueryDeviceIDAndDriverVersion(_GUID *,ushort *,ulong,ushort *,ulong)

- ea: `0x18007524c`
- end: `0x180075760`
- name: `?WFDMgrQueryDeviceIDAndDriverVersion@@YAKPEAU_GUID@@PEAGK1K@Z`
- size: `1300`
- prototype: `unsigned int(struct _GUID *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180074b8c`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18007524c`
- `0x180106340`
- `0x180107318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800755a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007567e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800756ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800755a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007567e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800756ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800754d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007551a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800754d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007551a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800754e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007555e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800754e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007555e`
- `RPCRT4!UuidFromStringW` at `0x180075571`
- `RPCRT4!UuidFromStringW` at `0x180075571`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180075410`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18007543e`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180075410`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18007543e`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18007546c`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18007546c`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180075499`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180075499`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800756fe`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800756fe`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800753dd`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800753dd`
- `DEVOBJ!DevObjGetClassDevs` at `0x18007536f`
- `DEVOBJ!DevObjGetClassDevs` at `0x18007536f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800752fa`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800752fa`

## pseudocode

```c
__int64 __fastcall WFDMgrQueryDeviceIDAndDriverVersion(
        struct _GUID *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  __int64 DeviceInfoList; // rax
  __int64 v8; // rsi
  DWORD LastError; // eax
  unsigned int v10; // edi
  PVOID *v11; // rcx
  DWORD v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int i; // r14d
  HKEY v16; // rbx
  unsigned int v17; // eax
  __int64 v18; // rax
  DWORD v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rbx
  unsigned __int64 v23; // rbx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD lpcbData; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v27; // [rsp+48h] [rbp-B8h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v29[3]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 StringUuid[39]; // [rsp+92h] [rbp-6Eh] BYREF
  BYTE Src[512]; // [rsp+2E0h] [rbp+1E0h] BYREF
  BYTE lpData[512]; // [rsp+4E0h] [rbp+3E0h] BYREF

  memset(v29, 0, sizeof(v29));
  cbData = 0;
  v27 = 0;
  lpcbData = 0;
  Uuid = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 705, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
  }
  *a2 = 0;
  *a4 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(&GUID_DEVCLASS_NET, 0, 0, 0, 0);
  v8 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v10 = LastError;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 706, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, LastError);
        goto LABEL_58;
      }
      goto LABEL_59;
    }
    return v10;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_NET, 0, 2, 0, 0) )
  {
    v12 = GetLastError();
    v10 = v12;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v14 = 707;
LABEL_15:
      WPP_SF_d(v13[12], v14, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, v12);
    }
    goto LABEL_57;
  }
  LODWORD(v29[0]) = 48;
  for ( i = 0; ; ++i )
  {
    if ( !(unsigned int)DevObjEnumDeviceInfo(v8, i, v29) )
      goto LABEL_56;
    cbData = 256;
    if ( !(unsigned int)DevObjGetDeviceRegistryProperty(v8, v29, 12)
      && !(unsigned int)DevObjGetDeviceRegistryProperty(v8, v29, 0) )
    {
      v19 = GetLastError();
      v10 = v19;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v21 = 708;
LABEL_54:
        WPP_SF_d(v20[12], v21, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, v19);
      }
LABEL_55:
      if ( v10 )
        goto LABEL_57;
LABEL_56:
      v10 = 1168;
      goto LABEL_57;
    }
    cbData = 256;
    if ( !(unsigned int)DevObjGetDeviceInstanceId(v8, v29, Src, 256, &v27) )
    {
      v19 = GetLastError();
      v10 = v19;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v21 = 709;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
    v16 = (HKEY)DevObjOpenDevRegKey(v8, v29, 1);
    if ( v16 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v19 = GetLastError();
      v10 = v19;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v21 = 710;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
    cbData = 78;
    if ( RegQueryValueExW(v16, L"NetCfgInstanceId", 0, 0, Data, &cbData) )
    {
      RegCloseKey(v16);
      continue;
    }
    lpcbData = 512;
    v17 = RegQueryValueExW(v16, L"DriverVersion", 0, 0, lpData, &lpcbData);
    if ( v17
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 711, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, v17);
    }
    RegCloseKey(v16);
    StringUuid[36] = 0;
    v12 = UuidFromStringW(StringUuid, &Uuid);
    v10 = v12;
    if ( v12 )
      break;
    v18 = *(_QWORD *)&Uuid.Data1 - *(_QWORD *)&a1->Data1;
    if ( *(_QWORD *)&Uuid.Data1 == *(_QWORD *)&a1->Data1 )
      v18 = *(_QWORD *)Uuid.Data4 - *(_QWORD *)a1->Data4;
    if ( !v18 )
    {
      if ( v27 >= 0x101 || (v22 = v27, memcpy_0(a2, Src, v22 * 2), a2[v22] = 0, (lpcbData & 0xFFFFFFFE) >= 0x202) )
      {
        v10 = 8;
      }
      else
      {
        v23 = lpcbData;
        memcpy_0(a4, lpData, lpcbData);
        a4[v23 >> 1] = 0;
      }
      goto LABEL_57;
    }
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    v14 = 712;
    goto LABEL_15;
  }
LABEL_57:
  DevObjDestroyDeviceInfoList(v8);
LABEL_58:
  v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_59:
  if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 105) >= 4u && (*((_BYTE *)v11 + 108) & 1) != 0 )
    WPP_SF_d(v11[12], 713, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18007524c  mov     [rsp-8+arg_0], rbx
0x180075251  push    rbp
0x180075252  push    rsi
0x180075253  push    rdi
0x180075254  push    r12
0x180075256  push    r13
0x180075258  push    r14
0x18007525a  push    r15
0x18007525c  lea     rbp, [rsp-5F0h]
0x180075264  sub     rsp, 6F0h
0x18007526b  mov     rax, cs:__security_cookie
0x180075272  xor     rax, rsp
0x180075275  mov     [rbp+620h+var_40], rax
0x18007527c  xorps   xmm0, xmm0
0x18007527f  xor     edi, edi
0x180075281  movups  [rsp+720h+var_6C0], xmm0
0x180075286  mov     [rsp+720h+cbData], edi
0x18007528a  mov     r15, r9
0x18007528d  movups  [rsp+720h+var_6B0], xmm0
0x180075292  mov     [rsp+720h+var_6D8], edi
0x180075296  mov     r12, rdx
0x180075299  movups  [rbp+620h+var_6A0], xmm0
0x18007529d  mov     [rsp+720h+var_6DC], edi
0x1800752a1  mov     r13, rcx
0x1800752a4  movups  xmmword ptr [rsp+720h+Uuid.Data1], xmm0
0x1800752a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800752b0  lea     rbx, WPP_GLOBAL_Control
0x1800752b7  cmp     rcx, rbx
0x1800752ba  jz      short loc_1800752DD
0x1800752bc  cmp     byte ptr [rcx+69h], 4
0x1800752c0  jb      short loc_1800752DD
0x1800752c2  test    byte ptr [rcx+6Ch], 1
0x1800752c6  jz      short loc_1800752DD
0x1800752c8  mov     rcx, [rcx+60h]
0x1800752cc  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1800752d3  mov     edx, 2C1h
0x1800752d8  call    WPP_SF_
0x1800752dd  mov     [r12], di
0x1800752e2  lea     rcx, GUID_DEVCLASS_NET
0x1800752e9  xor     r9d, r9d
0x1800752ec  mov     [r15], di
0x1800752f0  xor     r8d, r8d
0x1800752f3  mov     [rsp+720h+lpData], rdi
0x1800752f8  xor     edx, edx
0x1800752fa  call    cs:__imp_DevObjCreateDeviceInfoList
0x180075300  mov     rsi, rax
0x180075303  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180075307  jnz     short loc_180075352
0x180075309  call    cs:__imp_GetLastError
0x18007530f  mov     edi, eax
0x180075311  mov     rcx, cs:WPP_GLOBAL_Control
0x180075318  cmp     rcx, rbx
0x18007531b  jz      loc_180075734
0x180075321  cmp     byte ptr [rcx+69h], 1
0x180075325  jb      loc_18007570B
0x18007532b  test    byte ptr [rcx+6Ch], 1
0x18007532f  jz      loc_18007570B
0x180075335  mov     rcx, [rcx+60h]
0x180075339  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180075340  mov     edx, 2C2h
0x180075345  mov     r9d, eax
0x180075348  call    WPP_SF_d
0x18007534d  jmp     loc_180075704
0x180075352  mov     [rsp+720h+lpcbData], rdi
0x180075357  lea     rdx, GUID_DEVCLASS_NET
0x18007535e  mov     r9d, 2
0x180075364  mov     [rsp+720h+lpData], rdi
0x180075369  xor     r8d, r8d
0x18007536c  mov     rcx, rsi
0x18007536f  call    cs:__imp_DevObjGetClassDevs
0x180075375  test    eax, eax
0x180075377  jnz     short loc_1800753C2
0x180075379  call    cs:__imp_GetLastError
0x18007537f  mov     edi, eax
0x180075381  mov     rcx, cs:WPP_GLOBAL_Control
0x180075388  cmp     rcx, rbx
0x18007538b  jz      loc_1800756FB
0x180075391  cmp     byte ptr [rcx+69h], 1
0x180075395  jb      loc_1800756FB
0x18007539b  test    byte ptr [rcx+6Ch], 1
0x18007539f  jz      loc_1800756FB
0x1800753a5  mov     edx, 2C3h
0x1800753aa  mov     rcx, [rcx+60h]
0x1800753ae  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1800753b5  mov     r9d, eax
0x1800753b8  call    WPP_SF_d
0x1800753bd  jmp     loc_1800756FB
0x1800753c2  mov     dword ptr [rsp+720h+var_6C0], 30h ; '0'
0x1800753ca  mov     r14d, edi
0x1800753cd  lea     r8, [rsp+720h+var_6C0]
0x1800753d2  mov     edx, r14d
0x1800753d5  mov     rcx, rsi
0x1800753d8  mov     ebx, 100h
0x1800753dd  call    cs:__imp_DevObjEnumDeviceInfo
0x1800753e3  test    eax, eax
0x1800753e5  jz      loc_1800756EF
0x1800753eb  xor     r9d, r9d
0x1800753ee  mov     [rsp+720h+var_6F0], rdi
0x1800753f3  lea     rax, [rbp+620h+var_640]
0x1800753f7  mov     dword ptr [rsp+720h+lpcbData], ebx
0x1800753fb  lea     rdx, [rsp+720h+var_6C0]
0x180075400  mov     [rsp+720h+cbData], ebx
0x180075404  mov     rcx, rsi
0x180075407  mov     [rsp+720h+lpData], rax
0x18007540c  lea     r8d, [r9+0Ch]
0x180075410  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180075416  test    eax, eax
0x180075418  jnz     short loc_18007544C
0x18007541a  mov     eax, [rsp+720h+cbData]
0x18007541e  lea     rdx, [rsp+720h+var_6C0]
0x180075423  mov     [rsp+720h+var_6F0], rdi
0x180075428  xor     r9d, r9d
0x18007542b  mov     dword ptr [rsp+720h+lpcbData], eax
0x18007542f  xor     r8d, r8d
0x180075432  lea     rax, [rbp+620h+var_640]
0x180075436  mov     rcx, rsi
0x180075439  mov     [rsp+720h+lpData], rax
0x18007543e  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180075444  test    eax, eax
0x180075446  jz      loc_1800755A4
0x18007544c  lea     rax, [rsp+720h+var_6D8]
0x180075451  mov     [rsp+720h+cbData], ebx
0x180075455  mov     r9d, ebx
0x180075458  mov     [rsp+720h+lpData], rax
0x18007545d  lea     r8, [rbp+620h+Src]
0x180075464  mov     rcx, rsi
0x180075467  lea     rdx, [rsp+720h+var_6C0]
0x18007546c  call    cs:__imp_DevObjGetDeviceInstanceId
0x180075472  test    eax, eax
0x180075474  jz      loc_1800756AC
0x18007547a  xor     r9d, r9d
0x18007547d  mov     dword ptr [rsp+720h+lpcbData], 20019h
0x180075485  lea     rdx, [rsp+720h+var_6C0]
0x18007548a  mov     dword ptr [rsp+720h+lpData], 2
0x180075492  mov     rcx, rsi
0x180075495  lea     r8d, [r9+1]
0x180075499  call    cs:__imp_DevObjOpenDevRegKey
0x18007549f  mov     rbx, rax
0x1800754a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800754a6  jz      loc_18007567E
0x1800754ac  lea     rax, [rsp+720h+cbData]
0x1800754b1  mov     [rsp+720h+cbData], 4Eh ; 'N'
0x1800754b9  mov     [rsp+720h+lpcbData], rax; lpcbData
0x1800754be  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x1800754c5  lea     rax, [rbp+620h+Data]
0x1800754c9  xor     r9d, r9d; lpType
0x1800754cc  xor     r8d, r8d; lpReserved
0x1800754cf  mov     [rsp+720h+lpData], rax; lpData
0x1800754d4  mov     rcx, rbx; hKey
0x1800754d7  call    cs:__imp_RegQueryValueExW
0x1800754dd  mov     rcx, rbx; hKey
0x1800754e0  test    eax, eax
0x1800754e2  jz      short loc_1800754EF
0x1800754e4  call    cs:__imp_RegCloseKey
0x1800754ea  jmp     loc_18007559C
0x1800754ef  lea     rax, [rsp+720h+var_6DC]
0x1800754f4  mov     [rsp+720h+var_6DC], 200h
0x1800754fc  mov     [rsp+720h+lpcbData], rax; lpcbData
0x180075501  lea     rdx, aDriverversion; "DriverVersion"
0x180075508  lea     rax, [rbp+620h+var_240]
0x18007550f  xor     r9d, r9d; lpType
0x180075512  xor     r8d, r8d; lpReserved
0x180075515  mov     [rsp+720h+lpData], rax; lpData
0x18007551a  call    cs:__imp_RegQueryValueExW
0x180075520  test    eax, eax
0x180075522  jz      short loc_18007555B
0x180075524  mov     rcx, cs:WPP_GLOBAL_Control
0x18007552b  lea     rdx, WPP_GLOBAL_Control
0x180075532  cmp     rcx, rdx
0x180075535  jz      short loc_18007555B
0x180075537  cmp     byte ptr [rcx+69h], 1
0x18007553b  jb      short loc_18007555B
0x18007553d  test    byte ptr [rcx+6Ch], 1
0x180075541  jz      short loc_18007555B
0x180075543  mov     rcx, [rcx+60h]
0x180075547  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x18007554e  mov     edx, 2C7h
0x180075553  mov     r9d, eax
0x180075556  call    WPP_SF_d
0x18007555b  mov     rcx, rbx; hKey
0x18007555e  call    cs:__imp_RegCloseKey
0x180075564  lea     rdx, [rsp+720h+Uuid]; Uuid
0x180075569  mov     [rbp+620h+var_646], di
0x18007556d  lea     rcx, [rbp+620h+StringUuid]; StringUuid
0x180075571  call    cs:__imp_UuidFromStringW
0x180075577  mov     edi, eax
0x180075579  test    eax, eax
0x18007557b  jnz     loc_180075649
0x180075581  mov     rax, qword ptr [rsp+720h+Uuid.Data1]
0x180075586  sub     rax, [r13+0]
0x18007558a  jnz     short loc_180075595
0x18007558c  mov     rax, qword ptr [rsp+720h+Uuid.Data4]
0x180075591  sub     rax, [r13+8]
0x180075595  test    rax, rax
0x180075598  jz      short loc_1800755E1
0x18007559a  xor     edi, edi
0x18007559c  inc     r14d
0x18007559f  jmp     loc_1800753CD
0x1800755a4  call    cs:__imp_GetLastError
0x1800755aa  mov     edi, eax
0x1800755ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800755b3  lea     rbx, WPP_GLOBAL_Control
0x1800755ba  cmp     rcx, rbx
0x1800755bd  jz      loc_1800756EB
0x1800755c3  cmp     byte ptr [rcx+69h], 1
0x1800755c7  jb      loc_1800756EB
0x1800755cd  test    byte ptr [rcx+6Ch], 1
0x1800755d1  jz      loc_1800756EB
0x1800755d7  mov     edx, 2C4h
0x1800755dc  jmp     loc_1800756D8
0x1800755e1  cmp     [rsp+720h+var_6D8], 101h
0x1800755e9  jnb     short loc_18007563F
0x1800755eb  mov     eax, [rsp+720h+var_6D8]
0x1800755ef  lea     rdx, [rbp+620h+Src]; Src
0x1800755f6  mov     rcx, r12; void *
0x1800755f9  lea     rbx, [rax+rax]
0x1800755fd  mov     r8, rbx; Size
0x180075600  call    memcpy_0
0x180075605  xor     eax, eax
0x180075607  mov     [rbx+r12], ax
0x18007560c  mov     eax, [rsp+720h+var_6DC]
0x180075610  and     eax, 0FFFFFFFEh
0x180075613  cmp     eax, 202h
0x180075618  jnb     short loc_18007563F
0x18007561a  mov     ebx, [rsp+720h+var_6DC]
0x18007561e  lea     rdx, [rbp+620h+var_240]; Src
0x180075625  mov     r8d, ebx; Size
0x180075628  mov     rcx, r15; void *
0x18007562b  call    memcpy_0
0x180075630  shr     rbx, 1
0x180075633  xor     eax, eax
0x180075635  mov     [r15+rbx*2], ax
0x18007563a  jmp     loc_1800756F4
0x18007563f  mov     edi, 8
0x180075644  jmp     loc_1800756F4
0x180075649  mov     rcx, cs:WPP_GLOBAL_Control
0x180075650  lea     rbx, WPP_GLOBAL_Control
0x180075657  cmp     rcx, rbx
0x18007565a  jz      loc_1800756FB
0x180075660  cmp     byte ptr [rcx+69h], 1
0x180075664  jb      loc_1800756FB
0x18007566a  test    byte ptr [rcx+6Ch], 1
0x18007566e  jz      loc_1800756FB
0x180075674  mov     edx, 2C8h
0x180075679  jmp     loc_1800753AA
0x18007567e  call    cs:__imp_GetLastError
0x180075684  mov     edi, eax
0x180075686  mov     rcx, cs:WPP_GLOBAL_Control
0x18007568d  lea     rbx, WPP_GLOBAL_Control
0x180075694  cmp     rcx, rbx
0x180075697  jz      short loc_1800756EB
0x180075699  cmp     byte ptr [rcx+69h], 1
0x18007569d  jb      short loc_1800756EB
0x18007569f  test    byte ptr [rcx+6Ch], 1
0x1800756a3  jz      short loc_1800756EB
0x1800756a5  mov     edx, 2C6h
0x1800756aa  jmp     short loc_1800756D8
0x1800756ac  call    cs:__imp_GetLastError
0x1800756b2  mov     edi, eax
0x1800756b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800756bb  lea     rbx, WPP_GLOBAL_Control
0x1800756c2  cmp     rcx, rbx
0x1800756c5  jz      short loc_1800756EB
0x1800756c7  cmp     byte ptr [rcx+69h], 1
0x1800756cb  jb      short loc_1800756EB
0x1800756cd  test    byte ptr [rcx+6Ch], 1
0x1800756d1  jz      short loc_1800756EB
0x1800756d3  mov     edx, 2C5h
0x1800756d8  mov     rcx, [rcx+60h]
0x1800756dc  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1800756e3  mov     r9d, eax
0x1800756e6  call    WPP_SF_d
0x1800756eb  test    edi, edi
0x1800756ed  jnz     short loc_1800756FB
0x1800756ef  mov     edi, 490h
0x1800756f4  lea     rbx, WPP_GLOBAL_Control
0x1800756fb  mov     rcx, rsi
0x1800756fe  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180075704  mov     rcx, cs:WPP_GLOBAL_Control
0x18007570b  cmp     rcx, rbx
0x18007570e  jz      short loc_180075734
0x180075710  cmp     byte ptr [rcx+69h], 4
0x180075714  jb      short loc_180075734
0x180075716  test    byte ptr [rcx+6Ch], 1
0x18007571a  jz      short loc_180075734
0x18007571c  mov     rcx, [rcx+60h]
0x180075720  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180075727  mov     edx, 2C9h
0x18007572c  mov     r9d, edi
0x18007572f  call    WPP_SF_d
0x180075734  mov     eax, edi
0x180075736  mov     rcx, [rbp+620h+var_40]
0x18007573d  xor     rcx, rsp; StackCookie
0x180075740  call    __security_check_cookie
0x180075745  mov     rbx, [rsp+720h+arg_0]
0x18007574d  add     rsp, 6F0h
0x180075754  pop     r15
0x180075756  pop     r14
0x180075758  pop     r13
0x18007575a  pop     r12
  ... truncated ...
```

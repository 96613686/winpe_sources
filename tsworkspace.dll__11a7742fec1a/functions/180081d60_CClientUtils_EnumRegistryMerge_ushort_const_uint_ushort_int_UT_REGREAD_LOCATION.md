# CClientUtils::EnumRegistryMerge(ushort const *,uint,ushort *,int *,UT_REGREAD_LOCATION *)

- ea: `0x180081d60`
- end: `0x180082264`
- name: `?EnumRegistryMerge@CClientUtils@@UEAAHPEBGIPEAGPEAHPEAW4UT_REGREAD_LOCATION@@@Z`
- size: `1284`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *, int *, enum UT_REGREAD_LOCATION *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ece0`
- `0x180020bf0`
- `0x18004f09c`
- `0x180081d60`
- `0x1800824b4`
- `0x180084634`
- `0x180087938`
- `0x180087b50`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18008209e`
- `ADVAPI32!RegCloseKey` at `0x180082239`
- `ADVAPI32!RegCloseKey` at `0x18008209e`
- `ADVAPI32!RegCloseKey` at `0x180082239`
- `ADVAPI32!RegEnumKeyExW` at `0x18008204c`
- `ADVAPI32!RegEnumKeyExW` at `0x18008204c`
- `ADVAPI32!RegOpenKeyExW` at `0x180081e82`
- `ADVAPI32!RegOpenKeyExW` at `0x180081efc`
- `ADVAPI32!RegOpenKeyExW` at `0x180081f7a`
- `ADVAPI32!RegOpenKeyExW` at `0x18008211d`
- `ADVAPI32!RegOpenKeyExW` at `0x180081e82`
- `ADVAPI32!RegOpenKeyExW` at `0x180081efc`
- `ADVAPI32!RegOpenKeyExW` at `0x180081f7a`
- `ADVAPI32!RegOpenKeyExW` at `0x18008211d`

## string_xrefs

- `0x180081e38`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::EnumRegistryMerge(
        CClientUtils *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4,
        DWORD *a5,
        enum UT_REGREAD_LOCATION *a6)
{
  WCHAR *v8; // rdi
  unsigned int v9; // ebx
  int v10; // r15d
  int AppContainerRegistryLocation; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v13; // edi
  unsigned int v14; // eax
  LSTATUS v15; // edi
  unsigned int v16; // eax
  LSTATUS v17; // edi
  PVOID *v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // edx
  HKEY *v22; // rsi
  HKEY v23; // rcx
  DWORD v24; // edx
  LSTATUS v25; // edi
  unsigned int v26; // eax
  __int64 v27; // r8
  LSTATUS v28; // edi
  unsigned int v29; // eax
  __int64 v30; // r8
  bool v31; // zf
  LSTATUS v32; // edi
  PVOID *v33; // rcx
  unsigned int v34; // eax
  unsigned int v35; // eax
  LPWSTR lpClass; // [rsp+28h] [rbp-D8h]
  LPWSTR lpClassa; // [rsp+28h] [rbp-D8h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v40; // [rsp+48h] [rbp-B8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  enum UT_REGREAD_LOCATION *v43; // [rsp+60h] [rbp-A0h]
  WCHAR SubKey[272]; // [rsp+70h] [rbp-90h] BYREF

  v43 = a6;
  v40 = a4;
  v8 = a4;
  ftLastWriteTime = 0;
  hKey = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  v9 = 1;
  v10 = 2;
  if ( !a3 )
  {
    *((_BYTE *)this + 68) = 0;
    *((_DWORD *)this + 16) = 0;
    if ( !(unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
      goto LABEL_13;
    AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
    if ( AppContainerRegistryLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          AppContainerRegistryLocation);
      }
      goto LABEL_50;
    }
    v13 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, (PHKEY)this + 7);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        v14,
        (__int64)SubKey,
        v13);
    }
    if ( v13 )
    {
LABEL_13:
      v15 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, (PHKEY)this + 7);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(lpClass) = v15;
        WPP_SF_DSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          v16,
          (__int64)SubKey,
          lpClass);
      }
      if ( v15 )
      {
        *((_BYTE *)this + 68) = 1;
        v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)this + 7);
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(lpClass) = v17;
          WPP_SF_DSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
            v19,
            (__int64)SubKey,
            lpClass);
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v17 )
        {
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 3u )
          {
            v20 = RdpWppGetCurrentThreadActivityIdPrefix();
            v21 = 39;
LABEL_49:
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v21,
              (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
              v20,
              (__int64)SubKey);
          }
          goto LABEL_50;
        }
      }
    }
    v8 = v40;
  }
  v22 = (HKEY *)((char *)this + 56);
  do
  {
    v23 = *v22;
    v24 = a3 - *((_DWORD *)this + 16);
    cchName = *a5;
    v25 = RegEnumKeyExW(v23, v24, v8, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v35 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids, v35);
      }
      *a5 = cchName;
      v10 = *((_BYTE *)this + 68) != 0;
      goto LABEL_56;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v27, v26, v25);
    }
    v28 = RegCloseKey(*v22);
    if ( v28
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v30, v29, v28);
    }
    v31 = *((_BYTE *)this + 68) == 0;
    *v22 = 0;
    if ( !v31 )
      goto LABEL_50;
    *((_BYTE *)this + 68) = 1;
    *((_DWORD *)this + 16) = a3;
    v32 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)this + 7);
    v33 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v34 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(lpClassa) = v32;
      WPP_SF_DSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        v34,
        (__int64)SubKey,
        lpClassa);
      v33 = (PVOID *)WPP_GLOBAL_Control;
    }
    v31 = v32 == 0;
    v8 = v40;
  }
  while ( v31 );
  if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 3u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 44;
    goto LABEL_49;
  }
LABEL_50:
  v9 = 0;
LABEL_56:
  *(_DWORD *)v43 = v10;
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180081d60  push    rbp
0x180081d62  push    rbx
0x180081d63  push    rsi
0x180081d64  push    rdi
0x180081d65  push    r12
0x180081d67  push    r13
0x180081d69  push    r14
0x180081d6b  push    r15
0x180081d6d  lea     rbp, [rsp-1A8h]
0x180081d75  sub     rsp, 2A8h
0x180081d7c  mov     rax, cs:__security_cookie
0x180081d83  xor     rax, rsp
0x180081d86  mov     [rbp+1E0h+var_50], rax
0x180081d8d  mov     rax, [rbp+1E0h+arg_28]
0x180081d94  mov     r13d, r8d
0x180081d97  mov     r12, [rbp+1E0h+arg_20]
0x180081d9e  mov     r14, rcx
0x180081da1  mov     r8, rdx; unsigned __int16 *
0x180081da4  mov     [rsp+2E0h+var_280], rax
0x180081da9  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x180081dae  mov     [rsp+2E0h+var_298], r9
0x180081db3  mov     rdi, r9
0x180081db6  mov     qword ptr [rsp+2E0h+ftLastWriteTime.dwLowDateTime], 0
0x180081dbf  mov     [rsp+2E0h+hKey], 0
0x180081dc8  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x180081dcd  mov     ebx, 1
0x180081dd2  lea     r15d, [rbx+1]
0x180081dd6  test    r13d, r13d
0x180081dd9  jnz     loc_180082014
0x180081ddf  lea     rsi, [r14+38h]
0x180081de3  mov     [r14+44h], r13b
0x180081de7  mov     [rsi+8], r13d
0x180081deb  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x180081df0  test    eax, eax
0x180081df2  jz      loc_180081EE2
0x180081df8  lea     rcx, [rsp+2E0h+hKey]; HKEY *
0x180081dfd  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x180081e02  mov     edi, eax
0x180081e04  test    eax, eax
0x180081e06  jns     short loc_180081E6A
0x180081e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180081e0f  lea     rdx, WPP_GLOBAL_Control
0x180081e16  cmp     rcx, rdx
0x180081e19  jz      loc_1800821CE
0x180081e1f  test    byte ptr [rcx+1Ch], 8
0x180081e23  jz      loc_1800821CE
0x180081e29  cmp     [rcx+19h], r15b
0x180081e2d  jb      loc_1800821CE
0x180081e33  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081e38  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x180081e3f  mov     dword ptr [rsp+2E0h+lpClass], edi
0x180081e43  mov     [rsp+2E0h+phkResult], rcx
0x180081e48  lea     edx, [rbx+22h]
0x180081e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180081e52  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180081e59  mov     r9d, eax
0x180081e5c  mov     rcx, [rcx+10h]
0x180081e60  call    WPP_SF_DsD
0x180081e65  jmp     loc_1800821CE
0x180081e6a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180081e6f  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x180081e74  mov     r9d, 20019h; samDesired
0x180081e7a  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x180081e7f  xor     r8d, r8d; ulOptions
0x180081e82  call    cs:__imp_RegOpenKeyExW
0x180081e88  mov     edi, eax
0x180081e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180081e91  lea     rdx, WPP_GLOBAL_Control
0x180081e98  cmp     rcx, rdx
0x180081e9b  jz      short loc_180081EDA
0x180081e9d  test    [rcx+1Ch], bl
0x180081ea0  jz      short loc_180081EDA
0x180081ea2  cmp     byte ptr [rcx+19h], 4
0x180081ea6  jb      short loc_180081EDA
0x180081ea8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081ead  lea     rcx, [rsp+2E0h+SubKey]
0x180081eb2  mov     dword ptr [rsp+2E0h+lpClass], edi
0x180081eb6  mov     [rsp+2E0h+phkResult], rcx
0x180081ebb  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180081ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180081ec9  mov     edx, 24h ; '$'
0x180081ece  mov     r9d, eax
0x180081ed1  mov     rcx, [rcx+10h]
0x180081ed5  call    WPP_SF_DSD
0x180081eda  test    edi, edi
0x180081edc  jz      loc_18008200F
0x180081ee2  mov     r9d, 20019h; samDesired
0x180081ee8  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x180081eed  xor     r8d, r8d; ulOptions
0x180081ef0  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x180081ef5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180081efc  call    cs:__imp_RegOpenKeyExW
0x180081f02  mov     edi, eax
0x180081f04  mov     rcx, cs:WPP_GLOBAL_Control
0x180081f0b  lea     rax, WPP_GLOBAL_Control
0x180081f12  cmp     rcx, rax
0x180081f15  jz      short loc_180081F54
0x180081f17  test    [rcx+1Ch], bl
0x180081f1a  jz      short loc_180081F54
0x180081f1c  cmp     byte ptr [rcx+19h], 4
0x180081f20  jb      short loc_180081F54
0x180081f22  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081f27  lea     rcx, [rsp+2E0h+SubKey]
0x180081f2c  mov     dword ptr [rsp+2E0h+lpClass], edi
0x180081f30  mov     [rsp+2E0h+phkResult], rcx
0x180081f35  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180081f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180081f43  mov     edx, 25h ; '%'
0x180081f48  mov     r9d, eax
0x180081f4b  mov     rcx, [rcx+10h]
0x180081f4f  call    WPP_SF_DSD
0x180081f54  test    edi, edi
0x180081f56  jz      loc_18008200F
0x180081f5c  mov     r9d, 20019h; samDesired
0x180081f62  mov     [r14+44h], bl
0x180081f66  xor     r8d, r8d; ulOptions
0x180081f69  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x180081f6e  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x180081f73  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081f7a  call    cs:__imp_RegOpenKeyExW
0x180081f80  mov     edi, eax
0x180081f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180081f89  lea     rax, WPP_GLOBAL_Control
0x180081f90  cmp     rcx, rax
0x180081f93  jz      short loc_180081FE0
0x180081f95  test    [rcx+1Ch], bl
0x180081f98  jz      short loc_180081FE0
0x180081f9a  cmp     byte ptr [rcx+19h], 4
0x180081f9e  jb      short loc_180081FE0
0x180081fa0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081fa5  lea     rcx, [rsp+2E0h+SubKey]
0x180081faa  mov     dword ptr [rsp+2E0h+lpClass], edi
0x180081fae  mov     [rsp+2E0h+phkResult], rcx
0x180081fb3  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180081fba  mov     rcx, cs:WPP_GLOBAL_Control
0x180081fc1  mov     edx, 26h ; '&'
0x180081fc6  mov     r9d, eax
0x180081fc9  mov     rcx, [rcx+10h]
0x180081fcd  call    WPP_SF_DSD
0x180081fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180081fd9  lea     rax, WPP_GLOBAL_Control
0x180081fe0  test    edi, edi
0x180081fe2  jz      short loc_18008200F
0x180081fe4  cmp     rcx, rax
0x180081fe7  jz      loc_1800821CE
0x180081fed  test    [rcx+1Ch], bl
0x180081ff0  jz      loc_1800821CE
0x180081ff6  cmp     byte ptr [rcx+19h], 3
0x180081ffa  jb      loc_1800821CE
0x180082000  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180082005  mov     edx, 27h ; '''
0x18008200a  jmp     loc_1800821AA
0x18008200f  mov     rdi, [rsp+2E0h+var_298]
0x180082014  lea     rsi, [r14+38h]
0x180082018  mov     eax, [r12]
0x18008201c  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180082021  mov     rcx, [rsi]; hKey
0x180082024  mov     edx, r13d
0x180082027  sub     edx, [rsi+8]; dwIndex
0x18008202a  mov     r8, rdi; lpName
0x18008202d  mov     [rsp+2E0h+cchName], eax
0x180082031  lea     rax, [rsp+2E0h+ftLastWriteTime]
0x180082036  mov     [rsp+2E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18008203b  xor     eax, eax
0x18008203d  mov     [rsp+2E0h+lpcchClass], rax; lpcchClass
0x180082042  mov     [rsp+2E0h+lpClass], rax; lpClass
0x180082047  mov     [rsp+2E0h+phkResult], rax; lpReserved
0x18008204c  call    cs:__imp_RegEnumKeyExW
0x180082052  mov     edi, eax
0x180082054  test    eax, eax
0x180082056  jz      loc_1800821D2
0x18008205c  mov     rcx, cs:WPP_GLOBAL_Control
0x180082063  lea     rax, WPP_GLOBAL_Control
0x18008206a  cmp     rcx, rax
0x18008206d  jz      short loc_18008209B
0x18008206f  test    [rcx+1Ch], bl
0x180082072  jz      short loc_18008209B
0x180082074  cmp     byte ptr [rcx+19h], 4
0x180082078  jb      short loc_18008209B
0x18008207a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008207f  mov     rcx, cs:WPP_GLOBAL_Control
0x180082086  mov     edx, 29h ; ')'
0x18008208b  mov     r9d, eax
0x18008208e  mov     dword ptr [rsp+2E0h+phkResult], edi
0x180082092  mov     rcx, [rcx+10h]
0x180082096  call    WPP_SF_Dl
0x18008209b  mov     rcx, [rsi]; hKey
0x18008209e  call    cs:__imp_RegCloseKey
0x1800820a4  mov     edi, eax
0x1800820a6  test    eax, eax
0x1800820a8  jz      short loc_1800820E9
0x1800820aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800820b1  lea     rax, WPP_GLOBAL_Control
0x1800820b8  cmp     rcx, rax
0x1800820bb  jz      short loc_1800820E9
0x1800820bd  test    [rcx+1Ch], bl
0x1800820c0  jz      short loc_1800820E9
0x1800820c2  cmp     [rcx+19h], r15b
0x1800820c6  jb      short loc_1800820E9
0x1800820c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800820cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800820d4  mov     edx, 2Ah ; '*'
0x1800820d9  mov     r9d, eax
0x1800820dc  mov     dword ptr [rsp+2E0h+phkResult], edi
0x1800820e0  mov     rcx, [rcx+10h]
0x1800820e4  call    WPP_SF_Dl
0x1800820e9  cmp     byte ptr [r14+44h], 0
0x1800820ee  mov     qword ptr [rsi], 0
0x1800820f5  jnz     loc_1800821CE
0x1800820fb  mov     r9d, 20019h; samDesired
0x180082101  mov     [r14+44h], bl
0x180082105  xor     r8d, r8d; ulOptions
0x180082108  mov     [r14+40h], r13d
0x18008210c  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x180082111  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x180082116  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008211d  call    cs:__imp_RegOpenKeyExW
0x180082123  mov     edi, eax
0x180082125  mov     rcx, cs:WPP_GLOBAL_Control
0x18008212c  lea     rax, WPP_GLOBAL_Control
0x180082133  cmp     rcx, rax
0x180082136  jz      short loc_180082183
0x180082138  test    [rcx+1Ch], bl
0x18008213b  jz      short loc_180082183
0x18008213d  cmp     byte ptr [rcx+19h], 4
0x180082141  jb      short loc_180082183
0x180082143  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180082148  lea     rcx, [rsp+2E0h+SubKey]
0x18008214d  mov     dword ptr [rsp+2E0h+lpClass], edi
0x180082151  mov     [rsp+2E0h+phkResult], rcx
0x180082156  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x18008215d  mov     rcx, cs:WPP_GLOBAL_Control
0x180082164  mov     edx, 2Bh ; '+'
0x180082169  mov     r9d, eax
0x18008216c  mov     rcx, [rcx+10h]
0x180082170  call    WPP_SF_DSD
0x180082175  mov     rcx, cs:WPP_GLOBAL_Control
0x18008217c  lea     rax, WPP_GLOBAL_Control
0x180082183  test    edi, edi
0x180082185  mov     rdi, [rsp+2E0h+var_298]
0x18008218a  jz      loc_180082018
0x180082190  cmp     rcx, rax
0x180082193  jz      short loc_1800821CE
0x180082195  test    [rcx+1Ch], bl
0x180082198  jz      short loc_1800821CE
0x18008219a  cmp     byte ptr [rcx+19h], 3
0x18008219e  jb      short loc_1800821CE
0x1800821a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800821a5  mov     edx, 2Ch ; ','
0x1800821aa  lea     rcx, [rsp+2E0h+SubKey]
0x1800821af  mov     r9d, eax
0x1800821b2  mov     [rsp+2E0h+phkResult], rcx
0x1800821b7  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1800821be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800821c5  mov     rcx, [rcx+10h]
0x1800821c9  call    WPP_SF_DS
0x1800821ce  xor     ebx, ebx
0x1800821d0  jmp     short loc_180082227
0x1800821d2  mov     rax, cs:WPP_GLOBAL_Control
0x1800821d9  lea     rdx, WPP_GLOBAL_Control
0x1800821e0  cmp     rax, rdx
0x1800821e3  jz      short loc_180082214
0x1800821e5  test    [rax+1Ch], bl
0x1800821e8  jz      short loc_180082214
0x1800821ea  cmp     byte ptr [rax+19h], 4
0x1800821ee  jb      short loc_180082214
0x1800821f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800821f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800821fc  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180082203  mov     edx, 28h ; '('
0x180082208  mov     r9d, eax
0x18008220b  mov     rcx, [rcx+10h]
0x18008220f  call    WPP_SF_D
0x180082214  mov     eax, [rsp+2E0h+cchName]
0x180082218  xor     r15d, r15d
0x18008221b  mov     [r12], eax
0x18008221f  cmp     [r14+44h], r15b
0x180082223  setnz   r15b
0x180082227  mov     rax, [rsp+2E0h+var_280]
0x18008222c  mov     [rax], r15d
0x18008222f  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180082234  test    rcx, rcx
0x180082237  jz      short loc_18008223F
0x180082239  call    cs:__imp_RegCloseKey
0x18008223f  mov     eax, ebx
0x180082241  mov     rcx, [rbp+1E0h+var_50]
0x180082248  xor     rcx, rsp; StackCookie
0x18008224b  call    __security_check_cookie
0x180082250  add     rsp, 2A8h
0x180082257  pop     r15
0x180082259  pop     r14
0x18008225b  pop     r13
0x18008225d  pop     r12
0x18008225f  pop     rdi
0x180082260  pop     rsi
0x180082261  pop     rbx
0x180082262  pop     rbp
0x180082263  retn
```

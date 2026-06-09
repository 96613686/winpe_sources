# CClientUtils::EnumRegistryMerge(ushort const *,uint,ushort *,int *,UT_REGREAD_LOCATION *)

- ea: `0x180007820`
- end: `0x180007d30`
- name: `?EnumRegistryMerge@CClientUtils@@UEAAHPEBGIPEAGPEAHPEAW4UT_REGREAD_LOCATION@@@Z`
- size: `1296`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *, int *, enum UT_REGREAD_LOCATION *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x1800053ac`
- `0x180005438`
- `0x18000594c`
- `0x180007820`
- `0x180007f84`
- `0x18000a7b8`
- `0x18000a858`
- `0x18000a8ac`
- `0x18000aac4`
- `0x18000aea0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180007c4c`
- `ADVAPI32!RegEnumKeyExW` at `0x180007c4c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000793f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800079b2`
- `ADVAPI32!RegOpenKeyExW` at `0x180007a29`
- `ADVAPI32!RegOpenKeyExW` at `0x180007bae`
- `ADVAPI32!RegOpenKeyExW` at `0x18000793f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800079b2`
- `ADVAPI32!RegOpenKeyExW` at `0x180007a29`
- `ADVAPI32!RegOpenKeyExW` at `0x180007bae`
- `ADVAPI32!RegCloseKey` at `0x180007b2f`
- `ADVAPI32!RegCloseKey` at `0x180007cc3`
- `ADVAPI32!RegCloseKey` at `0x180007b2f`
- `ADVAPI32!RegCloseKey` at `0x180007cc3`

## string_xrefs

- `0x1800078f5`: `Unable to get AppContainer registry location.`

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
  unsigned int v8; // ebx
  int v9; // r15d
  int AppContainerRegistryLocation; // eax
  char v11; // di
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v13; // edi
  unsigned int v14; // eax
  int v15; // r8d
  LSTATUS v16; // edi
  unsigned int v17; // eax
  int v18; // r8d
  LSTATUS v19; // edi
  _BYTE *v20; // rcx
  unsigned int v21; // eax
  int v22; // r8d
  unsigned int v23; // eax
  int v24; // edx
  HKEY *v25; // rsi
  LSTATUS i; // eax
  unsigned int v27; // eax
  __int64 v28; // r8
  LSTATUS v29; // edi
  unsigned int v30; // eax
  __int64 v31; // r8
  bool v32; // zf
  LSTATUS v33; // edi
  _BYTE *v34; // rcx
  unsigned int v35; // eax
  int v36; // r8d
  LSTATUS v37; // edi
  unsigned int v38; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR lpName; // [rsp+58h] [rbp-A8h]
  enum UT_REGREAD_LOCATION *v44; // [rsp+60h] [rbp-A0h]
  WCHAR SubKey[272]; // [rsp+70h] [rbp-90h] BYREF

  v44 = a6;
  lpName = a4;
  ftLastWriteTime = 0;
  hKey = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  v8 = 1;
  v9 = 2;
  if ( !a3 )
  {
    *((_BYTE *)this + 68) = 0;
    *((_DWORD *)this + 16) = 0;
    if ( !(unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
      goto LABEL_13;
    AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
    v11 = AppContainerRegistryLocation;
    if ( AppContainerRegistryLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
          v11);
      }
      goto LABEL_58;
    }
    v13 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, (PHKEY)this + 7);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, v15, v14, (__int64)SubKey, v13);
    }
    if ( v13 )
    {
LABEL_13:
      v16 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, (PHKEY)this + 7);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v18, v17, (__int64)SubKey, v16);
      }
      if ( v16 )
      {
        *((_BYTE *)this + 68) = 1;
        v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)this + 7);
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v22, v21, (__int64)SubKey, v19);
          v20 = WPP_GLOBAL_Control;
        }
        if ( v19 )
        {
          if ( v20 != (_BYTE *)&WPP_GLOBAL_Control && (v20[28] & 1) != 0 && v20[25] >= 3u )
          {
            v23 = RdpWppGetCurrentThreadActivityIdPrefix();
            v24 = 39;
LABEL_57:
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v24,
              (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
              v23,
              (__int64)SubKey);
          }
          goto LABEL_58;
        }
      }
    }
  }
  v25 = (HKEY *)((char *)this + 56);
  cchName = *a5;
  for ( i = RegEnumKeyExW(*((HKEY *)this + 7), a3 - *((_DWORD *)this + 16), lpName, &cchName, 0, 0, 0, &ftLastWriteTime);
        ;
        i = RegEnumKeyExW(*v25, a3 - *((_DWORD *)this + 16), lpName, &cchName, 0, 0, 0, &ftLastWriteTime) )
  {
    v37 = i;
    if ( !i )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v38 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids, v38);
      }
      *a5 = cchName;
      v9 = *((_BYTE *)this + 68) != 0;
      goto LABEL_50;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v28, v27, v37);
    }
    v29 = RegCloseKey(*v25);
    if ( v29
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v30 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v31, v30, v29);
    }
    v32 = *((_BYTE *)this + 68) == 0;
    *v25 = 0;
    if ( !v32 )
      goto LABEL_58;
    *((_BYTE *)this + 68) = 1;
    *((_DWORD *)this + 16) = a3;
    v33 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)this + 7);
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v35 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v36, v35, (__int64)SubKey, v33);
      v34 = WPP_GLOBAL_Control;
    }
    if ( v33 )
      break;
    cchName = *a5;
  }
  if ( v34 != (_BYTE *)&WPP_GLOBAL_Control && (v34[28] & 1) != 0 && v34[25] >= 3u )
  {
    v23 = RdpWppGetCurrentThreadActivityIdPrefix();
    v24 = 44;
    goto LABEL_57;
  }
LABEL_58:
  v8 = 0;
LABEL_50:
  *(_DWORD *)v44 = v9;
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180007820  push    rbp
0x180007822  push    rbx
0x180007823  push    rsi
0x180007824  push    rdi
0x180007825  push    r12
0x180007827  push    r13
0x180007829  push    r14
0x18000782b  push    r15
0x18000782d  lea     rbp, [rsp-1A8h]
0x180007835  sub     rsp, 2A8h
0x18000783c  mov     rax, cs:__security_cookie
0x180007843  xor     rax, rsp
0x180007846  mov     [rbp+1E0h+var_50], rax
0x18000784d  mov     rax, [rbp+1E0h+arg_28]
0x180007854  mov     r13d, r8d
0x180007857  mov     r12, [rbp+1E0h+arg_20]
0x18000785e  mov     r14, rcx
0x180007861  mov     r8, rdx; unsigned __int16 *
0x180007864  mov     [rsp+2E0h+var_280], rax
0x180007869  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18000786e  mov     [rsp+2E0h+lpName], r9
0x180007873  mov     qword ptr [rsp+2E0h+ftLastWriteTime.dwLowDateTime], 0
0x18000787c  mov     [rsp+2E0h+hKey], 0
0x180007885  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x18000788a  mov     ebx, 1
0x18000788f  lea     r15d, [rbx+1]
0x180007893  test    r13d, r13d
0x180007896  jnz     loc_180007AB7
0x18000789c  lea     rsi, [r14+38h]
0x1800078a0  mov     [r14+44h], r13b
0x1800078a4  mov     [rsi+8], r13d
0x1800078a8  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1800078ad  test    eax, eax
0x1800078af  jz      loc_180007998
0x1800078b5  lea     rcx, [rsp+2E0h+hKey]; HKEY *
0x1800078ba  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1800078bf  mov     edi, eax
0x1800078c1  test    eax, eax
0x1800078c3  jns     short loc_180007927
0x1800078c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078cc  lea     rdx, WPP_GLOBAL_Control
0x1800078d3  cmp     rcx, rdx
0x1800078d6  jz      loc_180007D2C
0x1800078dc  test    byte ptr [rcx+1Ch], 8
0x1800078e0  jz      loc_180007D2C
0x1800078e6  cmp     [rcx+19h], r15b
0x1800078ea  jb      loc_180007D2C
0x1800078f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800078f5  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x1800078fc  mov     dword ptr [rsp+2E0h+lpClass], edi
0x180007900  mov     [rsp+2E0h+phkResult], rcx
0x180007905  lea     edx, [rbx+22h]
0x180007908  mov     rcx, cs:WPP_GLOBAL_Control
0x18000790f  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180007916  mov     r9d, eax
0x180007919  mov     rcx, [rcx+10h]
0x18000791d  call    WPP_SF_DsD
0x180007922  jmp     loc_180007D2C
0x180007927  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000792c  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x180007931  mov     r9d, 20019h; samDesired
0x180007937  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x18000793c  xor     r8d, r8d; ulOptions
0x18000793f  call    cs:__imp_RegOpenKeyExW
0x180007945  mov     edi, eax
0x180007947  mov     rcx, cs:WPP_GLOBAL_Control
0x18000794e  lea     rax, WPP_GLOBAL_Control
0x180007955  cmp     rcx, rax
0x180007958  jz      short loc_180007990
0x18000795a  test    [rcx+1Ch], bl
0x18000795d  jz      short loc_180007990
0x18000795f  cmp     byte ptr [rcx+19h], 4
0x180007963  jb      short loc_180007990
0x180007965  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000796a  lea     rcx, [rsp+2E0h+SubKey]
0x18000796f  mov     dword ptr [rsp+2E0h+lpClass], edi
0x180007973  mov     [rsp+2E0h+phkResult], rcx
0x180007978  mov     edx, 24h ; '$'
0x18000797d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007984  mov     r9d, eax
0x180007987  mov     rcx, [rcx+10h]
0x18000798b  call    WPP_SF_DSd
0x180007990  test    edi, edi
0x180007992  jz      loc_180007AB7
0x180007998  mov     r9d, 20019h; samDesired
0x18000799e  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x1800079a3  xor     r8d, r8d; ulOptions
0x1800079a6  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x1800079ab  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800079b2  call    cs:__imp_RegOpenKeyExW
0x1800079b8  mov     edi, eax
0x1800079ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079c1  lea     rax, WPP_GLOBAL_Control
0x1800079c8  cmp     rcx, rax
0x1800079cb  jz      short loc_180007A03
0x1800079cd  test    [rcx+1Ch], bl
0x1800079d0  jz      short loc_180007A03
0x1800079d2  cmp     byte ptr [rcx+19h], 4
0x1800079d6  jb      short loc_180007A03
0x1800079d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800079dd  lea     rcx, [rsp+2E0h+SubKey]
0x1800079e2  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1800079e6  mov     [rsp+2E0h+phkResult], rcx
0x1800079eb  mov     edx, 25h ; '%'
0x1800079f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079f7  mov     r9d, eax
0x1800079fa  mov     rcx, [rcx+10h]
0x1800079fe  call    WPP_SF_DSd
0x180007a03  test    edi, edi
0x180007a05  jz      loc_180007AB7
0x180007a0b  mov     r9d, 20019h; samDesired
0x180007a11  mov     [r14+44h], bl
0x180007a15  xor     r8d, r8d; ulOptions
0x180007a18  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x180007a1d  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x180007a22  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007a29  call    cs:__imp_RegOpenKeyExW
0x180007a2f  mov     edi, eax
0x180007a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a38  lea     rax, WPP_GLOBAL_Control
0x180007a3f  cmp     rcx, rax
0x180007a42  jz      short loc_180007A88
0x180007a44  test    [rcx+1Ch], bl
0x180007a47  jz      short loc_180007A88
0x180007a49  cmp     byte ptr [rcx+19h], 4
0x180007a4d  jb      short loc_180007A88
0x180007a4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007a54  lea     rcx, [rsp+2E0h+SubKey]
0x180007a59  mov     dword ptr [rsp+2E0h+lpClass], edi
0x180007a5d  mov     [rsp+2E0h+phkResult], rcx
0x180007a62  mov     edx, 26h ; '&'
0x180007a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a6e  mov     r9d, eax
0x180007a71  mov     rcx, [rcx+10h]
0x180007a75  call    WPP_SF_DSd
0x180007a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a81  lea     rax, WPP_GLOBAL_Control
0x180007a88  test    edi, edi
0x180007a8a  jz      short loc_180007AB7
0x180007a8c  cmp     rcx, rax
0x180007a8f  jz      loc_180007D2C
0x180007a95  test    [rcx+1Ch], bl
0x180007a98  jz      loc_180007D2C
0x180007a9e  cmp     byte ptr [rcx+19h], 3
0x180007aa2  jb      loc_180007D2C
0x180007aa8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007aad  mov     edx, 27h ; '''
0x180007ab2  jmp     loc_180007D08
0x180007ab7  mov     eax, [r12]
0x180007abb  lea     rsi, [r14+38h]
0x180007abf  mov     [rsp+2E0h+cchName], eax
0x180007ac3  lea     rax, [rsp+2E0h+ftLastWriteTime]
0x180007ac8  mov     [rsp+2E0h+lpftLastWriteTime], rax
0x180007acd  mov     [rsp+2E0h+lpcchClass], 0
0x180007ad6  mov     [rsp+2E0h+lpClass], 0
0x180007adf  mov     [rsp+2E0h+phkResult], 0
0x180007ae8  jmp     loc_180007C38
0x180007aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180007af4  lea     rax, WPP_GLOBAL_Control
0x180007afb  cmp     rcx, rax
0x180007afe  jz      short loc_180007B2C
0x180007b00  test    [rcx+1Ch], bl
0x180007b03  jz      short loc_180007B2C
0x180007b05  cmp     byte ptr [rcx+19h], 4
0x180007b09  jb      short loc_180007B2C
0x180007b0b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b17  mov     edx, 29h ; ')'
0x180007b1c  mov     r9d, eax
0x180007b1f  mov     dword ptr [rsp+2E0h+phkResult], edi
0x180007b23  mov     rcx, [rcx+10h]
0x180007b27  call    WPP_SF_Dl
0x180007b2c  mov     rcx, [rsi]; hKey
0x180007b2f  call    cs:__imp_RegCloseKey
0x180007b35  mov     edi, eax
0x180007b37  test    eax, eax
0x180007b39  jz      short loc_180007B7A
0x180007b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b42  lea     rax, WPP_GLOBAL_Control
0x180007b49  cmp     rcx, rax
0x180007b4c  jz      short loc_180007B7A
0x180007b4e  test    [rcx+1Ch], bl
0x180007b51  jz      short loc_180007B7A
0x180007b53  cmp     [rcx+19h], r15b
0x180007b57  jb      short loc_180007B7A
0x180007b59  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b65  mov     edx, 2Ah ; '*'
0x180007b6a  mov     r9d, eax
0x180007b6d  mov     dword ptr [rsp+2E0h+phkResult], edi
0x180007b71  mov     rcx, [rcx+10h]
0x180007b75  call    WPP_SF_Dl
0x180007b7a  cmp     byte ptr [r14+44h], 0
0x180007b7f  mov     qword ptr [rsi], 0
0x180007b86  jnz     loc_180007D2C
0x180007b8c  mov     r9d, 20019h; samDesired
0x180007b92  mov     [r14+44h], bl
0x180007b96  xor     r8d, r8d; ulOptions
0x180007b99  mov     [r14+40h], r13d
0x180007b9d  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x180007ba2  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x180007ba7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007bae  call    cs:__imp_RegOpenKeyExW
0x180007bb4  mov     edi, eax
0x180007bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bbd  lea     rax, WPP_GLOBAL_Control
0x180007bc4  cmp     rcx, rax
0x180007bc7  jz      short loc_180007C0D
0x180007bc9  test    [rcx+1Ch], bl
0x180007bcc  jz      short loc_180007C0D
0x180007bce  cmp     byte ptr [rcx+19h], 4
0x180007bd2  jb      short loc_180007C0D
0x180007bd4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007bd9  lea     rcx, [rsp+2E0h+SubKey]
0x180007bde  mov     dword ptr [rsp+2E0h+lpClass], edi
0x180007be2  mov     [rsp+2E0h+phkResult], rcx
0x180007be7  mov     edx, 2Bh ; '+'
0x180007bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bf3  mov     r9d, eax
0x180007bf6  mov     rcx, [rcx+10h]
0x180007bfa  call    WPP_SF_DSd
0x180007bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c06  lea     rax, WPP_GLOBAL_Control
0x180007c0d  test    edi, edi
0x180007c0f  jnz     loc_180007CEE
0x180007c15  mov     eax, [r12]
0x180007c19  mov     [rsp+2E0h+cchName], eax
0x180007c1d  lea     rax, [rsp+2E0h+ftLastWriteTime]
0x180007c22  mov     [rsp+2E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007c27  xor     eax, eax
0x180007c29  mov     [rsp+2E0h+lpcchClass], rax; lpcchClass
0x180007c2e  mov     [rsp+2E0h+lpClass], rax; lpClass
0x180007c33  mov     [rsp+2E0h+phkResult], rax; lpReserved
0x180007c38  mov     r8, [rsp+2E0h+lpName]; lpName
0x180007c3d  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180007c42  mov     rcx, [rsi]; hKey
0x180007c45  mov     edx, r13d
0x180007c48  sub     edx, [r14+40h]; dwIndex
0x180007c4c  call    cs:__imp_RegEnumKeyExW
0x180007c52  mov     edi, eax
0x180007c54  test    eax, eax
0x180007c56  jnz     loc_180007AED
0x180007c5c  mov     rax, cs:WPP_GLOBAL_Control
0x180007c63  lea     rdx, WPP_GLOBAL_Control
0x180007c6a  cmp     rax, rdx
0x180007c6d  jz      short loc_180007C9E
0x180007c6f  test    [rax+1Ch], bl
0x180007c72  jz      short loc_180007C9E
0x180007c74  cmp     byte ptr [rax+19h], 4
0x180007c78  jb      short loc_180007C9E
0x180007c7a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c86  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180007c8d  mov     edx, 28h ; '('
0x180007c92  mov     r9d, eax
0x180007c95  mov     rcx, [rcx+10h]
0x180007c99  call    WPP_SF_D
0x180007c9e  mov     eax, [rsp+2E0h+cchName]
0x180007ca2  xor     r15d, r15d
0x180007ca5  mov     [r12], eax
0x180007ca9  cmp     [r14+44h], r15b
0x180007cad  setnz   r15b
0x180007cb1  mov     rax, [rsp+2E0h+var_280]
0x180007cb6  mov     [rax], r15d
0x180007cb9  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180007cbe  test    rcx, rcx
0x180007cc1  jz      short loc_180007CC9
0x180007cc3  call    cs:__imp_RegCloseKey
0x180007cc9  mov     eax, ebx
0x180007ccb  mov     rcx, [rbp+1E0h+var_50]
0x180007cd2  xor     rcx, rsp; StackCookie
0x180007cd5  call    __security_check_cookie
0x180007cda  add     rsp, 2A8h
0x180007ce1  pop     r15
0x180007ce3  pop     r14
0x180007ce5  pop     r13
0x180007ce7  pop     r12
0x180007ce9  pop     rdi
0x180007cea  pop     rsi
0x180007ceb  pop     rbx
0x180007cec  pop     rbp
0x180007ced  retn
0x180007cee  cmp     rcx, rax
0x180007cf1  jz      short loc_180007D2C
0x180007cf3  test    [rcx+1Ch], bl
0x180007cf6  jz      short loc_180007D2C
0x180007cf8  cmp     byte ptr [rcx+19h], 3
0x180007cfc  jb      short loc_180007D2C
0x180007cfe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007d03  mov     edx, 2Ch ; ','
0x180007d08  lea     rcx, [rsp+2E0h+SubKey]
0x180007d0d  mov     r9d, eax
0x180007d10  mov     [rsp+2E0h+phkResult], rcx
0x180007d15  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180007d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d23  mov     rcx, [rcx+10h]
0x180007d27  call    WPP_SF_DS
0x180007d2c  xor     ebx, ebx
0x180007d2e  jmp     short loc_180007CB1
```

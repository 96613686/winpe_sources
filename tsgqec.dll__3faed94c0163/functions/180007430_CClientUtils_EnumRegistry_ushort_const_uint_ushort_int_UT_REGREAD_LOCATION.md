# CClientUtils::EnumRegistry(ushort const *,uint,ushort *,int *,UT_REGREAD_LOCATION)

- ea: `0x180007430`
- end: `0x180007811`
- name: `?EnumRegistry@CClientUtils@@UEAAHPEBGIPEAGPEAHW4UT_REGREAD_LOCATION@@@Z`
- size: `993`
- prototype: `int __high(const unsigned __int16 *, unsigned int, unsigned __int16 *, int *, enum UT_REGREAD_LOCATION)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x1800053ac`
- `0x180005438`
- `0x18000594c`
- `0x180007430`
- `0x180007f84`
- `0x18000a7b8`
- `0x18000a858`
- `0x18000a8ac`
- `0x18000aac4`
- `0x18000aea0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180007620`
- `ADVAPI32!RegEnumKeyExW` at `0x180007620`
- `ADVAPI32!RegOpenKeyExW` at `0x180007534`
- `ADVAPI32!RegOpenKeyExW` at `0x1800075a8`
- `ADVAPI32!RegOpenKeyExW` at `0x180007699`
- `ADVAPI32!RegOpenKeyExW` at `0x180007534`
- `ADVAPI32!RegOpenKeyExW` at `0x1800075a8`
- `ADVAPI32!RegOpenKeyExW` at `0x180007699`
- `ADVAPI32!RegCloseKey` at `0x180007795`
- `ADVAPI32!RegCloseKey` at `0x1800077e8`
- `ADVAPI32!RegCloseKey` at `0x180007795`
- `ADVAPI32!RegCloseKey` at `0x1800077e8`

## string_xrefs

- `0x1800074e6`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::EnumRegistry(
        __int64 a1,
        const unsigned __int16 *a2,
        DWORD a3,
        WCHAR *a4,
        DWORD *lpcchName,
        int a6)
{
  unsigned int v8; // esi
  int AppContainerRegistryLocation; // eax
  char v11; // bl
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v13; // ebx
  unsigned int v14; // eax
  int v15; // r8d
  char v16; // bl
  unsigned int v17; // eax
  int v18; // r8d
  LSTATUS v19; // ebx
  unsigned int v20; // eax
  LSTATUS v21; // ebx
  _BYTE *v22; // rcx
  unsigned int v23; // eax
  int v24; // r8d
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // r8
  LSTATUS v28; // ebx
  unsigned int v29; // eax
  __int64 v30; // r8
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[272]; // [rsp+50h] [rbp-B0h] BYREF

  v8 = 0;
  ftLastWriteTime = 0;
  hKey = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  if ( a3 )
    goto LABEL_18;
  if ( !a6 )
  {
    if ( !(unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
      goto LABEL_14;
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
          27,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v11);
      }
      goto LABEL_43;
    }
    v13 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, (PHKEY)(a1 + 56));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v15, v14, (__int64)SubKey, v13);
    }
    if ( v13 )
    {
LABEL_14:
      v16 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, (PHKEY)(a1 + 56));
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v18, v17, (__int64)SubKey, v16);
      }
    }
    goto LABEL_18;
  }
  v21 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)(a1 + 56));
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v23 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v24, v23, (__int64)SubKey, v21);
    v22 = WPP_GLOBAL_Control;
  }
  if ( !v21 )
  {
LABEL_18:
    v19 = RegEnumKeyExW(*(HKEY *)(a1 + 56), a3, a4, lpcchName, 0, 0, 0, &ftLastWriteTime);
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v27, v26, v19);
      }
      v28 = RegCloseKey(*(HKEY *)(a1 + 56));
      if ( v28
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v30, v29, v28);
      }
      *(_QWORD *)(a1 + 56) = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids, v20);
      }
      v8 = 1;
    }
    goto LABEL_43;
  }
  if ( v22 != (_BYTE *)&WPP_GLOBAL_Control && (v22[28] & 1) != 0 && v22[25] >= 3u )
  {
    v25 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
      v25,
      (__int64)SubKey);
  }
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180007430  push    rbp
0x180007432  push    rbx
0x180007433  push    rsi
0x180007434  push    rdi
0x180007435  push    r12
0x180007437  push    r14
0x180007439  push    r15
0x18000743b  lea     rbp, [rsp-180h]
0x180007443  sub     rsp, 280h
0x18000744a  mov     rax, cs:__security_cookie
0x180007451  xor     rax, rsp
0x180007454  mov     [rbp+1B0h+var_40], rax
0x18000745b  mov     r12, [rbp+1B0h+lpcchName]
0x180007462  mov     r14d, r8d
0x180007465  mov     rdi, rcx
0x180007468  xor     esi, esi
0x18000746a  mov     r8, rdx; unsigned __int16 *
0x18000746d  mov     qword ptr [rsp+2B0h+ftLastWriteTime.dwLowDateTime], rsi
0x180007472  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x180007477  mov     [rsp+2B0h+hKey], rsi
0x18000747c  mov     r15, r9
0x18000747f  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x180007484  test    r14d, r14d
0x180007487  jnz     loc_1800075FA
0x18000748d  cmp     [rbp+1B0h+arg_28], esi
0x180007493  jnz     loc_18000767B
0x180007499  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x18000749e  test    eax, eax
0x1800074a0  jz      loc_18000758A
0x1800074a6  lea     rcx, [rsp+2B0h+hKey]; HKEY *
0x1800074ab  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1800074b0  mov     ebx, eax
0x1800074b2  test    eax, eax
0x1800074b4  jns     short loc_180007518
0x1800074b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074bd  lea     rdx, WPP_GLOBAL_Control
0x1800074c4  cmp     rcx, rdx
0x1800074c7  jz      loc_1800077DE
0x1800074cd  test    byte ptr [rcx+1Ch], 8
0x1800074d1  jz      loc_1800077DE
0x1800074d7  cmp     byte ptr [rcx+19h], 2
0x1800074db  jb      loc_1800077DE
0x1800074e1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800074e6  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x1800074ed  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1800074f1  mov     [rsp+2B0h+phkResult], rcx
0x1800074f6  lea     edx, [rsi+1Bh]
0x1800074f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007500  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180007507  mov     r9d, eax
0x18000750a  mov     rcx, [rcx+10h]
0x18000750e  call    WPP_SF_DsD
0x180007513  jmp     loc_1800077DE
0x180007518  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18000751d  lea     rax, [rdi+38h]
0x180007521  mov     r9d, 20019h; samDesired
0x180007527  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000752c  xor     r8d, r8d; ulOptions
0x18000752f  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180007534  call    cs:__imp_RegOpenKeyExW
0x18000753a  mov     ebx, eax
0x18000753c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007543  lea     rax, WPP_GLOBAL_Control
0x18000754a  cmp     rcx, rax
0x18000754d  jz      short loc_180007586
0x18000754f  test    byte ptr [rcx+1Ch], 1
0x180007553  jz      short loc_180007586
0x180007555  cmp     byte ptr [rcx+19h], 4
0x180007559  jb      short loc_180007586
0x18000755b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007560  lea     rcx, [rsp+2B0h+SubKey]
0x180007565  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x180007569  mov     [rsp+2B0h+phkResult], rcx
0x18000756e  mov     edx, 1Ch
0x180007573  mov     rcx, cs:WPP_GLOBAL_Control
0x18000757a  mov     r9d, eax
0x18000757d  mov     rcx, [rcx+10h]
0x180007581  call    WPP_SF_DSd
0x180007586  test    ebx, ebx
0x180007588  jz      short loc_1800075FA
0x18000758a  lea     rax, [rdi+38h]
0x18000758e  mov     r9d, 20019h; samDesired
0x180007594  xor     r8d, r8d; ulOptions
0x180007597  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000759c  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1800075a1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800075a8  call    cs:__imp_RegOpenKeyExW
0x1800075ae  mov     ebx, eax
0x1800075b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075b7  lea     rax, WPP_GLOBAL_Control
0x1800075be  cmp     rcx, rax
0x1800075c1  jz      short loc_1800075FA
0x1800075c3  test    byte ptr [rcx+1Ch], 1
0x1800075c7  jz      short loc_1800075FA
0x1800075c9  cmp     byte ptr [rcx+19h], 4
0x1800075cd  jb      short loc_1800075FA
0x1800075cf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800075d4  lea     rcx, [rsp+2B0h+SubKey]
0x1800075d9  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1800075dd  mov     [rsp+2B0h+phkResult], rcx
0x1800075e2  mov     edx, 1Dh
0x1800075e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075ee  mov     r9d, eax
0x1800075f1  mov     rcx, [rcx+10h]
0x1800075f5  call    WPP_SF_DSd
0x1800075fa  mov     rcx, [rdi+38h]; hKey
0x1800075fe  lea     rax, [rsp+2B0h+ftLastWriteTime]
0x180007603  mov     [rsp+2B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007608  mov     r9, r12; lpcchName
0x18000760b  mov     [rsp+2B0h+lpcchClass], rsi; lpcchClass
0x180007610  mov     r8, r15; lpName
0x180007613  mov     [rsp+2B0h+lpClass], rsi; lpClass
0x180007618  mov     edx, r14d; dwIndex
0x18000761b  mov     [rsp+2B0h+phkResult], rsi; lpReserved
0x180007620  call    cs:__imp_RegEnumKeyExW
0x180007626  mov     ebx, eax
0x180007628  test    eax, eax
0x18000762a  jnz     loc_180007751
0x180007630  mov     rax, cs:WPP_GLOBAL_Control
0x180007637  lea     rdx, WPP_GLOBAL_Control
0x18000763e  cmp     rax, rdx
0x180007641  jz      short loc_180007671
0x180007643  test    byte ptr [rax+1Ch], 1
0x180007647  jz      short loc_180007671
0x180007649  cmp     byte ptr [rax+19h], 4
0x18000764d  jb      short loc_180007671
0x18000764f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007654  mov     rcx, cs:WPP_GLOBAL_Control
0x18000765b  lea     edx, [rbx+20h]
0x18000765e  mov     r9d, eax
0x180007661  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180007668  mov     rcx, [rcx+10h]
0x18000766c  call    WPP_SF_D
0x180007671  mov     esi, 1
0x180007676  jmp     loc_1800077DE
0x18000767b  lea     rax, [rdi+38h]
0x18000767f  mov     r9d, 20019h; samDesired
0x180007685  xor     r8d, r8d; ulOptions
0x180007688  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000768d  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180007692  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007699  call    cs:__imp_RegOpenKeyExW
0x18000769f  mov     ebx, eax
0x1800076a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076a8  lea     rax, WPP_GLOBAL_Control
0x1800076af  cmp     rcx, rax
0x1800076b2  jz      short loc_1800076F9
0x1800076b4  test    byte ptr [rcx+1Ch], 1
0x1800076b8  jz      short loc_1800076F9
0x1800076ba  cmp     byte ptr [rcx+19h], 4
0x1800076be  jb      short loc_1800076F9
0x1800076c0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800076c5  lea     rcx, [rsp+2B0h+SubKey]
0x1800076ca  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1800076ce  mov     [rsp+2B0h+phkResult], rcx
0x1800076d3  mov     edx, 1Eh
0x1800076d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076df  mov     r9d, eax
0x1800076e2  mov     rcx, [rcx+10h]
0x1800076e6  call    WPP_SF_DSd
0x1800076eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076f2  lea     rax, WPP_GLOBAL_Control
0x1800076f9  test    ebx, ebx
0x1800076fb  jz      loc_1800075FA
0x180007701  cmp     rcx, rax
0x180007704  jz      loc_1800077DE
0x18000770a  test    byte ptr [rcx+1Ch], 1
0x18000770e  jz      loc_1800077DE
0x180007714  cmp     byte ptr [rcx+19h], 3
0x180007718  jb      loc_1800077DE
0x18000771e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007723  lea     rcx, [rsp+2B0h+SubKey]
0x180007728  mov     edx, 1Fh
0x18000772d  mov     [rsp+2B0h+phkResult], rcx
0x180007732  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180007739  mov     rcx, cs:WPP_GLOBAL_Control
0x180007740  mov     r9d, eax
0x180007743  mov     rcx, [rcx+10h]
0x180007747  call    WPP_SF_DS
0x18000774c  jmp     loc_1800077DE
0x180007751  mov     rax, cs:WPP_GLOBAL_Control
0x180007758  lea     r14, WPP_GLOBAL_Control
0x18000775f  cmp     rax, r14
0x180007762  jz      short loc_180007791
0x180007764  test    byte ptr [rax+1Ch], 1
0x180007768  jz      short loc_180007791
0x18000776a  cmp     byte ptr [rax+19h], 4
0x18000776e  jb      short loc_180007791
0x180007770  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007775  mov     rcx, cs:WPP_GLOBAL_Control
0x18000777c  mov     edx, 21h ; '!'
0x180007781  mov     r9d, eax
0x180007784  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x180007788  mov     rcx, [rcx+10h]
0x18000778c  call    WPP_SF_Dl
0x180007791  mov     rcx, [rdi+38h]; hKey
0x180007795  call    cs:__imp_RegCloseKey
0x18000779b  mov     ebx, eax
0x18000779d  test    eax, eax
0x18000779f  jz      short loc_1800077DA
0x1800077a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077a8  cmp     rcx, r14
0x1800077ab  jz      short loc_1800077DA
0x1800077ad  test    byte ptr [rcx+1Ch], 1
0x1800077b1  jz      short loc_1800077DA
0x1800077b3  cmp     byte ptr [rcx+19h], 2
0x1800077b7  jb      short loc_1800077DA
0x1800077b9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800077be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077c5  mov     edx, 22h ; '"'
0x1800077ca  mov     r9d, eax
0x1800077cd  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x1800077d1  mov     rcx, [rcx+10h]
0x1800077d5  call    WPP_SF_Dl
0x1800077da  mov     [rdi+38h], rsi
0x1800077de  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800077e3  test    rcx, rcx
0x1800077e6  jz      short loc_1800077EE
0x1800077e8  call    cs:__imp_RegCloseKey
0x1800077ee  mov     eax, esi
0x1800077f0  mov     rcx, [rbp+1B0h+var_40]
0x1800077f7  xor     rcx, rsp; StackCookie
0x1800077fa  call    __security_check_cookie
0x1800077ff  add     rsp, 280h
0x180007806  pop     r15
0x180007808  pop     r14
0x18000780a  pop     r12
0x18000780c  pop     rdi
0x18000780d  pop     rsi
0x18000780e  pop     rbx
0x18000780f  pop     rbp
0x180007810  retn
```

# CDevicePersistenceManager::GetDeviceProviders(long *,ushort * * *)

- ea: `0x180023530`
- end: `0x180023789`
- name: `?GetDeviceProviders@CDevicePersistenceManager@@UEAAJPEAJPEAPEAPEAG@Z`
- size: `601`
- prototype: `__int64 __fastcall(CDevicePersistenceManager *this, int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000db4c`
- `0x18000f3f8`
- `0x180013180`
- `0x180018738`
- `0x18001dcac`
- `0x180023530`
- `0x180023790`
- `0x18002aa74`
- `0x180038ce4`
- `0x18003a560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002368d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002368d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180023604`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180023604`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800236ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800236ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023709`

## pseudocode

```c
__int64 __fastcall CDevicePersistenceManager::GetDeviceProviders(
        CDevicePersistenceManager *this,
        int *a2,
        unsigned __int16 ***a3)
{
  signed int v5; // edi
  int IsAllowedCOMCallLocality; // ebx
  int v7; // eax
  bool v8; // zf
  int v9; // eax
  signed int v10; // r9d
  __int64 v11; // r8
  signed int i; // esi
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  void *v15; // [rsp+48h] [rbp-B8h] BYREF
  int v16[2]; // [rsp+50h] [rbp-B0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v18; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v15 = 0;
  v5 = 0;
  *(_QWORD *)v16 = 0;
  hKey = 0;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_25;
  IsAllowedCOMCallLocality = HrCreateOrOpenProvidersKey(&hKey);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_25;
  cchName = 0;
  ftLastWriteTime = 0;
  while ( IsAllowedCOMCallLocality >= 0 )
  {
    cchName = 260;
    v7 = RegEnumKeyExW(hKey, v5, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    v8 = v7 == 0;
    if ( v7 > 0 )
    {
      if ( v7 == 259 )
        goto LABEL_17;
      v7 = (unsigned __int16)v7 | 0x80070000;
      v8 = v7 == 0;
    }
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
          (unsigned int)"HrRegEnumKeyEx",
          v7);
LABEL_17:
      IsAllowedCOMCallLocality = 0;
      break;
    }
    v18 = 0;
    IsAllowedCOMCallLocality = HrCoTaskMemAllocString(Name, &v18);
    if ( IsAllowedCOMCallLocality >= 0 )
      IsAllowedCOMCallLocality = CUArray<unsigned short *>::HrPushBack(&v15, &v18);
    ++v5;
  }
  RegCloseKey(hKey);
  v5 = v16[0];
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_25;
  if ( v16[0] )
  {
    v9 = HrCoTaskMemAllocArray(v16[0], 8, (void **)a3);
    IsAllowedCOMCallLocality = v9;
    if ( v9 >= 0 )
    {
      v10 = 0;
      if ( v5 > 0 )
      {
        do
        {
          v11 = (unsigned int)v10++;
          (*a3)[v11] = (unsigned __int16 *)*((_QWORD *)v15 + v11);
        }
        while ( v10 < v5 );
        goto LABEL_35;
      }
    }
    *a2 = v5;
    if ( v9 >= 0 )
      goto LABEL_29;
LABEL_25:
    *a2 = 0;
    if ( *a3 )
      CoTaskMemFree(*a3);
    *a3 = 0;
    for ( i = 0; i < v5; ++i )
      CoTaskMemFree(*((LPVOID *)v15 + (unsigned int)i));
    goto LABEL_29;
  }
  *a3 = 0;
LABEL_35:
  *a2 = v5;
LABEL_29:
  if ( IsAllowedCOMCallLocality
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  }
  operator delete(v15);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x180023530  mov     [rsp-8+arg_0], rbx
0x180023535  mov     [rsp-8+arg_18], rsi
0x18002353a  push    rbp
0x18002353b  push    rdi
0x18002353c  push    r13
0x18002353e  push    r14
0x180023540  push    r15
0x180023542  lea     rbp, [rsp-190h]
0x18002354a  sub     rsp, 290h
0x180023551  mov     rax, cs:__security_cookie
0x180023558  xor     rax, rsp
0x18002355b  mov     [rbp+1B0h+var_30], rax
0x180023562  xor     r15d, r15d
0x180023565  mov     rsi, r8
0x180023568  mov     r14, rdx
0x18002356b  test    rdx, rdx
0x18002356e  jz      loc_180023759
0x180023574  test    r8, r8
0x180023577  jz      loc_180023759
0x18002357d  lea     ecx, [r15+1]
0x180023581  mov     [r8], r15
0x180023584  mov     [rsp+2B0h+var_268], r15
0x180023589  mov     edi, r15d
0x18002358c  mov     qword ptr [rsp+2B0h+var_260], r15
0x180023591  mov     [rsp+2B0h+hKey], r15
0x180023596  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18002359b  lea     r13, WPP_GLOBAL_Control
0x1800235a2  mov     ebx, eax
0x1800235a4  test    eax, eax
0x1800235a6  js      loc_1800236E3
0x1800235ac  lea     rcx, [rsp+2B0h+hKey]; HKEY *
0x1800235b1  call    ?HrCreateOrOpenProvidersKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenProvidersKey(HKEY__ * *)
0x1800235b6  mov     ebx, eax
0x1800235b8  test    eax, eax
0x1800235ba  js      loc_1800236E3
0x1800235c0  mov     [rsp+2B0h+cchName], r15d
0x1800235c5  mov     qword ptr [rsp+2B0h+ftLastWriteTime.dwLowDateTime], r15
0x1800235ca  test    ebx, ebx
0x1800235cc  js      loc_180023688
0x1800235d2  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800235d7  lea     rax, [rsp+2B0h+ftLastWriteTime]
0x1800235dc  mov     [rsp+2B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800235e1  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x1800235e6  mov     [rsp+2B0h+lpcchClass], r15; lpcchClass
0x1800235eb  lea     r8, [rsp+2B0h+Name]; lpName
0x1800235f0  mov     [rsp+2B0h+lpClass], r15; lpClass
0x1800235f5  mov     edx, edi; dwIndex
0x1800235f7  mov     [rsp+2B0h+lpReserved], r15; lpReserved
0x1800235fc  mov     [rsp+2B0h+cchName], 104h
0x180023604  call    cs:__imp_RegEnumKeyExW
0x18002360a  test    eax, eax
0x18002360c  jle     short loc_18002361F
0x18002360e  cmp     eax, 103h
0x180023613  jz      short loc_180023685
0x180023615  movzx   eax, ax
0x180023618  or      eax, 80070000h
0x18002361d  test    eax, eax
0x18002361f  jnz     short loc_180023653
0x180023621  lea     rdx, [rsp+2B0h+var_250]; unsigned __int16 **
0x180023626  mov     [rsp+2B0h+var_250], r15
0x18002362b  lea     rcx, [rsp+2B0h+Name]; pszSrc
0x180023630  call    ?HrCoTaskMemAllocString@@YAJPEAGPEAPEAG@Z; HrCoTaskMemAllocString(ushort *,ushort * *)
0x180023635  mov     ebx, eax
0x180023637  test    eax, eax
0x180023639  js      short loc_18002364C
0x18002363b  lea     rdx, [rsp+2B0h+var_250]
0x180023640  lea     rcx, [rsp+2B0h+var_268]
0x180023645  call    ?HrPushBack@?$CUArray@PEAG@@QEAAJAEBQEAG@Z; CUArray<ushort *>::HrPushBack(ushort * const &)
0x18002364a  mov     ebx, eax
0x18002364c  inc     edi
0x18002364e  jmp     loc_1800235CA
0x180023653  mov     rcx, cs:WPP_GLOBAL_Control
0x18002365a  cmp     rcx, r13
0x18002365d  jz      short loc_180023685
0x18002365f  test    byte ptr [rcx+1Ch], 1
0x180023663  jz      short loc_180023685
0x180023665  mov     rcx, [rcx+10h]
0x180023669  lea     r9, aHrregenumkeyex; "HrRegEnumKeyEx"
0x180023670  mov     edx, 0Dh
0x180023675  mov     dword ptr [rsp+2B0h+lpReserved], eax
0x180023679  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180023680  call    WPP_SF_sd
0x180023685  mov     ebx, r15d
0x180023688  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002368d  call    cs:__imp_RegCloseKey
0x180023693  mov     edi, [rsp+2B0h+var_260]
0x180023697  test    ebx, ebx
0x180023699  js      short loc_1800236E3
0x18002369b  test    edi, edi
0x18002369d  jz      loc_180023751
0x1800236a3  mov     r8, rsi; void **
0x1800236a6  mov     edx, 8; int
0x1800236ab  mov     ecx, edi; int
0x1800236ad  call    ?HrCoTaskMemAllocArray@@YAJJJPEAPEAX@Z; HrCoTaskMemAllocArray(long,long,void * *)
0x1800236b2  mov     ebx, eax
0x1800236b4  test    eax, eax
0x1800236b6  js      short loc_1800236DC
0x1800236b8  mov     r9d, r15d
0x1800236bb  test    edi, edi
0x1800236bd  jle     short loc_1800236DC
0x1800236bf  mov     rax, [rsp+2B0h+var_268]
0x1800236c4  mov     rdx, [rsi]
0x1800236c7  mov     r8d, r9d
0x1800236ca  inc     r9d
0x1800236cd  mov     rcx, [rax+r8*8]
0x1800236d1  mov     [rdx+r8*8], rcx
0x1800236d5  cmp     r9d, edi
0x1800236d8  jl      short loc_1800236BF
0x1800236da  jmp     short loc_180023754
0x1800236dc  mov     [r14], edi
0x1800236df  test    eax, eax
0x1800236e1  jns     short loc_180023715
0x1800236e3  mov     [r14], r15d
0x1800236e6  mov     rcx, [rsi]; pv
0x1800236e9  test    rcx, rcx
0x1800236ec  jz      short loc_1800236F4
0x1800236ee  call    cs:__imp_CoTaskMemFree
0x1800236f4  mov     [rsi], r15
0x1800236f7  mov     esi, r15d
0x1800236fa  test    edi, edi
0x1800236fc  jle     short loc_180023715
0x1800236fe  mov     rcx, [rsp+2B0h+var_268]
0x180023703  mov     eax, esi
0x180023705  mov     rcx, [rcx+rax*8]; pv
0x180023709  call    cs:__imp_CoTaskMemFree
0x18002370f  inc     esi
0x180023711  cmp     esi, edi
0x180023713  jl      short loc_1800236FE
0x180023715  test    ebx, ebx
0x180023717  jz      short loc_180023743
0x180023719  mov     rcx, cs:WPP_GLOBAL_Control
0x180023720  cmp     rcx, r13
0x180023723  jz      short loc_180023743
0x180023725  test    byte ptr [rcx+1Ch], 1
0x180023729  jz      short loc_180023743
0x18002372b  mov     rcx, [rcx+10h]
0x18002372f  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x180023736  mov     edx, 14h
0x18002373b  mov     r9d, ebx
0x18002373e  call    WPP_SF_d
0x180023743  mov     rcx, [rsp+2B0h+var_268]; void *
0x180023748  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002374d  mov     eax, ebx
0x18002374f  jmp     short loc_18002375E
0x180023751  mov     [rsi], r15
0x180023754  mov     [r14], edi
0x180023757  jmp     short loc_180023715
0x180023759  mov     eax, 80004003h
0x18002375e  mov     rcx, [rbp+1B0h+var_30]
0x180023765  xor     rcx, rsp; StackCookie
0x180023768  call    __security_check_cookie
0x18002376d  lea     r11, [rsp+2B0h+var_20]
0x180023775  mov     rbx, [r11+30h]
0x180023779  mov     rsi, [r11+48h]
0x18002377d  mov     rsp, r11
0x180023780  pop     r15
0x180023782  pop     r14
0x180023784  pop     r13
0x180023786  pop     rdi
0x180023787  pop     rbp
0x180023788  retn
```

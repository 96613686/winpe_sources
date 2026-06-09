# CDevicePersistenceManager::GetDeviceProviders(long *,ushort * * *)

- ea: `0x180024230`
- end: `0x1800244a5`
- name: `?GetDeviceProviders@CDevicePersistenceManager@@UEAAJPEAJPEAPEAPEAG@Z`
- size: `629`
- prototype: `__int64 __fastcall(CDevicePersistenceManager *this, int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18000c8e0`
- `0x180012d70`
- `0x1800200f4`
- `0x180024230`
- `0x1800244b0`
- `0x18002bed8`
- `0x18002c5ec`
- `0x18003b1cc`
- `0x18003cb60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024393`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024304`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024304`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800243fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002441e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800243fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002441e`

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
0x180024230  mov     [rsp-8+arg_0], rbx
0x180024235  mov     [rsp-8+arg_18], rsi
0x18002423a  push    rbp
0x18002423b  push    rdi
0x18002423c  push    r13
0x18002423e  push    r14
0x180024240  push    r15
0x180024242  lea     rbp, [rsp-190h]
0x18002424a  sub     rsp, 290h
0x180024251  mov     rax, cs:__security_cookie
0x180024258  xor     rax, rsp
0x18002425b  mov     [rbp+1B0h+var_30], rax
0x180024262  xor     r15d, r15d
0x180024265  mov     rsi, r8
0x180024268  mov     r14, rdx
0x18002426b  test    rdx, rdx
0x18002426e  jz      loc_180024474
0x180024274  test    r8, r8
0x180024277  jz      loc_180024474
0x18002427d  lea     ecx, [r15+1]
0x180024281  mov     [r8], r15
0x180024284  mov     [rsp+2B0h+var_268], r15
0x180024289  mov     edi, r15d
0x18002428c  mov     qword ptr [rsp+2B0h+var_260], r15
0x180024291  mov     [rsp+2B0h+hKey], r15
0x180024296  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18002429b  lea     r13, WPP_GLOBAL_Control
0x1800242a2  mov     ebx, eax
0x1800242a4  test    eax, eax
0x1800242a6  js      loc_1800243F2
0x1800242ac  lea     rcx, [rsp+2B0h+hKey]; HKEY *
0x1800242b1  call    ?HrCreateOrOpenProvidersKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenProvidersKey(HKEY__ * *)
0x1800242b6  mov     ebx, eax
0x1800242b8  test    eax, eax
0x1800242ba  js      loc_1800243F2
0x1800242c0  mov     [rsp+2B0h+cchName], r15d
0x1800242c5  mov     qword ptr [rsp+2B0h+ftLastWriteTime.dwLowDateTime], r15
0x1800242ca  test    ebx, ebx
0x1800242cc  js      loc_18002438E
0x1800242d2  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800242d7  lea     rax, [rsp+2B0h+ftLastWriteTime]
0x1800242dc  mov     [rsp+2B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800242e1  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x1800242e6  mov     [rsp+2B0h+lpcchClass], r15; lpcchClass
0x1800242eb  lea     r8, [rsp+2B0h+Name]; lpName
0x1800242f0  mov     [rsp+2B0h+lpClass], r15; lpClass
0x1800242f5  mov     edx, edi; dwIndex
0x1800242f7  mov     [rsp+2B0h+lpReserved], r15; lpReserved
0x1800242fc  mov     [rsp+2B0h+cchName], 104h
0x180024304  call    cs:__imp_RegEnumKeyExW
0x18002430b  nop     dword ptr [rax+rax+00h]
0x180024310  test    eax, eax
0x180024312  jle     short loc_180024325
0x180024314  cmp     eax, 103h
0x180024319  jz      short loc_18002438B
0x18002431b  movzx   eax, ax
0x18002431e  or      eax, 80070000h
0x180024323  test    eax, eax
0x180024325  jnz     short loc_180024359
0x180024327  lea     rdx, [rsp+2B0h+var_250]; unsigned __int16 **
0x18002432c  mov     [rsp+2B0h+var_250], r15
0x180024331  lea     rcx, [rsp+2B0h+Name]; pszSrc
0x180024336  call    ?HrCoTaskMemAllocString@@YAJPEAGPEAPEAG@Z; HrCoTaskMemAllocString(ushort *,ushort * *)
0x18002433b  mov     ebx, eax
0x18002433d  test    eax, eax
0x18002433f  js      short loc_180024352
0x180024341  lea     rdx, [rsp+2B0h+var_250]
0x180024346  lea     rcx, [rsp+2B0h+var_268]
0x18002434b  call    ?HrPushBack@?$CUArray@PEAG@@QEAAJAEBQEAG@Z; CUArray<ushort *>::HrPushBack(ushort * const &)
0x180024350  mov     ebx, eax
0x180024352  inc     edi
0x180024354  jmp     loc_1800242CA
0x180024359  mov     rcx, cs:WPP_GLOBAL_Control
0x180024360  cmp     rcx, r13
0x180024363  jz      short loc_18002438B
0x180024365  test    byte ptr [rcx+1Ch], 1
0x180024369  jz      short loc_18002438B
0x18002436b  mov     rcx, [rcx+10h]
0x18002436f  lea     r9, aHrregenumkeyex; "HrRegEnumKeyEx"
0x180024376  mov     edx, 0Dh
0x18002437b  mov     dword ptr [rsp+2B0h+lpReserved], eax
0x18002437f  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180024386  call    WPP_SF_sd
0x18002438b  mov     ebx, r15d
0x18002438e  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180024393  call    cs:__imp_RegCloseKey
0x18002439a  nop     dword ptr [rax+rax+00h]
0x18002439f  mov     edi, [rsp+2B0h+var_260]
0x1800243a3  test    ebx, ebx
0x1800243a5  js      short loc_1800243F2
0x1800243a7  test    edi, edi
0x1800243a9  jz      loc_18002446C
0x1800243af  mov     r8, rsi; void **
0x1800243b2  mov     edx, 8; int
0x1800243b7  mov     ecx, edi; int
0x1800243b9  call    ?HrCoTaskMemAllocArray@@YAJJJPEAPEAX@Z; HrCoTaskMemAllocArray(long,long,void * *)
0x1800243be  mov     ebx, eax
0x1800243c0  test    eax, eax
0x1800243c2  js      short loc_1800243EB
0x1800243c4  mov     r9d, r15d
0x1800243c7  test    edi, edi
0x1800243c9  jle     short loc_1800243EB
0x1800243cb  mov     rax, [rsp+2B0h+var_268]
0x1800243d0  mov     rdx, [rsi]
0x1800243d3  mov     r8d, r9d
0x1800243d6  inc     r9d
0x1800243d9  mov     rcx, [rax+r8*8]
0x1800243dd  mov     [rdx+r8*8], rcx
0x1800243e1  cmp     r9d, edi
0x1800243e4  jl      short loc_1800243CB
0x1800243e6  jmp     loc_18002446F
0x1800243eb  mov     [r14], edi
0x1800243ee  test    eax, eax
0x1800243f0  jns     short loc_180024430
0x1800243f2  mov     [r14], r15d
0x1800243f5  mov     rcx, [rsi]; pv
0x1800243f8  test    rcx, rcx
0x1800243fb  jz      short loc_180024409
0x1800243fd  call    cs:__imp_CoTaskMemFree
0x180024404  nop     dword ptr [rax+rax+00h]
0x180024409  mov     [rsi], r15
0x18002440c  mov     esi, r15d
0x18002440f  test    edi, edi
0x180024411  jle     short loc_180024430
0x180024413  mov     rcx, [rsp+2B0h+var_268]
0x180024418  mov     eax, esi
0x18002441a  mov     rcx, [rcx+rax*8]; pv
0x18002441e  call    cs:__imp_CoTaskMemFree
0x180024425  nop     dword ptr [rax+rax+00h]
0x18002442a  inc     esi
0x18002442c  cmp     esi, edi
0x18002442e  jl      short loc_180024413
0x180024430  test    ebx, ebx
0x180024432  jz      short loc_18002445E
0x180024434  mov     rcx, cs:WPP_GLOBAL_Control
0x18002443b  cmp     rcx, r13
0x18002443e  jz      short loc_18002445E
0x180024440  test    byte ptr [rcx+1Ch], 1
0x180024444  jz      short loc_18002445E
0x180024446  mov     rcx, [rcx+10h]
0x18002444a  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x180024451  mov     edx, 14h
0x180024456  mov     r9d, ebx
0x180024459  call    WPP_SF_d
0x18002445e  mov     rcx, [rsp+2B0h+var_268]; void *
0x180024463  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024468  mov     eax, ebx
0x18002446a  jmp     short loc_180024479
0x18002446c  mov     [rsi], r15
0x18002446f  mov     [r14], edi
0x180024472  jmp     short loc_180024430
0x180024474  mov     eax, 80004003h
0x180024479  mov     rcx, [rbp+1B0h+var_30]
0x180024480  xor     rcx, rsp; StackCookie
0x180024483  call    __security_check_cookie
0x180024488  lea     r11, [rsp+2B0h+var_20]
0x180024490  mov     rbx, [r11+30h]
0x180024494  mov     rsi, [r11+48h]
0x180024498  mov     rsp, r11
0x18002449b  pop     r15
0x18002449d  pop     r14
0x18002449f  pop     r13
0x1800244a1  pop     rdi
0x1800244a2  pop     rbp
0x1800244a3  retn
```

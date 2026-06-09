# CControlPanelFolder::GetCustomAttributes(_ITEMID_CHILD const *,ulong,tagControlPanelCategoryInfo *,ulong *)

- ea: `0x18004a6b0`
- end: `0x18004af08`
- name: `?GetCustomAttributes@CControlPanelFolder@@UEAAJPEBU_ITEMID_CHILD@@KPEAUtagControlPanelCategoryInfo@@PEAK@Z`
- size: `2136`
- prototype: `int(CControlPanelFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned int, struct tagControlPanelCategoryInfo *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800499e4`
- `0x18004a6b0`
- `0x18011611c`
- `0x1801e0300`
- `0x1801eb320`
- `0x180249490`
- `0x18031b228`
- `0x18039ca18`
- `0x18039d698`
- `0x18039f220`
- `0x18039f404`
- `0x18039f4cc`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ac0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ac3d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ac8a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004acb4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004acde`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ad08`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ad32`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ad5c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ad86`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004adb0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004adda`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ae04`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ae2e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ac0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ac3d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ac8a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004acb4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004acde`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ad08`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ad32`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ad5c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ad86`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004adb0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004adda`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ae04`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ae2e`
- `USER32!GetSystemMetrics` at `0x18004a766`
- `USER32!GetSystemMetrics` at `0x18004a766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ac55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ac55`

## pseudocode

```c
__int64 __fastcall CControlPanelFolder::GetCustomAttributes(
        CControlPanelFolder *this,
        const struct _ITEMID_CHILD *a2,
        int a3,
        struct tagControlPanelCategoryInfo *a4,
        unsigned int *a5)
{
  int (__fastcall ***v9)(_QWORD, GUID *, struct IShellFolder **); // rcx
  const struct _tagpropertykey *v10; // r8
  int SystemMetrics; // edi
  const struct _tagpropertykey *v12; // r8
  int v13; // ecx
  int v14; // eax
  bool v15; // zf
  unsigned int v16; // r8d
  bool v17; // dl
  __int64 v18; // r9
  bool IsDigitizerAttached; // al
  GUID *v20; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  LPCWCH lpString1; // [rsp+30h] [rbp-D0h] BYREF
  struct IShellFolder *v23; // [rsp+38h] [rbp-C8h] BYREF
  int v24[12]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String2[48]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v26[6]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v27[6]; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v28[6]; // [rsp+190h] [rbp+90h] BYREF
  _OWORD v29[6]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v30[6]; // [rsp+250h] [rbp+150h] BYREF
  _OWORD v31[6]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _OWORD v32[6]; // [rsp+310h] [rbp+210h] BYREF
  _OWORD v33[6]; // [rsp+370h] [rbp+270h] BYREF
  _OWORD v34[6]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _OWORD v35[6]; // [rsp+430h] [rbp+330h] BYREF
  _OWORD v36[6]; // [rsp+490h] [rbp+390h] BYREF
  _OWORD v37[6]; // [rsp+4F0h] [rbp+3F0h] BYREF

  if ( (a3 & 0x100000) != 0 )
  {
    v9 = (int (__fastcall ***)(_QWORD, GUID *, struct IShellFolder **))*((_QWORD *)this - 5);
    v23 = 0;
    if ( (**v9)(v9, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &v23) >= 0 )
    {
      if ( *((_DWORD *)this + 14) )
      {
        LODWORD(lpString1) = 0;
        if ( a4 )
        {
          v16 = *((_DWORD *)a4 + 12);
          LODWORD(lpString1) = v16;
        }
        else
        {
          if ( GetInt32ArrayProperty((struct IShellFolder2 *)v23, a2, v10, v24, bIgnoreCase, (unsigned int *)&lpString1) < 0 )
            goto LABEL_5;
          v16 = (unsigned int)lpString1;
          a4 = (struct tagControlPanelCategoryInfo *)v24;
        }
        if ( v16 )
        {
          v17 = 0;
          v18 = 0;
          while ( !v17 )
          {
            v17 = *((_DWORD *)a4 + v18) == *((_DWORD *)this + 14);
            v18 = (unsigned int)(v18 + 1);
            if ( (unsigned int)v18 >= v16 )
            {
              if ( !v17 )
                *a5 |= 0x100000u;
              break;
            }
          }
        }
      }
LABEL_5:
      if ( (*a5 & 0x100000) != 0 )
        goto LABEL_23;
      SystemMetrics = GetSystemMetrics(67);
      if ( SystemMetrics > 0 )
      {
        if ( (LODWORD(lpString1) = 0, GetInt32Property((struct IShellFolder2 *)v23, a2, v12, (int *)&lpString1) < 0)
          || SystemMetrics == 1 && ((unsigned __int8)lpString1 & 1) == 0
          || (unsigned int)(SystemMetrics - 2) <= 1 && ((unsigned __int8)lpString1 & 2) == 0 )
        {
          *a5 |= 0x100000u;
        }
      }
      if ( (*a5 & 0x100000) != 0 )
        goto LABEL_23;
      lpString1 = 0;
      if ( DisplayNameOfAsString(v23, a2, 0x8001u, (unsigned __int16 **)&lpString1) < 0 )
        goto LABEL_23;
      wcscpy(String2, L"::{5EA4F148-308C-46D7-98A9-49041B1DD468}");
      wcscpy((wchar_t *)v26, L"::{96AE8D84-A250-4520-95A5-A47A7E3C548B}");
      wcscpy((wchar_t *)v30, L"::{E95A4861-D57A-4BE1-AD0F-35267E261739}");
      wcscpy((wchar_t *)v31, L"::{8060B2E3-C9D7-4A5D-8C6B-CE8EBA111328}");
      wcscpy((wchar_t *)v27, L"::{F82DF8F7-8B9F-442E-A48C-818EA735FF9B}");
      wcscpy((wchar_t *)v28, L"::{80F3F1D5-FECA-45F3-BC32-752C152E456E}");
      wcscpy((wchar_t *)v29, L"::{D17D1D6D-CC3F-4815-8FE3-607E7D5D10B3}");
      wcscpy((wchar_t *)v32, L"::{A0275511-0E86-4ECA-97C2-ECD8F1221D08}");
      wcscpy((wchar_t *)v33, L"::{D9EF8727-CAC2-4e60-809E-86F80A666C91}");
      wcscpy((wchar_t *)v34, L"::{ED834ED6-4B5A-4BFE-8F11-A626DCB6A921}");
      wcscpy((wchar_t *)v35, L"::{BF782CC9-5A52-4A17-806C-2A894FFEEAC5}");
      wcscpy((wchar_t *)v36, L"::{5FFAA809-0961-40CF-90A4-58037867FA50}");
      wcscpy((wchar_t *)v37, L"::{995D28E5-A9C1-4A82-8EFB-C1CE53C06F07}");
      if ( CompareStringOrdinal(lpString1, -1, String2, -1, 1) == 2 )
      {
        v14 = IsMobilityCenterEnabledWithOverride(v13);
LABEL_17:
        v15 = v14 == 0;
        goto LABEL_18;
      }
      if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)v26, -1, 1) == 2 )
        goto LABEL_21;
      if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)v27, -1, 1) == 2 )
      {
        IsDigitizerAttached = CControlPanelFolder::_IsDigitizerAttached();
      }
      else
      {
        if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)v28, -1, 1) == 2 )
        {
          v14 = IsOS_OS_TABLETPC();
          goto LABEL_17;
        }
        if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)v29, -1, 1) == 2 )
        {
          v14 = IsOS_OS_ANYSERVER();
          goto LABEL_17;
        }
        if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)v30, -1, 1) == 2 )
        {
          v20 = &GUID_DEVINTERFACE_SIDESHOW;
        }
        else
        {
          if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)v31, -1, 1) != 2 )
          {
            if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)v32, -1, 1) == 2 )
            {
              IsDigitizerAttached = CControlPanelFolder::_IsIrDASupported();
            }
            else
            {
              if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)v33, -1, 1) != 2 )
              {
                if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)v34, -1, 1) == 2
                  || CompareStringOrdinal(lpString1, -1, (LPCWCH)v35, -1, 1) == 2
                  || CompareStringOrdinal(lpString1, -1, (LPCWCH)v36, -1, 1) == 2 )
                {
                  goto LABEL_21;
                }
                v15 = CompareStringOrdinal(lpString1, -1, (LPCWCH)v37, -1, 1) == 2;
                goto LABEL_18;
              }
              IsDigitizerAttached = CControlPanelFolder::_IsBitLockerOrDeviceEncryptionSupported();
            }
            goto LABEL_47;
          }
          v20 = &GUID_DEVINTERFACE_NFP;
        }
        IsDigitizerAttached = IsDeviceConnected(v20);
      }
LABEL_47:
      v15 = !IsDigitizerAttached;
LABEL_18:
      if ( !v15 )
      {
LABEL_22:
        CoTaskMemFree((LPVOID)lpString1);
LABEL_23:
        ((void (__fastcall *)(struct IShellFolder *))v23->lpVtbl->Release)(v23);
        goto LABEL_2;
      }
LABEL_21:
      *a5 |= 0x100000u;
      goto LABEL_22;
    }
  }
LABEL_2:
  *a5 &= 0xFFFFFFDD;
  return 0;
}

```

## disassembly

```asm
0x18004a6b0  push    rbp
0x18004a6b2  push    rbx
0x18004a6b3  push    rsi
0x18004a6b4  push    rdi
0x18004a6b5  push    r12
0x18004a6b7  push    r13
0x18004a6b9  push    r14
0x18004a6bb  lea     rbp, [rsp-460h]
0x18004a6c3  sub     rsp, 560h
0x18004a6ca  mov     rax, cs:__security_cookie
0x18004a6d1  xor     rax, rsp
0x18004a6d4  mov     [rbp+490h+var_40], rax
0x18004a6db  mov     rbx, [rbp+490h+arg_20]
0x18004a6e2  mov     r12d, 100000h
0x18004a6e8  mov     rdi, r9
0x18004a6eb  mov     r14, rdx
0x18004a6ee  mov     rsi, rcx
0x18004a6f1  test    r12d, r8d
0x18004a6f4  jnz     short loc_18004A71D
0x18004a6f6  and     dword ptr [rbx], 0FFFFFFDDh
0x18004a6f9  xor     eax, eax
0x18004a6fb  mov     rcx, [rbp+490h+var_40]
0x18004a702  xor     rcx, rsp; StackCookie
0x18004a705  call    __security_check_cookie
0x18004a70a  add     rsp, 560h
0x18004a711  pop     r14
0x18004a713  pop     r13
0x18004a715  pop     r12
0x18004a717  pop     rdi
0x18004a718  pop     rsi
0x18004a719  pop     rbx
0x18004a71a  pop     rbp
0x18004a71b  retn
0x18004a71d  mov     rcx, [rcx-28h]
0x18004a721  lea     r8, [rsp+590h+var_558]
0x18004a726  mov     [rsp+590h+var_558], 0
0x18004a72f  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18004a736  mov     rax, [rcx]
0x18004a739  mov     rax, [rax]
0x18004a73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a741  test    eax, eax
0x18004a743  js      short loc_18004A6F6
0x18004a745  cmp     dword ptr [rsi+38h], 0
0x18004a749  mov     r13d, 1
0x18004a74f  jnz     loc_18004AE41
0x18004a755  mov     esi, 2
0x18004a75a  test    [rbx], r12d
0x18004a75d  jnz     loc_18004AC61
0x18004a763  lea     ecx, [rsi+41h]; nIndex
0x18004a766  call    cs:__imp_GetSystemMetrics
0x18004a76d  nop     dword ptr [rax+rax+00h]
0x18004a772  mov     edi, eax
0x18004a774  test    eax, eax
0x18004a776  jle     short loc_18004A7B4
0x18004a778  mov     rcx, [rsp+590h+var_558]; struct IShellFolder2 *
0x18004a77d  lea     r9, [rsp+590h+lpString1]; int *
0x18004a782  mov     rdx, r14; struct _ITEMID_CHILD *
0x18004a785  mov     dword ptr [rsp+590h+lpString1], 0
0x18004a78d  call    ?GetInt32Property@@YAJPEAUIShellFolder2@@PEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAJ@Z; GetInt32Property(IShellFolder2 *,_ITEMID_CHILD const *,_tagpropertykey const &,long *)
0x18004a792  test    eax, eax
0x18004a794  js      short loc_18004A7B1
0x18004a796  cmp     edi, r13d
0x18004a799  jnz     short loc_18004A7A2
0x18004a79b  test    byte ptr [rsp+590h+lpString1], r13b
0x18004a7a0  jz      short loc_18004A7B1
0x18004a7a2  lea     eax, [rdi-2]
0x18004a7a5  cmp     eax, r13d
0x18004a7a8  ja      short loc_18004A7B4
0x18004a7aa  test    byte ptr [rsp+590h+lpString1], sil
0x18004a7af  jnz     short loc_18004A7B4
0x18004a7b1  or      [rbx], r12d
0x18004a7b4  test    [rbx], r12d
0x18004a7b7  jnz     loc_18004AC61
0x18004a7bd  mov     rcx, [rsp+590h+var_558]; struct IShellFolder *
0x18004a7c2  lea     r9, [rsp+590h+lpString1]; unsigned __int16 **
0x18004a7c7  mov     r8d, 8001h; unsigned int
0x18004a7cd  mov     [rsp+590h+lpString1], 0
0x18004a7d6  mov     rdx, r14; struct _ITEMIDLIST_RELATIVE *
0x18004a7d9  call    ?DisplayNameOfAsString@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@KPEAPEAG@Z; DisplayNameOfAsString(IShellFolder *,_ITEMIDLIST_RELATIVE const *,ulong,ushort * *)
0x18004a7de  test    eax, eax
0x18004a7e0  js      loc_18004AC61
0x18004a7e6  movaps  xmm0, xmmword ptr cs:a5ea4f148308c46; "::{5EA4F148-308C-46D7-98A9-49041B1DD468"...
0x18004a7ed  movaps  xmm1, xmmword ptr cs:a5ea4f148308c46+10h; "148-308C-46D7-98A9-49041B1DD468}"
0x18004a7f4  movzx   eax, word ptr cs:a5ea4f148308c46+50h; ""
0x18004a7fb  movaps  xmmword ptr [rsp+590h+String2], xmm0
0x18004a800  movaps  xmm0, xmmword ptr cs:a5ea4f148308c46+20h; "-46D7-98A9-49041B1DD468}"
0x18004a807  movaps  [rbp+490h+var_500], xmm0
0x18004a80b  movaps  xmm0, xmmword ptr cs:a5ea4f148308c46+40h; "B1DD468}"
0x18004a812  movaps  [rbp+490h+var_4E0], xmm0
0x18004a816  movaps  xmm0, xmmword ptr cs:a96ae8d84A25045; "::{96AE8D84-A250-4520-95A5-A47A7E3C548B"...
0x18004a81d  movaps  xmmword ptr [rbp+490h+var_4C0], xmm0
0x18004a821  movaps  xmm0, xmmword ptr cs:a96ae8d84A25045+20h; "-4520-95A5-A47A7E3C548B}"
0x18004a828  movaps  xmmword ptr [rbp+490h+var_4C0+20h], xmm0
0x18004a82c  movaps  xmm0, xmmword ptr cs:a96ae8d84A25045+40h; "E3C548B}"
0x18004a833  movaps  [rbp+490h+var_480], xmm0
0x18004a837  movaps  xmm0, xmmword ptr cs:aE95a4861D57a4b_0; "::{E95A4861-D57A-4BE1-AD0F-35267E261739"...
0x18004a83e  movaps  xmmword ptr [rbp+490h+var_340], xmm0
0x18004a845  movaps  xmm0, xmmword ptr cs:aE95a4861D57a4b_0+20h; "-4BE1-AD0F-35267E261739}"
0x18004a84c  movaps  [rbp+490h+var_510], xmm1
0x18004a850  movaps  xmm1, xmmword ptr cs:a5ea4f148308c46+30h; "A9-49041B1DD468}"
0x18004a857  movaps  xmmword ptr [rbp+490h+var_340+20h], xmm0
0x18004a85e  movaps  xmm0, xmmword ptr cs:aE95a4861D57a4b_0+40h; "E261739}"
0x18004a865  movaps  [rbp+490h+var_4F0], xmm1
0x18004a869  movaps  xmm1, xmmword ptr cs:a96ae8d84A25045+10h; "D84-A250-4520-95A5-A47A7E3C548B}"
0x18004a870  movaps  [rbp+490h+var_300], xmm0
0x18004a877  movaps  xmm0, xmmword ptr cs:a8060b2e3C9d74a; "::{8060B2E3-C9D7-4A5D-8C6B-CE8EBA111328"...
0x18004a87e  movaps  xmmword ptr [rbp+490h+var_4C0+10h], xmm1
0x18004a882  movaps  xmm1, xmmword ptr cs:a96ae8d84A25045+30h; "A5-A47A7E3C548B}"
0x18004a889  movaps  xmmword ptr [rbp+490h+var_2E0], xmm0
0x18004a890  movaps  xmm0, xmmword ptr cs:a8060b2e3C9d74a+20h; "-4A5D-8C6B-CE8EBA111328}"
0x18004a897  movaps  [rbp+490h+var_490], xmm1
0x18004a89b  movaps  xmm1, xmmword ptr cs:aE95a4861D57a4b_0+10h; "861-D57A-4BE1-AD0F-35267E261739}"
0x18004a8a2  movaps  xmmword ptr [rbp+490h+var_2E0+20h], xmm0
0x18004a8a9  movaps  xmm0, xmmword ptr cs:a8060b2e3C9d74a+40h; "A111328}"
0x18004a8b0  movaps  xmmword ptr [rbp+490h+var_340+10h], xmm1
0x18004a8b7  movaps  xmm1, xmmword ptr cs:aE95a4861D57a4b_0+30h; "0F-35267E261739}"
0x18004a8be  movaps  [rbp+490h+var_2A0], xmm0
0x18004a8c5  movaps  xmm0, xmmword ptr cs:aF82df8f78b9f44; "::{F82DF8F7-8B9F-442E-A48C-818EA735FF9B"...
0x18004a8cc  movaps  [rbp+490h+var_310], xmm1
0x18004a8d3  movaps  xmm1, xmmword ptr cs:a8060b2e3C9d74a+10h; "2E3-C9D7-4A5D-8C6B-CE8EBA111328}"
0x18004a8da  movaps  xmmword ptr [rbp+490h+var_460], xmm0
0x18004a8de  movaps  xmm0, xmmword ptr cs:aF82df8f78b9f44+20h; "-442E-A48C-818EA735FF9B}"
0x18004a8e5  movaps  xmmword ptr [rbp+490h+var_2E0+10h], xmm1
0x18004a8ec  movaps  xmm1, xmmword ptr cs:a8060b2e3C9d74a+30h; "6B-CE8EBA111328}"
0x18004a8f3  movaps  xmmword ptr [rbp+490h+var_460+20h], xmm0
0x18004a8f7  movaps  xmm0, xmmword ptr cs:aF82df8f78b9f44+40h; "735FF9B}"
0x18004a8fe  movaps  [rbp+490h+var_2B0], xmm1
0x18004a905  movaps  xmm1, xmmword ptr cs:aF82df8f78b9f44+10h; "8F7-8B9F-442E-A48C-818EA735FF9B}"
0x18004a90c  movaps  [rbp+490h+var_420], xmm0
0x18004a910  movaps  xmm0, xmmword ptr cs:a80f3f1d5Feca45_0; "::{80F3F1D5-FECA-45F3-BC32-752C152E456E"...
0x18004a917  mov     [rbp+490h+var_4D0], ax
0x18004a91b  movzx   eax, word ptr cs:a96ae8d84A25045+50h; ""
0x18004a922  movaps  xmmword ptr [rbp+490h+var_460+10h], xmm1
0x18004a926  movaps  xmm1, xmmword ptr cs:aF82df8f78b9f44+30h; "8C-818EA735FF9B}"
0x18004a92d  movaps  xmmword ptr [rbp+490h+var_400], xmm0
0x18004a934  movaps  xmm0, xmmword ptr cs:a80f3f1d5Feca45_0+20h; "-45F3-BC32-752C152E456E}"
0x18004a93b  mov     [rbp+490h+var_470], ax
0x18004a93f  movzx   eax, word ptr cs:aE95a4861D57a4b_0+50h; ""
0x18004a946  movaps  [rbp+490h+var_430], xmm1
0x18004a94a  movaps  xmm1, xmmword ptr cs:a80f3f1d5Feca45_0+10h; "1D5-FECA-45F3-BC32-752C152E456E}"
0x18004a951  movaps  xmmword ptr [rbp+490h+var_400+20h], xmm0
0x18004a958  movaps  xmm0, xmmword ptr cs:a80f3f1d5Feca45_0+40h; "52E456E}"
0x18004a95f  mov     [rbp+490h+var_2F0], ax
0x18004a966  movzx   eax, word ptr cs:a8060b2e3C9d74a+50h; ""
0x18004a96d  movaps  xmmword ptr [rbp+490h+var_400+10h], xmm1
0x18004a974  movaps  xmm1, xmmword ptr cs:a80f3f1d5Feca45_0+30h; "32-752C152E456E}"
0x18004a97b  movaps  [rbp+490h+var_3C0], xmm0
0x18004a982  movaps  xmm0, xmmword ptr cs:aD17d1d6dCc3f48; "::{D17D1D6D-CC3F-4815-8FE3-607E7D5D10B3"...
0x18004a989  mov     [rbp+490h+var_290], ax
0x18004a990  movzx   eax, word ptr cs:aF82df8f78b9f44+50h; ""
0x18004a997  movaps  [rbp+490h+var_3D0], xmm1
0x18004a99e  movaps  xmm1, xmmword ptr cs:aD17d1d6dCc3f48+10h; "D6D-CC3F-4815-8FE3-607E7D5D10B3}"
0x18004a9a5  movaps  xmmword ptr [rbp+490h+var_3A0], xmm0
0x18004a9ac  movaps  xmm0, xmmword ptr cs:aD17d1d6dCc3f48+20h; "-4815-8FE3-607E7D5D10B3}"
0x18004a9b3  mov     [rbp+490h+var_410], ax
0x18004a9ba  movzx   eax, word ptr cs:a80f3f1d5Feca45_0+50h; ""
0x18004a9c1  movaps  xmmword ptr [rbp+490h+var_3A0+10h], xmm1
0x18004a9c8  movaps  xmm1, xmmword ptr cs:aD17d1d6dCc3f48+30h; "E3-607E7D5D10B3}"
0x18004a9cf  movaps  xmmword ptr [rbp+490h+var_3A0+20h], xmm0
0x18004a9d6  movaps  xmm0, xmmword ptr cs:aD17d1d6dCc3f48+40h; "D5D10B3}"
0x18004a9dd  mov     [rbp+490h+var_3B0], ax
0x18004a9e4  movaps  [rbp+490h+var_370], xmm1
0x18004a9eb  movaps  xmm1, xmmword ptr cs:aA02755110e864e+10h; "511-0E86-4ECA-97C2-ECD8F1221D08}"
0x18004a9f2  lea     r8, [rsp+590h+String2]; lpString2
0x18004a9f7  movzx   eax, word ptr cs:aD17d1d6dCc3f48+50h; ""
0x18004a9fe  or      edi, 0FFFFFFFFh
0x18004aa01  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004aa06  mov     r9d, edi; cchCount2
0x18004aa09  movaps  [rbp+490h+var_360], xmm0
0x18004aa10  mov     edx, edi; cchCount1
0x18004aa12  movaps  xmm0, xmmword ptr cs:aA02755110e864e; "::{A0275511-0E86-4ECA-97C2-ECD8F1221D08"...
0x18004aa19  movaps  xmmword ptr [rbp+490h+var_280], xmm0
0x18004aa20  movaps  xmm0, xmmword ptr cs:aA02755110e864e+20h; "-4ECA-97C2-ECD8F1221D08}"
0x18004aa27  movaps  xmmword ptr [rbp+490h+var_280+20h], xmm0
0x18004aa2e  movaps  xmm0, xmmword ptr cs:aA02755110e864e+40h; "1221D08}"
0x18004aa35  movaps  [rbp+490h+var_240], xmm0
0x18004aa3c  movaps  xmm0, xmmword ptr cs:aD9ef8727Cac24e_0; "::{D9EF8727-CAC2-4e60-809E-86F80A666C91"...
0x18004aa43  movaps  xmmword ptr [rbp+490h+var_220], xmm0
0x18004aa4a  movaps  xmm0, xmmword ptr cs:aD9ef8727Cac24e_0+20h; "-4e60-809E-86F80A666C91}"
0x18004aa51  movaps  xmmword ptr [rbp+490h+var_220+20h], xmm0
0x18004aa58  movaps  xmm0, xmmword ptr cs:aD9ef8727Cac24e_0+40h; "A666C91}"
0x18004aa5f  movaps  [rbp+490h+var_1E0], xmm0
0x18004aa66  movaps  xmm0, xmmword ptr cs:aEd834ed64b5a4b; "::{ED834ED6-4B5A-4BFE-8F11-A626DCB6A921"...
0x18004aa6d  movaps  xmmword ptr [rbp+490h+var_1C0], xmm0
0x18004aa74  movaps  xmm0, xmmword ptr cs:aEd834ed64b5a4b+20h; "-4BFE-8F11-A626DCB6A921}"
0x18004aa7b  movaps  xmmword ptr [rbp+490h+var_280+10h], xmm1
0x18004aa82  movaps  xmm1, xmmword ptr cs:aA02755110e864e+30h; "C2-ECD8F1221D08}"
0x18004aa89  movaps  xmmword ptr [rbp+490h+var_1C0+20h], xmm0
0x18004aa90  movaps  xmm0, xmmword ptr cs:aEd834ed64b5a4b+40h; "CB6A921}"
0x18004aa97  movaps  [rbp+490h+var_250], xmm1
0x18004aa9e  movaps  xmm1, xmmword ptr cs:aD9ef8727Cac24e_0+10h; "727-CAC2-4e60-809E-86F80A666C91}"
0x18004aaa5  movaps  [rbp+490h+var_180], xmm0
0x18004aaac  movaps  xmm0, xmmword ptr cs:aBf782cc95a524a; "::{BF782CC9-5A52-4A17-806C-2A894FFEEAC5"...
0x18004aab3  movaps  xmmword ptr [rbp+490h+var_220+10h], xmm1
0x18004aaba  movaps  xmm1, xmmword ptr cs:aD9ef8727Cac24e_0+30h; "9E-86F80A666C91}"
0x18004aac1  movaps  xmmword ptr [rbp+490h+var_160], xmm0
0x18004aac8  movaps  xmm0, xmmword ptr cs:aBf782cc95a524a+20h; "-4A17-806C-2A894FFEEAC5}"
0x18004aacf  movaps  [rbp+490h+var_1F0], xmm1
0x18004aad6  movaps  xmm1, xmmword ptr cs:aEd834ed64b5a4b+10h; "ED6-4B5A-4BFE-8F11-A626DCB6A921}"
0x18004aadd  movaps  xmmword ptr [rbp+490h+var_160+20h], xmm0
0x18004aae4  movaps  xmm0, xmmword ptr cs:aBf782cc95a524a+40h; "FFEEAC5}"
0x18004aaeb  movaps  xmmword ptr [rbp+490h+var_1C0+10h], xmm1
0x18004aaf2  movaps  xmm1, xmmword ptr cs:aEd834ed64b5a4b+30h; "11-A626DCB6A921}"
0x18004aaf9  movaps  [rbp+490h+var_120], xmm0
0x18004ab00  movaps  xmm0, xmmword ptr cs:a5ffaa809096140; "::{5FFAA809-0961-40CF-90A4-58037867FA50"...
0x18004ab07  mov     [rbp+490h+var_350], ax
0x18004ab0e  movzx   eax, word ptr cs:aA02755110e864e+50h; ""
0x18004ab15  movaps  [rbp+490h+var_190], xmm1
0x18004ab1c  movaps  xmm1, xmmword ptr cs:aBf782cc95a524a+10h; "CC9-5A52-4A17-806C-2A894FFEEAC5}"
0x18004ab23  movaps  xmmword ptr [rbp+490h+var_100], xmm0
0x18004ab2a  movaps  xmm0, xmmword ptr cs:a5ffaa809096140+20h; "-40CF-90A4-58037867FA50}"
0x18004ab31  mov     [rbp+490h+var_230], ax
0x18004ab38  movzx   eax, word ptr cs:aD9ef8727Cac24e_0+50h; ""
0x18004ab3f  movaps  xmmword ptr [rbp+490h+var_160+10h], xmm1
0x18004ab46  movaps  xmm1, xmmword ptr cs:aBf782cc95a524a+30h; "6C-2A894FFEEAC5}"
0x18004ab4d  movaps  xmmword ptr [rbp+490h+var_100+20h], xmm0
0x18004ab54  movaps  xmm0, xmmword ptr cs:a5ffaa809096140+40h; "867FA50}"
0x18004ab5b  mov     [rbp+490h+var_1D0], ax
0x18004ab62  movzx   eax, word ptr cs:aEd834ed64b5a4b+50h; ""
0x18004ab69  movaps  [rbp+490h+var_130], xmm1
0x18004ab70  movaps  xmm1, xmmword ptr cs:a5ffaa809096140+10h; "809-0961-40CF-90A4-58037867FA50}"
0x18004ab77  movaps  [rbp+490h+var_C0], xmm0
0x18004ab7e  movaps  xmm0, xmmword ptr cs:a995d28e5A9c14a; "::{995D28E5-A9C1-4A82-8EFB-C1CE53C06F07"...
0x18004ab85  mov     [rbp+490h+var_170], ax
0x18004ab8c  movzx   eax, word ptr cs:aBf782cc95a524a+50h; ""
0x18004ab93  movaps  xmmword ptr [rbp+490h+var_100+10h], xmm1
0x18004ab9a  movaps  xmm1, xmmword ptr cs:a5ffaa809096140+30h; "A4-58037867FA50}"
0x18004aba1  movaps  xmmword ptr [rbp+490h+var_A0], xmm0
0x18004aba8  movaps  xmm0, xmmword ptr cs:a995d28e5A9c14a+20h; "-4A82-8EFB-C1CE53C06F07}"
0x18004abaf  mov     [rbp+490h+var_110], ax
0x18004abb6  movzx   eax, word ptr cs:a5ffaa809096140+50h; ""
0x18004abbd  movaps  [rbp+490h+var_D0], xmm1
0x18004abc4  movaps  xmm1, xmmword ptr cs:a995d28e5A9c14a+10h; "8E5-A9C1-4A82-8EFB-C1CE53C06F07}"
0x18004abcb  movaps  xmmword ptr [rbp+490h+var_A0+20h], xmm0
0x18004abd2  movaps  xmm0, xmmword ptr cs:a995d28e5A9c14a+40h; "3C06F07}"
0x18004abd9  mov     [rbp+490h+var_B0], ax
0x18004abe0  movzx   eax, word ptr cs:a995d28e5A9c14a+50h; ""
0x18004abe7  movaps  xmmword ptr [rbp+490h+var_A0+10h], xmm1
0x18004abee  movaps  xmm1, xmmword ptr cs:a995d28e5A9c14a+30h; "FB-C1CE53C06F07}"
0x18004abf5  movaps  [rbp+490h+var_60], xmm0
0x18004abfc  movaps  [rbp+490h+var_70], xmm1
0x18004ac03  mov     [rbp+490h+var_50], ax
0x18004ac0a  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004ac0f  call    cs:__imp_CompareStringOrdinal
0x18004ac16  nop     dword ptr [rax+rax+00h]
0x18004ac1b  cmp     eax, esi
0x18004ac1d  jnz     short loc_18004AC2A
0x18004ac1f  call    ?IsMobilityCenterEnabledWithOverride@@YAHH@Z; IsMobilityCenterEnabledWithOverride(int)
0x18004ac24  test    eax, eax
0x18004ac26  jnz     short loc_18004AC50
0x18004ac28  jmp     short loc_18004AC4D
0x18004ac2a  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004ac2f  lea     r8, [rbp+490h+var_4C0]; lpString2
0x18004ac33  mov     r9d, edi; cchCount2
0x18004ac36  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004ac3b  mov     edx, edi; cchCount1
0x18004ac3d  call    cs:__imp_CompareStringOrdinal
0x18004ac44  nop     dword ptr [rax+rax+00h]
0x18004ac49  cmp     eax, esi
0x18004ac4b  jnz     short loc_18004AC77
0x18004ac4d  or      [rbx], r12d
0x18004ac50  mov     rcx, [rsp+590h+lpString1]; pv
0x18004ac55  call    cs:__imp_CoTaskMemFree
0x18004ac5c  nop     dword ptr [rax+rax+00h]
0x18004ac61  mov     rcx, [rsp+590h+var_558]
0x18004ac66  mov     rax, [rcx]
0x18004ac69  mov     rax, [rax+10h]
0x18004ac6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac72  jmp     loc_18004A6F6
0x18004ac77  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004ac7c  lea     r8, [rbp+490h+var_460]; lpString2
0x18004ac80  mov     r9d, edi; cchCount2
0x18004ac83  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004ac88  mov     edx, edi; cchCount1
0x18004ac8a  call    cs:__imp_CompareStringOrdinal
0x18004ac91  nop     dword ptr [rax+rax+00h]
0x18004ac96  cmp     eax, esi
0x18004ac98  jz      loc_18004AEC3
0x18004ac9e  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004aca3  lea     r8, [rbp+490h+var_400]; lpString2
0x18004acaa  mov     r9d, edi; cchCount2
0x18004acad  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004acb2  mov     edx, edi; cchCount1
0x18004acb4  call    cs:__imp_CompareStringOrdinal
0x18004acbb  nop     dword ptr [rax+rax+00h]
0x18004acc0  cmp     eax, esi
0x18004acc2  jz      loc_18004AED6
0x18004acc8  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004accd  lea     r8, [rbp+490h+var_3A0]; lpString2
0x18004acd4  mov     r9d, edi; cchCount2
0x18004acd7  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004acdc  mov     edx, edi; cchCount1
0x18004acde  call    cs:__imp_CompareStringOrdinal
0x18004ace5  nop     dword ptr [rax+rax+00h]
0x18004acea  cmp     eax, esi
0x18004acec  jz      loc_18004AEE0
0x18004acf2  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004acf7  lea     r8, [rbp+490h+var_340]; lpString2
0x18004acfe  mov     r9d, edi; cchCount2
0x18004ad01  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
  ... truncated ...
```

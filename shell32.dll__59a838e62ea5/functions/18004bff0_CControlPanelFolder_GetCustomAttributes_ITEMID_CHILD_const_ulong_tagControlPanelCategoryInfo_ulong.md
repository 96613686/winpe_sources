# CControlPanelFolder::GetCustomAttributes(_ITEMID_CHILD const *,ulong,tagControlPanelCategoryInfo *,ulong *)

- ea: `0x18004bff0`
- end: `0x18004c7ed`
- name: `?GetCustomAttributes@CControlPanelFolder@@UEAAJPEBU_ITEMID_CHILD@@KPEAUtagControlPanelCategoryInfo@@PEAK@Z`
- size: `2045`
- prototype: `int(CControlPanelFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned int, struct tagControlPanelCategoryInfo *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18004bc80`
- `0x18004bff0`
- `0x180107838`
- `0x1801c9dcc`
- `0x1801d41ec`
- `0x180233280`
- `0x1802faf70`
- `0x1803776f8`
- `0x180378270`
- `0x180379cd8`
- `0x180379eb4`
- `0x180379f70`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c548`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c570`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c5b1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c5d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c5f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c61d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c641`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c665`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c689`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c6ad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c6d1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c6f5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c719`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c548`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c570`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c5b1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c5d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c5f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c61d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c641`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c665`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c689`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c6ad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c6d1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c6f5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c719`
- `USER32!GetSystemMetrics` at `0x18004c0a5`
- `USER32!GetSystemMetrics` at `0x18004c0a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c582`

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
0x18004bff0  push    rbp
0x18004bff2  push    rbx
0x18004bff3  push    rsi
0x18004bff4  push    rdi
0x18004bff5  push    r12
0x18004bff7  push    r13
0x18004bff9  push    r14
0x18004bffb  lea     rbp, [rsp-460h]
0x18004c003  sub     rsp, 560h
0x18004c00a  mov     rax, cs:__security_cookie
0x18004c011  xor     rax, rsp
0x18004c014  mov     [rbp+490h+var_40], rax
0x18004c01b  mov     rbx, [rbp+490h+arg_20]
0x18004c022  mov     r12d, 100000h
0x18004c028  mov     rdi, r9
0x18004c02b  mov     r14, rdx
0x18004c02e  mov     rsi, rcx
0x18004c031  test    r12d, r8d
0x18004c034  jnz     short loc_18004C05C
0x18004c036  and     dword ptr [rbx], 0FFFFFFDDh
0x18004c039  xor     eax, eax
0x18004c03b  mov     rcx, [rbp+490h+var_40]
0x18004c042  xor     rcx, rsp; StackCookie
0x18004c045  call    __security_check_cookie
0x18004c04a  add     rsp, 560h
0x18004c051  pop     r14
0x18004c053  pop     r13
0x18004c055  pop     r12
0x18004c057  pop     rdi
0x18004c058  pop     rsi
0x18004c059  pop     rbx
0x18004c05a  pop     rbp
0x18004c05b  retn
0x18004c05c  mov     rcx, [rcx-28h]
0x18004c060  lea     r8, [rsp+590h+var_558]
0x18004c065  mov     [rsp+590h+var_558], 0
0x18004c06e  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18004c075  mov     rax, [rcx]
0x18004c078  mov     rax, [rax]
0x18004c07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c080  test    eax, eax
0x18004c082  js      short loc_18004C036
0x18004c084  cmp     dword ptr [rsi+38h], 0
0x18004c088  mov     r13d, 1
0x18004c08e  jnz     loc_18004C726
0x18004c094  mov     esi, 2
0x18004c099  test    [rbx], r12d
0x18004c09c  jnz     loc_18004C588
0x18004c0a2  lea     ecx, [rsi+41h]; nIndex
0x18004c0a5  call    cs:__imp_GetSystemMetrics
0x18004c0ab  mov     edi, eax
0x18004c0ad  test    eax, eax
0x18004c0af  jle     short loc_18004C0ED
0x18004c0b1  mov     rcx, [rsp+590h+var_558]; struct IShellFolder2 *
0x18004c0b6  lea     r9, [rsp+590h+lpString1]; int *
0x18004c0bb  mov     rdx, r14; struct _ITEMID_CHILD *
0x18004c0be  mov     dword ptr [rsp+590h+lpString1], 0
0x18004c0c6  call    ?GetInt32Property@@YAJPEAUIShellFolder2@@PEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAJ@Z; GetInt32Property(IShellFolder2 *,_ITEMID_CHILD const *,_tagpropertykey const &,long *)
0x18004c0cb  test    eax, eax
0x18004c0cd  js      short loc_18004C0EA
0x18004c0cf  cmp     edi, r13d
0x18004c0d2  jnz     short loc_18004C0DB
0x18004c0d4  test    byte ptr [rsp+590h+lpString1], r13b
0x18004c0d9  jz      short loc_18004C0EA
0x18004c0db  lea     eax, [rdi-2]
0x18004c0de  cmp     eax, r13d
0x18004c0e1  ja      short loc_18004C0ED
0x18004c0e3  test    byte ptr [rsp+590h+lpString1], sil
0x18004c0e8  jnz     short loc_18004C0ED
0x18004c0ea  or      [rbx], r12d
0x18004c0ed  test    [rbx], r12d
0x18004c0f0  jnz     loc_18004C588
0x18004c0f6  mov     rcx, [rsp+590h+var_558]; struct IShellFolder *
0x18004c0fb  lea     r9, [rsp+590h+lpString1]; unsigned __int16 **
0x18004c100  mov     r8d, 8001h; unsigned int
0x18004c106  mov     [rsp+590h+lpString1], 0
0x18004c10f  mov     rdx, r14; struct _ITEMIDLIST_RELATIVE *
0x18004c112  call    ?DisplayNameOfAsString@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@KPEAPEAG@Z; DisplayNameOfAsString(IShellFolder *,_ITEMIDLIST_RELATIVE const *,ulong,ushort * *)
0x18004c117  test    eax, eax
0x18004c119  js      loc_18004C588
0x18004c11f  movaps  xmm0, xmmword ptr cs:a5ea4f148308c46; "::{5EA4F148-308C-46D7-98A9-49041B1DD468"...
0x18004c126  movaps  xmm1, xmmword ptr cs:a5ea4f148308c46+10h; "148-308C-46D7-98A9-49041B1DD468}"
0x18004c12d  movzx   eax, word ptr cs:a5ea4f148308c46+50h; ""
0x18004c134  movaps  xmmword ptr [rsp+590h+String2], xmm0
0x18004c139  movaps  xmm0, xmmword ptr cs:a5ea4f148308c46+20h; "-46D7-98A9-49041B1DD468}"
0x18004c140  movaps  [rbp+490h+var_500], xmm0
0x18004c144  movaps  xmm0, xmmword ptr cs:a5ea4f148308c46+40h; "B1DD468}"
0x18004c14b  movaps  [rbp+490h+var_4E0], xmm0
0x18004c14f  movaps  xmm0, xmmword ptr cs:a96ae8d84A25045; "::{96AE8D84-A250-4520-95A5-A47A7E3C548B"...
0x18004c156  movaps  xmmword ptr [rbp+490h+var_4C0], xmm0
0x18004c15a  movaps  xmm0, xmmword ptr cs:a96ae8d84A25045+20h; "-4520-95A5-A47A7E3C548B}"
0x18004c161  movaps  xmmword ptr [rbp+490h+var_4C0+20h], xmm0
0x18004c165  movaps  xmm0, xmmword ptr cs:a96ae8d84A25045+40h; "E3C548B}"
0x18004c16c  movaps  [rbp+490h+var_480], xmm0
0x18004c170  movaps  xmm0, xmmword ptr cs:aE95a4861D57a4b_0; "::{E95A4861-D57A-4BE1-AD0F-35267E261739"...
0x18004c177  movaps  xmmword ptr [rbp+490h+var_340], xmm0
0x18004c17e  movaps  xmm0, xmmword ptr cs:aE95a4861D57a4b_0+20h; "-4BE1-AD0F-35267E261739}"
0x18004c185  movaps  [rbp+490h+var_510], xmm1
0x18004c189  movaps  xmm1, xmmword ptr cs:a5ea4f148308c46+30h; "A9-49041B1DD468}"
0x18004c190  movaps  xmmword ptr [rbp+490h+var_340+20h], xmm0
0x18004c197  movaps  xmm0, xmmword ptr cs:aE95a4861D57a4b_0+40h; "E261739}"
0x18004c19e  movaps  [rbp+490h+var_4F0], xmm1
0x18004c1a2  movaps  xmm1, xmmword ptr cs:a96ae8d84A25045+10h; "D84-A250-4520-95A5-A47A7E3C548B}"
0x18004c1a9  movaps  [rbp+490h+var_300], xmm0
0x18004c1b0  movaps  xmm0, xmmword ptr cs:a8060b2e3C9d74a; "::{8060B2E3-C9D7-4A5D-8C6B-CE8EBA111328"...
0x18004c1b7  movaps  xmmword ptr [rbp+490h+var_4C0+10h], xmm1
0x18004c1bb  movaps  xmm1, xmmword ptr cs:a96ae8d84A25045+30h; "A5-A47A7E3C548B}"
0x18004c1c2  movaps  xmmword ptr [rbp+490h+var_2E0], xmm0
0x18004c1c9  movaps  xmm0, xmmword ptr cs:a8060b2e3C9d74a+20h; "-4A5D-8C6B-CE8EBA111328}"
0x18004c1d0  movaps  [rbp+490h+var_490], xmm1
0x18004c1d4  movaps  xmm1, xmmword ptr cs:aE95a4861D57a4b_0+10h; "861-D57A-4BE1-AD0F-35267E261739}"
0x18004c1db  movaps  xmmword ptr [rbp+490h+var_2E0+20h], xmm0
0x18004c1e2  movaps  xmm0, xmmword ptr cs:a8060b2e3C9d74a+40h; "A111328}"
0x18004c1e9  movaps  xmmword ptr [rbp+490h+var_340+10h], xmm1
0x18004c1f0  movaps  xmm1, xmmword ptr cs:aE95a4861D57a4b_0+30h; "0F-35267E261739}"
0x18004c1f7  movaps  [rbp+490h+var_2A0], xmm0
0x18004c1fe  movaps  xmm0, xmmword ptr cs:aF82df8f78b9f44; "::{F82DF8F7-8B9F-442E-A48C-818EA735FF9B"...
0x18004c205  movaps  [rbp+490h+var_310], xmm1
0x18004c20c  movaps  xmm1, xmmword ptr cs:a8060b2e3C9d74a+10h; "2E3-C9D7-4A5D-8C6B-CE8EBA111328}"
0x18004c213  movaps  xmmword ptr [rbp+490h+var_460], xmm0
0x18004c217  movaps  xmm0, xmmword ptr cs:aF82df8f78b9f44+20h; "-442E-A48C-818EA735FF9B}"
0x18004c21e  movaps  xmmword ptr [rbp+490h+var_2E0+10h], xmm1
0x18004c225  movaps  xmm1, xmmword ptr cs:a8060b2e3C9d74a+30h; "6B-CE8EBA111328}"
0x18004c22c  movaps  xmmword ptr [rbp+490h+var_460+20h], xmm0
0x18004c230  movaps  xmm0, xmmword ptr cs:aF82df8f78b9f44+40h; "735FF9B}"
0x18004c237  movaps  [rbp+490h+var_2B0], xmm1
0x18004c23e  movaps  xmm1, xmmword ptr cs:aF82df8f78b9f44+10h; "8F7-8B9F-442E-A48C-818EA735FF9B}"
0x18004c245  movaps  [rbp+490h+var_420], xmm0
0x18004c249  movaps  xmm0, xmmword ptr cs:a80f3f1d5Feca45_0; "::{80F3F1D5-FECA-45F3-BC32-752C152E456E"...
0x18004c250  mov     [rbp+490h+var_4D0], ax
0x18004c254  movzx   eax, word ptr cs:a96ae8d84A25045+50h; ""
0x18004c25b  movaps  xmmword ptr [rbp+490h+var_460+10h], xmm1
0x18004c25f  movaps  xmm1, xmmword ptr cs:aF82df8f78b9f44+30h; "8C-818EA735FF9B}"
0x18004c266  movaps  xmmword ptr [rbp+490h+var_400], xmm0
0x18004c26d  movaps  xmm0, xmmword ptr cs:a80f3f1d5Feca45_0+20h; "-45F3-BC32-752C152E456E}"
0x18004c274  mov     [rbp+490h+var_470], ax
0x18004c278  movzx   eax, word ptr cs:aE95a4861D57a4b_0+50h; ""
0x18004c27f  movaps  [rbp+490h+var_430], xmm1
0x18004c283  movaps  xmm1, xmmword ptr cs:a80f3f1d5Feca45_0+10h; "1D5-FECA-45F3-BC32-752C152E456E}"
0x18004c28a  movaps  xmmword ptr [rbp+490h+var_400+20h], xmm0
0x18004c291  movaps  xmm0, xmmword ptr cs:a80f3f1d5Feca45_0+40h; "52E456E}"
0x18004c298  mov     [rbp+490h+var_2F0], ax
0x18004c29f  movzx   eax, word ptr cs:a8060b2e3C9d74a+50h; ""
0x18004c2a6  movaps  xmmword ptr [rbp+490h+var_400+10h], xmm1
0x18004c2ad  movaps  xmm1, xmmword ptr cs:a80f3f1d5Feca45_0+30h; "32-752C152E456E}"
0x18004c2b4  movaps  [rbp+490h+var_3C0], xmm0
0x18004c2bb  movaps  xmm0, xmmword ptr cs:aD17d1d6dCc3f48; "::{D17D1D6D-CC3F-4815-8FE3-607E7D5D10B3"...
0x18004c2c2  mov     [rbp+490h+var_290], ax
0x18004c2c9  movzx   eax, word ptr cs:aF82df8f78b9f44+50h; ""
0x18004c2d0  movaps  [rbp+490h+var_3D0], xmm1
0x18004c2d7  movaps  xmm1, xmmword ptr cs:aD17d1d6dCc3f48+10h; "D6D-CC3F-4815-8FE3-607E7D5D10B3}"
0x18004c2de  movaps  xmmword ptr [rbp+490h+var_3A0], xmm0
0x18004c2e5  movaps  xmm0, xmmword ptr cs:aD17d1d6dCc3f48+20h; "-4815-8FE3-607E7D5D10B3}"
0x18004c2ec  mov     [rbp+490h+var_410], ax
0x18004c2f3  movzx   eax, word ptr cs:a80f3f1d5Feca45_0+50h; ""
0x18004c2fa  movaps  xmmword ptr [rbp+490h+var_3A0+10h], xmm1
0x18004c301  movaps  xmm1, xmmword ptr cs:aD17d1d6dCc3f48+30h; "E3-607E7D5D10B3}"
0x18004c308  movaps  xmmword ptr [rbp+490h+var_3A0+20h], xmm0
0x18004c30f  movaps  xmm0, xmmword ptr cs:aD17d1d6dCc3f48+40h; "D5D10B3}"
0x18004c316  mov     [rbp+490h+var_3B0], ax
0x18004c31d  movaps  [rbp+490h+var_370], xmm1
0x18004c324  movaps  xmm1, xmmword ptr cs:aA02755110e864e+10h; "511-0E86-4ECA-97C2-ECD8F1221D08}"
0x18004c32b  lea     r8, [rsp+590h+String2]; lpString2
0x18004c330  movzx   eax, word ptr cs:aD17d1d6dCc3f48+50h; ""
0x18004c337  or      edi, 0FFFFFFFFh
0x18004c33a  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004c33f  mov     r9d, edi; cchCount2
0x18004c342  movaps  [rbp+490h+var_360], xmm0
0x18004c349  mov     edx, edi; cchCount1
0x18004c34b  movaps  xmm0, xmmword ptr cs:aA02755110e864e; "::{A0275511-0E86-4ECA-97C2-ECD8F1221D08"...
0x18004c352  movaps  xmmword ptr [rbp+490h+var_280], xmm0
0x18004c359  movaps  xmm0, xmmword ptr cs:aA02755110e864e+20h; "-4ECA-97C2-ECD8F1221D08}"
0x18004c360  movaps  xmmword ptr [rbp+490h+var_280+20h], xmm0
0x18004c367  movaps  xmm0, xmmword ptr cs:aA02755110e864e+40h; "1221D08}"
0x18004c36e  movaps  [rbp+490h+var_240], xmm0
0x18004c375  movaps  xmm0, xmmword ptr cs:aD9ef8727Cac24e_0; "::{D9EF8727-CAC2-4e60-809E-86F80A666C91"...
0x18004c37c  movaps  xmmword ptr [rbp+490h+var_220], xmm0
0x18004c383  movaps  xmm0, xmmword ptr cs:aD9ef8727Cac24e_0+20h; "-4e60-809E-86F80A666C91}"
0x18004c38a  movaps  xmmword ptr [rbp+490h+var_220+20h], xmm0
0x18004c391  movaps  xmm0, xmmword ptr cs:aD9ef8727Cac24e_0+40h; "A666C91}"
0x18004c398  movaps  [rbp+490h+var_1E0], xmm0
0x18004c39f  movaps  xmm0, xmmword ptr cs:aEd834ed64b5a4b; "::{ED834ED6-4B5A-4BFE-8F11-A626DCB6A921"...
0x18004c3a6  movaps  xmmword ptr [rbp+490h+var_1C0], xmm0
0x18004c3ad  movaps  xmm0, xmmword ptr cs:aEd834ed64b5a4b+20h; "-4BFE-8F11-A626DCB6A921}"
0x18004c3b4  movaps  xmmword ptr [rbp+490h+var_280+10h], xmm1
0x18004c3bb  movaps  xmm1, xmmword ptr cs:aA02755110e864e+30h; "C2-ECD8F1221D08}"
0x18004c3c2  movaps  xmmword ptr [rbp+490h+var_1C0+20h], xmm0
0x18004c3c9  movaps  xmm0, xmmword ptr cs:aEd834ed64b5a4b+40h; "CB6A921}"
0x18004c3d0  movaps  [rbp+490h+var_250], xmm1
0x18004c3d7  movaps  xmm1, xmmword ptr cs:aD9ef8727Cac24e_0+10h; "727-CAC2-4e60-809E-86F80A666C91}"
0x18004c3de  movaps  [rbp+490h+var_180], xmm0
0x18004c3e5  movaps  xmm0, xmmword ptr cs:aBf782cc95a524a; "::{BF782CC9-5A52-4A17-806C-2A894FFEEAC5"...
0x18004c3ec  movaps  xmmword ptr [rbp+490h+var_220+10h], xmm1
0x18004c3f3  movaps  xmm1, xmmword ptr cs:aD9ef8727Cac24e_0+30h; "9E-86F80A666C91}"
0x18004c3fa  movaps  xmmword ptr [rbp+490h+var_160], xmm0
0x18004c401  movaps  xmm0, xmmword ptr cs:aBf782cc95a524a+20h; "-4A17-806C-2A894FFEEAC5}"
0x18004c408  movaps  [rbp+490h+var_1F0], xmm1
0x18004c40f  movaps  xmm1, xmmword ptr cs:aEd834ed64b5a4b+10h; "ED6-4B5A-4BFE-8F11-A626DCB6A921}"
0x18004c416  movaps  xmmword ptr [rbp+490h+var_160+20h], xmm0
0x18004c41d  movaps  xmm0, xmmword ptr cs:aBf782cc95a524a+40h; "FFEEAC5}"
0x18004c424  movaps  xmmword ptr [rbp+490h+var_1C0+10h], xmm1
0x18004c42b  movaps  xmm1, xmmword ptr cs:aEd834ed64b5a4b+30h; "11-A626DCB6A921}"
0x18004c432  movaps  [rbp+490h+var_120], xmm0
0x18004c439  movaps  xmm0, xmmword ptr cs:a5ffaa809096140; "::{5FFAA809-0961-40CF-90A4-58037867FA50"...
0x18004c440  mov     [rbp+490h+var_350], ax
0x18004c447  movzx   eax, word ptr cs:aA02755110e864e+50h; ""
0x18004c44e  movaps  [rbp+490h+var_190], xmm1
0x18004c455  movaps  xmm1, xmmword ptr cs:aBf782cc95a524a+10h; "CC9-5A52-4A17-806C-2A894FFEEAC5}"
0x18004c45c  movaps  xmmword ptr [rbp+490h+var_100], xmm0
0x18004c463  movaps  xmm0, xmmword ptr cs:a5ffaa809096140+20h; "-40CF-90A4-58037867FA50}"
0x18004c46a  mov     [rbp+490h+var_230], ax
0x18004c471  movzx   eax, word ptr cs:aD9ef8727Cac24e_0+50h; ""
0x18004c478  movaps  xmmword ptr [rbp+490h+var_160+10h], xmm1
0x18004c47f  movaps  xmm1, xmmword ptr cs:aBf782cc95a524a+30h; "6C-2A894FFEEAC5}"
0x18004c486  movaps  xmmword ptr [rbp+490h+var_100+20h], xmm0
0x18004c48d  movaps  xmm0, xmmword ptr cs:a5ffaa809096140+40h; "867FA50}"
0x18004c494  mov     [rbp+490h+var_1D0], ax
0x18004c49b  movzx   eax, word ptr cs:aEd834ed64b5a4b+50h; ""
0x18004c4a2  movaps  [rbp+490h+var_130], xmm1
0x18004c4a9  movaps  xmm1, xmmword ptr cs:a5ffaa809096140+10h; "809-0961-40CF-90A4-58037867FA50}"
0x18004c4b0  movaps  [rbp+490h+var_C0], xmm0
0x18004c4b7  movaps  xmm0, xmmword ptr cs:a995d28e5A9c14a; "::{995D28E5-A9C1-4A82-8EFB-C1CE53C06F07"...
0x18004c4be  mov     [rbp+490h+var_170], ax
0x18004c4c5  movzx   eax, word ptr cs:aBf782cc95a524a+50h; ""
0x18004c4cc  movaps  xmmword ptr [rbp+490h+var_100+10h], xmm1
0x18004c4d3  movaps  xmm1, xmmword ptr cs:a5ffaa809096140+30h; "A4-58037867FA50}"
0x18004c4da  movaps  xmmword ptr [rbp+490h+var_A0], xmm0
0x18004c4e1  movaps  xmm0, xmmword ptr cs:a995d28e5A9c14a+20h; "-4A82-8EFB-C1CE53C06F07}"
0x18004c4e8  mov     [rbp+490h+var_110], ax
0x18004c4ef  movzx   eax, word ptr cs:a5ffaa809096140+50h; ""
0x18004c4f6  movaps  [rbp+490h+var_D0], xmm1
0x18004c4fd  movaps  xmm1, xmmword ptr cs:a995d28e5A9c14a+10h; "8E5-A9C1-4A82-8EFB-C1CE53C06F07}"
0x18004c504  movaps  xmmword ptr [rbp+490h+var_A0+20h], xmm0
0x18004c50b  movaps  xmm0, xmmword ptr cs:a995d28e5A9c14a+40h; "3C06F07}"
0x18004c512  mov     [rbp+490h+var_B0], ax
0x18004c519  movzx   eax, word ptr cs:a995d28e5A9c14a+50h; ""
0x18004c520  movaps  xmmword ptr [rbp+490h+var_A0+10h], xmm1
0x18004c527  movaps  xmm1, xmmword ptr cs:a995d28e5A9c14a+30h; "FB-C1CE53C06F07}"
0x18004c52e  movaps  [rbp+490h+var_60], xmm0
0x18004c535  movaps  [rbp+490h+var_70], xmm1
0x18004c53c  mov     [rbp+490h+var_50], ax
0x18004c543  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004c548  call    cs:__imp_CompareStringOrdinal
0x18004c54e  cmp     eax, esi
0x18004c550  jnz     short loc_18004C55D
0x18004c552  call    ?IsMobilityCenterEnabledWithOverride@@YAHH@Z; IsMobilityCenterEnabledWithOverride(int)
0x18004c557  test    eax, eax
0x18004c559  jnz     short loc_18004C57D
0x18004c55b  jmp     short loc_18004C57A
0x18004c55d  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004c562  lea     r8, [rbp+490h+var_4C0]; lpString2
0x18004c566  mov     r9d, edi; cchCount2
0x18004c569  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004c56e  mov     edx, edi; cchCount1
0x18004c570  call    cs:__imp_CompareStringOrdinal
0x18004c576  cmp     eax, esi
0x18004c578  jnz     short loc_18004C59E
0x18004c57a  or      [rbx], r12d
0x18004c57d  mov     rcx, [rsp+590h+lpString1]; pv
0x18004c582  call    cs:__imp_CoTaskMemFree
0x18004c588  mov     rcx, [rsp+590h+var_558]
0x18004c58d  mov     rax, [rcx]
0x18004c590  mov     rax, [rax+10h]
0x18004c594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c599  jmp     loc_18004C036
0x18004c59e  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004c5a3  lea     r8, [rbp+490h+var_460]; lpString2
0x18004c5a7  mov     r9d, edi; cchCount2
0x18004c5aa  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004c5af  mov     edx, edi; cchCount1
0x18004c5b1  call    cs:__imp_CompareStringOrdinal
0x18004c5b7  cmp     eax, esi
0x18004c5b9  jz      loc_18004C7A8
0x18004c5bf  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004c5c4  lea     r8, [rbp+490h+var_400]; lpString2
0x18004c5cb  mov     r9d, edi; cchCount2
0x18004c5ce  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004c5d3  mov     edx, edi; cchCount1
0x18004c5d5  call    cs:__imp_CompareStringOrdinal
0x18004c5db  cmp     eax, esi
0x18004c5dd  jz      loc_18004C7BB
0x18004c5e3  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004c5e8  lea     r8, [rbp+490h+var_3A0]; lpString2
0x18004c5ef  mov     r9d, edi; cchCount2
0x18004c5f2  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004c5f7  mov     edx, edi; cchCount1
0x18004c5f9  call    cs:__imp_CompareStringOrdinal
0x18004c5ff  cmp     eax, esi
0x18004c601  jz      loc_18004C7C5
0x18004c607  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004c60c  lea     r8, [rbp+490h+var_340]; lpString2
0x18004c613  mov     r9d, edi; cchCount2
0x18004c616  mov     [rsp+590h+bIgnoreCase], r13d; bIgnoreCase
0x18004c61b  mov     edx, edi; cchCount1
0x18004c61d  call    cs:__imp_CompareStringOrdinal
0x18004c623  cmp     eax, esi
0x18004c625  jz      loc_18004C7CF
0x18004c62b  mov     rcx, [rsp+590h+lpString1]; lpString1
0x18004c630  lea     r8, [rbp+490h+var_2E0]; lpString2
0x18004c637  mov     r9d, edi; cchCount2
  ... truncated ...
```

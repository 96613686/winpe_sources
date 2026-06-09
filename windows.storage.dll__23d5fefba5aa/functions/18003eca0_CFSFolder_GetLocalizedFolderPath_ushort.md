# CFSFolder::_GetLocalizedFolderPath(ushort * *)

- ea: `0x18003eca0`
- end: `0x18003f5d9`
- name: `?_GetLocalizedFolderPath@CFSFolder@@IEAAJPEAPEAG@Z`
- size: `2361`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800407c0`
- `0x1800407f0`
- `0x180045c80`
- `0x18022c760`

## callees

- `0x1800376a0`
- `0x18003df10`
- `0x18003eb00`
- `0x18003eca0`
- `0x180045230`
- `0x1800688f0`
- `0x18007b9d0`
- `0x1803b1f60`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003ee56`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003ee56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003f19a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003f300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003f19a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003f300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ed8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f1d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ed8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f1d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f349`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003edb7`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003edb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f11e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f44b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f48d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f11e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f44b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f48d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFSFolder::_GetLocalizedFolderPath(CFSFolder *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rsi
  struct _GUID *v5; // rcx
  __int64 v6; // rax
  const ITEMIDLIST *v7; // rcx
  unsigned __int16 *v8; // r13
  __int64 v9; // rdi
  HRESULT inited; // r12d
  unsigned __int16 *v11; // r14
  size_t v12; // rbx
  SIZE_T v13; // rcx
  LPMALLOC v14; // r15
  size_t v15; // rsi
  IShellFolder *v16; // r14
  CMarshalByValue *v17; // rax
  CMarshalByValue *v18; // rsi
  __int64 v19; // rcx
  __int16 *v20; // rbx
  unsigned __int64 v21; // rsi
  unsigned __int16 *v22; // rcx
  __int64 v23; // rax
  bool v24; // zf
  unsigned __int64 v25; // r14
  __int64 v26; // rax
  unsigned __int64 v27; // kr00_8
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // rax
  __int64 v30; // rcx
  const WCHAR *v31; // rdx
  __int64 v32; // r9
  WCHAR *v33; // r8
  WCHAR v34; // ax
  WCHAR *v35; // rcx
  unsigned __int64 v36; // r15
  unsigned __int64 v37; // rsi
  __int64 v38; // rax
  unsigned __int64 v39; // kr10_8
  unsigned __int64 v40; // r14
  unsigned __int16 *v41; // rax
  unsigned __int16 *v42; // rax
  unsigned __int64 v43; // rdx
  unsigned __int16 *v44; // r8
  unsigned __int64 v45; // rcx
  unsigned __int16 v46; // ax
  __int64 v47; // r8
  unsigned __int16 *v48; // rax
  unsigned __int16 *v50; // [rsp+30h] [rbp-49h] BYREF
  __int64 v51; // [rsp+38h] [rbp-41h]
  unsigned __int64 v52; // [rsp+40h] [rbp-39h]
  unsigned __int16 *v53; // [rsp+48h] [rbp-31h]
  int v54; // [rsp+50h] [rbp-29h]
  unsigned __int16 *v55; // [rsp+58h] [rbp-21h]
  unsigned __int16 **v56; // [rsp+60h] [rbp-19h]
  LPVOID pv; // [rsp+68h] [rbp-11h] BYREF
  IShellFolder *ppshf; // [rsp+70h] [rbp-9h] BYREF
  __int64 v59; // [rsp+78h] [rbp-1h] BYREF
  LPMALLOC ppMalloc[2]; // [rsp+80h] [rbp+7h] BYREF

  v56 = a2;
  v4 = 0;
  v55 = 0;
  pv = 0;
  v5 = (struct _GUID *)((char *)this + 496);
  v6 = *(_QWORD *)&v5->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&v5->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v6 = *(_QWORD *)v5->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v6 )
  {
    SHGetKnownFolderIDList_Internal(v5, 0x1000u, 0, (struct _ITEMIDLIST_ABSOLUTE **)&pv);
    v4 = (unsigned __int16 *)pv;
    v55 = (unsigned __int16 *)pv;
  }
  else
  {
    v7 = (const ITEMIDLIST *)*((_QWORD *)this + 55);
    if ( v7 )
    {
      v4 = (unsigned __int16 *)ILClone(v7);
      v55 = v4;
    }
  }
  *a2 = 0;
  v8 = 0;
  v50 = 0;
  v9 = 0;
  v51 = 0;
  v52 = 0;
  ppshf = 0;
  inited = SHGetDesktopFolder(&ppshf);
  if ( inited >= 0 )
  {
    v54 = 0;
    if ( v4 )
    {
      v11 = v4;
      v53 = v4;
    }
    else
    {
      v11 = (unsigned __int16 *)*((_QWORD *)this + 54);
      v53 = v11;
    }
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v11 || (v12 = *v11, !(_WORD)v12) || inited < 0 )
        {
          ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
          v4 = v55;
          if ( inited >= 0 )
          {
            v48 = v8;
            v8 = 0;
            *v56 = v48;
          }
          goto LABEL_111;
        }
        v13 = (unsigned int)(v12 + 2);
        if ( (unsigned int)v13 >= (unsigned int)v12 )
        {
          v14 = (LPMALLOC)CoTaskMemAlloc(v13);
          if ( v14 )
            break;
        }
        inited = -2147024882;
      }
      v15 = 0;
      ppMalloc[0] = 0;
      if ( CoGetMalloc(1u, ppMalloc) >= 0 )
      {
        v15 = ((__int64 (__fastcall *)(LPMALLOC, LPMALLOC))ppMalloc[0]->lpVtbl->GetSize)(ppMalloc[0], v14);
        ((void (__fastcall *)(LPMALLOC))ppMalloc[0]->lpVtbl->Release)(ppMalloc[0]);
      }
      memset_0(v14, 0, v15);
      memcpy_0(v14, v11, v12);
      *(_WORD *)((char *)&v14->lpVtbl + v12) = 0;
      v16 = ppshf;
      v59 = 0;
      ppMalloc[0] = 0;
      inited = -2147024882;
      v17 = (CMarshalByValue *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
      v18 = v17;
      if ( !v17 )
        goto LABEL_115;
      CMarshalByValue::CMarshalByValue(v17);
      *(_DWORD *)(v19 + 120) = -2;
      *(_DWORD *)(v19 + 124) = 1;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v19 + 80));
      *(_QWORD *)v18 = &CShellItem::`vftable'{for `CMarshalByValue'};
      *((_QWORD *)v18 + 1) = &CShellItem::`vftable'{for `IShellItem2'};
      *((_QWORD *)v18 + 2) = &CShellItem::`vftable'{for `IShellItemImageFactoryPriv'};
      *((_QWORD *)v18 + 3) = &CShellItem::`vftable'{for `IPersistIDList'};
      *((_QWORD *)v18 + 4) = &CShellItem::`vftable'{for `IParentAndItem'};
      *((_QWORD *)v18 + 5) = &CShellItem::`vftable'{for `IPersistStream'};
      *((_QWORD *)v18 + 6) = &CShellItem::`vftable'{for `ICacheableObject'};
      *((_QWORD *)v18 + 7) = &CShellItem::`vftable'{for `IChildId'};
      *((_QWORD *)v18 + 8) = &CShellItem::`vftable'{for `IObjectWithBackReferences'};
      *((_QWORD *)v18 + 9) = &CShellItem::`vftable'{for `IInitializeWithFolder'};
      *((_DWORD *)v18 + 32) = 1;
      *((_QWORD *)v18 + 17) = 0;
      *((_QWORD *)v18 + 18) = 0;
      *((_QWORD *)v18 + 19) = 0;
      *((_QWORD *)v18 + 20) = 0;
      *((_QWORD *)v18 + 21) = 0;
      *((_QWORD *)v18 + 22) = 0;
      *((_QWORD *)v18 + 23) = 0;
      *((_QWORD *)v18 + 24) = 0;
      *((_QWORD *)v18 + 25) = 0;
      *((_DWORD *)v18 + 52) = 0;
      inited = CObjectWithThreadUseDetection::InitApartmentId((CMarshalByValue *)((char *)v18 + 80));
      if ( inited >= 0 )
        inited = (**(__int64 (__fastcall ***)(CMarshalByValue *, GUID *, LPMALLOC *))v18)(
                   v18,
                   &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
                   ppMalloc);
      (*(void (__fastcall **)(CMarshalByValue *))(*(_QWORD *)v18 + 16LL))(v18);
      if ( inited < 0 )
        goto LABEL_115;
      inited = ((__int64 (__fastcall *)(LPMALLOC, _QWORD, IShellFolder *, LPMALLOC))ppMalloc[0]->lpVtbl->Alloc)(
                 ppMalloc[0],
                 0,
                 v16,
                 v14);
      if ( inited >= 0 )
        inited = ((__int64 (__fastcall *)(LPMALLOC, GUID *, __int64 *))ppMalloc[0]->lpVtbl->QueryInterface)(
                   ppMalloc[0],
                   &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
                   &v59);
      ((void (__fastcall *)(LPMALLOC))ppMalloc[0]->lpVtbl->Release)(ppMalloc[0]);
      if ( inited < 0 )
      {
LABEL_115:
        v11 = v53;
        goto LABEL_48;
      }
      if ( !v54 )
      {
        ppMalloc[0] = 0;
        if ( (*(int (__fastcall **)(__int64, __int64, LPMALLOC *))(*(_QWORD *)v59 + 40LL))(v59, 2147844096LL, ppMalloc) >= 0 )
        {
          v54 = 1;
          if ( ppMalloc[0] )
          {
            v47 = -1;
            do
              ++v47;
            while ( *((_WORD *)&ppMalloc[0]->lpVtbl + v47) );
          }
          else
          {
            v47 = 0;
          }
          inited = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                     &v50,
                     ppMalloc[0],
                     v47);
          CoTaskMemFree(ppMalloc[0]);
          v9 = v51;
          v8 = v50;
        }
        goto LABEL_43;
      }
      pv = 0;
      inited = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v59 + 40LL))(v59, 0, &pv);
      if ( inited >= 0 )
        break;
LABEL_43:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v11 = v53;
      if ( inited >= 0 )
      {
        v23 = *v53;
        v24 = (unsigned __int16 *)((char *)v53 + v23) == 0;
        v11 = (unsigned __int16 *)((char *)v53 + v23);
        v53 = (unsigned __int16 *)((char *)v53 + v23);
        if ( !v24 )
        {
          if ( *v11 )
          {
            pv = 0;
            inited = ((__int64 (__fastcall *)(IShellFolder *, LPMALLOC, _QWORD, GUID *, LPVOID *))ppshf->lpVtbl->BindToObject)(
                       ppshf,
                       v14,
                       0,
                       &GUID_000214e6_0000_0000_c000_000000000046,
                       &pv);
            if ( inited >= 0 )
            {
              ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
              ppshf = (IShellFolder *)pv;
            }
          }
        }
      }
LABEL_48:
      CoTaskMemFree(v14);
    }
    v20 = (__int16 *)pv;
    if ( v9 == -1 )
    {
      if ( v8 )
      {
        do
          ++v9;
        while ( v8[v9] );
      }
      else
      {
        v9 = 0;
      }
      v51 = v9;
    }
    if ( !v9 || v8[v9 - 1] == 92 )
    {
      v25 = v52;
      goto LABEL_70;
    }
    if ( v9 == -1 )
    {
      if ( !v8 )
      {
        v9 = 0;
        v51 = 0;
        v21 = 2;
        goto LABEL_50;
      }
      do
        ++v9;
      while ( v8[v9] );
      v51 = v9;
    }
    v21 = v9 + 2;
    if ( v9 + 2 < (unsigned __int64)(v9 + 1) )
    {
LABEL_36:
      inited = -2147024362;
LABEL_42:
      CoTaskMemFree(pv);
      goto LABEL_43;
    }
LABEL_50:
    v25 = v52;
    if ( v52 != -1 )
      goto LABEL_51;
    if ( v9 == -1 )
    {
      if ( !v8 )
      {
        v9 = 0;
        v51 = 0;
        goto LABEL_138;
      }
      do
        ++v9;
      while ( v8[v9] );
      v51 = v9;
    }
    if ( v8 )
    {
      v25 = v9 + 1;
LABEL_130:
      v52 = v25;
LABEL_51:
      if ( v25 )
      {
        if ( v21 <= v25 )
          goto LABEL_63;
        ppMalloc[0] = 0;
        v27 = v25;
        v26 = 2 * v25;
        v25 *= 2LL;
        if ( !is_mul_ok(v27, 2u) )
          goto LABEL_36;
        if ( v26 - v52 > 0x800 )
          v25 = v52 + 2048;
        if ( v21 > v25 )
          v25 = v21;
        v28 = (unsigned __int16 *)CoTaskMemRealloc(v8, 2 * v25);
        if ( v28 )
        {
          v52 = v25;
          v8 = v28;
          v50 = v28;
          goto LABEL_63;
        }
      }
      else
      {
        ppMalloc[0] = 0;
        if ( !is_mul_ok(v21, 2u) )
          goto LABEL_36;
        v29 = (unsigned __int16 *)CoTaskMemAlloc(2 * v21);
        if ( v29 )
        {
          v25 = v21;
          v52 = v21;
          v8 = v29;
          v50 = v29;
          *v29 = 0;
LABEL_63:
          v30 = 1;
          v31 = L"\\";
          v32 = 2;
          v33 = &v8[v9];
          do
          {
            if ( !v30 )
              break;
            v34 = *v31;
            if ( !*v31 )
              break;
            ++v31;
            *v33++ = v34;
            --v30;
            --v32;
          }
          while ( v32 );
          v35 = v33 - 1;
          if ( v32 )
            v35 = v33;
          *v35 = 0;
          v51 = ++v9;
LABEL_70:
          if ( !v20 )
          {
            inited = 0;
            goto LABEL_42;
          }
          ppMalloc[0] = v14;
          v36 = -1;
          do
            ++v36;
          while ( v20[v36] );
          if ( v9 == -1 )
          {
            if ( v8 )
            {
              do
                ++v9;
              while ( v8[v9] );
            }
            else
            {
              v9 = 0;
            }
            v51 = v9;
          }
          v37 = v36 + v9 + 1;
          if ( v37 < v36 + v9 )
            goto LABEL_88;
          if ( v25 != -1 )
          {
LABEL_79:
            if ( v25 )
            {
              inited = 0;
              if ( v37 > v25 )
              {
                v39 = v25;
                v38 = 2 * v25;
                v40 = 2 * v25;
                if ( is_mul_ok(v39, 2u) )
                {
                  if ( v38 - v52 > 0x800 )
                    v40 = v52 + 2048;
                  if ( v37 > v40 )
                    v40 = v37;
                  v41 = (unsigned __int16 *)CoTaskMemRealloc(v8, 2 * v40);
                  if ( !v41 )
                  {
                    inited = -2147024882;
                    v14 = ppMalloc[0];
                    goto LABEL_42;
                  }
                  v52 = v40;
                  v8 = v41;
                  v50 = v41;
LABEL_95:
                  v43 = v36 + 1;
                  v44 = &v8[v9];
                  if ( v36 != -1 )
                  {
                    if ( v43 > 0x7FFFFFFF || v36 > 0x7FFFFFFE )
                    {
                      *v44 = 0;
                    }
                    else
                    {
                      v45 = v36;
                      do
                      {
                        if ( !v45 )
                          break;
                        v46 = *v20;
                        if ( !*v20 )
                          break;
                        ++v20;
                        *v44++ = v46;
                        --v45;
                        --v43;
                      }
                      while ( v43 );
                      v22 = v44 - 1;
                      if ( v43 )
                        v22 = v44;
                      *v22 = 0;
                    }
                  }
                  v9 += v36;
                  v51 = v9;
                  v14 = ppMalloc[0];
                  goto LABEL_42;
                }
                goto LABEL_88;
              }
LABEL_94:
              if ( inited >= 0 )
                goto LABEL_95;
LABEL_89:
              v14 = ppMalloc[0];
              goto LABEL_42;
            }
            ppMalloc[1] = 0;
            if ( is_mul_ok(v37, 2u) )
            {
              v42 = (unsigned __int16 *)CoTaskMemAlloc(2 * v37);
              if ( v42 )
              {
                v52 = v37;
                v8 = v42;
                v50 = v42;
                *v42 = 0;
                inited = 0;
                goto LABEL_95;
              }
              inited = -2147024882;
              goto LABEL_94;
            }
LABEL_88:
            inited = -2147024362;
            goto LABEL_89;
          }
          if ( v9 == -1 )
          {
            if ( !v8 )
            {
              v9 = 0;
              v51 = 0;
              goto LABEL_134;
            }
            do
              ++v9;
            while ( v8[v9] );
            v51 = v9;
          }
          if ( v8 )
          {
            v25 = v9 + 1;
LABEL_122:
            v52 = v25;
            goto LABEL_79;
          }
LABEL_134:
          v25 = 0;
          goto LABEL_122;
        }
      }
      inited = -2147024882;
      goto LABEL_42;
    }
LABEL_138:
    v25 = 0;
    goto LABEL_130;
  }
LABEL_111:
  CoTaskMemFree(v4);
  if ( v8 )
    CoTaskMemFree(v8);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18003eca0  mov     [rsp-8+arg_10], rbx
0x18003eca5  push    rbp
0x18003eca6  push    rsi
0x18003eca7  push    rdi
0x18003eca8  push    r12
0x18003ecaa  push    r13
0x18003ecac  push    r14
0x18003ecae  push    r15
0x18003ecb0  lea     rbp, [rsp-27h]
0x18003ecb5  sub     rsp, 0A0h
0x18003ecbc  mov     rax, cs:__security_cookie
0x18003ecc3  xor     rax, rsp
0x18003ecc6  mov     [rbp+57h+var_40], rax
0x18003ecca  mov     r15, rdx
0x18003eccd  mov     [rbp+57h+var_70], rdx
0x18003ecd1  mov     rbx, rcx
0x18003ecd4  xor     r14d, r14d
0x18003ecd7  mov     esi, r14d
0x18003ecda  mov     [rbp+57h+var_78], r14
0x18003ecde  mov     [rbp+57h+pv], r14
0x18003ece2  add     rcx, 1F0h; struct _GUID *
0x18003ece9  mov     rax, [rcx]
0x18003ecec  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18003ecf3  jnz     short loc_18003ED00
0x18003ecf5  mov     rax, [rcx+8]
0x18003ecf9  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18003ed00  test    rax, rax
0x18003ed03  jnz     loc_18003F4D9
0x18003ed09  mov     rcx, [rbx+1B8h]; pidl
0x18003ed10  test    rcx, rcx
0x18003ed13  jz      short loc_18003ED21
0x18003ed15  call    ILClone
0x18003ed1a  mov     rsi, rax
0x18003ed1d  mov     [rbp+57h+var_78], rax
0x18003ed21  mov     [r15], r14
0x18003ed24  mov     r13, r14
0x18003ed27  mov     [rbp+57h+var_A0], r14
0x18003ed2b  mov     rdi, r14
0x18003ed2e  mov     [rbp+57h+var_98], r14
0x18003ed32  mov     [rbp+57h+var_90], r14
0x18003ed36  mov     [rbp+57h+ppshf], r14
0x18003ed3a  lea     rcx, [rbp+57h+ppshf]; ppshf
0x18003ed3e  call    SHGetDesktopFolder
0x18003ed43  mov     r12d, eax
0x18003ed46  test    eax, eax
0x18003ed48  js      loc_18003F48A
0x18003ed4e  mov     [rbp+57h+var_80], r14d
0x18003ed52  test    rsi, rsi
0x18003ed55  jz      loc_18003F581
0x18003ed5b  mov     r14, rsi
0x18003ed5e  mov     [rbp+57h+var_88], rsi
0x18003ed62  test    r14, r14
0x18003ed65  jz      loc_18003F464
0x18003ed6b  movzx   ebx, word ptr [r14]
0x18003ed6f  test    bx, bx
0x18003ed72  jz      loc_18003F464
0x18003ed78  test    r12d, r12d
0x18003ed7b  js      loc_18003F464
0x18003ed81  lea     ecx, [rbx+2]; cb
0x18003ed84  cmp     ecx, ebx
0x18003ed86  jb      loc_18003F06B
0x18003ed8c  call    cs:__imp_CoTaskMemAlloc
0x18003ed93  nop     dword ptr [rax+rax+00h]
0x18003ed98  mov     r15, rax
0x18003ed9b  test    rax, rax
0x18003ed9e  jz      loc_18003F06B
0x18003eda4  xor     r12d, r12d
0x18003eda7  mov     esi, r12d
0x18003edaa  mov     [rbp+57h+ppMalloc], r12
0x18003edae  lea     rdx, [rbp+57h+ppMalloc]; ppMalloc
0x18003edb2  mov     ecx, 1; dwMemContext
0x18003edb7  call    cs:__imp_CoGetMalloc
0x18003edbe  nop     dword ptr [rax+rax+00h]
0x18003edc3  test    eax, eax
0x18003edc5  js      short loc_18003EDED
0x18003edc7  mov     rcx, [rbp+57h+ppMalloc]
0x18003edcb  mov     rax, [rcx]
0x18003edce  mov     rdx, r15
0x18003edd1  mov     rax, [rax+30h]
0x18003edd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003edda  mov     rsi, rax
0x18003eddd  mov     rcx, [rbp+57h+ppMalloc]
0x18003ede1  mov     rdx, [rcx]
0x18003ede4  mov     rax, [rdx+10h]
0x18003ede8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eded  mov     r8, rsi; Size
0x18003edf0  xor     edx, edx; Val
0x18003edf2  mov     rcx, r15; void *
0x18003edf5  call    memset_0
0x18003edfa  mov     r8, rbx; Size
0x18003edfd  mov     rdx, r14; Src
0x18003ee00  mov     rcx, r15; void *
0x18003ee03  call    memcpy_0
0x18003ee08  mov     [r15+rbx], r12w
0x18003ee0d  mov     r14, [rbp+57h+ppshf]
0x18003ee11  mov     [rbp+57h+var_58], r12
0x18003ee15  mov     [rbp+57h+ppMalloc], r12
0x18003ee19  mov     r12d, 8007000Eh
0x18003ee1f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ee26  mov     ecx, 0D8h; unsigned __int64
0x18003ee2b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003ee30  mov     rsi, rax
0x18003ee33  test    rax, rax
0x18003ee36  jz      loc_18003F4F7
0x18003ee3c  mov     rcx, rax; this
0x18003ee3f  call    ??0CMarshalByValue@@QEAA@XZ; CMarshalByValue::CMarshalByValue(void)
0x18003ee44  mov     dword ptr [rcx+78h], 0FFFFFFFEh
0x18003ee4b  mov     dword ptr [rcx+7Ch], 1
0x18003ee52  lea     rcx, [rcx+50h]; lpCriticalSection
0x18003ee56  call    cs:__imp_InitializeCriticalSection
0x18003ee5d  nop     dword ptr [rax+rax+00h]
0x18003ee62  lea     rax, ??_7CShellItem@@6BCMarshalByValue@@@; const CShellItem::`vftable'{for `CMarshalByValue'}
0x18003ee69  mov     [rsi], rax
0x18003ee6c  lea     rax, ??_7CShellItem@@6BIShellItem2@@@; const CShellItem::`vftable'{for `IShellItem2'}
0x18003ee73  mov     [rsi+8], rax
0x18003ee77  lea     rax, ??_7CShellItem@@6BIShellItemImageFactoryPriv@@@; const CShellItem::`vftable'{for `IShellItemImageFactoryPriv'}
0x18003ee7e  mov     [rsi+10h], rax
0x18003ee82  lea     rax, ??_7CShellItem@@6BIPersistIDList@@@; const CShellItem::`vftable'{for `IPersistIDList'}
0x18003ee89  mov     [rsi+18h], rax
0x18003ee8d  lea     rax, ??_7CShellItem@@6BIParentAndItem@@@; const CShellItem::`vftable'{for `IParentAndItem'}
0x18003ee94  mov     [rsi+20h], rax
0x18003ee98  lea     rax, ??_7CShellItem@@6BIPersistStream@@@; const CShellItem::`vftable'{for `IPersistStream'}
0x18003ee9f  mov     [rsi+28h], rax
0x18003eea3  lea     rax, ??_7CShellItem@@6BICacheableObject@@@; const CShellItem::`vftable'{for `ICacheableObject'}
0x18003eeaa  mov     [rsi+30h], rax
0x18003eeae  lea     rax, ??_7CShellItem@@6BIChildId@@@; const CShellItem::`vftable'{for `IChildId'}
0x18003eeb5  mov     [rsi+38h], rax
0x18003eeb9  lea     rax, ??_7CShellItem@@6BIObjectWithBackReferences@@@; const CShellItem::`vftable'{for `IObjectWithBackReferences'}
0x18003eec0  mov     [rsi+40h], rax
0x18003eec4  lea     rax, ??_7CShellItem@@6BIInitializeWithFolder@@@; const CShellItem::`vftable'{for `IInitializeWithFolder'}
0x18003eecb  mov     [rsi+48h], rax
0x18003eecf  mov     dword ptr [rsi+80h], 1
0x18003eed9  xor     eax, eax
0x18003eedb  mov     [rsi+88h], rax
0x18003eee2  mov     [rsi+90h], rax
0x18003eee9  mov     [rsi+98h], rax
0x18003eef0  mov     [rsi+0A0h], rax
0x18003eef7  mov     [rsi+0A8h], rax
0x18003eefe  mov     [rsi+0B0h], rax
0x18003ef05  mov     [rsi+0B8h], rax
0x18003ef0c  mov     [rsi+0C0h], rax
0x18003ef13  mov     [rsi+0C8h], rax
0x18003ef1a  mov     [rsi+0D0h], eax
0x18003ef20  lea     rcx, [rsi+50h]; this
0x18003ef24  call    ?InitApartmentId@CObjectWithThreadUseDetection@@QEAAJXZ; CObjectWithThreadUseDetection::InitApartmentId(void)
0x18003ef29  mov     r12d, eax
0x18003ef2c  test    eax, eax
0x18003ef2e  js      short loc_18003EF4C
0x18003ef30  mov     rax, [rsi]
0x18003ef33  lea     r8, [rbp+57h+ppMalloc]
0x18003ef37  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x18003ef3e  mov     rcx, rsi
0x18003ef41  mov     rax, [rax]
0x18003ef44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef49  mov     r12d, eax
0x18003ef4c  mov     rax, [rsi]
0x18003ef4f  mov     rcx, rsi
0x18003ef52  mov     rax, [rax+10h]
0x18003ef56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef5b  test    r12d, r12d
0x18003ef5e  js      loc_18003F4F7
0x18003ef64  mov     rcx, [rbp+57h+ppMalloc]
0x18003ef68  mov     rax, [rcx]
0x18003ef6b  mov     r9, r15
0x18003ef6e  mov     r8, r14
0x18003ef71  xor     edx, edx
0x18003ef73  mov     rax, [rax+18h]
0x18003ef77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef7c  mov     r12d, eax
0x18003ef7f  test    eax, eax
0x18003ef81  js      short loc_18003EFA0
0x18003ef83  mov     rcx, [rbp+57h+ppMalloc]
0x18003ef87  mov     rax, [rcx]
0x18003ef8a  lea     r8, [rbp+57h+var_58]
0x18003ef8e  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x18003ef95  mov     rax, [rax]
0x18003ef98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef9d  mov     r12d, eax
0x18003efa0  mov     rcx, [rbp+57h+ppMalloc]
0x18003efa4  mov     rax, [rcx]
0x18003efa7  mov     rax, [rax+10h]
0x18003efab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efb0  test    r12d, r12d
0x18003efb3  js      loc_18003F4F7
0x18003efb9  mov     rcx, [rbp+57h+var_58]
0x18003efbd  cmp     [rbp+57h+var_80], 0
0x18003efc1  jz      loc_18003F3EF
0x18003efc7  mov     [rbp+57h+pv], 0
0x18003efcf  mov     rax, [rcx]
0x18003efd2  lea     r8, [rbp+57h+pv]
0x18003efd6  xor     edx, edx
0x18003efd8  mov     rax, [rax+28h]
0x18003efdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efe1  mov     r12d, eax
0x18003efe4  test    eax, eax
0x18003efe6  js      loc_18003F0A1
0x18003efec  mov     rbx, [rbp+57h+pv]
0x18003eff0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003eff4  jnz     short loc_18003F010
0x18003eff6  test    r13, r13
0x18003eff9  jz      loc_18003F59C
0x18003efff  nop
0x18003f000  inc     rdi
0x18003f003  cmp     word ptr [r13+rdi*2+0], 0
0x18003f00a  jnz     short loc_18003F000
0x18003f00c  mov     [rbp+57h+var_98], rdi
0x18003f010  test    rdi, rdi
0x18003f013  jz      loc_18003F3E6
0x18003f019  cmp     word ptr [r13+rdi*2-2], 5Ch ; '\'
0x18003f020  jz      loc_18003F3E6
0x18003f026  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003f02a  jnz     short loc_18003F050
0x18003f02c  test    r13, r13
0x18003f02f  jz      loc_18003F12F
0x18003f035  nop     word ptr [rax+rax+00000000h]
0x18003f040  inc     rdi
0x18003f043  cmp     word ptr [r13+rdi*2+0], 0
0x18003f04a  jnz     short loc_18003F040
0x18003f04c  mov     [rbp+57h+var_98], rdi
0x18003f050  mov     rax, rdi
0x18003f053  inc     rax
0x18003f056  lea     rsi, [rax+1]
0x18003f05a  cmp     rsi, rax
0x18003f05d  jnb     loc_18003F13A
0x18003f063  mov     r12d, 80070216h
0x18003f069  jmp     short loc_18003F091
0x18003f06b  mov     r12d, 8007000Eh
0x18003f071  jmp     loc_18003ED62
0x18003f076  lea     rcx, [r8-2]
0x18003f07a  test    rdx, rdx
0x18003f07d  cmovnz  rcx, r8
0x18003f081  xor     eax, eax
0x18003f083  mov     [rcx], ax
0x18003f086  add     rdi, r15
0x18003f089  mov     [rbp+57h+var_98], rdi
0x18003f08d  mov     r15, [rbp+57h+ppMalloc]
0x18003f091  mov     rcx, [rbp+57h+pv]; pv
0x18003f095  call    cs:__imp_CoTaskMemFree
0x18003f09c  nop     dword ptr [rax+rax+00h]
0x18003f0a1  mov     rcx, [rbp+57h+var_58]
0x18003f0a5  mov     rax, [rcx]
0x18003f0a8  mov     rax, [rax+10h]
0x18003f0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0b1  mov     r14, [rbp+57h+var_88]
0x18003f0b5  test    r12d, r12d
0x18003f0b8  js      short loc_18003F11B
0x18003f0ba  movzx   eax, word ptr [r14]
0x18003f0be  add     r14, rax
0x18003f0c1  mov     [rbp+57h+var_88], r14
0x18003f0c5  jz      short loc_18003F11B
0x18003f0c7  cmp     word ptr [r14], 0
0x18003f0cc  jz      short loc_18003F11B
0x18003f0ce  mov     [rbp+57h+pv], 0
0x18003f0d6  mov     rcx, [rbp+57h+ppshf]
0x18003f0da  mov     rax, [rcx]
0x18003f0dd  lea     rdx, [rbp+57h+pv]
0x18003f0e1  mov     [rsp+0D0h+var_B0], rdx
0x18003f0e6  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x18003f0ed  xor     r8d, r8d
0x18003f0f0  mov     rdx, r15
0x18003f0f3  mov     rax, [rax+28h]
0x18003f0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0fc  mov     r12d, eax
0x18003f0ff  test    eax, eax
0x18003f101  js      short loc_18003F11B
0x18003f103  mov     rcx, [rbp+57h+ppshf]
0x18003f107  mov     rax, [rcx]
0x18003f10a  mov     rax, [rax+10h]
0x18003f10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f113  mov     rax, [rbp+57h+pv]
0x18003f117  mov     [rbp+57h+ppshf], rax
0x18003f11b  mov     rcx, r15; pv
0x18003f11e  call    cs:__imp_CoTaskMemFree
0x18003f125  nop     dword ptr [rax+rax+00h]
0x18003f12a  jmp     loc_18003ED62
0x18003f12f  xor     edi, edi
0x18003f131  mov     [rbp+57h+var_98], rdi
0x18003f135  mov     esi, 2
0x18003f13a  mov     r14, [rbp+57h+var_90]
0x18003f13e  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18003f142  jz      loc_18003F53D
0x18003f148  test    r14, r14
0x18003f14b  jz      short loc_18003F1BC
0x18003f14d  cmp     rsi, r14
0x18003f150  jbe     loc_18003F200
0x18003f156  mov     [rbp+57h+ppMalloc], 0
0x18003f15e  mov     eax, 2
0x18003f163  mul     r14
0x18003f166  mov     r14, rax
0x18003f169  test    rdx, rdx
0x18003f16c  jnz     loc_18003F063
0x18003f172  mov     rcx, rax
0x18003f175  mov     rdx, [rbp+57h+var_90]
0x18003f179  sub     rcx, rdx
0x18003f17c  cmp     rcx, 800h
0x18003f183  jbe     short loc_18003F18C
0x18003f185  lea     r14, [rdx+800h]
0x18003f18c  cmp     rsi, r14
0x18003f18f  cmova   r14, rsi
0x18003f193  lea     rdx, [r14+r14]; cb
  ... truncated ...
```

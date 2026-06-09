# CFSFolder::_GetLocalizedFolderPath(ushort * *)

- ea: `0x1800481a0`
- end: `0x180048a99`
- name: `?_GetLocalizedFolderPath@CFSFolder@@IEAAJPEAPEAG@Z`
- size: `2297`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005e4f4`
- `0x18008f5a0`
- `0x180094d10`
- `0x180211830`

## callees

- `0x180041b00`
- `0x180047ec0`
- `0x1800481a0`
- `0x180049980`
- `0x18005f280`
- `0x180093c20`
- `0x1800d6b80`
- `0x1803a4cb0`
- `0x1803a518c`
- `0x1803a57e0`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004834a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004834a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18004867e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800487d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18004867e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800487d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004828c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800486b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004828c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800486b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048813`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800482b1`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800482b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048585`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004891b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048966`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048585`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004891b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048966`

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
          inited = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&v50);
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
0x1800481a0  mov     [rsp-8+arg_10], rbx
0x1800481a5  push    rbp
0x1800481a6  push    rsi
0x1800481a7  push    rdi
0x1800481a8  push    r12
0x1800481aa  push    r13
0x1800481ac  push    r14
0x1800481ae  push    r15
0x1800481b0  lea     rbp, [rsp-27h]
0x1800481b5  sub     rsp, 0A0h
0x1800481bc  mov     rax, cs:__security_cookie
0x1800481c3  xor     rax, rsp
0x1800481c6  mov     [rbp+57h+var_40], rax
0x1800481ca  mov     r15, rdx
0x1800481cd  mov     [rbp+57h+var_70], rdx
0x1800481d1  mov     rbx, rcx
0x1800481d4  xor     r14d, r14d
0x1800481d7  mov     esi, r14d
0x1800481da  mov     [rbp+57h+var_78], r14
0x1800481de  mov     [rbp+57h+pv], r14
0x1800481e2  add     rcx, 1F0h; struct _GUID *
0x1800481e9  mov     rax, [rcx]
0x1800481ec  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800481f3  jnz     short loc_180048200
0x1800481f5  mov     rax, [rcx+8]
0x1800481f9  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180048200  test    rax, rax
0x180048203  jnz     loc_180048996
0x180048209  mov     rcx, [rbx+1B8h]; pidl
0x180048210  test    rcx, rcx
0x180048213  jz      short loc_180048221
0x180048215  call    ILClone
0x18004821a  mov     rsi, rax
0x18004821d  mov     [rbp+57h+var_78], rax
0x180048221  mov     [r15], r14
0x180048224  mov     r13, r14
0x180048227  mov     [rbp+57h+var_A0], r14
0x18004822b  mov     rdi, r14
0x18004822e  mov     [rbp+57h+var_98], r14
0x180048232  mov     [rbp+57h+var_90], r14
0x180048236  mov     [rbp+57h+ppshf], r14
0x18004823a  lea     rcx, [rbp+57h+ppshf]; ppshf
0x18004823e  call    SHGetDesktopFolder
0x180048243  mov     r12d, eax
0x180048246  test    eax, eax
0x180048248  js      loc_180048954
0x18004824e  mov     [rbp+57h+var_80], r14d
0x180048252  test    rsi, rsi
0x180048255  jz      loc_180048A41
0x18004825b  mov     r14, rsi
0x18004825e  mov     [rbp+57h+var_88], rsi
0x180048262  test    r14, r14
0x180048265  jz      loc_18004892E
0x18004826b  movzx   ebx, word ptr [r14]
0x18004826f  test    bx, bx
0x180048272  jz      loc_18004892E
0x180048278  test    r12d, r12d
0x18004827b  js      loc_18004892E
0x180048281  lea     ecx, [rbx+2]; cb
0x180048284  cmp     ecx, ebx
0x180048286  jb      loc_18004855B
0x18004828c  call    cs:__imp_CoTaskMemAlloc
0x180048292  mov     r15, rax
0x180048295  test    rax, rax
0x180048298  jz      loc_18004855B
0x18004829e  xor     r12d, r12d
0x1800482a1  mov     esi, r12d
0x1800482a4  mov     [rbp+57h+ppMalloc], r12
0x1800482a8  lea     rdx, [rbp+57h+ppMalloc]; ppMalloc
0x1800482ac  mov     ecx, 1; dwMemContext
0x1800482b1  call    cs:__imp_CoGetMalloc
0x1800482b7  test    eax, eax
0x1800482b9  js      short loc_1800482E1
0x1800482bb  mov     rcx, [rbp+57h+ppMalloc]
0x1800482bf  mov     rax, [rcx]
0x1800482c2  mov     rdx, r15
0x1800482c5  mov     rax, [rax+30h]
0x1800482c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482ce  mov     rsi, rax
0x1800482d1  mov     rcx, [rbp+57h+ppMalloc]
0x1800482d5  mov     rdx, [rcx]
0x1800482d8  mov     rax, [rdx+10h]
0x1800482dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482e1  mov     r8, rsi; Size
0x1800482e4  xor     edx, edx; Val
0x1800482e6  mov     rcx, r15; void *
0x1800482e9  call    memset_0
0x1800482ee  mov     r8, rbx; Size
0x1800482f1  mov     rdx, r14; Src
0x1800482f4  mov     rcx, r15; void *
0x1800482f7  call    memcpy_0
0x1800482fc  mov     [r15+rbx], r12w
0x180048301  mov     r14, [rbp+57h+ppshf]
0x180048305  mov     [rbp+57h+var_58], r12
0x180048309  mov     [rbp+57h+ppMalloc], r12
0x18004830d  mov     r12d, 8007000Eh
0x180048313  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004831a  mov     ecx, 0D8h; unsigned __int64
0x18004831f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180048324  mov     rsi, rax
0x180048327  test    rax, rax
0x18004832a  jz      loc_1800489B4
0x180048330  mov     rcx, rax; this
0x180048333  call    ??0CMarshalByValue@@QEAA@XZ; CMarshalByValue::CMarshalByValue(void)
0x180048338  mov     dword ptr [rcx+78h], 0FFFFFFFEh
0x18004833f  mov     dword ptr [rcx+7Ch], 1
0x180048346  lea     rcx, [rcx+50h]; lpCriticalSection
0x18004834a  call    cs:__imp_InitializeCriticalSection
0x180048350  lea     rax, ??_7CShellItem@@6BCMarshalByValue@@@; const CShellItem::`vftable'{for `CMarshalByValue'}
0x180048357  mov     [rsi], rax
0x18004835a  lea     rax, ??_7CShellItem@@6BIShellItem2@@@; const CShellItem::`vftable'{for `IShellItem2'}
0x180048361  mov     [rsi+8], rax
0x180048365  lea     rax, ??_7CShellItem@@6BIShellItemImageFactoryPriv@@@; const CShellItem::`vftable'{for `IShellItemImageFactoryPriv'}
0x18004836c  mov     [rsi+10h], rax
0x180048370  lea     rax, ??_7CShellItem@@6BIPersistIDList@@@; const CShellItem::`vftable'{for `IPersistIDList'}
0x180048377  mov     [rsi+18h], rax
0x18004837b  lea     rax, ??_7CShellItem@@6BIParentAndItem@@@; const CShellItem::`vftable'{for `IParentAndItem'}
0x180048382  mov     [rsi+20h], rax
0x180048386  lea     rax, ??_7CShellItem@@6BIPersistStream@@@; const CShellItem::`vftable'{for `IPersistStream'}
0x18004838d  mov     [rsi+28h], rax
0x180048391  lea     rax, ??_7CShellItem@@6BICacheableObject@@@; const CShellItem::`vftable'{for `ICacheableObject'}
0x180048398  mov     [rsi+30h], rax
0x18004839c  lea     rax, ??_7CShellItem@@6BIChildId@@@; const CShellItem::`vftable'{for `IChildId'}
0x1800483a3  mov     [rsi+38h], rax
0x1800483a7  lea     rax, ??_7CShellItem@@6BIObjectWithBackReferences@@@; const CShellItem::`vftable'{for `IObjectWithBackReferences'}
0x1800483ae  mov     [rsi+40h], rax
0x1800483b2  lea     rax, ??_7CShellItem@@6BIInitializeWithFolder@@@; const CShellItem::`vftable'{for `IInitializeWithFolder'}
0x1800483b9  mov     [rsi+48h], rax
0x1800483bd  mov     dword ptr [rsi+80h], 1
0x1800483c7  xor     eax, eax
0x1800483c9  mov     [rsi+88h], rax
0x1800483d0  mov     [rsi+90h], rax
0x1800483d7  mov     [rsi+98h], rax
0x1800483de  mov     [rsi+0A0h], rax
0x1800483e5  mov     [rsi+0A8h], rax
0x1800483ec  mov     [rsi+0B0h], rax
0x1800483f3  mov     [rsi+0B8h], rax
0x1800483fa  mov     [rsi+0C0h], rax
0x180048401  mov     [rsi+0C8h], rax
0x180048408  mov     [rsi+0D0h], eax
0x18004840e  lea     rcx, [rsi+50h]; this
0x180048412  call    ?InitApartmentId@CObjectWithThreadUseDetection@@QEAAJXZ; CObjectWithThreadUseDetection::InitApartmentId(void)
0x180048417  mov     r12d, eax
0x18004841a  test    eax, eax
0x18004841c  js      short loc_18004843A
0x18004841e  mov     rax, [rsi]
0x180048421  lea     r8, [rbp+57h+ppMalloc]
0x180048425  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x18004842c  mov     rcx, rsi
0x18004842f  mov     rax, [rax]
0x180048432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048437  mov     r12d, eax
0x18004843a  mov     rax, [rsi]
0x18004843d  mov     rcx, rsi
0x180048440  mov     rax, [rax+10h]
0x180048444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048449  test    r12d, r12d
0x18004844c  js      loc_1800489B4
0x180048452  mov     rcx, [rbp+57h+ppMalloc]
0x180048456  mov     rax, [rcx]
0x180048459  mov     r9, r15
0x18004845c  mov     r8, r14
0x18004845f  xor     edx, edx
0x180048461  mov     rax, [rax+18h]
0x180048465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004846a  mov     r12d, eax
0x18004846d  test    eax, eax
0x18004846f  js      short loc_18004848E
0x180048471  mov     rcx, [rbp+57h+ppMalloc]
0x180048475  mov     rax, [rcx]
0x180048478  lea     r8, [rbp+57h+var_58]
0x18004847c  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180048483  mov     rax, [rax]
0x180048486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004848b  mov     r12d, eax
0x18004848e  mov     rcx, [rbp+57h+ppMalloc]
0x180048492  mov     rax, [rcx]
0x180048495  mov     rax, [rax+10h]
0x180048499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004849e  test    r12d, r12d
0x1800484a1  js      loc_1800489B4
0x1800484a7  mov     rcx, [rbp+57h+var_58]
0x1800484ab  cmp     [rbp+57h+var_80], 0
0x1800484af  jz      loc_1800488B8
0x1800484b5  mov     [rbp+57h+pv], 0
0x1800484bd  mov     rax, [rcx]
0x1800484c0  lea     r8, [rbp+57h+pv]
0x1800484c4  xor     edx, edx
0x1800484c6  mov     rax, [rax+28h]
0x1800484ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484cf  mov     r12d, eax
0x1800484d2  test    eax, eax
0x1800484d4  js      loc_18004858B
0x1800484da  mov     rbx, [rbp+57h+pv]
0x1800484de  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800484e2  jnz     short loc_180048500
0x1800484e4  test    r13, r13
0x1800484e7  jz      loc_180048A5C
0x1800484ed  nop     dword ptr [rax]
0x1800484f0  inc     rdi
0x1800484f3  cmp     word ptr [r13+rdi*2+0], 0
0x1800484fa  jnz     short loc_1800484F0
0x1800484fc  mov     [rbp+57h+var_98], rdi
0x180048500  test    rdi, rdi
0x180048503  jz      loc_1800488AF
0x180048509  cmp     word ptr [r13+rdi*2-2], 5Ch ; '\'
0x180048510  jz      loc_1800488AF
0x180048516  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18004851a  jnz     short loc_180048540
0x18004851c  test    r13, r13
0x18004851f  jz      loc_180048613
0x180048525  nop     word ptr [rax+rax+00000000h]
0x180048530  inc     rdi
0x180048533  cmp     word ptr [r13+rdi*2+0], 0
0x18004853a  jnz     short loc_180048530
0x18004853c  mov     [rbp+57h+var_98], rdi
0x180048540  mov     rax, rdi
0x180048543  inc     rax
0x180048546  lea     rsi, [rax+1]
0x18004854a  cmp     rsi, rax
0x18004854d  jnb     loc_18004861E
0x180048553  mov     r12d, 80070216h
0x180048559  jmp     short loc_180048581
0x18004855b  mov     r12d, 8007000Eh
0x180048561  jmp     loc_180048262
0x180048566  lea     rcx, [r8-2]
0x18004856a  test    rdx, rdx
0x18004856d  cmovnz  rcx, r8
0x180048571  xor     eax, eax
0x180048573  mov     [rcx], ax
0x180048576  add     rdi, r15
0x180048579  mov     [rbp+57h+var_98], rdi
0x18004857d  mov     r15, [rbp+57h+ppMalloc]
0x180048581  mov     rcx, [rbp+57h+pv]; pv
0x180048585  call    cs:__imp_CoTaskMemFree
0x18004858b  mov     rcx, [rbp+57h+var_58]
0x18004858f  mov     rax, [rcx]
0x180048592  mov     rax, [rax+10h]
0x180048596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004859b  mov     r14, [rbp+57h+var_88]
0x18004859f  test    r12d, r12d
0x1800485a2  js      short loc_180048605
0x1800485a4  movzx   eax, word ptr [r14]
0x1800485a8  add     r14, rax
0x1800485ab  mov     [rbp+57h+var_88], r14
0x1800485af  jz      short loc_180048605
0x1800485b1  cmp     word ptr [r14], 0
0x1800485b6  jz      short loc_180048605
0x1800485b8  mov     [rbp+57h+pv], 0
0x1800485c0  mov     rcx, [rbp+57h+ppshf]
0x1800485c4  mov     rax, [rcx]
0x1800485c7  lea     rdx, [rbp+57h+pv]
0x1800485cb  mov     [rsp+0D0h+var_B0], rdx
0x1800485d0  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x1800485d7  xor     r8d, r8d
0x1800485da  mov     rdx, r15
0x1800485dd  mov     rax, [rax+28h]
0x1800485e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485e6  mov     r12d, eax
0x1800485e9  test    eax, eax
0x1800485eb  js      short loc_180048605
0x1800485ed  mov     rcx, [rbp+57h+ppshf]
0x1800485f1  mov     rax, [rcx]
0x1800485f4  mov     rax, [rax+10h]
0x1800485f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485fd  mov     rax, [rbp+57h+pv]
0x180048601  mov     [rbp+57h+ppshf], rax
0x180048605  mov     rcx, r15; pv
0x180048608  call    cs:__imp_CoTaskMemFree
0x18004860e  jmp     loc_180048262
0x180048613  xor     edi, edi
0x180048615  mov     [rbp+57h+var_98], rdi
0x180048619  mov     esi, 2
0x18004861e  mov     r14, [rbp+57h+var_90]
0x180048622  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180048626  jz      loc_1800489FD
0x18004862c  test    r14, r14
0x18004862f  jz      short loc_18004869A
0x180048631  cmp     rsi, r14
0x180048634  jbe     loc_1800486D8
0x18004863a  mov     [rbp+57h+ppMalloc], 0
0x180048642  mov     eax, 2
0x180048647  mul     r14
0x18004864a  mov     r14, rax
0x18004864d  test    rdx, rdx
0x180048650  jnz     loc_180048553
0x180048656  mov     rcx, rax
0x180048659  mov     rdx, [rbp+57h+var_90]
0x18004865d  sub     rcx, rdx
0x180048660  cmp     rcx, 800h
0x180048667  jbe     short loc_180048670
0x180048669  lea     r14, [rdx+800h]
0x180048670  cmp     rsi, r14
0x180048673  cmova   r14, rsi
0x180048677  lea     rdx, [r14+r14]; cb
0x18004867b  mov     rcx, r13; pv
0x18004867e  call    cs:__imp_CoTaskMemRealloc
0x180048684  test    rax, rax
0x180048687  jz      loc_1800489F2
0x18004868d  mov     [rbp+57h+var_90], r14
  ... truncated ...
```

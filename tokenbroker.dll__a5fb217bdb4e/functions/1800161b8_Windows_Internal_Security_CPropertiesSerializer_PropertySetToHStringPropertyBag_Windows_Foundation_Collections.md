# Windows::Internal::Security::CPropertiesSerializer::PropertySetToHStringPropertyBag(Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> * *)

- ea: `0x1800161b8`
- end: `0x1800168ea`
- name: `?PropertySetToHStringPropertyBag@CPropertiesSerializer@Security@Internal@Windows@@SAJPEAUIPropertySet@Collections@Foundation@4@PEAPEAU?$IMap@PEAUHSTRING__@@PEAU1@@674@@Z`
- size: `1842`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180025c60`

## callees

- `0x18000f8e8`
- `0x180015830`
- `0x1800161b8`
- `0x180016e24`
- `0x180016e40`
- `0x180016e5c`
- `0x180016ee4`
- `0x180016f44`
- `0x1800175c0`
- `0x180018428`
- `0x18003e0f8`
- `0x18003e214`
- `0x180048bd4`
- `0x18008f1ec`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016382`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016382`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001653d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001653d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001633a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180016358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001633a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180016358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800163b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800163b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016281`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800162e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001654a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016554`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001658e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800165c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800165d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001684c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016281`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800162e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001654a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016554`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001658e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800165c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800165d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001684c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180016681`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180016681`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::CPropertiesSerializer::PropertySetToHStringPropertyBag(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        _QWORD *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  HRESULT inited; // esi
  __int64 v6; // r14
  __int64 v7; // rbx
  __int64 *v8; // rcx
  __int64 (__fastcall *v9)(__int64, __int64 **); // rdi
  __int64 *v10; // rdi
  __int64 (__fastcall *v11)(__int64 *, HSTRING *); // rbx
  __int64 v12; // rax
  __int64 v13; // rdi
  int v14; // ebx
  HSTRING v15; // rdi
  HSTRING v16; // rbx
  char v17; // r15
  HSTRING v18; // rbx
  RTL_SRWLOCK *v19; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v21; // rcx
  unsigned int v22; // esi
  unsigned __int64 i; // rdx
  int v24; // ecx
  __int64 v25; // r15
  __int64 *j; // r15
  __int64 *v27; // r13
  PCWSTR v28; // rax
  __int64 v29; // rcx
  UINT32 v30; // esi
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // r8
  int v33; // ecx
  __int64 v34; // r15
  __int64 v35; // rdx
  __int64 *k; // r15
  __int64 v37; // r15
  __int64 v38; // r8
  RTL_SRWLOCK *v39; // rcx
  __int64 *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // kr00_8
  __int64 v46; // rdx
  __int64 (__fastcall *v47)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, __int64 *); // rbx
  _QWORD *v50; // rax
  int v51; // r8d
  _QWORD *m; // rdx
  __int64 v53; // rdx
  int v54; // eax
  __int64 v55; // rdx
  unsigned int v56; // eax
  _BYTE v57[8]; // [rsp+30h] [rbp-69h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-61h] BYREF
  HSTRING v59; // [rsp+40h] [rbp-59h] BYREF
  UINT32 length[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 *v61; // [rsp+50h] [rbp-49h] BYREF
  __int64 v62; // [rsp+58h] [rbp-41h] BYREF
  UINT32 v63; // [rsp+60h] [rbp-39h] BYREF
  HSTRING v64; // [rsp+68h] [rbp-31h] BYREF
  HSTRING string; // [rsp+70h] [rbp-29h] BYREF
  __int64 v66; // [rsp+78h] [rbp-21h] BYREF
  __int64 v67; // [rsp+80h] [rbp-19h] BYREF
  unsigned int v68; // [rsp+88h] [rbp-11h]
  HSTRING v69; // [rsp+90h] [rbp-9h]
  __int64 v70; // [rsp+98h] [rbp-1h] BYREF
  int v71; // [rsp+A0h] [rbp+7h]
  __int64 *v72; // [rsp+A8h] [rbp+Fh] BYREF
  _QWORD v73[8]; // [rsp+B0h] [rbp+17h] BYREF
  char v75; // [rsp+118h] [rbp+7Fh] BYREF

  v67 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(&v67);
  v66 = 0;
  inited = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(
             v4,
             v3,
             &v67);
  v62 = 0;
  v75 = 0;
  if ( inited >= 0 )
  {
    v47 = **a1;
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v66);
    inited = v47(a1, &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204, &v66);
    if ( inited >= 0 )
    {
      v48 = v66;
      v49 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v66 + 48LL);
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v62);
      inited = v49(v48, &v62);
      if ( inited >= 0 )
        inited = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v62 + 56LL))(v62, &v75);
    }
  }
  v70 = 0;
  v71 = 0;
  v61 = 0;
  string = 0;
  v64 = 0;
  if ( inited < 0 )
    goto LABEL_58;
  v6 = v67;
  while ( v75 )
  {
    v7 = v62;
    v8 = v61;
    v9 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v62 + 48LL);
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64 *))(*v8 + 16))(v8);
    }
    inited = v9(v7, &v61);
    if ( inited < 0 )
      goto LABEL_54;
    v10 = v61;
    v11 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v61 + 48);
    WindowsDeleteString(string);
    string = 0;
    inited = v11(v10, &string);
    if ( inited < 0 )
      goto LABEL_54;
    v12 = *v61;
    v72 = &v70;
    v73[0] = 0;
    inited = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(v12 + 56))(v61, v73);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v72);
    if ( inited >= 0 )
    {
      v13 = v70;
      v14 = v71;
      WindowsDeleteString(v64);
      v64 = 0;
      if ( v14 == 7 )
      {
        inited = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v13 + 152LL))(v13, &v64);
      }
      else
      {
        inited = -2147316576;
        if ( v14 < 0 )
          inited = v14;
      }
    }
    if ( inited < 0 )
      goto LABEL_54;
    v15 = string;
    v16 = v64;
    v69 = string;
    if ( !*(_BYTE *)(v6 + 184) )
      RoOriginateError(2147549183LL, 0);
    newString = 0;
    inited = WindowsDuplicateString(v15, &newString);
    if ( inited >= 0 )
    {
      v17 = 0;
      inited = WindowsDuplicateString(v16, &v59);
      v18 = 0;
      if ( inited >= 0 )
      {
        v19 = (RTL_SRWLOCK *)(v6 + 168);
        if ( *(_DWORD *)(v6 + 160) == 1 )
        {
          if ( !LODWORD(v19->Ptr) )
            LODWORD(v19->Ptr) = -268435456;
        }
        else
        {
          AcquireSRWLockExclusive(v19);
        }
        XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(v57, *(unsigned __int8 *)(v6 + 186), v6 + 188);
        XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(v6 + 176));
        length[0] = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(newString, length);
        v22 = -2128831035;
        for ( i = 0; i < 2 * (unsigned __int64)length[0]; v22 = 16777619 * v21 )
        {
          v24 = *((unsigned __int8 *)StringRawBuffer + i++);
          v21 = v22 ^ v24;
        }
        v25 = *(_QWORD *)(v6 + 80);
        if ( v25 )
        {
          for ( j = *(__int64 **)(v25 + 8LL * (v22 % *(_DWORD *)(v6 + 96))); j; j = (__int64 *)j[2] )
          {
            if ( *((_DWORD *)j + 6) == v22 )
            {
              v53 = *j;
              v57[0] = 0;
              v54 = XWinRT::StringEquals::operator()(v21, v53, newString, v57);
              v21 = (unsigned int)v54;
              if ( v54 < 0 )
              {
                j = 0;
                goto LABEL_26;
              }
              if ( v57[0] )
                goto LABEL_25;
            }
          }
        }
        j = 0;
LABEL_25:
        LODWORD(v21) = 0;
LABEL_26:
        inited = v21;
        v27 = 0;
        if ( (int)v21 >= 0 )
        {
          inited = 0;
          v27 = j;
        }
        if ( inited >= 0 )
        {
          if ( v27 )
          {
            v18 = (HSTRING)v27[1];
            WindowsDeleteString(0);
            v17 = 1;
            v27[1] = (__int64)v59;
            v59 = 0;
            goto LABEL_46;
          }
          if ( *(_QWORD *)(v6 + 88) != 0x7FFFFFFF )
          {
            v63 = 0;
            v28 = WindowsGetStringRawBuffer(newString, &v63);
            v30 = -2128831035;
            length[0] = -2128831035;
            v31 = 0;
            v32 = 2LL * v63;
            if ( v32 )
            {
              do
              {
                v33 = *((unsigned __int8 *)v28 + v31++);
                v29 = v30 ^ v33;
                v30 = 16777619 * v29;
              }
              while ( v31 < v32 );
              length[0] = 16777619 * v29;
            }
            v34 = *(_QWORD *)(v6 + 80);
            v35 = v30 % *(_DWORD *)(v6 + 96);
            v68 = v35;
            if ( v34 )
            {
              for ( k = *(__int64 **)(v34 + 8 * v35); k; k = (__int64 *)k[2] )
              {
                if ( *((_DWORD *)k + 6) == v30 )
                {
                  v55 = *k;
                  v57[0] = 0;
                  inited = XWinRT::StringEquals::operator()(v29, v55, newString, v57);
                  if ( inited < 0 )
                    goto LABEL_45;
                  if ( v57[0] )
                  {
                    k[1] = (__int64)v59;
                    goto LABEL_42;
                  }
                  v30 = length[0];
                }
              }
            }
            if ( *(_QWORD *)(v6 + 80) )
            {
LABEL_38:
              if ( *(_QWORD *)(v6 + 144) )
              {
LABEL_39:
                v37 = *(_QWORD *)(v6 + 144);
                if ( v37 )
                {
                  v38 = v68;
                  *(_QWORD *)(v6 + 144) = *(_QWORD *)(v37 + 16);
                  *(_QWORD *)v37 = newString;
                  *(_DWORD *)(v37 + 24) = v30;
                  ++*(_QWORD *)(v6 + 88);
                  *(_QWORD *)(v37 + 16) = *(_QWORD *)(*(_QWORD *)(v6 + 80) + 8 * v38);
                  *(_QWORD *)(*(_QWORD *)(v6 + 80) + 8 * v38) = v37;
                  if ( *(_QWORD *)(v6 + 88) <= *(_QWORD *)(v6 + 112)
                    || *(_DWORD *)(v6 + 128)
                    || (v56 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::PickSize(v6 + 72),
                        inited = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Rehash(
                                   v6 + 72,
                                   v56),
                        inited >= 0) )
                  {
                    *(_QWORD *)(v37 + 8) = v59;
LABEL_42:
                    newString = 0;
                    inited = 0;
                    v59 = 0;
                  }
                }
                else
                {
                  inited = -2147418113;
                }
              }
              else
              {
                v45 = *(unsigned int *)(v6 + 132);
                v44 = 32 * v45;
                *(_QWORD *)length = 0;
                if ( is_mul_ok(v45, 0x20u) && v44 + 8 >= v44 )
                {
                  v50 = o_malloc_0(v44 + 8);
                  if ( v50 )
                  {
                    *v50 = *(_QWORD *)(v6 + 136);
                    *(_QWORD *)(v6 + 136) = v50;
                    v51 = *(_DWORD *)(v6 + 132) - 1;
                    for ( m = &v50[4 * (unsigned int)v51 + 1]; v51 >= 0; --v51 )
                    {
                      m[2] = *(_QWORD *)(v6 + 144);
                      *(_QWORD *)(v6 + 144) = m;
                      m -= 4;
                    }
                    goto LABEL_39;
                  }
                }
                inited = -2147024882;
              }
            }
            else
            {
              v46 = *(unsigned int *)(v6 + 96);
              LOBYTE(v32) = 1;
              v57[0] = 0;
              inited = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::InitHashTable(
                         v6 + 72,
                         v46,
                         v32,
                         v57);
              if ( inited >= 0 )
              {
                if ( v57[0] )
                {
                  v30 = length[0];
                  goto LABEL_38;
                }
                inited = -2147024882;
              }
            }
            v17 = 0;
LABEL_46:
            if ( v6 != -160 )
            {
              v39 = (RTL_SRWLOCK *)(v6 + 168);
              if ( *(_DWORD *)(v6 + 160) == 1 )
                LODWORD(v39->Ptr) += 0x10000000;
              else
                ReleaseSRWLockExclusive(v39);
            }
            v15 = v69;
LABEL_50:
            WindowsDeleteString(v18);
            WindowsDeleteString(v59);
            v59 = 0;
            if ( inited >= 0 )
              inited = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
                         0,
                         *(unsigned __int8 *)(v6 + 185),
                         v6,
                         v17 != 0 ? 3 : 1,
                         v15);
            goto LABEL_52;
          }
          inited = -2147024882;
        }
LABEL_45:
        v17 = 0;
        goto LABEL_46;
      }
      v59 = 0;
      goto LABEL_50;
    }
LABEL_52:
    WindowsDeleteString(newString);
    newString = 0;
    if ( inited >= 0 )
    {
      inited = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v62 + 64LL))(v62, &v75);
      if ( inited >= 0 )
        continue;
    }
    goto LABEL_54;
  }
  v67 = 0;
  *a2 = v6;
LABEL_54:
  if ( v64 )
    WindowsDeleteString(v64);
  if ( string )
    WindowsDeleteString(string);
LABEL_58:
  v40 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
  }
  RoVariant::~RoVariant((RoVariant *)&v70);
  v41 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v66;
  if ( v66 )
  {
    v66 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(&v67);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800161b8  mov     [rsp-8+arg_0], rbx
0x1800161bd  mov     [rsp-8+arg_8], rdx
0x1800161c2  push    rbp
0x1800161c3  push    rsi
0x1800161c4  push    rdi
0x1800161c5  push    r12
0x1800161c7  push    r13
0x1800161c9  push    r14
0x1800161cb  push    r15
0x1800161cd  lea     rbp, [rsp-27h]
0x1800161d2  sub     rsp, 0C0h
0x1800161d9  mov     rdi, rcx
0x1800161dc  xor     r12d, r12d
0x1800161df  lea     rcx, [rbp+57h+var_70]
0x1800161e3  mov     [rbp+57h+var_70], r12
0x1800161e7  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(void)
0x1800161ec  lea     r8, [rbp+57h+var_70]
0x1800161f0  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>> * *)
0x1800161f5  mov     [rbp+57h+var_78], r12
0x1800161f9  mov     esi, eax
0x1800161fb  mov     [rbp+57h+var_98], r12
0x1800161ff  mov     [rbp+57h+arg_18], r12b
0x180016203  test    eax, eax
0x180016205  jns     loc_1800166F4
0x18001620b  mov     [rbp+57h+var_58], r12
0x18001620f  mov     [rbp+57h+var_50], r12d
0x180016213  mov     [rbp+57h+var_A0], r12
0x180016217  mov     [rbp+57h+string], r12
0x18001621b  mov     [rbp+57h+var_88], r12
0x18001621f  test    esi, esi
0x180016221  js      loc_1800165D8
0x180016227  mov     r14, [rbp+57h+var_70]
0x18001622b  cmp     [rbp+57h+arg_18], r12b
0x18001622f  jz      loc_180016836
0x180016235  mov     rbx, [rbp+57h+var_98]
0x180016239  mov     rcx, [rbp+57h+var_A0]
0x18001623d  mov     rax, [rbx]
0x180016240  mov     rdi, [rax+30h]
0x180016244  test    rcx, rcx
0x180016247  jz      short loc_180016259
0x180016249  mov     [rbp+57h+var_A0], r12
0x18001624d  mov     rdx, [rcx]
0x180016250  mov     rax, [rdx+10h]
0x180016254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016259  lea     rdx, [rbp+57h+var_A0]
0x18001625d  mov     rcx, rbx
0x180016260  mov     rax, rdi
0x180016263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016268  mov     esi, eax
0x18001626a  test    eax, eax
0x18001626c  js      loc_1800165BA
0x180016272  mov     rdi, [rbp+57h+var_A0]
0x180016276  mov     rcx, [rbp+57h+string]; string
0x18001627a  mov     rax, [rdi]
0x18001627d  mov     rbx, [rax+30h]
0x180016281  call    cs:__imp_WindowsDeleteString
0x180016287  lea     rdx, [rbp+57h+string]
0x18001628b  mov     [rbp+57h+string], r12
0x18001628f  mov     rcx, rdi
0x180016292  mov     rax, rbx
0x180016295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001629a  mov     esi, eax
0x18001629c  test    eax, eax
0x18001629e  js      loc_1800165BA
0x1800162a4  mov     rcx, [rbp+57h+var_A0]
0x1800162a8  lea     rdx, [rbp+57h+var_58]
0x1800162ac  mov     rax, [rcx]
0x1800162af  mov     [rbp+57h+var_48], rdx
0x1800162b3  lea     rdx, [rbp+57h+var_40]
0x1800162b7  mov     [rbp+57h+var_40], r12
0x1800162bb  mov     rax, [rax+38h]
0x1800162bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162c4  lea     rcx, [rbp+57h+var_48]; this
0x1800162c8  mov     esi, eax
0x1800162ca  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x1800162cf  mov     eax, esi
0x1800162d1  shr     eax, 1Fh
0x1800162d4  xor     al, 1
0x1800162d6  jz      short loc_18001630E
0x1800162d8  mov     rcx, [rbp+57h+var_88]; string
0x1800162dc  mov     rdi, [rbp+57h+var_58]
0x1800162e0  mov     ebx, [rbp+57h+var_50]
0x1800162e3  call    cs:__imp_WindowsDeleteString
0x1800162e9  mov     [rbp+57h+var_88], r12
0x1800162ed  cmp     ebx, 7
0x1800162f0  jnz     loc_180016866
0x1800162f6  mov     rax, [rdi]
0x1800162f9  lea     rdx, [rbp+57h+var_88]
0x1800162fd  mov     rcx, rdi
0x180016300  mov     rax, [rax+98h]
0x180016307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001630c  mov     esi, eax
0x18001630e  test    esi, esi
0x180016310  js      loc_1800165BA
0x180016316  mov     rdi, [rbp+57h+string]
0x18001631a  mov     rbx, [rbp+57h+var_88]
0x18001631e  mov     [rbp+57h+var_60], rdi
0x180016322  cmp     [r14+0B8h], r12b
0x180016329  jz      loc_18001667A
0x18001632f  lea     rdx, [rbp+57h+newString]; newString
0x180016333  mov     [rbp+57h+newString], r12
0x180016337  mov     rcx, rdi; string
0x18001633a  call    cs:__imp_WindowsDuplicateString
0x180016340  mov     esi, eax
0x180016342  test    eax, eax
0x180016344  js      loc_18001658A
0x18001634a  lea     rdx, [rbp+57h+var_B0]; newString
0x18001634e  mov     [rbp+57h+arg_10], r12b
0x180016352  mov     rcx, rbx; string
0x180016355  mov     r15b, r12b
0x180016358  call    cs:__imp_WindowsDuplicateString
0x18001635e  mov     esi, eax
0x180016360  mov     rbx, r12
0x180016363  test    eax, eax
0x180016365  js      loc_1800166B8
0x18001636b  lea     rdi, [r14+0A0h]
0x180016372  cmp     dword ptr [rdi], 1
0x180016375  lea     rcx, [r14+0A8h]; SRWLock
0x18001637c  jz      loc_1800168B6
0x180016382  call    cs:__imp_AcquireSRWLockExclusive
0x180016388  movzx   edx, byte ptr [r14+0BAh]
0x180016390  lea     r8, [r14+0BCh]
0x180016397  lea     rcx, [rbp+57h+var_C0]
0x18001639b  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800163a0  lea     rcx, [r14+0B0h]; this
0x1800163a7  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x1800163ac  mov     rcx, [rbp+57h+newString]; string
0x1800163b0  lea     rdx, [rbp+57h+length]; length
0x1800163b4  mov     [rbp+57h+length], r12d
0x1800163b8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800163be  mov     r8d, [rbp+57h+length]
0x1800163c2  mov     esi, 811C9DC5h
0x1800163c7  mov     rdx, r12
0x1800163ca  add     r8, r8
0x1800163cd  jz      short loc_1800163E3
0x1800163cf  movzx   ecx, byte ptr [rdx+rax]
0x1800163d3  inc     rdx
0x1800163d6  xor     ecx, esi
0x1800163d8  imul    esi, ecx, 1000193h
0x1800163de  cmp     rdx, r8
0x1800163e1  jb      short loc_1800163CF
0x1800163e3  mov     r15, [r14+50h]
0x1800163e7  test    r15, r15
0x1800163ea  jz      short loc_180016401
0x1800163ec  xor     edx, edx
0x1800163ee  mov     eax, esi
0x1800163f0  div     dword ptr [r14+60h]
0x1800163f4  mov     r15, [r15+rdx*8]
0x1800163f8  test    r15, r15
0x1800163fb  jnz     loc_180016667
0x180016401  mov     r15, r12
0x180016404  mov     ecx, r12d
0x180016407  test    ecx, ecx
0x180016409  mov     esi, ecx
0x18001640b  mov     r13, r12
0x18001640e  cmovns  esi, r12d
0x180016412  cmovns  r13, r15
0x180016416  test    esi, esi
0x180016418  js      loc_180016528
0x18001641e  test    r13, r13
0x180016421  jnz     loc_180016846
0x180016427  cmp     qword ptr [r14+58h], 7FFFFFFFh
0x18001642f  jz      loc_180016523
0x180016435  mov     rcx, [rbp+57h+newString]; string
0x180016439  lea     rdx, [rbp+57h+var_90]; length
0x18001643d  mov     [rbp+57h+var_90], r12d
0x180016441  call    cs:__imp_WindowsGetStringRawBuffer
0x180016447  mov     r8d, [rbp+57h+var_90]
0x18001644b  mov     esi, 811C9DC5h
0x180016450  mov     [rbp+57h+length], esi
0x180016453  mov     rdx, r12
0x180016456  add     r8, r8
0x180016459  jz      short loc_180016472
0x18001645b  movzx   ecx, byte ptr [rdx+rax]
0x18001645f  inc     rdx
0x180016462  xor     ecx, esi
0x180016464  imul    esi, ecx, 1000193h
0x18001646a  cmp     rdx, r8
0x18001646d  jb      short loc_18001645B
0x18001646f  mov     [rbp+57h+length], esi
0x180016472  mov     r15, [r14+50h]
0x180016476  xor     edx, edx
0x180016478  mov     eax, esi
0x18001647a  div     dword ptr [r14+60h]
0x18001647e  mov     [rbp+57h+var_68], edx
0x180016481  test    r15, r15
0x180016484  jz      short loc_180016493
0x180016486  mov     r15, [r15+rdx*8]
0x18001648a  test    r15, r15
0x18001648d  jnz     loc_18001676B
0x180016493  xor     r15d, r15d
0x180016496  mov     r13, r12
0x180016499  lea     r12, [r14+48h]
0x18001649d  cmp     [r14+50h], r15
0x1800164a1  jz      loc_1800166C1
0x1800164a7  cmp     [r14+90h], r15
0x1800164ae  jz      loc_18001668C
0x1800164b4  mov     r15, [r14+90h]
0x1800164bb  test    r15, r15
0x1800164be  jz      loc_180016652
0x1800164c4  mov     rax, [r15+10h]
0x1800164c8  mov     r8d, [rbp+57h+var_68]
0x1800164cc  mov     [r14+90h], rax
0x1800164d3  mov     rax, [rbp+57h+newString]
0x1800164d7  mov     [r15], rax
0x1800164da  mov     [r15+18h], esi
0x1800164de  inc     qword ptr [r14+58h]
0x1800164e2  mov     rax, [r14+50h]
0x1800164e6  mov     rdx, [rax+r8*8]
0x1800164ea  mov     [r15+10h], rdx
0x1800164ee  mov     rax, [r14+50h]
0x1800164f2  mov     [rax+r8*8], r15
0x1800164f6  mov     rdx, [r14+58h]
0x1800164fa  cmp     rdx, [r14+70h]
0x1800164fe  ja      loc_180016884
0x180016504  xor     r12d, r12d
0x180016507  mov     r13, r15
0x18001650a  mov     rax, [rbp+57h+var_B0]
0x18001650e  mov     [r13+8], rax
0x180016512  mov     [rbp+57h+newString], r12
0x180016516  mov     esi, r12d
0x180016519  mov     [rbp+57h+var_B0], r12
0x18001651d  mov     r15b, [rbp+57h+arg_10]
0x180016521  jmp     short loc_18001652B
0x180016523  mov     esi, 8007000Eh
0x180016528  mov     r15b, r12b
0x18001652b  test    rdi, rdi
0x18001652e  jz      short loc_180016543
0x180016530  cmp     dword ptr [rdi], 1
0x180016533  lea     rcx, [rdi+8]; SRWLock
0x180016537  jz      loc_1800168DF
0x18001653d  call    cs:__imp_ReleaseSRWLockExclusive
0x180016543  mov     rdi, [rbp+57h+var_60]
0x180016547  mov     rcx, rbx; string
0x18001654a  call    cs:__imp_WindowsDeleteString
0x180016550  mov     rcx, [rbp+57h+var_B0]; string
0x180016554  call    cs:__imp_WindowsDeleteString
0x18001655a  mov     [rbp+57h+var_B0], r12
0x18001655e  test    esi, esi
0x180016560  js      short loc_18001658A
0x180016562  movzx   edx, byte ptr [r14+0B9h]
0x18001656a  neg     r15b
0x18001656d  movzx   ecx, [rbp+57h+arg_10]
0x180016571  mov     r8, r14
0x180016574  sbb     r9d, r9d
0x180016577  mov     [rsp+0F0h+var_D0], rdi
0x18001657c  and     r9d, 2
0x180016580  inc     r9d
0x180016583  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180016588  mov     esi, eax
0x18001658a  mov     rcx, [rbp+57h+newString]; string
0x18001658e  call    cs:__imp_WindowsDeleteString
0x180016594  mov     [rbp+57h+newString], r12
0x180016598  test    esi, esi
0x18001659a  js      short loc_1800165BA
0x18001659c  mov     rcx, [rbp+57h+var_98]
0x1800165a0  lea     rdx, [rbp+57h+arg_18]
0x1800165a4  mov     rax, [rcx]
0x1800165a7  mov     rax, [rax+40h]
0x1800165ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165b0  mov     esi, eax
0x1800165b2  test    eax, eax
0x1800165b4  jns     loc_18001622B
0x1800165ba  mov     rcx, [rbp+57h+var_88]; string
0x1800165be  test    rcx, rcx
0x1800165c1  jz      short loc_1800165C9
0x1800165c3  call    cs:__imp_WindowsDeleteString
0x1800165c9  mov     rcx, [rbp+57h+string]; string
0x1800165cd  test    rcx, rcx
0x1800165d0  jz      short loc_1800165D8
0x1800165d2  call    cs:__imp_WindowsDeleteString
0x1800165d8  mov     rcx, [rbp+57h+var_A0]
0x1800165dc  test    rcx, rcx
0x1800165df  jz      short loc_1800165F1
0x1800165e1  mov     [rbp+57h+var_A0], r12
0x1800165e5  mov     rax, [rcx]
0x1800165e8  mov     rax, [rax+10h]
0x1800165ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165f1  lea     rcx, [rbp+57h+var_58]; this
0x1800165f5  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800165fa  mov     rcx, [rbp+57h+var_98]
0x1800165fe  test    rcx, rcx
0x180016601  jz      short loc_180016613
0x180016603  mov     [rbp+57h+var_98], r12
0x180016607  mov     rax, [rcx]
0x18001660a  mov     rax, [rax+10h]
0x18001660e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016613  mov     rcx, [rbp+57h+var_78]
0x180016617  test    rcx, rcx
0x18001661a  jz      short loc_18001662C
0x18001661c  mov     [rbp+57h+var_78], r12
0x180016620  mov     rax, [rcx]
0x180016623  mov     rax, [rax+10h]
0x180016627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001662c  lea     rcx, [rbp+57h+var_70]
0x180016630  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(void)
0x180016635  mov     rbx, [rsp+0F0h+arg_0]
0x18001663d  mov     eax, esi
0x18001663f  add     rsp, 0C0h
0x180016646  pop     r15
  ... truncated ...
```

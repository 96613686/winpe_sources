# Microsoft::Windows::Performance::CElfImageEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002dea0`
- end: `0x18002e6a2`
- name: `?OnAfterEvents@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `2050`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800085b8`
- `0x18000e390`
- `0x1800143b8`
- `0x1800185cc`
- `0x180018660`
- `0x18001cc68`
- `0x18002c15c`
- `0x18002c9ac`
- `0x18002d3d0`
- `0x18002d6d8`
- `0x18002dea0`
- `0x18002ebd8`
- `0x18002ed18`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!wcschr` at `0x18002e2a4`
- `msvcrt!wcschr` at `0x18002e2e6`
- `msvcrt!wcschr` at `0x18002e2a4`
- `msvcrt!wcschr` at `0x18002e2e6`
- `msvcrt!malloc` at `0x18002e1cb`
- `msvcrt!malloc` at `0x18002e233`
- `msvcrt!malloc` at `0x18002e1cb`
- `msvcrt!malloc` at `0x18002e233`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e11a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e650`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e11a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e650`
- `KERNEL32!QueryDosDeviceW` at `0x18002df3f`
- `KERNEL32!QueryDosDeviceW` at `0x18002df3f`
- `bcrypt!BCryptGetProperty` at `0x18002e18f`
- `bcrypt!BCryptGetProperty` at `0x18002e203`
- `bcrypt!BCryptGetProperty` at `0x18002e18f`
- `bcrypt!BCryptGetProperty` at `0x18002e203`
- `bcrypt!BCryptCreateHash` at `0x18002e265`
- `bcrypt!BCryptCreateHash` at `0x18002e265`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002e153`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002e153`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CElfImageEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CElfImageEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v5; // r12
  unsigned int v6; // esi
  __int64 v7; // rdx
  unsigned int v8; // r13d
  WCHAR *v9; // r15
  DWORD DosDeviceW; // eax
  __int64 *v11; // rax
  _QWORD *v12; // rbx
  char *v13; // rdi
  char *v14; // rcx
  signed __int64 v15; // r9
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rcx
  unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  int v21; // edx
  int v22; // r8d
  volatile signed __int32 *v23; // rsi
  __int64 v24; // rax
  _QWORD *v25; // rdx
  _QWORD *v26; // rdx
  __int64 v27; // r8
  size_t v28; // rcx
  size_t v29; // rcx
  NTSTATUS v30; // eax
  char v31; // cl
  __int64 *v32; // rbx
  __int64 v33; // rcx
  wchar_t *v34; // rax
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rcx
  wchar_t *v38; // rax
  __int64 v39; // rdi
  __int64 v40; // rax
  __int64 *v41; // rcx
  __int64 v42; // rsi
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 *v47; // rax
  _QWORD *v48; // r15
  unsigned __int16 *v49; // rcx
  __int64 v50; // r10
  __int64 v51; // rcx
  unsigned __int16 *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rdx
  int v55; // eax
  int v56; // edi
  int v57; // r12d
  __int64 *v58; // rcx
  __int64 v59; // rdi
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  _QWORD *v63; // rdx
  _QWORD *v64; // rdx
  int v65; // eax
  __int64 *i; // rax
  __int64 *v67; // rcx
  __int64 v68; // rcx
  ULONG pcbResult[2]; // [rsp+40h] [rbp-79h] BYREF
  _QWORD *v71; // [rsp+48h] [rbp-71h] BYREF
  __int64 v72; // [rsp+50h] [rbp-69h]
  unsigned int v73; // [rsp+58h] [rbp-61h]
  char *v74; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v75; // [rsp+68h] [rbp-51h]
  LPWSTR lpTargetPath[2]; // [rsp+70h] [rbp-49h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+80h] [rbp-39h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+88h] [rbp-31h]
  UCHAR pbOutput[4]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v80; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v81; // [rsp+A8h] [rbp-11h]
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v82; // [rsp+B0h] [rbp-9h]
  __int64 v83; // [rsp+B8h] [rbp-1h]
  WCHAR DeviceName[4]; // [rsp+C0h] [rbp+7h] BYREF

  v83 = -2;
  v75 = a4;
  v73 = a3;
  v5 = this;
  v82 = this;
  v6 = 0;
  v72 = 0;
  v71 = (_QWORD *)std::_Tree_alloc<0,std::_Tree_base_types<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>>::_Buyheadnode();
  wcscpy(DeviceName, L"_:");
  LOWORD(pcbResult[0]) = 0;
  *(_OWORD *)lpTargetPath = 0;
  phHash = 0;
  std::vector<unsigned short>::_Construct_n(lpTargetPath, v7, pcbResult);
  DeviceName[0] = 65;
  v8 = 1;
  v9 = lpTargetPath[0];
  do
  {
    DosDeviceW = QueryDosDeviceW(DeviceName, v9, lpTargetPath[1] - v9);
    if ( DosDeviceW > 1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v74,
        v9,
        DosDeviceW - 2);
      v11 = (__int64 *)v71[1];
      v12 = v71;
      v13 = v74;
      if ( !*((_BYTE *)v11 + 25) )
      {
        if ( !v74 )
          goto LABEL_122;
        do
        {
          v14 = (char *)v11[4];
          v15 = v74 - v14;
          do
          {
            v16 = *(unsigned __int16 *)&v14[v15];
            v17 = *(unsigned __int16 *)v14 - v16;
            if ( v17 )
              break;
            v14 += 2;
          }
          while ( v16 );
          if ( v17 >= 0 )
          {
            v12 = v11;
            v11 = (__int64 *)*v11;
          }
          else
          {
            v11 = (__int64 *)v11[2];
          }
        }
        while ( !*((_BYTE *)v11 + 25) );
      }
      if ( v12 == v71 )
        goto LABEL_18;
      v18 = v12[4];
      if ( !v18 )
LABEL_122:
        ATL::AtlThrowImpl(-2147467259);
      v19 = (unsigned __int16 *)v74;
      v20 = v18 - (_QWORD)v74;
      do
      {
        v21 = *(unsigned __int16 *)((char *)v19 + v20);
        v22 = *v19 - v21;
        if ( v22 )
          break;
        ++v19;
      }
      while ( v21 );
      if ( v22 < 0 )
      {
LABEL_18:
        v23 = (volatile signed __int32 *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
        v80 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v13 - 24) + 24;
        v81 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v23) + 24;
        v24 = std::_Tree_buy<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::_Buynode<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(
                &v71,
                &v80);
        std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,0>>::_Insert_hint<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>> &,std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *> *>(
          (unsigned int)&v71,
          (unsigned int)pcbResult,
          (_DWORD)v12,
          v24 + 32,
          v24);
        v12 = *(_QWORD **)pcbResult;
        v25 = (_QWORD *)(v81 - 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v81 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
        v26 = (_QWORD *)(v80 - 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v80 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
        if ( _InterlockedExchangeAdd(v23 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23, v23);
        v6 = 0;
      }
      v27 = -1;
      do
        ++v27;
      while ( DeviceName[v27] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(v12 + 5, DeviceName, v27);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 - 3) + 8LL))(*((_QWORD *)v13 - 3));
    }
    ++DeviceName[0];
  }
  while ( DeviceName[0] != 91 );
  if ( v9 )
    operator delete(v9);
  if ( *((_QWORD *)v5 + 9) )
  {
    LOBYTE(lpTargetPath[0]) = 0;
    *(_OWORD *)pbHashObject = 0;
    if ( BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&lpTargetPath[1], L"SHA256", 0, 0x20u) < 0 )
      goto LABEL_49;
    *(_DWORD *)DeviceName = 0;
    pcbResult[0] = 0;
    if ( BCryptGetProperty(lpTargetPath[1], L"ObjectLength", (PUCHAR)DeviceName, 4u, pcbResult, 0) < 0
      || pcbResult[0] != 4 )
    {
      goto LABEL_49;
    }
    v28 = *(unsigned int *)DeviceName;
    if ( *(_DWORD *)DeviceName )
    {
      if ( !(0xFFFFFFFFFFFFFFFFuLL / *(unsigned int *)DeviceName) )
        goto LABEL_49;
    }
    else
    {
      v28 = 0;
    }
    pbHashObject[0] = (PUCHAR)malloc(v28);
    if ( pbHashObject[0]
      && BCryptGetProperty(lpTargetPath[1], L"HashDigestLength", pbOutput, 4u, pcbResult, 0) >= 0
      && pcbResult[0] == 4 )
    {
      v29 = *(unsigned int *)pbOutput;
      if ( !*(_DWORD *)pbOutput )
      {
        v29 = 0;
        goto LABEL_45;
      }
      if ( 0xFFFFFFFFFFFFFFFFuLL / *(unsigned int *)pbOutput )
      {
LABEL_45:
        pbHashObject[1] = (PUCHAR)malloc(v29);
        if ( pbHashObject[1] )
        {
          v30 = BCryptCreateHash(lpTargetPath[1], &phHash, pbHashObject[0], *(ULONG *)DeviceName, 0, 0, 0x20u);
          v31 = (char)lpTargetPath[0];
          if ( v30 >= 0 )
            v31 = 1;
          LOBYTE(lpTargetPath[0]) = v31;
        }
      }
    }
LABEL_49:
    v32 = (__int64 *)**((_QWORD **)v5 + 8);
    while ( 1 )
    {
      if ( v32 == *((__int64 **)v5 + 8) )
      {
        Microsoft::Windows::Performance::CryptographicHasher::~CryptographicHasher((Microsoft::Windows::Performance::CryptographicHasher *)lpTargetPath);
        goto LABEL_116;
      }
      v33 = v32[4];
      if ( *(int *)(v33 - 16) <= 1 )
        break;
      v34 = wcschr((const wchar_t *)(v33 + 2), 0x5Cu);
      if ( v34 )
        v35 = ((__int64)v34 - v32[4]) >> 1;
      else
        LODWORD(v35) = -1;
      v36 = v35 + 1;
      if ( v36 >= 0 )
        goto LABEL_58;
LABEL_105:
      if ( !*((_BYTE *)v32 + 25) )
      {
        i = (__int64 *)v32[2];
        if ( *((_BYTE *)i + 25) )
        {
          for ( i = (__int64 *)v32[1]; !*((_BYTE *)i + 25) && v32 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v32 = i;
LABEL_114:
          v32 = i;
        }
        else
        {
          v67 = (__int64 *)*i;
          if ( *(_BYTE *)(*i + 25) )
            goto LABEL_114;
          do
          {
            v32 = v67;
            v67 = (__int64 *)*v67;
          }
          while ( !*((_BYTE *)v67 + 25) );
        }
      }
    }
    v36 = 0;
LABEL_58:
    v37 = v32[4];
    if ( v36 < *(_DWORD *)(v37 - 16) )
    {
      v38 = wcschr((const wchar_t *)(v37 + 2LL * v36), 0x5Cu);
      if ( v38 )
      {
        v39 = ((__int64)v38 - v32[4]) >> 1;
        if ( (_DWORD)v39 != -1 )
        {
          if ( (int)v39 >= 0 )
            v6 = ((__int64)v38 - v32[4]) >> 1;
          v40 = v32[4];
          v41 = (__int64 *)(v40 - 24);
          if ( (signed int)v6 < *(_DWORD *)(v40 - 16) )
          {
            v45 = *v41;
            if ( !v45 || (v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 32LL))(v45)) == 0 )
              v46 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
            ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(pcbResult, v32[4], v6, v46);
            v42 = *(_QWORD *)pcbResult;
          }
          else
          {
            v42 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v41) + 24;
            *(_QWORD *)pcbResult = v42;
          }
          v47 = (__int64 *)v71[1];
          v48 = v71;
          if ( !*((_BYTE *)v47 + 25) )
          {
            if ( !v42 )
              goto LABEL_123;
            do
            {
              v49 = (unsigned __int16 *)v47[4];
              v50 = v42 - (_QWORD)v49;
              do
              {
                v43 = *(unsigned __int16 *)((char *)v49 + v50);
                v44 = *v49 - (unsigned int)v43;
                if ( (_DWORD)v44 )
                  break;
                ++v49;
              }
              while ( (_DWORD)v43 );
              if ( (int)v44 >= 0 )
              {
                v48 = v47;
                v47 = (__int64 *)*v47;
              }
              else
              {
                v47 = (__int64 *)v47[2];
              }
            }
            while ( !*((_BYTE *)v47 + 25) );
          }
          if ( v48 == v71 )
            goto LABEL_84;
          v51 = v48[4];
          if ( !v51 )
LABEL_123:
            ATL::AtlThrowImpl(-2147467259);
          v52 = (unsigned __int16 *)v42;
          v53 = v51 - v42;
          do
          {
            v43 = *(unsigned __int16 *)((char *)v52 + v53);
            v44 = *v52 - (unsigned int)v43;
            if ( (_DWORD)v44 )
              break;
            ++v52;
          }
          while ( (_DWORD)v43 );
          if ( (int)v44 < 0 )
LABEL_84:
            v48 = v71;
          if ( v48 != v71 )
          {
            v54 = v32[4];
            v55 = *(_DWORD *)(v54 - 16) - v39;
            v56 = 0;
            if ( v55 >= 0 )
              v56 = v55;
            v57 = 0;
            if ( *(int *)(v54 - 16) >= 0 )
              v57 = *(_DWORD *)(v54 - 16);
            v58 = (__int64 *)(v54 - 24);
            if ( v56 < v57 )
            {
              v60 = *v58;
              if ( !v60 || (v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 32LL))(v60)) == 0 )
                v44 = ((__int64 (__fastcall *)(void ***, __int64, __int64, __int64))ATL::g_strmgr[4])(
                        &ATL::g_strmgr,
                        v54,
                        v43,
                        v44);
              ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(
                &v74,
                v32[4] + 2 * (v57 - (__int64)v56),
                (unsigned int)v56,
                v44);
              v59 = (__int64)v74;
            }
            else
            {
              v59 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v58) + 24;
              v74 = (char *)v59;
            }
            v61 = *(_QWORD *)(v48[5] - 24LL);
            if ( !v61 || (v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v61 + 32LL))(v61)) == 0 )
            {
              v62 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
              if ( !v62 )
                ATL::AtlThrowImpl(-2147467259);
            }
            *(_QWORD *)DeviceName = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 24LL))(v62) + 24;
            ATL::CSimpleStringT<unsigned short,0>::Concatenate(
              DeviceName,
              v48[5],
              *(unsigned int *)(v48[5] - 16LL),
              v59,
              *(_DWORD *)(v59 - 16));
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v59 - 24 + 16), 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v59 - 24) + 8LL))(*(_QWORD *)(v59 - 24));
            v5 = v82;
            (*(void (__fastcall **)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, WCHAR *, LPWSTR *, union _LARGE_INTEGER, unsigned int))(*(_QWORD *)v82 + 152LL))(
              v82,
              DeviceName,
              lpTargetPath,
              a2,
              v73);
            v63 = (_QWORD *)(*(_QWORD *)DeviceName - 24LL);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)DeviceName - 24LL + 16), 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v63 + 8LL))(*v63);
          }
          v64 = (_QWORD *)(v42 - 24);
          v65 = _InterlockedExchangeAdd((volatile signed __int32 *)(v42 - 24 + 16), 0xFFFFFFFF);
          v6 = 0;
          if ( v65 <= 1 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v64 + 8LL))(*v64);
        }
      }
    }
    goto LABEL_105;
  }
LABEL_116:
  v68 = *((_QWORD *)v5 + 1);
  if ( v68 )
    v8 = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v68 + 96LL))(
           v68,
           a2,
           v73,
           v75);
  if ( v8 == -2147467263 )
    v8 = 0;
  std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,0>>::_Erase(
    &v71,
    v71[1]);
  v71[1] = v71;
  *v71 = v71;
  v71[2] = v71;
  v72 = 0;
  operator delete(v71);
  return v8;
}

```

## disassembly

```asm
0x18002dea0  push    rbp
0x18002dea2  push    rbx
0x18002dea3  push    rsi
0x18002dea4  push    rdi
0x18002dea5  push    r12
0x18002dea7  push    r13
0x18002dea9  push    r14
0x18002deab  push    r15
0x18002dead  lea     rbp, [rsp-1Fh]
0x18002deb2  sub     rsp, 0D8h
0x18002deb9  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x18002dec1  mov     rax, cs:__security_cookie
0x18002dec8  xor     rax, rsp
0x18002decb  mov     [rbp+57h+var_48], rax
0x18002decf  mov     [rbp+57h+var_A8], r9d
0x18002ded3  mov     [rbp+57h+var_B8], r8d
0x18002ded7  mov     r14, rdx
0x18002deda  mov     r12, rcx
0x18002dedd  mov     [rbp+57h+var_60], rcx
0x18002dee1  xor     esi, esi
0x18002dee3  mov     [rbp+57h+var_C8], rsi
0x18002dee7  mov     [rbp+57h+var_C0], rsi
0x18002deeb  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>>::_Buyheadnode(void)
0x18002def0  mov     [rbp+57h+var_C8], rax
0x18002def4  lea     eax, [rsi+5Fh]
0x18002def7  mov     [rbp+57h+DeviceName], ax
0x18002defb  mov     dword ptr [rbp+57h+DeviceName+2], 3Ah ; ':'
0x18002df02  mov     word ptr [rbp+57h+var_D0], si
0x18002df06  xorps   xmm0, xmm0
0x18002df09  movdqu  xmmword ptr [rbp+57h+lpTargetPath], xmm0
0x18002df0e  mov     [rbp+57h+phHash], rsi
0x18002df12  lea     r8, [rbp+57h+var_D0]
0x18002df16  lea     rcx, [rbp+57h+lpTargetPath]
0x18002df1a  call    ?_Construct_n@?$vector@GV?$allocator@G@std@@@std@@QEAAX_KPEBG@Z; std::vector<ushort>::_Construct_n(unsigned __int64,ushort const *)
0x18002df1f  lea     eax, [rsi+41h]
0x18002df22  mov     [rbp+57h+DeviceName], ax
0x18002df26  lea     r13d, [rsi+1]
0x18002df2a  mov     r15, [rbp+57h+lpTargetPath]
0x18002df2e  mov     r8, [rbp+57h+lpTargetPath+8]
0x18002df32  sub     r8, r15
0x18002df35  sar     r8, 1; ucchMax
0x18002df38  mov     rdx, r15; lpTargetPath
0x18002df3b  lea     rcx, [rbp+57h+DeviceName]; lpDeviceName
0x18002df3f  call    cs:__imp_QueryDosDeviceW
0x18002df46  nop     dword ptr [rax+rax+00h]
0x18002df4b  cmp     eax, r13d
0x18002df4e  jbe     loc_18002E0FC
0x18002df54  lea     r8d, [rax-2]
0x18002df58  mov     rdx, r15
0x18002df5b  lea     rcx, [rbp+57h+var_B0]
0x18002df5f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x18002df64  mov     r10, [rbp+57h+var_C8]
0x18002df68  mov     rax, [r10+8]
0x18002df6c  mov     rbx, r10
0x18002df6f  mov     rdi, [rbp+57h+var_B0]
0x18002df73  cmp     [rax+19h], sil
0x18002df77  jnz     short loc_18002DFB9
0x18002df79  test    rdi, rdi
0x18002df7c  jz      loc_18002E68C
0x18002df82  mov     rcx, [rax+20h]
0x18002df86  mov     r9, rdi
0x18002df89  sub     r9, rcx
0x18002df8c  movzx   r8d, word ptr [rcx]
0x18002df90  movzx   edx, word ptr [rcx+r9]
0x18002df95  sub     r8d, edx
0x18002df98  jnz     short loc_18002DFA2
0x18002df9a  add     rcx, 2
0x18002df9e  test    edx, edx
0x18002dfa0  jnz     short loc_18002DF8C
0x18002dfa2  test    r8d, r8d
0x18002dfa5  jns     short loc_18002DFAD
0x18002dfa7  mov     rax, [rax+10h]
0x18002dfab  jmp     short loc_18002DFB3
0x18002dfad  mov     rbx, rax
0x18002dfb0  mov     rax, [rax]
0x18002dfb3  cmp     [rax+19h], sil
0x18002dfb7  jz      short loc_18002DF82
0x18002dfb9  cmp     rbx, r10
0x18002dfbc  jz      short loc_18002DFEF
0x18002dfbe  mov     rcx, [rbx+20h]
0x18002dfc2  test    rcx, rcx
0x18002dfc5  jz      loc_18002E68C
0x18002dfcb  mov     rax, rdi
0x18002dfce  sub     rcx, rdi
0x18002dfd1  movzx   r8d, word ptr [rax]
0x18002dfd5  movzx   edx, word ptr [rax+rcx]
0x18002dfd9  sub     r8d, edx
0x18002dfdc  jnz     short loc_18002DFE6
0x18002dfde  add     rax, 2
0x18002dfe2  test    edx, edx
0x18002dfe4  jnz     short loc_18002DFD1
0x18002dfe6  test    r8d, r8d
0x18002dfe9  jns     loc_18002E0BD
0x18002dfef  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002dff6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002dffd  mov     rax, [rax+18h]
0x18002e001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e006  mov     rsi, rax
0x18002e009  lea     rcx, [rdi-18h]
0x18002e00d  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002e012  add     rax, 18h
0x18002e016  mov     [rbp+57h+var_70], rax
0x18002e01a  mov     rcx, rsi
0x18002e01d  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002e022  add     rax, 18h
0x18002e026  mov     [rbp+57h+var_68], rax
0x18002e02a  lea     rdx, [rbp+57h+var_70]
0x18002e02e  lea     rcx, [rbp+57h+var_C8]
0x18002e032  call    ??$_Buynode@U?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@?$_Tree_buy@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@$$QEAU?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@1@@Z; std::_Tree_buy<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::_Buynode<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &&)
0x18002e037  lea     r9, [rax+20h]
0x18002e03b  mov     [rsp+110h+pcbResult], rax
0x18002e040  mov     r8, rbx
0x18002e043  lea     rdx, [rbp+57h+var_D0]
0x18002e047  lea     rcx, [rbp+57h+var_C8]
0x18002e04b  call    ??$_Insert_hint@AEAU?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@@1@AEAU?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,0>>::_Insert_hint<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>,std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x18002e050  mov     rbx, qword ptr [rbp+57h+var_D0]
0x18002e054  mov     rdx, [rbp+57h+var_68]
0x18002e058  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002e05c  or      eax, 0FFFFFFFFh
0x18002e05f  lock xadd [rdx+10h], eax
0x18002e064  sub     eax, r13d
0x18002e067  jg      short loc_18002E078
0x18002e069  mov     rcx, [rdx]
0x18002e06c  mov     rax, [rcx]
0x18002e06f  mov     rax, [rax+8]
0x18002e073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e078  mov     rdx, [rbp+57h+var_70]
0x18002e07c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002e080  or      eax, 0FFFFFFFFh
0x18002e083  lock xadd [rdx+10h], eax
0x18002e088  sub     eax, r13d
0x18002e08b  jg      short loc_18002E09C
0x18002e08d  mov     rcx, [rdx]
0x18002e090  mov     rax, [rcx]
0x18002e093  mov     rax, [rax+8]
0x18002e097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e09c  or      eax, 0FFFFFFFFh
0x18002e09f  lock xadd [rsi+10h], eax
0x18002e0a4  sub     eax, r13d
0x18002e0a7  jg      short loc_18002E0BB
0x18002e0a9  mov     rcx, [rsi]
0x18002e0ac  mov     rax, [rcx]
0x18002e0af  mov     rdx, rsi
0x18002e0b2  mov     rax, [rax+8]
0x18002e0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0bb  xor     esi, esi
0x18002e0bd  lea     rax, [rbp+57h+DeviceName]
0x18002e0c1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002e0c5  inc     r8
0x18002e0c8  cmp     [rax+r8*2], si
0x18002e0cd  jnz     short loc_18002E0C5
0x18002e0cf  lea     rcx, [rbx+28h]
0x18002e0d3  lea     rdx, [rbp+57h+DeviceName]
0x18002e0d7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002e0dc  lea     rdx, [rdi-18h]
0x18002e0e0  or      eax, 0FFFFFFFFh
0x18002e0e3  lock xadd [rdx+10h], eax
0x18002e0e8  sub     eax, r13d
0x18002e0eb  jg      short loc_18002E0FC
0x18002e0ed  mov     rcx, [rdx]
0x18002e0f0  mov     rax, [rcx]
0x18002e0f3  mov     rax, [rax+8]
0x18002e0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0fc  movzx   eax, [rbp+57h+DeviceName]
0x18002e100  add     ax, r13w
0x18002e104  mov     [rbp+57h+DeviceName], ax
0x18002e108  cmp     ax, 5Bh ; '['
0x18002e10c  jnz     loc_18002DF2E
0x18002e112  test    r15, r15
0x18002e115  jz      short loc_18002E126
0x18002e117  mov     rcx, r15
0x18002e11a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002e121  nop     dword ptr [rax+rax+00h]
0x18002e126  cmp     [r12+48h], rsi
0x18002e12b  jz      loc_18002E5F1
0x18002e131  mov     byte ptr [rbp+57h+lpTargetPath], sil
0x18002e135  xorps   xmm0, xmm0
0x18002e138  movdqu  xmmword ptr [rbp+57h+pbHashObject], xmm0
0x18002e13d  mov     edi, 20h ; ' '
0x18002e142  mov     r9d, edi; dwFlags
0x18002e145  xor     r8d, r8d; pszImplementation
0x18002e148  lea     rdx, pszAlgId; "SHA256"
0x18002e14f  lea     rcx, [rbp+57h+lpTargetPath+8]; phAlgorithm
0x18002e153  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002e15a  nop     dword ptr [rax+rax+00h]
0x18002e15f  test    eax, eax
0x18002e161  js      loc_18002E27E
0x18002e167  mov     dword ptr [rbp+57h+DeviceName], esi
0x18002e16a  mov     [rbp+57h+var_D0], esi
0x18002e16d  mov     [rsp+110h+dwFlags], esi; dwFlags
0x18002e171  lea     rax, [rbp+57h+var_D0]
0x18002e175  mov     [rsp+110h+pcbResult], rax; pcbResult
0x18002e17a  lea     ebx, [rdi-1Ch]
0x18002e17d  mov     r9d, ebx; cbOutput
0x18002e180  lea     r8, [rbp+57h+DeviceName]; pbOutput
0x18002e184  lea     rdx, pszProperty; "ObjectLength"
0x18002e18b  mov     rcx, [rbp+57h+lpTargetPath+8]; hObject
0x18002e18f  call    cs:__imp_BCryptGetProperty
0x18002e196  nop     dword ptr [rax+rax+00h]
0x18002e19b  test    eax, eax
0x18002e19d  js      loc_18002E27E
0x18002e1a3  cmp     [rbp+57h+var_D0], ebx
0x18002e1a6  jnz     loc_18002E27E
0x18002e1ac  mov     ecx, dword ptr [rbp+57h+DeviceName]; Size
0x18002e1af  test    rcx, rcx
0x18002e1b2  jnz     short loc_18002E1B9
0x18002e1b4  mov     rcx, rsi
0x18002e1b7  jmp     short loc_18002E1CB
0x18002e1b9  xor     edx, edx
0x18002e1bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e1bf  div     rcx
0x18002e1c2  cmp     rax, r13
0x18002e1c5  jb      loc_18002E27E
0x18002e1cb  call    cs:__imp_malloc
0x18002e1d2  nop     dword ptr [rax+rax+00h]
0x18002e1d7  mov     [rbp+57h+pbHashObject], rax
0x18002e1db  test    rax, rax
0x18002e1de  jz      loc_18002E27E
0x18002e1e4  mov     [rsp+110h+dwFlags], esi; dwFlags
0x18002e1e8  lea     rax, [rbp+57h+var_D0]
0x18002e1ec  mov     [rsp+110h+pcbResult], rax; pcbResult
0x18002e1f1  mov     r9d, ebx; cbOutput
0x18002e1f4  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18002e1f8  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18002e1ff  mov     rcx, [rbp+57h+lpTargetPath+8]; hObject
0x18002e203  call    cs:__imp_BCryptGetProperty
0x18002e20a  nop     dword ptr [rax+rax+00h]
0x18002e20f  test    eax, eax
0x18002e211  js      short loc_18002E27E
0x18002e213  cmp     [rbp+57h+var_D0], ebx
0x18002e216  jnz     short loc_18002E27E
0x18002e218  mov     ecx, dword ptr [rbp+57h+pbOutput]; Size
0x18002e21b  test    rcx, rcx
0x18002e21e  jnz     short loc_18002E225
0x18002e220  mov     rcx, rsi
0x18002e223  jmp     short loc_18002E233
0x18002e225  xor     edx, edx
0x18002e227  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e22b  div     rcx
0x18002e22e  cmp     rax, r13
0x18002e231  jb      short loc_18002E27E
0x18002e233  call    cs:__imp_malloc
0x18002e23a  nop     dword ptr [rax+rax+00h]
0x18002e23f  mov     [rbp+57h+pbHashObject+8], rax
0x18002e243  test    rax, rax
0x18002e246  jz      short loc_18002E27E
0x18002e248  mov     [rsp+110h+var_E0], edi; dwFlags
0x18002e24c  mov     [rsp+110h+dwFlags], esi; cbSecret
0x18002e250  mov     [rsp+110h+pcbResult], rsi; pbSecret
0x18002e255  mov     r9d, dword ptr [rbp+57h+DeviceName]; cbHashObject
0x18002e259  mov     r8, [rbp+57h+pbHashObject]; pbHashObject
0x18002e25d  lea     rdx, [rbp+57h+phHash]; phHash
0x18002e261  mov     rcx, [rbp+57h+lpTargetPath+8]; hAlgorithm
0x18002e265  call    cs:__imp_BCryptCreateHash
0x18002e26c  nop     dword ptr [rax+rax+00h]
0x18002e271  movzx   ecx, byte ptr [rbp+57h+lpTargetPath]
0x18002e275  test    eax, eax
0x18002e277  cmovns  ecx, r13d
0x18002e27b  mov     byte ptr [rbp+57h+lpTargetPath], cl
0x18002e27e  mov     rbx, [r12+40h]
0x18002e283  mov     rbx, [rbx]
0x18002e286  cmp     rbx, [r12+40h]
0x18002e28b  jz      loc_18002E5E8
0x18002e291  mov     rcx, [rbx+20h]
0x18002e295  cmp     [rcx-10h], r13d
0x18002e299  jle     short loc_18002E2CC
0x18002e29b  mov     edx, 5Ch ; '\'; Ch
0x18002e2a0  add     rcx, 2; Str
0x18002e2a4  call    cs:__imp_wcschr
0x18002e2ab  nop     dword ptr [rax+rax+00h]
0x18002e2b0  test    rax, rax
0x18002e2b3  jnz     short loc_18002E2BA
0x18002e2b5  or      eax, 0FFFFFFFFh
0x18002e2b8  jmp     short loc_18002E2C1
0x18002e2ba  sub     rax, [rbx+20h]
0x18002e2be  sar     rax, 1
0x18002e2c1  add     eax, r13d
0x18002e2c4  js      loc_18002E596
0x18002e2ca  jmp     short loc_18002E2CE
0x18002e2cc  mov     eax, esi
0x18002e2ce  mov     rcx, [rbx+20h]
0x18002e2d2  cmp     eax, [rcx-10h]
0x18002e2d5  jge     loc_18002E596
0x18002e2db  mov     edx, 5Ch ; '\'; Ch
0x18002e2e0  cdqe
0x18002e2e2  lea     rcx, [rcx+rax*2]; Str
0x18002e2e6  call    cs:__imp_wcschr
0x18002e2ed  nop     dword ptr [rax+rax+00h]
0x18002e2f2  mov     rdi, rax
0x18002e2f5  test    rax, rax
0x18002e2f8  jz      loc_18002E596
0x18002e2fe  sub     rdi, [rbx+20h]
0x18002e302  sar     rdi, 1
0x18002e305  cmp     edi, 0FFFFFFFFh
0x18002e308  jz      loc_18002E596
0x18002e30e  test    edi, edi
0x18002e310  cmovns  esi, edi
0x18002e313  mov     rax, [rbx+20h]
0x18002e317  lea     rcx, [rax-18h]
0x18002e31b  cmp     esi, [rax-10h]
  ... truncated ...
```

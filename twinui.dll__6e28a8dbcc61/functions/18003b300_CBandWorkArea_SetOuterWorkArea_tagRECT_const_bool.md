# CBandWorkArea::SetOuterWorkArea(tagRECT const *,bool)

- ea: `0x18003b300`
- end: `0x18003bcf6`
- name: `?SetOuterWorkArea@CBandWorkArea@@UEAA_NPEBUtagRECT@@_N@Z`
- size: `2550`
- prototype: `bool(CBandWorkArea *__hidden this, const struct tagRECT *, bool)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b7e8`
- `0x18003b300`
- `0x18003c5e4`
- `0x18003c65c`
- `0x18003c8c8`
- `0x18003c92c`
- `0x1800e9c10`
- `0x18013d330`
- `0x18013d354`
- `0x18013df8c`
- `0x18013e516`
- `0x18013e55e`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b349`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b390`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b818`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bc67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b349`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b390`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b818`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bc67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b37a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b3cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b847`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003bc82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b37a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b3cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b847`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003bc82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003b680`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003b78d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003b92b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003ba41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003b680`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003b78d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003b92b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003ba41`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x18003bc5e`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x18003bc5e`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18003b3ac`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18003b3c4`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18003b83e`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18003b3ac`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18003b3c4`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18003b83e`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18003b35a`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18003b39c`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18003b827`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18003bc73`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18003b35a`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18003b39c`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18003b827`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18003bc73`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18003b3d7`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18003b3d7`

## pseudocode

```c
bool __fastcall CBandWorkArea::SetOuterWorkArea(RTL_SRWLOCK *this, const struct tagRECT *a2, char a3)
{
  RTL_SRWLOCK *v3; // rsi
  RTL_SRWLOCK *v4; // r12
  const RECT *v6; // r15
  const RECT *v7; // r14
  BOOL v8; // edi
  char v9; // bl
  RTL_SRWLOCK *v10; // rax
  int v11; // r13d
  Microsoft::WRL::FtmBase *v12; // rax
  Microsoft::WRL::FtmBase *v13; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v14; // rcx
  unsigned __int64 Ptr; // rsi
  int v16; // ebx
  bool v17; // di
  unsigned int v18; // ebx
  __int64 v19; // rcx
  bool result; // al
  unsigned int i; // esi
  __int64 v22; // rcx
  unsigned __int64 v23; // rbx
  char *v24; // rax
  char *v25; // r14
  unsigned __int64 v26; // rax
  __int64 *v27; // r15
  __int64 *v28; // r12
  unsigned __int64 v29; // rcx
  __int64 v30; // rsi
  unsigned __int64 v31; // rsi
  unsigned __int64 v32; // r8
  unsigned __int64 v33; // rbx
  char *v34; // rax
  char *v35; // r14
  unsigned __int64 v36; // rax
  __int64 *v37; // rdx
  __int64 v38; // rcx
  RTL_SRWLOCK *v39; // r15
  CGITCallbackArray *v40; // rax
  CGITCallbackArray *v41; // rax
  unsigned __int64 v42; // rdi
  CGITCallbackArray *v43; // rbx
  unsigned __int64 v44; // r8
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rsi
  char *v47; // rax
  char *v48; // r14
  unsigned __int64 v49; // rax
  int v50; // eax
  __int64 *v51; // r15
  __int64 *v52; // r12
  unsigned __int64 v53; // rcx
  __int64 v54; // rdi
  unsigned __int64 v55; // rdi
  unsigned __int64 v56; // r8
  unsigned __int64 v57; // rsi
  unsigned int v58; // edi
  char *v59; // rax
  char *v60; // r14
  unsigned __int64 v61; // rax
  int v62; // eax
  __int64 *v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // rdi
  int (__fastcall *v66)(__int64, _QWORD, GUID *, Microsoft::WRL::FtmBase **); // rbx
  Microsoft::WRL::FtmBase *v67; // rcx
  Microsoft::WRL::FtmBase *v68; // rcx
  int v69; // [rsp+20h] [rbp-49h]
  bool v70; // [rsp+30h] [rbp-39h]
  char v71; // [rsp+31h] [rbp-38h]
  Microsoft::WRL::FtmBase *v72; // [rsp+38h] [rbp-31h] BYREF
  __int64 v73; // [rsp+40h] [rbp-29h] BYREF
  const struct tagRECT *v74; // [rsp+48h] [rbp-21h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-19h]
  RTL_SRWLOCK *v76; // [rsp+58h] [rbp-11h]
  BOOL v77; // [rsp+60h] [rbp-9h]
  RECT rcSrc2; // [rsp+68h] [rbp-1h] BYREF
  struct tagRECT rcDst; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v3 = this + 10;
  v76 = this;
  v4 = this;
  v74 = a2;
  SRWLock = this + 10;
  v6 = a2;
  AcquireSRWLockExclusive(this + 10);
  v7 = (const RECT *)&v4[5];
  v77 = EqualRect(v6, (const RECT *)&v4[5]);
  v8 = v77;
  if ( a3 || (v10 = v4 + 9, LOBYTE(v4[9].Ptr)) || !v77 )
  {
    v9 = 1;
    v10 = v4 + 9;
  }
  else
  {
    v9 = 0;
  }
  LOBYTE(v10->Ptr) = 0;
  ReleaseSRWLockExclusive(v3);
  if ( !v9 )
    return 0;
  v70 = 0;
  AcquireSRWLockExclusive(v3);
  if ( !EqualRect(v6, (const RECT *)&v4[5]) )
  {
    CopyRect((LPRECT)&v4[5], v6);
    v70 = 1;
  }
  rcDst = 0;
  CopyRect(&rcDst, (const RECT *)&v4[5]);
  ReleaseSRWLockExclusive(v3);
  v11 = -2147024882;
  if ( !IsRectEmpty(&rcDst) )
  {
    v71 = 1;
    AcquireSRWLockShared_0(v4 + 12);
    v73 = 0;
    v12 = (Microsoft::WRL::FtmBase *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
    v72 = v12;
    v13 = v12;
    if ( !v12 )
    {
      Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(&v72);
      v16 = -2147024882;
LABEL_17:
      ReleaseSRWLockShared_0(v4 + 12);
      if ( v16 >= 0 )
      {
        LODWORD(v74) = 0;
        if ( (*(int (__fastcall **)(__int64, const struct tagRECT **))(*(_QWORD *)v73 + 24LL))(v73, &v74) >= 0 )
        {
          v17 = 1;
          v18 = 0;
          do
          {
            if ( v18 >= (unsigned int)v74 )
              break;
            v72 = 0;
            if ( (*(int (__fastcall **)(__int64, _QWORD, GUID *, Microsoft::WRL::FtmBase **))(*(_QWORD *)v73 + 32LL))(
                   v73,
                   v18,
                   &GUID_05088755_ef51_4684_8f7c_b07c8d5d5f39,
                   &v72) >= 0 )
            {
              rcSrc2 = 0;
              if ( (*(int (__fastcall **)(Microsoft::WRL::FtmBase *, struct tagRECT *, RECT *))(*(_QWORD *)v72 + 32LL))(
                     v72,
                     &rcDst,
                     &rcSrc2) >= 0 )
              {
                (*(void (__fastcall **)(Microsoft::WRL::FtmBase *, _QWORD, struct tagRECT *))(*(_QWORD *)v72 + 24LL))(
                  v72,
                  LODWORD(v4[2].Ptr),
                  &rcDst);
                SubtractRect(&rcDst, &rcDst, &rcSrc2);
              }
              AcquireSRWLockExclusive(v3);
              v17 = EqualRect(v6, v7);
              ReleaseSRWLockExclusive(v3);
            }
            v68 = v72;
            if ( v72 )
            {
              v72 = 0;
              (*(void (__fastcall **)(Microsoft::WRL::FtmBase *))(*(_QWORD *)v68 + 16LL))(v68);
            }
            ++v18;
          }
          while ( v17 );
          v71 = v17;
        }
      }
      v19 = v73;
      if ( v73 )
      {
        v73 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      if ( !v71 )
        return 0;
      v8 = v77;
      goto LABEL_70;
    }
    Microsoft::WRL::FtmBase::FtmBase(v12);
    v14 = Microsoft::WRL::Details::ModuleBase::module_;
    *(_QWORD *)v13 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IObjectArray>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'};
    *((_QWORD *)v13 + 4) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IObjectArray>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectArray>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'};
    *((_DWORD *)v13 + 11) = 1;
    if ( v14 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v14 + 8LL))(v14);
    v72 = 0;
    *(_QWORD *)v13 = &CGITCallbackArray::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'};
    *((_QWORD *)v13 + 4) = &CGITCallbackArray::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectArray>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'};
    *((_QWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 7) = 0;
    *((_QWORD *)v13 + 8) = 0;
    *((_QWORD *)v13 + 9) = 0;
    Ptr = (unsigned __int64)v4[14].Ptr;
    if ( !Ptr )
      goto LABEL_15;
    if ( Ptr > 0xFFFFFFFE )
    {
      v16 = -2147024774;
    }
    else
    {
      *(_QWORD *)&rcSrc2.left = 0;
      if ( is_mul_ok(0, 2u) && (*(_QWORD *)&rcSrc2.left = 0, v23 = 8 * Ptr, is_mul_ok(Ptr, 8u)) )
      {
        v24 = (char *)CoTaskMemRealloc(*((LPVOID *)v13 + 6), 8 * Ptr);
        v25 = v24;
        if ( v24 )
        {
          v26 = CTCoAllocPolicy::_CoTaskMemSize(v24);
          if ( v26 > v23 )
            memset_0(&v25[v23], 0, v26 - v23);
          v16 = 0;
        }
        else
        {
          v16 = -2147024882;
        }
        if ( v16 >= 0 )
        {
          *((_QWORD *)v13 + 9) = Ptr;
          *((_QWORD *)v13 + 6) = v25;
          v27 = (__int64 *)v4[13].Ptr;
          v28 = &v27[(__int64)v4[14].Ptr];
          while ( v27 != v28 )
          {
            v29 = *((_QWORD *)v13 + 9);
            v30 = *((_QWORD *)v13 + 7);
            if ( v30 == v29 )
            {
              v31 = v30 + 1;
              v16 = -2147024774;
              if ( v31 > 0xFFFFFFFE )
                goto LABEL_53;
              if ( v31 > v29 )
              {
                *(_QWORD *)&rcSrc2.left = 0;
                v32 = 2 * v29;
                if ( !is_mul_ok(v29, 2u) )
                  goto LABEL_52;
                if ( v29 > 0x1000 )
                  v32 = v29 + 4096;
                if ( v31 <= v32 )
                {
                  v31 = v32;
                  if ( v32 > 0xFFFFFFFE )
                    v31 = 4294967294LL;
                }
                *(_QWORD *)&rcSrc2.left = 0;
                v33 = 8 * v31;
                if ( !is_mul_ok(v31, 8u) )
                {
LABEL_52:
                  v16 = -2147024362;
LABEL_53:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x63,
                    (unsigned int)"shell\\lib\\gitreglist.cpp",
                    (const char *)(unsigned int)v16,
                    v69);
                  v4 = v76;
                  v6 = v74;
                  goto LABEL_54;
                }
                v34 = (char *)CoTaskMemRealloc(*((LPVOID *)v13 + 6), 8 * v31);
                v35 = v34;
                if ( v34 )
                {
                  v36 = CTCoAllocPolicy::_CoTaskMemSize(v34);
                  if ( v36 > v33 )
                    memset_0(&v35[v33], 0, v36 - v33);
                  v16 = 0;
                }
                else
                {
                  v16 = -2147024882;
                }
                if ( v16 < 0 )
                  goto LABEL_53;
                *((_QWORD *)v13 + 9) = v31;
                *((_QWORD *)v13 + 6) = v35;
              }
            }
            v37 = (__int64 *)(*((_QWORD *)v13 + 6) + 8 * (*((_QWORD *)v13 + 7))++);
            if ( v37 )
            {
              v38 = *v27;
              *v37 = *v27;
              if ( v38 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
            }
            ++v27;
          }
          v4 = v76;
          v6 = v74;
LABEL_15:
          v16 = (**(__int64 (__fastcall ***)(Microsoft::WRL::FtmBase *, GUID *, __int64 *))v13)(
                  v13,
                  &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                  &v73);
          (*(void (__fastcall **)(Microsoft::WRL::FtmBase *))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_16:
          v3 = SRWLock;
          v7 = (const RECT *)&v4[5];
          goto LABEL_17;
        }
      }
      else
      {
        v16 = -2147024362;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"shell\\lib\\gitreglist.cpp",
      (const char *)(unsigned int)v16,
      v69);
LABEL_54:
    (*(void (__fastcall **)(Microsoft::WRL::FtmBase *))(*(_QWORD *)v13 + 16LL))(v13);
    Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(&v72);
    goto LABEL_16;
  }
LABEL_70:
  AcquireSRWLockExclusive(v3);
  if ( !EqualRect(&rcDst, (const RECT *)&v4[7]) )
  {
    v70 = 1;
    CopyRect((LPRECT)&v4[7], &rcDst);
  }
  ReleaseSRWLockExclusive(v3);
  result = v70;
  if ( v70 && !v8 )
  {
    v39 = v4 + 24;
    v73 = 0;
    SRWLock = v4 + 24;
    rcDst = 0;
    AcquireSRWLockShared_0(v4 + 24);
    v73 = 0;
    v40 = (CGITCallbackArray *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
    v72 = v40;
    if ( v40 )
    {
      v41 = CGITCallbackArray::CGITCallbackArray(v40);
      v42 = (unsigned __int64)v4[26].Ptr;
      v43 = v41;
      v72 = 0;
      if ( !v42 )
      {
LABEL_28:
        v11 = (**(__int64 (__fastcall ***)(CGITCallbackArray *, GUID *, __int64 *))v43)(
                v43,
                &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                &v73);
        (*(void (__fastcall **)(CGITCallbackArray *))(*(_QWORD *)v43 + 16LL))(v43);
        goto LABEL_29;
      }
      if ( v42 > 0xFFFFFFFE )
      {
        v11 = -2147024774;
      }
      else
      {
        v44 = *((_QWORD *)v41 + 9);
        if ( v42 <= v44 )
          goto LABEL_91;
        v45 = 2 * v44;
        if ( !is_mul_ok(v44, 2u) )
          goto LABEL_26;
        if ( v44 > 0x1000 )
          v45 = v44 + 4096;
        if ( v42 <= v45 )
        {
          v42 = v45;
          if ( v45 > 0xFFFFFFFE )
            v42 = 4294967294LL;
        }
        v46 = 8 * v42;
        if ( is_mul_ok(v42, 8u) )
        {
          v47 = (char *)CoTaskMemRealloc(*((LPVOID *)v41 + 6), 8 * v42);
          v48 = v47;
          if ( v47 )
          {
            v49 = CTCoAllocPolicy::_CoTaskMemSize(v47);
            if ( v49 > v46 )
              memset_0(&v48[v46], 0, v49 - v46);
            v50 = 0;
          }
          else
          {
            v50 = -2147024882;
          }
          if ( v50 >= 0 )
          {
            *((_QWORD *)v43 + 6) = v48;
            *((_QWORD *)v43 + 9) = v42;
LABEL_91:
            v51 = (__int64 *)v4[25].Ptr;
            v52 = &v51[(__int64)v4[26].Ptr];
            while ( v51 != v52 )
            {
              v53 = *((_QWORD *)v43 + 9);
              v54 = *((_QWORD *)v43 + 7);
              if ( v54 == v53 )
              {
                v55 = v54 + 1;
                if ( v55 > 0xFFFFFFFE )
                {
                  v58 = -2147024774;
                  goto LABEL_102;
                }
                if ( v55 > v53 )
                {
                  v56 = 2 * v53;
                  if ( !is_mul_ok(v53, 2u) )
                    goto LABEL_101;
                  if ( v53 > 0x1000 )
                    v56 = v53 + 4096;
                  if ( v55 <= v56 )
                  {
                    v55 = v56;
                    if ( v56 > 0xFFFFFFFE )
                      v55 = 4294967294LL;
                  }
                  v57 = 8 * v55;
                  if ( !is_mul_ok(v55, 8u) )
                  {
LABEL_101:
                    v58 = -2147024362;
LABEL_102:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x63,
                      (unsigned int)"shell\\lib\\gitreglist.cpp",
                      (const char *)v58,
                      v69);
                    v39 = SRWLock;
                    v4 = v76;
                    v11 = v58;
                    goto LABEL_103;
                  }
                  v59 = (char *)CoTaskMemRealloc(*((LPVOID *)v43 + 6), 8 * v55);
                  v60 = v59;
                  if ( v59 )
                  {
                    v61 = CTCoAllocPolicy::_CoTaskMemSize(v59);
                    if ( v61 > v57 )
                      memset_0(&v60[v57], 0, v61 - v57);
                    v62 = 0;
                  }
                  else
                  {
                    v62 = -2147024882;
                  }
                  if ( v62 < 0 )
                  {
                    v58 = v62;
                    goto LABEL_102;
                  }
                  *((_QWORD *)v43 + 6) = v60;
                  *((_QWORD *)v43 + 9) = v55;
                }
              }
              v63 = (__int64 *)(*((_QWORD *)v43 + 6) + 8 * (*((_QWORD *)v43 + 7))++);
              if ( v63 )
              {
                v64 = *v51;
                *v63 = *v51;
                if ( v64 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 8LL))(v64);
              }
              ++v51;
            }
            v39 = SRWLock;
            v4 = v76;
            goto LABEL_28;
          }
          v11 = v50;
        }
        else
        {
LABEL_26:
          v11 = -2147024362;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"shell\\lib\\gitreglist.cpp",
        (const char *)(unsigned int)v11,
        v69);
LABEL_103:
      if ( v43 )
        (*(void (__fastcall **)(CGITCallbackArray *))(*(_QWORD *)v43 + 16LL))(v43);
    }
    Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(&v72);
LABEL_29:
    ReleaseSRWLockShared_0(v39);
    if ( v11 >= 0 )
    {
      LODWORD(v74) = 0;
      if ( (*(int (__fastcall **)(__int64, const struct tagRECT **))(*(_QWORD *)v73 + 24LL))(v73, &v74) >= 0 )
      {
        for ( i = 0; i < (unsigned int)v74; ++i )
        {
          v65 = v73;
          v72 = 0;
          v66 = *(int (__fastcall **)(__int64, _QWORD, GUID *, Microsoft::WRL::FtmBase **))(*(_QWORD *)v73 + 32LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v72);
          if ( v66(v65, i, &GUID_6a5e657d_223a_4875_838b_c311ed73523b, &v72) >= 0 )
            (*(void (__fastcall **)(Microsoft::WRL::FtmBase *, _QWORD, struct tagRECT *))(*(_QWORD *)v72 + 24LL))(
              v72,
              LODWORD(v4[2].Ptr),
              &rcDst);
          v67 = v72;
          if ( v72 )
          {
            v72 = 0;
            (*(void (__fastcall **)(Microsoft::WRL::FtmBase *))(*(_QWORD *)v67 + 16LL))(v67);
          }
        }
      }
    }
    v22 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return v70;
  }
  return result;
}

```

## disassembly

```asm
0x18003b300  mov     [rsp-8+arg_10], rbx
0x18003b305  push    rbp
0x18003b306  push    rsi
0x18003b307  push    rdi
0x18003b308  push    r12
0x18003b30a  push    r13
0x18003b30c  push    r14
0x18003b30e  push    r15
0x18003b310  lea     rbp, [rsp-27h]
0x18003b315  sub     rsp, 90h
0x18003b31c  mov     rax, cs:__security_cookie
0x18003b323  xor     rax, rsp
0x18003b326  mov     [rbp+57h+var_38], rax
0x18003b32a  lea     rsi, [rcx+50h]
0x18003b32e  mov     [rbp+57h+var_68], rcx
0x18003b332  mov     r12, rcx
0x18003b335  mov     [rbp+57h+var_78], rdx
0x18003b339  mov     rcx, rsi; SRWLock
0x18003b33c  mov     [rbp+57h+SRWLock], rsi
0x18003b340  mov     bl, r8b
0x18003b343  mov     r15, rdx
0x18003b346  xor     r13d, r13d
0x18003b349  call    cs:__imp_AcquireSRWLockExclusive
0x18003b34f  lea     r14, [r12+28h]
0x18003b354  mov     rcx, r15; lprc1
0x18003b357  mov     rdx, r14; lprc2
0x18003b35a  call    cs:__imp_EqualRect
0x18003b360  mov     [rbp+57h+var_60], eax
0x18003b363  mov     edi, eax
0x18003b365  test    bl, bl
0x18003b367  jz      loc_18003BB88
0x18003b36d  mov     bl, 1
0x18003b36f  lea     rax, [r12+48h]
0x18003b374  mov     rcx, rsi; SRWLock
0x18003b377  mov     [rax], r13b
0x18003b37a  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b380  test    bl, bl
0x18003b382  jz      loc_18003BADB
0x18003b388  xor     ebx, ebx
0x18003b38a  mov     rcx, rsi; SRWLock
0x18003b38d  mov     [rbp+57h+var_90], bl
0x18003b390  call    cs:__imp_AcquireSRWLockExclusive
0x18003b396  mov     rdx, r14; lprc2
0x18003b399  mov     rcx, r15; lprc1
0x18003b39c  call    cs:__imp_EqualRect
0x18003b3a2  test    eax, eax
0x18003b3a4  jnz     short loc_18003B3B6
0x18003b3a6  mov     rdx, r15; lprcSrc
0x18003b3a9  mov     rcx, r14; lprcDst
0x18003b3ac  call    cs:__imp_CopyRect
0x18003b3b2  mov     [rbp+57h+var_90], 1
0x18003b3b6  xorps   xmm0, xmm0
0x18003b3b9  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18003b3bd  mov     rdx, r14; lprcSrc
0x18003b3c0  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x18003b3c4  call    cs:__imp_CopyRect
0x18003b3ca  mov     rcx, rsi; SRWLock
0x18003b3cd  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b3d3  lea     rcx, [rbp+57h+rcDst]; lprc
0x18003b3d7  call    cs:__imp_IsRectEmpty
0x18003b3dd  mov     r13d, 8007000Eh
0x18003b3e3  test    eax, eax
0x18003b3e5  jnz     loc_18003BAD3
0x18003b3eb  lea     rcx, [r12+60h]; SRWLock
0x18003b3f0  mov     [rbp+57h+var_8F], 1
0x18003b3f4  mov     [rbp+57h+var_80], rbx
0x18003b3f8  call    AcquireSRWLockShared_0
0x18003b3fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b404  mov     [rbp+57h+var_80], rbx
0x18003b408  mov     ecx, 50h ; 'P'; unsigned __int64
0x18003b40d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003b412  mov     [rbp+57h+var_88], rax
0x18003b416  mov     rdi, rax
0x18003b419  test    rax, rax
0x18003b41c  jz      loc_18003BBA6
0x18003b422  mov     rcx, rax; this
0x18003b425  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18003b42a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003b431  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIObjectArray@@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIObjectArray@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IObjectArray>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'}
0x18003b438  mov     [rdi], rax
0x18003b43b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIObjectArray@@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectArray@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIObjectArray@@@234@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IObjectArray>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectArray>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'}
0x18003b442  mov     [rdi+20h], rax
0x18003b446  mov     dword ptr [rdi+2Ch], 1
0x18003b44d  test    rcx, rcx
0x18003b450  jz      short loc_18003B45E
0x18003b452  mov     rax, [rcx]
0x18003b455  mov     rax, [rax+8]
0x18003b459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b45e  lea     rax, ??_7CGITCallbackArray@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIObjectArray@@@Details@23@@Details@WRL@Microsoft@@@; const CGITCallbackArray::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'}
0x18003b465  mov     [rbp+57h+var_88], rbx
0x18003b469  mov     [rdi], rax
0x18003b46c  lea     rax, ??_7CGITCallbackArray@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectArray@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIObjectArray@@@234@@Details@WRL@Microsoft@@@; const CGITCallbackArray::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectArray>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'}
0x18003b473  mov     [rdi+20h], rax
0x18003b477  mov     [rdi+30h], rbx
0x18003b47b  mov     [rdi+38h], rbx
0x18003b47f  mov     [rdi+40h], rbx
0x18003b483  mov     [rdi+48h], rbx
0x18003b487  mov     rsi, [r12+70h]
0x18003b48c  test    rsi, rsi
0x18003b48f  jz      short loc_18003B4DA
0x18003b491  mov     r8d, 0FFFFFFFEh
0x18003b497  cmp     rsi, r8
0x18003b49a  ja      loc_18003BBE3
0x18003b4a0  mov     eax, 2
0x18003b4a5  mov     qword ptr [rbp+57h+rcSrc2.left], rbx
0x18003b4a9  mul     rbx
0x18003b4ac  test    rdx, rdx
0x18003b4af  jz      loc_18003B646
0x18003b4b5  mov     ebx, 80070216h
0x18003b4ba  mov     rcx, [rbp+5Fh]; this
0x18003b4be  lea     r8, aShellLibGitreg; "shell\\lib\\gitreglist.cpp"
0x18003b4c5  mov     r9d, ebx; char *
0x18003b4c8  mov     edx, 5Fh ; '_'; void *
0x18003b4cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b4d2  test    ebx, ebx
0x18003b4d4  js      loc_18003B769
0x18003b4da  mov     rax, [rdi]
0x18003b4dd  lea     r8, [rbp+57h+var_80]
0x18003b4e1  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18003b4e8  mov     rcx, rdi
0x18003b4eb  mov     rax, [rax]
0x18003b4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4f3  mov     ebx, eax
0x18003b4f5  mov     rcx, rdi
0x18003b4f8  mov     rax, [rdi]
0x18003b4fb  mov     rax, [rax+10h]
0x18003b4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b504  mov     rsi, [rbp+57h+SRWLock]
0x18003b508  lea     r14, [r12+28h]
0x18003b50d  lea     rcx, [r12+60h]; SRWLock
0x18003b512  call    ReleaseSRWLockShared_0
0x18003b517  test    ebx, ebx
0x18003b519  js      short loc_18003B54D
0x18003b51b  mov     rcx, [rbp+57h+var_80]
0x18003b51f  lea     rdx, [rbp+57h+var_78]
0x18003b523  mov     dword ptr [rbp+57h+var_78], 0
0x18003b52a  mov     rax, [rcx]
0x18003b52d  mov     rax, [rax+18h]
0x18003b531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b536  test    eax, eax
0x18003b538  js      short loc_18003B54D
0x18003b53a  mov     dil, [rbp+57h+var_8F]
0x18003b53e  xor     ebx, ebx
0x18003b540  cmp     ebx, dword ptr [rbp+57h+var_78]
0x18003b543  jb      loc_18003BBED
0x18003b549  mov     [rbp+57h+var_8F], dil
0x18003b54d  mov     rcx, [rbp+57h+var_80]
0x18003b551  xor     r14d, r14d
0x18003b554  test    rcx, rcx
0x18003b557  jz      short loc_18003B569
0x18003b559  mov     [rbp+57h+var_80], r14
0x18003b55d  mov     rax, [rcx]
0x18003b560  mov     rax, [rax+10h]
0x18003b564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b569  cmp     [rbp+57h+var_8F], r14b
0x18003b56d  jnz     loc_18003B812
0x18003b573  mov     al, r14b
0x18003b576  jmp     loc_18003B61F
0x18003b57b  mov     r13d, 80070216h
0x18003b581  mov     rcx, [rbp+5Fh]; this
0x18003b585  lea     r8, aShellLibGitreg; "shell\\lib\\gitreglist.cpp"
0x18003b58c  mov     r9d, r13d; char *
0x18003b58f  mov     edx, 5Fh ; '_'; void *
0x18003b594  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b599  test    r13d, r13d
0x18003b59c  js      loc_18003BA18
0x18003b5a2  mov     rax, [rbx]
0x18003b5a5  lea     r8, [rbp+57h+var_80]
0x18003b5a9  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18003b5b0  mov     rcx, rbx
0x18003b5b3  mov     rax, [rax]
0x18003b5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5bb  mov     r13d, eax
0x18003b5be  mov     rcx, rbx
0x18003b5c1  mov     rax, [rbx]
0x18003b5c4  mov     rax, [rax+10h]
0x18003b5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5cd  mov     rcx, r15; SRWLock
0x18003b5d0  call    ReleaseSRWLockShared_0
0x18003b5d5  test    r13d, r13d
0x18003b5d8  js      short loc_18003B603
0x18003b5da  mov     rcx, [rbp+57h+var_80]
0x18003b5de  lea     rdx, [rbp+57h+var_78]
0x18003b5e2  mov     dword ptr [rbp+57h+var_78], r14d
0x18003b5e6  mov     rax, [rcx]
0x18003b5e9  mov     rax, [rax+18h]
0x18003b5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5f2  test    eax, eax
0x18003b5f4  js      short loc_18003B603
0x18003b5f6  mov     esi, r14d
0x18003b5f9  cmp     dword ptr [rbp+57h+var_78], r14d
0x18003b5fd  ja      loc_18003BAE3
0x18003b603  mov     rcx, [rbp+57h+var_80]
0x18003b607  test    rcx, rcx
0x18003b60a  jz      short loc_18003B61C
0x18003b60c  mov     [rbp+57h+var_80], r14
0x18003b610  mov     rdx, [rcx]
0x18003b613  mov     rax, [rdx+10h]
0x18003b617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b61c  mov     al, [rbp+57h+var_90]
0x18003b61f  mov     rcx, [rbp+57h+var_38]
0x18003b623  xor     rcx, rsp; StackCookie
0x18003b626  call    __security_check_cookie
0x18003b62b  mov     rbx, [rsp+0C0h+arg_10]
0x18003b633  add     rsp, 90h
0x18003b63a  pop     r15
0x18003b63c  pop     r14
0x18003b63e  pop     r13
0x18003b640  pop     r12
0x18003b642  pop     rdi
0x18003b643  pop     rsi
0x18003b644  pop     rbp
0x18003b645  retn
0x18003b646  mov     ecx, 1000h
0x18003b64b  cmp     rax, rcx
0x18003b64e  cmova   rax, rcx
0x18003b652  cmp     rsi, rax
0x18003b655  ja      short loc_18003B661
0x18003b657  cmp     rax, r8
0x18003b65a  mov     rsi, rax
0x18003b65d  cmova   rsi, r8
0x18003b661  mov     eax, 8
0x18003b666  mov     qword ptr [rbp+57h+rcSrc2.left], rbx
0x18003b66a  mul     rsi
0x18003b66d  mov     rbx, rax
0x18003b670  test    rdx, rdx
0x18003b673  jnz     loc_18003B4B5
0x18003b679  mov     rcx, [rdi+30h]; pv
0x18003b67d  mov     rdx, rax; cb
0x18003b680  call    cs:__imp_CoTaskMemRealloc
0x18003b686  mov     r14, rax
0x18003b689  test    rax, rax
0x18003b68c  jz      loc_18003BB78
0x18003b692  mov     rcx, rax; void *
0x18003b695  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18003b69a  cmp     rax, rbx
0x18003b69d  ja      loc_18003BBB7
0x18003b6a3  xor     ebx, ebx
0x18003b6a5  test    ebx, ebx
0x18003b6a7  js      loc_18003B4BA
0x18003b6ad  mov     [rdi+48h], rsi
0x18003b6b1  mov     [rdi+30h], r14
0x18003b6b5  mov     r15, [r12+68h]
0x18003b6ba  mov     rax, [r12+70h]
0x18003b6bf  lea     r12, [r15+rax*8]
0x18003b6c3  cmp     r15, r12
0x18003b6c6  jz      loc_18003B805
0x18003b6cc  mov     rcx, [rdi+48h]
0x18003b6d0  mov     rsi, [rdi+38h]
0x18003b6d4  cmp     rsi, rcx
0x18003b6d7  jnz     loc_18003B7BE
0x18003b6dd  inc     rsi
0x18003b6e0  mov     r9d, 0FFFFFFFEh
0x18003b6e6  mov     ebx, 8007007Ah
0x18003b6eb  cmp     rsi, r9
0x18003b6ee  ja      short loc_18003B749
0x18003b6f0  cmp     rsi, rcx
0x18003b6f3  jbe     loc_18003B7BE
0x18003b6f9  mov     eax, 2
0x18003b6fe  mov     qword ptr [rbp+57h+rcSrc2.left], 0
0x18003b706  mul     rcx
0x18003b709  mov     r8, rax
0x18003b70c  test    rdx, rdx
0x18003b70f  jnz     short loc_18003B744
0x18003b711  sub     rax, rcx
0x18003b714  cmp     rax, 1000h
0x18003b71a  jbe     short loc_18003B723
0x18003b71c  lea     r8, [rcx+1000h]
0x18003b723  cmp     rsi, r8
0x18003b726  jbe     loc_18003B7F6
0x18003b72c  mov     eax, 8
0x18003b731  mov     qword ptr [rbp+57h+rcSrc2.left], 0
0x18003b739  mul     rsi
0x18003b73c  mov     rbx, rax
0x18003b73f  test    rdx, rdx
0x18003b742  jz      short loc_18003B786
0x18003b744  mov     ebx, 80070216h
0x18003b749  mov     rcx, [rbp+5Fh]; this
0x18003b74d  lea     r8, aShellLibGitreg; "shell\\lib\\gitreglist.cpp"
0x18003b754  mov     r9d, ebx; char *
0x18003b757  mov     edx, 63h ; 'c'; void *
0x18003b75c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b761  mov     r12, [rbp+57h+var_68]
0x18003b765  mov     r15, [rbp+57h+var_78]
0x18003b769  mov     rax, [rdi]
0x18003b76c  mov     rcx, rdi
0x18003b76f  mov     rax, [rax+10h]
0x18003b773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b778  lea     rcx, [rbp+57h+var_88]
0x18003b77c  call    ??1?$MakeAllocator@VSttExperienceManagerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(void)
0x18003b781  jmp     loc_18003B504
0x18003b786  mov     rcx, [rdi+30h]; pv
0x18003b78a  mov     rdx, rbx; cb
0x18003b78d  call    cs:__imp_CoTaskMemRealloc
0x18003b793  mov     r14, rax
0x18003b796  test    rax, rax
0x18003b799  jz      loc_18003BB5D
0x18003b79f  mov     rcx, rax; void *
0x18003b7a2  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18003b7a7  cmp     rax, rbx
  ... truncated ...
```
